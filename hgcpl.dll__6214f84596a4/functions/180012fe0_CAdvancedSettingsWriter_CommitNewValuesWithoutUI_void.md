# CAdvancedSettingsWriter::CommitNewValuesWithoutUI(void)

- ea: `0x180012fe0`
- end: `0x1800130b5`
- name: `?CommitNewValuesWithoutUI@CAdvancedSettingsWriter@@UEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(CAdvancedSettingsWriter *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180012fe0`
- `0x18001505c`
- `0x18001510c`
- `0x180015324`
- `0x1800154e8`
- `0x18001566c`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001303c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001303c`

## pseudocode

```c
__int64 __fastcall CAdvancedSettingsWriter::CommitNewValuesWithoutUI(CAdvancedSettingsWriter *this)
{
  bool IsSettingChanged; // bp
  bool v3; // al
  bool v4; // bl
  const struct ADVANCED_SETTING_WRITER_VALUE *v5; // rcx
  __int64 v6; // rdx
  const struct ADVANCED_SETTING_WRITER_VALUE *v7; // rcx
  struct ISharingConfigurationManager *ppv; // [rsp+50h] [rbp+8h] BYREF

  IsSettingChanged = CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 80));
  v3 = CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 88));
  v4 = v3;
  if ( IsSettingChanged || v3 )
  {
    ppv = 0;
    if ( CoCreateInstance(
           &CLSID_SharingConfigurationManager,
           0,
           1u,
           &GUID_b4cd448a_9c86_4466_9201_2e62105b87ae,
           (LPVOID *)&ppv) >= 0 )
    {
      if ( v4 )
        CAdvancedSettingsWriter::_s_CommitPasswordProtection(ppv, (CAdvancedSettingsWriter *)((char *)this + 88));
      if ( IsSettingChanged )
        CAdvancedSettingsWriter::_s_CommitPublicFolder(ppv, (CAdvancedSettingsWriter *)((char *)this + 80));
      ((void (__fastcall *)(struct ISharingConfigurationManager *))ppv->lpVtbl->Release)(ppv);
    }
  }
  if ( CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 96)) )
    CAdvancedSettingsWriter::_s_CommitFileSharingMinEncryption(v5);
  if ( CAdvancedSettingsWriter::_s_IsSettingChanged((CAdvancedSettingsWriter *)((char *)this + 112)) )
    CAdvancedSettingsWriter::_s_CommitNcdAutoSetup(v7, v6);
  return 0;
}

```

## disassembly

```asm
0x180012fe0  mov     [rsp+arg_8], rbx
0x180012fe5  mov     [rsp+arg_10], rbp
0x180012fea  push    rsi
0x180012feb  push    rdi
0x180012fec  push    r14
0x180012fee  sub     rsp, 30h
0x180012ff2  mov     rsi, rcx
0x180012ff5  add     rcx, 50h ; 'P'; struct ADVANCED_SETTING_WRITER_VALUE *
0x180012ff9  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180012ffe  lea     rcx, [rsi+58h]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180013002  mov     bpl, al
0x180013005  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x18001300a  mov     bl, al
0x18001300c  test    bpl, bpl
0x18001300f  jnz     short loc_180013015
0x180013011  test    al, al
0x180013013  jz      short loc_18001307C
0x180013015  xor     edx, edx; pUnkOuter
0x180013017  mov     [rsp+48h+arg_0], 0
0x180013020  lea     rax, [rsp+48h+arg_0]
0x180013025  lea     r9, _GUID_b4cd448a_9c86_4466_9201_2e62105b87ae; riid
0x18001302c  mov     [rsp+48h+ppv], rax; ppv
0x180013031  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x180013038  lea     r8d, [rdx+1]; dwClsContext
0x18001303c  call    cs:__imp_CoCreateInstance
0x180013042  test    eax, eax
0x180013044  js      short loc_18001307C
0x180013046  test    bl, bl
0x180013048  jz      short loc_180013058
0x18001304a  mov     rcx, [rsp+48h+arg_0]; struct ISharingConfigurationManager *
0x18001304f  lea     rdx, [rsi+58h]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180013053  call    ?_s_CommitPasswordProtection@CAdvancedSettingsWriter@@CAXPEAUISharingConfigurationManager@@AEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_CommitPasswordProtection(ISharingConfigurationManager *,ADVANCED_SETTING_WRITER_VALUE const &)
0x180013058  test    bpl, bpl
0x18001305b  jz      short loc_18001306B
0x18001305d  mov     rcx, [rsp+48h+arg_0]; struct ISharingConfigurationManager *
0x180013062  lea     rdx, [rsi+50h]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180013066  call    ?_s_CommitPublicFolder@CAdvancedSettingsWriter@@CAXPEAUISharingConfigurationManager@@AEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_CommitPublicFolder(ISharingConfigurationManager *,ADVANCED_SETTING_WRITER_VALUE const &)
0x18001306b  mov     rcx, [rsp+48h+arg_0]
0x180013070  mov     rax, [rcx]
0x180013073  mov     rax, [rax+10h]
0x180013077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001307c  lea     rcx, [rsi+60h]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180013080  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180013085  test    al, al
0x180013087  jz      short loc_18001308E
0x180013089  call    ?_s_CommitFileSharingMinEncryption@CAdvancedSettingsWriter@@CAXAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_CommitFileSharingMinEncryption(ADVANCED_SETTING_WRITER_VALUE const &)
0x18001308e  lea     rcx, [rsi+70h]; struct ADVANCED_SETTING_WRITER_VALUE *
0x180013092  call    ?_s_IsSettingChanged@CAdvancedSettingsWriter@@CA_NAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_IsSettingChanged(ADVANCED_SETTING_WRITER_VALUE const &)
0x180013097  test    al, al
0x180013099  jz      short loc_1800130A0
0x18001309b  call    ?_s_CommitNcdAutoSetup@CAdvancedSettingsWriter@@CAXAEBUADVANCED_SETTING_WRITER_VALUE@@@Z; CAdvancedSettingsWriter::_s_CommitNcdAutoSetup(ADVANCED_SETTING_WRITER_VALUE const &)
0x1800130a0  mov     rbx, [rsp+48h+arg_8]
0x1800130a5  xor     eax, eax
0x1800130a7  mov     rbp, [rsp+48h+arg_10]
0x1800130ac  add     rsp, 30h
0x1800130b0  pop     r14
0x1800130b2  pop     rdi
0x1800130b3  pop     rsi
0x1800130b4  retn
```
