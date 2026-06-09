# SetZeroRecoveryAsDone(void *)

- ea: `0x18002def8`
- end: `0x18002e128`
- name: `?SetZeroRecoveryAsDone@@YAKPEAX@Z`
- size: `560`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x180007f10`
- `0x18000a5d0`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001f68c`
- `0x18001f8c0`
- `0x18002a600`
- `0x18002cd1c`
- `0x18002def8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002dfe2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002dfe2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e01d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e01d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e07e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e07e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dfcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dfcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0db`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002dfbf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002dfbf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002e0cb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002e0cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002dfa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002dfa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e0ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e0ee`
- `ntdll!RtlEnterCriticalSection` at `0x18002dff5`
- `ntdll!RtlEnterCriticalSection` at `0x18002dff5`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e0b3`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e0b3`

## string_xrefs

- `0x18002df86`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002e096`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall SetZeroRecoveryAsDone(void *a1)
{
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v4; // eax
  __int64 v5; // r9
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  TokenHandle = 0;
  Data[0] = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 121, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  if ( !(unsigned int)GetTextualSid(a1, ValueName, 261) )
  {
    LastError = 8;
    DebugTraceError(8, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 7126);
    goto LABEL_14;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    goto LABEL_18;
  }
  RevertToSelf();
  RtlEnterCriticalSection(&stru_18004C940);
  Data[1] = 1;
  hKey = 0;
  v4 = OpenZeroRecoveryKey(0x20006u, &hKey);
  LastError = v4;
  if ( v4 )
  {
    v5 = 7151;
LABEL_12:
    DebugTraceError(v4, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v5);
    goto LABEL_13;
  }
  v4 = RegSetValueExW(hKey, ValueName, 0, 3u, Data, 1u);
  LastError = v4;
  if ( v4 )
  {
    v5 = 7161;
    goto LABEL_12;
  }
LABEL_13:
  RtlLeaveCriticalSection(&stru_18004C940);
LABEL_14:
  if ( TokenHandle )
  {
    if ( !SetThreadToken(0, TokenHandle) )
      LastError = GetLastError();
    CloseHandle(TokenHandle);
  }
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return LastError;
}

```

## disassembly

```asm
0x18002def8  mov     [rsp-8+arg_8], rbx
0x18002defd  push    rbp
0x18002defe  lea     rbp, [rsp-170h]
0x18002df06  sub     rsp, 270h
0x18002df0d  mov     rax, cs:__security_cookie
0x18002df14  xor     rax, rsp
0x18002df17  mov     [rbp+170h+var_10], rax
0x18002df1e  mov     rbx, rcx
0x18002df21  mov     [rsp+270h+hKey], 0
0x18002df2a  mov     [rsp+270h+TokenHandle], 0
0x18002df33  mov     [rsp+270h+Data], 1
0x18002df38  lea     rax, WPP_GLOBAL_Control
0x18002df3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df46  cmp     rcx, rax
0x18002df49  jz      short loc_18002DF66
0x18002df4b  test    byte ptr [rcx+1Ch], 4
0x18002df4f  jz      short loc_18002DF66
0x18002df51  mov     edx, 79h ; 'y'
0x18002df56  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002df5d  mov     rcx, [rcx+10h]
0x18002df61  call    WPP_SF_
0x18002df66  mov     r8d, 105h
0x18002df6c  lea     rdx, [rsp+270h+ValueName]
0x18002df71  mov     rcx, rbx
0x18002df74  call    GetTextualSid
0x18002df79  test    eax, eax
0x18002df7b  jnz     short loc_18002DFA0
0x18002df7d  lea     ebx, [rax+8]
0x18002df80  mov     r9d, 1BD6h
0x18002df86  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002df8d  lea     rdx, aDwerror; "dwError"
0x18002df94  mov     ecx, ebx
0x18002df96  call    DebugTraceError
0x18002df9b  jmp     loc_18002E0BF
0x18002dfa0  call    cs:__imp_GetCurrentThread
0x18002dfa7  nop     dword ptr [rax+rax+00h]
0x18002dfac  mov     rcx, rax; ThreadHandle
0x18002dfaf  lea     r9, [rsp+270h+TokenHandle]; TokenHandle
0x18002dfb4  mov     edx, 2000Ch; DesiredAccess
0x18002dfb9  mov     r8d, 1; OpenAsSelf
0x18002dfbf  call    cs:__imp_OpenThreadToken
0x18002dfc6  nop     dword ptr [rax+rax+00h]
0x18002dfcb  test    eax, eax
0x18002dfcd  jnz     short loc_18002DFE2
0x18002dfcf  call    cs:__imp_GetLastError
0x18002dfd6  nop     dword ptr [rax+rax+00h]
0x18002dfdb  mov     ebx, eax
0x18002dfdd  jmp     loc_18002E0FB
0x18002dfe2  call    cs:__imp_RevertToSelf
0x18002dfe9  nop     dword ptr [rax+rax+00h]
0x18002dfee  lea     rcx, stru_18004C940; CriticalSection
0x18002dff5  call    cs:__imp_RtlEnterCriticalSection
0x18002dffc  nop     dword ptr [rax+rax+00h]
0x18002e001  mov     [rsp+270h+var_23F], 1
0x18002e006  mov     rbx, [rsp+270h+hKey]
0x18002e00b  test    rbx, rbx
0x18002e00e  jz      short loc_18002E033
0x18002e010  lea     rcx, [rsp+270h+var_228]; this
0x18002e015  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e01a  mov     rcx, rbx; hKey
0x18002e01d  call    cs:__imp_RegCloseKey
0x18002e024  nop     dword ptr [rax+rax+00h]
0x18002e029  lea     rcx, [rsp+270h+var_228]; this
0x18002e02e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e033  mov     [rsp+270h+hKey], 0
0x18002e03c  lea     rdx, [rsp+270h+hKey]; phkResult
0x18002e041  mov     ecx, 20006h; samDesired
0x18002e046  call    OpenZeroRecoveryKey
0x18002e04b  mov     ebx, eax
0x18002e04d  test    eax, eax
0x18002e04f  jz      short loc_18002E059
0x18002e051  mov     r9d, 1BEFh
0x18002e057  jmp     short loc_18002E096
0x18002e059  mov     [rsp+270h+cbData], 1; cbData
0x18002e061  lea     rax, [rsp+270h+Data]
0x18002e066  mov     [rsp+270h+lpData], rax; lpData
0x18002e06b  mov     r9d, 3; dwType
0x18002e071  xor     r8d, r8d; Reserved
0x18002e074  lea     rdx, [rsp+270h+ValueName]; lpValueName
0x18002e079  mov     rcx, [rsp+270h+hKey]; hKey
0x18002e07e  call    cs:__imp_RegSetValueExW
0x18002e085  nop     dword ptr [rax+rax+00h]
0x18002e08a  mov     ebx, eax
0x18002e08c  test    eax, eax
0x18002e08e  jz      short loc_18002E0AC
0x18002e090  mov     r9d, 1BF9h
0x18002e096  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002e09d  lea     rdx, aDwerror; "dwError"
0x18002e0a4  mov     ecx, eax
0x18002e0a6  call    DebugTraceError
0x18002e0ab  nop
0x18002e0ac  lea     rcx, stru_18004C940; CriticalSection
0x18002e0b3  call    cs:__imp_RtlLeaveCriticalSection
0x18002e0ba  nop     dword ptr [rax+rax+00h]
0x18002e0bf  mov     rdx, [rsp+270h+TokenHandle]; Token
0x18002e0c4  test    rdx, rdx
0x18002e0c7  jz      short loc_18002E0FB
0x18002e0c9  xor     ecx, ecx; Thread
0x18002e0cb  call    cs:__imp_SetThreadToken
0x18002e0d2  nop     dword ptr [rax+rax+00h]
0x18002e0d7  test    eax, eax
0x18002e0d9  jnz     short loc_18002E0E9
0x18002e0db  call    cs:__imp_GetLastError
0x18002e0e2  nop     dword ptr [rax+rax+00h]
0x18002e0e7  mov     ebx, eax
0x18002e0e9  mov     rcx, [rsp+270h+TokenHandle]; hObject
0x18002e0ee  call    cs:__imp_CloseHandle
0x18002e0f5  nop     dword ptr [rax+rax+00h]
0x18002e0fa  nop
0x18002e0fb  lea     rcx, [rsp+270h+hKey]
0x18002e100  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002e105  mov     eax, ebx
0x18002e107  mov     rcx, [rbp+170h+var_10]
0x18002e10e  xor     rcx, rsp; StackCookie
0x18002e111  call    __security_check_cookie
0x18002e116  mov     rbx, [rsp+270h+arg_8]
0x18002e11e  add     rsp, 270h
0x18002e125  pop     rbp
0x18002e126  retn
```
