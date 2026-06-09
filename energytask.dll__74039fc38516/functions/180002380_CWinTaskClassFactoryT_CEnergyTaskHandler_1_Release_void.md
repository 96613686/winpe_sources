# CWinTaskClassFactoryT<CEnergyTaskHandler,1>::Release(void)

- ea: `0x180002380`
- end: `0x1800023af`
- name: `?Release@?$CWinTaskClassFactoryT@VCEnergyTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002380`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEnergyTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x180002380  push    rbx
0x180002382  sub     rsp, 20h
0x180002386  or      ebx, 0FFFFFFFFh
0x180002389  lock xadd [rcx+8], ebx
0x18000238e  sub     ebx, 1
0x180002391  jnz     short loc_1800023A7
0x180002393  test    rcx, rcx
0x180002396  jz      short loc_1800023A7
0x180002398  mov     rdx, [rcx]
0x18000239b  mov     rax, [rdx+28h]
0x18000239f  lea     edx, [rbx+1]
0x1800023a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a7  mov     eax, ebx
0x1800023a9  add     rsp, 20h
0x1800023ad  pop     rbx
0x1800023ae  retn
```
