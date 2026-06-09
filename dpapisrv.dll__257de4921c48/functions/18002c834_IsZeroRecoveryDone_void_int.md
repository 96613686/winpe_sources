# IsZeroRecoveryDone(void *,int &)

- ea: `0x18002c834`
- end: `0x18002ca68`
- name: `?IsZeroRecoveryDone@@YAKPEAXAEAH@Z`
- size: `564`
- prototype: `__int64 __fastcall(void *, int *)`
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
- `0x18002c834`
- `0x18002cd1c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c927`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c927`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c9c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c9c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca17`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c904`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c904`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002ca07`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002ca07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c8e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c8e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ca2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ca2a`
- `ntdll!RtlEnterCriticalSection` at `0x18002c93a`
- `ntdll!RtlEnterCriticalSection` at `0x18002c93a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c9ef`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c9ef`

## string_xrefs

- `0x18002c8cb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall IsZeroRecoveryDone(void *a1, int *a2)
{
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v9[8]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  TokenHandle = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 122, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  *a2 = 0;
  if ( (unsigned int)GetTextualSid(a1, ValueName, 261) )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      goto LABEL_22;
    }
    RevertToSelf();
    RtlEnterCriticalSection(&stru_18004C940);
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v9);
      RegCloseKey(hKey);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
    }
    hKey = 0;
    LastError = OpenZeroRecoveryKey(0x20019u, &hKey);
    if ( LastError )
    {
      *a2 = 0;
    }
    else
    {
      LastError = RegQueryValueExW(hKey, ValueName, 0, 0, 0, 0);
      if ( LastError )
      {
        *a2 = 0;
        if ( LastError == 2 )
          LastError = 0;
      }
      else
      {
        *a2 = 1;
      }
    }
    RtlLeaveCriticalSection(&stru_18004C940);
  }
  else
  {
    LastError = 8;
    DebugTraceError(8, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 7201);
  }
  if ( TokenHandle )
  {
    if ( !SetThreadToken(0, TokenHandle) )
      LastError = GetLastError();
    CloseHandle(TokenHandle);
  }
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return LastError;
}

```

## disassembly

```asm
0x18002c834  mov     [rsp-8+arg_10], rbx
0x18002c839  mov     [rsp-8+arg_18], rdi
0x18002c83e  push    rbp
0x18002c83f  lea     rbp, [rsp-170h]
0x18002c847  sub     rsp, 270h
0x18002c84e  mov     rax, cs:__security_cookie
0x18002c855  xor     rax, rsp
0x18002c858  mov     [rbp+170h+var_10], rax
0x18002c85f  mov     rdi, rdx
0x18002c862  mov     rbx, rcx
0x18002c865  mov     [rsp+270h+hKey], 0
0x18002c86e  mov     [rsp+270h+TokenHandle], 0
0x18002c877  lea     rax, WPP_GLOBAL_Control
0x18002c87e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c885  cmp     rcx, rax
0x18002c888  jz      short loc_18002C8A5
0x18002c88a  test    byte ptr [rcx+1Ch], 4
0x18002c88e  jz      short loc_18002C8A5
0x18002c890  mov     edx, 7Ah ; 'z'
0x18002c895  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002c89c  mov     rcx, [rcx+10h]
0x18002c8a0  call    WPP_SF_
0x18002c8a5  mov     dword ptr [rdi], 0
0x18002c8ab  mov     r8d, 105h
0x18002c8b1  lea     rdx, [rsp+270h+ValueName]
0x18002c8b6  mov     rcx, rbx
0x18002c8b9  call    GetTextualSid
0x18002c8be  test    eax, eax
0x18002c8c0  jnz     short loc_18002C8E5
0x18002c8c2  lea     ebx, [rax+8]
0x18002c8c5  mov     r9d, 1C21h
0x18002c8cb  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002c8d2  lea     rdx, aDwerror; "dwError"
0x18002c8d9  mov     ecx, ebx
0x18002c8db  call    DebugTraceError
0x18002c8e0  jmp     loc_18002C9FB
0x18002c8e5  call    cs:__imp_GetCurrentThread
0x18002c8ec  nop     dword ptr [rax+rax+00h]
0x18002c8f1  mov     rcx, rax; ThreadHandle
0x18002c8f4  lea     r9, [rsp+270h+TokenHandle]; TokenHandle
0x18002c8f9  mov     edx, 2000Ch; DesiredAccess
0x18002c8fe  mov     r8d, 1; OpenAsSelf
0x18002c904  call    cs:__imp_OpenThreadToken
0x18002c90b  nop     dword ptr [rax+rax+00h]
0x18002c910  test    eax, eax
0x18002c912  jnz     short loc_18002C927
0x18002c914  call    cs:__imp_GetLastError
0x18002c91b  nop     dword ptr [rax+rax+00h]
0x18002c920  mov     ebx, eax
0x18002c922  jmp     loc_18002CA37
0x18002c927  call    cs:__imp_RevertToSelf
0x18002c92e  nop     dword ptr [rax+rax+00h]
0x18002c933  lea     rcx, stru_18004C940; CriticalSection
0x18002c93a  call    cs:__imp_RtlEnterCriticalSection
0x18002c941  nop     dword ptr [rax+rax+00h]
0x18002c946  mov     [rsp+270h+var_240], 1
0x18002c94b  mov     rbx, [rsp+270h+hKey]
0x18002c950  test    rbx, rbx
0x18002c953  jz      short loc_18002C978
0x18002c955  lea     rcx, [rsp+270h+var_228]; this
0x18002c95a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002c95f  mov     rcx, rbx; hKey
0x18002c962  call    cs:__imp_RegCloseKey
0x18002c969  nop     dword ptr [rax+rax+00h]
0x18002c96e  lea     rcx, [rsp+270h+var_228]; this
0x18002c973  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002c978  mov     [rsp+270h+hKey], 0
0x18002c981  lea     rdx, [rsp+270h+hKey]; phkResult
0x18002c986  mov     ecx, 20019h; samDesired
0x18002c98b  call    OpenZeroRecoveryKey
0x18002c990  mov     ebx, eax
0x18002c992  test    eax, eax
0x18002c994  jz      short loc_18002C99E
0x18002c996  mov     dword ptr [rdi], 0
0x18002c99c  jmp     short loc_18002C9E8
0x18002c99e  mov     [rsp+270h+lpcbData], 0; lpcbData
0x18002c9a7  mov     [rsp+270h+lpData], 0; lpData
0x18002c9b0  xor     r9d, r9d; lpType
0x18002c9b3  xor     r8d, r8d; lpReserved
0x18002c9b6  lea     rdx, [rsp+270h+ValueName]; lpValueName
0x18002c9bb  mov     rcx, [rsp+270h+hKey]; hKey
0x18002c9c0  call    cs:__imp_RegQueryValueExW
0x18002c9c7  nop     dword ptr [rax+rax+00h]
0x18002c9cc  mov     ebx, eax
0x18002c9ce  test    eax, eax
0x18002c9d0  jz      short loc_18002C9E2
0x18002c9d2  mov     dword ptr [rdi], 0
0x18002c9d8  xor     eax, eax
0x18002c9da  cmp     ebx, 2
0x18002c9dd  cmovz   ebx, eax
0x18002c9e0  jmp     short loc_18002C9E8
0x18002c9e2  mov     dword ptr [rdi], 1
0x18002c9e8  lea     rcx, stru_18004C940; CriticalSection
0x18002c9ef  call    cs:__imp_RtlLeaveCriticalSection
0x18002c9f6  nop     dword ptr [rax+rax+00h]
0x18002c9fb  mov     rdx, [rsp+270h+TokenHandle]; Token
0x18002ca00  test    rdx, rdx
0x18002ca03  jz      short loc_18002CA37
0x18002ca05  xor     ecx, ecx; Thread
0x18002ca07  call    cs:__imp_SetThreadToken
0x18002ca0e  nop     dword ptr [rax+rax+00h]
0x18002ca13  test    eax, eax
0x18002ca15  jnz     short loc_18002CA25
0x18002ca17  call    cs:__imp_GetLastError
0x18002ca1e  nop     dword ptr [rax+rax+00h]
0x18002ca23  mov     ebx, eax
0x18002ca25  mov     rcx, [rsp+270h+TokenHandle]; hObject
0x18002ca2a  call    cs:__imp_CloseHandle
0x18002ca31  nop     dword ptr [rax+rax+00h]
0x18002ca36  nop
0x18002ca37  lea     rcx, [rsp+270h+hKey]
0x18002ca3c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002ca41  mov     eax, ebx
0x18002ca43  mov     rcx, [rbp+170h+var_10]
0x18002ca4a  xor     rcx, rsp; StackCookie
0x18002ca4d  call    __security_check_cookie
0x18002ca52  lea     r11, [rsp+270h+var_s0]
0x18002ca5a  mov     rbx, [r11+20h]
0x18002ca5e  mov     rdi, [r11+28h]
0x18002ca62  mov     rsp, r11
0x18002ca65  pop     rbp
0x18002ca66  retn
```
