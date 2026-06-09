# GetCurrentToken(void * *)

- ea: `0x1801c6db4`
- end: `0x1801c6f4e`
- name: `?GetCurrentToken@@YAJPEAPEAX@Z`
- size: `410`
- prototype: `HRESULT __fastcall(void **phToken)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801c6f60`
- `0x1801c7170`

## callees

- `0x180087660`
- `0x18008db2c`
- `0x1801c6db4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c6df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c6e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c6e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c6df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c6e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c6e90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c6e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c6e81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801c6e05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801c6e05`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801c6e16`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801c6e16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801c6dd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801c6dd1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801c6de6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801c6de6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1801c6e74`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1801c6e74`

## string_xrefs

- `0x1801c6f1d`: `GetCurrentToken`
- `0x1801c6f24`: `onecore\com\combase\dcomrem\globalopt.cxx`

## pseudocode

```c
__int64 __fastcall GetCurrentToken(void **phToken)
{
  HRESULT v1; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v6; // eax
  int v7; // r8d
  BOOL v8; // ebx
  signed int v9; // eax
  void *hToken; // [rsp+48h] [rbp+10h] BYREF
  void *hDup; // [rsp+50h] [rbp+18h] BYREF

  v1 = 0;
  hToken = 0;
  hDup = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &hToken) )
    goto LABEL_27;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xEu, &hToken) )
    {
      v8 = DuplicateToken(hToken, SecurityImpersonation, &hDup);
      CloseHandle(hToken);
      hToken = 0;
      if ( v8 )
      {
        hToken = hDup;
        goto LABEL_26;
      }
      v9 = GetLastError();
      v1 = v9;
      if ( v9 > 0 )
        v1 = (unsigned __int16)v9 | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      {
        v7 = 102;
        goto LABEL_25;
      }
    }
    else
    {
      v6 = GetLastError();
      v1 = v6;
      if ( v6 > 0 )
        v1 = (unsigned __int16)v6 | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      {
        v7 = 91;
LABEL_25:
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\dcomrem\\globalopt.cxx",
          "GetCurrentToken",
          v7,
          ERRORS,
          L"%!HRESULT!",
          v1);
      }
    }
  }
  else
  {
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    else
      v1 = LastError;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      v7 = 114;
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( v1 >= 0 )
LABEL_27:
    *phToken = hToken;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1801c6db4  mov     rax, rsp
0x1801c6db7  mov     [rax+8], rbx
0x1801c6dbb  mov     [rax+20h], rsi
0x1801c6dbf  push    rdi
0x1801c6dc0  sub     rsp, 30h
0x1801c6dc4  xor     edi, edi
0x1801c6dc6  mov     rsi, phToken
0x1801c6dc9  mov     [rax+10h], rdi
0x1801c6dcd  mov     [rax+18h], rdi
0x1801c6dd1  call    cs:__imp_GetCurrentThread
0x1801c6dd7  mov     phToken, rax; ThreadHandle
0x1801c6dda  lea     r9, [rsp+38h+hToken]; TokenHandle
0x1801c6ddf  lea     edx, [rdi+0Ch]; DesiredAccess
0x1801c6de2  lea     r8d, [rdi+1]; OpenAsSelf
0x1801c6de6  call    cs:__imp_OpenThreadToken
0x1801c6dec  test    eax, eax
0x1801c6dee  jnz     loc_1801C6F34
0x1801c6df4  call    cs:__imp_GetLastError
0x1801c6dfa  cmp     eax, 3F0h
0x1801c6dff  jnz     loc_1801C6ED6
0x1801c6e05  call    cs:__imp_GetCurrentProcess
0x1801c6e0b  mov     phToken, rax; ProcessHandle
0x1801c6e0e  lea     r8, [rsp+38h+hToken]; TokenHandle
0x1801c6e13  lea     edx, [rdi+0Eh]; DesiredAccess
0x1801c6e16  call    cs:__imp_OpenProcessToken
0x1801c6e1c  test    eax, eax
0x1801c6e1e  jnz     short loc_1801C6E65
0x1801c6e20  call    cs:__imp_GetLastError
0x1801c6e26  mov     edi, eax
0x1801c6e28  test    eax, eax
0x1801c6e2a  jle     short loc_1801C6E35
0x1801c6e2c  movzx   edi, ax
0x1801c6e2f  or      edi, 80070000h
0x1801c6e35  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801c6e3b  test    eax, eax
0x1801c6e3d  jnz     short loc_1801C6E5A
0x1801c6e3f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801c6e45  jz      loc_1801C6F30
0x1801c6e4b  xor     ecx, ecx; level
0x1801c6e4d  call    IsWppLevelEnabled
0x1801c6e52  test    al, al
0x1801c6e54  jz      loc_1801C6F30
0x1801c6e5a  mov     r8d, 5Bh ; '['
0x1801c6e60  jmp     loc_1801C6F0A
0x1801c6e65  mov     phToken, [rsp+38h+hToken]; ExistingTokenHandle
0x1801c6e6a  lea     r8, [rsp+38h+hDup]; DuplicateTokenHandle
0x1801c6e6f  mov     edx, 2; ImpersonationLevel
0x1801c6e74  call    cs:__imp_DuplicateToken
0x1801c6e7a  mov     phToken, [rsp+38h+hToken]; hObject
0x1801c6e7f  mov     ebx, eax
0x1801c6e81  call    cs:__imp_CloseHandle
0x1801c6e87  mov     [rsp+38h+hToken], rdi
0x1801c6e8c  test    ebx, ebx
0x1801c6e8e  jnz     short loc_1801C6ECA
0x1801c6e90  call    cs:__imp_GetLastError
0x1801c6e96  mov     edi, eax
0x1801c6e98  test    eax, eax
0x1801c6e9a  jle     short loc_1801C6EA5
0x1801c6e9c  movzx   edi, ax
0x1801c6e9f  or      edi, 80070000h
0x1801c6ea5  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801c6eab  test    eax, eax
0x1801c6ead  jnz     short loc_1801C6EC2
0x1801c6eaf  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801c6eb5  jz      short loc_1801C6F30
0x1801c6eb7  xor     ecx, ecx; level
0x1801c6eb9  call    IsWppLevelEnabled
0x1801c6ebe  test    al, al
0x1801c6ec0  jz      short loc_1801C6F30
0x1801c6ec2  mov     r8d, 66h ; 'f'
0x1801c6ec8  jmp     short loc_1801C6F0A
0x1801c6eca  mov     rax, [rsp+38h+hDup]
0x1801c6ecf  mov     [rsp+38h+hToken], rax
0x1801c6ed4  jmp     short loc_1801C6F30
0x1801c6ed6  test    eax, eax
0x1801c6ed8  jg      short loc_1801C6EDE
0x1801c6eda  mov     edi, eax
0x1801c6edc  jmp     short loc_1801C6EE7
0x1801c6ede  movzx   edi, ax
0x1801c6ee1  or      edi, 80070000h
0x1801c6ee7  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801c6eed  test    eax, eax
0x1801c6eef  jnz     short loc_1801C6F04
0x1801c6ef1  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801c6ef7  jz      short loc_1801C6F30
0x1801c6ef9  xor     ecx, ecx; level
0x1801c6efb  call    IsWppLevelEnabled
0x1801c6f00  test    al, al
0x1801c6f02  jz      short loc_1801C6F30
0x1801c6f04  mov     r8d, 72h ; 'r'; line
0x1801c6f0a  lea     rax, aHresult; "%!HRESULT!"
0x1801c6f11  mov     [rsp+38h+var_10], edi; <args_0>
0x1801c6f15  xor     r9d, r9d; level
0x1801c6f18  mov     [rsp+38h+format], rax; format
0x1801c6f1d  lea     rdx, aGetcurrenttoke; "GetCurrentToken"
0x1801c6f24  lea     phToken, aOnecoreComComb_132; "onecore\\com\\combase\\dcomrem\\globalo"...
0x1801c6f2b  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1801c6f30  test    edi, edi
0x1801c6f32  js      short loc_1801C6F3C
0x1801c6f34  mov     phToken, [rsp+38h+hToken]
0x1801c6f39  mov     [rsi], phToken
0x1801c6f3c  mov     rbx, [rsp+38h+arg_0]
0x1801c6f41  mov     eax, edi
0x1801c6f43  mov     rsi, [rsp+38h+arg_18]
0x1801c6f48  add     rsp, 30h
0x1801c6f4c  pop     rdi
0x1801c6f4d  retn
```
