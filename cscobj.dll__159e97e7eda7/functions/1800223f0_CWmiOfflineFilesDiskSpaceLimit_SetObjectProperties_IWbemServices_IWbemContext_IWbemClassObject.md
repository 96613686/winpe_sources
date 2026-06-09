# CWmiOfflineFilesDiskSpaceLimit::_SetObjectProperties(IWbemServices *,IWbemContext *,IWbemClassObject *)

- ea: `0x1800223f0`
- end: `0x1800224bd`
- name: `?_SetObjectProperties@CWmiOfflineFilesDiskSpaceLimit@@MEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CWmiOfflineFilesDiskSpaceLimit *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800140c8`
- `0x18001f1c4`
- `0x1800223f0`

## string_xrefs

- `0x180022462`: `AutoCacheSizeInMB`
- `0x18002248e`: `AutoCacheSizeInMB`

## pseudocode

```c
__int64 __fastcall CWmiOfflineFilesDiskSpaceLimit::_SetObjectProperties(
        CWmiOfflineFilesDiskSpaceLimit *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemClassObject *a4)
{
  int updated; // eax
  int v6; // ebx
  int v7; // eax

  updated = CSCWmiConfig::UpdateWbemClassObjectProp(L"TotalSizeInMB", 0, a4, 2);
  v6 = updated;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_SD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      82,
      (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
      (unsigned int)L"TotalSizeInMB",
      updated);
  }
  if ( v6 >= 0 )
  {
    v7 = CSCWmiConfig::UpdateWbemClassObjectProp(L"AutoCacheSizeInMB", 0, a4, 2);
    v6 = v7;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        83,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"AutoCacheSizeInMB",
        v7);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800223f0  mov     [rsp+arg_0], rbx
0x1800223f5  mov     [rsp+arg_8], rdi
0x1800223fa  push    r14
0x1800223fc  sub     rsp, 30h
0x180022400  mov     rdi, r9
0x180022403  lea     rcx, CSCWMI_STR_PROP_TOTALSIZE; "TotalSizeInMB"
0x18002240a  mov     r8, rdi
0x18002240d  mov     r9d, 2
0x180022413  xor     edx, edx
0x180022415  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18002241a  mov     ebx, eax
0x18002241c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022423  lea     r14, WPP_GLOBAL_Control
0x18002242a  cmp     rcx, r14
0x18002242d  jz      short loc_180022458
0x18002242f  test    dword ptr [rcx+1Ch], 4000000h
0x180022436  jz      short loc_180022458
0x180022438  mov     rcx, [rcx+10h]
0x18002243c  lea     r9, CSCWMI_STR_PROP_TOTALSIZE; "TotalSizeInMB"
0x180022443  mov     edx, 52h ; 'R'
0x180022448  mov     [rsp+38h+var_18], eax
0x18002244c  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180022453  call    WPP_SF_SD
0x180022458  test    ebx, ebx
0x18002245a  js      short loc_1800224AA
0x18002245c  mov     r9d, 2
0x180022462  lea     rcx, CSCWMI_STR_PROP_AUTOCACHESIZE; "AutoCacheSizeInMB"
0x180022469  mov     r8, rdi
0x18002246c  xor     edx, edx
0x18002246e  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180022473  mov     ebx, eax
0x180022475  mov     rcx, cs:WPP_GLOBAL_Control
0x18002247c  cmp     rcx, r14
0x18002247f  jz      short loc_1800224AA
0x180022481  test    dword ptr [rcx+1Ch], 4000000h
0x180022488  jz      short loc_1800224AA
0x18002248a  mov     rcx, [rcx+10h]
0x18002248e  lea     r9, CSCWMI_STR_PROP_AUTOCACHESIZE; "AutoCacheSizeInMB"
0x180022495  mov     edx, 53h ; 'S'
0x18002249a  mov     [rsp+38h+var_18], eax
0x18002249e  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x1800224a5  call    WPP_SF_SD
0x1800224aa  mov     rdi, [rsp+38h+arg_8]
0x1800224af  mov     eax, ebx
0x1800224b1  mov     rbx, [rsp+38h+arg_0]
0x1800224b6  add     rsp, 30h
0x1800224ba  pop     r14
0x1800224bc  retn
```
