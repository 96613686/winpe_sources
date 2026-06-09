# FwGetThreadToken

- ea: `0x180095688`
- end: `0x1800957aa`
- name: `FwGetThreadToken`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18009c4e8`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x180095688`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180095728`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180095728`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180095714`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180095714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095732`
- `RPCRT4!RpcRevertToSelf` at `0x180095785`
- `RPCRT4!RpcRevertToSelf` at `0x180095785`
- `RPCRT4!RpcImpersonateClient` at `0x1800956b9`
- `RPCRT4!RpcImpersonateClient` at `0x1800956b9`
- `fwbase!FwCloseHandle` at `0x18009577b`
- `fwbase!FwCloseHandle` at `0x18009577b`

## pseudocode

```c
__int64 __fastcall FwGetThreadToken(void *a1, void **a2)
{
  RPC_STATUS v3; // eax
  unsigned int v4; // ebx
  int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  *a2 = 0;
  v3 = RpcImpersonateClient(a1);
  v4 = v3;
  if ( v3 )
  {
    v5 = 0;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 32;
LABEL_7:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v4);
    }
  }
  else
  {
    v5 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
    {
      v4 = 0;
      *a2 = TokenHandle;
      TokenHandle = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 33;
        goto LABEL_7;
      }
    }
  }
  FwCloseHandle(TokenHandle);
  if ( v5 )
    RpcRevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x180095688  mov     [rsp+arg_10], rbx
0x18009568d  mov     [rsp+arg_18], rsi
0x180095692  push    rdi
0x180095693  sub     rsp, 30h
0x180095697  mov     rax, cs:__security_cookie
0x18009569e  xor     rax, rsp
0x1800956a1  mov     [rsp+38h+var_10], rax
0x1800956a6  mov     rdi, rdx
0x1800956a9  mov     [rsp+38h+TokenHandle], 0
0x1800956b2  mov     qword ptr [rdx], 0
0x1800956b9  call    cs:__imp_RpcImpersonateClient
0x1800956bf  mov     ebx, eax
0x1800956c1  test    eax, eax
0x1800956c3  jz      short loc_18009570F
0x1800956c5  xor     esi, esi
0x1800956c7  test    eax, eax
0x1800956c9  jle     short loc_1800956D4
0x1800956cb  movzx   ebx, ax
0x1800956ce  or      ebx, 80070000h
0x1800956d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800956db  lea     rax, WPP_GLOBAL_Control
0x1800956e2  cmp     rcx, rax
0x1800956e5  jz      loc_180095776
0x1800956eb  test    byte ptr [rcx+1Ch], 1
0x1800956ef  jz      loc_180095776
0x1800956f5  mov     edx, 20h ; ' '
0x1800956fa  mov     rcx, [rcx+10h]
0x1800956fe  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180095705  mov     r9d, ebx
0x180095708  call    WPP_SF_d
0x18009570d  jmp     short loc_180095776
0x18009570f  mov     esi, 1
0x180095714  call    cs:__imp_GetCurrentThread
0x18009571a  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18009571f  mov     r8d, esi; OpenAsSelf
0x180095722  mov     rcx, rax; ThreadHandle
0x180095725  lea     edx, [rsi+9]; DesiredAccess
0x180095728  call    cs:__imp_OpenThreadToken
0x18009572e  test    eax, eax
0x180095730  jnz     short loc_180095767
0x180095732  call    cs:__imp_GetLastError
0x180095738  mov     ebx, eax
0x18009573a  test    eax, eax
0x18009573c  jle     short loc_180095747
0x18009573e  movzx   ebx, ax
0x180095741  or      ebx, 80070000h
0x180095747  mov     rcx, cs:WPP_GLOBAL_Control
0x18009574e  lea     rax, WPP_GLOBAL_Control
0x180095755  cmp     rcx, rax
0x180095758  jz      short loc_180095776
0x18009575a  test    [rcx+1Ch], sil
0x18009575e  jz      short loc_180095776
0x180095760  mov     edx, 21h ; '!'
0x180095765  jmp     short loc_1800956FA
0x180095767  mov     rcx, [rsp+38h+TokenHandle]
0x18009576c  xor     ebx, ebx
0x18009576e  mov     [rdi], rcx
0x180095771  mov     [rsp+38h+TokenHandle], rbx
0x180095776  mov     rcx, [rsp+38h+TokenHandle]
0x18009577b  call    cs:__imp_FwCloseHandle
0x180095781  test    esi, esi
0x180095783  jz      short loc_18009578B
0x180095785  call    cs:__imp_RpcRevertToSelf
0x18009578b  mov     eax, ebx
0x18009578d  mov     rcx, [rsp+38h+var_10]
0x180095792  xor     rcx, rsp; StackCookie
0x180095795  call    __security_check_cookie
0x18009579a  mov     rbx, [rsp+38h+arg_10]
0x18009579f  mov     rsi, [rsp+38h+arg_18]
0x1800957a4  add     rsp, 30h
0x1800957a8  pop     rdi
0x1800957a9  retn
```
