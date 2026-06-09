# UpdateWbemClassObjectPropertyObject<CWmiOfflineFilesDiskSpaceLimit>(IWbemServices *,IWbemContext *,IWbemClassObject *,ushort const *,void *)

- ea: `0x18001c700`
- end: `0x18001c7b4`
- name: `??$UpdateWbemClassObjectPropertyObject@VCWmiOfflineFilesDiskSpaceLimit@@@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@PEBGPEAX@Z`
- size: `180`
- prototype: `__int64 __usercall@<rax>(struct IWbemServices *@<rcx>, struct IWbemContext *@<rdx>, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x180009d50`
- `0x18001c3e4`
- `0x18001c700`
- `0x18001c9d8`
- `0x18001d484`
- `0x18001de64`
- `0x180027264`
- `0x1800296a0`

## pseudocode

```c
__int64 __fastcall UpdateWbemClassObjectPropertyObject<CWmiOfflineFilesDiskSpaceLimit>(
        struct IWbemServices *a1,
        struct IWbemContext *a2,
        __int64 a3,
        __int64 a4,
        struct IWbemClassObject *a5)
{
  struct IUnknown *v6; // rbx
  int v9; // edi
  int v10; // eax
  VARIANTARG *v11; // rax
  struct IUnknown *v13; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v14[32]; // [rsp+28h] [rbp-20h] BYREF
  UstCommon::CRefCounted *v15; // [rsp+98h] [rbp+50h] BYREF

  v6 = 0;
  v13 = 0;
  v15 = 0;
  v9 = UstCommon::CWmiCreator<CWmiOfflineFilesDiskSpaceLimit>::CreateInstance<CWmiOfflineFilesDiskSpaceLimit>(a1, &v15);
  if ( v9 >= 0 )
  {
    a5 = 0;
    v9 = UstCommon::CWmiObject::CreateWbemClassObject(v15, a1, a2, &a5);
    if ( v9 >= 0 )
    {
      v10 = ATL::CComPtrBase<IWbemClassObject>::CopyTo(&a5, &v13);
      v6 = v13;
      v9 = v10;
    }
    UstCommon::CRefCounted::Release(v15);
    ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>((__int64 *)&a5);
    if ( v9 >= 0 )
    {
      v11 = (VARIANTARG *)ATL::CComVariant::CComVariant((ATL::CComVariant *)v14, v6);
      v9 = WmiProp_SetProperty(a3, (__int64)L"DiskSpaceLimitParams", v11);
    }
  }
  ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>((__int64 *)&v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c700  mov     [rsp-30h+arg_18], r9
0x18001c705  push    rbp
0x18001c706  push    rbx
0x18001c707  push    rsi
0x18001c708  push    rdi
0x18001c709  push    r14
0x18001c70b  push    r15
0x18001c70d  mov     rbp, rsp
0x18001c710  sub     rsp, 48h
0x18001c714  mov     rsi, rdx
0x18001c717  xor     ebx, ebx
0x18001c719  lea     rdx, [rbp+arg_18]
0x18001c71d  mov     [rbp+var_28], rbx
0x18001c721  mov     [rbp+arg_18], rbx
0x18001c725  mov     r15, r8
0x18001c728  mov     r14, rcx
0x18001c72b  call    ??$CreateInstance@VCWmiOfflineFilesDiskSpaceLimit@@@?$CWmiCreator@VCWmiOfflineFilesDiskSpaceLimit@@@UstCommon@@SAJPEAXPEAPEAVCWmiOfflineFilesDiskSpaceLimit@@@Z; UstCommon::CWmiCreator<CWmiOfflineFilesDiskSpaceLimit>::CreateInstance<CWmiOfflineFilesDiskSpaceLimit>(void *,CWmiOfflineFilesDiskSpaceLimit * *)
0x18001c730  mov     edi, eax
0x18001c732  test    eax, eax
0x18001c734  js      short loc_18001C79C
0x18001c736  mov     rcx, [rbp+arg_18]; this
0x18001c73a  lea     r9, [rbp+arg_20]; struct IWbemClassObject **
0x18001c73e  mov     r8, rsi; struct IWbemContext *
0x18001c741  mov     [rbp+arg_20], rbx
0x18001c745  mov     rdx, r14; struct IWbemServices *
0x18001c748  call    ?CreateWbemClassObject@CWmiObject@UstCommon@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; UstCommon::CWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x18001c74d  mov     edi, eax
0x18001c74f  test    eax, eax
0x18001c751  js      short loc_18001C766
0x18001c753  lea     rdx, [rbp+var_28]
0x18001c757  lea     rcx, [rbp+arg_20]
0x18001c75b  call    ?CopyTo@?$CComPtrBase@UIWbemClassObject@@@ATL@@QEAAJPEAPEAUIWbemClassObject@@@Z; ATL::CComPtrBase<IWbemClassObject>::CopyTo(IWbemClassObject * *)
0x18001c760  mov     rbx, [rbp+var_28]
0x18001c764  mov     edi, eax
0x18001c766  mov     rcx, [rbp+arg_18]; this
0x18001c76a  call    ?Release@CRefCounted@UstCommon@@QEAAKXZ; UstCommon::CRefCounted::Release(void)
0x18001c76f  lea     rcx, [rbp+arg_20]
0x18001c773  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x18001c778  test    edi, edi
0x18001c77a  js      short loc_18001C79C
0x18001c77c  mov     rdx, rbx; struct IUnknown *
0x18001c77f  lea     rcx, [rbp+var_20]; this
0x18001c783  call    ??0CComVariant@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComVariant::CComVariant(IUnknown *)
0x18001c788  mov     r8, rax
0x18001c78b  lea     rdx, CSCWMI_STR_PROP_DISKSPACELIMITPARAMS; "DiskSpaceLimitParams"
0x18001c792  mov     rcx, r15
0x18001c795  call    ?WmiProp_SetProperty@@YAJPEAUIWbemClassObject@@PEBGVCComVariant@ATL@@@Z; WmiProp_SetProperty(IWbemClassObject *,ushort const *,ATL::CComVariant)
0x18001c79a  mov     edi, eax
0x18001c79c  lea     rcx, [rbp+var_28]
0x18001c7a0  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x18001c7a5  mov     eax, edi
0x18001c7a7  add     rsp, 48h
0x18001c7ab  pop     r15
0x18001c7ad  pop     r14
0x18001c7af  pop     rdi
0x18001c7b0  pop     rsi
0x18001c7b1  pop     rbx
0x18001c7b2  pop     rbp
0x18001c7b3  retn
```
