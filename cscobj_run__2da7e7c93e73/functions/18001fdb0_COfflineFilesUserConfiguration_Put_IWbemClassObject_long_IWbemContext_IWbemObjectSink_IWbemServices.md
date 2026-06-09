# COfflineFilesUserConfiguration::_Put(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x18001fdb0`
- end: `0x18001ff3b`
- name: `?_Put@COfflineFilesUserConfiguration@@MEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(COfflineFilesUserConfiguration *__hidden this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ac4`
- `0x18000f5cc`
- `0x1800140c8`
- `0x18001e100`
- `0x18001e964`
- `0x18001fdb0`
- `0x18002c010`

## string_xrefs

- `0x18001fdfd`: `WorkOfflineButtonRemoved`
- `0x18001fe29`: `WorkOfflineButtonRemoved`
- `0x18001fe58`: `MakeAvailableOfflineButtonRemoved`
- `0x18001fe84`: `MakeAvailableOfflineButtonRemoved`

## pseudocode

```c
__int64 __fastcall COfflineFilesUserConfiguration::_Put(
        COfflineFilesUserConfiguration *this,
        struct IWbemClassObject *a2,
        char a3,
        struct IWbemContext *a4)
{
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // r8

  v6 = -2147217396;
  if ( (a3 & 1) == 0 )
    goto LABEL_16;
  v6 = (*(__int64 (__fastcall **)(char *, struct IWbemContext *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16, a4);
  if ( v6 < 0 )
    goto LABEL_16;
  v7 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(
         L"WorkOfflineButtonRemoved",
         *((_QWORD *)this + 6),
         (__int64)a2,
         33);
  v6 = v7;
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_SD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      149,
      (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
      (unsigned int)L"WorkOfflineButtonRemoved",
      v7);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v6 >= 0 )
  {
    v9 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(
           L"MakeAvailableOfflineButtonRemoved",
           *((_QWORD *)this + 6),
           (__int64)a2,
           33);
    v6 = v9;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        150,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"MakeAvailableOfflineButtonRemoved",
        v9);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v6 >= 0 )
    {
      v10 = CSCWmiConfig::UpdateOrRemoveWMIAssignedOfflineFilesProperty(a2, *((_QWORD *)this + 6));
      v6 = v10;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          151,
          (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          (unsigned int)L"AssignedOfflineFiles",
          v10);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v6 >= 0 )
      {
        v6 = ApplyCscPolicy(1, *((void **)this + 6), v11);
LABEL_16:
        v8 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_DWORD *)(v8 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v8 + 16), 152, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001fdb0  push    rbx
0x18001fdb2  push    rbp
0x18001fdb3  push    rsi
0x18001fdb4  push    rdi
0x18001fdb5  push    r15
0x18001fdb7  sub     rsp, 30h
0x18001fdbb  lea     r15, WPP_GLOBAL_Control
0x18001fdc2  mov     rsi, rdx
0x18001fdc5  mov     rdi, rcx
0x18001fdc8  mov     ebx, 8004100Ch
0x18001fdcd  mov     ebp, 4000000h
0x18001fdd2  test    r8b, 1
0x18001fdd6  jz      loc_18001FF05
0x18001fddc  add     rcx, 10h
0x18001fde0  mov     rdx, r9
0x18001fde3  mov     rax, [rcx]
0x18001fde6  mov     rax, [rax+8]
0x18001fdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdef  mov     ebx, eax
0x18001fdf1  test    eax, eax
0x18001fdf3  js      loc_18001FF05
0x18001fdf9  mov     rdx, [rdi+30h]
0x18001fdfd  lea     rcx, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x18001fe04  mov     r9d, 21h ; '!'
0x18001fe0a  mov     r8, rsi
0x18001fe0d  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001fe12  mov     ebx, eax
0x18001fe14  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe1b  cmp     rcx, r15
0x18001fe1e  jz      short loc_18001FE4C
0x18001fe20  test    [rcx+1Ch], ebp
0x18001fe23  jz      short loc_18001FE4C
0x18001fe25  mov     rcx, [rcx+10h]
0x18001fe29  lea     r9, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x18001fe30  mov     edx, 95h
0x18001fe35  mov     [rsp+58h+var_38], eax
0x18001fe39  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001fe40  call    WPP_SF_SD
0x18001fe45  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe4c  test    ebx, ebx
0x18001fe4e  js      loc_18001FF0C
0x18001fe54  mov     rdx, [rdi+30h]
0x18001fe58  lea     rcx, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x18001fe5f  mov     r9d, 21h ; '!'
0x18001fe65  mov     r8, rsi
0x18001fe68  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001fe6d  mov     ebx, eax
0x18001fe6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe76  cmp     rcx, r15
0x18001fe79  jz      short loc_18001FEA7
0x18001fe7b  test    [rcx+1Ch], ebp
0x18001fe7e  jz      short loc_18001FEA7
0x18001fe80  mov     rcx, [rcx+10h]
0x18001fe84  lea     r9, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x18001fe8b  mov     edx, 96h
0x18001fe90  mov     [rsp+58h+var_38], eax
0x18001fe94  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001fe9b  call    WPP_SF_SD
0x18001fea0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fea7  test    ebx, ebx
0x18001fea9  js      short loc_18001FF0C
0x18001feab  mov     rdx, [rdi+30h]
0x18001feaf  mov     rcx, rsi
0x18001feb2  call    ?UpdateOrRemoveWMIAssignedOfflineFilesProperty@CSCWmiConfig@@YAJPEAUIWbemClassObject@@PEAXW4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIAssignedOfflineFilesProperty(IWbemClassObject *,void *,USERSTATE_SETTING_SOURCES)
0x18001feb7  mov     ebx, eax
0x18001feb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fec0  cmp     rcx, r15
0x18001fec3  jz      short loc_18001FEF1
0x18001fec5  test    [rcx+1Ch], ebp
0x18001fec8  jz      short loc_18001FEF1
0x18001feca  mov     rcx, [rcx+10h]
0x18001fece  lea     r9, CSCWMI_STR_PROP_ASSIGNEDOFFLINEFILES; "AssignedOfflineFiles"
0x18001fed5  mov     edx, 97h
0x18001feda  mov     [rsp+58h+var_38], eax
0x18001fede  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001fee5  call    WPP_SF_SD
0x18001feea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fef1  test    ebx, ebx
0x18001fef3  js      short loc_18001FF0C
0x18001fef5  mov     rdx, [rdi+30h]; void *
0x18001fef9  mov     ecx, 1; int
0x18001fefe  call    ?ApplyCscPolicy@@YAJHPEAX@Z; ApplyCscPolicy(int,void *)
0x18001ff03  mov     ebx, eax
0x18001ff05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff0c  cmp     rcx, r15
0x18001ff0f  jz      short loc_18001FF2E
0x18001ff11  test    [rcx+1Ch], ebp
0x18001ff14  jz      short loc_18001FF2E
0x18001ff16  mov     rcx, [rcx+10h]
0x18001ff1a  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001ff21  mov     edx, 98h
0x18001ff26  mov     r9d, ebx
0x18001ff29  call    WPP_SF_d
0x18001ff2e  mov     eax, ebx
0x18001ff30  add     rsp, 30h
0x18001ff34  pop     r15
0x18001ff36  pop     rdi
0x18001ff37  pop     rsi
0x18001ff38  pop     rbp
0x18001ff39  pop     rbx
0x18001ff3a  retn
```
