# ShowAcceptConnectionDialog(HWND__ *,int *,ushort *)

- ea: `0x14002b9d8`
- end: `0x14002bd45`
- name: `?ShowAcceptConnectionDialog@@YAJPEAUHWND__@@PEAHPEAG@Z`
- size: `877`
- prototype: `__int64 __fastcall(HWND, int *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140011ec0`
- `0x140025740`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x140028a2c`
- `0x14002b9d8`
- `0x140034ce4`
- `0x140036efc`
- `0x1400373f4`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14002bc93`
- `KERNEL32!SetEvent` at `0x14002bc93`
- `KERNEL32!GetModuleHandleW` at `0x14002baf0`
- `KERNEL32!GetModuleHandleW` at `0x14002bb81`
- `KERNEL32!GetModuleHandleW` at `0x14002baf0`
- `KERNEL32!GetModuleHandleW` at `0x14002bb81`
- `KERNEL32!CloseHandle` at `0x14002bd0c`
- `KERNEL32!CloseHandle` at `0x14002bd0c`
- `USER32!LoadStringW` at `0x14002bb10`
- `USER32!LoadStringW` at `0x14002bb9c`
- `USER32!LoadStringW` at `0x14002bb10`
- `USER32!LoadStringW` at `0x14002bb9c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bcf5`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bcf5`
- `OLEAUT32!__imp_SysStringLen` at `0x14002badd`
- `OLEAUT32!__imp_SysStringLen` at `0x14002badd`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002bcb0`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002bcb0`

## string_xrefs

- `0x14002bb37`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002bcd8`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ShowAcceptConnectionDialog(HWND a1, int *a2, unsigned __int16 *a3)
{
  OLECHAR *v6; // rbx
  HRESULT v7; // eax
  CEventLogger *v8; // rcx
  unsigned int v9; // edi
  unsigned int v10; // r9d
  BOOL v11; // esi
  int GroupPolicySetting; // eax
  HMODULE ModuleHandleW; // rax
  CEventLogger *v14; // rcx
  unsigned int v15; // r9d
  HMODULE v16; // rax
  unsigned __int16 *v17; // rax
  void *v18; // rcx
  BOOL pfVerificationFlagChecked; // [rsp+30h] [rbp-D0h] BYREF
  int pnRadioButton; // [rsp+34h] [rbp-CCh] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+44h] [rbp-BCh]
  int v25; // [rsp+4Ch] [rbp-B4h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+70h] [rbp-90h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[1024]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v32[1024]; // [rsp+920h] [rbp+820h] BYREF
  unsigned __int16 v33[1024]; // [rsp+1120h] [rbp+1020h] BYREF

  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  memset_0(v32, 0, sizeof(v32));
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v33, 0, sizeof(v33));
  hObject = 0;
  v28 = 0;
  v29 = 0;
  v6 = 0;
  pbstr = 0;
  v23 = 6;
  v24 = 546;
  v25 = 7;
  v26 = 548;
  v7 = CSettingsManager::Initialize((CSettingsManager *)&hObject);
  v9 = v7;
  if ( v7 < 0 )
  {
    v10 = 1475;
LABEL_19:
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v10,
      L"ShowAcceptConnectionDialog",
      v7);
    goto LABEL_20;
  }
  v11 = 0;
  GroupPolicySetting = CSettingsManager::GetGroupPolicySetting(&hObject, 1, &pbstr);
  v6 = pbstr;
  if ( GroupPolicySetting >= 0 )
    v11 = SysStringLen(pbstr) != 0;
  ModuleHandleW = GetModuleHandleW(0);
  if ( !LoadStringW(ModuleHandleW, 0x252u, Buffer, 1024) )
  {
    v15 = 1493;
LABEL_7:
    CEventLogger::LogError(
      v14,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v15,
      L"ShowAcceptConnectionDialog",
      0);
    v9 = -2147467259;
LABEL_20:
    *a2 = 7;
    goto LABEL_21;
  }
  StringCchPrintfW(v32, 0x400u, Buffer, a3);
  if ( !v11 )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    v16 = GetModuleHandleW(0);
    if ( !LoadStringW(v16, 0x253u, Buffer, 1024) )
    {
      v15 = 1510;
      goto LABEL_7;
    }
    v7 = StringCchPrintfW(v33, 0x400u, Buffer, a3);
    v9 = v7;
    if ( v7 < 0 )
    {
      v10 = 1516;
      goto LABEL_19;
    }
  }
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = a1;
  pTaskConfig.hInstance = (HINSTANCE)*((_QWORD *)_AtlModule + 76);
  *(_QWORD *)&pTaskConfig.dwFlags = 2057;
  pTaskConfig.pszWindowTitle = (PCWSTR)100;
  pTaskConfig.hMainIcon = 0;
  pTaskConfig.pszMainInstruction = v32;
  v17 = v33;
  if ( v11 )
    v17 = v6;
  pTaskConfig.pszContent = v17;
  pTaskConfig.cButtons = 2;
  pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v23;
  pTaskConfig.nDefaultButton = 7;
  memset(&pTaskConfig.pszVerificationText, 0, 40);
  pTaskConfig.pszFooter = (PCWSTR)596;
  pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)TaskDialogCallbackProc;
  pTaskConfig.lpCallbackData = 0;
  pfVerificationFlagChecked = 0;
  pnRadioButton = 0;
  FlashAndBeep(a1);
  v18 = (void *)*((_QWORD *)_AtlModule + 108);
  if ( v18 )
    SetEvent(v18);
  v7 = TaskDialogIndirect(&pTaskConfig, a2, &pnRadioButton, &pfVerificationFlagChecked);
  v9 = v7;
  if ( v7 < 0 )
  {
    v10 = 1572;
    goto LABEL_19;
  }
LABEL_21:
  SysFreeString(v6);
  if ( hObject )
    CloseHandle(hObject);
  return v9;
}

```

## disassembly

```asm
0x14002b9d8  mov     [rsp-8+arg_18], rbx
0x14002b9dd  push    rbp
0x14002b9de  push    rsi
0x14002b9df  push    rdi
0x14002b9e0  push    r12
0x14002b9e2  push    r13
0x14002b9e4  push    r14
0x14002b9e6  push    r15
0x14002b9e8  lea     rbp, [rsp-1830h]
0x14002b9f0  mov     eax, 1930h
0x14002b9f5  call    _alloca_probe
0x14002b9fa  sub     rsp, rax
0x14002b9fd  mov     rax, cs:__security_cookie
0x14002ba04  xor     rax, rsp
0x14002ba07  mov     [rbp+1860h+var_40], rax
0x14002ba0e  mov     r15, r8
0x14002ba11  mov     r14, rdx
0x14002ba14  mov     r12, rcx
0x14002ba17  xor     edx, edx; Val
0x14002ba19  mov     r8d, 0A0h; Size
0x14002ba1f  lea     rcx, [rbp+1860h+pTaskConfig]; void *
0x14002ba23  call    memset_0
0x14002ba28  mov     ebx, 800h
0x14002ba2d  mov     r8d, ebx; Size
0x14002ba30  xor     edx, edx; Val
0x14002ba32  lea     rcx, [rbp+1860h+var_1040]; void *
0x14002ba39  call    memset_0
0x14002ba3e  mov     r8d, ebx; Size
0x14002ba41  xor     edx, edx; Val
0x14002ba43  lea     rcx, [rbp+1860h+Buffer]; void *
0x14002ba47  call    memset_0
0x14002ba4c  mov     r8d, ebx; Size
0x14002ba4f  xor     edx, edx; Val
0x14002ba51  lea     rcx, [rbp+1860h+var_840]; void *
0x14002ba58  call    memset_0
0x14002ba5d  xor     r13d, r13d
0x14002ba60  mov     [rsp+1960h+hObject], r13
0x14002ba65  xorps   xmm0, xmm0
0x14002ba68  xor     eax, eax
0x14002ba6a  movups  [rsp+1960h+var_1900], xmm0
0x14002ba6f  mov     [rsp+1960h+var_18F0], eax
0x14002ba73  mov     ebx, r13d
0x14002ba76  mov     [rsp+1960h+pbstr], rbx
0x14002ba7b  mov     [rsp+1960h+var_1920], 6
0x14002ba83  mov     [rsp+1960h+var_191C], 222h
0x14002ba8c  mov     [rsp+1960h+var_1914], 7
0x14002ba94  mov     [rsp+1960h+var_1910], 224h
0x14002ba9d  lea     rcx, [rsp+1960h+hObject]; this
0x14002baa2  call    ?Initialize@CSettingsManager@@QEAAJXZ; CSettingsManager::Initialize(void)
0x14002baa7  mov     edi, eax
0x14002baa9  test    eax, eax
0x14002baab  jns     short loc_14002BAB8
0x14002baad  mov     r9d, 5C3h
0x14002bab3  jmp     loc_14002BCC8
0x14002bab8  mov     esi, r13d
0x14002babb  lea     r8, [rsp+1960h+pbstr]
0x14002bac0  mov     edi, 1
0x14002bac5  mov     edx, edi
0x14002bac7  lea     rcx, [rsp+1960h+hObject]
0x14002bacc  call    ?GetGroupPolicySetting@CSettingsManager@@QEAAJW4_RAGroupPolicySettingString@@PEAPEAG@Z; CSettingsManager::GetGroupPolicySetting(_RAGroupPolicySettingString,ushort * *)
0x14002bad1  mov     rbx, [rsp+1960h+pbstr]
0x14002bad6  test    eax, eax
0x14002bad8  js      short loc_14002BAEE
0x14002bada  mov     rcx, rbx; pbstr
0x14002badd  call    cs:__imp_SysStringLen
0x14002bae4  nop     dword ptr [rax+rax+00h]
0x14002bae9  test    eax, eax
0x14002baeb  cmovnz  esi, edi
0x14002baee  xor     ecx, ecx; lpModuleName
0x14002baf0  call    cs:__imp_GetModuleHandleW
0x14002baf7  nop     dword ptr [rax+rax+00h]
0x14002bafc  mov     rcx, rax; hInstance
0x14002baff  mov     edi, 400h
0x14002bb04  mov     r9d, edi; cchBufferMax
0x14002bb07  lea     r8, [rbp+1860h+Buffer]; lpBuffer
0x14002bb0b  mov     edx, 252h; uID
0x14002bb10  call    cs:__imp_LoadStringW
0x14002bb17  nop     dword ptr [rax+rax+00h]
0x14002bb1c  test    eax, eax
0x14002bb1e  jnz     short loc_14002BB54
0x14002bb20  mov     r9d, 5D5h; unsigned int
0x14002bb26  mov     [rsp+1960h+var_1938], r13d; unsigned int
0x14002bb2b  lea     rax, aShowacceptconn_0; "ShowAcceptConnectionDialog"
0x14002bb32  mov     [rsp+1960h+var_1940], rax; unsigned __int16 *
0x14002bb37  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002bb3e  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002bb45  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002bb4a  mov     edi, 80004005h
0x14002bb4f  jmp     loc_14002BCEB
0x14002bb54  mov     r9, r15
0x14002bb57  lea     r8, [rbp+1860h+Buffer]; unsigned __int16 *
0x14002bb5b  mov     rdx, rdi; unsigned __int64
0x14002bb5e  lea     rcx, [rbp+1860h+var_1040]; unsigned __int16 *
0x14002bb65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002bb6a  test    esi, esi
0x14002bb6c  jnz     short loc_14002BBDE
0x14002bb6e  xor     edx, edx; Val
0x14002bb70  mov     r8d, 800h; Size
0x14002bb76  lea     rcx, [rbp+1860h+Buffer]; void *
0x14002bb7a  call    memset_0
0x14002bb7f  xor     ecx, ecx; lpModuleName
0x14002bb81  call    cs:__imp_GetModuleHandleW
0x14002bb88  nop     dword ptr [rax+rax+00h]
0x14002bb8d  mov     rcx, rax; hInstance
0x14002bb90  mov     r9d, edi; cchBufferMax
0x14002bb93  lea     r8, [rbp+1860h+Buffer]; lpBuffer
0x14002bb97  mov     edx, 253h; uID
0x14002bb9c  call    cs:__imp_LoadStringW
0x14002bba3  nop     dword ptr [rax+rax+00h]
0x14002bba8  test    eax, eax
0x14002bbaa  jnz     short loc_14002BBB7
0x14002bbac  mov     r9d, 5E6h
0x14002bbb2  jmp     loc_14002BB26
0x14002bbb7  mov     r9, r15
0x14002bbba  lea     r8, [rbp+1860h+Buffer]; unsigned __int16 *
0x14002bbbe  mov     rdx, rdi; unsigned __int64
0x14002bbc1  lea     rcx, [rbp+1860h+var_840]; unsigned __int16 *
0x14002bbc8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002bbcd  mov     edi, eax
0x14002bbcf  test    eax, eax
0x14002bbd1  jns     short loc_14002BBDE
0x14002bbd3  mov     r9d, 5ECh
0x14002bbd9  jmp     loc_14002BCC8
0x14002bbde  mov     [rbp+1860h+pTaskConfig.cbSize], 0A0h
0x14002bbe5  mov     [rbp+1860h+pTaskConfig.hwndParent], r12
0x14002bbe9  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002bbf0  mov     rcx, [rax+260h]
0x14002bbf7  mov     [rbp+1860h+pTaskConfig.hInstance], rcx
0x14002bbfb  mov     qword ptr [rbp+1860h+pTaskConfig.dwFlags], 809h
0x14002bc03  mov     [rbp+1860h+pTaskConfig.pszWindowTitle], 64h ; 'd'
0x14002bc0b  mov     qword ptr [rbp+1860h+pTaskConfig.24h], r13
0x14002bc0f  lea     rax, [rbp+1860h+var_1040]
0x14002bc16  mov     [rbp+1860h+pTaskConfig.pszMainInstruction], rax
0x14002bc1a  lea     rax, [rbp+1860h+var_840]
0x14002bc21  cmp     esi, 1
0x14002bc24  cmovz   rax, rbx
0x14002bc28  mov     [rbp+1860h+pTaskConfig.pszContent], rax
0x14002bc2c  mov     [rbp+1860h+pTaskConfig.cButtons], 2
0x14002bc33  lea     rax, [rsp+1960h+var_1920]
0x14002bc38  mov     [rbp+1860h+pTaskConfig.pButtons], rax
0x14002bc3c  mov     [rbp+1860h+pTaskConfig.nDefaultButton], 7
0x14002bc43  mov     [rbp+1860h+pTaskConfig.pszVerificationText], r13
0x14002bc47  mov     [rbp+1860h+pTaskConfig.pszExpandedInformation], r13
0x14002bc4b  mov     [rbp+1860h+pTaskConfig.pszExpandedControlText], r13
0x14002bc4f  mov     [rbp+1860h+pTaskConfig.pszCollapsedControlText], r13
0x14002bc53  mov     qword ptr [rbp+1860h+pTaskConfig.7Ch], r13
0x14002bc57  mov     [rbp+1860h+pTaskConfig.pszFooter], 254h
0x14002bc5f  lea     rax, ?TaskDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; TaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x14002bc66  mov     [rbp+1860h+pTaskConfig.pfCallback], rax
0x14002bc6a  mov     [rbp+1860h+pTaskConfig.lpCallbackData], r13
0x14002bc6e  mov     [rsp+1960h+pfVerificationFlagChecked], r13d
0x14002bc73  mov     [rsp+1960h+pnRadioButton], r13d
0x14002bc78  mov     rcx, r12; HWND
0x14002bc7b  call    ?FlashAndBeep@@YAXPEAUHWND__@@@Z; FlashAndBeep(HWND__ *)
0x14002bc80  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002bc87  mov     rcx, [rax+360h]; hEvent
0x14002bc8e  test    rcx, rcx
0x14002bc91  jz      short loc_14002BC9F
0x14002bc93  call    cs:__imp_SetEvent
0x14002bc9a  nop     dword ptr [rax+rax+00h]
0x14002bc9f  lea     r9, [rsp+1960h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x14002bca4  lea     r8, [rsp+1960h+pnRadioButton]; pnRadioButton
0x14002bca9  mov     rdx, r14; pnButton
0x14002bcac  lea     rcx, [rbp+1860h+pTaskConfig]; pTaskConfig
0x14002bcb0  call    cs:__imp_TaskDialogIndirect
0x14002bcb7  nop     dword ptr [rax+rax+00h]
0x14002bcbc  mov     edi, eax
0x14002bcbe  test    eax, eax
0x14002bcc0  jns     short loc_14002BCF2
0x14002bcc2  mov     r9d, 624h; unsigned int
0x14002bcc8  mov     [rsp+1960h+var_1938], eax; unsigned int
0x14002bccc  lea     rax, aShowacceptconn_0; "ShowAcceptConnectionDialog"
0x14002bcd3  mov     [rsp+1960h+var_1940], rax; unsigned __int16 *
0x14002bcd8  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002bcdf  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002bce6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002bceb  mov     dword ptr [r14], 7
0x14002bcf2  mov     rcx, rbx; bstrString
0x14002bcf5  call    cs:__imp_SysFreeString
0x14002bcfc  nop     dword ptr [rax+rax+00h]
0x14002bd01  nop
0x14002bd02  mov     rcx, [rsp+1960h+hObject]; hObject
0x14002bd07  test    rcx, rcx
0x14002bd0a  jz      short loc_14002BD18
0x14002bd0c  call    cs:__imp_CloseHandle
0x14002bd13  nop     dword ptr [rax+rax+00h]
0x14002bd18  mov     eax, edi
0x14002bd1a  mov     rcx, [rbp+1860h+var_40]
0x14002bd21  xor     rcx, rsp; StackCookie
0x14002bd24  call    __security_check_cookie
0x14002bd29  mov     rbx, [rsp+1960h+arg_18]
0x14002bd31  add     rsp, 1930h
0x14002bd38  pop     r15
0x14002bd3a  pop     r14
0x14002bd3c  pop     r13
0x14002bd3e  pop     r12
0x14002bd40  pop     rdi
0x14002bd41  pop     rsi
0x14002bd42  pop     rbp
0x14002bd43  retn
```
