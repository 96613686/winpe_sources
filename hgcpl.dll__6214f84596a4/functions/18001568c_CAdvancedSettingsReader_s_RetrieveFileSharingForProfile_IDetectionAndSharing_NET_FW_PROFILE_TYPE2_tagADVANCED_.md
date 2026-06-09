# CAdvancedSettingsReader::_s_RetrieveFileSharingForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,tagADVANCED_SETTING_READER_VALUE *)

- ea: `0x18001568c`
- end: `0x1800157b2`
- name: `?_s_RetrieveFileSharingForProfile@CAdvancedSettingsReader@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z`
- size: `294`
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
- `0x180012d4c`
- `0x1800139e4`
- `0x18001568c`
- `0x180015db8`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001574b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001574b`

## pseudocode

```c
void __fastcall CAdvancedSettingsReader::_s_RetrieveFileSharingForProfile(
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
    "RetrieveFileSharing");
  v15[0] = &AdvancedSettingsTelemetry::RetrieveFileSharing::`vftable';
  AdvancedSettingsTelemetry::RetrieveFileSharing::StartActivity((AdvancedSettingsTelemetry::RetrieveFileSharing *)v15);
  v7 = *(_QWORD *)a1;
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IDetectionAndSharing *, _QWORD, __int64, int *, _QWORD))(v7 + 48))(
         a1,
         a2,
         1,
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
      McTemplateU0z_EventWriteTransfer(v11, Operational_RetrieveFileSharingFailed, v12);
      v5 = 1;
    }
    if ( (v5 & 1) != 0 )
      LocalFree(hMem);
    v13 = 0;
  }
  *(_DWORD *)a3 = IsOnFromValue_enum__DtshState_(qword_18001EBC0);
  *((_DWORD *)a3 + 1) = ButtonFromValue_enum__DtshState_();
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15, v9);
  AdvancedSettingsTelemetry::RetrieveFileSharing::~RetrieveFileSharing((AdvancedSettingsTelemetry::RetrieveFileSharing *)v15);
}

```

## disassembly

```asm
0x18001568c  mov     [rsp+arg_18], rbx
0x180015691  push    rsi
0x180015692  push    rdi
0x180015693  push    r14
0x180015695  sub     rsp, 1A0h
0x18001569c  mov     rax, cs:__security_cookie
0x1800156a3  xor     rax, rsp
0x1800156a6  mov     [rsp+1B8h+var_28], rax
0x1800156ae  mov     edi, edx
0x1800156b0  mov     rbx, rcx
0x1800156b3  xor     esi, esi
0x1800156b5  lea     rdx, aRetrievefilesh; "RetrieveFileSharing"
0x1800156bc  lea     rcx, [rsp+1B8h+var_178]
0x1800156c1  mov     [rsp+1B8h+var_188], esi
0x1800156c5  mov     r14, r8
0x1800156c8  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800156cd  lea     rax, ??_7RetrieveFileSharing@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::RetrieveFileSharing::`vftable'
0x1800156d4  lea     rcx, [rsp+1B8h+var_178]; this
0x1800156d9  mov     [rsp+1B8h+var_178], rax
0x1800156de  call    ?StartActivity@RetrieveFileSharing@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::RetrieveFileSharing::StartActivity(void)
0x1800156e3  mov     rax, [rbx]
0x1800156e6  lea     r9, [rsp+1B8h+var_188]
0x1800156eb  lea     r8d, [rsi+1]
0x1800156ef  mov     [rsp+1B8h+var_188], esi
0x1800156f3  mov     edx, edi
0x1800156f5  mov     [rsp+1B8h+var_198], rsi
0x1800156fa  mov     rcx, rbx
0x1800156fd  mov     rax, [rax+30h]
0x180015701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015706  mov     ebx, eax
0x180015708  test    eax, eax
0x18001570a  jns     short loc_18001575B
0x18001570c  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 1
0x180015713  jz      short loc_180015740
0x180015715  mov     edx, eax; dwMessageId
0x180015717  lea     rcx, [rsp+1B8h+hMem]; lpBuffer
0x18001571c  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180015721  lea     r8, asc_18001ECC8; "???"
0x180015728  lea     rdx, Operational_RetrieveFileSharingFailed
0x18001572f  cmp     [rax], rsi
0x180015732  cmovnz  r8, [rax]
0x180015736  call    McTemplateU0z_EventWriteTransfer
0x18001573b  mov     esi, 1
0x180015740  test    sil, 1
0x180015744  jz      short loc_180015751
0x180015746  mov     rcx, [rsp+1B8h+hMem]; hMem
0x18001574b  call    cs:__imp_LocalFree
0x180015751  xor     r8d, r8d
0x180015754  mov     [rsp+1B8h+var_188], r8d
0x180015759  jmp     short loc_180015760
0x18001575b  mov     r8d, [rsp+1B8h+var_188]
0x180015760  lea     rcx, qword_18001EBC0
0x180015767  call    _IsOnFromValue_enum__DtshState_
0x18001576c  mov     [r14], eax
0x18001576f  call    _ButtonFromValue_enum__DtshState_
0x180015774  mov     edx, ebx
0x180015776  mov     [r14+4], eax
0x18001577a  lea     rcx, [rsp+1B8h+var_178]
0x18001577f  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180015784  lea     rcx, [rsp+1B8h+var_178]; this
0x180015789  call    ??1RetrieveFileSharing@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::RetrieveFileSharing::~RetrieveFileSharing(void)
0x18001578e  mov     rcx, [rsp+1B8h+var_28]
0x180015796  xor     rcx, rsp; StackCookie
0x180015799  call    __security_check_cookie
0x18001579e  mov     rbx, [rsp+1B8h+arg_18]
0x1800157a6  add     rsp, 1A0h
0x1800157ad  pop     r14
0x1800157af  pop     rdi
0x1800157b0  pop     rsi
0x1800157b1  retn
```
