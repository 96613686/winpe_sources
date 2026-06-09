# UpdateOrRemoveWMIPropertiesFromObject<CWmiOfflineFilesBackgroundSync>(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *,ushort const *,void *)

- ea: `0x18001c4ec`
- end: `0x18001c590`
- name: `??$UpdateOrRemoveWMIPropertiesFromObject@VCWmiOfflineFilesBackgroundSync@@@@YAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@PEBGPEAX@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001f820`

## callees

- `0x180009d50`
- `0x18001c2dc`
- `0x18001c4ec`
- `0x18001de64`
- `0x180027d98`
- `0x18002841c`

## pseudocode

```c
__int64 __fastcall UpdateOrRemoveWMIPropertiesFromObject<CWmiOfflineFilesBackgroundSync>(
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
  PropertyObjectFromParent = GetPropertyObjectFromParent(a1, L"BackgroundSyncParams", &a7);
  if ( PropertyObjectFromParent >= 0 )
  {
    a6 = 0;
    PropertyObjectFromParent = UstCommon::CWmiCreator<CWmiOfflineFilesBackgroundSync>::CreateInstance<CWmiOfflineFilesBackgroundSync>(
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
0x18001c4ec  mov     rax, rsp
0x18001c4ef  push    rbx
0x18001c4f0  push    rbp
0x18001c4f1  push    rsi
0x18001c4f2  push    rdi
0x18001c4f3  sub     rsp, 38h
0x18001c4f7  mov     rsi, r8
0x18001c4fa  mov     qword ptr [rax+38h], 0
0x18001c502  mov     ebp, edx
0x18001c504  lea     r8, [rax+38h]; struct IWbemClassObject **
0x18001c508  lea     rdx, CSCWMI_STR_PROP_BACKGROUNDSYNCPARAMS; "BackgroundSyncParams"
0x18001c50f  mov     rdi, r9
0x18001c512  call    ?GetPropertyObjectFromParent@@YAJPEAUIWbemClassObject@@PEBGPEAPEAU1@@Z; GetPropertyObjectFromParent(IWbemClassObject *,ushort const *,IWbemClassObject * *)
0x18001c517  mov     ebx, eax
0x18001c519  test    eax, eax
0x18001c51b  js      short loc_18001C578
0x18001c51d  lea     rdx, [rsp+58h+arg_28]
0x18001c525  mov     [rsp+58h+arg_28], 0
0x18001c531  call    ??$CreateInstance@VCWmiOfflineFilesBackgroundSync@@@?$CWmiCreator@VCWmiOfflineFilesBackgroundSync@@@UstCommon@@SAJPEAXPEAPEAVCWmiOfflineFilesBackgroundSync@@@Z; UstCommon::CWmiCreator<CWmiOfflineFilesBackgroundSync>::CreateInstance<CWmiOfflineFilesBackgroundSync>(void *,CWmiOfflineFilesBackgroundSync * *)
0x18001c536  mov     ebx, eax
0x18001c538  test    eax, eax
0x18001c53a  js      short loc_18001C578
0x18001c53c  mov     rax, [rsp+58h+arg_20]
0x18001c544  mov     r9, rsi; struct IWbemContext *
0x18001c547  mov     rdx, [rsp+58h+arg_30]; struct IWbemClassObject *
0x18001c54f  mov     r8d, ebp; int
0x18001c552  mov     rcx, [rsp+58h+arg_28]; this
0x18001c55a  mov     [rsp+58h+var_30], rax; struct IWbemServices *
0x18001c55f  mov     [rsp+58h+var_38], rdi; struct IWbemObjectSink *
0x18001c564  call    ?PutInstance@CWmiObject@UstCommon@@QEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; UstCommon::CWmiObject::PutInstance(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x18001c569  mov     rcx, [rsp+58h+arg_28]; this
0x18001c571  mov     ebx, eax
0x18001c573  call    ?Release@CRefCounted@UstCommon@@QEAAKXZ; UstCommon::CRefCounted::Release(void)
0x18001c578  lea     rcx, [rsp+58h+arg_30]
0x18001c580  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x18001c585  mov     eax, ebx
0x18001c587  add     rsp, 38h
0x18001c58b  pop     rdi
0x18001c58c  pop     rsi
0x18001c58d  pop     rbp
0x18001c58e  pop     rbx
0x18001c58f  retn
```
