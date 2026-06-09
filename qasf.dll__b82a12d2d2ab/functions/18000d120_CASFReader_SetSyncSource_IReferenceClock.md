# CASFReader::SetSyncSource(IReferenceClock *)

- ea: `0x18000d120`
- end: `0x18000d140`
- name: `?SetSyncSource@CASFReader@@UEAAJPEAUIReferenceClock@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, struct IReferenceClock *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006940`
- `0x18000d120`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::SetSyncSource(CASFReader *this, struct IReferenceClock *a2)
{
  __int64 v2; // r8

  v2 = *((_QWORD *)this + 55);
  if ( v2 )
    return (*(__int64 (__fastcall **)(_QWORD, struct IReferenceClock *))(*(_QWORD *)v2 + 64LL))(
             *((_QWORD *)this + 55),
             a2);
  else
    return CBaseFilter::SetSyncSource(this, a2);
}

```

## disassembly

```asm
0x18000d120  mov     r8, [rcx+1B8h]
0x18000d127  test    r8, r8
0x18000d12a  jz      short loc_18000D13B
0x18000d12c  mov     rax, [r8]
0x18000d12f  mov     rcx, r8; this
0x18000d132  mov     rax, [rax+40h]
0x18000d136  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d13b  jmp     ?SetSyncSource@CBaseFilter@@UEAAJPEAUIReferenceClock@@@Z; CBaseFilter::SetSyncSource(IReferenceClock *)
```
