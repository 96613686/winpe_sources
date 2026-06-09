# CASFReader::GetSyncSource(IReferenceClock * *)

- ea: `0x18000a710`
- end: `0x18000a730`
- name: `?GetSyncSource@CASFReader@@UEAAJPEAPEAUIReferenceClock@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, struct IReferenceClock **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004de0`
- `0x18000a710`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetSyncSource(CASFReader *this, struct IReferenceClock **a2)
{
  __int64 v2; // r8

  v2 = *((_QWORD *)this + 55);
  if ( v2 )
    return (*(__int64 (__fastcall **)(_QWORD, struct IReferenceClock **))(*(_QWORD *)v2 + 72LL))(
             *((_QWORD *)this + 55),
             a2);
  else
    return CBaseFilter::GetSyncSource(this, a2);
}

```

## disassembly

```asm
0x18000a710  mov     r8, [rcx+1B8h]
0x18000a717  test    r8, r8
0x18000a71a  jz      short loc_18000A72B
0x18000a71c  mov     rax, [r8]
0x18000a71f  mov     rcx, r8; this
0x18000a722  mov     rax, [rax+48h]
0x18000a726  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000a72b  jmp     ?GetSyncSource@CBaseFilter@@UEAAJPEAPEAUIReferenceClock@@@Z; CBaseFilter::GetSyncSource(IReferenceClock * *)
```
