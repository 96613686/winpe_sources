# IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)

- ea: `0x18001e25c`
- end: `0x18001e404`
- name: `?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z`
- size: `424`
- prototype: `HRESULT __fastcall(void *hToken, _TOKEN_INFORMATION_CLASS isPresent, int *hToken)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e150`
- `0x18001e230`
- `0x1800404b0`
- `0x1800cd9d4`

## callees

- `0x18001e25c`
- `0x18001e40c`
- `0x180045504`
- `0x18004d474`
- `0x180087068`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e396`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e313`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e2fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e2fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e2c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e2c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e2a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e2a0`

## string_xrefs

- `0x18001e37a`: `IsTokenBoolPresent`
- `0x18001e3ec`: `IsTokenBoolPresent`
- `0x18001e381`: `onecore\com\combase\common\internal\processtoken.cxx`
- `0x18001e3f3`: `onecore\com\combase\common\internal\processtoken.cxx`

## pseudocode

```c
HRESULT __fastcall IsTokenBoolPresent(void *hToken, _TOKEN_INFORMATION_CLASS isPresent, int *a3)
{
  HRESULT file; // ebx
  void *v5; // rcx
  HRESULT result; // eax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  TraceLevel v9; // r9d
  signed int v10; // eax
  TraceLevel v11; // r9d
  unsigned int size; // [rsp+50h] [rbp+20h] BYREF
  unsigned int tokenBoolValue; // [rsp+58h] [rbp+28h] BYREF
  void *hLocalProcessToken; // [rsp+60h] [rbp+30h] BYREF
  void *hImpersonationToken; // [rsp+68h] [rbp+38h] BYREF

  hImpersonationToken = 0;
  file = 0;
  *a3 = 0;
  hLocalProcessToken = 0;
  tokenBoolValue = 0;
  size = 0;
  if ( hToken )
    goto LABEL_2;
  result = SuspendImpersonate(&hImpersonationToken);
  file = result;
  if ( result >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &hLocalProcessToken) )
    {
      LastError = GetLastError();
      file = LastError;
      if ( LastError > 0 )
        file = (unsigned __int16)LastError | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\common\\internal\\processtoken.cxx",
          "IsTokenBoolPresent",
          88,
          v9,
          L"hr:%!HRESULT!",
          file);
      v5 = hImpersonationToken;
LABEL_7:
      ResumeImpersonate(v5);
      return file;
    }
    hToken = hLocalProcessToken;
LABEL_2:
    if ( GetTokenInformation(hToken, TokenIsAppContainer, &tokenBoolValue, 4u, &size) )
    {
      *a3 = tokenBoolValue != 0;
    }
    else
    {
      v10 = GetLastError();
      file = v10;
      if ( v10 > 0 )
        file = (unsigned __int16)v10 | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\common\\internal\\processtoken.cxx",
          "IsTokenBoolPresent",
          104,
          v11,
          L"hr:%!HRESULT!",
          file);
    }
    if ( hLocalProcessToken )
      CloseHandle(hLocalProcessToken);
    v5 = hImpersonationToken;
    if ( !hImpersonationToken )
      return file;
    goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x18001e25c  mov     [rsp-18h+tokenBoolValue], edx
0x18001e260  push    rbp
0x18001e261  push    rbx
0x18001e262  push    rdi
0x18001e263  mov     rbp, rsp
0x18001e266  sub     rsp, 30h
0x18001e26a  and     [rbp+hImpersonationToken], 0
0x18001e26f  xor     ebx, ebx
0x18001e271  and     [isPresent], ebx
0x18001e274  mov     rdi, isPresent
0x18001e277  and     [rbp+hLocalProcessToken], 0
0x18001e27c  and     [rbp+tokenBoolValue], 0
0x18001e280  and     [rbp+size], 0
0x18001e284  test    hToken, hToken
0x18001e287  jz      short loc_18001E2EC
0x18001e289  mov     r9d, 4; TokenInformationLength
0x18001e28f  lea     rax, [rbp+size]
0x18001e293  lea     isPresent, [rbp+tokenBoolValue]; TokenInformation
0x18001e297  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001e29c  lea     edx, [r9+19h]; TokenInformationClass
0x18001e2a0  call    cs:__imp_GetTokenInformation
0x18001e2a7  nop     dword ptr [rax+rax+00h]
0x18001e2ac  test    eax, eax
0x18001e2ae  jz      loc_18001E396
0x18001e2b4  xor     eax, eax
0x18001e2b6  cmp     [rbp+tokenBoolValue], eax
0x18001e2b9  setnz   al
0x18001e2bc  mov     [rdi], eax
0x18001e2be  mov     hToken, [rbp+hLocalProcessToken]; hObject
0x18001e2c2  test    hToken, hToken
0x18001e2c5  jz      short loc_18001E2D3
0x18001e2c7  call    cs:__imp_CloseHandle
0x18001e2ce  nop     dword ptr [rax+rax+00h]
0x18001e2d3  mov     hToken, [rbp+hImpersonationToken]; hToken
0x18001e2d7  test    hToken, hToken
0x18001e2da  jz      short loc_18001E2E1
0x18001e2dc  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x18001e2e1  mov     eax, ebx
0x18001e2e3  add     rsp, 30h
0x18001e2e7  pop     rdi
0x18001e2e8  pop     rbx
0x18001e2e9  pop     rbp
0x18001e2ea  retn
0x18001e2ec  lea     hToken, [rbp+hImpersonationToken]; pHandle
0x18001e2f0  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x18001e2f5  mov     ebx, eax
0x18001e2f7  test    eax, eax
0x18001e2f9  js      short loc_18001E2E3
0x18001e2fb  call    cs:__imp_GetCurrentProcess
0x18001e302  nop     dword ptr [rax+rax+00h]
0x18001e307  lea     isPresent, [rbp+hLocalProcessToken]; TokenHandle
0x18001e30b  mov     edx, 8; DesiredAccess
0x18001e310  mov     hToken, rax; ProcessHandle
0x18001e313  call    cs:__imp_OpenProcessToken
0x18001e31a  nop     dword ptr [rax+rax+00h]
0x18001e31f  test    eax, eax
0x18001e321  jz      short loc_18001E32C
0x18001e323  mov     hToken, [rbp+hLocalProcessToken]
0x18001e327  jmp     loc_18001E289
0x18001e32c  call    cs:__imp_GetLastError
0x18001e333  nop     dword ptr [rax+rax+00h]
0x18001e338  mov     ebx, eax
0x18001e33a  test    eax, eax
0x18001e33c  jle     short loc_18001E347
0x18001e33e  movzx   ebx, ax
0x18001e341  or      ebx, 80070000h
0x18001e347  cmp     cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1, 0
0x18001e34e  ja      short loc_18001E364
0x18001e350  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18001e357  jz      short loc_18001E38D
0x18001e359  xor     ecx, ecx; level
0x18001e35b  call    IsWppLevelEnabled
0x18001e360  test    al, al
0x18001e362  jz      short loc_18001E38D
0x18001e364  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x18001e36b  mov     [rsp+30h+file], ebx; file
0x18001e36f  mov     r8d, 58h ; 'X'; line
0x18001e375  mov     [rsp+30h+ReturnLength], rax; <args_0>
0x18001e37a  lea     rdx, aIstokenboolpre; "IsTokenBoolPresent"
0x18001e381  lea     hToken, aOnecoreComComb_1; "onecore\\com\\combase\\common\\internal"...
0x18001e388  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18001e38d  mov     hToken, [rbp+hImpersonationToken]
0x18001e391  jmp     loc_18001E2DC
0x18001e396  call    cs:__imp_GetLastError
0x18001e39d  nop     dword ptr [rax+rax+00h]
0x18001e3a2  mov     ebx, eax
0x18001e3a4  test    eax, eax
0x18001e3a6  jle     short loc_18001E3B1
0x18001e3a8  movzx   ebx, ax
0x18001e3ab  or      ebx, 80070000h
0x18001e3b1  cmp     cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1, 0
0x18001e3b8  ja      short loc_18001E3D6
0x18001e3ba  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18001e3c1  jz      loc_18001E2BE
0x18001e3c7  xor     ecx, ecx; level
0x18001e3c9  call    IsWppLevelEnabled
0x18001e3ce  test    al, al
0x18001e3d0  jz      loc_18001E2BE
0x18001e3d6  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x18001e3dd  mov     [rsp+30h+file], ebx; file
0x18001e3e1  mov     r8d, 68h ; 'h'; line
0x18001e3e7  mov     [rsp+30h+ReturnLength], rax; <args_0>
0x18001e3ec  lea     rdx, aIstokenboolpre; "IsTokenBoolPresent"
0x18001e3f3  lea     hToken, aOnecoreComComb_1; "onecore\\com\\combase\\common\\internal"...
0x18001e3fa  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18001e3ff  jmp     loc_18001E2BE
```
