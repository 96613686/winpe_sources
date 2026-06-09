# IkeInitAnonymousToken

- ea: `0x180055378`
- end: `0x180055439`
- name: `IkeInitAnonymousToken`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054bf4`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180055378`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800553e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800553e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180055393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800553cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180055393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800553cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553f0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005540c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005540c`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18005539c`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18005539c`

## string_xrefs

- `0x180055387`: `IkeInitAnonymousToken`
- `0x180055414`: `IkeInitAnonymousToken`
- `0x180055420`: `IkeInitAnonymousToken`
- `0x1800553b2`: `ImpersonateAnonymousToken`
- `0x1800553fd`: `ImpersonateAnonymousToken`

## pseudocode

```c
__int64 IkeInitAnonymousToken()
{
  HANDLE CurrentThread; // rax
  DWORD v1; // eax
  __int64 v2; // rcx
  __int64 v3; // rdi
  LPCRITICAL_SECTION v4; // rbx
  HANDLE v5; // rax
  DWORD LastError; // eax
  __int64 v7; // rcx

  TraceLogHelper("IkeInitAnonymousToken", 1);
  CurrentThread = GetCurrentThread();
  if ( ImpersonateAnonymousToken(CurrentThread) )
  {
    v4 = gIkeExtGlobals;
    v3 = 0;
    v5 = GetCurrentThread();
    if ( !OpenThreadToken(v5, 0xAu, 1, &v4[86].OwningThread) )
    {
      LastError = GetLastError();
      v3 = WfpReportSysErrorAsWinError(v7, "ImpersonateAnonymousToken", LastError, 1);
    }
    RevertToSelf();
  }
  else
  {
    v1 = GetLastError();
    v3 = WfpReportSysErrorAsWinError(v2, "ImpersonateAnonymousToken", v1, 1);
  }
  TraceLogHelper("IkeInitAnonymousToken", 0);
  return IkeReturnError(v3, "IkeInitAnonymousToken");
}

```

## disassembly

```asm
0x180055378  mov     [rsp+arg_0], rbx
0x18005537d  push    rdi
0x18005537e  sub     rsp, 20h
0x180055382  mov     edx, 1
0x180055387  lea     rcx, aIkeinitanonymo; "IkeInitAnonymousToken"
0x18005538e  call    TraceLogHelper
0x180055393  call    cs:__imp_GetCurrentThread
0x180055399  mov     rcx, rax; ThreadHandle
0x18005539c  call    cs:__imp_ImpersonateAnonymousToken
0x1800553a2  test    eax, eax
0x1800553a4  jnz     short loc_1800553C6
0x1800553a6  call    cs:__imp_GetLastError
0x1800553ac  mov     r9d, 1
0x1800553b2  lea     rdx, aImpersonateano; "ImpersonateAnonymousToken"
0x1800553b9  mov     r8d, eax
0x1800553bc  call    WfpReportSysErrorAsWinError
0x1800553c1  mov     rdi, rax
0x1800553c4  jmp     short loc_180055412
0x1800553c6  mov     rbx, cs:gIkeExtGlobals
0x1800553cd  xor     edi, edi
0x1800553cf  call    cs:__imp_GetCurrentThread
0x1800553d5  mov     rcx, rax; ThreadHandle
0x1800553d8  lea     r9, [rbx+0D80h]; TokenHandle
0x1800553df  lea     edx, [rdi+0Ah]; DesiredAccess
0x1800553e2  lea     r8d, [rdi+1]; OpenAsSelf
0x1800553e6  call    cs:__imp_OpenThreadToken
0x1800553ec  test    eax, eax
0x1800553ee  jnz     short loc_18005540C
0x1800553f0  call    cs:__imp_GetLastError
0x1800553f6  mov     r8d, eax
0x1800553f9  lea     r9d, [rdi+1]
0x1800553fd  lea     rdx, aImpersonateano; "ImpersonateAnonymousToken"
0x180055404  call    WfpReportSysErrorAsWinError
0x180055409  mov     rdi, rax
0x18005540c  call    cs:__imp_RevertToSelf
0x180055412  xor     edx, edx
0x180055414  lea     rcx, aIkeinitanonymo; "IkeInitAnonymousToken"
0x18005541b  call    TraceLogHelper
0x180055420  lea     rdx, aIkeinitanonymo; "IkeInitAnonymousToken"
0x180055427  mov     rcx, rdi
0x18005542a  mov     rbx, [rsp+28h+arg_0]
0x18005542f  add     rsp, 20h
0x180055433  pop     rdi
0x180055434  jmp     IkeReturnError
```
