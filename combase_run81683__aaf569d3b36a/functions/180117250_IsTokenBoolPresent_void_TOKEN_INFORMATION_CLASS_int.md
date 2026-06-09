# IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)

- ea: `0x180117250`
- end: `0x1801173db`
- name: `?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z`
- size: `395`
- prototype: `HRESULT __fastcall(void *hToken, _TOKEN_INFORMATION_CLASS type, int *isPresent)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180076b34`
- `0x180076d30`
- `0x180076d88`
- `0x180141d28`

## callees

- `0x18005cde8`
- `0x18005ce60`
- `0x180087660`
- `0x18008db2c`
- `0x180117250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801172bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801172bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117347`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801173b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801173b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801172a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801172a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801172b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801172b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18011733d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18011733d`

## string_xrefs

- `0x18011730b`: `onecore\com\combase\common\internal\tokenproperties.cpp`
- `0x180117393`: `onecore\com\combase\common\internal\tokenproperties.cpp`
- `0x1801172ff`: `IsTokenBoolPresent`
- `0x180117387`: `IsTokenBoolPresent`

## pseudocode

```c
HRESULT __fastcall IsTokenBoolPresent(void *hToken, _TOKEN_INFORMATION_CLASS type, int *isPresent)
{
  HRESULT v3; // ebx
  HRESULT result; // eax
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  void *v9; // rcx
  signed int LastError; // eax
  void *hImpersonationToken; // [rsp+30h] [rbp-10h] BYREF
  unsigned int tokenBoolValue; // [rsp+60h] [rbp+20h] BYREF
  unsigned int size; // [rsp+70h] [rbp+30h] BYREF
  void *hLocalProcessToken; // [rsp+78h] [rbp+38h] BYREF

  v3 = 0;
  hImpersonationToken = 0;
  hLocalProcessToken = 0;
  tokenBoolValue = 0;
  size = 0;
  *isPresent = 0;
  if ( hToken )
  {
LABEL_12:
    if ( GetTokenInformation(hToken, type, &tokenBoolValue, 4u, &size) )
    {
      *isPresent = tokenBoolValue != 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\common\\internal\\tokenproperties.cpp",
          "IsTokenBoolPresent",
          58,
          ERRORS,
          L"hr:%!HRESULT!",
          v3);
    }
    if ( hLocalProcessToken )
      CloseHandle(hLocalProcessToken);
    v9 = hImpersonationToken;
    if ( !hImpersonationToken )
      return v3;
    goto LABEL_23;
  }
  result = SuspendImpersonate(&hImpersonationToken);
  v3 = result;
  if ( result < 0 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &hLocalProcessToken) )
  {
    hToken = hLocalProcessToken;
    goto LABEL_12;
  }
  v8 = GetLastError();
  v3 = v8;
  if ( v8 > 0 )
    v3 = (unsigned __int16)v8 | 0x80070000;
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    ComTraceMessageT<long>(
      "onecore\\com\\combase\\common\\internal\\tokenproperties.cpp",
      "IsTokenBoolPresent",
      42,
      ERRORS,
      L"hr:%!HRESULT!",
      v3);
  v9 = hImpersonationToken;
LABEL_23:
  ResumeImpersonate(v9);
  return v3;
}

```

## disassembly

```asm
0x180117250  mov     [rsp-18h+arg_8], rbx
0x180117255  push    rbp
0x180117256  push    rsi
0x180117257  push    rdi
0x180117258  mov     rbp, rsp
0x18011725b  sub     rsp, 40h
0x18011725f  xor     ebx, ebx
0x180117261  mov     [rbp+hImpersonationToken], 0
0x180117269  mov     [rbp+hLocalProcessToken], 0
0x180117271  mov     rdi, isPresent
0x180117274  mov     [rbp+tokenBoolValue], 0
0x18011727b  mov     esi, type
0x18011727d  mov     [rbp+size], 0
0x180117284  mov     [isPresent], ebx
0x180117287  test    hToken, hToken
0x18011728a  jnz     loc_180117328
0x180117290  lea     hToken, [rbp+hImpersonationToken]; pHandle
0x180117294  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180117299  mov     ebx, eax
0x18011729b  test    eax, eax
0x18011729d  js      loc_1801173CE
0x1801172a3  call    cs:__imp_GetCurrentProcess
0x1801172a9  lea     isPresent, [rbp+hLocalProcessToken]; TokenHandle
0x1801172ad  mov     type, 8; DesiredAccess
0x1801172b2  mov     hToken, rax; ProcessHandle
0x1801172b5  call    cs:__imp_OpenProcessToken
0x1801172bb  test    eax, eax
0x1801172bd  jnz     short loc_180117324
0x1801172bf  call    cs:__imp_GetLastError
0x1801172c5  mov     ebx, eax
0x1801172c7  test    eax, eax
0x1801172c9  jle     short loc_1801172D4
0x1801172cb  movzx   ebx, ax
0x1801172ce  or      ebx, 80070000h
0x1801172d4  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801172da  test    eax, eax
0x1801172dc  jnz     short loc_1801172F1
0x1801172de  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801172e4  jz      short loc_18011731B
0x1801172e6  xor     ecx, ecx; level
0x1801172e8  call    IsWppLevelEnabled
0x1801172ed  test    al, al
0x1801172ef  jz      short loc_18011731B
0x1801172f1  xor     r9d, r9d; level
0x1801172f4  mov     [rsp+40h+var_18], ebx; <args_0>
0x1801172f8  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x1801172ff  lea     rdx, aIstokenboolpre; "IsTokenBoolPresent"
0x180117306  mov     [rsp+40h+format], rax; format
0x18011730b  lea     hToken, aOnecoreComComb_24; "onecore\\com\\combase\\common\\internal"...
0x180117312  lea     r8d, [r9+2Ah]; line
0x180117316  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18011731b  mov     hToken, [rbp+hImpersonationToken]
0x18011731f  jmp     loc_1801173C7
0x180117324  mov     hToken, [rbp+hLocalProcessToken]; TokenHandle
0x180117328  lea     rax, [rbp+size]
0x18011732c  mov     r9d, 4; TokenInformationLength
0x180117332  lea     isPresent, [rbp+tokenBoolValue]; TokenInformation
0x180117336  mov     [rsp+40h+format], rax; ReturnLength
0x18011733b  mov     type, esi; TokenInformationClass
0x18011733d  call    cs:__imp_GetTokenInformation
0x180117343  test    eax, eax
0x180117345  jnz     short loc_1801173A5
0x180117347  call    cs:__imp_GetLastError
0x18011734d  mov     ebx, eax
0x18011734f  test    eax, eax
0x180117351  jle     short loc_18011735C
0x180117353  movzx   ebx, ax
0x180117356  or      ebx, 80070000h
0x18011735c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180117362  test    eax, eax
0x180117364  jnz     short loc_180117379
0x180117366  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18011736c  jz      short loc_1801173AF
0x18011736e  xor     ecx, ecx; level
0x180117370  call    IsWppLevelEnabled
0x180117375  test    al, al
0x180117377  jz      short loc_1801173AF
0x180117379  xor     r9d, r9d; level
0x18011737c  mov     [rsp+40h+var_18], ebx; <args_0>
0x180117380  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x180117387  lea     rdx, aIstokenboolpre; "IsTokenBoolPresent"
0x18011738e  mov     [rsp+40h+format], rax; format
0x180117393  lea     hToken, aOnecoreComComb_24; "onecore\\com\\combase\\common\\internal"...
0x18011739a  lea     r8d, [r9+3Ah]; line
0x18011739e  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1801173a3  jmp     short loc_1801173AF
0x1801173a5  xor     eax, eax
0x1801173a7  cmp     [rbp+tokenBoolValue], eax
0x1801173aa  setnz   al
0x1801173ad  mov     [rdi], eax
0x1801173af  mov     hToken, [rbp+hLocalProcessToken]; hObject
0x1801173b3  test    hToken, hToken
0x1801173b6  jz      short loc_1801173BE
0x1801173b8  call    cs:__imp_CloseHandle
0x1801173be  mov     hToken, [rbp+hImpersonationToken]; hToken
0x1801173c2  test    hToken, hToken
0x1801173c5  jz      short loc_1801173CC
0x1801173c7  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1801173cc  mov     eax, ebx
0x1801173ce  mov     rbx, [rsp+40h+arg_8]
0x1801173d3  add     rsp, 40h
0x1801173d7  pop     rdi
0x1801173d8  pop     rsi
0x1801173d9  pop     rbp
0x1801173da  retn
```
