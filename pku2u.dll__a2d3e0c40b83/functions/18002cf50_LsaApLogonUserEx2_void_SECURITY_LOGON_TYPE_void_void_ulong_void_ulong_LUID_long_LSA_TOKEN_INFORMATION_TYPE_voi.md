# LsaApLogonUserEx2(void * *,_SECURITY_LOGON_TYPE,void *,void *,ulong,void * *,ulong *,_LUID *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x18002cf50`
- end: `0x18002d5ef`
- name: `?LsaApLogonUserEx2@@YAJPEAPEAXW4_SECURITY_LOGON_TYPE@@PEAX2K0PEAKPEAU_LUID@@PEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@0PEAPEAU_UNICODE_STRING@@77PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `1695`
- prototype: `int(void **, enum _SECURITY_LOGON_TYPE, void *, void *, unsigned int, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800057f0`
- `0x180016860`
- `0x18001a0b0`
- `0x180021a54`
- `0x180023ce0`
- `0x180023d9c`
- `0x18002b408`
- `0x18002cf50`
- `0x18002d5f8`
- `0x18003b41c`
- `0x180046010`

## import_xrefs

- `LSASRV!LsaIAddNamesToLogonSession` at `0x18002d510`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x18002d510`

## string_xrefs

- `0x18002d218`: `onecore\ds\security\protocols\pku2u\logonapi.cxx`
- `0x18002d37f`: `onecore\ds\security\protocols\pku2u\logonapi.cxx`
- `0x18002d45c`: `onecore\ds\security\protocols\pku2u\logonapi.cxx`

## pseudocode

```c
__int64 __fastcall LsaApLogonUserEx2(
        void **a1,
        enum _SECURITY_LOGON_TYPE a2,
        _DWORD *a3,
        unsigned __int64 a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7,
        struct _LUID *a8,
        int *a9,
        enum _LSA_TOKEN_INFORMATION_TYPE *a10,
        void **a11,
        struct _UNICODE_STRING **a12,
        struct _UNICODE_STRING **a13,
        struct _UNICODE_STRING **a14,
        struct _SECPKG_PRIMARY_CRED *a15,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a16)
{
  int *v16; // r13
  struct _UNICODE_STRING **v18; // rbx
  _QWORD *v19; // r14
  struct _SECPKG_PRIMARY_CRED *LocallyUniqueId; // rdi
  void **v22; // rax
  struct _UNICODE_STRING **v23; // rax
  struct _LUID *v24; // r12
  struct _UNICODE_STRING *v25; // rax
  int v26; // ebx
  _DWORD *v27; // rsi
  void **v28; // r15
  struct _UNICODE_STRING **v29; // rdi
  struct _UNICODE_STRING **v30; // rdi
  struct _UNICODE_STRING **v31; // rdi
  __int64 v33; // rax
  struct _UNICODE_STRING *v34; // rax
  unsigned int v35; // ebx
  void *v36; // rdx
  int v37; // eax
  unsigned __int8 v38; // r8
  unsigned __int8 v39; // r8
  unsigned __int8 v40; // r8
  bool v41; // zf
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v42; // [rsp+40h] [rbp-38h] BYREF
  void *v43[2]; // [rsp+48h] [rbp-30h] BYREF
  __int128 v44; // [rsp+58h] [rbp-20h] BYREF
  __int64 v45; // [rsp+68h] [rbp-10h]

  v16 = a9;
  v18 = a13;
  v19 = a3;
  LocallyUniqueId = a15;
  *a6 = 0;
  v43[0] = a3;
  v42 = 0;
  *a7 = 0;
  v22 = a11;
  *v16 = 0;
  *v22 = 0;
  *a12 = 0;
  v23 = a14;
  *v18 = 0;
  *v23 = 0;
  *a16 = 0;
  memset_0(LocallyUniqueId, 0, sizeof(struct _SECPKG_PRIMARY_CRED));
  v24 = a8;
  *a8 = 0;
  v25 = (struct _UNICODE_STRING *)((__int64 (__fastcall *)(__int64))Pku2uGlobalLsaFunctions->AllocateLsaHeap)(16);
  *a12 = v25;
  if ( !v25
    || (v33 = ((__int64 (__fastcall *)(__int64))Pku2uGlobalLsaFunctions->AllocateLsaHeap)(16),
        (*v18 = (struct _UNICODE_STRING *)v33) == 0)
    || (v34 = (struct _UNICODE_STRING *)((__int64 (__fastcall *)(__int64))Pku2uGlobalLsaFunctions->AllocateLsaHeap)(16),
        (*a14 = v34) == 0) )
  {
    v26 = -1073741670;
LABEL_3:
    v27 = a3;
LABEL_4:
    v28 = a11;
    if ( *a11 )
    {
      ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
      *v28 = 0;
    }
    KerbFreeString2(&LocallyUniqueId->DownlevelName);
    KerbFreeString2(&LocallyUniqueId->DomainName);
    KerbFreeString2(&LocallyUniqueId->LogonServer);
    KerbFreeString2(&LocallyUniqueId->Password);
    if ( LocallyUniqueId->UserSid )
      ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
    memset_0(LocallyUniqueId, 0, sizeof(struct _SECPKG_PRIMARY_CRED));
    v29 = a12;
    if ( *a12 )
    {
      KerbFreeString2(*a12);
      ((void (__fastcall *)(struct _UNICODE_STRING *))Pku2uGlobalLsaFunctions->FreeLsaHeap)(*v29);
      *v29 = 0;
    }
    v30 = a14;
    if ( *a14 )
    {
      KerbFreeString2(*a14);
      ((void (__fastcall *)(struct _UNICODE_STRING *))Pku2uGlobalLsaFunctions->FreeLsaHeap)(*v30);
      *v30 = 0;
    }
    v31 = a13;
    if ( *a13 )
    {
      KerbFreeString2(*a13);
      ((void (__fastcall *)(struct _UNICODE_STRING *))Pku2uGlobalLsaFunctions->FreeLsaHeap)(*v31);
      *v31 = 0;
    }
    if ( *v24 )
      ((void (__fastcall *)(struct _LUID *))Pku2uGlobalLsaFunctions->DeleteLogonSession)(v24);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
        (unsigned int)v26,
        *v16);
    goto LABEL_19;
  }
  if ( a2 != Network )
  {
    v26 = -1073741557;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
        a2,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
        178);
    goto LABEL_3;
  }
  v35 = a5;
  v27 = a3;
  if ( a5 < 4 )
  {
LABEL_32:
    v26 = -1073741811;
    goto LABEL_4;
  }
  if ( *a3 != 14 )
  {
    v26 = -1073741821;
    goto LABEL_3;
  }
  v45 = 0;
  v44 = 0;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))Pku2uGlobalLsaFunctions->GetCallInfo)(&v44) )
  {
    v26 = -1073741595;
    goto LABEL_3;
  }
  if ( (BYTE8(v44) & 0x40) != 0 )
  {
    v37 = Pku2uConvertWOWLogonBuffer(a3, v36, &a5, (enum _PKU2U_LOGON_SUBMIT_TYPE)*a3, v43);
    v19 = v43[0];
    v26 = v37;
    if ( v37 < 0 )
    {
      v27 = a3;
      goto LABEL_41;
    }
    v35 = a5;
    v27 = v43[0];
  }
  else
  {
    v27 = a3;
  }
  if ( v35 < 0x38 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
        v35,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
        149);
    goto LABEL_32;
  }
  v26 = Pku2uS4UToSelfLogon(v19, a4, v35, a10, a11, &LocallyUniqueId->LogonId, &v42);
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
        (unsigned int)v26);
    goto LABEL_41;
  }
  v26 = ((__int64 (__fastcall *)(struct _SECPKG_PRIMARY_CRED *))Pku2uGlobalLsaFunctions->CreateLogonSession)(LocallyUniqueId);
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_7e7e3542d015350663d795ca61e34c82_Traceguids,
        v26,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\logonapi.cxx",
        189);
LABEL_41:
    if ( v26 > -1073740924 )
    {
      if ( v26 > -1073740916 )
      {
        if ( v26 != -1073740915
          && v26 != -1073740788
          && v26 != -1073740787
          && v26 != -1073740786
          && v26 != -1073740785
          && v26 != -1073740753 )
        {
          goto LABEL_4;
        }
        goto LABEL_95;
      }
      if ( v26 != -1073740916
        && v26 != -1073740923
        && v26 != -1073740922
        && v26 != -1073740921
        && v26 != -1073740919
        && v26 != -1073740918 )
      {
        v41 = v26 == -1073740917;
LABEL_79:
        if ( !v41 )
          goto LABEL_4;
      }
    }
    else
    {
      if ( v26 == -1073740924 )
        goto LABEL_95;
      if ( v26 <= -1073741421 )
      {
        if ( v26 == -1073741421 )
        {
          *v16 = -1073741421;
          goto LABEL_4;
        }
        if ( v26 != -1073741724 && v26 != -1073741718 )
        {
          if ( v26 == -1073741714 )
          {
            *v16 = -1073741714;
            goto LABEL_4;
          }
          if ( v26 != -1073741713 && v26 != -1073741712 && v26 != -1073741711 && v26 != -1073741710 )
            goto LABEL_4;
          goto LABEL_52;
        }
        goto LABEL_95;
      }
      if ( v26 != -1073741063 )
      {
        if ( v26 == -1073741062 )
        {
LABEL_52:
          *v16 = v26;
          v26 = -1073741714;
          goto LABEL_4;
        }
        if ( v26 != -1073741024 && v26 != -1073740928 && v26 != -1073740927 )
        {
          v41 = v26 == -1073740925;
          goto LABEL_79;
        }
      }
    }
LABEL_95:
    *v16 = v26;
    v26 = -1073741715;
    goto LABEL_4;
  }
  *v24 = LocallyUniqueId->LogonId;
  v26 = KerbDuplicateStringEx2(*a14, &LocallyUniqueId->LogonServer, v38);
  if ( v26 < 0 )
    goto LABEL_41;
  v26 = KerbDuplicateStringEx2(*a13, &LocallyUniqueId->DomainName, v39);
  if ( v26 < 0 )
    goto LABEL_41;
  v26 = KerbDuplicateStringEx2(*a12, &LocallyUniqueId->DownlevelName, v40);
  if ( v26 < 0 )
    goto LABEL_41;
  if ( !v42 )
    goto LABEL_21;
  v43[0] = (void *)3;
  v43[1] = (char *)v42 + 64;
  LsaIAddNamesToLogonSession(v24, 1, v43);
LABEL_19:
  if ( v42 )
    Pku2uFree(v42);
LABEL_21:
  if ( v19 && v19 != (_QWORD *)v27 )
    Pku2uFree(v19);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18002cf50  mov     [rsp-40h+arg_10], r8
0x18002cf55  push    rbp
0x18002cf56  push    rbx
0x18002cf57  push    rsi
0x18002cf58  push    rdi
0x18002cf59  push    r12
0x18002cf5b  push    r13
0x18002cf5d  push    r14
0x18002cf5f  push    r15
0x18002cf61  mov     rbp, rsp
0x18002cf64  sub     rsp, 78h
0x18002cf68  mov     rax, [rbp+arg_28]
0x18002cf6c  xor     ecx, ecx
0x18002cf6e  mov     r13, [rbp+arg_40]
0x18002cf75  mov     esi, edx
0x18002cf77  mov     rbx, [rbp+arg_60]
0x18002cf7e  mov     r14, r8
0x18002cf81  mov     rdi, [rbp+arg_70]
0x18002cf88  xor     edx, edx; Val
0x18002cf8a  mov     [rax], rcx
0x18002cf8d  mov     r15, r9
0x18002cf90  mov     rax, [rbp+arg_30]
0x18002cf94  mov     [rbp+var_30], r8
0x18002cf98  mov     r8d, 0C8h; Size
0x18002cf9e  mov     [rbp+var_38], rcx
0x18002cfa2  mov     [rax], ecx
0x18002cfa4  mov     rax, [rbp+arg_50]
0x18002cfab  mov     [r13+0], ecx
0x18002cfaf  mov     [rax], rcx
0x18002cfb2  mov     rax, [rbp+arg_58]
0x18002cfb9  mov     [rax], rcx
0x18002cfbc  mov     rax, [rbp+arg_68]
0x18002cfc3  mov     [rbx], rcx
0x18002cfc6  mov     [rax], rcx
0x18002cfc9  mov     rax, [rbp+arg_78]
0x18002cfd0  mov     [rax], rcx
0x18002cfd3  mov     rcx, rdi; void *
0x18002cfd6  call    memset_0
0x18002cfdb  mov     r12, [rbp+arg_38]
0x18002cfe2  xor     eax, eax
0x18002cfe4  mov     ecx, 10h
0x18002cfe9  mov     [r12], rax
0x18002cfed  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002cff4  mov     rax, [rax+28h]
0x18002cff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cffd  mov     rcx, [rbp+arg_58]
0x18002d004  mov     [rcx], rax
0x18002d007  test    rax, rax
0x18002d00a  jnz     loc_18002D1A0
0x18002d010  mov     ebx, 0C000009Ah
0x18002d015  mov     rsi, [rbp+arg_10]
0x18002d019  mov     r15, [rbp+arg_50]
0x18002d020  mov     rcx, [r15]
0x18002d023  test    rcx, rcx
0x18002d026  jz      short loc_18002D03F
0x18002d028  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d02f  mov     rax, [rax+30h]
0x18002d033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d038  mov     qword ptr [r15], 0
0x18002d03f  lea     rcx, [rdi+8]; struct _UNICODE_STRING *
0x18002d043  call    ?KerbFreeString2@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString2(_UNICODE_STRING *)
0x18002d048  lea     rcx, [rdi+18h]; struct _UNICODE_STRING *
0x18002d04c  call    ?KerbFreeString2@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString2(_UNICODE_STRING *)
0x18002d051  lea     rcx, [rdi+78h]; struct _UNICODE_STRING *
0x18002d055  call    ?KerbFreeString2@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString2(_UNICODE_STRING *)
0x18002d05a  lea     rcx, [rdi+28h]; struct _UNICODE_STRING *
0x18002d05e  call    ?KerbFreeString2@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString2(_UNICODE_STRING *)
0x18002d063  mov     rcx, [rdi+48h]
0x18002d067  test    rcx, rcx
0x18002d06a  jz      short loc_18002D07C
0x18002d06c  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d073  mov     rax, [rax+30h]
0x18002d077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d07c  xor     edx, edx; Val
0x18002d07e  mov     r8d, 0C8h; Size
0x18002d084  mov     rcx, rdi; void *
0x18002d087  call    memset_0
0x18002d08c  mov     rdi, [rbp+arg_58]
0x18002d093  mov     rcx, [rdi]; struct _UNICODE_STRING *
0x18002d096  test    rcx, rcx
0x18002d099  jz      short loc_18002D0BA
0x18002d09b  call    ?KerbFreeString2@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString2(_UNICODE_STRING *)
0x18002d0a0  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d0a7  mov     rcx, [rdi]
0x18002d0aa  mov     rax, [rax+30h]
0x18002d0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b3  mov     qword ptr [rdi], 0
0x18002d0ba  mov     rdi, [rbp+arg_68]
0x18002d0c1  mov     rcx, [rdi]; struct _UNICODE_STRING *
0x18002d0c4  test    rcx, rcx
0x18002d0c7  jz      short loc_18002D0E8
0x18002d0c9  call    ?KerbFreeString2@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString2(_UNICODE_STRING *)
0x18002d0ce  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d0d5  mov     rcx, [rdi]
0x18002d0d8  mov     rax, [rax+30h]
0x18002d0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0e1  mov     qword ptr [rdi], 0
0x18002d0e8  mov     rdi, [rbp+arg_60]
0x18002d0ef  mov     rcx, [rdi]; struct _UNICODE_STRING *
0x18002d0f2  test    rcx, rcx
0x18002d0f5  jz      short loc_18002D116
0x18002d0f7  call    ?KerbFreeString2@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString2(_UNICODE_STRING *)
0x18002d0fc  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d103  mov     rcx, [rdi]
0x18002d106  mov     rax, [rax+30h]
0x18002d10a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d10f  mov     qword ptr [rdi], 0
0x18002d116  mov     eax, [r12+4]
0x18002d11b  or      eax, [r12]
0x18002d11f  jz      short loc_18002D134
0x18002d121  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d128  mov     rcx, r12
0x18002d12b  mov     rax, [rax+8]
0x18002d12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d134  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d13b  lea     rax, WPP_GLOBAL_Control
0x18002d142  cmp     rcx, rax
0x18002d145  jz      short loc_18002D16D
0x18002d147  test    byte ptr [rcx+1Ch], 1
0x18002d14b  jz      short loc_18002D16D
0x18002d14d  mov     eax, [r13+0]
0x18002d151  lea     r8, WPP_7e7e3542d015350663d795ca61e34c82_Traceguids
0x18002d158  mov     rcx, [rcx+10h]
0x18002d15c  mov     edx, 15h
0x18002d161  mov     r9d, ebx
0x18002d164  mov     dword ptr [rsp+78h+var_58], eax
0x18002d168  call    WPP_SF_dd
0x18002d16d  mov     rcx, [rbp+var_38]; void *
0x18002d171  test    rcx, rcx
0x18002d174  jz      short loc_18002D17B
0x18002d176  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18002d17b  test    r14, r14
0x18002d17e  jz      short loc_18002D18D
0x18002d180  cmp     r14, rsi
0x18002d183  jz      short loc_18002D18D
0x18002d185  mov     rcx, r14; void *
0x18002d188  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18002d18d  mov     eax, ebx
0x18002d18f  add     rsp, 78h
0x18002d193  pop     r15
0x18002d195  pop     r14
0x18002d197  pop     r13
0x18002d199  pop     r12
0x18002d19b  pop     rdi
0x18002d19c  pop     rsi
0x18002d19d  pop     rbx
0x18002d19e  pop     rbp
0x18002d19f  retn
0x18002d1a0  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d1a7  mov     ecx, 10h
0x18002d1ac  mov     rax, [rax+28h]
0x18002d1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1b5  mov     [rbx], rax
0x18002d1b8  test    rax, rax
0x18002d1bb  jz      loc_18002D010
0x18002d1c1  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d1c8  mov     ecx, 10h
0x18002d1cd  mov     rax, [rax+28h]
0x18002d1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1d6  mov     rcx, [rbp+arg_68]
0x18002d1dd  mov     [rcx], rax
0x18002d1e0  test    rax, rax
0x18002d1e3  jz      loc_18002D010
0x18002d1e9  cmp     esi, 3
0x18002d1ec  jz      short loc_18002D245
0x18002d1ee  mov     ebx, 0C000010Bh
0x18002d1f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1fa  lea     rax, WPP_GLOBAL_Control
0x18002d201  cmp     rcx, rax
0x18002d204  jz      loc_18002D015
0x18002d20a  test    byte ptr [rcx+1Ch], 1
0x18002d20e  jz      loc_18002D015
0x18002d214  mov     rcx, [rcx+10h]
0x18002d218  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002d21f  mov     edx, 13h
0x18002d224  mov     dword ptr [rsp+78h+LocallyUniqueId], 1B2h
0x18002d22c  mov     r9d, esi
0x18002d22f  mov     [rsp+78h+var_58], rax
0x18002d234  lea     r8, WPP_7e7e3542d015350663d795ca61e34c82_Traceguids
0x18002d23b  call    WPP_SF_dsd
0x18002d240  jmp     loc_18002D015
0x18002d245  mov     ebx, [rbp+arg_20]
0x18002d248  mov     rsi, [rbp+arg_10]
0x18002d24c  cmp     ebx, 4
0x18002d24f  jnb     short loc_18002D25B
0x18002d251  mov     ebx, 0C000000Dh
0x18002d256  jmp     loc_18002D019
0x18002d25b  cmp     dword ptr [rsi], 0Eh
0x18002d25e  jz      short loc_18002D26A
0x18002d260  mov     ebx, 0C0000003h
0x18002d265  jmp     loc_18002D015
0x18002d26a  xor     eax, eax
0x18002d26c  lea     rcx, [rbp+var_20]
0x18002d270  mov     [rbp+var_10], rax
0x18002d274  xorps   xmm0, xmm0
0x18002d277  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d27e  movups  [rbp+var_20], xmm0
0x18002d282  mov     rax, [rax+0C0h]
0x18002d289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d28e  test    al, al
0x18002d290  jnz     short loc_18002D29C
0x18002d292  mov     ebx, 0C00000E5h
0x18002d297  jmp     loc_18002D015
0x18002d29c  test    byte ptr [rbp+var_20+8], 40h
0x18002d2a0  jz      loc_18002D351
0x18002d2a6  mov     r9d, [rsi]; enum _PKU2U_LOGON_SUBMIT_TYPE
0x18002d2a9  lea     rax, [rbp+var_30]
0x18002d2ad  lea     r8, [rbp+arg_20]; unsigned int *
0x18002d2b1  mov     [rsp+78h+var_58], rax; void **
0x18002d2b6  mov     rcx, rsi; void *
0x18002d2b9  call    ?Pku2uConvertWOWLogonBuffer@@YAJPEAX0PEAKW4_PKU2U_LOGON_SUBMIT_TYPE@@PEAPEAX@Z; Pku2uConvertWOWLogonBuffer(void *,void *,ulong *,_PKU2U_LOGON_SUBMIT_TYPE,void * *)
0x18002d2be  mov     r14, [rbp+var_30]
0x18002d2c2  mov     ebx, eax
0x18002d2c4  test    eax, eax
0x18002d2c6  js      short loc_18002D2D3
0x18002d2c8  mov     ebx, [rbp+arg_20]
0x18002d2cb  mov     rsi, r14
0x18002d2ce  jmp     loc_18002D355
0x18002d2d3  mov     rsi, [rbp+arg_10]
0x18002d2d7  mov     eax, 0C0000384h
0x18002d2dc  cmp     ebx, eax
0x18002d2de  jg      loc_18002D572
0x18002d2e4  jz      loc_18002D5E1
0x18002d2ea  mov     eax, 0C0000193h
0x18002d2ef  mov     ecx, 0C000006Eh
0x18002d2f4  cmp     ebx, eax
0x18002d2f6  jg      loc_18002D52D
0x18002d2fc  jz      loc_18002D524
0x18002d302  cmp     ebx, 0C0000064h
0x18002d308  jz      loc_18002D5E1
0x18002d30e  cmp     ebx, 0C000006Ah
0x18002d314  jz      loc_18002D5E1
0x18002d31a  cmp     ebx, ecx
0x18002d31c  jz      loc_18002D51B
0x18002d322  cmp     ebx, 0C000006Fh
0x18002d328  jz      short loc_18002D346
0x18002d32a  cmp     ebx, 0C0000070h
0x18002d330  jz      short loc_18002D346
0x18002d332  cmp     ebx, 0C0000071h
0x18002d338  jz      short loc_18002D346
0x18002d33a  cmp     ebx, 0C0000072h
0x18002d340  jnz     loc_18002D019
0x18002d346  mov     [r13+0], ebx
0x18002d34a  mov     ebx, ecx
0x18002d34c  jmp     loc_18002D019
0x18002d351  mov     rsi, [rbp+arg_10]
0x18002d355  cmp     ebx, 38h ; '8'
0x18002d358  jnb     short loc_18002D3AC
0x18002d35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d361  lea     rax, WPP_GLOBAL_Control
0x18002d368  cmp     rcx, rax
0x18002d36b  jz      loc_18002D251
0x18002d371  test    byte ptr [rcx+1Ch], 1
0x18002d375  jz      loc_18002D251
0x18002d37b  mov     rcx, [rcx+10h]
0x18002d37f  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002d386  mov     edx, 11h
0x18002d38b  mov     dword ptr [rsp+78h+LocallyUniqueId], 195h
0x18002d393  mov     r9d, ebx
0x18002d396  mov     [rsp+78h+var_58], rax
0x18002d39b  lea     r8, WPP_7e7e3542d015350663d795ca61e34c82_Traceguids
0x18002d3a2  call    WPP_SF_dsd
0x18002d3a7  jmp     loc_18002D251
0x18002d3ac  mov     r9, [rbp+arg_48]; enum _LSA_TOKEN_INFORMATION_TYPE *
0x18002d3b3  lea     rax, [rbp+var_38]
0x18002d3b7  mov     [rsp+78h+var_48], rax; struct _NETLOGON_VALIDATION_SAM_INFO4 **
0x18002d3bc  mov     r8d, ebx; unsigned int
0x18002d3bf  mov     rax, [rbp+arg_50]
0x18002d3c6  mov     rdx, r15; void *
0x18002d3c9  mov     [rsp+78h+LocallyUniqueId], rdi; LocallyUniqueId
0x18002d3ce  mov     rcx, r14; void *
0x18002d3d1  mov     [rsp+78h+var_58], rax; void **
0x18002d3d6  call    ?Pku2uS4UToSelfLogon@@YAJPEAX0KPEAW4_LSA_TOKEN_INFORMATION_TYPE@@PEAPEAXPEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z; Pku2uS4UToSelfLogon(void *,void *,ulong,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_SECPKG_PRIMARY_CRED *,_NETLOGON_VALIDATION_SAM_INFO4 * *)
0x18002d3db  mov     ebx, eax
0x18002d3dd  test    eax, eax
0x18002d3df  jns     short loc_18002D41F
0x18002d3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3e8  lea     rax, WPP_GLOBAL_Control
0x18002d3ef  cmp     rcx, rax
0x18002d3f2  jz      loc_18002D2D7
0x18002d3f8  test    byte ptr [rcx+1Ch], 1
0x18002d3fc  jz      loc_18002D2D7
0x18002d402  mov     rcx, [rcx+10h]
0x18002d406  lea     r8, WPP_7e7e3542d015350663d795ca61e34c82_Traceguids
0x18002d40d  mov     edx, 12h
0x18002d412  mov     r9d, ebx
0x18002d415  call    WPP_SF_d
0x18002d41a  jmp     loc_18002D2D7
0x18002d41f  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002d426  mov     rcx, rdi
0x18002d429  mov     rax, [rax]
0x18002d42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d431  mov     ebx, eax
0x18002d433  test    eax, eax
0x18002d435  jns     short loc_18002D489
0x18002d437  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d43e  lea     rax, WPP_GLOBAL_Control
0x18002d445  cmp     rcx, rax
0x18002d448  jz      loc_18002D2D7
0x18002d44e  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
