# CASFReader::EnumPins(IEnumPins * *)

- ea: `0x180009600`
- end: `0x180009620`
- name: `?EnumPins@CASFReader@@UEAAJPEAPEAUIEnumPins@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, struct IEnumPins **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800048c0`
- `0x180009600`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::EnumPins(CASFReader *this, struct IEnumPins **a2)
{
  __int64 v2; // r8

  v2 = *((_QWORD *)this + 55);
  if ( v2 )
    return (*(__int64 (__fastcall **)(_QWORD, struct IEnumPins **))(*(_QWORD *)v2 + 80LL))(*((_QWORD *)this + 55), a2);
  else
    return CBaseFilter::EnumPins(this, a2);
}

```

## disassembly

```asm
0x180009600  mov     r8, [rcx+1B8h]
0x180009607  test    r8, r8
0x18000960a  jz      short loc_18000961B
0x18000960c  mov     rax, [r8]
0x18000960f  mov     rcx, r8; this
0x180009612  mov     rax, [rax+50h]
0x180009616  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000961b  jmp     ?EnumPins@CBaseFilter@@UEAAJPEAPEAUIEnumPins@@@Z; CBaseFilter::EnumPins(IEnumPins * *)
```
