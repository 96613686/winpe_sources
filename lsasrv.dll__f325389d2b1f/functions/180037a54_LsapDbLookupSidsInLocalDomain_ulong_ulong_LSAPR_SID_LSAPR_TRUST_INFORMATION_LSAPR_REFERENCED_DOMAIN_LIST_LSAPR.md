# LsapDbLookupSidsInLocalDomain(ulong,ulong,_LSAPR_SID * *,_LSAPR_TRUST_INFORMATION *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *,ulong *)

- ea: `0x180037a54`
- end: `0x180037ffd`
- name: `?LsapDbLookupSidsInLocalDomain@@YAJKKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_TRUST_INFORMATION@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK4@Z`
- size: `1449`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct _LSAPR_SID **, struct _LSAPR_TRUST_INFORMATION *, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_NAMES_EX *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180036610`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x18001ddc0`
- `0x1800379d4`
- `0x180037a54`
- `0x180038020`
- `0x180038470`
- `0x180039400`
- `0x180077a6c`
- `0x180077ac4`
- `0x1800b1d58`
- `0x1800b1db8`
- `0x1800bbbfc`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037e53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037e72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037eeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037e53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037e72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037eeb`
- `ntdll!RtlSubAuthorityCountSid` at `0x180037c2c`
- `ntdll!RtlSubAuthorityCountSid` at `0x180037c2c`
- `ntdll!RtlSubAuthoritySid` at `0x180037c8c`
- `ntdll!RtlSubAuthoritySid` at `0x180037c8c`
- `ntdll!RtlEqualSid` at `0x180037cd5`
- `ntdll!RtlEqualSid` at `0x180037cd5`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_RETURNED_USTRING_ARRAY` at `0x180037f82`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_RETURNED_USTRING_ARRAY` at `0x180037f82`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrLookupIdsInDomain` at `0x180037d50`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrLookupIdsInDomain` at `0x180037d50`

## pseudocode

```c
__int64 __fastcall LsapDbLookupSidsInLocalDomain(
        unsigned int a1,
        unsigned int a2,
        struct _LSAPR_SID **a3,
        struct _LSAPR_TRUST_INFORMATION *a4,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a5,
        struct _LSAPR_TRANSLATED_NAMES_EX *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  void *v8; // rax
  unsigned int *v10; // r15
  unsigned int *v11; // rsi
  __int64 result; // rax
  __int64 v13; // r8
  struct _RTL_BALANCED_NODE *v14; // r12
  void *v15; // rdx
  unsigned __int64 v16; // rcx
  __int64 v17; // rdi
  int v18; // ebx
  int v19; // eax
  unsigned int v20; // r15d
  int v21; // r12d
  PSID v22; // rbx
  __int64 v23; // r14
  __int64 v24; // rsi
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v25; // r14
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // ebx
  __int64 v29; // r12
  __int64 v30; // r14
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rsi
  void *v35; // rsi
  unsigned int *v36; // r14
  int v37; // eax
  __int64 v38; // rsi
  unsigned int v39; // r14d
  __int64 v40; // rdx
  int v41; // ecx
  __int64 v42; // r14
  __int64 v43; // rsi
  void *v44; // rcx
  __int64 i; // r14
  __int64 v46; // rsi
  __int64 j; // r14
  __int64 v48; // rsi
  int v49; // eax
  unsigned int v50; // [rsp+38h] [rbp-59h] BYREF
  unsigned int v51; // [rsp+3Ch] [rbp-55h]
  int v52; // [rsp+40h] [rbp-51h]
  __int64 v53; // [rsp+48h] [rbp-49h]
  int v54; // [rsp+50h] [rbp-41h] BYREF
  __int128 v55; // [rsp+58h] [rbp-39h] BYREF
  struct _RTL_BALANCED_NODE *v56; // [rsp+68h] [rbp-29h]
  __int128 v57; // [rsp+70h] [rbp-21h] BYREF
  int v58; // [rsp+80h] [rbp-11h]
  PSID Sid; // [rsp+88h] [rbp-9h]
  UCHAR v63; // [rsp+F0h] [rbp+5Fh]

  v8 = (void *)*((_QWORD *)a4 + 2);
  v54 = -1;
  Sid = v8;
  v55 = 0;
  v50 = 0;
  v57 = 0;
  v10 = a8;
  v11 = a7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_08c77a85c8fb32461bb1cd34cd300b68_Traceguids, a2, *a7, *a8);
  result = LsapOpenSamEx(0);
  if ( (int)result >= 0 )
  {
    v14 = 0;
    v15 = (void *)*a8;
    v16 = (unsigned int)v15 + *a7;
    v56 = 0;
    v17 = *((_QWORD *)a6 + 1);
    v53 = 0;
    LODWORD(v55) = 0;
    *((_QWORD *)&v55 + 1) = 0;
    LODWORD(v57) = 0;
    *((_QWORD *)&v57 + 1) = 0;
    if ( (unsigned int)v16 > a2 )
    {
      v18 = -1073741811;
      goto LABEL_64;
    }
    v18 = 0;
    v58 = 0;
    if ( (_DWORD)v15 )
    {
      v19 = 0;
      LODWORD(v16) = 0;
      v20 = 0;
      v51 = 0;
      v52 = 0;
      v21 = -1;
      v50 = 0;
      if ( !a2 )
      {
        v14 = 0;
        goto LABEL_78;
      }
      v22 = Sid;
      v23 = 0;
      while ( 1 )
      {
        v24 = 32 * v23;
        if ( *(_DWORD *)(32 * v23 + v17) != 8 || *(_DWORD *)(v24 + v17 + 24) != -1 )
          goto LABEL_14;
        if ( LsapRtlPrefixSid(v22, a3[v23]) )
        {
          ++v50;
        }
        else if ( RtlEqualSid(v22, a3[v23]) )
        {
          ++v51;
          *(_DWORD *)(v24 + v17 + 8) = 0;
          v19 = v52 + 1;
          *(_DWORD *)(v24 + v17 + 24) = v21;
          v52 = v19;
          v21 = v20;
          *(_DWORD *)(v24 + v17) = 3;
          *(_QWORD *)(v24 + v17 + 16) = 0;
          goto LABEL_14;
        }
        v19 = v52;
LABEL_14:
        ++v20;
        ++v23;
        if ( v20 >= a2 )
        {
          v18 = v58;
          if ( v50 || v19 )
          {
            v25 = a5;
            v18 = LsapDbLookupAddListReferencedDomains(a5, a4, &v54);
            if ( v18 < 0 )
              goto LABEL_76;
            if ( v21 != -1 )
            {
              v26 = v54;
              do
              {
                v27 = 32LL * v21;
                v21 = *(_DWORD *)(v27 + v17 + 24);
                *(_DWORD *)(v27 + v17 + 24) = v26;
              }
              while ( v21 != -1 );
            }
            if ( v50 )
            {
              v56 = (struct _RTL_BALANCED_NODE *)LsapAllocate(4LL * v50);
              v18 = -1073741670;
              if ( v56 )
              {
                v53 = LsapAllocate(4LL * v50);
                v14 = (struct _RTL_BALANCED_NODE *)v53;
                if ( !v53 )
                  goto LABEL_58;
                v28 = v50;
                v29 = 0;
                v30 = 0;
                v63 = *RtlSubAuthorityCountSid(Sid);
                do
                {
                  if ( (unsigned int)v30 >= a2 )
                    break;
                  v34 = 32LL * (unsigned int)v30;
                  if ( *(_DWORD *)(v34 + v17) == 8 && *(_DWORD *)(v34 + v17 + 24) == -1 )
                  {
                    if ( LsapRtlPrefixSid(Sid, a3[v30]) )
                    {
                      *(_DWORD *)(v53 + 4 * v29) = v30;
                      v32 = *RtlSubAuthoritySid(a3[v30], v63);
                      *((_DWORD *)v56->Children + v29) = v32;
                      v29 = (unsigned int)(v29 + 1);
                      *(_DWORD *)(v34 + v17 + 24) = v54;
                    }
                    v28 = v50;
                  }
                  v30 = (unsigned int)(v30 + 1);
                }
                while ( (unsigned int)v29 < v28 );
                if ( a1 == 1 )
                {
                  v35 = LsapBuiltinDomainHandle;
                }
                else
                {
                  v35 = LsapLocalAccountDomainHandle;
                  if ( a1 == 2 )
                    v35 = LsapAccountDomainHandle;
                }
                if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v32, v31, v33) )
                {
                  v36 = (unsigned int *)v56;
                  v37 = SamrLookupIdsInDomain(v35, v28, v56, &v55, &v57);
                  v18 = v37;
                  if ( v37 >= 0 )
                    goto LABEL_44;
                  if ( v37 == -1073741604 )
                    v18 = LsapSamExtLookupIdsInDomain(
                            v35,
                            v50,
                            v36,
                            (struct _SAMPR_RETURNED_USTRING_ARRAY *)&v55,
                            (struct _SAMPR_ULONG_ARRAY *)&v57);
                  if ( v18 == -1073741709 )
                  {
                    v18 = 0;
LABEL_44:
                    v14 = (struct _RTL_BALANCED_NODE *)v53;
                    v38 = 0;
                    if ( !(_DWORD)v55 )
                    {
                      LODWORD(v16) = v51;
                      goto LABEL_78;
                    }
                    do
                    {
                      v39 = *((_DWORD *)v14->Children + v38);
                      v40 = 32LL * v39;
                      v41 = *(_DWORD *)(*((_QWORD *)&v57 + 1) + 4 * v38);
                      *(_DWORD *)(v40 + v17) = v41;
                      if ( v41 == 8 )
                      {
                        if ( (int)LsapLoadLsaDbExtensionDll() >= 0 )
                          (*((void (__fastcall **)(_QWORD, _QWORD, unsigned int *, __int64))g_pLsaExtensionTableLsaDb
                           + 27))(
                            a1,
                            v39,
                            &v50,
                            v17);
                        v16 = v51;
                      }
                      else
                      {
                        v18 = LsapRpcCopyUnicodeString(
                                0,
                                v17 + v40 + 8,
                                *((_QWORD *)&v55 + 1) + 16LL * (unsigned int)v38);
                        if ( v18 < 0 )
                          goto LABEL_57;
                        v16 = ++v51;
                      }
                      v38 = (unsigned int)(v38 + 1);
                    }
                    while ( (unsigned int)v38 < (unsigned int)v55 );
                    if ( v18 >= 0 )
                    {
LABEL_78:
                      v10 = a8;
                      *a7 += v16;
                      v16 = v50 + v52;
                      *a8 -= v16;
                      goto LABEL_79;
                    }
LABEL_57:
                    v25 = a5;
LABEL_58:
                    if ( v54 >= 0 )
                    {
                      v42 = *((_QWORD *)v25 + 1);
                      v43 = 3LL * v54;
                      v44 = *(void **)(v42 + 24LL * v54 + 16);
                      if ( v44 )
                      {
                        LocalFree(v44);
                        *(_QWORD *)(v42 + 8 * v43 + 16) = 0;
                      }
                      v16 = *(_QWORD *)(v42 + 8 * v43 + 8);
                      if ( v16 )
                      {
                        LocalFree((HLOCAL)v16);
                        *(_QWORD *)(v42 + 8 * v43 + 8) = 0;
                        *(_DWORD *)(v42 + 8 * v43) = 0;
                      }
                    }
                    v10 = a8;
LABEL_64:
                    for ( i = 0; (unsigned int)i < (unsigned int)v55; i = (unsigned int)(i + 1) )
                    {
                      v46 = 32LL * *((unsigned int *)v14->Children + i);
                      v16 = *(_QWORD *)(v17 + v46 + 16);
                      if ( v16 )
                      {
                        LocalFree((HLOCAL)v16);
                        *(_QWORD *)(v46 + v17 + 16) = 0;
                        *(_DWORD *)(v46 + v17 + 8) = 0;
                      }
                    }
                    for ( j = 0; (unsigned int)j < (unsigned int)v55; *(_DWORD *)(v17 + v48 + 24) = -1 )
                    {
                      v48 = 32LL * *((unsigned int *)v14->Children + j);
                      v16 = *(_QWORD *)(v17 + v48 + 16);
                      if ( v16 )
                      {
                        LocalFree((HLOCAL)v16);
                        *(_QWORD *)(v48 + v17 + 16) = 0;
                        *(_DWORD *)(v48 + v17 + 8) = 0;
                      }
                      j = (unsigned int)(j + 1);
                      *(_DWORD *)(v48 + v17) = 8;
                    }
                    v49 = 0;
                    if ( v18 < 0 )
                      v49 = v18;
                    v18 = v49;
LABEL_79:
                    if ( v56 )
                      LsapSubProv_FreeRoutine(v56, v15);
                    if ( v14 )
                      LsapSubProv_FreeRoutine(v14, v15);
                    if ( (_DWORD)v55 )
                    {
                      if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v16, v15, v13) )
                        SamIFree_SAMPR_RETURNED_USTRING_ARRAY(&v55);
                      LODWORD(v55) = 0;
                    }
                    if ( (_DWORD)v57 )
                    {
                      LsapSamExtFreeULongArray((struct _SAMPR_ULONG_ARRAY *)&v57);
                      LODWORD(v57) = 0;
                    }
                    v11 = a7;
                    break;
                  }
                }
                else
                {
                  v18 = -1073741637;
                }
                v14 = (struct _RTL_BALANCED_NODE *)v53;
                goto LABEL_57;
              }
LABEL_76:
              v14 = (struct _RTL_BALANCED_NODE *)v53;
              goto LABEL_58;
            }
          }
          LODWORD(v16) = v51;
          v14 = (struct _RTL_BALANCED_NODE *)v53;
          goto LABEL_78;
        }
      }
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
      WPP_SF_ddD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        32,
        WPP_08c77a85c8fb32461bb1cd34cd300b68_Traceguids,
        *v11,
        *v10,
        v18);
    return (unsigned int)v18;
  }
  return result;
}

```

## disassembly

```asm
0x180037a54  mov     rax, rsp
0x180037a57  mov     [rax+10h], rbx
0x180037a5b  mov     [rax+20h], r9
0x180037a5f  mov     [rax+18h], r8
0x180037a63  mov     [rax+8], ecx
0x180037a66  push    rbp
0x180037a67  push    rsi
0x180037a68  push    rdi
0x180037a69  push    r12
0x180037a6b  push    r13
0x180037a6d  push    r14
0x180037a6f  push    r15
0x180037a71  lea     rbp, [rax-3Fh]
0x180037a75  sub     rsp, 90h
0x180037a7c  mov     rax, [r9+10h]
0x180037a80  or      r14d, 0FFFFFFFFh
0x180037a84  xorps   xmm0, xmm0
0x180037a87  mov     [rbp+37h+var_78], r14d
0x180037a8b  xorps   xmm1, xmm1
0x180037a8e  mov     [rbp+37h+Sid], rax
0x180037a92  movups  [rbp+37h+var_70], xmm0
0x180037a96  mov     r13d, edx
0x180037a99  mov     [rbp+37h+var_90], 0
0x180037aa0  movups  [rbp+37h+var_58], xmm1
0x180037aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180037aab  mov     r15, [rbp+37h+arg_38]
0x180037aaf  mov     rsi, [rbp+37h+arg_30]
0x180037ab3  test    byte ptr [rcx+6Ch], 40h
0x180037ab7  jz      short loc_180037ADD
0x180037ab9  mov     eax, [r15]
0x180037abc  lea     edx, [r14+20h]
0x180037ac0  mov     rcx, [rcx+60h]
0x180037ac4  lea     r8, WPP_08c77a85c8fb32461bb1cd34cd300b68_Traceguids
0x180037acb  mov     [rsp+28h], eax
0x180037acf  mov     r9d, r13d
0x180037ad2  mov     eax, [rsi]
0x180037ad4  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180037ad8  call    WPP_SF_DDD
0x180037add  xor     ecx, ecx; unsigned __int8
0x180037adf  call    ?LsapOpenSamEx@@YAJE@Z; LsapOpenSamEx(uchar)
0x180037ae4  test    eax, eax
0x180037ae6  js      loc_180037FE1
0x180037aec  mov     rax, [rbp+37h+arg_28]
0x180037af0  xor     r12d, r12d
0x180037af3  mov     ecx, [rsi]
0x180037af5  mov     edx, [r15]; void *
0x180037af8  add     ecx, edx
0x180037afa  mov     [rbp+37h+var_60], 0
0x180037b02  mov     rdi, [rax+8]
0x180037b06  mov     [rbp+37h+var_80], r12
0x180037b0a  mov     dword ptr [rbp+37h+var_70], r12d
0x180037b0e  mov     qword ptr [rbp+37h+var_70+8], r12
0x180037b12  mov     dword ptr [rbp+37h+var_58], r12d
0x180037b16  mov     qword ptr [rbp+37h+var_58+8], r12
0x180037b1a  cmp     ecx, r13d
0x180037b1d  jbe     short loc_180037B29
0x180037b1f  mov     ebx, 0C000000Dh
0x180037b24  jmp     loc_180037E91
0x180037b29  xor     ebx, ebx
0x180037b2b  mov     [rbp+37h+var_48], ebx
0x180037b2e  test    edx, edx
0x180037b30  jz      loc_180037FAF
0x180037b36  xor     eax, eax
0x180037b38  xor     ecx, ecx
0x180037b3a  xor     r15d, r15d
0x180037b3d  mov     [rbp+37h+var_8C], ecx
0x180037b40  mov     [rbp+37h+var_88], eax
0x180037b43  mov     r12d, r14d
0x180037b46  mov     [rbp+37h+var_90], eax
0x180037b49  test    r13d, r13d
0x180037b4c  jz      loc_180037F3B
0x180037b52  mov     rbx, [rbp+37h+Sid]
0x180037b56  xor     r14d, r14d
0x180037b59  mov     rsi, r14
0x180037b5c  shl     rsi, 5
0x180037b60  cmp     dword ptr [rsi+rdi], 8
0x180037b64  jnz     short loc_180037B8B
0x180037b66  cmp     dword ptr [rsi+rdi+18h], 0FFFFFFFFh
0x180037b6b  jnz     short loc_180037B8B
0x180037b6d  mov     rax, [rbp+37h+arg_10]
0x180037b71  mov     rcx, rbx; Sid1
0x180037b74  mov     rdx, [rax+r14*8]; Sid
0x180037b78  call    LsapRtlPrefixSid
0x180037b7d  test    al, al
0x180037b7f  jz      loc_180037CCA
0x180037b85  inc     [rbp+37h+var_90]
0x180037b88  mov     eax, [rbp+37h+var_88]
0x180037b8b  inc     r15d
0x180037b8e  inc     r14
0x180037b91  cmp     r15d, r13d
0x180037b94  jb      short loc_180037B59
0x180037b96  cmp     [rbp+37h+var_90], 0
0x180037b9a  mov     ebx, [rbp+37h+var_48]
0x180037b9d  jnz     short loc_180037BA7
0x180037b9f  test    eax, eax
0x180037ba1  jz      loc_180037F29
0x180037ba7  mov     r14, [rbp+37h+arg_20]
0x180037bab  lea     r8, [rbp+37h+var_78]
0x180037baf  mov     rdx, [rbp+37h+arg_18]
0x180037bb3  mov     rcx, r14
0x180037bb6  call    LsapDbLookupAddListReferencedDomains
0x180037bbb  mov     ebx, eax
0x180037bbd  test    eax, eax
0x180037bbf  js      loc_180037F32
0x180037bc5  cmp     r12d, 0FFFFFFFFh
0x180037bc9  jz      short loc_180037BE4
0x180037bcb  mov     eax, [rbp+37h+var_78]
0x180037bce  movsxd  rcx, r12d
0x180037bd1  shl     rcx, 5
0x180037bd5  mov     r12d, [rcx+rdi+18h]
0x180037bda  mov     [rcx+rdi+18h], eax
0x180037bde  cmp     r12d, 0FFFFFFFFh
0x180037be2  jnz     short loc_180037BCE
0x180037be4  mov     eax, [rbp+37h+var_90]
0x180037be7  test    eax, eax
0x180037be9  jz      loc_180037F29
0x180037bef  mov     ecx, eax
0x180037bf1  shl     rcx, 2
0x180037bf5  call    LsapAllocate
0x180037bfa  mov     [rbp+37h+var_60], rax
0x180037bfe  mov     ebx, 0C000009Ah
0x180037c03  test    rax, rax
0x180037c06  jz      loc_180037F32
0x180037c0c  mov     ecx, [rbp+37h+var_90]
0x180037c0f  shl     rcx, 2
0x180037c13  call    LsapAllocate
0x180037c18  mov     [rbp+37h+var_80], rax
0x180037c1c  mov     r12, rax
0x180037c1f  test    rax, rax
0x180037c22  jz      loc_180037E39
0x180037c28  mov     rcx, [rbp+37h+Sid]; Sid
0x180037c2c  call    cs:__imp_RtlSubAuthorityCountSid
0x180037c33  nop     dword ptr [rax+rax+00h]
0x180037c38  mov     ebx, [rbp+37h+var_90]
0x180037c3b  xor     r12d, r12d
0x180037c3e  xor     r14d, r14d
0x180037c41  mov     al, [rax]
0x180037c43  mov     byte ptr [rbp+37h+arg_18], al
0x180037c46  test    ebx, ebx
0x180037c48  jz      short loc_180037CB7
0x180037c4a  cmp     r14d, r13d
0x180037c4d  jnb     short loc_180037CB7
0x180037c4f  mov     esi, r14d
0x180037c52  shl     rsi, 5
0x180037c56  cmp     dword ptr [rsi+rdi], 8
0x180037c5a  jnz     short loc_180037CAF
0x180037c5c  cmp     dword ptr [rsi+rdi+18h], 0FFFFFFFFh
0x180037c61  jnz     short loc_180037CAF
0x180037c63  mov     rax, [rbp+37h+arg_10]
0x180037c67  mov     rcx, [rbp+37h+Sid]; Sid1
0x180037c6b  mov     rdx, [rax+r14*8]; Sid
0x180037c6f  call    LsapRtlPrefixSid
0x180037c74  test    al, al
0x180037c76  jz      short loc_180037CAC
0x180037c78  mov     rax, [rbp+37h+var_80]
0x180037c7c  movzx   edx, byte ptr [rbp+37h+arg_18]; SubAuthority
0x180037c80  mov     [rax+r12*4], r14d
0x180037c84  mov     rax, [rbp+37h+arg_10]
0x180037c88  mov     rcx, [rax+r14*8]; Sid
0x180037c8c  call    cs:__imp_RtlSubAuthoritySid
0x180037c93  nop     dword ptr [rax+rax+00h]
0x180037c98  mov     ecx, [rax]
0x180037c9a  mov     rax, [rbp+37h+var_60]
0x180037c9e  mov     [rax+r12*4], ecx
0x180037ca2  inc     r12d
0x180037ca5  mov     eax, [rbp+37h+var_78]
0x180037ca8  mov     [rsi+rdi+18h], eax
0x180037cac  mov     ebx, [rbp+37h+var_90]
0x180037caf  inc     r14d
0x180037cb2  cmp     r12d, ebx
0x180037cb5  jb      short loc_180037C4A
0x180037cb7  mov     r15d, [rbp+37h+arg_0]
0x180037cbb  cmp     r15d, 1
0x180037cbf  jnz     short loc_180037D17
0x180037cc1  mov     rsi, cs:?LsapBuiltinDomainHandle@@3PEAXEA; void * LsapBuiltinDomainHandle
0x180037cc8  jmp     short loc_180037D2A
0x180037cca  mov     rax, [rbp+37h+arg_10]
0x180037cce  mov     rcx, rbx; Sid1
0x180037cd1  mov     rdx, [rax+r14*8]; Sid2
0x180037cd5  call    cs:__imp_RtlEqualSid
0x180037cdc  nop     dword ptr [rax+rax+00h]
0x180037ce1  test    al, al
0x180037ce3  jz      loc_180037B88
0x180037ce9  inc     [rbp+37h+var_8C]
0x180037cec  xor     eax, eax
0x180037cee  mov     [rsi+rdi+8], eax
0x180037cf2  mov     eax, [rbp+37h+var_88]
0x180037cf5  inc     eax
0x180037cf7  mov     [rsi+rdi+18h], r12d
0x180037cfc  mov     [rbp+37h+var_88], eax
0x180037cff  mov     r12d, r15d
0x180037d02  mov     dword ptr [rsi+rdi], 3
0x180037d09  mov     qword ptr [rsi+rdi+10h], 0
0x180037d12  jmp     loc_180037B8B
0x180037d17  mov     rsi, cs:?LsapLocalAccountDomainHandle@@3PEAXEA; void * LsapLocalAccountDomainHandle
0x180037d1e  cmp     r15d, 2
0x180037d22  cmovz   rsi, cs:?LsapAccountDomainHandle@@3PEAXEA; void * LsapAccountDomainHandle
0x180037d2a  call    IsSamIDecodeClaimsBlobPresent
0x180037d2f  test    al, al
0x180037d31  jz      loc_180037E2C
0x180037d37  mov     r14, [rbp+37h+var_60]
0x180037d3b  lea     rax, [rbp+37h+var_58]
0x180037d3f  mov     r8, r14
0x180037d42  mov     [rsp+0C0h+var_A0], rax
0x180037d47  lea     r9, [rbp+37h+var_70]
0x180037d4b  mov     edx, ebx
0x180037d4d  mov     rcx, rsi
0x180037d50  call    cs:__imp_SamrLookupIdsInDomain
0x180037d57  nop     dword ptr [rax+rax+00h]
0x180037d5c  mov     ebx, eax
0x180037d5e  test    eax, eax
0x180037d60  jns     short loc_180037D94
0x180037d62  cmp     eax, 0C00000DCh
0x180037d67  jnz     short loc_180037D86
0x180037d69  mov     edx, [rbp+37h+var_90]; unsigned int
0x180037d6c  lea     rax, [rbp+37h+var_58]
0x180037d70  lea     r9, [rbp+37h+var_70]; struct _SAMPR_RETURNED_USTRING_ARRAY *
0x180037d74  mov     [rsp+0C0h+var_A0], rax; struct _SAMPR_ULONG_ARRAY *
0x180037d79  mov     r8, r14; unsigned int *
0x180037d7c  mov     rcx, rsi; void *
0x180037d7f  call    ?LsapSamExtLookupIdsInDomain@@YAJPEAXKPEAKPEAU_SAMPR_RETURNED_USTRING_ARRAY@@PEAU_SAMPR_ULONG_ARRAY@@@Z; LsapSamExtLookupIdsInDomain(void *,ulong,ulong *,_SAMPR_RETURNED_USTRING_ARRAY *,_SAMPR_ULONG_ARRAY *)
0x180037d84  mov     ebx, eax
0x180037d86  cmp     ebx, 0C0000073h
0x180037d8c  jnz     loc_180037E31
0x180037d92  xor     ebx, ebx
0x180037d94  mov     r12, [rbp+37h+var_80]
0x180037d98  xor     esi, esi
0x180037d9a  cmp     dword ptr [rbp+37h+var_70], esi
0x180037d9d  jbe     loc_180037E24
0x180037da3  mov     r14d, [r12+rsi*4]
0x180037da7  mov     rax, qword ptr [rbp+37h+var_58+8]
0x180037dab  mov     edx, r14d
0x180037dae  shl     rdx, 5
0x180037db2  mov     r8d, esi
0x180037db5  mov     ecx, [rax+rsi*4]
0x180037db8  mov     [rdx+rdi], ecx
0x180037dbb  cmp     ecx, 8
0x180037dbe  jz      short loc_180037DE6
0x180037dc0  shl     r8, 4
0x180037dc4  add     rdx, 8
0x180037dc8  add     r8, qword ptr [rbp+37h+var_70+8]
0x180037dcc  add     rdx, rdi
0x180037dcf  xor     ecx, ecx
0x180037dd1  call    LsapRpcCopyUnicodeString
0x180037dd6  mov     ebx, eax
0x180037dd8  test    eax, eax
0x180037dda  js      short loc_180037E35
0x180037ddc  mov     ecx, [rbp+37h+var_8C]
0x180037ddf  inc     ecx
0x180037de1  mov     [rbp+37h+var_8C], ecx
0x180037de4  jmp     short loc_180037E12
0x180037de6  call    ?LsapLoadLsaDbExtensionDll@@YAJXZ; LsapLoadLsaDbExtensionDll(void)
0x180037deb  test    eax, eax
0x180037ded  js      short loc_180037E0F
0x180037def  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x180037df6  lea     r8, [rbp+37h+var_90]
0x180037dfa  mov     r9, rdi
0x180037dfd  mov     edx, r14d
0x180037e00  mov     ecx, r15d
0x180037e03  mov     rax, [rax+0D8h]
0x180037e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e0f  mov     ecx, [rbp+37h+var_8C]
0x180037e12  inc     esi
0x180037e14  mov     eax, ebx
0x180037e16  cmp     esi, dword ptr [rbp+37h+var_70]
0x180037e19  jb      short loc_180037DA3
0x180037e1b  test    eax, eax
0x180037e1d  js      short loc_180037E35
0x180037e1f  jmp     loc_180037F3E
0x180037e24  mov     ecx, [rbp+37h+var_8C]
0x180037e27  jmp     loc_180037F3E
0x180037e2c  mov     ebx, 0C00000BBh
0x180037e31  mov     r12, [rbp+37h+var_80]
0x180037e35  mov     r14, [rbp+37h+arg_20]
0x180037e39  movsxd  rax, [rbp+37h+var_78]
0x180037e3d  test    eax, eax
0x180037e3f  js      short loc_180037E8D
0x180037e41  mov     r14, [r14+8]
0x180037e45  lea     rsi, [rax+rax*2]
0x180037e49  mov     rcx, [r14+rsi*8+10h]; hMem
0x180037e4e  test    rcx, rcx
0x180037e51  jz      short loc_180037E68
0x180037e53  call    cs:__imp_LocalFree
0x180037e5a  nop     dword ptr [rax+rax+00h]
0x180037e5f  mov     qword ptr [r14+rsi*8+10h], 0
0x180037e68  mov     rcx, [r14+rsi*8+8]; hMem
0x180037e6d  test    rcx, rcx
0x180037e70  jz      short loc_180037E8D
0x180037e72  call    cs:__imp_LocalFree
0x180037e79  nop     dword ptr [rax+rax+00h]
0x180037e7e  xor     eax, eax
0x180037e80  mov     qword ptr [r14+rsi*8+8], 0
0x180037e89  mov     [r14+rsi*8], eax
0x180037e8d  mov     r15, [rbp+37h+arg_38]
0x180037e91  xor     r14d, r14d
0x180037e94  cmp     dword ptr [rbp+37h+var_70], r14d
0x180037e98  jbe     short loc_180037ED0
0x180037e9a  mov     esi, [r12+r14*4]
0x180037e9e  shl     rsi, 5
0x180037ea2  mov     rcx, [rdi+rsi+10h]; hMem
  ... truncated ...
```
