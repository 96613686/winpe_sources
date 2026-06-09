# HandleDomainUserPasswordChange(void *,_CREDENTIAL_KEY *)

- ea: `0x18002c0a0`
- end: `0x18002c4a6`
- name: `?HandleDomainUserPasswordChange@@YAKPEAXPEAU_CREDENTIAL_KEY@@@Z`
- size: `1030`
- prototype: `__int64 __fastcall(HANDLE hToken, struct _CREDENTIAL_KEY *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028900`

## callees

- `0x180001184`
- `0x1800011e0`
- `0x180007f10`
- `0x1800097f0`
- `0x18000db40`
- `0x180013a18`
- `0x180013ac0`
- `0x180013f2c`
- `0x18001467c`
- `0x18001ab70`
- `0x18001d810`
- `0x18001e1b4`
- `0x18002ae48`
- `0x18002c0a0`
- `0x18002e130`
- `0x180039d90`
- `0x18003e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c2cb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c2cb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c31c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c31c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2db`
- `LSASRV!LsaIDeriveCredentialKey` at `0x18002c25b`
- `LSASRV!LsaIDeriveCredentialKey` at `0x18002c25b`
- `ntdll!NtQueryInformationToken` at `0x18002c1ce`
- `ntdll!NtQueryInformationToken` at `0x18002c1ce`
- `ntdll!RtlNtStatusToDosError` at `0x18002c3c0`
- `ntdll!RtlNtStatusToDosError` at `0x18002c3c0`

## string_xrefs

- `0x18002c217`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002c2f8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002c3a3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall HandleDomainUserPasswordChange(HANDLE hToken, struct _CREDENTIAL_KEY *a2)
{
  int v4; // r12d
  _DWORD *v5; // r9
  unsigned int v6; // edi
  __int64 v7; // r14
  unsigned int v8; // r15d
  NTSTATUS v9; // ebx
  __int64 v10; // r9
  NTSTATUS v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // edx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int LastError; // eax
  unsigned int v17; // ebx
  __int64 v18; // r9
  __int64 v19; // rcx
  void *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  int *v23; // rax
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int *v27; // [rsp+48h] [rbp-B8h] BYREF
  void (*v28)(void); // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+58h] [rbp-A8h] BYREF
  char v30; // [rsp+5Ch] [rbp-A4h]
  _BYTE v31[16]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v32[4]; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+80h] [rbp-80h] BYREF
  __int128 v34; // [rsp+84h] [rbp-7Ch]
  __int128 v35; // [rsp+94h] [rbp-6Ch]
  _BYTE v36[24]; // [rsp+A4h] [rbp-5Ch] BYREF
  _QWORD v37[6]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v38; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned int v39[142]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD TokenInformation[12]; // [rsp+330h] [rbp+230h] BYREF

  memset_0(v37, 0, 0x270u);
  v4 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  memset(v36, 0, sizeof(v36));
  v27 = 0;
  v28 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  v29 = 0;
  v30 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v29);
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    if ( v30 && (v32[0] || v32[1] || v32[2] || v32[3]) )
      v5 = v32;
    else
      LODWORD(v5) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (int)&dword_18004C260,
      (int)byte_180044BEB,
      (int)v31,
      (int)v5);
  }
  v6 = (*((_DWORD *)a2 + 1) & 4 | 8u) >> 2;
  v7 = *((unsigned int *)a2 + 2);
  v8 = *((unsigned __int16 *)a2 + 6);
  v9 = NtQueryInformationToken(hToken, TokenUser, TokenInformation, 0x58u, &ReturnLength);
  if ( v9 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        35,
        WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
        (unsigned int)v9);
    v10 = 1831;
    goto LABEL_16;
  }
  v9 = LsaIDeriveCredentialKey(TokenInformation[0], 0, (char *)a2 + v7, v8, v6, &v27, &v28);
  if ( v9 < 0 )
  {
    v10 = 1846;
LABEL_16:
    DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v10);
    v11 = v9;
LABEL_32:
    v17 = RtlNtStatusToDosError(v11);
    goto LABEL_33;
  }
  v12 = v27[3];
  if ( v12 > 0xFFFF || (v13 = v27[2], v13 > *v27) || v13 + v12 > *v27 )
  {
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 1858);
    v11 = -1073741811;
    goto LABEL_32;
  }
  HIDWORD(v34) = v27[1];
  v14 = v27[2];
  v35 = *(_OWORD *)((char *)v27 + v14);
  *(_DWORD *)v36 = *(unsigned int *)((char *)v27 + v14 + 16);
  v15 = v27[2];
  *(_OWORD *)&v36[4] = *(_OWORD *)((char *)v27 + v15 + 20);
  *(_DWORD *)&v36[20] = *(unsigned int *)((char *)v27 + v15 + 36);
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    v17 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v37, 0, 0, 0);
    RevertToSelf();
    if ( v17 )
    {
      v18 = 1892;
      v19 = v17;
      goto LABEL_25;
    }
    v4 = 1;
    GetDefaultAlgInfo(v20, &v38, 0, v39, 0);
    LastError = SynchronizeMasterKeys(v37, 0, (struct DP_KEK *)&v33, 0, 3u, 0, 0);
    v17 = LastError;
    if ( !LastError )
    {
      UpdateLastMasterKeySync(v37);
      goto LABEL_33;
    }
    v18 = 1918;
  }
  else
  {
    LastError = GetLastError();
    v17 = LastError;
    v18 = 1882;
  }
  v19 = LastError;
LABEL_25:
  DebugTraceError(v19, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v18);
LABEL_33:
  v29 = 2;
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    v26 = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)&dword_18004C260,
      (int)word_180044DAA,
      (int)v31,
      v21,
      (__int64)&v26);
  }
  if ( v4 )
    CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v37);
  else
    DPAPISynchronizeMasterKeys(hToken, 0, 0, 0);
  if ( v28 && v27 )
    v28();
  v22 = 60;
  v23 = &v33;
  do
  {
    *(_BYTE *)v23 = 0;
    v23 = (int *)((char *)v23 + 1);
    --v22;
  }
  while ( v22 );
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v29);
  return v17;
}

```

## disassembly

```asm
0x18002c0a0  mov     [rsp-8+arg_10], rbx
0x18002c0a5  push    rbp
0x18002c0a6  push    rsi
0x18002c0a7  push    rdi
0x18002c0a8  push    r12
0x18002c0aa  push    r13
0x18002c0ac  push    r14
0x18002c0ae  push    r15
0x18002c0b0  lea     rbp, [rsp-2A0h]
0x18002c0b8  sub     rsp, 3A0h
0x18002c0bf  mov     rax, cs:__security_cookie
0x18002c0c6  xor     rax, rsp
0x18002c0c9  mov     [rbp+2D0h+var_40], rax
0x18002c0d0  mov     rsi, rdx
0x18002c0d3  mov     r13, rcx
0x18002c0d6  xor     edx, edx; Val
0x18002c0d8  mov     r8d, 270h; Size
0x18002c0de  lea     rcx, [rbp+2D0h+var_310]; void *
0x18002c0e2  call    memset_0
0x18002c0e7  xor     ebx, ebx
0x18002c0e9  mov     r12d, ebx
0x18002c0ec  mov     [rbp+2D0h+var_350], ebx
0x18002c0ef  xorps   xmm0, xmm0
0x18002c0f2  xor     eax, eax
0x18002c0f4  movups  [rbp+2D0h+var_34C], xmm0
0x18002c0f8  movups  [rbp+2D0h+var_33C], xmm0
0x18002c0fc  movups  [rbp+2D0h+var_32C], xmm0
0x18002c100  mov     [rbp+2D0h+var_31C], rax
0x18002c104  mov     [rsp+3D0h+var_388], rbx
0x18002c109  mov     [rsp+3D0h+var_380], rbx
0x18002c10e  xor     edx, edx; Val
0x18002c110  lea     r8d, [rbx+58h]; Size
0x18002c114  lea     rcx, [rbp+2D0h+TokenInformation]; void *
0x18002c11b  call    memset_0
0x18002c120  mov     [rsp+3D0h+var_390], ebx
0x18002c124  mov     [rsp+3D0h+var_378], ebx
0x18002c128  mov     [rsp+3D0h+var_374], bl
0x18002c12c  lea     rcx, [rsp+3D0h+var_378]
0x18002c131  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18002c136  mov     eax, cs:dword_18004C260
0x18002c13c  cmp     eax, 5
0x18002c13f  jbe     short loc_18002C19B
0x18002c141  mov     rdx, 400000000000h
0x18002c14b  lea     rcx, dword_18004C260
0x18002c152  call    _tlgKeywordOn
0x18002c157  test    al, al
0x18002c159  jz      short loc_18002C19B
0x18002c15b  cmp     [rsp+3D0h+var_374], bl
0x18002c15f  jz      short loc_18002C180
0x18002c161  cmp     [rsp+3D0h+var_360], ebx
0x18002c165  jnz     short loc_18002C179
0x18002c167  cmp     [rsp+3D0h+var_35C], ebx
0x18002c16b  jnz     short loc_18002C179
0x18002c16d  cmp     [rsp+3D0h+var_358], ebx
0x18002c171  jnz     short loc_18002C179
0x18002c173  cmp     [rsp+3D0h+var_354], ebx
0x18002c177  jz      short loc_18002C180
0x18002c179  lea     r9, [rsp+3D0h+var_360]
0x18002c17e  jmp     short loc_18002C183
0x18002c180  mov     r9, rbx
0x18002c183  lea     r8, [rsp+3D0h+var_370]
0x18002c188  lea     rdx, byte_180044BEB
0x18002c18f  lea     rcx, dword_18004C260
0x18002c196  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002c19b  mov     edi, [rsi+4]
0x18002c19e  and     edi, 4
0x18002c1a1  or      edi, 8
0x18002c1a4  shr     edi, 2
0x18002c1a7  mov     r14d, [rsi+8]
0x18002c1ab  movzx   r15d, word ptr [rsi+0Ch]
0x18002c1b0  lea     rax, [rsp+3D0h+var_390]
0x18002c1b5  mov     [rsp+3D0h+ReturnLength], rax; ReturnLength
0x18002c1ba  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18002c1c0  lea     r8, [rbp+2D0h+TokenInformation]; TokenInformation
0x18002c1c7  lea     edx, [r9-57h]; TokenInformationClass
0x18002c1cb  mov     rcx, r13; TokenHandle
0x18002c1ce  call    cs:__imp_NtQueryInformationToken
0x18002c1d5  nop     dword ptr [rax+rax+00h]
0x18002c1da  mov     ebx, eax
0x18002c1dc  test    eax, eax
0x18002c1de  jns     short loc_18002C233
0x18002c1e0  lea     rax, WPP_GLOBAL_Control
0x18002c1e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1ee  cmp     rcx, rax
0x18002c1f1  jz      short loc_18002C211
0x18002c1f3  test    byte ptr [rcx+1Ch], 1
0x18002c1f7  jz      short loc_18002C211
0x18002c1f9  mov     edx, 23h ; '#'
0x18002c1fe  mov     r9d, ebx
0x18002c201  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002c208  mov     rcx, [rcx+10h]
0x18002c20c  call    WPP_SF_d
0x18002c211  mov     r9d, 727h
0x18002c217  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002c21e  lea     rdx, aStatus; "Status"
0x18002c225  mov     ecx, ebx
0x18002c227  call    DebugTraceError
0x18002c22c  mov     ecx, ebx
0x18002c22e  jmp     loc_18002C3C0
0x18002c233  mov     r9d, r15d
0x18002c236  lea     r8, [rsi+r14]
0x18002c23a  lea     rax, [rsp+3D0h+var_380]
0x18002c23f  mov     [rsp+3D0h+var_3A0], rax
0x18002c244  lea     rax, [rsp+3D0h+var_388]
0x18002c249  mov     [rsp+3D0h+var_3A8], rax
0x18002c24e  mov     dword ptr [rsp+3D0h+ReturnLength], edi
0x18002c252  xor     edx, edx
0x18002c254  mov     rcx, [rbp+2D0h+TokenInformation]
0x18002c25b  call    cs:__imp_LsaIDeriveCredentialKey
0x18002c262  nop     dword ptr [rax+rax+00h]
0x18002c267  mov     ebx, eax
0x18002c269  test    eax, eax
0x18002c26b  jns     short loc_18002C275
0x18002c26d  mov     r9d, 736h
0x18002c273  jmp     short loc_18002C217
0x18002c275  mov     rcx, [rsp+3D0h+var_388]
0x18002c27a  mov     eax, [rcx+0Ch]
0x18002c27d  cmp     eax, 0FFFFh
0x18002c282  ja      loc_18002C39D
0x18002c288  mov     edx, [rcx+8]
0x18002c28b  cmp     edx, [rcx]
0x18002c28d  ja      loc_18002C39D
0x18002c293  add     eax, edx
0x18002c295  cmp     eax, [rcx]
0x18002c297  ja      loc_18002C39D
0x18002c29d  mov     eax, [rcx+4]
0x18002c2a0  mov     dword ptr [rbp+2D0h+var_34C+0Ch], eax
0x18002c2a3  mov     eax, [rcx+8]
0x18002c2a6  movups  xmm0, xmmword ptr [rax+rcx]
0x18002c2aa  movups  [rbp+2D0h+var_33C], xmm0
0x18002c2ae  mov     eax, [rax+rcx+10h]
0x18002c2b2  mov     dword ptr [rbp+2D0h+var_32C], eax
0x18002c2b5  mov     eax, [rcx+8]
0x18002c2b8  movups  xmm0, xmmword ptr [rax+rcx+14h]
0x18002c2bd  movups  [rbp+2D0h+var_32C+4], xmm0
0x18002c2c1  mov     eax, [rax+rcx+24h]
0x18002c2c5  mov     dword ptr [rbp+2D0h+var_31C+4], eax
0x18002c2c8  mov     rcx, r13; hToken
0x18002c2cb  call    cs:__imp_ImpersonateLoggedOnUser
0x18002c2d2  nop     dword ptr [rax+rax+00h]
0x18002c2d7  test    eax, eax
0x18002c2d9  jnz     short loc_18002C309
0x18002c2db  call    cs:__imp_GetLastError
0x18002c2e2  nop     dword ptr [rax+rax+00h]
0x18002c2e7  mov     ebx, eax
0x18002c2e9  mov     r9d, 75Ah
0x18002c2ef  mov     ecx, eax
0x18002c2f1  lea     rdx, aDwerror; "dwError"
0x18002c2f8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002c2ff  call    DebugTraceError
0x18002c304  jmp     loc_18002C3CE
0x18002c309  xor     r9d, r9d; unsigned int *
0x18002c30c  xor     r8d, r8d; unsigned __int16 **
0x18002c30f  xor     edx, edx; void *
0x18002c311  lea     rcx, [rbp+2D0h+var_310]; struct CRYPT_SERVER_CONTEXT *
0x18002c315  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18002c31a  mov     ebx, eax
0x18002c31c  call    cs:__imp_RevertToSelf
0x18002c323  nop     dword ptr [rax+rax+00h]
0x18002c328  test    ebx, ebx
0x18002c32a  jz      short loc_18002C336
0x18002c32c  mov     r9d, 764h
0x18002c332  mov     ecx, ebx
0x18002c334  jmp     short loc_18002C2F1
0x18002c336  mov     r12d, 1
0x18002c33c  mov     [rsp+3D0h+ReturnLength], 0; unsigned int *
0x18002c345  lea     r9, [rbp+2D0h+var_2D8]; unsigned int *
0x18002c349  xor     r8d, r8d; unsigned int *
0x18002c34c  lea     rdx, [rbp+2D0h+var_2DC]; unsigned int *
0x18002c350  call    ?GetDefaultAlgInfo@@YAXPEAXPEAK111@Z; GetDefaultAlgInfo(void *,ulong *,ulong *,ulong *,ulong *)
0x18002c355  mov     [rsp+3D0h+var_3A0], 0; unsigned int *
0x18002c35e  mov     [rsp+3D0h+var_3A8], 0; unsigned int *
0x18002c367  mov     dword ptr [rsp+3D0h+ReturnLength], 3; unsigned int
0x18002c36f  xor     r9d, r9d; struct DP_KEK *
0x18002c372  lea     r8, [rbp+2D0h+var_350]; struct DP_KEK *
0x18002c376  xor     edx, edx; unsigned int
0x18002c378  lea     rcx, [rbp+2D0h+var_310]; void *
0x18002c37c  call    ?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z; SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002c381  mov     ebx, eax
0x18002c383  test    eax, eax
0x18002c385  jz      short loc_18002C392
0x18002c387  mov     r9d, 77Eh
0x18002c38d  jmp     loc_18002C2EF
0x18002c392  lea     rcx, [rbp+2D0h+var_310]; void *
0x18002c396  call    ?UpdateLastMasterKeySync@@YAKPEAX@Z; UpdateLastMasterKeySync(void *)
0x18002c39b  jmp     short loc_18002C3CE
0x18002c39d  mov     r9d, 742h
0x18002c3a3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002c3aa  lea     rdx, aStatus; "Status"
0x18002c3b1  mov     ecx, 0C000000Dh
0x18002c3b6  call    DebugTraceError
0x18002c3bb  mov     ecx, 0C000000Dh; Status
0x18002c3c0  call    cs:__imp_RtlNtStatusToDosError
0x18002c3c7  nop     dword ptr [rax+rax+00h]
0x18002c3cc  mov     ebx, eax
0x18002c3ce  mov     [rsp+3D0h+var_378], 2
0x18002c3d6  mov     eax, cs:dword_18004C260
0x18002c3dc  cmp     eax, 5
0x18002c3df  jbe     short loc_18002C421
0x18002c3e1  mov     rdx, 400000000000h
0x18002c3eb  lea     rcx, dword_18004C260
0x18002c3f2  call    _tlgKeywordOn
0x18002c3f7  test    al, al
0x18002c3f9  jz      short loc_18002C421
0x18002c3fb  mov     [rsp+3D0h+var_38C], ebx
0x18002c3ff  lea     rax, [rsp+3D0h+var_38C]
0x18002c404  mov     [rsp+3D0h+ReturnLength], rax
0x18002c409  lea     r8, [rsp+3D0h+var_370]
0x18002c40e  lea     rdx, word_180044DAA
0x18002c415  lea     rcx, dword_18004C260
0x18002c41c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002c421  test    r12d, r12d
0x18002c424  jz      short loc_18002C431
0x18002c426  lea     rcx, [rbp+2D0h+var_310]; struct CRYPT_SERVER_CONTEXT *
0x18002c42a  call    ?CPSDeleteServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@@Z; CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *)
0x18002c42f  jmp     short loc_18002C441
0x18002c431  xor     r9d, r9d; struct DP_KEK *
0x18002c434  xor     r8d, r8d; struct DP_KEK *
0x18002c437  xor     edx, edx; unsigned int
0x18002c439  mov     rcx, r13; hToken
0x18002c43c  call    ?DPAPISynchronizeMasterKeys@@YAXPEAXKPEAUDP_KEK@@1@Z; DPAPISynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *)
0x18002c441  mov     rax, [rsp+3D0h+var_380]
0x18002c446  test    rax, rax
0x18002c449  jz      short loc_18002C45A
0x18002c44b  mov     rcx, [rsp+3D0h+var_388]
0x18002c450  test    rcx, rcx
0x18002c453  jz      short loc_18002C45A
0x18002c455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c45a  mov     ecx, 3Ch ; '<'
0x18002c45f  lea     rax, [rbp+2D0h+var_350]
0x18002c463  mov     byte ptr [rax], 0
0x18002c466  inc     rax
0x18002c469  sub     rcx, 1
0x18002c46d  jnz     short loc_18002C463
0x18002c46f  lea     rcx, [rsp+3D0h+var_378]
0x18002c474  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18002c479  mov     eax, ebx
0x18002c47b  mov     rcx, [rbp+2D0h+var_40]
0x18002c482  xor     rcx, rsp; StackCookie
0x18002c485  call    __security_check_cookie
0x18002c48a  mov     rbx, [rsp+3D0h+arg_10]
0x18002c492  add     rsp, 3A0h
0x18002c499  pop     r15
0x18002c49b  pop     r14
0x18002c49d  pop     r13
0x18002c49f  pop     r12
0x18002c4a1  pop     rdi
0x18002c4a2  pop     rsi
0x18002c4a3  pop     rbp
0x18002c4a4  retn
```
