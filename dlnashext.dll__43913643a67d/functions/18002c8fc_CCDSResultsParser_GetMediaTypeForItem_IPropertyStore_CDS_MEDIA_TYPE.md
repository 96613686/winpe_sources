# CCDSResultsParser::GetMediaTypeForItem(IPropertyStore *,_CDS_MEDIA_TYPE *)

- ea: `0x18002c8fc`
- end: `0x18002c97f`
- name: `?GetMediaTypeForItem@CCDSResultsParser@@SAJPEAUIPropertyStore@@PEAW4_CDS_MEDIA_TYPE@@@Z`
- size: `131`
- prototype: `__int64 __fastcall(struct IPropertyStore *, enum _CDS_MEDIA_TYPE *)`
- caller_count: `10`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c40c`
- `0x18002d9d0`
- `0x18002da80`
- `0x18002db50`
- `0x18002dec0`
- `0x18002df80`
- `0x18002e360`
- `0x18002e710`
- `0x18002ef70`
- `0x18002f190`

## callees

- `0x18000f91c`
- `0x180014b90`
- `0x180015204`
- `0x18002c8fc`
- `0x18002c988`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c960`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCDSResultsParser::GetMediaTypeForItem(struct IPropertyStore *a1, enum _CDS_MEDIA_TYPE *a2)
{
  int v3; // ebx
  struct _tagpropertykey v5; // [rsp+20h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF
  char v7; // [rsp+68h] [rbp+20h] BYREF

  CPropertyStoreHelper::CPropertyStoreHelper((CPropertyStoreHelper *)&v7, a1);
  pv = 0;
  v5 = PKEY_ItemClass;
  v3 = CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v7, &v5, &pv);
  if ( v3 >= 0 )
    *(_DWORD *)a2 = CCDSResultsParser::GetMediaTypeFromClass(pv);
  CoTaskMemFree(pv);
  CPropertyStoreHelperBase<IPropertyStore>::~CPropertyStoreHelperBase<IPropertyStore>(&v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002c8fc  mov     [rsp+arg_0], rbx
0x18002c901  push    rdi
0x18002c902  sub     rsp, 40h
0x18002c906  mov     rdi, rdx
0x18002c909  mov     rdx, rcx; struct IPropertyStore *
0x18002c90c  lea     rcx, [rsp+48h+arg_18]; this
0x18002c911  call    ??0CPropertyStoreHelper@@QEAA@PEAUIPropertyStore@@@Z; CPropertyStoreHelper::CPropertyStoreHelper(IPropertyStore *)
0x18002c916  mov     [rsp+48h+pv], 0
0x18002c91f  movups  xmm0, xmmword ptr cs:PKEY_ItemClass.fmtid.Data1
0x18002c926  movaps  [rsp+48h+var_28], xmm0
0x18002c92b  mov     eax, cs:PKEY_ItemClass.pid
0x18002c931  mov     [rsp+48h+var_18], eax
0x18002c935  lea     r8, [rsp+48h+pv]
0x18002c93a  lea     rdx, [rsp+48h+var_28]
0x18002c93f  lea     rcx, [rsp+48h+arg_18]
0x18002c944  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18002c949  mov     ebx, eax
0x18002c94b  test    eax, eax
0x18002c94d  js      short loc_18002C95B
0x18002c94f  mov     rcx, [rsp+48h+pv]
0x18002c954  call    ?GetMediaTypeFromClass@CCDSResultsParser@@SA?AW4_CDS_MEDIA_TYPE@@PEBG@Z; CCDSResultsParser::GetMediaTypeFromClass(ushort const *)
0x18002c959  mov     [rdi], eax
0x18002c95b  mov     rcx, [rsp+48h+pv]; pv
0x18002c960  call    cs:__imp_CoTaskMemFree
0x18002c966  nop
0x18002c967  lea     rcx, [rsp+48h+arg_18]
0x18002c96c  call    ??1?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAA@XZ; CPropertyStoreHelperBase<IPropertyStore>::~CPropertyStoreHelperBase<IPropertyStore>(void)
0x18002c971  nop
0x18002c972  mov     eax, ebx
0x18002c974  mov     rbx, [rsp+48h+arg_0]
0x18002c979  add     rsp, 40h
0x18002c97d  pop     rdi
0x18002c97e  retn
```
