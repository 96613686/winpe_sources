# CIISComputer::get_Schema(ushort * *)

- ea: `0x180006440`
- end: `0x18000645b`
- name: `?get_Schema@CIISComputer@@UEAAJPEAPEAG@Z`
- size: `27`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006440`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::get_Schema(CIISComputer *this, unsigned __int16 **a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 96LL))(*((_QWORD *)this + 7));
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180006440  test    rdx, rdx
0x180006443  jnz     short loc_18000644B
0x180006445  mov     eax, 80004003h
0x18000644a  retn
0x18000644b  mov     rcx, [rcx+38h]
0x18000644f  mov     rax, [rcx]
0x180006452  mov     rax, [rax+60h]
0x180006456  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
