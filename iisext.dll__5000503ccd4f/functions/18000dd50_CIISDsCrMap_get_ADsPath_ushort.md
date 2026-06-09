# CIISDsCrMap::get_ADsPath(ushort * *)

- ea: `0x18000dd50`
- end: `0x18000dd6b`
- name: `?get_ADsPath@CIISDsCrMap@@UEAAJPEAPEAG@Z`
- size: `27`
- prototype: `__int64 __fastcall(CIISDsCrMap *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dd50`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::get_ADsPath(CIISDsCrMap *this, unsigned __int16 **a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 80LL))(*((_QWORD *)this + 13));
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x18000dd50  test    rdx, rdx
0x18000dd53  jnz     short loc_18000DD5B
0x18000dd55  mov     eax, 80004003h
0x18000dd5a  retn
0x18000dd5b  mov     rcx, [rcx+68h]
0x18000dd5f  mov     rax, [rcx]
0x18000dd62  mov     rax, [rax+50h]
0x18000dd66  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
