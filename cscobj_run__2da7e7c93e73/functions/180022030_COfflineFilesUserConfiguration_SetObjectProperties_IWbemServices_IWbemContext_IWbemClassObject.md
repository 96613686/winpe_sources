# COfflineFilesUserConfiguration::_SetObjectProperties(IWbemServices *,IWbemContext *,IWbemClassObject *)

- ea: `0x180022030`
- end: `0x1800221df`
- name: `?_SetObjectProperties@COfflineFilesUserConfiguration@@MEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `431`
- prototype: `int(COfflineFilesUserConfiguration *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f5cc`
- `0x1800140c8`
- `0x18001ec30`
- `0x18001f1c4`
- `0x180022030`
- `0x180028508`
- `0x1800296a0`
- `0x18002c010`

## string_xrefs

- `0x180022070`: `WorkOfflineButtonRemoved`
- `0x18002209f`: `WorkOfflineButtonRemoved`
- `0x1800220ce`: `MakeAvailableOfflineButtonRemoved`
- `0x1800220f7`: `MakeAvailableOfflineButtonRemoved`
- `0x180022185`: `IsConfiguredByWMI`

## pseudocode

```c
__int64 __fastcall COfflineFilesUserConfiguration::_SetObjectProperties(
        COfflineFilesUserConfiguration *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemContext *a4)
{
  int v6; // ebx
  int updated; // eax
  __int64 v8; // rcx
  int v9; // eax
  void *v10; // r9
  int v11; // eax
  _WORD v13[44]; // [rsp+30h] [rbp-58h] BYREF

  v6 = (*(__int64 (__fastcall **)(char *, struct IWbemContext *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16, a3);
  if ( v6 < 0 )
    goto LABEL_15;
  updated = CSCWmiConfig::UpdateWbemClassObjectProp(L"WorkOfflineButtonRemoved", *((_QWORD *)this + 6), a4, 1);
  v6 = updated;
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_SD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      145,
      (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
      (unsigned int)L"WorkOfflineButtonRemoved",
      updated);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v6 >= 0 )
  {
    v9 = CSCWmiConfig::UpdateWbemClassObjectProp(L"MakeAvailableOfflineButtonRemoved", *((_QWORD *)this + 6), a4, 1);
    v6 = v9;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        146,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"MakeAvailableOfflineButtonRemoved",
        v9);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v6 >= 0 )
    {
      v11 = CSCWmiConfig::UpdateWbemClassObjectAssignedOfflineFilesProp(
              (CSCWmiConfig *)v8,
              a4,
              *((struct IWbemClassObject **)this + 6),
              v10);
      v6 = v11;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          147,
          (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          (unsigned int)L"AssignedOfflineFiles",
          v11);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v6 >= 0 )
      {
        v13[0] = 11;
        v13[4] = ((unsigned int)GetSettingAuthority(3) != 1) - 1;
        v6 = WmiProp_SetProperty(a4, L"IsConfiguredByWMI", v13);
LABEL_15:
        v8 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_DWORD *)(v8 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v8 + 16), 148, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022030  push    rbx
0x180022032  push    rbp
0x180022033  push    rsi
0x180022034  push    rdi
0x180022035  push    r12
0x180022037  push    r15
0x180022039  sub     rsp, 58h
0x18002203d  mov     rdi, rcx
0x180022040  mov     rdx, r8
0x180022043  add     rcx, 10h
0x180022047  mov     rsi, r9
0x18002204a  mov     rax, [rcx]
0x18002204d  mov     rax, [rax+8]
0x180022051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022056  lea     r15, WPP_GLOBAL_Control
0x18002205d  mov     ebx, eax
0x18002205f  mov     ebp, 4000000h
0x180022064  test    eax, eax
0x180022066  js      loc_1800221A7
0x18002206c  mov     rdx, [rdi+30h]
0x180022070  lea     rcx, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x180022077  mov     r12d, 1
0x18002207d  mov     r8, rsi
0x180022080  mov     r9d, r12d
0x180022083  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180022088  mov     ebx, eax
0x18002208a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022091  cmp     rcx, r15
0x180022094  jz      short loc_1800220C2
0x180022096  test    [rcx+1Ch], ebp
0x180022099  jz      short loc_1800220C2
0x18002209b  mov     rcx, [rcx+10h]
0x18002209f  lea     r9, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x1800220a6  mov     edx, 91h
0x1800220ab  mov     [rsp+88h+var_68], eax
0x1800220af  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x1800220b6  call    WPP_SF_SD
0x1800220bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220c2  test    ebx, ebx
0x1800220c4  js      loc_1800221AE
0x1800220ca  mov     rdx, [rdi+30h]
0x1800220ce  lea     rcx, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x1800220d5  mov     r9d, r12d
0x1800220d8  mov     r8, rsi
0x1800220db  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x1800220e0  mov     ebx, eax
0x1800220e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220e9  cmp     rcx, r15
0x1800220ec  jz      short loc_18002211A
0x1800220ee  test    [rcx+1Ch], ebp
0x1800220f1  jz      short loc_18002211A
0x1800220f3  mov     rcx, [rcx+10h]
0x1800220f7  lea     r9, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x1800220fe  mov     edx, 92h
0x180022103  mov     [rsp+88h+var_68], eax
0x180022107  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18002210e  call    WPP_SF_SD
0x180022113  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18002211a  test    ebx, ebx
0x18002211c  js      loc_1800221AE
0x180022122  mov     r8, [rdi+30h]; struct IWbemClassObject *
0x180022126  mov     rdx, rsi; struct IWbemContext *
0x180022129  call    ?UpdateWbemClassObjectAssignedOfflineFilesProp@CSCWmiConfig@@YAJPEAUIWbemContext@@PEAUIWbemClassObject@@PEAX@Z; CSCWmiConfig::UpdateWbemClassObjectAssignedOfflineFilesProp(IWbemContext *,IWbemClassObject *,void *)
0x18002212e  mov     ebx, eax
0x180022130  mov     rcx, cs:WPP_GLOBAL_Control
0x180022137  cmp     rcx, r15
0x18002213a  jz      short loc_180022168
0x18002213c  test    [rcx+1Ch], ebp
0x18002213f  jz      short loc_180022168
0x180022141  mov     rcx, [rcx+10h]
0x180022145  lea     r9, CSCWMI_STR_PROP_ASSIGNEDOFFLINEFILES; "AssignedOfflineFiles"
0x18002214c  mov     edx, 93h
0x180022151  mov     [rsp+88h+var_68], eax
0x180022155  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18002215c  call    WPP_SF_SD
0x180022161  mov     rcx, cs:WPP_GLOBAL_Control
0x180022168  test    ebx, ebx
0x18002216a  js      short loc_1800221AE
0x18002216c  mov     ecx, 3
0x180022171  call    ?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z; GetSettingAuthority(UST_COMPONENT_ID)
0x180022176  mov     ecx, 0Bh
0x18002217b  lea     r8, [rsp+88h+var_58]
0x180022180  mov     [rsp+88h+var_58], cx
0x180022185  lea     rdx, CSCWMI_STR_PROP_ISCONFIGUREDBYWMI; "IsConfiguredByWMI"
0x18002218c  xor     ecx, ecx
0x18002218e  cmp     eax, r12d
0x180022191  setnz   cl
0x180022194  sub     cx, r12w
0x180022198  mov     [rsp+88h+var_50], cx
0x18002219d  mov     rcx, rsi
0x1800221a0  call    ?WmiProp_SetProperty@@YAJPEAUIWbemClassObject@@PEBGVCComVariant@ATL@@@Z; WmiProp_SetProperty(IWbemClassObject *,ushort const *,ATL::CComVariant)
0x1800221a5  mov     ebx, eax
0x1800221a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221ae  cmp     rcx, r15
0x1800221b1  jz      short loc_1800221D0
0x1800221b3  test    [rcx+1Ch], ebp
0x1800221b6  jz      short loc_1800221D0
0x1800221b8  mov     rcx, [rcx+10h]
0x1800221bc  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x1800221c3  mov     edx, 94h
0x1800221c8  mov     r9d, ebx
0x1800221cb  call    WPP_SF_d
0x1800221d0  mov     eax, ebx
0x1800221d2  add     rsp, 58h
0x1800221d6  pop     r15
0x1800221d8  pop     r12
0x1800221da  pop     rdi
0x1800221db  pop     rsi
0x1800221dc  pop     rbp
0x1800221dd  pop     rbx
0x1800221de  retn
```
