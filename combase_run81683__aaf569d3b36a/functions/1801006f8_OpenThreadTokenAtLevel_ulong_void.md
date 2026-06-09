# OpenThreadTokenAtLevel(ulong,void * *)

- ea: `0x1801006f8`
- end: `0x18010087a`
- name: `?OpenThreadTokenAtLevel@@YAJKPEAPEAX@Z`
- size: `386`
- prototype: `HRESULT __fastcall(unsigned int lImpReq, void **pToken)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801003d4`
- `0x18015bd0c`

## callees

- `0x18008db2c`
- `0x1801006f8`
- `0x1801457c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801007fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801007fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801007f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801007f2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180100781`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801007e4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180100781`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801007e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180100738`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010075a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180100738`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010075a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180100750`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010076d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180100750`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010076d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1801007d6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1801007d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010079f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010079f`

## string_xrefs

- `0x180100848`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180100841`: `OpenThreadTokenAtLevel`

## pseudocode

```c
__int64 __fastcall OpenThreadTokenAtLevel(unsigned int lImpReq, void **pToken)
{
  SECURITY_IMPERSONATION_LEVEL v4; // r12d
  HANDLE CurrentThread; // rax
  int v6; // ebx
  HANDLE v7; // rax
  unsigned int v8; // edi
  BOOL TokenInformation; // esi
  signed int LastError; // ebx
  unsigned int lImpTok; // [rsp+70h] [rbp+40h] BYREF
  unsigned int lIgnore; // [rsp+78h] [rbp+48h] BYREF
  void *hThread; // [rsp+80h] [rbp+50h] BYREF

  hThread = 0;
  lImpTok = 0;
  lIgnore = 0;
  v4 = ImpLevelToSecLevel[lImpReq];
  *pToken = 0;
  CurrentThread = GetCurrentThread();
  v6 = 1;
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &hThread)
    || (v7 = GetCurrentThread(), OpenThreadToken(v7, 0xCu, 1, &hThread)) )
  {
    v8 = 0;
    SetThreadToken(0, 0);
    TokenInformation = GetTokenInformation(hThread, TokenImpersonationLevel, &lImpTok, 4u, &lIgnore);
    if ( TokenInformation )
    {
      if ( lImpTok >= 2 )
      {
        if ( lImpTok + 1 > lImpReq )
        {
          TokenInformation = DuplicateToken(hThread, v4, pToken);
        }
        else
        {
          v6 = 0;
          *pToken = hThread;
        }
      }
      else
      {
        v8 = -2147417829;
      }
    }
    SetThreadToken(0, hThread);
    if ( v6 )
      CloseHandle(hThread);
    if ( TokenInformation )
      return v8;
  }
  LastError = GetLastError();
  if ( LastError == 1008 )
    return 0;
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    ComTraceMessageT<unsigned int>(
      "onecore\\com\\combase\\dcomrem\\security.cxx",
      "OpenThreadTokenAtLevel",
      6551,
      ERRORS,
      L"%!WINERROR!",
      LastError);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1801006f8  push    rbp
0x1801006fa  push    rbx
0x1801006fb  push    rsi
0x1801006fc  push    rdi
0x1801006fd  push    r12
0x1801006ff  push    r14
0x180100701  push    r15
0x180100703  mov     rbp, rsp
0x180100706  sub     rsp, 30h
0x18010070a  mov     r15d, lImpReq
0x18010070d  lea     r12, ImpLevelToSecLevel
0x180100714  mov     r14, pToken
0x180100717  mov     [rbp+hThread], 0
0x18010071f  mov     [rbp+lImpTok], 0
0x180100726  mov     [rbp+lIgnore], 0
0x18010072d  mov     r12d, [r12+r15*4]
0x180100731  mov     qword ptr [pToken], 0
0x180100738  call    cs:__imp_GetCurrentThread
0x18010073e  mov     ebx, 1
0x180100743  lea     r9, [rbp+hThread]; TokenHandle
0x180100747  mov     rcx, rax; ThreadHandle
0x18010074a  mov     r8d, ebx; OpenAsSelf
0x18010074d  lea     edx, [rbx+0Dh]; DesiredAccess
0x180100750  call    cs:__imp_OpenThreadToken
0x180100756  test    eax, eax
0x180100758  jnz     short loc_18010077B
0x18010075a  call    cs:__imp_GetCurrentThread
0x180100760  lea     r9, [rbp+hThread]; TokenHandle
0x180100764  mov     r8d, ebx; OpenAsSelf
0x180100767  mov     rcx, rax; ThreadHandle
0x18010076a  lea     edx, [rbx+0Bh]; DesiredAccess
0x18010076d  call    cs:__imp_OpenThreadToken
0x180100773  test    eax, eax
0x180100775  jz      loc_1801007FC
0x18010077b  xor     edx, edx; Token
0x18010077d  xor     lImpReq, lImpReq; Thread
0x18010077f  xor     edi, edi
0x180100781  call    cs:__imp_SetThreadToken
0x180100787  mov     rcx, [rbp+hThread]; TokenHandle
0x18010078b  lea     rax, [rbp+lIgnore]
0x18010078f  lea     r9d, [rdi+4]; TokenInformationLength
0x180100793  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180100798  lea     r8, [rbp+lImpTok]; TokenInformation
0x18010079c  lea     edx, [rdi+9]; TokenInformationClass
0x18010079f  call    cs:__imp_GetTokenInformation
0x1801007a5  mov     esi, eax
0x1801007a7  test    eax, eax
0x1801007a9  jz      short loc_1801007DE
0x1801007ab  mov     eax, [rbp+lImpTok]
0x1801007ae  cmp     eax, 2
0x1801007b1  jnb     short loc_1801007BA
0x1801007b3  mov     edi, 8001011Bh
0x1801007b8  jmp     short loc_1801007DE
0x1801007ba  inc     eax
0x1801007bc  cmp     eax, r15d
0x1801007bf  ja      short loc_1801007CC
0x1801007c1  mov     rax, [rbp+hThread]
0x1801007c5  xor     ebx, ebx
0x1801007c7  mov     [r14], rax
0x1801007ca  jmp     short loc_1801007DE
0x1801007cc  mov     rcx, [rbp+hThread]; ExistingTokenHandle
0x1801007d0  mov     r8, r14; DuplicateTokenHandle
0x1801007d3  mov     edx, r12d; ImpersonationLevel
0x1801007d6  call    cs:__imp_DuplicateToken
0x1801007dc  mov     esi, eax
0x1801007de  mov     pToken, [rbp+hThread]; Token
0x1801007e2  xor     lImpReq, lImpReq; Thread
0x1801007e4  call    cs:__imp_SetThreadToken
0x1801007ea  test    ebx, ebx
0x1801007ec  jz      short loc_1801007F8
0x1801007ee  mov     rcx, [rbp+hThread]; hObject
0x1801007f2  call    cs:__imp_CloseHandle
0x1801007f8  test    esi, esi
0x1801007fa  jnz     short loc_180100869
0x1801007fc  call    cs:__imp_GetLastError
0x180100802  mov     ebx, eax
0x180100804  cmp     eax, 3F0h
0x180100809  jz      short loc_180100865
0x18010080b  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180100811  test    eax, eax
0x180100813  jnz     short loc_180100828
0x180100815  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18010081b  jz      short loc_180100854
0x18010081d  xor     lImpReq, lImpReq; level
0x18010081f  call    IsWppLevelEnabled
0x180100824  test    al, al
0x180100826  jz      short loc_180100854
0x180100828  lea     rax, aWinerror; "%!WINERROR!"
0x18010082f  mov     [rsp+30h+var_8], ebx; <args_0>
0x180100833  xor     r9d, r9d; level
0x180100836  mov     [rsp+30h+ReturnLength], rax; format
0x18010083b  mov     r8d, 1997h; line
0x180100841  lea     pToken, aOpenthreadtoke; "OpenThreadTokenAtLevel"
0x180100848  lea     rcx, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18010084f  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x180100854  test    ebx, ebx
0x180100856  jle     short loc_180100861
0x180100858  movzx   ebx, bx
0x18010085b  or      ebx, 80070000h
0x180100861  mov     eax, ebx
0x180100863  jmp     short loc_18010086B
0x180100865  xor     eax, eax
0x180100867  jmp     short loc_18010086B
0x180100869  mov     eax, edi
0x18010086b  add     rsp, 30h
0x18010086f  pop     r15
0x180100871  pop     r14
0x180100873  pop     r12
0x180100875  pop     rdi
0x180100876  pop     rsi
0x180100877  pop     rbx
0x180100878  pop     rbp
0x180100879  retn
```
