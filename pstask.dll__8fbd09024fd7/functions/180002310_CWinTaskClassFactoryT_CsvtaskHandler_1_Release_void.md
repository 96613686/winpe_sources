# CWinTaskClassFactoryT<CsvtaskHandler,1>::Release(void)

- ea: `0x180002310`
- end: `0x18000233f`
- name: `?Release@?$CWinTaskClassFactoryT@VCsvtaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002310`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CsvtaskHandler,1>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x180002310  push    rbx
0x180002312  sub     rsp, 20h
0x180002316  or      ebx, 0FFFFFFFFh
0x180002319  lock xadd [rcx+8], ebx
0x18000231e  sub     ebx, 1
0x180002321  jnz     short loc_180002337
0x180002323  test    rcx, rcx
0x180002326  jz      short loc_180002337
0x180002328  mov     rdx, [rcx]
0x18000232b  mov     rax, [rdx+28h]
0x18000232f  lea     edx, [rbx+1]
0x180002332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002337  mov     eax, ebx
0x180002339  add     rsp, 20h
0x18000233d  pop     rbx
0x18000233e  retn
```
