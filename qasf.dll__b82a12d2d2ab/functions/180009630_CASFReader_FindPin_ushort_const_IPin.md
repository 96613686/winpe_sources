# CASFReader::FindPin(ushort const *,IPin * *)

- ea: `0x180009630`
- end: `0x180009650`
- name: `?FindPin@CASFReader@@UEAAJPEBGPEAPEAUIPin@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, const unsigned __int16 *, struct IPin **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004920`
- `0x180009630`
- `0x18001f010`

## pseudocode

```c
int __fastcall CASFReader::FindPin(CASFReader *this, const unsigned __int16 *a2, struct IPin **a3)
{
  __int64 v3; // r9

  v3 = *((_QWORD *)this + 55);
  if ( v3 )
    return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, struct IPin **))(*(_QWORD *)v3 + 88LL))(
             *((_QWORD *)this + 55),
             a2,
             a3);
  else
    return CBaseFilter::FindPin(this, a2, a3);
}

```

## disassembly

```asm
0x180009630  mov     r9, [rcx+1B8h]
0x180009637  test    r9, r9
0x18000963a  jz      short loc_18000964B
0x18000963c  mov     rax, [r9]
0x18000963f  mov     rcx, r9; this
0x180009642  mov     rax, [rax+58h]
0x180009646  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000964b  jmp     ?FindPin@CBaseFilter@@UEAAJPEBGPEAPEAUIPin@@@Z; CBaseFilter::FindPin(ushort const *,IPin * *)
```
