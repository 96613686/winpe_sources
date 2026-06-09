# CAdvancedPage::_s_CommitAdvancedSettings(void *)

- ea: `0x18000a9c0`
- end: `0x18000abc1`
- name: `?_s_CommitAdvancedSettings@CAdvancedPage@@CAKPEAX@Z`
- size: `513`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006dfc`
- `0x180007170`
- `0x1800072cc`
- `0x180008bfc`
- `0x180008fd0`
- `0x18000a640`
- `0x18000a9c0`
- `0x18000b18c`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aab6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aab6`

## string_xrefs

- `0x18000aa15`: `CommitSettings`

## pseudocode

```c
__int64 __fastcall CAdvancedPage::_s_CommitAdvancedSettings(CMarshaledInterface *Parameter, __int64 a2, __int64 a3)
{
  const struct _GUID *v4; // rdx
  bool v5; // r9
  bool v6; // zf
  HRESULT Instance; // ebx
  __int64 v8; // rdx
  HRESULT v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  void *v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v15[42]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv[2]; // [rsp+190h] [rbp+90h] BYREF

  if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(Parameter, Perf_Settings_AdvancedPageCommit_Start, a3, 1, ppv);
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "CommitSettings");
  v15[0] = &AdvancedSettingsTelemetry::CommitSettings::`vftable';
  AdvancedSettingsTelemetry::CommitSettings::StartActivity((AdvancedSettingsTelemetry::CommitSettings *)v15);
  v6 = *(_QWORD *)Parameter == 0;
  v13 = 0;
  if ( v6 )
  {
    Instance = -2147467259;
  }
  else
  {
    Instance = CMarshaledInterface::_Unmarshal(Parameter, v4, &v13, v5);
    if ( Instance >= 0 )
    {
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, *((_QWORD *)Parameter + 1));
      if ( *((_DWORD *)Parameter + 4) )
      {
        ppv[0] = 0;
        Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     ppv);
        if ( Instance >= 0 )
        {
          v8 = *((unsigned int *)Parameter + 4);
          v14 = 0;
          Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, __int64 *))(*(_QWORD *)ppv[0] + 40LL))(
                       ppv[0],
                       v8,
                       &GUID_2edfba4a_2ec9_4b2e_b133_40624a784bec,
                       &v14);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
        }
      }
      v9 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v13 + 48LL))(v13);
      if ( Instance >= 0 )
        Instance = v9;
      (*(void (**)(void))(*(_QWORD *)v13 + 16LL))();
    }
  }
  if ( Parameter )
    ADVANCED_PAGE_COMMIT_CONTEXT::`scalar deleting destructor'(Parameter, (unsigned int)v4);
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v15,
    (unsigned int)Instance);
  if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v10, Perf_Settings_AdvancedPageCommit_Stop, v11, 1, ppv);
  AdvancedSettingsTelemetry::CommitSettings::~CommitSettings((AdvancedSettingsTelemetry::CommitSettings *)v15);
  return 0;
}

```

## disassembly

```asm
0x18000a9c0  mov     [rsp-8+arg_8], rbx
0x18000a9c5  mov     [rsp-8+arg_10], rdi
0x18000a9ca  push    rbp
0x18000a9cb  lea     rbp, [rsp-0B0h]
0x18000a9d3  sub     rsp, 1B0h
0x18000a9da  mov     rax, cs:__security_cookie
0x18000a9e1  xor     rax, rsp
0x18000a9e4  mov     [rbp+0B0h+var_10], rax
0x18000a9eb  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 4
0x18000a9f2  mov     rdi, rcx
0x18000a9f5  jz      short loc_18000AA15
0x18000a9f7  lea     rax, [rbp+0B0h+var_20]
0x18000a9fe  mov     r9d, 1
0x18000aa04  lea     rdx, Perf_Settings_AdvancedPageCommit_Start
0x18000aa0b  mov     [rsp+1B0h+ppv], rax
0x18000aa10  call    McGenEventWrite_EventWriteTransfer
0x18000aa15  lea     rdx, aCommitsettings; "CommitSettings"
0x18000aa1c  lea     rcx, [rsp+1B0h+var_170]
0x18000aa21  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000aa26  lea     rax, ??_7CommitSettings@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitSettings::`vftable'
0x18000aa2d  lea     rcx, [rsp+1B0h+var_170]; this
0x18000aa32  mov     [rsp+1B0h+var_170], rax
0x18000aa37  call    ?StartActivity@CommitSettings@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::CommitSettings::StartActivity(void)
0x18000aa3c  cmp     qword ptr [rdi], 0
0x18000aa40  mov     [rsp+1B0h+var_180], 0
0x18000aa49  jnz     short loc_18000AA55
0x18000aa4b  mov     ebx, 80004005h
0x18000aa50  jmp     loc_18000AB51
0x18000aa55  lea     r8, [rsp+1B0h+var_180]; void **
0x18000aa5a  mov     rcx, rdi; this
0x18000aa5d  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x18000aa62  mov     ebx, eax
0x18000aa64  test    eax, eax
0x18000aa66  js      loc_18000AB51
0x18000aa6c  mov     rcx, [rsp+1B0h+var_180]
0x18000aa71  mov     rdx, [rdi+8]
0x18000aa75  mov     rax, [rcx]
0x18000aa78  mov     rax, [rax+28h]
0x18000aa7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa81  cmp     dword ptr [rdi+10h], 0
0x18000aa85  jbe     loc_18000AB2A
0x18000aa8b  xor     edx, edx; pUnkOuter
0x18000aa8d  mov     [rbp+0B0h+var_20], 0
0x18000aa98  lea     rax, [rbp+0B0h+var_20]
0x18000aa9f  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000aaa6  mov     [rsp+1B0h+ppv], rax; ppv
0x18000aaab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000aab2  lea     r8d, [rdx+1]; dwClsContext
0x18000aab6  call    cs:__imp_CoCreateInstance
0x18000aabc  mov     ebx, eax
0x18000aabe  test    eax, eax
0x18000aac0  js      short loc_18000AB2A
0x18000aac2  mov     rcx, [rbp+0B0h+var_20]
0x18000aac9  lea     r9, [rsp+1B0h+var_178]
0x18000aace  mov     edx, [rdi+10h]
0x18000aad1  lea     r8, _GUID_2edfba4a_2ec9_4b2e_b133_40624a784bec
0x18000aad8  mov     [rsp+1B0h+var_178], 0
0x18000aae1  mov     rax, [rcx]
0x18000aae4  mov     rax, [rax+28h]
0x18000aae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaed  mov     ebx, eax
0x18000aaef  test    eax, eax
0x18000aaf1  js      short loc_18000AB17
0x18000aaf3  mov     rcx, [rsp+1B0h+var_178]
0x18000aaf8  mov     rax, [rcx]
0x18000aafb  mov     rax, [rax+38h]
0x18000aaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab04  mov     rcx, [rsp+1B0h+var_178]
0x18000ab09  mov     ebx, eax
0x18000ab0b  mov     rax, [rcx]
0x18000ab0e  mov     rax, [rax+10h]
0x18000ab12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab17  mov     rcx, [rbp+0B0h+var_20]
0x18000ab1e  mov     rax, [rcx]
0x18000ab21  mov     rax, [rax+10h]
0x18000ab25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab2a  mov     rcx, [rsp+1B0h+var_180]
0x18000ab2f  mov     rax, [rcx]
0x18000ab32  mov     rax, [rax+30h]
0x18000ab36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab3b  mov     rcx, [rsp+1B0h+var_180]
0x18000ab40  test    ebx, ebx
0x18000ab42  cmovns  ebx, eax
0x18000ab45  mov     rax, [rcx]
0x18000ab48  mov     rax, [rax+10h]
0x18000ab4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab51  test    rdi, rdi
0x18000ab54  jz      short loc_18000AB5E
0x18000ab56  mov     rcx, rdi; this
0x18000ab59  call    ??_GADVANCED_PAGE_COMMIT_CONTEXT@@QEAAPEAXI@Z; ADVANCED_PAGE_COMMIT_CONTEXT::`scalar deleting destructor'(uint)
0x18000ab5e  mov     edx, ebx
0x18000ab60  lea     rcx, [rsp+1B0h+var_170]
0x18000ab65  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000ab6a  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 4
0x18000ab71  jz      short loc_18000AB91
0x18000ab73  lea     rax, [rbp+0B0h+var_20]
0x18000ab7a  mov     r9d, 1
0x18000ab80  lea     rdx, Perf_Settings_AdvancedPageCommit_Stop
0x18000ab87  mov     [rsp+1B0h+ppv], rax
0x18000ab8c  call    McGenEventWrite_EventWriteTransfer
0x18000ab91  lea     rcx, [rsp+1B0h+var_170]; this
0x18000ab96  call    ??1CommitSettings@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::CommitSettings::~CommitSettings(void)
0x18000ab9b  xor     eax, eax
0x18000ab9d  mov     rcx, [rbp+0B0h+var_10]
0x18000aba4  xor     rcx, rsp; StackCookie
0x18000aba7  call    __security_check_cookie
0x18000abac  lea     r11, [rsp+1B0h+var_s0]
0x18000abb4  mov     rbx, [r11+18h]
0x18000abb8  mov     rdi, [r11+20h]
0x18000abbc  mov     rsp, r11
0x18000abbf  pop     rbp
0x18000abc0  retn
```
