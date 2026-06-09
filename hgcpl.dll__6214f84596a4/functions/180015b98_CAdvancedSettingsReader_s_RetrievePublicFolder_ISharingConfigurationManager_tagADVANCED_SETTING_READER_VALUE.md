# CAdvancedSettingsReader::_s_RetrievePublicFolder(ISharingConfigurationManager *,tagADVANCED_SETTING_READER_VALUE *)

- ea: `0x180015b98`
- end: `0x180015d02`
- name: `?_s_RetrievePublicFolder@CAdvancedSettingsReader@@CAXPEAUISharingConfigurationManager@@PEAUtagADVANCED_SETTING_READER_VALUE@@@Z`
- size: `362`
- prototype: `void __fastcall(struct ISharingConfigurationManager *, struct tagADVANCED_SETTING_READER_VALUE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013368`

## callees

- `0x180006dfc`
- `0x180008fd0`
- `0x180012dd0`
- `0x180013c24`
- `0x180015b98`
- `0x180015db8`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015c4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015c4f`

## pseudocode

```c
void __fastcall CAdvancedSettingsReader::_s_RetrievePublicFolder(
        struct ISharingConfigurationManager *a1,
        struct tagADVANCED_SETTING_READER_VALUE *a2)
{
  char v4; // di
  struct ISharingConfigurationManagerVtbl *lpVtbl; // rax
  signed int v6; // eax
  unsigned int v7; // ebx
  const wchar_t **v8; // rax
  __int64 v9; // rcx
  const wchar_t *v10; // r8
  int v11; // r8d
  unsigned int v12; // r9d
  unsigned int i; // edx
  __int64 v14; // rax
  unsigned int v15; // r9d
  unsigned int v16; // edx
  int v17; // [rsp+20h] [rbp-178h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-170h] BYREF
  _QWORD v19[42]; // [rsp+30h] [rbp-168h] BYREF

  v4 = 0;
  v17 = 0;
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "RetrievePublicFolderPermissions");
  v19[0] = &AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::`vftable';
  AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::StartActivity((AdvancedSettingsTelemetry::RetrievePublicFolderPermissions *)v19);
  lpVtbl = a1->lpVtbl;
  v17 = 0;
  v6 = ((__int64 (__fastcall *)(struct ISharingConfigurationManager *, __int64, int *))lpVtbl->GetSharePermissions)(
         a1,
         2,
         &v17);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v11 = v17;
  }
  else
  {
    if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 1) != 0 )
    {
      v8 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v6);
      v10 = L"???";
      if ( *v8 )
        v10 = *v8;
      McTemplateU0z_EventWriteTransfer(v9, Operational_RetrievePublicFolderFailed, v10);
      v4 = 1;
    }
    if ( (v4 & 1) != 0 )
      LocalFree(hMem);
    v11 = -1;
    v17 = -1;
  }
  v12 = 0;
  for ( i = 1; i < 3; ++i )
  {
    if ( *((_DWORD *)qword_18001EC50 + 3 * i) == v11 )
    {
      v12 = i;
      break;
    }
  }
  v14 = v12;
  v15 = 0;
  v16 = 1;
  *(_DWORD *)a2 = *((_DWORD *)&qword_18001EC50[1] + 3 * v14);
  while ( v16 < 3 )
  {
    if ( *((_DWORD *)qword_18001EC50 + 3 * v16) == v11 )
    {
      v15 = v16;
      break;
    }
    ++v16;
  }
  *((_DWORD *)a2 + 1) = *((_DWORD *)qword_18001EC50 + 3 * v15 + 1);
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19, v7);
  AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::~RetrievePublicFolderPermissions((AdvancedSettingsTelemetry::RetrievePublicFolderPermissions *)v19);
}

```

## disassembly

```asm
0x180015b98  mov     [rsp+arg_10], rbx
0x180015b9d  mov     [rsp+arg_18], rsi
0x180015ba2  push    rdi
0x180015ba3  sub     rsp, 190h
0x180015baa  mov     rax, cs:__security_cookie
0x180015bb1  xor     rax, rsp
0x180015bb4  mov     [rsp+198h+var_18], rax
0x180015bbc  mov     rsi, rdx
0x180015bbf  mov     rbx, rcx
0x180015bc2  xor     edi, edi
0x180015bc4  lea     rdx, aRetrievepublic; "RetrievePublicFolderPermissions"
0x180015bcb  lea     rcx, [rsp+198h+var_168]
0x180015bd0  mov     [rsp+198h+var_178], edi
0x180015bd4  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015bd9  lea     rax, ??_7RetrievePublicFolderPermissions@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::`vftable'
0x180015be0  lea     rcx, [rsp+198h+var_168]; this
0x180015be5  mov     [rsp+198h+var_168], rax
0x180015bea  call    ?StartActivity@RetrievePublicFolderPermissions@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::StartActivity(void)
0x180015bef  mov     rax, [rbx]
0x180015bf2  lea     r8, [rsp+198h+var_178]
0x180015bf7  lea     edx, [rdi+2]
0x180015bfa  mov     [rsp+198h+var_178], edi
0x180015bfe  mov     rcx, rbx
0x180015c01  mov     rax, [rax+30h]
0x180015c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c0a  mov     ebx, eax
0x180015c0c  test    eax, eax
0x180015c0e  jns     short loc_180015C60
0x180015c10  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 1
0x180015c17  jz      short loc_180015C44
0x180015c19  mov     edx, eax; dwMessageId
0x180015c1b  lea     rcx, [rsp+198h+hMem]; lpBuffer
0x180015c20  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180015c25  lea     r8, asc_18001ECC8; "???"
0x180015c2c  lea     rdx, Operational_RetrievePublicFolderFailed
0x180015c33  cmp     [rax], rdi
0x180015c36  cmovnz  r8, [rax]
0x180015c3a  call    McTemplateU0z_EventWriteTransfer
0x180015c3f  mov     edi, 1
0x180015c44  test    dil, 1
0x180015c48  jz      short loc_180015C55
0x180015c4a  mov     rcx, [rsp+198h+hMem]; hMem
0x180015c4f  call    cs:__imp_LocalFree
0x180015c55  or      r8d, 0FFFFFFFFh
0x180015c59  mov     [rsp+198h+var_178], r8d
0x180015c5e  jmp     short loc_180015C65
0x180015c60  mov     r8d, [rsp+198h+var_178]
0x180015c65  xor     r9d, r9d
0x180015c68  lea     r10, qword_18001EC50
0x180015c6f  lea     edx, [r9+1]
0x180015c73  cmp     edx, 3
0x180015c76  jnb     short loc_180015C8B
0x180015c78  mov     eax, edx
0x180015c7a  lea     rcx, [rax+rax*2]
0x180015c7e  cmp     [r10+rcx*4], r8d
0x180015c82  jz      short loc_180015C88
0x180015c84  inc     edx
0x180015c86  jmp     short loc_180015C73
0x180015c88  mov     r9d, edx
0x180015c8b  mov     eax, r9d
0x180015c8e  xor     r9d, r9d
0x180015c91  lea     rax, [rax+rax*2]
0x180015c95  mov     eax, [r10+rax*4+8]
0x180015c9a  lea     edx, [r9+1]
0x180015c9e  mov     [rsi], eax
0x180015ca0  cmp     edx, 3
0x180015ca3  jnb     short loc_180015CB8
0x180015ca5  mov     eax, edx
0x180015ca7  lea     rcx, [rax+rax*2]
0x180015cab  cmp     [r10+rcx*4], r8d
0x180015caf  jz      short loc_180015CB5
0x180015cb1  inc     edx
0x180015cb3  jmp     short loc_180015CA0
0x180015cb5  mov     r9d, edx
0x180015cb8  mov     eax, r9d
0x180015cbb  lea     rcx, [rsp+198h+var_168]
0x180015cc0  mov     edx, ebx
0x180015cc2  lea     rax, [rax+rax*2]
0x180015cc6  mov     eax, [r10+rax*4+4]
0x180015ccb  mov     [rsi+4], eax
0x180015cce  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180015cd3  lea     rcx, [rsp+198h+var_168]; this
0x180015cd8  call    ??1RetrievePublicFolderPermissions@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::~RetrievePublicFolderPermissions(void)
0x180015cdd  mov     rcx, [rsp+198h+var_18]
0x180015ce5  xor     rcx, rsp; StackCookie
0x180015ce8  call    __security_check_cookie
0x180015ced  lea     r11, [rsp+198h+var_8]
0x180015cf5  mov     rbx, [r11+20h]
0x180015cf9  mov     rsi, [r11+28h]
0x180015cfd  mov     rsp, r11
0x180015d00  pop     rdi
0x180015d01  retn
```
