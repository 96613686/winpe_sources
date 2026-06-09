# CAdvancedSettingsWriter::_s_CommitFileSharingForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,ADVANCED_SETTING_WRITER_VALUE const &,HWND__ *)

- ea: `0x180014f30`
- end: `0x180015053`
- name: `?_s_CommitFileSharingForProfile@CAdvancedSettingsWriter@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@AEBUADVANCED_SETTING_WRITER_VALUE@@PEAUHWND__@@@Z`
- size: `291`
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
- `0x180012c9c`
- `0x1800136e4`
- `0x180014f30`
- `0x180015e38`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015010`

## string_xrefs

- `0x180014f5d`: `CommitFileSharing`

## pseudocode

```c
void __fastcall CAdvancedSettingsWriter::_s_CommitFileSharingForProfile(
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
    "CommitFileSharing");
  v17[0] = &AdvancedSettingsTelemetry::CommitFileSharing::`vftable';
  AdvancedSettingsTelemetry::CommitFileSharing::StartActivity((AdvancedSettingsTelemetry::CommitFileSharing *)v17);
  v10 = ValueFromButton_enum__DtshState_(qword_18001EBC0, v9, *((unsigned int *)a3 + 1)) == 1;
  v11 = (*(__int64 (__fastcall **)(struct IDetectionAndSharing *, HWND, _QWORD, __int64, BOOL))(*(_QWORD *)a1 + 56LL))(
          a1,
          a4,
          a2,
          1,
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
      McTemplateU0zq_EventWriteTransfer(v14, Operational_CommitFileSharingFailed, v15, v10);
      v6 = 1;
    }
    if ( (v6 & 1) != 0 )
      LocalFree(hMem[0]);
  }
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17, v12);
  AdvancedSettingsTelemetry::CommitFileSharing::~CommitFileSharing((AdvancedSettingsTelemetry::CommitFileSharing *)v17);
}

```

## disassembly

```asm
0x180014f30  mov     [rsp+arg_10], rbx
0x180014f35  push    rbp
0x180014f36  push    rsi
0x180014f37  push    rdi
0x180014f38  push    r14
0x180014f3a  push    r15
0x180014f3c  sub     rsp, 1A0h
0x180014f43  mov     rax, cs:__security_cookie
0x180014f4a  xor     rax, rsp
0x180014f4d  mov     [rsp+1C8h+var_38], rax
0x180014f55  mov     edi, edx
0x180014f57  mov     rsi, rcx
0x180014f5a  xor     r14d, r14d
0x180014f5d  lea     rdx, aCommitfileshar; "CommitFileSharing"
0x180014f64  lea     rcx, [rsp+1C8h+var_188]
0x180014f69  mov     dword ptr [rsp+1C8h+hMem], r14d
0x180014f6e  mov     rbp, r9
0x180014f71  mov     rbx, r8
0x180014f74  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014f79  lea     rax, ??_7CommitFileSharing@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitFileSharing::`vftable'
0x180014f80  lea     rcx, [rsp+1C8h+var_188]; this
0x180014f85  mov     [rsp+1C8h+var_188], rax
0x180014f8a  call    ?StartActivity@CommitFileSharing@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::CommitFileSharing::StartActivity(void)
0x180014f8f  mov     r8d, [rbx+4]
0x180014f93  lea     rcx, qword_18001EBC0
0x180014f9a  call    _ValueFromButton_enum__DtshState_
0x180014f9f  xor     r15d, r15d
0x180014fa2  lea     r9d, [r14+1]
0x180014fa6  cmp     eax, 1
0x180014fa9  mov     r8d, edi
0x180014fac  mov     rax, [rsi]
0x180014faf  mov     rdx, rbp
0x180014fb2  setz    r15b
0x180014fb6  mov     rcx, rsi
0x180014fb9  mov     [rsp+1C8h+var_1A8], r15d
0x180014fbe  mov     rax, [rax+38h]
0x180014fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fc7  mov     ebx, eax
0x180014fc9  test    eax, eax
0x180014fcb  jns     short loc_180015016
0x180014fcd  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 1
0x180014fd4  jz      short loc_180015005
0x180014fd6  mov     edx, eax; dwMessageId
0x180014fd8  lea     rcx, [rsp+1C8h+hMem]; lpBuffer
0x180014fdd  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180014fe2  lea     r8, asc_18001ECC8; "???"
0x180014fe9  mov     r9d, r15d
0x180014fec  lea     rdx, Operational_CommitFileSharingFailed
0x180014ff3  cmp     [rax], r14
0x180014ff6  cmovnz  r8, [rax]
0x180014ffa  call    McTemplateU0zq_EventWriteTransfer
0x180014fff  mov     r14d, 1
0x180015005  test    r14b, 1
0x180015009  jz      short loc_180015016
0x18001500b  mov     rcx, [rsp+1C8h+hMem]; hMem
0x180015010  call    cs:__imp_LocalFree
0x180015016  mov     edx, ebx
0x180015018  lea     rcx, [rsp+1C8h+var_188]
0x18001501d  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180015022  lea     rcx, [rsp+1C8h+var_188]; this
0x180015027  call    ??1CommitFileSharing@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::CommitFileSharing::~CommitFileSharing(void)
0x18001502c  mov     rcx, [rsp+1C8h+var_38]
0x180015034  xor     rcx, rsp; StackCookie
0x180015037  call    __security_check_cookie
0x18001503c  mov     rbx, [rsp+1C8h+arg_10]
0x180015044  add     rsp, 1A0h
0x18001504b  pop     r15
0x18001504d  pop     r14
0x18001504f  pop     rdi
0x180015050  pop     rsi
0x180015051  pop     rbp
0x180015052  retn
```
