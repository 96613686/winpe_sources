# ExtractRPCClientSID

- ea: `0x180059714`
- end: `0x180059885`
- name: `ExtractRPCClientSID`
- size: `369`
- prototype: ``
- caller_count: `34`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800355c0`
- `0x180047e34`
- `0x180054ea8`
- `0x18005a810`
- `0x1800997c0`
- `0x18009b0f0`
- `0x18009b620`
- `0x18009bb44`
- `0x18009cb7c`
- `0x18009cea8`
- `0x18009d280`
- `0x18009d778`
- `0x18009dafc`
- `0x18009de48`
- `0x18009e1d8`
- `0x18009e51c`
- `0x18009e988`
- `0x18009edb8`
- `0x18009f6ac`
- `0x18009f98c`
- `0x18009fd80`
- `0x18009ff70`
- `0x1800a0160`
- `0x1800a1918`
- `0x1800a2424`
- `0x1800a2578`
- `0x1800a2d7c`
- `0x1800a32ac`
- `0x1800a376c`
- `0x1800a4378`
- `0x1800a50dc`
- `0x1800a575c`
- `0x1800a5ac0`
- `0x1800a5f9c`

## callees

- `0x18000a710`
- `0x180059714`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005978f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005978f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800597a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800597a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597b9`
- `RPCRT4!RpcImpersonateClient` at `0x18005973e`
- `RPCRT4!RpcImpersonateClient` at `0x18005973e`
- `RPCRT4!RpcRevertToSelf` at `0x180059859`
- `RPCRT4!RpcRevertToSelf` at `0x180059859`
- `fwbase!FwGetTokenInformation` at `0x180059801`
- `fwbase!FwGetTokenInformation` at `0x180059801`
- `fwbase!FwCloseHandle` at `0x180059849`
- `fwbase!FwCloseHandle` at `0x180059849`

## pseudocode

```c
__int64 __fastcall ExtractRPCClientSID(void *a1, __int64 a2)
{
  RPC_STATUS v3; // eax
  unsigned int TokenInformation; // ebx
  int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  v3 = RpcImpersonateClient(a1);
  TokenInformation = v3;
  if ( v3 )
  {
    v5 = 0;
    if ( v3 > 0 )
      TokenInformation = (unsigned __int16)v3 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 29;
LABEL_17:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, TokenInformation);
    }
  }
  else
  {
    v5 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      TokenInformation = FwGetTokenInformation(TokenHandle, 1, a2, 0);
      if ( (TokenInformation & 0x80000000) != 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = 31;
          goto LABEL_17;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      TokenInformation = LastError;
      if ( LastError > 0 )
        TokenInformation = (unsigned __int16)LastError | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 30;
        goto LABEL_17;
      }
    }
  }
  FwCloseHandle(TokenHandle);
  if ( v5 )
    RpcRevertToSelf();
  return TokenInformation;
}

```

## disassembly

```asm
0x180059714  mov     [rsp+arg_10], rbx
0x180059719  mov     [rsp+arg_18], rbp
0x18005971e  push    rsi
0x18005971f  sub     rsp, 30h
0x180059723  mov     rax, cs:__security_cookie
0x18005972a  xor     rax, rsp
0x18005972d  mov     [rsp+38h+var_10], rax
0x180059732  mov     rbp, rdx
0x180059735  mov     [rsp+38h+TokenHandle], 0
0x18005973e  call    cs:__imp_RpcImpersonateClient
0x180059745  nop     dword ptr [rax+rax+00h]
0x18005974a  mov     ebx, eax
0x18005974c  test    eax, eax
0x18005974e  jz      short loc_18005978A
0x180059750  xor     esi, esi
0x180059752  test    eax, eax
0x180059754  jle     short loc_18005975F
0x180059756  movzx   ebx, ax
0x180059759  or      ebx, 80070000h
0x18005975f  mov     rcx, cs:WPP_GLOBAL_Control
0x180059766  lea     rax, WPP_GLOBAL_Control
0x18005976d  cmp     rcx, rax
0x180059770  jz      loc_180059844
0x180059776  test    byte ptr [rcx+1Ch], 1
0x18005977a  jz      loc_180059844
0x180059780  mov     edx, 1Dh
0x180059785  jmp     loc_180059831
0x18005978a  mov     esi, 1
0x18005978f  call    cs:__imp_GetCurrentThread
0x180059796  nop     dword ptr [rax+rax+00h]
0x18005979b  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800597a0  mov     r8d, esi; OpenAsSelf
0x1800597a3  mov     rcx, rax; ThreadHandle
0x1800597a6  lea     edx, [rsi+7]; DesiredAccess
0x1800597a9  call    cs:__imp_OpenThreadToken
0x1800597b0  nop     dword ptr [rax+rax+00h]
0x1800597b5  test    eax, eax
0x1800597b7  jnz     short loc_1800597F4
0x1800597b9  call    cs:__imp_GetLastError
0x1800597c0  nop     dword ptr [rax+rax+00h]
0x1800597c5  mov     ebx, eax
0x1800597c7  test    eax, eax
0x1800597c9  jle     short loc_1800597D4
0x1800597cb  movzx   ebx, ax
0x1800597ce  or      ebx, 80070000h
0x1800597d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800597db  lea     rax, WPP_GLOBAL_Control
0x1800597e2  cmp     rcx, rax
0x1800597e5  jz      short loc_180059844
0x1800597e7  test    [rcx+1Ch], sil
0x1800597eb  jz      short loc_180059844
0x1800597ed  mov     edx, 1Eh
0x1800597f2  jmp     short loc_180059831
0x1800597f4  mov     rcx, [rsp+38h+TokenHandle]
0x1800597f9  xor     r9d, r9d
0x1800597fc  mov     r8, rbp
0x1800597ff  mov     edx, esi
0x180059801  call    cs:__imp_FwGetTokenInformation
0x180059808  nop     dword ptr [rax+rax+00h]
0x18005980d  mov     ebx, eax
0x18005980f  test    eax, eax
0x180059811  jns     short loc_180059844
0x180059813  mov     rcx, cs:WPP_GLOBAL_Control
0x18005981a  lea     rax, WPP_GLOBAL_Control
0x180059821  cmp     rcx, rax
0x180059824  jz      short loc_180059844
0x180059826  test    [rcx+1Ch], sil
0x18005982a  jz      short loc_180059844
0x18005982c  mov     edx, 1Fh
0x180059831  mov     rcx, [rcx+10h]
0x180059835  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18005983c  mov     r9d, ebx
0x18005983f  call    WPP_SF_d
0x180059844  mov     rcx, [rsp+38h+TokenHandle]
0x180059849  call    cs:__imp_FwCloseHandle
0x180059850  nop     dword ptr [rax+rax+00h]
0x180059855  test    esi, esi
0x180059857  jz      short loc_180059865
0x180059859  call    cs:__imp_RpcRevertToSelf
0x180059860  nop     dword ptr [rax+rax+00h]
0x180059865  mov     eax, ebx
0x180059867  mov     rcx, [rsp+38h+var_10]
0x18005986c  xor     rcx, rsp; StackCookie
0x18005986f  call    __security_check_cookie
0x180059874  mov     rbx, [rsp+38h+arg_10]
0x180059879  mov     rbp, [rsp+38h+arg_18]
0x18005987e  add     rsp, 30h
0x180059882  pop     rsi
0x180059883  retn
```
