# CAdvancedSettingsWriter::_s_CommitNetworkDiscoveryForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,ADVANCED_SETTING_WRITER_VALUE const &,HWND__ *)

- ea: `0x1800151fc`
- end: `0x18001531e`
- name: `?_s_CommitNetworkDiscoveryForProfile@CAdvancedSettingsWriter@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@AEBUADVANCED_SETTING_WRITER_VALUE@@PEAUHWND__@@@Z`
- size: `290`
- prototype: `void __fastcall(struct IDetectionAndSharing *, enum NET_FW_PROFILE_TYPE2_, const struct ADVANCED_SETTING_WRITER_VALUE *, HWND)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012e00`

## callees

- `0x180006dfc`
- `0x180008fd0`
- `0x180012bfc`
- `0x180012cc8`
- `0x1800137a4`
- `0x1800151fc`
- `0x180015e38`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152db`

## string_xrefs

- `0x180015229`: `CommitNetworkDiscovery`

## pseudocode

```c
void __fastcall CAdvancedSettingsWriter::_s_CommitNetworkDiscoveryForProfile(
        struct IDetectionAndSharing *a1,
        unsigned int a2,
        const struct ADVANCED_SETTING_WRITER_VALUE *a3,
        HWND a4)
{
  char v6; // r14
  __int64 v9; // rdx
  BOOL v10; // r15d
  signed int v11; // eax
  unsigned int v12; // ebx
  const wchar_t **v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // r8
  HLOCAL hMem[2]; // [rsp+30h] [rbp-198h] BYREF
  _QWORD v17[42]; // [rsp+40h] [rbp-188h] BYREF

  v6 = 0;
  LODWORD(hMem[0]) = 0;
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "CommitNetworkDiscovery");
  v17[0] = &AdvancedSettingsTelemetry::CommitNetworkDiscovery::`vftable';
  AdvancedSettingsTelemetry::CommitNetworkDiscovery::StartActivity((AdvancedSettingsTelemetry::CommitNetworkDiscovery *)v17);
  v10 = ValueFromButton_enum__DtshState_(qword_18001EC10, v9, *((unsigned int *)a3 + 1)) == 1;
  v11 = (*(__int64 (__fastcall **)(struct IDetectionAndSharing *, HWND, _QWORD, _QWORD, BOOL))(*(_QWORD *)a1 + 56LL))(
          a1,
          a4,
          a2,
          0,
          v10);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 1) != 0 )
    {
      v13 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)hMem, v11);
      v15 = L"???";
      if ( *v13 )
        v15 = *v13;
      McTemplateU0zq_EventWriteTransfer(v14, Operational_CommitNetworkDiscoveryFailed, v15, v10);
      v6 = 1;
    }
    if ( (v6 & 1) != 0 )
      LocalFree(hMem[0]);
  }
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17, v12);
  AdvancedSettingsTelemetry::CommitNetworkDiscovery::~CommitNetworkDiscovery((AdvancedSettingsTelemetry::CommitNetworkDiscovery *)v17);
}

```

## disassembly

```asm
0x1800151fc  mov     [rsp+arg_10], rbx
0x180015201  push    rbp
0x180015202  push    rsi
0x180015203  push    rdi
0x180015204  push    r14
0x180015206  push    r15
0x180015208  sub     rsp, 1A0h
0x18001520f  mov     rax, cs:__security_cookie
0x180015216  xor     rax, rsp
0x180015219  mov     [rsp+1C8h+var_38], rax
0x180015221  mov     edi, edx
0x180015223  mov     rsi, rcx
0x180015226  xor     r14d, r14d
0x180015229  lea     rdx, aCommitnetworkd; "CommitNetworkDiscovery"
0x180015230  lea     rcx, [rsp+1C8h+var_188]
0x180015235  mov     dword ptr [rsp+1C8h+hMem], r14d
0x18001523a  mov     rbp, r9
0x18001523d  mov     rbx, r8
0x180015240  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015245  lea     rax, ??_7CommitNetworkDiscovery@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitNetworkDiscovery::`vftable'
0x18001524c  lea     rcx, [rsp+1C8h+var_188]; this
0x180015251  mov     [rsp+1C8h+var_188], rax
0x180015256  call    ?StartActivity@CommitNetworkDiscovery@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::CommitNetworkDiscovery::StartActivity(void)
0x18001525b  mov     r8d, [rbx+4]
0x18001525f  lea     rcx, qword_18001EC10
0x180015266  call    _ValueFromButton_enum__DtshState_
0x18001526b  xor     r15d, r15d
0x18001526e  mov     r8d, edi
0x180015271  cmp     eax, 1
0x180015274  mov     rdx, rbp
0x180015277  mov     rax, [rsi]
0x18001527a  mov     rcx, rsi
0x18001527d  setz    r15b
0x180015281  xor     r9d, r9d
0x180015284  mov     [rsp+1C8h+var_1A8], r15d
0x180015289  mov     rax, [rax+38h]
0x18001528d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015292  mov     ebx, eax
0x180015294  test    eax, eax
0x180015296  jns     short loc_1800152E1
0x180015298  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 1
0x18001529f  jz      short loc_1800152D0
0x1800152a1  mov     edx, eax; dwMessageId
0x1800152a3  lea     rcx, [rsp+1C8h+hMem]; lpBuffer
0x1800152a8  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x1800152ad  lea     r8, asc_18001ECC8; "???"
0x1800152b4  mov     r9d, r15d
0x1800152b7  lea     rdx, Operational_CommitNetworkDiscoveryFailed
0x1800152be  cmp     [rax], r14
0x1800152c1  cmovnz  r8, [rax]
0x1800152c5  call    McTemplateU0zq_EventWriteTransfer
0x1800152ca  mov     r14d, 1
0x1800152d0  test    r14b, 1
0x1800152d4  jz      short loc_1800152E1
0x1800152d6  mov     rcx, [rsp+1C8h+hMem]; hMem
0x1800152db  call    cs:__imp_LocalFree
0x1800152e1  mov     edx, ebx
0x1800152e3  lea     rcx, [rsp+1C8h+var_188]
0x1800152e8  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800152ed  lea     rcx, [rsp+1C8h+var_188]; this
0x1800152f2  call    ??1CommitNetworkDiscovery@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::CommitNetworkDiscovery::~CommitNetworkDiscovery(void)
0x1800152f7  mov     rcx, [rsp+1C8h+var_38]
0x1800152ff  xor     rcx, rsp; StackCookie
0x180015302  call    __security_check_cookie
0x180015307  mov     rbx, [rsp+1C8h+arg_10]
0x18001530f  add     rsp, 1A0h
0x180015316  pop     r15
0x180015318  pop     r14
0x18001531a  pop     rdi
0x18001531b  pop     rsi
0x18001531c  pop     rbp
0x18001531d  retn
```
