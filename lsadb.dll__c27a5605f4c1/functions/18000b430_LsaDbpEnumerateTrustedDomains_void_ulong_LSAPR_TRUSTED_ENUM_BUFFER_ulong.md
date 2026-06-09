# LsaDbpEnumerateTrustedDomains(void *,ulong *,_LSAPR_TRUSTED_ENUM_BUFFER *,ulong)

- ea: `0x18000b430`
- end: `0x18000b7bf`
- name: `?LsaDbpEnumerateTrustedDomains@@YAJPEAXPEAKPEAU_LSAPR_TRUSTED_ENUM_BUFFER@@K@Z`
- size: `911`
- prototype: `__int64 __fastcall(void *, unsigned int *, struct _LSAPR_TRUSTED_ENUM_BUFFER *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180001fb8`
- `0x18000b430`
- `0x18002c328`
- `0x18002c818`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b689`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b689`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b6d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b6d1`
- `LSASRV!LsapDbFreeTrustedDomainsEx` at `0x18000b778`
- `LSASRV!LsapDbFreeTrustedDomainsEx` at `0x18000b78e`
- `LSASRV!LsapDbFreeTrustedDomainsEx` at `0x18000b778`
- `LSASRV!LsapDbFreeTrustedDomainsEx` at `0x18000b78e`
- `LSASRV!LsapRpcCopySid` at `0x18000b70e`
- `LSASRV!LsapRpcCopySid` at `0x18000b70e`
- `LSASRV!LsapDbEnumerateTrustedDomainsEx` at `0x18000b544`
- `LSASRV!LsapDbEnumerateTrustedDomainsEx` at `0x18000b544`
- `LSASRV!LsapTraceEvent` at `0x18000b47b`
- `LSASRV!LsapTraceEvent` at `0x18000b79c`
- `LSASRV!LsapTraceEvent` at `0x18000b47b`
- `LSASRV!LsapTraceEvent` at `0x18000b79c`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b6f8`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b6f8`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18000b760`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18000b760`
- `LSASRV!LsapDbQueryInformationPolicy` at `0x18000b575`
- `LSASRV!LsapDbQueryInformationPolicy` at `0x18000b575`
- `ntdll!RtlEqualSid` at `0x18000b594`
- `ntdll!RtlEqualSid` at `0x18000b5c7`
- `ntdll!RtlEqualSid` at `0x18000b594`
- `ntdll!RtlEqualSid` at `0x18000b5c7`

## pseudocode

```c
__int64 __fastcall LsaDbpEnumerateTrustedDomains(void *a1, unsigned int *a2, const void **a3)
{
  char v3; // r13
  void *v6; // rcx
  signed int v7; // ebx
  char *v8; // rsi
  unsigned int v9; // r15d
  int v10; // eax
  struct _LIST_ENTRY *Flink; // rdi
  unsigned int v12; // eax
  int v13; // ecx
  unsigned int v14; // r12d
  unsigned int v15; // edx
  unsigned int i; // ebx
  void *v17; // rcx
  struct _LIST_ENTRY *v18; // rax
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v20; // rax
  unsigned int v21; // eax
  size_t v22; // rbx
  char *v23; // rax
  struct _LIST_ENTRY *v24; // rdi
  __int64 v25; // r9
  int v27; // [rsp+40h] [rbp-29h]
  unsigned int v28; // [rsp+44h] [rbp-25h]
  int v29; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  __int64 v31; // [rsp+58h] [rbp-11h] BYREF
  struct _LIST_ENTRY *v32; // [rsp+60h] [rbp-9h]
  struct _LIST_ENTRY v33; // [rsp+68h] [rbp-1h] BYREF
  struct _LIST_ENTRY v34; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v36; // [rsp+E0h] [rbp+77h] BYREF

  v3 = 0;
  v31 = 0;
  v30 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  LsapTraceEvent(1, 5);
  if ( a3 )
  {
    v8 = 0;
    v33.Blink = &v33;
    v9 = 0;
    v33.Flink = &v33;
    v34.Blink = &v34;
    v34.Flink = &v34;
    v7 = LsaDbpBuildForestTrustInfoLists(v6, &v34);
    if ( v7 >= 0 )
    {
      v10 = *a2;
      Flink = v34.Flink;
      v12 = v10 & 0x7FFFFFFF;
      v28 = v12;
      v13 = 0;
      v14 = 0;
      v27 = 0;
      while ( Flink != &v34 )
      {
        v32 = Flink->Flink;
        if ( v14 >= v12 && Flink[6].Flink && LOWORD(Flink[2].Flink) )
        {
          if ( !v3 )
          {
            v29 = 0;
            v7 = LsapDbEnumerateTrustedDomainsEx(LsaDbpPolicyHandle, &v29, 5, &v30, -1, &v36, 1);
            if ( v7 == -2147483622 )
            {
              v36 = 0;
              v30 = 0;
            }
            else if ( v7 )
            {
              if ( v7 == 261 )
                v7 = -1073741596;
              goto LABEL_44;
            }
            v7 = LsapDbQueryInformationPolicy(LsaDbpPolicyHandle, 3, &v31);
            if ( v7 < 0 )
              goto LABEL_44;
            v3 = 1;
          }
          if ( RtlEqualSid(*(PSID *)(v31 + 16), Flink[6].Flink) )
          {
LABEL_24:
            v13 = v27;
          }
          else
          {
            v15 = v36;
            for ( i = 0; i < v15; ++i )
            {
              v17 = *(void **)(v30 + 24LL * i + 16);
              if ( v17 )
              {
                if ( RtlEqualSid(v17, Flink[6].Flink) )
                  goto LABEL_24;
                v15 = v36;
              }
            }
            v18 = Flink->Flink;
            if ( Flink->Flink->Blink != Flink
              || (Blink = Flink->Blink, Blink->Flink != Flink)
              || (Blink->Flink = v18, v18->Blink = Blink, v20 = v33.Blink, v33.Blink->Flink != &v33) )
            {
              __fastfail(3u);
            }
            Flink->Blink = v33.Blink;
            Flink->Flink = &v33;
            v13 = v27 + 1;
            v20->Flink = Flink;
            ++v27;
            v33.Blink = Flink;
          }
          v12 = v28;
        }
        Flink = v32;
        ++v14;
      }
      v21 = 24 * (*(_DWORD *)a3 + v13);
      if ( v21 )
      {
        v22 = v21;
        v23 = (char *)LocalAlloc(0x40u, v21);
        v8 = v23;
        if ( v23 )
        {
          memset_0(v23, 0, v22);
          if ( *(_DWORD *)a3 )
          {
            v9 = *(_DWORD *)a3;
            memcpy_0(v8, a3[1], 24LL * *(unsigned int *)a3);
            LocalFree((HLOCAL)a3[1]);
            a3[1] = 0;
            *(_DWORD *)a3 = 0;
          }
          v24 = v33.Flink;
          while ( v24 != &v33 )
          {
            v7 = LsapRpcCopyUnicodeString(0, &v8[24 * v9], &v24[2]);
            if ( v7 < 0 )
              goto LABEL_44;
            v7 = LsapRpcCopySid(0, &v8[24 * v9 + 16], v24[6].Flink, v25);
            if ( v7 < 0 )
              goto LABEL_44;
            v24 = v24->Flink;
            ++v9;
          }
          v7 = 0;
          *a2 = v14 | 0x80000000;
          a3[1] = v8;
          v8 = 0;
          *(_DWORD *)a3 = v9;
        }
        else
        {
          v7 = -1073741670;
        }
      }
      else
      {
        v7 = *a2 != 0 ? 0x8000001A : 0;
      }
    }
LABEL_44:
    LsaDbpDsForestFreeTrustBlobList(&v34);
    LsaDbpDsForestFreeTrustBlobList(&v33);
    LsaIFree_LSAPR_POLICY_INFORMATION(3);
    if ( v30 )
      LsapDbFreeTrustedDomainsEx(5, v30, v36);
    if ( v8 )
      LsapDbFreeTrustedDomainsEx(5, v8, v9);
  }
  else
  {
    v7 = -1073741811;
  }
  LsapTraceEvent(2, 5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b430  mov     [rsp-8+arg_0], rbx
0x18000b435  mov     [rsp-8+arg_8], rdx
0x18000b43a  push    rbp
0x18000b43b  push    rsi
0x18000b43c  push    rdi
0x18000b43d  push    r12
0x18000b43f  push    r13
0x18000b441  push    r14
0x18000b443  push    r15
0x18000b445  lea     rbp, [rsp-27h]
0x18000b44a  sub     rsp, 90h
0x18000b451  xor     r13d, r13d
0x18000b454  mov     rdi, rdx
0x18000b457  xorps   xmm0, xmm0
0x18000b45a  mov     [rbp+57h+var_68], r13
0x18000b45e  xorps   xmm1, xmm1
0x18000b461  mov     [rbp+57h+var_70], r13
0x18000b465  mov     r14, r8
0x18000b468  mov     [rbp+57h+arg_10], r13d
0x18000b46c  lea     edx, [r13+5]
0x18000b470  lea     ecx, [rdx-4]
0x18000b473  movups  xmmword ptr [rbp+57h+var_58.Flink], xmm0
0x18000b477  movups  xmmword ptr [rbp+57h+var_48.Flink], xmm1
0x18000b47b  call    cs:__imp_LsapTraceEvent
0x18000b481  test    r14, r14
0x18000b484  jnz     short loc_18000B490
0x18000b486  mov     ebx, 0C000000Dh
0x18000b48b  jmp     loc_18000B794
0x18000b490  lea     rax, [rbp+57h+var_58]
0x18000b494  mov     rsi, r13
0x18000b497  mov     [rbp+57h+var_58.Blink], rax
0x18000b49b  lea     rdx, [rbp+57h+var_48]; struct _LIST_ENTRY *
0x18000b49f  lea     rax, [rbp+57h+var_58]
0x18000b4a3  mov     r15d, r13d
0x18000b4a6  mov     [rbp+57h+var_58.Flink], rax
0x18000b4aa  lea     rax, [rbp+57h+var_48]
0x18000b4ae  mov     [rbp+57h+var_48.Blink], rax
0x18000b4b2  lea     rax, [rbp+57h+var_48]
0x18000b4b6  mov     [rbp+57h+var_48.Flink], rax
0x18000b4ba  call    ?LsaDbpBuildForestTrustInfoLists@@YAJPEAXPEAU_LIST_ENTRY@@@Z; LsaDbpBuildForestTrustInfoLists(void *,_LIST_ENTRY *)
0x18000b4bf  mov     ebx, eax
0x18000b4c1  test    eax, eax
0x18000b4c3  js      loc_18000B745
0x18000b4c9  mov     eax, [rdi]
0x18000b4cb  mov     rdi, [rbp+57h+var_48.Flink]
0x18000b4cf  btr     eax, 1Fh
0x18000b4d3  xor     r8d, r8d
0x18000b4d6  mov     [rbp+57h+var_7C], eax
0x18000b4d9  mov     ecx, r8d
0x18000b4dc  mov     r12d, r8d
0x18000b4df  mov     [rbp+57h+var_80], ecx
0x18000b4e2  jmp     loc_18000B634
0x18000b4e7  mov     rbx, [rdi]
0x18000b4ea  mov     [rbp+57h+var_60], rbx
0x18000b4ee  cmp     r12d, eax
0x18000b4f1  jb      loc_18000B62D
0x18000b4f7  cmp     [rdi+60h], r8
0x18000b4fb  jz      loc_18000B62D
0x18000b501  cmp     [rdi+20h], r8w
0x18000b506  jz      loc_18000B62D
0x18000b50c  test    r13b, r13b
0x18000b50f  jnz     short loc_18000B588
0x18000b511  mov     rcx, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x18000b518  lea     rax, [rbp+57h+arg_10]
0x18000b51c  xor     r13d, r13d
0x18000b51f  mov     [rsp+0C0h+var_90], 1
0x18000b527  mov     [rsp+0C0h+var_98], rax
0x18000b52c  lea     r9, [rbp+57h+var_70]
0x18000b530  lea     rdx, [rbp+57h+var_78]
0x18000b534  mov     [rbp+57h+var_78], r13d
0x18000b538  mov     [rsp+0C0h+var_A0], 0FFFFFFFFh
0x18000b540  lea     r8d, [r13+5]
0x18000b544  call    cs:__imp_LsapDbEnumerateTrustedDomainsEx
0x18000b54a  mov     ebx, eax
0x18000b54c  cmp     eax, 8000001Ah
0x18000b551  jnz     short loc_18000B55D
0x18000b553  mov     [rbp+57h+arg_10], r13d
0x18000b557  mov     [rbp+57h+var_70], r13
0x18000b55b  jmp     short loc_18000B565
0x18000b55d  test    ebx, ebx
0x18000b55f  jnz     loc_18000B666
0x18000b565  mov     rcx, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x18000b56c  lea     r8, [rbp+57h+var_68]
0x18000b570  mov     edx, 3
0x18000b575  call    cs:__imp_LsapDbQueryInformationPolicy
0x18000b57b  mov     ebx, eax
0x18000b57d  test    eax, eax
0x18000b57f  js      loc_18000B745
0x18000b585  mov     r13b, 1
0x18000b588  mov     rcx, [rbp+57h+var_68]
0x18000b58c  mov     rdx, [rdi+60h]; Sid2
0x18000b590  mov     rcx, [rcx+10h]; Sid1
0x18000b594  call    cs:__imp_RtlEqualSid
0x18000b59a  xor     r8d, r8d
0x18000b59d  test    al, al
0x18000b59f  jnz     loc_18000B627
0x18000b5a5  mov     edx, [rbp+57h+arg_10]
0x18000b5a8  mov     ebx, r8d
0x18000b5ab  test    edx, edx
0x18000b5ad  jz      short loc_18000B5DD
0x18000b5af  mov     eax, ebx
0x18000b5b1  lea     rcx, [rax+rax*2]
0x18000b5b5  mov     rax, [rbp+57h+var_70]
0x18000b5b9  mov     rcx, [rax+rcx*8+10h]; Sid1
0x18000b5be  test    rcx, rcx
0x18000b5c1  jz      short loc_18000B5D7
0x18000b5c3  mov     rdx, [rdi+60h]; Sid2
0x18000b5c7  call    cs:__imp_RtlEqualSid
0x18000b5cd  xor     r8d, r8d
0x18000b5d0  test    al, al
0x18000b5d2  jnz     short loc_18000B627
0x18000b5d4  mov     edx, [rbp+57h+arg_10]
0x18000b5d7  inc     ebx
0x18000b5d9  cmp     ebx, edx
0x18000b5db  jb      short loc_18000B5AF
0x18000b5dd  mov     rax, [rdi]
0x18000b5e0  cmp     [rax+8], rdi
0x18000b5e4  jnz     loc_18000B679
0x18000b5ea  mov     rcx, [rdi+8]
0x18000b5ee  cmp     [rcx], rdi
0x18000b5f1  jnz     loc_18000B679
0x18000b5f7  mov     [rcx], rax
0x18000b5fa  mov     [rax+8], rcx
0x18000b5fe  lea     rcx, [rbp+57h+var_58]
0x18000b602  mov     rax, [rbp+57h+var_58.Blink]
0x18000b606  cmp     [rax], rcx
0x18000b609  jnz     short loc_18000B679
0x18000b60b  lea     rcx, [rbp+57h+var_58]
0x18000b60f  mov     [rdi+8], rax
0x18000b613  mov     [rdi], rcx
0x18000b616  mov     ecx, [rbp+57h+var_80]
0x18000b619  inc     ecx
0x18000b61b  mov     [rax], rdi
0x18000b61e  mov     [rbp+57h+var_80], ecx
0x18000b621  mov     [rbp+57h+var_58.Blink], rdi
0x18000b625  jmp     short loc_18000B62A
0x18000b627  mov     ecx, [rbp+57h+var_80]
0x18000b62a  mov     eax, [rbp+57h+var_7C]
0x18000b62d  mov     rdi, [rbp+57h+var_60]
0x18000b631  inc     r12d
0x18000b634  lea     rdx, [rbp+57h+var_48]
0x18000b638  cmp     rdi, rdx
0x18000b63b  jnz     loc_18000B4E7
0x18000b641  add     ecx, [r14]
0x18000b644  xor     r13d, r13d
0x18000b647  lea     eax, [rcx+rcx*2]
0x18000b64a  shl     eax, 3
0x18000b64d  test    eax, eax
0x18000b64f  jnz     short loc_18000B680
0x18000b651  mov     rax, [rbp+57h+arg_8]
0x18000b655  mov     eax, [rax]
0x18000b657  neg     eax
0x18000b659  sbb     ebx, ebx
0x18000b65b  and     ebx, 8000001Ah
0x18000b661  jmp     loc_18000B745
0x18000b666  cmp     ebx, 105h
0x18000b66c  mov     eax, 0C00000E4h
0x18000b671  cmovz   ebx, eax
0x18000b674  jmp     loc_18000B745
0x18000b679  mov     ecx, 3
0x18000b67e  int     29h; Win8: RtlFailFast(ecx)
0x18000b680  mov     edx, eax; uBytes
0x18000b682  mov     ecx, 40h ; '@'; uFlags
0x18000b687  mov     ebx, eax
0x18000b689  call    cs:__imp_LocalAlloc
0x18000b68f  mov     rsi, rax
0x18000b692  test    rax, rax
0x18000b695  jnz     short loc_18000B6A1
0x18000b697  mov     ebx, 0C000009Ah
0x18000b69c  jmp     loc_18000B745
0x18000b6a1  mov     r8, rbx; Size
0x18000b6a4  xor     edx, edx; Val
0x18000b6a6  mov     rcx, rsi; void *
0x18000b6a9  call    memset_0
0x18000b6ae  cmp     [r14], r13d
0x18000b6b1  jz      short loc_18000B6DE
0x18000b6b3  mov     r15d, [r14]
0x18000b6b6  mov     rcx, rsi; void *
0x18000b6b9  mov     rdx, [r14+8]; Src
0x18000b6bd  mov     eax, r15d
0x18000b6c0  lea     r8, [rax+rax*2]
0x18000b6c4  shl     r8, 3; Size
0x18000b6c8  call    memcpy_0
0x18000b6cd  mov     rcx, [r14+8]; hMem
0x18000b6d1  call    cs:__imp_LocalFree
0x18000b6d7  mov     [r14+8], r13
0x18000b6db  mov     [r14], r13d
0x18000b6de  mov     rdi, [rbp+57h+var_58.Flink]
0x18000b6e2  jmp     short loc_18000B723
0x18000b6e4  mov     eax, r15d
0x18000b6e7  lea     r8, [rdi+20h]
0x18000b6eb  lea     rcx, [rax+rax*2]
0x18000b6ef  lea     r13, [rsi+rcx*8]
0x18000b6f3  xor     ecx, ecx
0x18000b6f5  mov     rdx, r13
0x18000b6f8  call    cs:__imp_LsapRpcCopyUnicodeString
0x18000b6fe  mov     ebx, eax
0x18000b700  test    eax, eax
0x18000b702  js      short loc_18000B745
0x18000b704  mov     r8, [rdi+60h]
0x18000b708  lea     rdx, [r13+10h]
0x18000b70c  xor     ecx, ecx
0x18000b70e  call    cs:__imp_LsapRpcCopySid
0x18000b714  xor     r13d, r13d
0x18000b717  mov     ebx, eax
0x18000b719  test    eax, eax
0x18000b71b  js      short loc_18000B745
0x18000b71d  mov     rdi, [rdi]
0x18000b720  inc     r15d
0x18000b723  lea     rax, [rbp+57h+var_58]
0x18000b727  cmp     rdi, rax
0x18000b72a  jnz     short loc_18000B6E4
0x18000b72c  mov     rax, [rbp+57h+arg_8]
0x18000b730  bts     r12d, 1Fh
0x18000b735  mov     ebx, r13d
0x18000b738  mov     [rax], r12d
0x18000b73b  mov     [r14+8], rsi
0x18000b73f  mov     rsi, r13
0x18000b742  mov     [r14], r15d
0x18000b745  lea     rcx, [rbp+57h+var_48]; struct _LIST_ENTRY *
0x18000b749  call    ?LsaDbpDsForestFreeTrustBlobList@@YAXPEAU_LIST_ENTRY@@@Z; LsaDbpDsForestFreeTrustBlobList(_LIST_ENTRY *)
0x18000b74e  lea     rcx, [rbp+57h+var_58]; struct _LIST_ENTRY *
0x18000b752  call    ?LsaDbpDsForestFreeTrustBlobList@@YAXPEAU_LIST_ENTRY@@@Z; LsaDbpDsForestFreeTrustBlobList(_LIST_ENTRY *)
0x18000b757  mov     rdx, [rbp+57h+var_68]
0x18000b75b  mov     ecx, 3
0x18000b760  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x18000b766  mov     rdx, [rbp+57h+var_70]
0x18000b76a  test    rdx, rdx
0x18000b76d  jz      short loc_18000B77E
0x18000b76f  mov     r8d, [rbp+57h+arg_10]
0x18000b773  mov     ecx, 5
0x18000b778  call    cs:__imp_LsapDbFreeTrustedDomainsEx
0x18000b77e  test    rsi, rsi
0x18000b781  jz      short loc_18000B794
0x18000b783  mov     r8d, r15d
0x18000b786  mov     rdx, rsi
0x18000b789  mov     ecx, 5
0x18000b78e  call    cs:__imp_LsapDbFreeTrustedDomainsEx
0x18000b794  mov     edx, 5
0x18000b799  lea     ecx, [rdx-3]
0x18000b79c  call    cs:__imp_LsapTraceEvent
0x18000b7a2  mov     eax, ebx
0x18000b7a4  mov     rbx, [rsp+0C0h+arg_0]
0x18000b7ac  add     rsp, 90h
0x18000b7b3  pop     r15
0x18000b7b5  pop     r14
0x18000b7b7  pop     r13
0x18000b7b9  pop     r12
0x18000b7bb  pop     rdi
0x18000b7bc  pop     rsi
0x18000b7bd  pop     rbp
0x18000b7be  retn
```
