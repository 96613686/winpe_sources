# VerifyClientMembership(WELL_KNOWN_SID_TYPE)

- ea: `0x180027cd8`
- end: `0x180027de7`
- name: `?VerifyClientMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(enum WELL_KNOWN_SID_TYPE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025d78`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180025e6c`
- `0x180027cd8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180027d4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180027d4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027d33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027dab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027dab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027dbe`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180027d7e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180027d7e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180027d09`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180027d09`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall VerifyClientMembership(enum WELL_KNOWN_SID_TYPE a1)
{
  HRESULT v1; // ebx
  HANDLE CurrentThread; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int16 v7; // ax
  _QWORD v9[8]; // [rsp+20h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+18h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v9, "VerifyClientMembership", 0x13Fu, 1u);
  TokenHandle = 0;
  v1 = CoImpersonateClient();
  LODWORD(v9[0]) = v1;
  if ( v1 >= 0 )
  {
    WORD2(v9[0]) = 324;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    {
      WORD2(v9[0]) = 326;
      LODWORD(v9[0]) = 0;
      LODWORD(v9[0]) = VerifyTokenMembership(TokenHandle, v3);
      v7 = 327;
      if ( SLODWORD(v9[0]) >= 0 )
      {
        WORD2(v9[0]) = 327;
LABEL_7:
        CoRevertToSelf();
        v1 = v9[0];
        goto LABEL_8;
      }
    }
    else
    {
      LODWORD(v9[0]) = GetLastFailureAsHRESULT(v4, v3, v5, v6, v9[0]);
      v7 = 326;
    }
    HIWORD(v9[0]) = v7;
    goto LABEL_7;
  }
  HIWORD(v9[0]) = 324;
LABEL_8:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v9);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180027cd8  mov     [rsp-8+arg_0], rbx
0x180027cdd  push    rbp
0x180027cde  mov     rbp, rsp
0x180027ce1  sub     rsp, 60h
0x180027ce5  mov     r9d, 1; unsigned __int16
0x180027ceb  lea     rdx, aVerifyclientme; "VerifyClientMembership"
0x180027cf2  mov     r8d, 13Fh; unsigned __int16
0x180027cf8  lea     rcx, [rbp+var_40]; this
0x180027cfc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180027d01  mov     [rbp+TokenHandle], 0
0x180027d09  call    cs:__imp_CoImpersonateClient
0x180027d0f  mov     ebx, eax
0x180027d11  mov     [rbp+var_40], eax
0x180027d14  test    eax, eax
0x180027d16  mov     eax, 144h
0x180027d1b  js      loc_180027DCE
0x180027d21  mov     rcx, [rbp+TokenHandle]; hObject
0x180027d25  mov     [rbp+var_3C], ax
0x180027d29  lea     rax, [rcx-1]
0x180027d2d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027d31  jbe     short loc_180027DAB
0x180027d33  call    cs:__imp_GetCurrentThread
0x180027d39  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180027d3d  mov     edx, 2000Ch; DesiredAccess
0x180027d42  mov     rcx, rax; ThreadHandle
0x180027d45  mov     r8d, 1; OpenAsSelf
0x180027d4b  call    cs:__imp_OpenThreadToken
0x180027d51  test    eax, eax
0x180027d53  jz      short loc_180027DD4
0x180027d55  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180027d59  mov     eax, 146h
0x180027d5e  mov     [rbp+var_3C], ax
0x180027d62  mov     [rbp+var_40], 0
0x180027d69  call    ?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z; VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)
0x180027d6e  mov     [rbp+var_40], eax
0x180027d71  test    eax, eax
0x180027d73  mov     eax, 147h
0x180027d78  js      short loc_180027DE1
0x180027d7a  mov     [rbp+var_3C], ax
0x180027d7e  call    cs:__imp_CoRevertToSelf
0x180027d84  mov     ebx, [rbp+var_40]
0x180027d87  mov     rcx, [rbp+TokenHandle]; hObject
0x180027d8b  lea     rdx, [rcx-1]
0x180027d8f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180027d93  jbe     short loc_180027DBE
0x180027d95  lea     rcx, [rbp+var_40]; this
0x180027d99  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180027d9e  mov     eax, ebx
0x180027da0  mov     rbx, [rsp+60h+arg_0]
0x180027da5  add     rsp, 60h
0x180027da9  pop     rbp
0x180027daa  retn
0x180027dab  call    cs:__imp_CloseHandle
0x180027db1  mov     [rbp+TokenHandle], 0
0x180027db9  jmp     loc_180027D33
0x180027dbe  call    cs:__imp_CloseHandle
0x180027dc4  mov     [rbp+TokenHandle], 0
0x180027dcc  jmp     short loc_180027D95
0x180027dce  mov     [rbp+var_3A], ax
0x180027dd2  jmp     short loc_180027D87
0x180027dd4  call    GetLastFailureAsHRESULT
0x180027dd9  mov     [rbp+var_40], eax
0x180027ddc  mov     eax, 146h
0x180027de1  mov     [rbp+var_3A], ax
0x180027de5  jmp     short loc_180027D7E
```
