# DetailsView::Importer::StreamSource::Read(void *,ulong,ulong *)

- ea: `0x18000f2f0`
- end: `0x18000f313`
- name: `?Read@StreamSource@Importer@DetailsView@@UEAAJPEAXKPEAK@Z`
- size: `35`
- prototype: `__int64 __fastcall(DetailsView::Importer::StreamSource *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f2f0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall DetailsView::Importer::StreamSource::Read(
        DetailsView::Importer::StreamSource *this,
        void *a2,
        __int64 a3,
        unsigned int *a4)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *((_QWORD *)this + 1);
  result = 2147500037LL;
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, void *, __int64, unsigned int *))(*(_QWORD *)v4 + 24LL))(v4, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x18000f2f0  sub     rsp, 38h
0x18000f2f4  mov     rcx, [rcx+8]
0x18000f2f8  mov     eax, 80004005h
0x18000f2fd  test    rcx, rcx
0x18000f300  jz      short loc_18000F30E
0x18000f302  mov     rax, [rcx]
0x18000f305  mov     rax, [rax+18h]
0x18000f309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f30e  add     rsp, 38h
0x18000f312  retn
```
