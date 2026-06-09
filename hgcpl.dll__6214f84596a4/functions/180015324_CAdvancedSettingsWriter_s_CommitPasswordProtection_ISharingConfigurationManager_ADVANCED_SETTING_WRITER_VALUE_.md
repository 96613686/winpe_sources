# CAdvancedSettingsWriter::_s_CommitPasswordProtection(ISharingConfigurationManager *,ADVANCED_SETTING_WRITER_VALUE const &)

- ea: `0x180015324`
- end: `0x1800154df`
- name: `?_s_CommitPasswordProtection@CAdvancedSettingsWriter@@CAXPEAUISharingConfigurationManager@@AEBUADVANCED_SETTING_WRITER_VALUE@@@Z`
- size: `443`
- prototype: `void __fastcall(struct ISharingConfigurationManager *, const struct ADVANCED_SETTING_WRITER_VALUE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012fe0`

## callees

- `0x180006dfc`
- `0x180008fd0`
- `0x180012cf4`
- `0x180013864`
- `0x180015324`
- `0x180015e38`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800154a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800154a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800153e0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800153e0`

## string_xrefs

- `0x180015397`: `CommitPasswordProtection`

## pseudocode

```c
void __fastcall CAdvancedSettingsWriter::_s_CommitPasswordProtection(
        struct ISharingConfigurationManager *a1,
        const struct ADVANCED_SETTING_WRITER_VALUE *a2)
{
  unsigned int v2; // ebx
  unsigned int v4; // r9d
  unsigned int i; // r8d
  int v6; // esi
  HRESULT v7; // edi
  __int64 v8; // rax
  HRESULT v9; // eax
  const wchar_t **v10; // rax
  __int64 v11; // rcx
  const wchar_t *v12; // r8
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v15[42]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = 0;
  LODWORD(ppv) = 0;
  v4 = 0;
  for ( i = 1; i < 3; ++i )
  {
    if ( *((_DWORD *)qword_18001EB90 + 3 * i + 1) == *((_DWORD *)a2 + 1) )
    {
      v4 = i;
      break;
    }
  }
  v6 = *((_DWORD *)qword_18001EB90 + 3 * v4);
  if ( v6 )
  {
    wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v15,
      "CommitPasswordProtection");
    v15[0] = &AdvancedSettingsTelemetry::CommitPasswordProtection::`vftable';
    AdvancedSettingsTelemetry::CommitPasswordProtection::StartActivity((AdvancedSettingsTelemetry::CommitPasswordProtection *)v15);
    ppv = 0;
    v7 = CoCreateInstance(&CLSID_ShellLocalMachine, 0, 1u, &GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461, &ppv);
    if ( v7 < 0
      || ((v8 = *(_QWORD *)ppv, v6 != 1)
        ? (v9 = (*(__int64 (__fastcall **)(LPVOID, __int64))(v8 + 128))(ppv, 2))
        : (v9 = (*(__int64 (__fastcall **)(LPVOID, __int64))(v8 + 136))(ppv, 2)),
          (v7 = v9, (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv), v7 < 0)
       || !((unsigned int (__fastcall *)(struct ISharingConfigurationManager *, __int64))a1->lpVtbl->ShareExists)(a1, 1)
       && (v7 = ((__int64 (__fastcall *)(struct ISharingConfigurationManager *, __int64, __int64))a1->lpVtbl->CreateShare)(
                  a1,
                  1,
                  2),
           v7 < 0)) )
    {
      if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 1) != 0 )
      {
        v10 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v7);
        v12 = L"???";
        if ( *v10 )
          v12 = *v10;
        LOBYTE(v2) = v6 == 1;
        McTemplateU0zq_EventWriteTransfer(v11, Operational_CommitPasswordProtectionFailed, v12, v2);
        LOBYTE(v2) = 1;
      }
      if ( (v2 & 1) != 0 )
        LocalFree(hMem);
    }
    wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v15,
      (unsigned int)v7);
    AdvancedSettingsTelemetry::CommitPasswordProtection::~CommitPasswordProtection((AdvancedSettingsTelemetry::CommitPasswordProtection *)v15);
  }
}

```

## disassembly

```asm
0x180015324  push    rbp
0x180015326  push    rbx
0x180015327  push    rsi
0x180015328  push    rdi
0x180015329  push    r14
0x18001532b  push    r15
0x18001532d  lea     rbp, [rsp-0A8h]
0x180015335  sub     rsp, 1A8h
0x18001533c  mov     rax, cs:__security_cookie
0x180015343  xor     rax, rsp
0x180015346  mov     [rbp+0D0h+var_40], rax
0x18001534d  xor     ebx, ebx
0x18001534f  lea     rsi, qword_18001EB90
0x180015356  mov     r14, rcx
0x180015359  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18001535d  xor     r9d, r9d
0x180015360  lea     r15d, [rbx+1]
0x180015364  mov     r8d, r15d
0x180015367  cmp     r8d, 3
0x18001536b  jnb     short loc_180015385
0x18001536d  mov     eax, r8d
0x180015370  lea     rcx, [rax+rax*2]
0x180015374  mov     eax, [rdx+4]
0x180015377  cmp     [rsi+rcx*4+4], eax
0x18001537b  jz      short loc_180015382
0x18001537d  add     r8d, r15d
0x180015380  jmp     short loc_180015367
0x180015382  mov     r9d, r8d
0x180015385  mov     eax, r9d
0x180015388  lea     rcx, [rax+rax*2]
0x18001538c  mov     esi, [rsi+rcx*4]
0x18001538f  test    esi, esi
0x180015391  jz      loc_1800154C0
0x180015397  lea     rdx, aCommitpassword; "CommitPasswordProtection"
0x18001539e  lea     rcx, [rsp+1D0h+var_190]
0x1800153a3  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800153a8  lea     rax, ??_7CommitPasswordProtection@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitPasswordProtection::`vftable'
0x1800153af  lea     rcx, [rsp+1D0h+var_190]; this
0x1800153b4  mov     [rsp+1D0h+var_190], rax
0x1800153b9  call    ?StartActivity@CommitPasswordProtection@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::CommitPasswordProtection::StartActivity(void)
0x1800153be  lea     rax, [rsp+1D0h+var_1A0]
0x1800153c3  mov     [rsp+1D0h+var_1A0], rbx
0x1800153c8  lea     r9, _GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461; riid
0x1800153cf  mov     [rsp+1D0h+ppv], rax; ppv
0x1800153d4  mov     r8d, r15d; dwClsContext
0x1800153d7  lea     rcx, CLSID_ShellLocalMachine; rclsid
0x1800153de  xor     edx, edx; pUnkOuter
0x1800153e0  call    cs:__imp_CoCreateInstance
0x1800153e6  mov     edi, eax
0x1800153e8  test    eax, eax
0x1800153ea  js      short loc_18001545E
0x1800153ec  mov     rcx, [rsp+1D0h+var_1A0]
0x1800153f1  mov     edx, 2
0x1800153f6  mov     rax, [rcx]
0x1800153f9  cmp     esi, r15d
0x1800153fc  jnz     short loc_180015407
0x1800153fe  mov     rax, [rax+88h]
0x180015405  jmp     short loc_18001540E
0x180015407  mov     rax, [rax+80h]
0x18001540e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015413  mov     rcx, [rsp+1D0h+var_1A0]
0x180015418  mov     edi, eax
0x18001541a  mov     rax, [rcx]
0x18001541d  mov     rax, [rax+10h]
0x180015421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015426  test    edi, edi
0x180015428  js      short loc_18001545E
0x18001542a  mov     rax, [r14]
0x18001542d  mov     edx, r15d
0x180015430  mov     rcx, r14
0x180015433  mov     rax, [rax+28h]
0x180015437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001543c  test    eax, eax
0x18001543e  jnz     short loc_1800154AA
0x180015440  mov     rax, [r14]
0x180015443  mov     r8d, 2
0x180015449  mov     edx, r15d
0x18001544c  mov     rcx, r14
0x18001544f  mov     rax, [rax+18h]
0x180015453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015458  mov     edi, eax
0x18001545a  test    eax, eax
0x18001545c  jns     short loc_1800154AA
0x18001545e  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, r15b
0x180015465  jz      short loc_18001549A
0x180015467  cmp     esi, r15d
0x18001546a  lea     rcx, [rsp+1D0h+hMem]; lpBuffer
0x18001546f  mov     edx, edi; dwMessageId
0x180015471  setz    bl
0x180015474  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180015479  lea     r8, asc_18001ECC8; "???"
0x180015480  mov     r9d, ebx
0x180015483  lea     rdx, Operational_CommitPasswordProtectionFailed
0x18001548a  cmp     qword ptr [rax], 0
0x18001548e  cmovnz  r8, [rax]
0x180015492  call    McTemplateU0zq_EventWriteTransfer
0x180015497  mov     ebx, r15d
0x18001549a  test    r15b, bl
0x18001549d  jz      short loc_1800154AA
0x18001549f  mov     rcx, [rsp+1D0h+hMem]; hMem
0x1800154a4  call    cs:__imp_LocalFree
0x1800154aa  mov     edx, edi
0x1800154ac  lea     rcx, [rsp+1D0h+var_190]
0x1800154b1  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800154b6  lea     rcx, [rsp+1D0h+var_190]; this
0x1800154bb  call    ??1CommitPasswordProtection@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::CommitPasswordProtection::~CommitPasswordProtection(void)
0x1800154c0  mov     rcx, [rbp+0D0h+var_40]
0x1800154c7  xor     rcx, rsp; StackCookie
0x1800154ca  call    __security_check_cookie
0x1800154cf  add     rsp, 1A8h
0x1800154d6  pop     r15
0x1800154d8  pop     r14
0x1800154da  pop     rdi
0x1800154db  pop     rsi
0x1800154dc  pop     rbx
0x1800154dd  pop     rbp
0x1800154de  retn
```
