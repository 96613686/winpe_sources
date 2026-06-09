# ExtractRPCClientSID

- ea: `0x18005441c`
- end: `0x180054562`
- name: `ExtractRPCClientSID`
- size: `326`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `34`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800314c4`
- `0x180050be8`
- `0x180054748`
- `0x1800558ec`
- `0x180094980`
- `0x18009612c`
- `0x180096624`
- `0x180096b10`
- `0x180097afc`
- `0x180097df8`
- `0x18009819c`
- `0x18009866c`
- `0x1800989bc`
- `0x180098cd8`
- `0x180099038`
- `0x18009934c`
- `0x180099770`
- `0x180099b5c`
- `0x18009a3e8`
- `0x18009a6a0`
- `0x18009aa54`
- `0x18009ac38`
- `0x18009ae1c`
- `0x18009c4e8`
- `0x18009cf88`
- `0x18009d0c8`
- `0x18009d814`
- `0x18009dd10`
- `0x18009e19c`
- `0x18009ed70`
- `0x18009fa7c`
- `0x1800a00c8`
- `0x1800a03fc`
- `0x1800a08b0`

## callees

- `0x18000af3c`
- `0x18005441c`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800544a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800544a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180054491`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180054491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800544af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800544af`
- `RPCRT4!RpcRevertToSelf` at `0x18005453d`
- `RPCRT4!RpcRevertToSelf` at `0x18005453d`
- `RPCRT4!RpcImpersonateClient` at `0x180054446`
- `RPCRT4!RpcImpersonateClient` at `0x180054446`
- `fwbase!FwGetTokenInformation` at `0x1800544f1`
- `fwbase!FwGetTokenInformation` at `0x1800544f1`
- `fwbase!FwCloseHandle` at `0x180054533`
- `fwbase!FwCloseHandle` at `0x180054533`

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
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, TokenInformation);
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
0x18005441c  mov     [rsp+arg_10], rbx
0x180054421  mov     [rsp+arg_18], rbp
0x180054426  push    rsi
0x180054427  sub     rsp, 30h
0x18005442b  mov     rax, cs:__security_cookie
0x180054432  xor     rax, rsp
0x180054435  mov     [rsp+38h+var_10], rax
0x18005443a  mov     rbp, rdx
0x18005443d  mov     [rsp+38h+TokenHandle], 0
0x180054446  call    cs:__imp_RpcImpersonateClient
0x18005444c  mov     ebx, eax
0x18005444e  test    eax, eax
0x180054450  jz      short loc_18005448C
0x180054452  xor     esi, esi
0x180054454  test    eax, eax
0x180054456  jle     short loc_180054461
0x180054458  movzx   ebx, ax
0x18005445b  or      ebx, 80070000h
0x180054461  mov     rcx, cs:WPP_GLOBAL_Control
0x180054468  lea     rax, WPP_GLOBAL_Control
0x18005446f  cmp     rcx, rax
0x180054472  jz      loc_18005452E
0x180054478  test    byte ptr [rcx+1Ch], 1
0x18005447c  jz      loc_18005452E
0x180054482  mov     edx, 1Dh
0x180054487  jmp     loc_18005451B
0x18005448c  mov     esi, 1
0x180054491  call    cs:__imp_GetCurrentThread
0x180054497  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18005449c  mov     r8d, esi; OpenAsSelf
0x18005449f  mov     rcx, rax; ThreadHandle
0x1800544a2  lea     edx, [rsi+7]; DesiredAccess
0x1800544a5  call    cs:__imp_OpenThreadToken
0x1800544ab  test    eax, eax
0x1800544ad  jnz     short loc_1800544E4
0x1800544af  call    cs:__imp_GetLastError
0x1800544b5  mov     ebx, eax
0x1800544b7  test    eax, eax
0x1800544b9  jle     short loc_1800544C4
0x1800544bb  movzx   ebx, ax
0x1800544be  or      ebx, 80070000h
0x1800544c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800544cb  lea     rax, WPP_GLOBAL_Control
0x1800544d2  cmp     rcx, rax
0x1800544d5  jz      short loc_18005452E
0x1800544d7  test    [rcx+1Ch], sil
0x1800544db  jz      short loc_18005452E
0x1800544dd  mov     edx, 1Eh
0x1800544e2  jmp     short loc_18005451B
0x1800544e4  mov     rcx, [rsp+38h+TokenHandle]
0x1800544e9  xor     r9d, r9d
0x1800544ec  mov     r8, rbp
0x1800544ef  mov     edx, esi
0x1800544f1  call    cs:__imp_FwGetTokenInformation
0x1800544f7  mov     ebx, eax
0x1800544f9  test    eax, eax
0x1800544fb  jns     short loc_18005452E
0x1800544fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180054504  lea     rax, WPP_GLOBAL_Control
0x18005450b  cmp     rcx, rax
0x18005450e  jz      short loc_18005452E
0x180054510  test    [rcx+1Ch], sil
0x180054514  jz      short loc_18005452E
0x180054516  mov     edx, 1Fh
0x18005451b  mov     rcx, [rcx+10h]
0x18005451f  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180054526  mov     r9d, ebx
0x180054529  call    WPP_SF_d
0x18005452e  mov     rcx, [rsp+38h+TokenHandle]
0x180054533  call    cs:__imp_FwCloseHandle
0x180054539  test    esi, esi
0x18005453b  jz      short loc_180054543
0x18005453d  call    cs:__imp_RpcRevertToSelf
0x180054543  mov     eax, ebx
0x180054545  mov     rcx, [rsp+38h+var_10]
0x18005454a  xor     rcx, rsp; StackCookie
0x18005454d  call    __security_check_cookie
0x180054552  mov     rbx, [rsp+38h+arg_10]
0x180054557  mov     rbp, [rsp+38h+arg_18]
0x18005455c  add     rsp, 30h
0x180054560  pop     rsi
0x180054561  retn
```
