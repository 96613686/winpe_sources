# UpdateWbemClassObjectPropertyObject<CWmiOfflineFilesBackgroundSync>(IWbemServices *,IWbemContext *,IWbemClassObject *,ushort const *,void *)

- ea: `0x18001c644`
- end: `0x18001c6f8`
- name: `??$UpdateWbemClassObjectPropertyObject@VCWmiOfflineFilesBackgroundSync@@@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@PEBGPEAX@Z`
- size: `180`
- prototype: `__int64 __usercall@<rax>(struct IWbemServices *@<rcx>, struct IWbemContext *@<rdx>, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x180009d50`
- `0x18001c2dc`
- `0x18001c644`
- `0x18001c9d8`
- `0x18001d484`
- `0x18001de64`
- `0x180027264`
- `0x1800296a0`

## pseudocode

```c
__int64 __fastcall UpdateWbemClassObjectPropertyObject<CWmiOfflineFilesBackgroundSync>(
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
  v9 = UstCommon::CWmiCreator<CWmiOfflineFilesBackgroundSync>::CreateInstance<CWmiOfflineFilesBackgroundSync>(a1, &v15);
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
      v9 = WmiProp_SetProperty(a3, (__int64)L"BackgroundSyncParams", v11);
    }
  }
  ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>((__int64 *)&v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c644  mov     [rsp-30h+arg_18], r9
0x18001c649  push    rbp
0x18001c64a  push    rbx
0x18001c64b  push    rsi
0x18001c64c  push    rdi
0x18001c64d  push    r14
0x18001c64f  push    r15
0x18001c651  mov     rbp, rsp
0x18001c654  sub     rsp, 48h
0x18001c658  mov     rsi, rdx
0x18001c65b  xor     ebx, ebx
0x18001c65d  lea     rdx, [rbp+arg_18]
0x18001c661  mov     [rbp+var_28], rbx
0x18001c665  mov     [rbp+arg_18], rbx
0x18001c669  mov     r15, r8
0x18001c66c  mov     r14, rcx
0x18001c66f  call    ??$CreateInstance@VCWmiOfflineFilesBackgroundSync@@@?$CWmiCreator@VCWmiOfflineFilesBackgroundSync@@@UstCommon@@SAJPEAXPEAPEAVCWmiOfflineFilesBackgroundSync@@@Z; UstCommon::CWmiCreator<CWmiOfflineFilesBackgroundSync>::CreateInstance<CWmiOfflineFilesBackgroundSync>(void *,CWmiOfflineFilesBackgroundSync * *)
0x18001c674  mov     edi, eax
0x18001c676  test    eax, eax
0x18001c678  js      short loc_18001C6E0
0x18001c67a  mov     rcx, [rbp+arg_18]; this
0x18001c67e  lea     r9, [rbp+arg_20]; struct IWbemClassObject **
0x18001c682  mov     r8, rsi; struct IWbemContext *
0x18001c685  mov     [rbp+arg_20], rbx
0x18001c689  mov     rdx, r14; struct IWbemServices *
0x18001c68c  call    ?CreateWbemClassObject@CWmiObject@UstCommon@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; UstCommon::CWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x18001c691  mov     edi, eax
0x18001c693  test    eax, eax
0x18001c695  js      short loc_18001C6AA
0x18001c697  lea     rdx, [rbp+var_28]
0x18001c69b  lea     rcx, [rbp+arg_20]
0x18001c69f  call    ?CopyTo@?$CComPtrBase@UIWbemClassObject@@@ATL@@QEAAJPEAPEAUIWbemClassObject@@@Z; ATL::CComPtrBase<IWbemClassObject>::CopyTo(IWbemClassObject * *)
0x18001c6a4  mov     rbx, [rbp+var_28]
0x18001c6a8  mov     edi, eax
0x18001c6aa  mov     rcx, [rbp+arg_18]; this
0x18001c6ae  call    ?Release@CRefCounted@UstCommon@@QEAAKXZ; UstCommon::CRefCounted::Release(void)
0x18001c6b3  lea     rcx, [rbp+arg_20]
0x18001c6b7  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x18001c6bc  test    edi, edi
0x18001c6be  js      short loc_18001C6E0
0x18001c6c0  mov     rdx, rbx; struct IUnknown *
0x18001c6c3  lea     rcx, [rbp+var_20]; this
0x18001c6c7  call    ??0CComVariant@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComVariant::CComVariant(IUnknown *)
0x18001c6cc  mov     r8, rax
0x18001c6cf  lea     rdx, CSCWMI_STR_PROP_BACKGROUNDSYNCPARAMS; "BackgroundSyncParams"
0x18001c6d6  mov     rcx, r15
0x18001c6d9  call    ?WmiProp_SetProperty@@YAJPEAUIWbemClassObject@@PEBGVCComVariant@ATL@@@Z; WmiProp_SetProperty(IWbemClassObject *,ushort const *,ATL::CComVariant)
0x18001c6de  mov     edi, eax
0x18001c6e0  lea     rcx, [rbp+var_28]
0x18001c6e4  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x18001c6e9  mov     eax, edi
0x18001c6eb  add     rsp, 48h
0x18001c6ef  pop     r15
0x18001c6f1  pop     r14
0x18001c6f3  pop     rdi
0x18001c6f4  pop     rsi
0x18001c6f5  pop     rbx
0x18001c6f6  pop     rbp
0x18001c6f7  retn
```
