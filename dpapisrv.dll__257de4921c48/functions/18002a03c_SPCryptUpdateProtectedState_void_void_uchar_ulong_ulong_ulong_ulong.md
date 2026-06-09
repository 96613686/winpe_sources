# SPCryptUpdateProtectedState(void *,void *,uchar *,ulong,ulong,ulong *,ulong *)

- ea: `0x18002a03c`
- end: `0x18002a4d3`
- name: `?SPCryptUpdateProtectedState@@YAKPEAX0PEAEKKPEAK2@Z`
- size: `1175`
- prototype: `__int64 __fastcall(_DWORD *, void *, unsigned __int8 *Memory, ULONG MemorySize, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024670`

## callees

- `0x180006c60`
- `0x180007f10`
- `0x18000a830`
- `0x18001ab70`
- `0x18001c9c0`
- `0x18001d810`
- `0x18002a03c`
- `0x18002e130`
- `0x18002e310`
- `0x180039d90`
- `0x18003e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a23e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a23e`
- `RPCRT4!RpcImpersonateClient` at `0x18002a275`
- `RPCRT4!RpcImpersonateClient` at `0x18002a275`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002a171`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002a171`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a2ac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a2ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a418`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a42c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a418`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a42c`
- `CRYPTBASE!SystemFunction041` at `0x18002a29e`
- `CRYPTBASE!SystemFunction041` at `0x18002a29e`
- `LSASRV!LsaIDeriveCredentialKey` at `0x18002a334`
- `LSASRV!LsaIDeriveCredentialKey` at `0x18002a334`
- `ntdll!RtlNtStatusToDosError` at `0x18002a2d9`
- `ntdll!RtlNtStatusToDosError` at `0x18002a2d9`

## string_xrefs

- `0x18002a1ca`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x18002a20e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x18002a2c2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x18002a3fd`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x18002a48d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`

## pseudocode

```c
__int64 __fastcall SPCryptUpdateProtectedState(
        _DWORD *a1,
        void *a2,
        unsigned __int8 *Memory,
        ULONG MemorySize,
        unsigned int a5,
        unsigned int *a6,
        unsigned int *a7)
{
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // r12
  int v13; // eax
  void *v14; // rcx
  unsigned int *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  ULONG v18; // ebx
  ULONG v19; // eax
  __int64 v20; // r9
  ULONG v21; // eax
  ULONG v22; // eax
  NTSTATUS v23; // ebx
  __int64 v24; // r9
  NTSTATUS v25; // ecx
  __int64 v26; // r15
  unsigned int v27; // eax
  unsigned int v28; // edx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  int *v33; // rax
  int v35; // [rsp+50h] [rbp-81h]
  unsigned __int16 *v36; // [rsp+58h] [rbp-79h] BYREF
  unsigned __int16 *v37; // [rsp+60h] [rbp-71h] BYREF
  unsigned int *v38; // [rsp+68h] [rbp-69h] BYREF
  unsigned int *v39; // [rsp+70h] [rbp-61h]
  void (*v40)(void); // [rsp+78h] [rbp-59h] BYREF
  unsigned int *v41; // [rsp+80h] [rbp-51h]
  int v42; // [rsp+88h] [rbp-49h] BYREF
  __int128 v43; // [rsp+8Ch] [rbp-45h]
  __int128 v44; // [rsp+9Ch] [rbp-35h]
  _BYTE v45[24]; // [rsp+ACh] [rbp-25h] BYREF

  v41 = a6;
  v9 = 0;
  v36 = 0;
  v10 = 0;
  v37 = 0;
  v42 = 0;
  v38 = 0;
  v40 = 0;
  v39 = a7;
  v43 = 0;
  v44 = 0;
  memset(v45, 0, sizeof(v45));
  v13 = IsDomainBackupRequired(a1);
  v35 = v13;
  if ( a1 )
  {
    GetDefaultAlgInfo(v14, a1 + 13, 0, a1 + 14, 0);
    v13 = v35;
  }
  if ( a6 )
    *a6 = 0;
  v15 = v39;
  if ( v39 )
    *v39 = 0;
  if ( a2 )
  {
    if ( !IsValidSid(a2) )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_13;
      v17 = 57;
      goto LABEL_12;
    }
    v21 = CPSGetUserStorageArea(a1, a2, 0, 0, &v36);
    v18 = v21;
    if ( v21 )
    {
      DebugTraceError(v21, "dwResult", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp", 2307);
      v9 = v36;
      goto LABEL_45;
    }
    v22 = CPSGetUserStorageArea(a1, 0, 1u, 1, &v37);
    v18 = v22;
    if ( v22 )
    {
      DebugTraceError(v22, "dwResult", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp", 2320);
      v9 = v36;
      v10 = v37;
      goto LABEL_45;
    }
    v10 = v37;
    v9 = v36;
    LODWORD(v36) = _o__wcsicmp(v36, v37) != 0;
    if ( Memory )
    {
      if ( MemorySize < 8 || (MemorySize & 7) != 0 )
      {
        v31 = 13;
        v20 = 2340;
        v18 = 13;
        goto LABEL_44;
      }
      v19 = RpcImpersonateClient(*((RPC_BINDING_HANDLE *)a1 + 1));
      v18 = v19;
      if ( v19 )
      {
        v20 = 2348;
        goto LABEL_43;
      }
      v23 = SystemFunction041(Memory, MemorySize, 2u);
      RevertToSelf();
      if ( v23 < 0 )
      {
        v24 = 2364;
LABEL_32:
        DebugTraceError(
          (unsigned int)v23,
          "sResult",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          v24);
        v25 = v23;
LABEL_33:
        v18 = RtlNtStatusToDosError(v25);
        goto LABEL_45;
      }
      if ( (unsigned __int8)(Memory[MemorySize - 1] - 2) > 6u )
      {
        v31 = 13;
        v20 = 2375;
        v18 = 13;
        goto LABEL_44;
      }
      v26 = MemorySize - Memory[MemorySize - 1];
      *(_WORD *)&Memory[v26] = 0;
      v23 = LsaIDeriveCredentialKey(a2, 0, Memory, (unsigned int)v26, 2, &v38, &v40);
      if ( v23 < 0 )
      {
        v24 = 2397;
        goto LABEL_32;
      }
      v27 = v38[3];
      if ( v27 > 0xFFFF || (v28 = v38[2], v28 > *v38) || v28 + v27 > *v38 )
      {
        DebugTraceError(
          3221225485LL,
          "sResult",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          2409);
        v25 = -1073741811;
        goto LABEL_33;
      }
      HIDWORD(v43) = v38[1];
      v29 = v38[2];
      v44 = *(_OWORD *)((char *)v38 + v29);
      *(_DWORD *)v45 = *(unsigned int *)((char *)v38 + v29 + 16);
      v30 = v38[2];
      *(_OWORD *)&v45[4] = *(_OWORD *)((char *)v38 + v30 + 20);
      *(_DWORD *)&v45[20] = *(unsigned int *)((char *)v38 + v30 + 36);
    }
    v19 = SynchronizeSidMasterKeys(
            a1,
            a2,
            0,
            (int)v36,
            (struct DP_KEK *)((unsigned __int64)&v42 & -(__int64)(Memory != 0)),
            0,
            v35 != 0 ? 3 : 0,
            v41,
            v39);
    v18 = v19;
    if ( !v19 )
      goto LABEL_45;
    v20 = 2447;
    goto LABEL_43;
  }
  if ( !Memory )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_13;
    v17 = 56;
LABEL_12:
    WPP_SF_(*(_QWORD *)(v16 + 16), v17, WPP_96027a338e1f3ff10006943bca18f271_Traceguids);
LABEL_13:
    v18 = 87;
    goto LABEL_49;
  }
  v19 = SynchronizeMasterKeys(a1, 0, 0, 0, v13 != 0 ? 3 : 0, a6, v15);
  v18 = v19;
  if ( v19 )
  {
    v20 = 2473;
LABEL_43:
    v31 = v19;
LABEL_44:
    DebugTraceError(v31, "dwResult", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp", v20);
    goto LABEL_45;
  }
  UpdateLastMasterKeySync(a1);
LABEL_45:
  if ( v9 )
    LocalFree(v9);
  if ( v10 )
    LocalFree(v10);
LABEL_49:
  if ( v40 && v38 )
    v40();
  v32 = 60;
  v33 = &v42;
  do
  {
    *(_BYTE *)v33 = 0;
    v33 = (int *)((char *)v33 + 1);
    --v32;
  }
  while ( v32 );
  return v18;
}

```

## disassembly

```asm
0x18002a03c  push    rbp
0x18002a03e  push    rbx
0x18002a03f  push    rsi
0x18002a040  push    rdi
0x18002a041  push    r12
0x18002a043  push    r13
0x18002a045  push    r14
0x18002a047  push    r15
0x18002a049  lea     rbp, [rsp-7]
0x18002a04e  sub     rsp, 0D8h
0x18002a055  mov     rax, cs:__security_cookie
0x18002a05c  xor     rax, rsp
0x18002a05f  mov     [rbp+3Fh+var_48], rax
0x18002a063  mov     rbx, [rbp+3Fh+arg_28]
0x18002a067  xorps   xmm0, xmm0
0x18002a06a  mov     rdi, rcx
0x18002a06d  mov     [rbp+3Fh+var_90], rbx
0x18002a071  xor     ecx, ecx
0x18002a073  mov     r13, rdx
0x18002a076  mov     rdx, [rbp+3Fh+arg_30]
0x18002a07a  mov     esi, ecx
0x18002a07c  mov     [rbp+3Fh+var_B8], rcx
0x18002a080  mov     r12d, ecx
0x18002a083  mov     [rbp+3Fh+var_B0], rcx
0x18002a087  xor     eax, eax
0x18002a089  mov     [rbp+3Fh+var_88], ecx
0x18002a08c  mov     r15d, r9d
0x18002a08f  mov     [rbp+3Fh+var_A8], rcx
0x18002a093  mov     r14, r8
0x18002a096  mov     [rbp+3Fh+var_98], rcx
0x18002a09a  mov     rcx, rdi; void *
0x18002a09d  mov     [rbp+3Fh+var_A0], rdx
0x18002a0a1  movups  [rbp+3Fh+var_84], xmm0
0x18002a0a5  mov     [rbp+3Fh+var_54], rax
0x18002a0a9  movups  [rbp+3Fh+var_74], xmm0
0x18002a0ad  movups  [rbp+3Fh+var_64], xmm0
0x18002a0b1  call    ?IsDomainBackupRequired@@YAHPEAX@Z; IsDomainBackupRequired(void *)
0x18002a0b6  mov     [rsp+110h+var_C0], eax
0x18002a0ba  test    rdi, rdi
0x18002a0bd  jz      short loc_18002A0D8
0x18002a0bf  lea     r9, [rdi+38h]; unsigned int *
0x18002a0c3  mov     [rsp+110h+var_F0], r12; unsigned int *
0x18002a0c8  lea     rdx, [rdi+34h]; unsigned int *
0x18002a0cc  xor     r8d, r8d; unsigned int *
0x18002a0cf  call    ?GetDefaultAlgInfo@@YAXPEAXPEAK111@Z; GetDefaultAlgInfo(void *,ulong *,ulong *,ulong *,ulong *)
0x18002a0d4  mov     eax, [rsp+110h+var_C0]
0x18002a0d8  test    rbx, rbx
0x18002a0db  jz      short loc_18002A0DF
0x18002a0dd  mov     [rbx], esi
0x18002a0df  mov     rcx, [rbp+3Fh+var_A0]
0x18002a0e3  test    rcx, rcx
0x18002a0e6  jz      short loc_18002A0EA
0x18002a0e8  mov     [rcx], esi
0x18002a0ea  test    r13, r13
0x18002a0ed  jnz     short loc_18002A16E
0x18002a0ef  test    r14, r14
0x18002a0f2  jnz     short loc_18002A12B
0x18002a0f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0fb  lea     rax, WPP_GLOBAL_Control
0x18002a102  cmp     rcx, rax
0x18002a105  jz      short loc_18002A121
0x18002a107  test    byte ptr [rcx+1Ch], 1
0x18002a10b  jz      short loc_18002A121
0x18002a10d  lea     edx, [r13+38h]
0x18002a111  mov     rcx, [rcx+10h]
0x18002a115  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x18002a11c  call    WPP_SF_
0x18002a121  mov     ebx, 57h ; 'W'
0x18002a126  jmp     loc_18002A438
0x18002a12b  mov     [rsp+110h+var_E0], rcx; unsigned int *
0x18002a130  neg     eax
0x18002a132  mov     [rsp+110h+var_E8], rbx; unsigned int *
0x18002a137  mov     rcx, rdi; void *
0x18002a13a  sbb     eax, eax
0x18002a13c  xor     r9d, r9d; struct DP_KEK *
0x18002a13f  and     eax, 3
0x18002a142  xor     r8d, r8d; struct DP_KEK *
0x18002a145  xor     edx, edx; unsigned int
0x18002a147  mov     dword ptr [rsp+110h+var_F0], eax; unsigned int
0x18002a14b  call    ?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z; SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002a150  mov     ebx, eax
0x18002a152  test    eax, eax
0x18002a154  jnz     short loc_18002A163
0x18002a156  mov     rcx, rdi; void *
0x18002a159  call    ?UpdateLastMasterKeySync@@YAKPEAX@Z; UpdateLastMasterKeySync(void *)
0x18002a15e  jmp     loc_18002A410
0x18002a163  mov     r9d, 9A9h
0x18002a169  jmp     loc_18002A3FB
0x18002a16e  mov     rcx, r13; pSid
0x18002a171  call    cs:__imp_IsValidSid
0x18002a178  nop     dword ptr [rax+rax+00h]
0x18002a17d  test    eax, eax
0x18002a17f  jnz     short loc_18002A1A4
0x18002a181  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a188  lea     rax, WPP_GLOBAL_Control
0x18002a18f  cmp     rcx, rax
0x18002a192  jz      short loc_18002A121
0x18002a194  test    byte ptr [rcx+1Ch], 1
0x18002a198  jz      short loc_18002A121
0x18002a19a  mov     edx, 39h ; '9'
0x18002a19f  jmp     loc_18002A111
0x18002a1a4  lea     rax, [rbp+3Fh+var_B8]
0x18002a1a8  xor     r9d, r9d; int
0x18002a1ab  xor     r8d, r8d; int
0x18002a1ae  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x18002a1b3  mov     rdx, r13; void *
0x18002a1b6  mov     rcx, rdi; void *
0x18002a1b9  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x18002a1be  mov     ebx, eax
0x18002a1c0  test    eax, eax
0x18002a1c2  jz      short loc_18002A1E8
0x18002a1c4  mov     r9d, 903h
0x18002a1ca  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a1d1  lea     rdx, aDwresult; "dwResult"
0x18002a1d8  mov     ecx, eax
0x18002a1da  call    DebugTraceError
0x18002a1df  mov     rsi, [rbp+3Fh+var_B8]
0x18002a1e3  jmp     loc_18002A410
0x18002a1e8  xor     edx, edx; void *
0x18002a1ea  lea     rax, [rbp+3Fh+var_B0]
0x18002a1ee  mov     rcx, rdi; void *
0x18002a1f1  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x18002a1f6  lea     r9d, [rdx+1]; int
0x18002a1fa  mov     r8d, r9d; int
0x18002a1fd  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x18002a202  mov     ebx, eax
0x18002a204  test    eax, eax
0x18002a206  jz      short loc_18002A230
0x18002a208  mov     r9d, 910h
0x18002a20e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a215  lea     rdx, aDwresult; "dwResult"
0x18002a21c  mov     ecx, eax
0x18002a21e  call    DebugTraceError
0x18002a223  mov     rsi, [rbp+3Fh+var_B8]
0x18002a227  mov     r12, [rbp+3Fh+var_B0]
0x18002a22b  jmp     loc_18002A410
0x18002a230  mov     r12, [rbp+3Fh+var_B0]
0x18002a234  mov     rsi, [rbp+3Fh+var_B8]
0x18002a238  mov     rdx, r12
0x18002a23b  mov     rcx, rsi
0x18002a23e  call    cs:__imp__o__wcsicmp
0x18002a245  nop     dword ptr [rax+rax+00h]
0x18002a24a  xor     ecx, ecx
0x18002a24c  test    eax, eax
0x18002a24e  setnz   cl
0x18002a251  mov     dword ptr [rbp+3Fh+var_B8], ecx
0x18002a254  test    r14, r14
0x18002a257  jz      loc_18002A3A3
0x18002a25d  cmp     r15d, 8
0x18002a261  jb      loc_18002A4C1
0x18002a267  test    r15b, 7
0x18002a26b  jnz     loc_18002A4C1
0x18002a271  mov     rcx, [rdi+8]; BindingHandle
0x18002a275  call    cs:__imp_RpcImpersonateClient
0x18002a27c  nop     dword ptr [rax+rax+00h]
0x18002a281  mov     ebx, eax
0x18002a283  test    eax, eax
0x18002a285  jz      short loc_18002A292
0x18002a287  mov     r9d, 92Ch
0x18002a28d  jmp     loc_18002A3FB
0x18002a292  mov     r8d, 2; OptionFlags
0x18002a298  mov     edx, r15d; MemorySize
0x18002a29b  mov     rcx, r14; Memory
0x18002a29e  call    cs:__imp_SystemFunction041
0x18002a2a5  nop     dword ptr [rax+rax+00h]
0x18002a2aa  mov     ebx, eax
0x18002a2ac  call    cs:__imp_RevertToSelf
0x18002a2b3  nop     dword ptr [rax+rax+00h]
0x18002a2b8  test    ebx, ebx
0x18002a2ba  jns     short loc_18002A2EC
0x18002a2bc  mov     r9d, 93Ch
0x18002a2c2  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a2c9  mov     ecx, ebx
0x18002a2cb  lea     rdx, aSresult; "sResult"
0x18002a2d2  call    DebugTraceError
0x18002a2d7  mov     ecx, ebx; Status
0x18002a2d9  call    cs:__imp_RtlNtStatusToDosError
0x18002a2e0  nop     dword ptr [rax+rax+00h]
0x18002a2e5  mov     ebx, eax
0x18002a2e7  jmp     loc_18002A410
0x18002a2ec  lea     eax, [r15-1]
0x18002a2f0  mov     ecx, eax
0x18002a2f2  mov     al, [rax+r14]
0x18002a2f6  sub     al, 2
0x18002a2f8  cmp     al, 6
0x18002a2fa  ja      loc_18002A4AF
0x18002a300  movzx   eax, byte ptr [rcx+r14]
0x18002a305  mov     r8, r14
0x18002a308  sub     r15d, eax
0x18002a30b  xor     ecx, ecx
0x18002a30d  lea     rax, [rbp+3Fh+var_98]
0x18002a311  mov     r9d, r15d
0x18002a314  mov     [rsp+110h+var_E0], rax
0x18002a319  xor     edx, edx
0x18002a31b  lea     rax, [rbp+3Fh+var_A8]
0x18002a31f  mov     [r15+r14], cx
0x18002a324  mov     rcx, r13
0x18002a327  mov     [rsp+110h+var_E8], rax
0x18002a32c  mov     dword ptr [rsp+110h+var_F0], 2
0x18002a334  call    cs:__imp_LsaIDeriveCredentialKey
0x18002a33b  nop     dword ptr [rax+rax+00h]
0x18002a340  mov     ebx, eax
0x18002a342  test    eax, eax
0x18002a344  jns     short loc_18002A351
0x18002a346  mov     r9d, 95Dh
0x18002a34c  jmp     loc_18002A2C2
0x18002a351  mov     rcx, [rbp+3Fh+var_A8]
0x18002a355  mov     eax, [rcx+0Ch]
0x18002a358  cmp     eax, 0FFFFh
0x18002a35d  ja      loc_18002A487
0x18002a363  mov     edx, [rcx+8]
0x18002a366  cmp     edx, [rcx]
0x18002a368  ja      loc_18002A487
0x18002a36e  add     eax, edx
0x18002a370  cmp     eax, [rcx]
0x18002a372  ja      loc_18002A487
0x18002a378  mov     eax, [rcx+4]
0x18002a37b  mov     dword ptr [rbp+3Fh+var_84+0Ch], eax
0x18002a37e  mov     eax, [rcx+8]
0x18002a381  movups  xmm0, xmmword ptr [rax+rcx]
0x18002a385  movups  [rbp+3Fh+var_74], xmm0
0x18002a389  mov     eax, [rax+rcx+10h]
0x18002a38d  mov     dword ptr [rbp+3Fh+var_64], eax
0x18002a390  mov     eax, [rcx+8]
0x18002a393  movups  xmm0, xmmword ptr [rax+rcx+14h]
0x18002a398  movups  [rbp+3Fh+var_64+4], xmm0
0x18002a39c  mov     eax, [rax+rcx+24h]
0x18002a3a0  mov     dword ptr [rbp+3Fh+var_54+4], eax
0x18002a3a3  neg     [rsp+110h+var_C0]
0x18002a3a7  lea     rdx, [rbp+3Fh+var_88]
0x18002a3ab  mov     r9d, dword ptr [rbp+3Fh+var_B8]; int
0x18002a3af  sbb     ecx, ecx
0x18002a3b1  and     ecx, 3
0x18002a3b4  neg     r14
0x18002a3b7  sbb     rax, rax
0x18002a3ba  xor     r8d, r8d; unsigned int
0x18002a3bd  and     rax, rdx
0x18002a3c0  mov     rdx, [rbp+3Fh+var_A0]
0x18002a3c4  mov     [rsp+110h+var_D0], rdx; unsigned int *
0x18002a3c9  mov     rdx, [rbp+3Fh+var_90]
0x18002a3cd  mov     [rsp+110h+var_D8], rdx; unsigned int *
0x18002a3d2  mov     rdx, r13; void *
0x18002a3d5  mov     dword ptr [rsp+110h+var_E0], ecx; unsigned int
0x18002a3d9  mov     rcx, rdi; void *
0x18002a3dc  mov     [rsp+110h+var_E8], 0; struct DP_KEK *
0x18002a3e5  mov     [rsp+110h+var_F0], rax; struct DP_KEK *
0x18002a3ea  call    ?SynchronizeSidMasterKeys@@YAKPEAX0KHPEAUDP_KEK@@1KPEAK2@Z; SynchronizeSidMasterKeys(void *,void *,ulong,int,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002a3ef  mov     ebx, eax
0x18002a3f1  test    eax, eax
0x18002a3f3  jz      short loc_18002A410
0x18002a3f5  mov     r9d, 98Fh
0x18002a3fb  mov     ecx, eax
0x18002a3fd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a404  lea     rdx, aDwresult; "dwResult"
0x18002a40b  call    DebugTraceError
0x18002a410  test    rsi, rsi
0x18002a413  jz      short loc_18002A424
0x18002a415  mov     rcx, rsi; hMem
0x18002a418  call    cs:__imp_LocalFree
0x18002a41f  nop     dword ptr [rax+rax+00h]
0x18002a424  test    r12, r12
0x18002a427  jz      short loc_18002A438
0x18002a429  mov     rcx, r12; hMem
0x18002a42c  call    cs:__imp_LocalFree
0x18002a433  nop     dword ptr [rax+rax+00h]
0x18002a438  mov     rax, [rbp+3Fh+var_98]
0x18002a43c  test    rax, rax
0x18002a43f  jz      short loc_18002A44F
0x18002a441  mov     rcx, [rbp+3Fh+var_A8]
0x18002a445  test    rcx, rcx
0x18002a448  jz      short loc_18002A44F
0x18002a44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a44f  mov     ecx, 3Ch ; '<'
0x18002a454  lea     rax, [rbp+3Fh+var_88]
0x18002a458  mov     byte ptr [rax], 0
0x18002a45b  inc     rax
0x18002a45e  sub     rcx, 1
0x18002a462  jnz     short loc_18002A458
0x18002a464  mov     eax, ebx
0x18002a466  mov     rcx, [rbp+3Fh+var_48]
0x18002a46a  xor     rcx, rsp; StackCookie
0x18002a46d  call    __security_check_cookie
0x18002a472  add     rsp, 0D8h
0x18002a479  pop     r15
0x18002a47b  pop     r14
0x18002a47d  pop     r13
0x18002a47f  pop     r12
0x18002a481  pop     rdi
0x18002a482  pop     rsi
0x18002a483  pop     rbx
0x18002a484  pop     rbp
0x18002a485  retn
0x18002a487  mov     r9d, 969h
0x18002a48d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a494  lea     rdx, aSresult; "sResult"
0x18002a49b  mov     ecx, 0C000000Dh
0x18002a4a0  call    DebugTraceError
0x18002a4a5  mov     ecx, 0C000000Dh
0x18002a4aa  jmp     loc_18002A2D9
0x18002a4af  mov     ecx, 0Dh
  ... truncated ...
```
