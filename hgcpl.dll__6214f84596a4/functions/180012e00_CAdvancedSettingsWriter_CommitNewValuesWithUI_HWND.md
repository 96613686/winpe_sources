# CAdvancedSettingsWriter::CommitNewValuesWithUI(HWND__ *)

- ea: `0x180012e00`
- end: `0x180012fd8`
- name: `?CommitNewValuesWithUI@CAdvancedSettingsWriter@@UEAAJPEAUHWND__@@@Z`
- size: `472`
- prototype: `int(CAdvancedSettingsWriter *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012e00`
- `0x180014f30`
- `0x1800151fc`
- `0x18001566c`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012ede`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012ede`
- `USER32!SetProcessDPIAware` at `0x180012e1a`
- `USER32!SetProcessDPIAware` at `0x180012e1a`

## pseudocode

```c
__int64 __fastcall CAdvancedSettingsWriter::CommitNewValuesWithUI(CAdvancedSettingsWriter *this, HWND a2)
{
  char *v4; // r13
  bool IsSettingChanged; // r12
  bool v6; // si
  bool v7; // bp
  bool v8; // r14
  bool v9; // r15
  bool v10; // al
  bool v11; // bl
  struct ADVANCED_SETTING_WRITER_VALUE *v13; // [rsp+30h] [rbp-48h]
  struct ADVANCED_SETTING_WRITER_VALUE *v14; // [rsp+38h] [rbp-40h]
  struct IDetectionAndSharing *ppv; // [rsp+80h] [rbp+8h] BYREF
  struct ADVANCED_SETTING_WRITER_VALUE *v16; // [rsp+90h] [rbp+18h]
  struct ADVANCED_SETTING_WRITER_VALUE *v17; // [rsp+98h] [rbp+20h]

  SetProcessDPIAware();
  v4 = (char *)this + 24;
  IsSettingChanged = CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 24));
  v6 = CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 32));
  v16 = (CAdvancedSettingsWriter *)((char *)this + 40);
  v7 = CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 40));
  v17 = (CAdvancedSettingsWriter *)((char *)this + 48);
  v8 = CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 48));
  v13 = (CAdvancedSettingsWriter *)((char *)this + 56);
  v9 = CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 56));
  v14 = (CAdvancedSettingsWriter *)((char *)this + 64);
  v10 = CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 64));
  v11 = v10;
  if ( IsSettingChanged || v6 || v7 || v8 || v9 || v10 )
  {
    ppv = 0;
    if ( CoCreateInstance(
           &GUID_1fda955b_61ff_11da_978c_0008744faab7,
           0,
           1u,
           &GUID_1fda955c_61ff_11da_978c_0008744faab7,
           (LPVOID *)&ppv) >= 0 )
    {
      if ( IsSettingChanged )
        CAdvancedSettingsWriter::_s_CommitNetworkDiscoveryForProfile(
          ppv,
          NET_FW_PROFILE2_PRIVATE,
          (const struct ADVANCED_SETTING_WRITER_VALUE *)v4,
          a2);
      if ( v6 )
        CAdvancedSettingsWriter::_s_CommitNetworkDiscoveryForProfile(
          ppv,
          NET_FW_PROFILE2_PUBLIC,
          (const struct ADVANCED_SETTING_WRITER_VALUE *)(v4 + 8),
          a2);
      if ( v7 )
        CAdvancedSettingsWriter::_s_CommitNetworkDiscoveryForProfile(ppv, NET_FW_PROFILE2_DOMAIN, v16, a2);
      if ( v8 )
        CAdvancedSettingsWriter::_s_CommitFileSharingForProfile(ppv, NET_FW_PROFILE2_PRIVATE, v17, a2);
      if ( v9 )
        CAdvancedSettingsWriter::_s_CommitFileSharingForProfile(ppv, NET_FW_PROFILE2_PUBLIC, v13, a2);
      if ( v11 )
        CAdvancedSettingsWriter::_s_CommitFileSharingForProfile(ppv, NET_FW_PROFILE2_DOMAIN, v14, a2);
      (*(void (__fastcall **)(struct IDetectionAndSharing *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012e00  mov     [rsp+arg_8], rbx
0x180012e05  push    rbp
0x180012e06  push    rsi
0x180012e07  push    rdi
0x180012e08  push    r12
0x180012e0a  push    r13
0x180012e0c  push    r14
0x180012e0e  push    r15
0x180012e10  sub     rsp, 40h
0x180012e14  mov     rdi, rdx
0x180012e17  mov     rbx, rcx
0x180012e1a  call    cs:__imp_SetProcessDPIAware
0x180012e20  lea     r13, [rbx+18h]
0x180012e24  mov     rcx, r13; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012e27  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180012e2c  lea     rcx, [r13+8]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012e30  mov     r12b, al
0x180012e33  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180012e38  mov     sil, al
0x180012e3b  lea     rax, [rbx+28h]
0x180012e3f  mov     rcx, rax; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012e42  mov     [rsp+78h+arg_10], rax
0x180012e4a  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180012e4f  mov     bpl, al
0x180012e52  lea     rax, [rbx+30h]
0x180012e56  mov     rcx, rax; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012e59  mov     [rsp+78h+arg_18], rax
0x180012e61  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180012e66  mov     r14b, al
0x180012e69  lea     rax, [rbx+38h]
0x180012e6d  mov     rcx, rax; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012e70  mov     [rsp+78h+var_48], rax
0x180012e75  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180012e7a  mov     r15b, al
0x180012e7d  lea     rax, [rbx+40h]
0x180012e81  mov     rcx, rax; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012e84  mov     [rsp+78h+var_40], rax
0x180012e89  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180012e8e  mov     bl, al
0x180012e90  test    r12b, r12b
0x180012e93  jnz     short loc_180012EB1
0x180012e95  test    sil, sil
0x180012e98  jnz     short loc_180012EB1
0x180012e9a  test    bpl, bpl
0x180012e9d  jnz     short loc_180012EB1
0x180012e9f  test    r14b, r14b
0x180012ea2  jnz     short loc_180012EB1
0x180012ea4  test    r15b, r15b
0x180012ea7  jnz     short loc_180012EB1
0x180012ea9  test    al, al
0x180012eab  jz      loc_180012FBE
0x180012eb1  xor     edx, edx; pUnkOuter
0x180012eb3  mov     [rsp+78h+arg_0], 0
0x180012ebf  lea     rax, [rsp+78h+arg_0]
0x180012ec7  lea     r9, _GUID_1fda955c_61ff_11da_978c_0008744faab7; riid
0x180012ece  mov     [rsp+78h+ppv], rax; ppv
0x180012ed3  lea     rcx, _GUID_1fda955b_61ff_11da_978c_0008744faab7; rclsid
0x180012eda  lea     r8d, [rdx+1]; dwClsContext
0x180012ede  call    cs:__imp_CoCreateInstance
0x180012ee4  test    eax, eax
0x180012ee6  js      loc_180012FBE
0x180012eec  test    r12b, r12b
0x180012eef  jz      short loc_180012F09
0x180012ef1  mov     rcx, [rsp+78h+arg_0]; struct IDetectionAndSharing *
0x180012ef9  mov     r9, rdi; HWND
0x180012efc  mov     r8, r13; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012eff  mov     edx, 2; enum NET_FW_PROFILE_TYPE2_
0x180012f04  call    ?_s_CommitNetworkDiscoveryForProfile@CAdvancedSettingsWriter@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@AEBUADVANCED_SETTING_WRITER_VALUE@@PEAUHWND__@@@Z; CAdvancedSettingsWriter::_s_CommitNetworkDiscoveryForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,ADVANCED_SETTING_WRITER_VALUE const &,HWND__ *)
0x180012f09  mov     r12d, 4
0x180012f0f  test    sil, sil
0x180012f12  jz      short loc_180012F2B
0x180012f14  mov     rcx, [rsp+78h+arg_0]; struct IDetectionAndSharing *
0x180012f1c  lea     r8, [r13+8]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012f20  mov     r9, rdi; HWND
0x180012f23  mov     edx, r12d; enum NET_FW_PROFILE_TYPE2_
0x180012f26  call    ?_s_CommitNetworkDiscoveryForProfile@CAdvancedSettingsWriter@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@AEBUADVANCED_SETTING_WRITER_VALUE@@PEAUHWND__@@@Z; CAdvancedSettingsWriter::_s_CommitNetworkDiscoveryForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,ADVANCED_SETTING_WRITER_VALUE const &,HWND__ *)
0x180012f2b  test    bpl, bpl
0x180012f2e  jz      short loc_180012F4D
0x180012f30  mov     r8, [rsp+78h+arg_10]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012f38  mov     r9, rdi; HWND
0x180012f3b  mov     rcx, [rsp+78h+arg_0]; struct IDetectionAndSharing *
0x180012f43  mov     edx, 1; enum NET_FW_PROFILE_TYPE2_
0x180012f48  call    ?_s_CommitNetworkDiscoveryForProfile@CAdvancedSettingsWriter@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@AEBUADVANCED_SETTING_WRITER_VALUE@@PEAUHWND__@@@Z; CAdvancedSettingsWriter::_s_CommitNetworkDiscoveryForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,ADVANCED_SETTING_WRITER_VALUE const &,HWND__ *)
0x180012f4d  test    r14b, r14b
0x180012f50  jz      short loc_180012F6F
0x180012f52  mov     r8, [rsp+78h+arg_18]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012f5a  mov     r9, rdi; HWND
0x180012f5d  mov     rcx, [rsp+78h+arg_0]; struct IDetectionAndSharing *
0x180012f65  mov     edx, 2; enum NET_FW_PROFILE_TYPE2_
0x180012f6a  call    ?_s_CommitFileSharingForProfile@CAdvancedSettingsWriter@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@AEBUADVANCED_SETTING_WRITER_VALUE@@PEAUHWND__@@@Z; CAdvancedSettingsWriter::_s_CommitFileSharingForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,ADVANCED_SETTING_WRITER_VALUE const &,HWND__ *)
0x180012f6f  test    r15b, r15b
0x180012f72  jz      short loc_180012F8C
0x180012f74  mov     r8, [rsp+78h+var_48]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012f79  mov     r9, rdi; HWND
0x180012f7c  mov     rcx, [rsp+78h+arg_0]; struct IDetectionAndSharing *
0x180012f84  mov     edx, r12d; enum NET_FW_PROFILE_TYPE2_
0x180012f87  call    ?_s_CommitFileSharingForProfile@CAdvancedSettingsWriter@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@AEBUADVANCED_SETTING_WRITER_VALUE@@PEAUHWND__@@@Z; CAdvancedSettingsWriter::_s_CommitFileSharingForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,ADVANCED_SETTING_WRITER_VALUE const &,HWND__ *)
0x180012f8c  test    bl, bl
0x180012f8e  jz      short loc_180012FAA
0x180012f90  mov     r8, [rsp+78h+var_40]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012f95  mov     r9, rdi; HWND
0x180012f98  mov     rcx, [rsp+78h+arg_0]; struct IDetectionAndSharing *
0x180012fa0  mov     edx, 1; enum NET_FW_PROFILE_TYPE2_
0x180012fa5  call    ?_s_CommitFileSharingForProfile@CAdvancedSettingsWriter@@CAXPEAUIDetectionAndSharing@@W4NET_FW_PROFILE_TYPE2_@@AEBUADVANCED_SETTING_WRITER_VALUE@@PEAUHWND__@@@Z; CAdvancedSettingsWriter::_s_CommitFileSharingForProfile(IDetectionAndSharing *,NET_FW_PROFILE_TYPE2_,ADVANCED_SETTING_WRITER_VALUE const &,HWND__ *)
0x180012faa  mov     rcx, [rsp+78h+arg_0]
0x180012fb2  mov     rax, [rcx]
0x180012fb5  mov     rax, [rax+10h]
0x180012fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fbe  mov     rbx, [rsp+78h+arg_8]
0x180012fc6  xor     eax, eax
0x180012fc8  add     rsp, 40h
0x180012fcc  pop     r15
0x180012fce  pop     r14
0x180012fd0  pop     r13
0x180012fd2  pop     r12
0x180012fd4  pop     rdi
0x180012fd5  pop     rsi
0x180012fd6  pop     rbp
0x180012fd7  retn
```
