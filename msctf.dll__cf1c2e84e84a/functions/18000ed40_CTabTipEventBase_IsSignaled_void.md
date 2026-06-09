# CTabTipEventBase::IsSignaled(void)

- ea: `0x18000ed40`
- end: `0x18000eeb0`
- name: `?IsSignaled@CTabTipEventBase@@QEAA_NXZ`
- size: `368`
- prototype: `bool __fastcall(CTabTipEventBase *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007a0f8`

## callees

- `0x18000ed40`
- `0x18000f030`
- `0x18000fac0`
- `0x180086b40`
- `0x180087150`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000ee69`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000ee69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000eddb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000eddb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ed8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ed8d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ed9a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ed9a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edcf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee4c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edcf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee4c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ee55`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ee55`

## pseudocode

```c
bool __fastcall CTabTipEventBase::IsSignaled(CTabTipEventBase *this)
{
  WCHAR *v2; // rbx
  DWORD CurrentProcessId; // eax
  OLECHAR *v5; // rcx
  HANDLE v6; // rax
  __int64 pSessionId; // [rsp+20h] [rbp-78h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-70h] BYREF
  unsigned __int16 v9[40]; // [rsp+30h] [rbp-68h] BYREF

  if ( *((_QWORD *)this + 1) )
    return WaitForSingleObject(*((HANDLE *)this + 1), 0) == 0;
  v2 = 0;
  bstrString = 0;
  if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"Local\\") < 0 )
    goto LABEL_17;
  LODWORD(pSessionId) = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, (DWORD *)&pSessionId);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::GetImpl'::`2'::impl) )
  {
    if ( IsUsingSystemToken() )
      StringCchPrintfW(v9, 0x28u, L"s_%d", (unsigned int)pSessionId, pSessionId);
    else
      StringCchPrintfW(v9, 0x28u, L"u_%d", (unsigned int)pSessionId, pSessionId);
  }
  else
  {
    StringCchPrintfW(v9, 0x28u, L"%d", (unsigned int)pSessionId, pSessionId);
  }
  if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, v9) < 0
    || ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, *((const unsigned __int16 **)this + 2)) < 0 )
  {
LABEL_17:
    v5 = bstrString;
  }
  else
  {
    v2 = bstrString;
    v5 = 0;
  }
  SysFreeString(v5);
  if ( SysStringLen(v2) )
  {
    v6 = OpenEventW(0x100000u, 0, v2);
    *((_QWORD *)this + 1) = v6;
    if ( v6 )
    {
      SysFreeString(v2);
      return WaitForSingleObject(*((HANDLE *)this + 1), 0) == 0;
    }
  }
  SysFreeString(v2);
  return 0;
}

```

## disassembly

```asm
0x18000ed40  mov     [rsp+arg_8], rbx
0x18000ed45  push    rdi
0x18000ed46  sub     rsp, 90h
0x18000ed4d  mov     rax, cs:__security_cookie
0x18000ed54  xor     rax, rsp
0x18000ed57  mov     [rsp+98h+var_18], rax
0x18000ed5f  cmp     qword ptr [rcx+8], 0
0x18000ed64  mov     rdi, rcx
0x18000ed67  jnz     short loc_18000EDD5
0x18000ed69  xor     ebx, ebx
0x18000ed6b  lea     rdx, aLocal_0; "Local\\"
0x18000ed72  lea     rcx, [rsp+98h+bstrString]; this
0x18000ed77  mov     [rsp+98h+bstrString], rbx
0x18000ed7c  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000ed81  test    eax, eax
0x18000ed83  js      loc_18000EEA9
0x18000ed89  mov     dword ptr [rsp+98h+pSessionId], ebx
0x18000ed8d  call    cs:__imp_GetCurrentProcessId
0x18000ed93  mov     ecx, eax; dwProcessId
0x18000ed95  lea     rdx, [rsp+98h+pSessionId]; pSessionId
0x18000ed9a  call    cs:__imp_ProcessIdToSessionId
0x18000eda0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize> `wil::Feature<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::GetImpl(void)'::`2'::impl
0x18000eda7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::__private_IsEnabled(void)
0x18000edac  test    al, al
0x18000edae  jnz     loc_18000EE81
0x18000edb4  mov     r9d, dword ptr [rsp+98h+pSessionId]
0x18000edb9  lea     r8, aD; "%d"
0x18000edc0  mov     edx, 28h ; '('
0x18000edc5  lea     rcx, [rsp+98h+var_68]
0x18000edca  jmp     short loc_18000EE1B
0x18000edcc  mov     rcx, rbx; bstrString
0x18000edcf  call    cs:__imp_SysFreeString
0x18000edd5  mov     rcx, [rdi+8]; hHandle
0x18000edd9  xor     edx, edx; dwMilliseconds
0x18000eddb  call    cs:__imp_WaitForSingleObject
0x18000ede1  test    eax, eax
0x18000ede3  setz    al
0x18000ede6  jmp     short loc_18000EDF3
0x18000ede8  mov     rcx, rbx; bstrString
0x18000edeb  call    cs:__imp_SysFreeString
0x18000edf1  xor     al, al
0x18000edf3  mov     rcx, [rsp+98h+var_18]
0x18000edfb  xor     rcx, rsp; StackCookie
0x18000edfe  call    __security_check_cookie
0x18000ee03  mov     rbx, [rsp+98h+arg_8]
0x18000ee0b  add     rsp, 90h
0x18000ee12  pop     rdi
0x18000ee13  retn
0x18000ee14  lea     r8, aSD_0; "s_%d"
0x18000ee1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ee20  lea     rdx, [rsp+98h+var_68]; unsigned __int16 *
0x18000ee25  lea     rcx, [rsp+98h+bstrString]; this
0x18000ee2a  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000ee2f  test    eax, eax
0x18000ee31  js      short loc_18000EEA9
0x18000ee33  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18000ee37  lea     rcx, [rsp+98h+bstrString]; this
0x18000ee3c  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000ee41  test    eax, eax
0x18000ee43  js      short loc_18000EEA9
0x18000ee45  mov     rbx, [rsp+98h+bstrString]
0x18000ee4a  xor     ecx, ecx; bstrString
0x18000ee4c  call    cs:__imp_SysFreeString
0x18000ee52  mov     rcx, rbx; pbstr
0x18000ee55  call    cs:__imp_SysStringLen
0x18000ee5b  test    eax, eax
0x18000ee5d  jz      short loc_18000EDE8
0x18000ee5f  mov     r8, rbx; lpName
0x18000ee62  xor     edx, edx; bInheritHandle
0x18000ee64  mov     ecx, 100000h; dwDesiredAccess
0x18000ee69  call    cs:__imp_OpenEventW
0x18000ee6f  mov     [rdi+8], rax
0x18000ee73  test    rax, rax
0x18000ee76  jnz     loc_18000EDCC
0x18000ee7c  jmp     loc_18000EDE8
0x18000ee81  call    ?IsUsingSystemToken@@YA_NXZ; IsUsingSystemToken(void)
0x18000ee86  mov     r9d, dword ptr [rsp+98h+pSessionId]
0x18000ee8b  mov     edx, 28h ; '('; unsigned __int64
0x18000ee90  lea     rcx, [rsp+98h+var_68]; unsigned __int16 *
0x18000ee95  test    al, al
0x18000ee97  jnz     loc_18000EE14
0x18000ee9d  lea     r8, aUD; "u_%d"
0x18000eea4  jmp     loc_18000EE1B
0x18000eea9  mov     rcx, [rsp+98h+bstrString]
0x18000eeae  jmp     short loc_18000EE4C
```
