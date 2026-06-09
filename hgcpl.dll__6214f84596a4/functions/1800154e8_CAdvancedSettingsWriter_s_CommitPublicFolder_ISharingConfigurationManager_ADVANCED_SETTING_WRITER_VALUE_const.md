# CAdvancedSettingsWriter::_s_CommitPublicFolder(ISharingConfigurationManager *,ADVANCED_SETTING_WRITER_VALUE const &)

- ea: `0x1800154e8`
- end: `0x180015665`
- name: `?_s_CommitPublicFolder@CAdvancedSettingsWriter@@CAXPEAUISharingConfigurationManager@@AEBUADVANCED_SETTING_WRITER_VALUE@@@Z`
- size: `381`
- prototype: `void __fastcall(struct ISharingConfigurationManager *, const struct ADVANCED_SETTING_WRITER_VALUE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012fe0`

## callees

- `0x180006dfc`
- `0x180008fd0`
- `0x180012d20`
- `0x180013924`
- `0x1800154e8`
- `0x180015e38`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001562d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001562d`

## string_xrefs

- `0x18001550e`: `CommitPublicFolder`

## pseudocode

```c
void __fastcall CAdvancedSettingsWriter::_s_CommitPublicFolder(
        struct ISharingConfigurationManager *a1,
        const struct ADVANCED_SETTING_WRITER_VALUE *a2)
{
  char v4; // si
  unsigned int v5; // r8d
  unsigned int i; // edx
  unsigned int v7; // ebp
  HRESULT (__stdcall *DeleteShare)(ISharingConfigurationManager *, DEF_SHARE_ID); // rax
  signed int v9; // eax
  unsigned int v10; // ebx
  const wchar_t **v11; // rax
  __int64 v12; // rcx
  const wchar_t *v13; // r8
  bool v14; // zf
  signed int v15; // eax
  const wchar_t **v16; // rax
  __int64 v17; // rcx
  const wchar_t *v18; // r8
  HLOCAL hMem[2]; // [rsp+20h] [rbp-198h] BYREF
  _QWORD v20[42]; // [rsp+30h] [rbp-188h] BYREF

  v4 = 0;
  LODWORD(hMem[0]) = 0;
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "CommitPublicFolder");
  v20[0] = &AdvancedSettingsTelemetry::CommitPublicFolder::`vftable';
  AdvancedSettingsTelemetry::CommitPublicFolder::StartActivity((AdvancedSettingsTelemetry::CommitPublicFolder *)v20);
  v5 = 0;
  for ( i = 1; i < 3; ++i )
  {
    if ( *((_DWORD *)qword_18001EC50 + 3 * i + 1) == *((_DWORD *)a2 + 1) )
    {
      v5 = i;
      break;
    }
  }
  v7 = *((_DWORD *)qword_18001EC50 + 3 * v5);
  DeleteShare = a1->lpVtbl->DeleteShare;
  if ( v7 == -1 )
  {
    v9 = ((__int64 (__fastcall *)(struct ISharingConfigurationManager *, __int64))DeleteShare)(a1, 2);
    v10 = v9;
    if ( v9 >= 0 )
      goto LABEL_21;
    if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 1) != 0 )
    {
      v11 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)hMem, v9);
      v13 = L"???";
      if ( *v11 )
        v13 = *v11;
      McTemplateU0zq_EventWriteTransfer(v12, Operational_CommitPublicFolderFailed, v13, 0xFFFFFFFFLL);
      v4 = 1;
    }
    v14 = (v4 & 1) == 0;
  }
  else
  {
    ((void (__fastcall *)(struct ISharingConfigurationManager *, __int64))DeleteShare)(a1, 2);
    v15 = ((__int64 (__fastcall *)(struct ISharingConfigurationManager *, __int64, _QWORD))a1->lpVtbl->CreateShare)(
            a1,
            2,
            v7);
    v10 = v15;
    if ( v15 >= 0 )
      goto LABEL_21;
    if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 1) != 0 )
    {
      v16 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)hMem, v15);
      v18 = L"???";
      if ( *v16 )
        v18 = *v16;
      McTemplateU0zq_EventWriteTransfer(v17, Operational_CommitPublicFolderFailed, v18, v7);
      v4 = 2;
    }
    v14 = (v4 & 2) == 0;
  }
  if ( !v14 )
    LocalFree(hMem[0]);
LABEL_21:
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20, v10);
  AdvancedSettingsTelemetry::CommitPublicFolder::~CommitPublicFolder((AdvancedSettingsTelemetry::CommitPublicFolder *)v20);
}

```

## disassembly

```asm
0x1800154e8  push    rbx
0x1800154ea  push    rbp
0x1800154eb  push    rsi
0x1800154ec  push    rdi
0x1800154ed  sub     rsp, 198h
0x1800154f4  mov     rax, cs:__security_cookie
0x1800154fb  xor     rax, rsp
0x1800154fe  mov     [rsp+1B8h+var_38], rax
0x180015506  mov     rdi, rdx
0x180015509  mov     rbx, rcx
0x18001550c  xor     esi, esi
0x18001550e  lea     rdx, aCommitpublicfo; "CommitPublicFolder"
0x180015515  lea     rcx, [rsp+1B8h+var_188]
0x18001551a  mov     dword ptr [rsp+1B8h+hMem], esi
0x18001551e  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015523  lea     rax, ??_7CommitPublicFolder@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitPublicFolder::`vftable'
0x18001552a  lea     rcx, [rsp+1B8h+var_188]; this
0x18001552f  mov     [rsp+1B8h+var_188], rax
0x180015534  call    ?StartActivity@CommitPublicFolder@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::CommitPublicFolder::StartActivity(void)
0x180015539  xor     r8d, r8d
0x18001553c  lea     edx, [rsi+1]
0x18001553f  lea     rbp, qword_18001EC50
0x180015546  cmp     edx, 3
0x180015549  jnb     short loc_180015561
0x18001554b  mov     eax, edx
0x18001554d  lea     rcx, [rax+rax*2]
0x180015551  mov     eax, [rdi+4]
0x180015554  cmp     [rbp+rcx*4+4], eax
0x180015558  jz      short loc_18001555E
0x18001555a  inc     edx
0x18001555c  jmp     short loc_180015546
0x18001555e  mov     r8d, edx
0x180015561  mov     eax, r8d
0x180015564  mov     rcx, rbx
0x180015567  lea     rdx, [rax+rax*2]
0x18001556b  mov     rax, [rbx]
0x18001556e  mov     ebp, [rbp+rdx*4+0]
0x180015572  mov     rax, [rax+20h]
0x180015576  cmp     ebp, 0FFFFFFFFh
0x180015579  jnz     short loc_1800155C9
0x18001557b  lea     edx, [rbp+3]
0x18001557e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015583  mov     ebx, eax
0x180015585  test    eax, eax
0x180015587  jns     loc_180015633
0x18001558d  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 1
0x180015594  jz      short loc_1800155C3
0x180015596  mov     edx, eax; dwMessageId
0x180015598  lea     rcx, [rsp+1B8h+hMem]; lpBuffer
0x18001559d  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x1800155a2  lea     r8, asc_18001ECC8; "???"
0x1800155a9  lea     rdx, Operational_CommitPublicFolderFailed
0x1800155b0  cmp     [rax], rsi
0x1800155b3  cmovnz  r8, [rax]
0x1800155b7  or      r9d, 0FFFFFFFFh
0x1800155bb  call    McTemplateU0zq_EventWriteTransfer
0x1800155c0  lea     esi, [rbp+2]
0x1800155c3  test    sil, 1
0x1800155c7  jmp     short loc_180015626
0x1800155c9  mov     edi, 2
0x1800155ce  mov     edx, edi
0x1800155d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155d5  mov     rax, [rbx]
0x1800155d8  mov     r8d, ebp
0x1800155db  mov     edx, edi
0x1800155dd  mov     rcx, rbx
0x1800155e0  mov     rax, [rax+18h]
0x1800155e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e9  mov     ebx, eax
0x1800155eb  test    eax, eax
0x1800155ed  jns     short loc_180015633
0x1800155ef  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 1
0x1800155f6  jz      short loc_180015623
0x1800155f8  mov     edx, eax; dwMessageId
0x1800155fa  lea     rcx, [rsp+1B8h+hMem]; lpBuffer
0x1800155ff  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180015604  lea     r8, asc_18001ECC8; "???"
0x18001560b  mov     r9d, ebp
0x18001560e  lea     rdx, Operational_CommitPublicFolderFailed
0x180015615  cmp     [rax], rsi
0x180015618  cmovnz  r8, [rax]
0x18001561c  call    McTemplateU0zq_EventWriteTransfer
0x180015621  mov     esi, edi
0x180015623  test    dil, sil
0x180015626  jz      short loc_180015633
0x180015628  mov     rcx, [rsp+1B8h+hMem]; hMem
0x18001562d  call    cs:__imp_LocalFree
0x180015633  mov     edx, ebx
0x180015635  lea     rcx, [rsp+1B8h+var_188]
0x18001563a  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001563f  lea     rcx, [rsp+1B8h+var_188]; this
0x180015644  call    ??1CommitPublicFolder@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::CommitPublicFolder::~CommitPublicFolder(void)
0x180015649  mov     rcx, [rsp+1B8h+var_38]
0x180015651  xor     rcx, rsp; StackCookie
0x180015654  call    __security_check_cookie
0x180015659  add     rsp, 198h
0x180015660  pop     rdi
0x180015661  pop     rsi
0x180015662  pop     rbp
0x180015663  pop     rbx
0x180015664  retn
```
