# CAdvancedPage::_s_DoGetAdvancedSettings(ulong)

- ea: `0x18000abc8`
- end: `0x18000add7`
- name: `?_s_DoGetAdvancedSettings@CAdvancedPage@@CAXK@Z`
- size: `527`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ade0`

## callees

- `0x180006dfc`
- `0x180007230`
- `0x18000766c`
- `0x180008e9c`
- `0x180008fd0`
- `0x18000abc8`
- `0x18000b18c`
- `0x18000bd88`
- `0x1800132e0`
- `0x180013368`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ac64`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ac64`

## pseudocode

```c
void __fastcall CAdvancedPage::_s_DoGetAdvancedSettings(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  HRESULT CurrentValues; // ebx
  unsigned __int64 v5; // rdx
  int v6; // esi
  __int64 v7; // rdx
  unsigned int i; // eax
  struct tagADVANCED_SETTING_READER_VALUE *v9; // rax
  struct tagADVANCED_SETTING_READER_VALUE *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // r8
  NET_FW_PROFILE_TYPE2_ v13; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v15[42]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+190h] [rbp+90h] BYREF

  v3 = a1;
  if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      a1,
      (const EVENT_DESCRIPTOR *)Perf_Settings_AdvancedPageRetrieve_Start,
      a3,
      1u,
      &v16);
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "RetrieveSettings");
  v15[0] = &AdvancedSettingsTelemetry::RetrieveSettings::`vftable';
  AdvancedSettingsTelemetry::RetrieveSettings::StartActivity((AdvancedSettingsTelemetry::RetrieveSettings *)v15);
  ppv = 0;
  CurrentValues = CoCreateInstance(
                    &CLSID_StdGlobalInterfaceTable,
                    0,
                    1u,
                    &GUID_00000146_0000_0000_c000_000000000046,
                    &ppv);
  if ( CurrentValues >= 0 )
  {
    v16.Ptr = 0;
    CurrentValues = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)ppv + 40LL))(
                      ppv,
                      v3,
                      &GUID_2edfba4a_2ec9_4b2e_b133_40624a784bec,
                      &v16);
    if ( CurrentValues >= 0 )
    {
      v13 = 0;
      v6 = CAdvancedSettingsReader::RetrieveCurrentProfile(&v13);
      if ( v6 >= 0 )
      {
        v7 = 0;
        for ( i = 0; i < 4; ++i )
        {
          if ( LODWORD(qword_18001C220[2 * i]) == v13 )
          {
            v7 = HIDWORD(qword_18001C220[2 * i]);
            break;
          }
        }
        v6 = (*(__int64 (__fastcall **)(ULONGLONG, __int64))(*(_QWORD *)v16.Ptr + 32LL))(v16.Ptr, v7);
      }
      v9 = (struct tagADVANCED_SETTING_READER_VALUE *)DirectUI::HAllocAndZero((DirectUI *)0x60, v5);
      v10 = v9;
      CurrentValues = v9 == 0 ? 0x8007000E : 0;
      if ( v9 )
      {
        CurrentValues = CAdvancedSettingsReader::RetrieveCurrentValues(v9);
        if ( CurrentValues >= 0 )
          CurrentValues = (*(__int64 (__fastcall **)(ULONGLONG, struct tagADVANCED_SETTING_READER_VALUE *))(*(_QWORD *)v16.Ptr + 24LL))(
                            v16.Ptr,
                            v10);
        operator delete(v10);
      }
      (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v16.Ptr + 16LL))(v16.Ptr);
      if ( v6 < 0 )
        CurrentValues = v6;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v15,
    CurrentValues);
  if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v11,
      (const EVENT_DESCRIPTOR *)Perf_Settings_AdvancedPageRetrieve_Stop,
      v12,
      1u,
      &v16);
  AdvancedSettingsTelemetry::RetrieveSettings::~RetrieveSettings((AdvancedSettingsTelemetry::RetrieveSettings *)v15);
}

```

## disassembly

```asm
0x18000abc8  push    rbp
0x18000abca  push    rbx
0x18000abcb  push    rsi
0x18000abcc  push    rdi
0x18000abcd  lea     rbp, [rsp-0B8h]
0x18000abd5  sub     rsp, 1B8h
0x18000abdc  mov     rax, cs:__security_cookie
0x18000abe3  xor     rax, rsp
0x18000abe6  mov     [rbp+0D0h+var_30], rax
0x18000abed  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 4
0x18000abf4  mov     edi, ecx
0x18000abf6  jz      short loc_18000AC16
0x18000abf8  lea     rax, [rbp+0D0h+var_40]
0x18000abff  mov     r9d, 1
0x18000ac05  lea     rdx, Perf_Settings_AdvancedPageRetrieve_Start
0x18000ac0c  mov     [rsp+1D0h+ppv], rax
0x18000ac11  call    McGenEventWrite_EventWriteTransfer
0x18000ac16  lea     rdx, aRetrievesettin; "RetrieveSettings"
0x18000ac1d  lea     rcx, [rsp+1D0h+var_190]
0x18000ac22  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ac27  lea     rax, ??_7RetrieveSettings@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::RetrieveSettings::`vftable'
0x18000ac2e  lea     rcx, [rsp+1D0h+var_190]; this
0x18000ac33  mov     [rsp+1D0h+var_190], rax
0x18000ac38  call    ?StartActivity@RetrieveSettings@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::RetrieveSettings::StartActivity(void)
0x18000ac3d  xor     edx, edx; pUnkOuter
0x18000ac3f  mov     [rsp+1D0h+var_198], 0
0x18000ac48  lea     rax, [rsp+1D0h+var_198]
0x18000ac4d  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000ac54  mov     [rsp+1D0h+ppv], rax; ppv
0x18000ac59  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000ac60  lea     r8d, [rdx+1]; dwClsContext
0x18000ac64  call    cs:__imp_CoCreateInstance
0x18000ac6a  mov     ebx, eax
0x18000ac6c  test    eax, eax
0x18000ac6e  js      loc_18000AD7F
0x18000ac74  mov     rcx, [rsp+1D0h+var_198]
0x18000ac79  lea     r9, [rbp+0D0h+var_40]
0x18000ac80  mov     qword ptr [rbp+0D0h+var_40], 0
0x18000ac8b  lea     r8, _GUID_2edfba4a_2ec9_4b2e_b133_40624a784bec
0x18000ac92  mov     edx, edi
0x18000ac94  mov     rax, [rcx]
0x18000ac97  mov     rax, [rax+28h]
0x18000ac9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aca0  mov     ebx, eax
0x18000aca2  test    eax, eax
0x18000aca4  js      loc_18000AD6E
0x18000acaa  lea     rcx, [rsp+1D0h+var_1A0]; enum NET_FW_PROFILE_TYPE2_ *
0x18000acaf  mov     [rsp+1D0h+var_1A0], 0
0x18000acb7  call    ?RetrieveCurrentProfile@CAdvancedSettingsReader@@SAJPEAW4NET_FW_PROFILE_TYPE2_@@@Z; CAdvancedSettingsReader::RetrieveCurrentProfile(NET_FW_PROFILE_TYPE2_ *)
0x18000acbc  mov     esi, eax
0x18000acbe  test    eax, eax
0x18000acc0  js      short loc_18000AD06
0x18000acc2  mov     r8, qword ptr [rbp+0D0h+var_40]
0x18000acc9  lea     r11, qword_18001C220
0x18000acd0  mov     r9d, [rsp+1D0h+var_1A0]
0x18000acd5  xor     edx, edx
0x18000acd7  mov     rax, [r8]
0x18000acda  mov     r10, [rax+20h]
0x18000acde  xor     eax, eax
0x18000ace0  cmp     eax, 4
0x18000ace3  jnb     short loc_18000ACF9
0x18000ace5  mov     ecx, eax
0x18000ace7  add     rcx, rcx
0x18000acea  cmp     [r11+rcx*8], r9d
0x18000acee  jz      short loc_18000ACF4
0x18000acf0  inc     eax
0x18000acf2  jmp     short loc_18000ACE0
0x18000acf4  mov     edx, [r11+rcx*8+4]
0x18000acf9  mov     rcx, r8
0x18000acfc  mov     rax, r10
0x18000acff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad04  mov     esi, eax
0x18000ad06  mov     ecx, 60h ; '`'; this
0x18000ad0b  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000ad10  mov     rcx, rax
0x18000ad13  mov     rdi, rax
0x18000ad16  neg     rcx
0x18000ad19  sbb     ebx, ebx
0x18000ad1b  not     ebx
0x18000ad1d  and     ebx, 8007000Eh
0x18000ad23  test    rax, rax
0x18000ad26  jz      short loc_18000AD56
0x18000ad28  mov     rcx, rax; struct tagADVANCED_SETTING_READER_VALUE *
0x18000ad2b  call    ?RetrieveCurrentValues@CAdvancedSettingsReader@@SAJPEAUtagADVANCED_SETTING_READER_VALUE@@@Z; CAdvancedSettingsReader::RetrieveCurrentValues(tagADVANCED_SETTING_READER_VALUE *)
0x18000ad30  mov     ebx, eax
0x18000ad32  test    eax, eax
0x18000ad34  js      short loc_18000AD4E
0x18000ad36  mov     rcx, qword ptr [rbp+0D0h+var_40]
0x18000ad3d  mov     rdx, rdi
0x18000ad40  mov     rax, [rcx]
0x18000ad43  mov     rax, [rax+18h]
0x18000ad47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad4c  mov     ebx, eax
0x18000ad4e  mov     rcx, rdi; lpMem
0x18000ad51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ad56  mov     rcx, qword ptr [rbp+0D0h+var_40]
0x18000ad5d  mov     rax, [rcx]
0x18000ad60  mov     rax, [rax+10h]
0x18000ad64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad69  test    esi, esi
0x18000ad6b  cmovs   ebx, esi
0x18000ad6e  mov     rcx, [rsp+1D0h+var_198]
0x18000ad73  mov     rax, [rcx]
0x18000ad76  mov     rax, [rax+10h]
0x18000ad7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad7f  mov     edx, ebx
0x18000ad81  lea     rcx, [rsp+1D0h+var_190]
0x18000ad86  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000ad8b  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 4
0x18000ad92  jz      short loc_18000ADB2
0x18000ad94  lea     rax, [rbp+0D0h+var_40]
0x18000ad9b  mov     r9d, 1
0x18000ada1  lea     rdx, Perf_Settings_AdvancedPageRetrieve_Stop
0x18000ada8  mov     [rsp+1D0h+ppv], rax
0x18000adad  call    McGenEventWrite_EventWriteTransfer
0x18000adb2  lea     rcx, [rsp+1D0h+var_190]; this
0x18000adb7  call    ??1RetrieveSettings@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::RetrieveSettings::~RetrieveSettings(void)
0x18000adbc  mov     rcx, [rbp+0D0h+var_30]
0x18000adc3  xor     rcx, rsp; StackCookie
0x18000adc6  call    __security_check_cookie
0x18000adcb  add     rsp, 1B8h
0x18000add2  pop     rdi
0x18000add3  pop     rsi
0x18000add4  pop     rbx
0x18000add5  pop     rbp
0x18000add6  retn
```
