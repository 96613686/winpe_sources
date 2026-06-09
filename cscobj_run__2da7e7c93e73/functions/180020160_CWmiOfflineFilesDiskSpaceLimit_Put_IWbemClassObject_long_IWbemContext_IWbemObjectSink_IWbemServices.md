# CWmiOfflineFilesDiskSpaceLimit::_Put(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x180020160`
- end: `0x18002023c`
- name: `?_Put@CWmiOfflineFilesDiskSpaceLimit@@MEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(CWmiOfflineFilesDiskSpaceLimit *this, struct IWbemClassObject *, char, struct IWbemContext *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800140c8`
- `0x18001e964`
- `0x180020160`

## string_xrefs

- `0x1800201e1`: `AutoCacheSizeInMB`
- `0x18002020d`: `AutoCacheSizeInMB`

## pseudocode

```c
__int64 __fastcall CWmiOfflineFilesDiskSpaceLimit::_Put(
        CWmiOfflineFilesDiskSpaceLimit *this,
        struct IWbemClassObject *a2,
        char a3,
        struct IWbemContext *a4)
{
  int v5; // ebx
  int v6; // eax
  int v7; // eax

  v5 = -2147217396;
  if ( (a3 & 1) != 0 )
  {
    v6 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"TotalSizeInMB", 0, a2, 34);
    v5 = v6;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        84,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"TotalSizeInMB",
        v6);
    }
    if ( v5 >= 0 )
    {
      v7 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"AutoCacheSizeInMB", 0, a2, 34);
      v5 = v7;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          85,
          (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          (unsigned int)L"AutoCacheSizeInMB",
          v7);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020160  mov     [rsp+arg_0], rbx
0x180020165  mov     [rsp+arg_8], rdi
0x18002016a  push    r14
0x18002016c  sub     rsp, 30h
0x180020170  mov     rdi, rdx
0x180020173  mov     ebx, 8004100Ch
0x180020178  test    r8b, 1
0x18002017c  jz      loc_180020229
0x180020182  mov     r8, rdx
0x180020185  lea     rcx, CSCWMI_STR_PROP_TOTALSIZE; "TotalSizeInMB"
0x18002018c  xor     edx, edx
0x18002018e  mov     r9d, 22h ; '"'
0x180020194  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180020199  mov     ebx, eax
0x18002019b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201a2  lea     r14, WPP_GLOBAL_Control
0x1800201a9  cmp     rcx, r14
0x1800201ac  jz      short loc_1800201D7
0x1800201ae  test    dword ptr [rcx+1Ch], 4000000h
0x1800201b5  jz      short loc_1800201D7
0x1800201b7  mov     rcx, [rcx+10h]
0x1800201bb  lea     r9, CSCWMI_STR_PROP_TOTALSIZE; "TotalSizeInMB"
0x1800201c2  mov     edx, 54h ; 'T'
0x1800201c7  mov     [rsp+38h+var_18], eax
0x1800201cb  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x1800201d2  call    WPP_SF_SD
0x1800201d7  test    ebx, ebx
0x1800201d9  js      short loc_180020229
0x1800201db  mov     r9d, 22h ; '"'
0x1800201e1  lea     rcx, CSCWMI_STR_PROP_AUTOCACHESIZE; "AutoCacheSizeInMB"
0x1800201e8  mov     r8, rdi
0x1800201eb  xor     edx, edx
0x1800201ed  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x1800201f2  mov     ebx, eax
0x1800201f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201fb  cmp     rcx, r14
0x1800201fe  jz      short loc_180020229
0x180020200  test    dword ptr [rcx+1Ch], 4000000h
0x180020207  jz      short loc_180020229
0x180020209  mov     rcx, [rcx+10h]
0x18002020d  lea     r9, CSCWMI_STR_PROP_AUTOCACHESIZE; "AutoCacheSizeInMB"
0x180020214  mov     edx, 55h ; 'U'
0x180020219  mov     [rsp+38h+var_18], eax
0x18002021d  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180020224  call    WPP_SF_SD
0x180020229  mov     rdi, [rsp+38h+arg_8]
0x18002022e  mov     eax, ebx
0x180020230  mov     rbx, [rsp+38h+arg_0]
0x180020235  add     rsp, 30h
0x180020239  pop     r14
0x18002023b  retn
```
