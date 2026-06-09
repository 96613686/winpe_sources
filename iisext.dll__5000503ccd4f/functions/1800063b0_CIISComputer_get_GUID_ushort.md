# CIISComputer::get_GUID(ushort * *)

- ea: `0x1800063b0`
- end: `0x1800063cb`
- name: `?get_GUID@CIISComputer@@UEAAJPEAPEAG@Z`
- size: `27`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::get_GUID(CIISComputer *this, unsigned __int16 **a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7));
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x1800063b0  test    rdx, rdx
0x1800063b3  jnz     short loc_1800063BB
0x1800063b5  mov     eax, 80004003h
0x1800063ba  retn
0x1800063bb  mov     rcx, [rcx+38h]
0x1800063bf  mov     rax, [rcx]
0x1800063c2  mov     rax, [rax+48h]
0x1800063c6  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
