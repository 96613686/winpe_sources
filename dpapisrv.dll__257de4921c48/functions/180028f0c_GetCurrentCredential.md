# GetCurrentCredential

- ea: `0x180028f0c`
- end: `0x1800290c1`
- name: `GetCurrentCredential`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003b98`

## callees

- `0x180007f10`
- `0x180013f2c`
- `0x180028f0c`
- `0x18003e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028f76`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029082`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028f55`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028f55`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180029072`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180029072`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028f38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028f38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029095`
- `ntdll!RtlNtStatusToDosError` at `0x1800290a7`
- `ntdll!RtlNtStatusToDosError` at `0x1800290a7`

## string_xrefs

- `0x180028fdb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
DWORD __fastcall GetCurrentCredential(__int64 a1, __int64 a2, _OWORD *a3)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v7; // ebx
  DWORD LastError; // edi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rax
  _DWORD *v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // ecx
  __int64 v13; // rax
  void *TokenHandle; // [rsp+20h] [rbp-38h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  *a3 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    return GetLastError();
  RevertToSelf();
  v7 = 0;
  LastError = 0;
  v9 = (__int64 (__fastcall *)(__int64, _QWORD, __int64 *))*((_QWORD *)g_pDPAPILsasrvIfTable + 13);
  if ( !v9 )
    goto LABEL_15;
  v7 = v9(a2, 0, &v15);
  if ( v7 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids,
        (unsigned int)v7);
    if ( v7 == -1073741637 )
      v7 = 0;
    goto LABEL_15;
  }
  v10 = (_DWORD *)v15;
  v11 = *(_DWORD *)(v15 + 12);
  if ( v11 > 0xFFFF || (v12 = *(_DWORD *)(v15 + 8), v12 > *(_DWORD *)v15) || v11 + v12 > *(_DWORD *)v15 )
  {
    v7 = -1073741811;
    DebugTraceError(3221225485LL, "ntstatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 134);
LABEL_15:
    v10 = (_DWORD *)v15;
    goto LABEL_16;
  }
  *a3 = *(_OWORD *)(v15 + 16);
LABEL_16:
  if ( v10 )
  {
    v13 = (unsigned int)*v10;
    if ( *v10 )
    {
      do
      {
        *(_BYTE *)v10 = 0;
        v10 = (_DWORD *)((char *)v10 + 1);
        --v13;
      }
      while ( v13 );
      v10 = (_DWORD *)v15;
    }
    (*((void (__fastcall **)(_DWORD *))g_pDPAPILsasrvIfTable + 3))(v10);
  }
  if ( !SetThreadToken(0, TokenHandle) )
    LastError = GetLastError();
  CloseHandle(TokenHandle);
  if ( v7 < 0 )
    return RtlNtStatusToDosError(v7);
  return LastError;
}

```

## disassembly

```asm
0x180028f0c  mov     [rsp+arg_18], r9
0x180028f11  push    rbx
0x180028f12  push    rbp
0x180028f13  push    rsi
0x180028f14  push    rdi
0x180028f15  sub     rsp, 38h
0x180028f19  xorps   xmm0, xmm0
0x180028f1c  mov     [rsp+58h+arg_18], 0
0x180028f25  movups  xmmword ptr [r8], xmm0
0x180028f29  mov     rsi, r8
0x180028f2c  mov     [rsp+58h+TokenHandle], 0
0x180028f35  mov     rbp, rdx
0x180028f38  call    cs:__imp_GetCurrentThread
0x180028f3f  nop     dword ptr [rax+rax+00h]
0x180028f44  mov     edx, 4; DesiredAccess
0x180028f49  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180028f4e  mov     rcx, rax; ThreadHandle
0x180028f51  lea     r8d, [rdx-3]; OpenAsSelf
0x180028f55  call    cs:__imp_OpenThreadToken
0x180028f5c  nop     dword ptr [rax+rax+00h]
0x180028f61  test    eax, eax
0x180028f63  jnz     short loc_180028F76
0x180028f65  call    cs:__imp_GetLastError
0x180028f6c  nop     dword ptr [rax+rax+00h]
0x180028f71  jmp     loc_1800290B7
0x180028f76  call    cs:__imp_RevertToSelf
0x180028f7d  nop     dword ptr [rax+rax+00h]
0x180028f82  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x180028f89  xor     ebx, ebx
0x180028f8b  xor     edi, edi
0x180028f8d  mov     rax, [rax+68h]
0x180028f91  test    rax, rax
0x180028f94  jz      loc_180029036
0x180028f9a  lea     r8, [rsp+58h+arg_18]
0x180028f9f  xor     edx, edx
0x180028fa1  mov     rcx, rbp
0x180028fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fa9  mov     ebx, eax
0x180028fab  test    eax, eax
0x180028fad  js      short loc_180028FFA
0x180028faf  mov     rdx, [rsp+58h+arg_18]
0x180028fb4  mov     eax, [rdx+0Ch]
0x180028fb7  cmp     eax, 0FFFFh
0x180028fbc  ja      short loc_180028FD5
0x180028fbe  mov     ecx, [rdx+8]
0x180028fc1  cmp     ecx, [rdx]
0x180028fc3  ja      short loc_180028FD5
0x180028fc5  add     ecx, eax
0x180028fc7  cmp     ecx, [rdx]
0x180028fc9  ja      short loc_180028FD5
0x180028fcb  movups  xmm0, xmmword ptr [rdx+10h]
0x180028fcf  movdqu  xmmword ptr [rsi], xmm0
0x180028fd3  jmp     short loc_18002903B
0x180028fd5  mov     r9d, 86h
0x180028fdb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180028fe2  lea     rdx, aNtstatus_0; "ntstatus"
0x180028fe9  mov     ecx, 0C000000Dh
0x180028fee  mov     ebx, 0C000000Dh
0x180028ff3  call    DebugTraceError
0x180028ff8  jmp     short loc_180029036
0x180028ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180029001  lea     rax, WPP_GLOBAL_Control
0x180029008  cmp     rcx, rax
0x18002900b  jz      short loc_18002902B
0x18002900d  test    byte ptr [rcx+1Ch], 8
0x180029011  jz      short loc_18002902B
0x180029013  mov     rcx, [rcx+10h]
0x180029017  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x18002901e  mov     edx, 0Ah
0x180029023  mov     r9d, ebx
0x180029026  call    WPP_SF_d
0x18002902b  xor     eax, eax
0x18002902d  cmp     ebx, 0C00000BBh
0x180029033  cmovz   ebx, eax
0x180029036  mov     rdx, [rsp+58h+arg_18]
0x18002903b  test    rdx, rdx
0x18002903e  jz      short loc_18002906B
0x180029040  mov     eax, [rdx]
0x180029042  test    rax, rax
0x180029045  jz      short loc_180029058
0x180029047  mov     [rdx], dil
0x18002904a  inc     rdx
0x18002904d  sub     rax, 1
0x180029051  jnz     short loc_180029047
0x180029053  mov     rdx, [rsp+58h+arg_18]
0x180029058  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x18002905f  mov     rcx, rdx
0x180029062  mov     rax, [rax+18h]
0x180029066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002906b  mov     rdx, [rsp+58h+TokenHandle]; Token
0x180029070  xor     ecx, ecx; Thread
0x180029072  call    cs:__imp_SetThreadToken
0x180029079  nop     dword ptr [rax+rax+00h]
0x18002907e  test    eax, eax
0x180029080  jnz     short loc_180029090
0x180029082  call    cs:__imp_GetLastError
0x180029089  nop     dword ptr [rax+rax+00h]
0x18002908e  mov     edi, eax
0x180029090  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180029095  call    cs:__imp_CloseHandle
0x18002909c  nop     dword ptr [rax+rax+00h]
0x1800290a1  test    ebx, ebx
0x1800290a3  jns     short loc_1800290B5
0x1800290a5  mov     ecx, ebx; Status
0x1800290a7  call    cs:__imp_RtlNtStatusToDosError
0x1800290ae  nop     dword ptr [rax+rax+00h]
0x1800290b3  mov     edi, eax
0x1800290b5  mov     eax, edi
0x1800290b7  add     rsp, 38h
0x1800290bb  pop     rdi
0x1800290bc  pop     rsi
0x1800290bd  pop     rbp
0x1800290be  pop     rbx
0x1800290bf  retn
```
