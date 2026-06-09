# CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyStorageFromIDList(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)

- ea: `0x180016728`
- end: `0x180016814`
- name: `?GetPropertyStorageFromIDList@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002862c`

## callees

- `0x18000d9d8`
- `0x180016728`
- `0x180035010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001678e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001678e`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyStorageFromIDList(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT v4; // ebx
  __int64 PropertyStorage; // rsi
  void *ppv; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v4 = -2147024809;
  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      LODWORD(v8) = 0;
      PropertyStorage = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyStorage(a1, &v8);
      if ( PropertyStorage )
      {
        ppv = 0;
        v4 = PSCreateMemoryPropertyStore(&GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &ppv);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppv + 32LL))(
                 ppv,
                 PropertyStorage,
                 (unsigned int)v8);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1);
            if ( v4 >= 0 )
              v4 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))ppv)(
                     ppv,
                     &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                     a3);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016728  mov     rax, rsp
0x18001672b  mov     [rax+18h], rbx
0x18001672f  mov     [rax+20h], rsi
0x180016733  mov     [rax+10h], rdx
0x180016737  push    rdi
0x180016738  sub     rsp, 20h
0x18001673c  mov     rdi, r8
0x18001673f  mov     ebx, 80070057h
0x180016744  test    rcx, rcx
0x180016747  jz      loc_180016802
0x18001674d  test    r8, r8
0x180016750  jz      loc_180016802
0x180016756  lea     rdx, [rax+10h]
0x18001675a  mov     qword ptr [r8], 0
0x180016761  mov     dword ptr [rax+10h], 0
0x180016768  call    ?GetPropertyStorage@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAPEFBUtagSERIALIZEDPROPSTORAGE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAK@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyStorage(_ITEMIDLIST_RELATIVE const *,ulong *)
0x18001676d  mov     rsi, rax
0x180016770  test    rax, rax
0x180016773  jz      loc_180016802
0x180016779  lea     rdx, [rsp+28h+ppv]; ppv
0x18001677e  mov     [rsp+28h+ppv], 0
0x180016787  lea     rcx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917; riid
0x18001678e  call    cs:__imp_PSCreateMemoryPropertyStore
0x180016794  mov     ebx, eax
0x180016796  test    eax, eax
0x180016798  js      short loc_180016802
0x18001679a  mov     rcx, [rsp+28h+ppv]
0x18001679f  mov     rdx, rsi
0x1800167a2  mov     r8d, dword ptr [rsp+28h+arg_8]
0x1800167a7  mov     rax, [rcx]
0x1800167aa  mov     rax, [rax+20h]
0x1800167ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167b3  mov     ebx, eax
0x1800167b5  test    eax, eax
0x1800167b7  js      short loc_1800167F1
0x1800167b9  mov     rcx, [rsp+28h+ppv]
0x1800167be  mov     edx, 1
0x1800167c3  mov     rax, [rcx]
0x1800167c6  mov     rax, [rax+18h]
0x1800167ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167cf  mov     ebx, eax
0x1800167d1  test    eax, eax
0x1800167d3  js      short loc_1800167F1
0x1800167d5  mov     rcx, [rsp+28h+ppv]
0x1800167da  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800167e1  mov     r8, rdi
0x1800167e4  mov     rax, [rcx]
0x1800167e7  mov     rax, [rax]
0x1800167ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167ef  mov     ebx, eax
0x1800167f1  mov     rcx, [rsp+28h+ppv]
0x1800167f6  mov     rax, [rcx]
0x1800167f9  mov     rax, [rax+10h]
0x1800167fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016802  mov     rsi, [rsp+28h+arg_18]
0x180016807  mov     eax, ebx
0x180016809  mov     rbx, [rsp+28h+arg_10]
0x18001680e  add     rsp, 20h
0x180016812  pop     rdi
0x180016813  retn
```
