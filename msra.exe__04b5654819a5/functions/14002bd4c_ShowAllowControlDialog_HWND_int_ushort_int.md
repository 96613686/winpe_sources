# ShowAllowControlDialog(HWND__ *,int *,ushort *,int *)

- ea: `0x14002bd4c`
- end: `0x14002c09b`
- name: `?ShowAllowControlDialog@@YAJPEAUHWND__@@PEAHPEAG1@Z`
- size: `847`
- prototype: `__int64 __fastcall(HWND, int *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140025860`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x140028a2c`
- `0x14002aeec`
- `0x14002bd4c`
- `0x140034ce4`
- `0x140036efc`
- `0x140037168`
- `0x14004a784`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `USER32!LoadStringW` at `0x14002be6c`
- `USER32!LoadStringW` at `0x14002bec3`
- `USER32!LoadStringW` at `0x14002be6c`
- `USER32!LoadStringW` at `0x14002bec3`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002c01e`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002c01e`

## string_xrefs

- `0x14002c03f`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall ShowAllowControlDialog(HWND a1, int *a2, unsigned __int16 *a3, int *a4)
{
  int v8; // esi
  BOOL v9; // ebx
  int GroupPolicySetting; // eax
  const WCHAR *v11; // r15
  CEventLogger *v12; // rcx
  CEventLogger *v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // edi
  HRESULT v17; // eax
  CEventLogger *v18; // rcx
  unsigned int v19; // r9d
  int v20; // esi
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  int v24; // [rsp+38h] [rbp-C8h] BYREF
  BOOL pfVerificationFlagChecked; // [rsp+3Ch] [rbp-C4h] BYREF
  int pnRadioButton; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+54h] [rbp-ACh]
  int v30; // [rsp+5Ch] [rbp-A4h]
  __int64 v31; // [rsp+60h] [rbp-A0h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[1024]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR v34[1024]; // [rsp+910h] [rbp+810h] BYREF
  unsigned __int16 v35[1024]; // [rsp+1110h] [rbp+1010h] BYREF
  unsigned __int16 v36[1024]; // [rsp+1910h] [rbp+1810h] BYREF

  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  memset_0(v35, 0, sizeof(v35));
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v34, 0, sizeof(v34));
  memset_0(v36, 0, sizeof(v36));
  v28 = 6;
  v27 = 0;
  v24 = 0;
  v8 = 0;
  v22 = 0;
  v9 = 1;
  pfVerificationFlagChecked = 0;
  v23 = 1;
  pnRadioButton = 0;
  v29 = 546;
  v30 = 7;
  v31 = 548;
  GroupPolicySetting = CSettingsManager::GetGroupPolicySetting((char *)_AtlModule + 696, 0, &v27);
  v11 = v27;
  if ( GroupPolicySetting >= 0 )
    LOBYTE(v8) = v27 != 0;
  if ( !LoadStringW(*((HINSTANCE *)_AtlModule + 76), 0x255u, Buffer, 1024) )
  {
    CEventLogger::LogError(
      v12,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x9F6u,
      L"ShowAllowControlDialog",
      0);
LABEL_21:
    *a2 = 7;
    return 0;
  }
  StringCchPrintfW(v35, 0x400u, Buffer, a3);
  if ( !LoadStringW(*((HINSTANCE *)_AtlModule + 76), 0x294u, v34, 1024) )
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0xA01u,
      L"ShowAllowControlDialog",
      0);
    goto LABEL_21;
  }
  StringCchPrintfW(v36, 0x400u, v34, a3);
  v15 = LUAPromptOnSecureDesktop(v14, &v22);
  v16 = v22;
  if ( v15 < 0 )
    v16 = 0;
  v17 = PromptToDisableUAC(&v24);
  if ( v17 < 0 )
  {
    v19 = 2574;
LABEL_20:
    CEventLogger::LogError(
      v18,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v19,
      L"ShowAllowControlDialog",
      v17);
    goto LABEL_21;
  }
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = a1;
  pTaskConfig.hInstance = (HINSTANCE)*((_QWORD *)_AtlModule + 76);
  pTaskConfig.pszMainInstruction = v35;
  *(_QWORD *)&pTaskConfig.dwFlags = 2057;
  pTaskConfig.pszWindowTitle = (PCWSTR)100;
  pTaskConfig.hMainIcon = 0;
  if ( v8 == 1 )
  {
    pTaskConfig.pszContent = v11;
  }
  else
  {
    CSettingsManager::GetSettingFromRegistry((char *)_AtlModule + 696, 2, &v23);
    pTaskConfig.pszContent = (PCWSTR)((-(__int64)(v23 != 0) & 0xFFFFFFFFFFFFFFB3uLL) + 675);
  }
  v20 = v24;
  pTaskConfig.cButtons = 2;
  pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v28;
  pTaskConfig.nDefaultButton = 7;
  if ( v16 && v24 )
    pTaskConfig.pszVerificationText = v36;
  else
    pTaskConfig.pszVerificationText = 0;
  memset(&pTaskConfig.pszExpandedInformation, 0, 32);
  pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)TaskDialogCallbackProc;
  pTaskConfig.pszFooter = (PCWSTR)596;
  pTaskConfig.lpCallbackData = 0;
  FlashAndBeep(a1);
  v17 = TaskDialogIndirect(&pTaskConfig, a2, &pnRadioButton, &pfVerificationFlagChecked);
  if ( v17 < 0 )
  {
    v19 = 2648;
    goto LABEL_20;
  }
  if ( a4 )
  {
    if ( v16 != 1 || v20 )
      v9 = pfVerificationFlagChecked;
    *a4 = v9;
  }
  return 0;
}

```

## disassembly

```asm
0x14002bd4c  push    rbp
0x14002bd4e  push    rbx
0x14002bd4f  push    rsi
0x14002bd50  push    rdi
0x14002bd51  push    r12
0x14002bd53  push    r13
0x14002bd55  push    r14
0x14002bd57  push    r15
0x14002bd59  lea     rbp, [rsp-2028h]
0x14002bd61  mov     eax, 2128h
0x14002bd66  call    _alloca_probe
0x14002bd6b  sub     rsp, rax
0x14002bd6e  mov     rax, cs:__security_cookie
0x14002bd75  xor     rax, rsp
0x14002bd78  mov     [rbp+2060h+var_50], rax
0x14002bd7f  mov     rdi, r8
0x14002bd82  mov     r12, rdx
0x14002bd85  mov     r13, rcx
0x14002bd88  xor     edx, edx; Val
0x14002bd8a  mov     r8d, 0A0h; Size
0x14002bd90  lea     rcx, [rsp+2160h+pTaskConfig]; void *
0x14002bd95  mov     r14, r9
0x14002bd98  call    memset_0
0x14002bd9d  mov     ebx, 800h
0x14002bda2  lea     rcx, [rbp+2060h+var_1050]; void *
0x14002bda9  mov     r8d, ebx; Size
0x14002bdac  xor     edx, edx; Val
0x14002bdae  call    memset_0
0x14002bdb3  mov     r8d, ebx; Size
0x14002bdb6  lea     rcx, [rbp+2060h+Buffer]; void *
0x14002bdba  xor     edx, edx; Val
0x14002bdbc  call    memset_0
0x14002bdc1  mov     r8d, ebx; Size
0x14002bdc4  lea     rcx, [rbp+2060h+var_1850]; void *
0x14002bdcb  xor     edx, edx; Val
0x14002bdcd  call    memset_0
0x14002bdd2  mov     r8d, ebx; Size
0x14002bdd5  lea     rcx, [rbp+2060h+var_850]; void *
0x14002bddc  xor     edx, edx; Val
0x14002bdde  call    memset_0
0x14002bde3  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002bdea  lea     r8, [rsp+2160h+var_2118]
0x14002bdef  xor     eax, eax
0x14002bdf1  mov     [rsp+2160h+var_2110], 6
0x14002bdf9  add     rcx, 2B8h
0x14002be00  mov     [rsp+2160h+var_2118], rax
0x14002be05  xor     edx, edx
0x14002be07  mov     [rsp+2160h+var_2128], eax
0x14002be0b  mov     esi, eax
0x14002be0d  mov     [rsp+2160h+var_2130], eax
0x14002be11  lea     ebx, [rax+1]
0x14002be14  mov     [rsp+2160h+pfVerificationFlagChecked], eax
0x14002be18  mov     [rsp+2160h+var_212C], ebx
0x14002be1c  mov     [rsp+2160h+pnRadioButton], eax
0x14002be20  mov     [rsp+2160h+var_210C], 222h
0x14002be29  mov     [rsp+2160h+var_2104], 7
0x14002be31  mov     [rsp+2160h+var_2100], 224h
0x14002be3a  call    ?GetGroupPolicySetting@CSettingsManager@@QEAAJW4_RAGroupPolicySettingString@@PEAPEAG@Z; CSettingsManager::GetGroupPolicySetting(_RAGroupPolicySettingString,ushort * *)
0x14002be3f  mov     r15, [rsp+2160h+var_2118]
0x14002be44  test    eax, eax
0x14002be46  js      short loc_14002BE4F
0x14002be48  test    r15, r15
0x14002be4b  setnz   sil
0x14002be4f  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002be56  lea     r8, [rbp+2060h+Buffer]; lpBuffer
0x14002be5a  mov     r9d, 400h; cchBufferMax
0x14002be60  mov     edx, 255h; uID
0x14002be65  mov     rcx, [rcx+260h]; hInstance
0x14002be6c  call    cs:__imp_LoadStringW
0x14002be73  nop     dword ptr [rax+rax+00h]
0x14002be78  test    eax, eax
0x14002be7a  jnz     short loc_14002BE8B
0x14002be7c  mov     [rsp+2160h+var_2138], eax
0x14002be80  mov     r9d, 9F6h
0x14002be86  jmp     loc_14002C038
0x14002be8b  mov     r9, rdi
0x14002be8e  lea     r8, [rbp+2060h+Buffer]; unsigned __int16 *
0x14002be92  mov     edx, 400h; unsigned __int64
0x14002be97  lea     rcx, [rbp+2060h+var_1050]; unsigned __int16 *
0x14002be9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002bea3  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002beaa  lea     r8, [rbp+2060h+var_1850]; lpBuffer
0x14002beb1  mov     r9d, 400h; cchBufferMax
0x14002beb7  mov     edx, 294h; uID
0x14002bebc  mov     rcx, [rcx+260h]; hInstance
0x14002bec3  call    cs:__imp_LoadStringW
0x14002beca  nop     dword ptr [rax+rax+00h]
0x14002becf  test    eax, eax
0x14002bed1  jnz     short loc_14002BEE2
0x14002bed3  mov     [rsp+2160h+var_2138], eax
0x14002bed7  mov     r9d, 0A01h
0x14002bedd  jmp     loc_14002C038
0x14002bee2  mov     r9, rdi
0x14002bee5  lea     r8, [rbp+2060h+var_1850]; unsigned __int16 *
0x14002beec  mov     edx, 400h; unsigned __int64
0x14002bef1  lea     rcx, [rbp+2060h+var_850]; unsigned __int16 *
0x14002bef8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002befd  lea     rdx, [rsp+2160h+var_2130]
0x14002bf02  call    LUAPromptOnSecureDesktop
0x14002bf07  mov     edi, [rsp+2160h+var_2130]
0x14002bf0b  xor     ecx, ecx
0x14002bf0d  test    eax, eax
0x14002bf0f  cmovs   edi, ecx
0x14002bf12  lea     rcx, [rsp+2160h+var_2128]; int *
0x14002bf17  call    ?PromptToDisableUAC@@YAJPEAH@Z; PromptToDisableUAC(int *)
0x14002bf1c  test    eax, eax
0x14002bf1e  jns     short loc_14002BF2B
0x14002bf20  mov     r9d, 0A0Eh
0x14002bf26  jmp     loc_14002C034
0x14002bf2b  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002bf32  mov     [rsp+2160h+pTaskConfig.cbSize], 0A0h
0x14002bf3a  mov     [rsp+2160h+pTaskConfig.hwndParent], r13
0x14002bf3f  mov     rax, [rcx+260h]
0x14002bf46  mov     [rsp+2160h+pTaskConfig.hInstance], rax
0x14002bf4b  lea     rax, [rbp+2060h+var_1050]
0x14002bf52  mov     [rbp+2060h+pTaskConfig.pszMainInstruction], rax
0x14002bf56  mov     qword ptr [rbp+2060h+pTaskConfig.dwFlags], 809h
0x14002bf5e  mov     [rbp+2060h+pTaskConfig.pszWindowTitle], 64h ; 'd'
0x14002bf66  mov     qword ptr [rbp+2060h+pTaskConfig.24h], 0
0x14002bf6e  cmp     esi, ebx
0x14002bf70  jnz     short loc_14002BF78
0x14002bf72  mov     [rbp+2060h+pTaskConfig.pszContent], r15
0x14002bf76  jmp     short loc_14002BFA6
0x14002bf78  add     rcx, 2B8h
0x14002bf7f  lea     r8, [rsp+2160h+var_212C]
0x14002bf84  mov     edx, 2
0x14002bf89  call    ?GetSettingFromRegistry@CSettingsManager@@QEAAJW4_RASettingDWORD@@PEAK@Z; CSettingsManager::GetSettingFromRegistry(_RASettingDWORD,ulong *)
0x14002bf8e  mov     eax, [rsp+2160h+var_212C]
0x14002bf92  neg     eax
0x14002bf94  sbb     rcx, rcx
0x14002bf97  and     rcx, 0FFFFFFFFFFFFFFB3h
0x14002bf9b  add     rcx, 2A3h
0x14002bfa2  mov     [rbp+2060h+pTaskConfig.pszContent], rcx
0x14002bfa6  mov     esi, [rsp+2160h+var_2128]
0x14002bfaa  lea     rax, [rsp+2160h+var_2110]
0x14002bfaf  xor     r15d, r15d
0x14002bfb2  mov     [rbp+2060h+pTaskConfig.cButtons], 2
0x14002bfb9  mov     [rbp+2060h+pTaskConfig.pButtons], rax
0x14002bfbd  mov     [rbp+2060h+pTaskConfig.nDefaultButton], 7
0x14002bfc4  test    edi, edi
0x14002bfc6  jz      short loc_14002BFD9
0x14002bfc8  test    esi, esi
0x14002bfca  jz      short loc_14002BFD9
0x14002bfcc  lea     rax, [rbp+2060h+var_850]
0x14002bfd3  mov     [rbp+2060h+pTaskConfig.pszVerificationText], rax
0x14002bfd7  jmp     short loc_14002BFDD
0x14002bfd9  mov     [rbp+2060h+pTaskConfig.pszVerificationText], r15
0x14002bfdd  lea     rax, ?TaskDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; TaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x14002bfe4  mov     [rbp+2060h+pTaskConfig.pszExpandedInformation], r15
0x14002bfe8  mov     rcx, r13; HWND
0x14002bfeb  mov     [rbp+2060h+pTaskConfig.pfCallback], rax
0x14002bfef  mov     [rbp+2060h+pTaskConfig.pszExpandedControlText], r15
0x14002bff3  mov     [rbp+2060h+pTaskConfig.pszCollapsedControlText], r15
0x14002bff7  mov     qword ptr [rbp+2060h+pTaskConfig.7Ch], r15
0x14002bffb  mov     [rbp+2060h+pTaskConfig.pszFooter], 254h
0x14002c003  mov     [rbp+2060h+pTaskConfig.lpCallbackData], r15
0x14002c007  call    ?FlashAndBeep@@YAXPEAUHWND__@@@Z; FlashAndBeep(HWND__ *)
0x14002c00c  lea     r9, [rsp+2160h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x14002c011  mov     rdx, r12; pnButton
0x14002c014  lea     r8, [rsp+2160h+pnRadioButton]; pnRadioButton
0x14002c019  lea     rcx, [rsp+2160h+pTaskConfig]; pTaskConfig
0x14002c01e  call    cs:__imp_TaskDialogIndirect
0x14002c025  nop     dword ptr [rax+rax+00h]
0x14002c02a  test    eax, eax
0x14002c02c  jns     short loc_14002C061
0x14002c02e  mov     r9d, 0A58h; unsigned int
0x14002c034  mov     [rsp+2160h+var_2138], eax; unsigned int
0x14002c038  lea     rax, aShowallowcontr; "ShowAllowControlDialog"
0x14002c03f  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002c046  mov     [rsp+2160h+var_2140], rax; unsigned __int16 *
0x14002c04b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002c052  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002c057  mov     dword ptr [r12], 7
0x14002c05f  jmp     short loc_14002C075
0x14002c061  test    r14, r14
0x14002c064  jz      short loc_14002C075
0x14002c066  cmp     edi, ebx
0x14002c068  jnz     short loc_14002C06E
0x14002c06a  test    esi, esi
0x14002c06c  jz      short loc_14002C072
0x14002c06e  mov     ebx, [rsp+2160h+pfVerificationFlagChecked]
0x14002c072  mov     [r14], ebx
0x14002c075  xor     eax, eax
0x14002c077  mov     rcx, [rbp+2060h+var_50]
0x14002c07e  xor     rcx, rsp; StackCookie
0x14002c081  call    __security_check_cookie
0x14002c086  add     rsp, 2128h
0x14002c08d  pop     r15
0x14002c08f  pop     r14
0x14002c091  pop     r13
0x14002c093  pop     r12
0x14002c095  pop     rdi
0x14002c096  pop     rsi
0x14002c097  pop     rbx
0x14002c098  pop     rbp
0x14002c099  retn
```
