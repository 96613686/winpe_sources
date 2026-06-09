# UpdateOrRemoveWMIPropertiesFromObject<CWmiOfflineFilesDiskSpaceLimit>(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *,ushort const *,void *)

- ea: `0x18001c598`
- end: `0x18001c63c`
- name: `??$UpdateOrRemoveWMIPropertiesFromObject@VCWmiOfflineFilesDiskSpaceLimit@@@@YAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@PEBGPEAX@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001f820`

## callees

- `0x180009d50`
- `0x18001c3e4`
- `0x18001c598`
- `0x18001de64`
- `0x180027d98`
- `0x18002841c`

## pseudocode

```c
__int64 __fastcall UpdateOrRemoveWMIPropertiesFromObject<CWmiOfflineFilesDiskSpaceLimit>(
        struct IWbemClassObject *a1,
        unsigned int a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        struct IWbemServices *a5,
        UstCommon::CRefCounted *a6,
        struct IWbemClassObject *a7)
{
  __int64 v10; // rcx
  int PropertyObjectFromParent; // ebx

  a7 = 0;
  PropertyObjectFromParent = GetPropertyObjectFromParent(a1, L"DiskSpaceLimitParams", &a7);
  if ( PropertyObjectFromParent >= 0 )
  {
    a6 = 0;
    PropertyObjectFromParent = UstCommon::CWmiCreator<CWmiOfflineFilesDiskSpaceLimit>::CreateInstance<CWmiOfflineFilesDiskSpaceLimit>(
                                 v10,
                                 &a6);
    if ( PropertyObjectFromParent >= 0 )
    {
      PropertyObjectFromParent = UstCommon::CWmiObject::PutInstance(a6, a7, a2, a3, a4, a5);
      UstCommon::CRefCounted::Release(a6);
    }
  }
  ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>((__int64 *)&a7);
  return (unsigned int)PropertyObjectFromParent;
}

```

## disassembly

```asm
0x18001c598  mov     rax, rsp
0x18001c59b  push    rbx
0x18001c59c  push    rbp
0x18001c59d  push    rsi
0x18001c59e  push    rdi
0x18001c59f  sub     rsp, 38h
0x18001c5a3  mov     rsi, r8
0x18001c5a6  mov     qword ptr [rax+38h], 0
0x18001c5ae  mov     ebp, edx
0x18001c5b0  lea     r8, [rax+38h]; struct IWbemClassObject **
0x18001c5b4  lea     rdx, CSCWMI_STR_PROP_DISKSPACELIMITPARAMS; "DiskSpaceLimitParams"
0x18001c5bb  mov     rdi, r9
0x18001c5be  call    ?GetPropertyObjectFromParent@@YAJPEAUIWbemClassObject@@PEBGPEAPEAU1@@Z; GetPropertyObjectFromParent(IWbemClassObject *,ushort const *,IWbemClassObject * *)
0x18001c5c3  mov     ebx, eax
0x18001c5c5  test    eax, eax
0x18001c5c7  js      short loc_18001C624
0x18001c5c9  lea     rdx, [rsp+58h+arg_28]
0x18001c5d1  mov     [rsp+58h+arg_28], 0
0x18001c5dd  call    ??$CreateInstance@VCWmiOfflineFilesDiskSpaceLimit@@@?$CWmiCreator@VCWmiOfflineFilesDiskSpaceLimit@@@UstCommon@@SAJPEAXPEAPEAVCWmiOfflineFilesDiskSpaceLimit@@@Z; UstCommon::CWmiCreator<CWmiOfflineFilesDiskSpaceLimit>::CreateInstance<CWmiOfflineFilesDiskSpaceLimit>(void *,CWmiOfflineFilesDiskSpaceLimit * *)
0x18001c5e2  mov     ebx, eax
0x18001c5e4  test    eax, eax
0x18001c5e6  js      short loc_18001C624
0x18001c5e8  mov     rax, [rsp+58h+arg_20]
0x18001c5f0  mov     r9, rsi; struct IWbemContext *
0x18001c5f3  mov     rdx, [rsp+58h+arg_30]; struct IWbemClassObject *
0x18001c5fb  mov     r8d, ebp; int
0x18001c5fe  mov     rcx, [rsp+58h+arg_28]; this
0x18001c606  mov     [rsp+58h+var_30], rax; struct IWbemServices *
0x18001c60b  mov     [rsp+58h+var_38], rdi; struct IWbemObjectSink *
0x18001c610  call    ?PutInstance@CWmiObject@UstCommon@@QEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; UstCommon::CWmiObject::PutInstance(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x18001c615  mov     rcx, [rsp+58h+arg_28]; this
0x18001c61d  mov     ebx, eax
0x18001c61f  call    ?Release@CRefCounted@UstCommon@@QEAAKXZ; UstCommon::CRefCounted::Release(void)
0x18001c624  lea     rcx, [rsp+58h+arg_30]
0x18001c62c  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x18001c631  mov     eax, ebx
0x18001c633  add     rsp, 38h
0x18001c637  pop     rdi
0x18001c638  pop     rsi
0x18001c639  pop     rbp
0x18001c63a  pop     rbx
0x18001c63b  retn
```
