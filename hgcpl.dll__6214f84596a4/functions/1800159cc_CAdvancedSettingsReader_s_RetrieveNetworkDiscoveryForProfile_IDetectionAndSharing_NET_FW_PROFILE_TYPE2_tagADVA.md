# CAdvancedSettingsReader::_s_RetrieveNetworkDiscoveryForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,tagADVANCED_SETTING_READER_VALUE *)

- ea: `0x1800159cc`
- end: `0x180015af1`
- name: `?_s_RetrieveNetworkDiscoveryForProfile@CAdvancedSettingsReader@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z`
- size: `293`
- prototype: `void __fastcall(struct IDetectionAndSharing *, enum NET_FW_PROFILE_TYPE2_, struct tagADVANCED_SETTING_READER_VALUE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013368`

## callees

- `0x180006dfc`
- `0x180008fd0`
- `0x180012b2c`
- `0x180012b94`
- `0x180012da4`
- `0x180013b64`
- `0x1800159cc`
- `0x180015db8`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a8a`

## pseudocode

```c
void __fastcall CAdvancedSettingsReader::_s_RetrieveNetworkDiscoveryForProfile(
        struct IDetectionAndSharing *a1,
        unsigned int a2,
        struct tagADVANCED_SETTING_READER_VALUE *a3)
{
  char v5; // si
  __int64 v7; // rax
  signed int v8; // eax
  unsigned int v9; // ebx
  const wchar_t **v10; // rax
  __int64 v11; // rcx
  const wchar_t *v12; // r8
  int v13; // [rsp+30h] [rbp-188h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-180h] BYREF
  _QWORD v15[42]; // [rsp+40h] [rbp-178h] BYREF

  v5 = 0;
  v13 = 0;
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "RetrieveNetworkDiscovery");
  v15[0] = &AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::`vftable';
  AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::StartActivity((AdvancedSettingsTelemetry::RetrieveNetworkDiscovery *)v15);
  v7 = *(_QWORD *)a1;
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IDetectionAndSharing *, _QWORD, _QWORD, int *, _QWORD))(v7 + 48))(
         a1,
         a2,
         0,
         &v13,
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 1) != 0 )
    {
      v10 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v8);
      v12 = L"???";
      if ( *v10 )
        v12 = *v10;
      McTemplateU0z_EventWriteTransfer(v11, Operational_RetrieveNetworkDiscoveryFailed, v12);
      v5 = 1;
    }
    if ( (v5 & 1) != 0 )
      LocalFree(hMem);
    v13 = 0;
  }
  *(_DWORD *)a3 = IsOnFromValue_enum__DtshState_(qword_18001EC10);
  *((_DWORD *)a3 + 1) = ButtonFromValue_enum__DtshState_();
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15, v9);
  AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::~RetrieveNetworkDiscovery((AdvancedSettingsTelemetry::RetrieveNetworkDiscovery *)v15);
}

```

## disassembly

```asm
0x1800159cc  mov     [rsp+arg_18], rbx
0x1800159d1  push    rsi
0x1800159d2  push    rdi
0x1800159d3  push    r14
0x1800159d5  sub     rsp, 1A0h
0x1800159dc  mov     rax, cs:__security_cookie
0x1800159e3  xor     rax, rsp
0x1800159e6  mov     [rsp+1B8h+var_28], rax
0x1800159ee  mov     edi, edx
0x1800159f0  mov     rbx, rcx
0x1800159f3  xor     esi, esi
0x1800159f5  lea     rdx, aRetrievenetwor; "RetrieveNetworkDiscovery"
0x1800159fc  lea     rcx, [rsp+1B8h+var_178]
0x180015a01  mov     [rsp+1B8h+var_188], esi
0x180015a05  mov     r14, r8
0x180015a08  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015a0d  lea     rax, ??_7RetrieveNetworkDiscovery@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::`vftable'
0x180015a14  lea     rcx, [rsp+1B8h+var_178]; this
0x180015a19  mov     [rsp+1B8h+var_178], rax
0x180015a1e  call    ?StartActivity@RetrieveNetworkDiscovery@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::StartActivity(void)
0x180015a23  mov     rax, [rbx]
0x180015a26  lea     r9, [rsp+1B8h+var_188]
0x180015a2b  xor     r8d, r8d
0x180015a2e  mov     [rsp+1B8h+var_188], esi
0x180015a32  mov     edx, edi
0x180015a34  mov     [rsp+1B8h+var_198], rsi
0x180015a39  mov     rcx, rbx
0x180015a3c  mov     rax, [rax+30h]
0x180015a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a45  mov     ebx, eax
0x180015a47  test    eax, eax
0x180015a49  jns     short loc_180015A9A
0x180015a4b  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 1
0x180015a52  jz      short loc_180015A7F
0x180015a54  mov     edx, eax; dwMessageId
0x180015a56  lea     rcx, [rsp+1B8h+hMem]; lpBuffer
0x180015a5b  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180015a60  lea     r8, asc_18001ECC8; "???"
0x180015a67  lea     rdx, Operational_RetrieveNetworkDiscoveryFailed
0x180015a6e  cmp     [rax], rsi
0x180015a71  cmovnz  r8, [rax]
0x180015a75  call    McTemplateU0z_EventWriteTransfer
0x180015a7a  mov     esi, 1
0x180015a7f  test    sil, 1
0x180015a83  jz      short loc_180015A90
0x180015a85  mov     rcx, [rsp+1B8h+hMem]; hMem
0x180015a8a  call    cs:__imp_LocalFree
0x180015a90  xor     r8d, r8d
0x180015a93  mov     [rsp+1B8h+var_188], r8d
0x180015a98  jmp     short loc_180015A9F
0x180015a9a  mov     r8d, [rsp+1B8h+var_188]
0x180015a9f  lea     rcx, qword_18001EC10
0x180015aa6  call    _IsOnFromValue_enum__DtshState_
0x180015aab  mov     [r14], eax
0x180015aae  call    _ButtonFromValue_enum__DtshState_
0x180015ab3  mov     edx, ebx
0x180015ab5  mov     [r14+4], eax
0x180015ab9  lea     rcx, [rsp+1B8h+var_178]
0x180015abe  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180015ac3  lea     rcx, [rsp+1B8h+var_178]; this
0x180015ac8  call    ??1RetrieveNetworkDiscovery@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::~RetrieveNetworkDiscovery(void)
0x180015acd  mov     rcx, [rsp+1B8h+var_28]
0x180015ad5  xor     rcx, rsp; StackCookie
0x180015ad8  call    __security_check_cookie
0x180015add  mov     rbx, [rsp+1B8h+arg_18]
0x180015ae5  add     rsp, 1A0h
0x180015aec  pop     r14
0x180015aee  pop     rdi
0x180015aef  pop     rsi
0x180015af0  retn
```
