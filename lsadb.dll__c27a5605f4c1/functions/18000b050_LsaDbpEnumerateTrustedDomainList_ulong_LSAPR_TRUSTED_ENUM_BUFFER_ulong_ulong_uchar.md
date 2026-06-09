# LsaDbpEnumerateTrustedDomainList(ulong *,_LSAPR_TRUSTED_ENUM_BUFFER *,ulong,ulong,uchar)

- ea: `0x18000b050`
- end: `0x18000b42a`
- name: `?LsaDbpEnumerateTrustedDomainList@@YAJPEAKPEAU_LSAPR_TRUSTED_ENUM_BUFFER@@KKE@Z`
- size: `986`
- prototype: `__int64 __fastcall(unsigned int *, struct _LSAPR_TRUSTED_ENUM_BUFFER *, unsigned int, unsigned int, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800027e0`

## callees

- `0x180001fb8`
- `0x180009ec4`
- `0x18000b050`
- `0x18000cca4`
- `0x18000fd18`
- `0x18000fd40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b23a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b23a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b30f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b321`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b30f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b321`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER` at `0x18000b41c`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER` at `0x18000b41c`
- `LSASRV!LsapRpcCopySid` at `0x18000b2ed`
- `LSASRV!LsapRpcCopySid` at `0x18000b390`
- `LSASRV!LsapRpcCopySid` at `0x18000b2ed`
- `LSASRV!LsapRpcCopySid` at `0x18000b390`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18000b0ad`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18000b0ad`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b2bc`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b2d2`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b37a`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b2bc`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b2d2`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b37a`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000b105`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000b105`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x18000b414`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX` at `0x18000b414`
- `ntdll!RtlLengthSid` at `0x18000b196`
- `ntdll!RtlLengthSid` at `0x18000b1d4`
- `ntdll!RtlLengthSid` at `0x18000b196`
- `ntdll!RtlLengthSid` at `0x18000b1d4`

## pseudocode

```c
__int64 __fastcall LsaDbpEnumerateTrustedDomainList(
        unsigned int *a1,
        struct _LSAPR_TRUSTED_ENUM_BUFFER *a2,
        int a3,
        int a4,
        char a5)
{
  int v5; // edi
  void *v8; // rcx
  int v9; // eax
  __int64 result; // rax
  char *v11; // r15
  unsigned int v12; // r12d
  __int64 v13; // rcx
  int v14; // esi
  unsigned int v15; // ebx
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v16; // r14
  struct _LSAPR_TRUST_INFORMATION *v17; // rcx
  bool v18; // cf
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v19; // rax
  unsigned int v20; // r13d
  void *v21; // rcx
  int v22; // ebx
  int v23; // edi
  unsigned int v24; // eax
  unsigned int v25; // r13d
  int v26; // ecx
  int v27; // ebx
  int v28; // eax
  unsigned int v29; // eax
  size_t v30; // rbx
  char *v31; // rax
  struct _LSAPR_TRUST_INFORMATION *v32; // rdi
  __int64 v33; // r13
  int v34; // eax
  char *v35; // rbx
  __int64 v36; // r9
  __int64 v37; // r8
  void *v38; // rcx
  void *v39; // rcx
  __int64 v40; // r9
  int v41; // [rsp+20h] [rbp-38h]
  unsigned int v42; // [rsp+24h] [rbp-34h]
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v43; // [rsp+28h] [rbp-30h] BYREF
  struct _LSAPR_TRUST_INFORMATION *v44; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v45[4]; // [rsp+38h] [rbp-20h] BYREF
  int v48; // [rsp+B0h] [rbp+58h]

  v5 = a4;
  v8 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
  v9 = 1;
  if ( a3 )
    v9 = a3;
  v42 = v9;
  result = LsapDbExpAcquireReadLockTrustedDomainList(v8);
  if ( (int)result < 0 )
    return result;
  v11 = 0;
  v12 = 0;
  v14 = LsaDbpBuildTrustedDomainCacheIfNecessary(1u, 0);
  if ( v14 < 0 )
    goto LABEL_13;
  v15 = *a1;
  v14 = LsaDbpBuildTrustedDomainCacheIfNecessary(1u, 0);
  if ( v14 < 0 )
    goto LABEL_13;
  v16 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)hMem;
  v13 = (__int64)&hMem;
  while ( 1 )
  {
    if ( v16 == (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)&hMem )
    {
      v14 = -2147483622;
      goto LABEL_13;
    }
    if ( v15 < *((_DWORD *)v16 + 24) )
      break;
    v16 = *(struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)v16;
  }
  v17 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)((char *)v16 + 72);
  v18 = *(_QWORD *)v16 != (_QWORD)&hMem;
  v44 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)((char *)v16 + 72);
  v19 = v16;
  v45[0] = (char *)v16 + 72;
  v43 = v16;
  v14 = v18 ? 0x105 : 0;
  v20 = 0;
  v48 = v14;
  v41 = 0;
  while ( 1 )
  {
    if ( v5 == 6 )
    {
      v21 = (void *)*((_QWORD *)v19 + 6);
      if ( v21 )
      {
        v22 = *((unsigned __int16 *)v19 + 9);
        v23 = *((unsigned __int16 *)v19 + 17);
        v24 = v23 + v22 + RtlLengthSid(v21);
        v5 = a4;
        v25 = v20 + 56;
LABEL_26:
        v20 = v24 + v25;
        ++v12;
        goto LABEL_27;
      }
      if ( a5 )
      {
        v26 = *((unsigned __int16 *)v19 + 17);
        v24 = v20 + *((unsigned __int16 *)v19 + 9);
        v25 = v26 + 56;
        goto LABEL_26;
      }
    }
    else if ( (*((_BYTE *)v19 + 56) & 2) != 0 && *((_QWORD *)v17 + 2) )
    {
      v27 = *((unsigned __int16 *)v17 + 1);
      v24 = v27 + RtlLengthSid(*((PSID *)v17 + 2));
      v25 = v20 + 24;
      goto LABEL_26;
    }
LABEL_27:
    ++v41;
    if ( v20 >= v42 || v14 != 261 )
      break;
    v14 = LsaDbpTraverseTrustedDomainList(&v43, &v44);
    if ( v14 < 0 )
      goto LABEL_13;
    v19 = v43;
    v17 = v44;
  }
  v28 = 56;
  v13 = 24;
  if ( v5 != 6 )
    v28 = 24;
  v29 = v12 * v28;
  if ( v29 )
  {
    v30 = v29;
    v31 = (char *)LocalAlloc(0x40u, v29);
    v11 = v31;
    if ( !v31 )
    {
      v14 = -1073741670;
      goto LABEL_13;
    }
    memset_0(v31, 0, v30);
  }
  v32 = (struct _LSAPR_TRUST_INFORMATION *)v45[0];
  v33 = 0;
  v34 = v48;
  v44 = (struct _LSAPR_TRUST_INFORMATION *)v45[0];
  v43 = v16;
  while ( 2 )
  {
    if ( a4 == 6 )
    {
      if ( !*((_QWORD *)v16 + 6) && !a5 )
        goto LABEL_56;
      if ( (_DWORD)v33 == v12 )
        goto LABEL_59;
      v35 = &v11[56 * (unsigned int)v33];
      *(_OWORD *)v35 = 0;
      *((_OWORD *)v35 + 1) = 0;
      *((_OWORD *)v35 + 2) = 0;
      *((_QWORD *)v35 + 6) = 0;
      v14 = LsapRpcCopyUnicodeString(0, v35, (char *)v16 + 16);
      if ( v14 >= 0 )
      {
        v14 = LsapRpcCopyUnicodeString(0, v35 + 16, (char *)v16 + 32);
        if ( v14 >= 0 )
        {
          v37 = *((_QWORD *)v16 + 6);
          if ( v37 )
          {
            v14 = LsapRpcCopySid(0, v35 + 32, v37, v36);
            if ( v14 < 0 )
              goto LABEL_46;
          }
          else
          {
            *((_QWORD *)v35 + 4) = 0;
          }
          *((_DWORD *)v35 + 11) = *((_DWORD *)v16 + 15);
          *((_DWORD *)v35 + 10) = *((_DWORD *)v16 + 14);
          *((_DWORD *)v35 + 12) = *((_DWORD *)v16 + 16);
LABEL_55:
          v33 = (unsigned int)(v33 + 1);
          v13 = (__int64)a1;
          *a1 = *((_DWORD *)v16 + 24);
          v34 = v48;
LABEL_56:
          if ( v34 != 261 )
            goto LABEL_60;
          v34 = LsaDbpTraverseTrustedDomainList(&v43, &v44);
          v14 = v34;
          if ( v34 < 0 )
            goto LABEL_64;
          v16 = v43;
          v32 = v44;
          v48 = v34;
          continue;
        }
      }
LABEL_46:
      LocalFree(*((HLOCAL *)v35 + 1));
      v38 = (void *)*((_QWORD *)v35 + 3);
      *((_QWORD *)v35 + 1) = 0;
      LocalFree(v38);
      v39 = (void *)*((_QWORD *)v35 + 4);
      *((_QWORD *)v35 + 3) = 0;
      LocalFree(v39);
      *((_QWORD *)v35 + 4) = 0;
LABEL_54:
      if ( v14 < 0 )
        goto LABEL_64;
      goto LABEL_55;
    }
    break;
  }
  if ( (*((_BYTE *)v16 + 56) & 2) == 0 || !*((_QWORD *)v32 + 2) )
    goto LABEL_56;
  if ( (_DWORD)v33 != v12 )
  {
    v14 = LsapRpcCopyUnicodeString(0, &v11[24 * v33], v32);
    if ( v14 >= 0 )
      v14 = LsapRpcCopySid(0, &v11[24 * v33 + 16], *((_QWORD *)v32 + 2), v40);
    goto LABEL_54;
  }
LABEL_59:
  v34 = 261;
LABEL_60:
  if ( v41 && v12 )
  {
    v14 = v34;
    goto LABEL_13;
  }
  v14 = -2147483622;
LABEL_64:
  if ( v11 )
  {
    v45[1] = v11;
    v45[0] = v12;
    if ( a4 == 6 )
      LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX(v45);
    else
      LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER(v45);
    v11 = 0;
  }
LABEL_13:
  LsapDbExpReleaseLockTrustedDomainList(v13);
  *((_QWORD *)a2 + 1) = v11;
  *(_DWORD *)a2 = v12;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
      (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000b050  mov     [rsp-40h+arg_18], r9d
0x18000b055  mov     [rsp-40h+arg_8], rdx
0x18000b05a  mov     [rsp-40h+arg_0], rcx
0x18000b05f  push    rbp
0x18000b060  push    rbx
0x18000b061  push    rsi
0x18000b062  push    rdi
0x18000b063  push    r12
0x18000b065  push    r13
0x18000b067  push    r14
0x18000b069  push    r15
0x18000b06b  mov     rbp, rsp
0x18000b06e  sub     rsp, 58h
0x18000b072  mov     edi, r9d
0x18000b075  mov     ebx, r8d
0x18000b078  mov     r14, rcx
0x18000b07b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b082  test    dword ptr [rcx+1Ch], 100h
0x18000b089  jz      short loc_18000B0A0
0x18000b08b  mov     rcx, [rcx+10h]
0x18000b08f  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000b096  mov     edx, 25h ; '%'
0x18000b09b  call    WPP_SF_
0x18000b0a0  mov     eax, 1
0x18000b0a5  test    ebx, ebx
0x18000b0a7  cmovnz  eax, ebx
0x18000b0aa  mov     [rbp+var_34], eax
0x18000b0ad  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x18000b0b3  test    eax, eax
0x18000b0b5  js      loc_18000B140
0x18000b0bb  xor     edx, edx; unsigned __int8
0x18000b0bd  mov     cl, 1; unsigned __int8
0x18000b0bf  xor     r15d, r15d
0x18000b0c2  xor     r12d, r12d
0x18000b0c5  call    ?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z; LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)
0x18000b0ca  mov     esi, eax
0x18000b0cc  test    eax, eax
0x18000b0ce  js      short loc_18000B105
0x18000b0d0  mov     ebx, [r14]
0x18000b0d3  xor     edx, edx; unsigned __int8
0x18000b0d5  mov     cl, 1; unsigned __int8
0x18000b0d7  call    ?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z; LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)
0x18000b0dc  mov     esi, eax
0x18000b0de  test    eax, eax
0x18000b0e0  js      short loc_18000B105
0x18000b0e2  mov     r14, cs:hMem
0x18000b0e9  lea     rcx, hMem
0x18000b0f0  jmp     short loc_18000B0FB
0x18000b0f2  cmp     ebx, [r14+60h]
0x18000b0f6  jb      short loc_18000B151
0x18000b0f8  mov     r14, [r14]
0x18000b0fb  cmp     r14, rcx
0x18000b0fe  jnz     short loc_18000B0F2
0x18000b100  mov     esi, 8000001Ah
0x18000b105  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18000b10b  mov     rax, [rbp+arg_8]
0x18000b10f  mov     [rax+8], r15
0x18000b113  mov     [rax], r12d
0x18000b116  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b11d  test    dword ptr [rcx+1Ch], 100h
0x18000b124  jz      short loc_18000B13E
0x18000b126  mov     rcx, [rcx+10h]
0x18000b12a  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000b131  mov     edx, 26h ; '&'
0x18000b136  mov     r9d, esi
0x18000b139  call    WPP_SF_d
0x18000b13e  mov     eax, esi
0x18000b140  add     rsp, 58h
0x18000b144  pop     r15
0x18000b146  pop     r14
0x18000b148  pop     r13
0x18000b14a  pop     r12
0x18000b14c  pop     rdi
0x18000b14d  pop     rsi
0x18000b14e  pop     rbx
0x18000b14f  pop     rbp
0x18000b150  retn
0x18000b151  mov     rax, [r14]
0x18000b154  sub     rax, rcx
0x18000b157  lea     rcx, [r14+48h]
0x18000b15b  neg     rax
0x18000b15e  mov     [rbp+var_28], rcx
0x18000b162  mov     rax, r14
0x18000b165  mov     [rbp+var_20], rcx
0x18000b169  sbb     esi, esi
0x18000b16b  mov     [rbp+var_30], rax
0x18000b16f  and     esi, 105h
0x18000b175  xor     r13d, r13d
0x18000b178  xor     edx, edx
0x18000b17a  mov     [rbp+arg_10], esi
0x18000b17d  mov     [rbp+var_38], edx
0x18000b180  cmp     edi, 6
0x18000b183  jnz     short loc_18000B1C0
0x18000b185  mov     rcx, [rax+30h]; Sid
0x18000b189  test    rcx, rcx
0x18000b18c  jz      short loc_18000B1A9
0x18000b18e  movzx   ebx, word ptr [rax+12h]
0x18000b192  movzx   edi, word ptr [rax+22h]
0x18000b196  call    cs:__imp_RtlLengthSid
0x18000b19c  add     eax, ebx
0x18000b19e  add     eax, edi
0x18000b1a0  mov     edi, [rbp+arg_18]
0x18000b1a3  add     r13d, 38h ; '8'
0x18000b1a7  jmp     short loc_18000B1E0
0x18000b1a9  cmp     [rbp+arg_20], r15b
0x18000b1ad  jz      short loc_18000B1E6
0x18000b1af  movzx   ecx, word ptr [rax+22h]
0x18000b1b3  movzx   eax, word ptr [rax+12h]
0x18000b1b7  add     eax, r13d
0x18000b1ba  lea     r13d, [rcx+38h]
0x18000b1be  jmp     short loc_18000B1E0
0x18000b1c0  test    byte ptr [rax+38h], 2
0x18000b1c4  jz      short loc_18000B1E6
0x18000b1c6  cmp     [rcx+10h], r15
0x18000b1ca  jz      short loc_18000B1E6
0x18000b1cc  movzx   ebx, word ptr [rcx+2]
0x18000b1d0  mov     rcx, [rcx+10h]; Sid
0x18000b1d4  call    cs:__imp_RtlLengthSid
0x18000b1da  add     eax, ebx
0x18000b1dc  add     r13d, 18h
0x18000b1e0  add     r13d, eax
0x18000b1e3  inc     r12d
0x18000b1e6  inc     [rbp+var_38]
0x18000b1e9  cmp     r13d, [rbp+var_34]
0x18000b1ed  jnb     short loc_18000B21B
0x18000b1ef  cmp     esi, 105h
0x18000b1f5  jnz     short loc_18000B21B
0x18000b1f7  lea     rdx, [rbp+var_28]; struct _LSAPR_TRUST_INFORMATION **
0x18000b1fb  lea     rcx, [rbp+var_30]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18000b1ff  call    ?LsaDbpTraverseTrustedDomainList@@YAJPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAPEAU_LSAPR_TRUST_INFORMATION@@@Z; LsaDbpTraverseTrustedDomainList(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *,_LSAPR_TRUST_INFORMATION * *)
0x18000b204  mov     esi, eax
0x18000b206  test    eax, eax
0x18000b208  js      loc_18000B105
0x18000b20e  mov     rax, [rbp+var_30]
0x18000b212  mov     rcx, [rbp+var_28]
0x18000b216  jmp     loc_18000B180
0x18000b21b  mov     eax, 38h ; '8'
0x18000b220  cmp     edi, 6
0x18000b223  lea     ecx, [rax-20h]
0x18000b226  cmovnz  eax, ecx
0x18000b229  imul    eax, r12d
0x18000b22d  test    eax, eax
0x18000b22f  jz      short loc_18000B25F
0x18000b231  mov     edx, eax; uBytes
0x18000b233  mov     ecx, 40h ; '@'; uFlags
0x18000b238  mov     ebx, eax
0x18000b23a  call    cs:__imp_LocalAlloc
0x18000b240  mov     r15, rax
0x18000b243  test    rax, rax
0x18000b246  jnz     short loc_18000B252
0x18000b248  mov     esi, 0C000009Ah
0x18000b24d  jmp     loc_18000B105
0x18000b252  mov     r8, rbx; Size
0x18000b255  xor     edx, edx; Val
0x18000b257  mov     rcx, rax; void *
0x18000b25a  call    memset_0
0x18000b25f  mov     rdi, [rbp+var_20]
0x18000b263  xor     r13d, r13d
0x18000b266  mov     eax, [rbp+arg_10]
0x18000b269  mov     [rbp+var_28], rdi
0x18000b26d  mov     [rbp+var_30], r14
0x18000b271  cmp     [rbp+arg_18], 6
0x18000b275  jnz     loc_18000B350
0x18000b27b  cmp     qword ptr [r14+30h], 0
0x18000b280  jnz     short loc_18000B28C
0x18000b282  cmp     [rbp+arg_20], 0
0x18000b286  jz      loc_18000B3AC
0x18000b28c  cmp     r13d, r12d
0x18000b28f  jz      loc_18000B3D6
0x18000b295  xorps   xmm0, xmm0
0x18000b298  mov     eax, r13d
0x18000b29b  imul    rbx, rax, 38h ; '8'
0x18000b29f  xor     eax, eax
0x18000b2a1  lea     r8, [r14+10h]
0x18000b2a5  add     rbx, r15
0x18000b2a8  xor     ecx, ecx
0x18000b2aa  mov     rdx, rbx
0x18000b2ad  movups  xmmword ptr [rbx], xmm0
0x18000b2b0  movups  xmmword ptr [rbx+10h], xmm0
0x18000b2b4  movups  xmmword ptr [rbx+20h], xmm0
0x18000b2b8  mov     [rbx+30h], rax
0x18000b2bc  call    cs:__imp_LsapRpcCopyUnicodeString
0x18000b2c2  mov     esi, eax
0x18000b2c4  test    eax, eax
0x18000b2c6  js      short loc_18000B2F9
0x18000b2c8  lea     r8, [r14+20h]
0x18000b2cc  xor     ecx, ecx
0x18000b2ce  lea     rdx, [rbx+10h]
0x18000b2d2  call    cs:__imp_LsapRpcCopyUnicodeString
0x18000b2d8  mov     esi, eax
0x18000b2da  test    eax, eax
0x18000b2dc  js      short loc_18000B2F9
0x18000b2de  mov     r8, [r14+30h]
0x18000b2e2  test    r8, r8
0x18000b2e5  jz      short loc_18000B331
0x18000b2e7  lea     rdx, [rbx+20h]
0x18000b2eb  xor     ecx, ecx
0x18000b2ed  call    cs:__imp_LsapRpcCopySid
0x18000b2f3  mov     esi, eax
0x18000b2f5  test    eax, eax
0x18000b2f7  jns     short loc_18000B339
0x18000b2f9  mov     rcx, [rbx+8]; hMem
0x18000b2fd  call    cs:__imp_LocalFree
0x18000b303  mov     rcx, [rbx+18h]; hMem
0x18000b307  mov     qword ptr [rbx+8], 0
0x18000b30f  call    cs:__imp_LocalFree
0x18000b315  mov     rcx, [rbx+20h]; hMem
0x18000b319  mov     qword ptr [rbx+18h], 0
0x18000b321  call    cs:__imp_LocalFree
0x18000b327  mov     qword ptr [rbx+20h], 0
0x18000b32f  jmp     short loc_18000B398
0x18000b331  mov     qword ptr [rbx+20h], 0
0x18000b339  mov     eax, [r14+3Ch]
0x18000b33d  mov     [rbx+2Ch], eax
0x18000b340  mov     eax, [r14+38h]
0x18000b344  mov     [rbx+28h], eax
0x18000b347  mov     eax, [r14+40h]
0x18000b34b  mov     [rbx+30h], eax
0x18000b34e  jmp     short loc_18000B39C
0x18000b350  test    byte ptr [r14+38h], 2
0x18000b355  jz      short loc_18000B3AC
0x18000b357  cmp     qword ptr [rdi+10h], 0
0x18000b35c  jz      short loc_18000B3AC
0x18000b35e  cmp     r13d, r12d
0x18000b361  jz      short loc_18000B3D6
0x18000b363  lea     rcx, ds:0[r13*2]
0x18000b36b  mov     r8, rdi
0x18000b36e  add     rcx, r13
0x18000b371  lea     rbx, [r15+rcx*8]
0x18000b375  xor     ecx, ecx
0x18000b377  mov     rdx, rbx
0x18000b37a  call    cs:__imp_LsapRpcCopyUnicodeString
0x18000b380  mov     esi, eax
0x18000b382  test    eax, eax
0x18000b384  js      short loc_18000B398
0x18000b386  mov     r8, [rdi+10h]
0x18000b38a  lea     rdx, [rbx+10h]
0x18000b38e  xor     ecx, ecx
0x18000b390  call    cs:__imp_LsapRpcCopySid
0x18000b396  mov     esi, eax
0x18000b398  test    esi, esi
0x18000b39a  js      short loc_18000B3F2
0x18000b39c  mov     eax, [r14+60h]
0x18000b3a0  inc     r13d
0x18000b3a3  mov     rcx, [rbp+arg_0]
0x18000b3a7  mov     [rcx], eax
0x18000b3a9  mov     eax, [rbp+arg_10]
0x18000b3ac  cmp     eax, 105h
0x18000b3b1  jnz     short loc_18000B3DB
0x18000b3b3  lea     rdx, [rbp+var_28]; struct _LSAPR_TRUST_INFORMATION **
0x18000b3b7  lea     rcx, [rbp+var_30]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18000b3bb  call    ?LsaDbpTraverseTrustedDomainList@@YAJPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAPEAU_LSAPR_TRUST_INFORMATION@@@Z; LsaDbpTraverseTrustedDomainList(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *,_LSAPR_TRUST_INFORMATION * *)
0x18000b3c0  mov     esi, eax
0x18000b3c2  test    eax, eax
0x18000b3c4  js      short loc_18000B3F2
0x18000b3c6  mov     r14, [rbp+var_30]
0x18000b3ca  mov     rdi, [rbp+var_28]
0x18000b3ce  mov     [rbp+arg_10], eax
0x18000b3d1  jmp     loc_18000B271
0x18000b3d6  mov     eax, 105h
0x18000b3db  cmp     [rbp+var_38], 0
0x18000b3df  jz      short loc_18000B3ED
0x18000b3e1  test    r12d, r12d
0x18000b3e4  jz      short loc_18000B3ED
0x18000b3e6  mov     esi, eax
0x18000b3e8  jmp     loc_18000B105
0x18000b3ed  mov     esi, 8000001Ah
0x18000b3f2  test    r15, r15
0x18000b3f5  jz      loc_18000B105
0x18000b3fb  cmp     [rbp+arg_18], 6
0x18000b3ff  lea     rcx, [rbp+var_20]
0x18000b403  mov     dword ptr [rbp+var_20+4], 0
0x18000b40a  mov     [rbp+var_18], r15
0x18000b40e  mov     dword ptr [rbp+var_20], r12d
0x18000b412  jnz     short loc_18000B41C
0x18000b414  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER_EX
0x18000b41a  jmp     short loc_18000B422
0x18000b41c  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_ENUM_BUFFER
0x18000b422  xor     r15d, r15d
0x18000b425  jmp     loc_18000B105
```
