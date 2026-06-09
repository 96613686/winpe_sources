# IsProtectedModeCOMCaller(int *)

- ea: `0x180064e80`
- end: `0x180064f5c`
- name: `?IsProtectedModeCOMCaller@@YAJPEAH@Z`
- size: `220`
- prototype: `int(int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180018410`
- `0x180024b80`
- `0x18005e8e4`
- `0x180064e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180064ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180064ed7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064eeb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064eeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064f44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064f44`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180064f29`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180064f29`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180064ec6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180064ec6`

## pseudocode

```c
__int64 __fastcall IsProtectedModeCOMCaller(int *a1)
{
  int v2; // ebx
  BOOL v3; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( (unsigned __int8)IEConfiguration_GetBool(268435519) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x397,
      (unsigned int)"onecoreuap\\inetcore\\lib\\il\\iel2_iertutil_legacy\\mic.cxx",
      (const char *)0x8000000ELL,
      v7);
  v2 = CoImpersonateClient();
  if ( v2 >= 0 )
  {
    v3 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      v2 = IsMICLowProcess(TokenHandle);
      v3 = v2 != 1;
    }
    if ( !TokenHandle )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    CoRevertToSelf();
    if ( v2 >= 0 && a1 )
      *a1 = v3;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180064e80  mov     [rsp+arg_0], rbx
0x180064e85  mov     [rsp+arg_10], rsi
0x180064e8a  push    rdi; int
0x180064e8b  sub     rsp, 20h
0x180064e8f  mov     rsi, rcx
0x180064e92  mov     [rsp+28h+TokenHandle], 0
0x180064e9b  mov     ecx, 1000003Fh
0x180064ea0  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180064ea5  test    al, al
0x180064ea7  jz      short loc_180064EC6
0x180064ea9  mov     rcx, [rsp+28h]; this
0x180064eae  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\lib\\il\\iel2_ier"...
0x180064eb5  mov     r9d, 8000000Eh; char *
0x180064ebb  mov     edx, 397h; void *
0x180064ec0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180064ec6  call    cs:__imp_CoImpersonateClient
0x180064ecc  mov     ebx, eax
0x180064ece  test    eax, eax
0x180064ed0  js      short loc_180064F3A
0x180064ed2  mov     edi, 1
0x180064ed7  call    cs:__imp_GetCurrentThread
0x180064edd  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180064ee2  xor     r8d, r8d; OpenAsSelf
0x180064ee5  mov     rcx, rax; ThreadHandle
0x180064ee8  lea     edx, [rdi+7]; DesiredAccess
0x180064eeb  call    cs:__imp_OpenThreadToken
0x180064ef1  test    eax, eax
0x180064ef3  jz      short loc_180064F0C
0x180064ef5  mov     rcx, [rsp+28h+TokenHandle]; void *
0x180064efa  call    ?IsMICLowProcess@@YAJPEAX@Z; IsMICLowProcess(void *)
0x180064eff  mov     ebx, eax
0x180064f01  test    eax, eax
0x180064f03  jz      short loc_180064F0C
0x180064f05  xor     eax, eax
0x180064f07  cmp     ebx, edi
0x180064f09  cmovz   edi, eax
0x180064f0c  cmp     [rsp+28h+TokenHandle], 0
0x180064f12  jnz     short loc_180064F29
0x180064f14  call    cs:__imp_GetLastError
0x180064f1a  mov     ebx, eax
0x180064f1c  test    eax, eax
0x180064f1e  jle     short loc_180064F29
0x180064f20  movzx   ebx, ax
0x180064f23  or      ebx, 80070000h
0x180064f29  call    cs:__imp_CoRevertToSelf
0x180064f2f  test    ebx, ebx
0x180064f31  js      short loc_180064F3A
0x180064f33  test    rsi, rsi
0x180064f36  jz      short loc_180064F3A
0x180064f38  mov     [rsi], edi
0x180064f3a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180064f3f  test    rcx, rcx
0x180064f42  jz      short loc_180064F4A
0x180064f44  call    cs:__imp_CloseHandle
0x180064f4a  mov     rsi, [rsp+28h+arg_10]
0x180064f4f  mov     eax, ebx
0x180064f51  mov     rbx, [rsp+28h+arg_0]
0x180064f56  add     rsp, 20h
0x180064f5a  pop     rdi
0x180064f5b  retn
```
