# CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::Release(void)

- ea: `0x18001cd50`
- end: `0x18001cd7f`
- name: `?Release@?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18001cd50`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::Release(volatile signed __int32 *a1)
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
0x18001cd50  push    rbx
0x18001cd52  sub     rsp, 20h
0x18001cd56  or      ebx, 0FFFFFFFFh
0x18001cd59  lock xadd [rcx+8], ebx
0x18001cd5e  sub     ebx, 1
0x18001cd61  jnz     short loc_18001CD77
0x18001cd63  test    rcx, rcx
0x18001cd66  jz      short loc_18001CD77
0x18001cd68  mov     rdx, [rcx]
0x18001cd6b  mov     rax, [rdx+28h]
0x18001cd6f  lea     edx, [rbx+1]
0x18001cd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd77  mov     eax, ebx
0x18001cd79  add     rsp, 20h
0x18001cd7d  pop     rbx
0x18001cd7e  retn
```
