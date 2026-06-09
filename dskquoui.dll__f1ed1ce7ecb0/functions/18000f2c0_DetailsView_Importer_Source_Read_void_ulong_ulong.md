# DetailsView::Importer::Source::Read(void *,ulong,ulong *)

- ea: `0x18000f2c0`
- end: `0x18000f2e3`
- name: `?Read@Source@Importer@DetailsView@@UEAAJPEAXKPEAK@Z`
- size: `35`
- prototype: `__int64 __fastcall(DetailsView::Importer::Source *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f2c0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall DetailsView::Importer::Source::Read(
        DetailsView::Importer::Source *this,
        void *a2,
        __int64 a3,
        unsigned int *a4)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *((_QWORD *)this + 1);
  result = 2147942414LL;
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, void *, __int64, unsigned int *))(*(_QWORD *)v4 + 8LL))(v4, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x18000f2c0  sub     rsp, 38h
0x18000f2c4  mov     rcx, [rcx+8]
0x18000f2c8  mov     eax, 8007000Eh
0x18000f2cd  test    rcx, rcx
0x18000f2d0  jz      short loc_18000F2DE
0x18000f2d2  mov     rax, [rcx]
0x18000f2d5  mov     rax, [rax+8]
0x18000f2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2de  add     rsp, 38h
0x18000f2e2  retn
```
