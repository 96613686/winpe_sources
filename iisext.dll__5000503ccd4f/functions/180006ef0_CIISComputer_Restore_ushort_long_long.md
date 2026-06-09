# CIISComputer::Restore(ushort *,long,long)

- ea: `0x180006ef0`
- end: `0x180006f18`
- name: `?Restore@CIISComputer@@UEAAJPEAGJJ@Z`
- size: `40`
- prototype: `__int64 __fastcall(CIISComputer *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006ef0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::Restore(CIISComputer *this, unsigned __int16 *a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 232LL))(*((_QWORD *)this + 15));
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180006ef0  sub     rsp, 38h
0x180006ef4  test    rdx, rdx
0x180006ef7  jnz     short loc_180006F00
0x180006ef9  mov     eax, 80004003h
0x180006efe  jmp     short loc_180006F13
0x180006f00  mov     rcx, [rcx+78h]
0x180006f04  mov     rax, [rcx]
0x180006f07  mov     rax, [rax+0E8h]
0x180006f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f13  add     rsp, 38h
0x180006f17  retn
```
