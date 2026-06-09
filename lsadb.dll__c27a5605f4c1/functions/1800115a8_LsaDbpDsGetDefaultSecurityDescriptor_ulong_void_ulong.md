# LsaDbpDsGetDefaultSecurityDescriptor(ulong,void * *,ulong *)

- ea: `0x1800115a8`
- end: `0x1800117aa`
- name: `?LsaDbpDsGetDefaultSecurityDescriptor@@YAJKPEAPEAXPEAK@Z`
- size: `514`
- prototype: `int(unsigned int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f43c`

## callees

- `0x180001670`
- `0x1800115a8`
- `0x180012a24`
- `0x180012a74`
- `0x1800361ec`
- `0x180036940`
- `0x1800372f4`
- `0x18003acd0`
- `0x18003b010`

## import_xrefs

- `LSASRV!LsapGetWellKnownSid` at `0x180011703`
- `LSASRV!LsapGetWellKnownSid` at `0x18001171f`
- `LSASRV!LsapGetWellKnownSid` at `0x180011703`
- `LSASRV!LsapGetWellKnownSid` at `0x18001171f`
- `LSASRV!LsapFreeLsaHeap` at `0x180011776`
- `LSASRV!LsapFreeLsaHeap` at `0x180011784`
- `LSASRV!LsapFreeLsaHeap` at `0x180011776`
- `LSASRV!LsapFreeLsaHeap` at `0x180011784`
- `NTDSA!SampGetClassAttribute` at `0x1800115f8`
- `NTDSA!SampGetClassAttribute` at `0x1800116b4`
- `NTDSA!SampGetClassAttribute` at `0x1800115f8`
- `NTDSA!SampGetClassAttribute` at `0x1800116b4`

## pseudocode

```c
__int64 __fastcall LsaDbpDsGetDefaultSecurityDescriptor(__int64 a1, void **a2, unsigned int *a3)
{
  struct _TOKEN_OWNER *v4; // rsi
  struct _TOKEN_PRIMARY_GROUP *v5; // r14
  unsigned int v6; // r12d
  struct _TOKEN_OWNER **v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  int ClassAttribute; // r15d
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  _DWORD *v17; // rax
  struct _ACL *Sacl; // r15
  struct _ACL *Dacl; // rax
  struct _ACL *v20; // r12
  PSID PrimaryGroup; // rdi
  PSID Owner; // rax
  __int64 v24; // [rsp+0h] [rbp-30h] BYREF
  unsigned int v25; // [rsp+30h] [rbp+0h] BYREF
  struct _TOKEN_OWNER *v26; // [rsp+38h] [rbp+8h] BYREF
  struct _TOKEN_PRIMARY_GROUP *v27; // [rsp+40h] [rbp+10h] BYREF
  void **v28; // [rsp+48h] [rbp+18h]

  v28 = a2;
  v4 = 0;
  v25 = 0;
  v5 = 0;
  v26 = 0;
  v27 = 0;
  v6 = a1;
  v7 = 0;
  ClassAttribute = SampGetClassAttribute(a1, 590048, &v25, 0);
  if ( ClassAttribute != -1073741789 )
    goto LABEL_15;
  v11 = v25;
  if ( !v25 )
    goto LABEL_35;
  if ( v25 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_35;
  v12 = v25 + g_ulAdditionalProbeSize + 8;
  if ( v12 < v25 || !(unsigned int)VerifyStackAvailable(v12, v8) )
    goto LABEL_35;
  v13 = v11 + 23;
  if ( v11 + 23 <= v11 + 8 )
    v13 = 0xFFFFFFFFFFFFFF0LL;
  v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
  v15 = alloca(v14);
  v16 = alloca(v14);
  v7 = (struct _TOKEN_OWNER **)&v25;
  if ( &v24 == (__int64 *)-48LL || (v25 = 1801679955, (v7 = &v26) == 0) )
  {
LABEL_35:
    if ( v11 + 8 >= v11 )
    {
      v17 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v7 = (struct _TOKEN_OWNER **)v17;
      if ( v17 )
      {
        *v17 = 1885431112;
        v7 = (struct _TOKEN_OWNER **)(v17 + 2);
      }
    }
  }
  if ( v7 )
  {
    ClassAttribute = SampGetClassAttribute(v6, 590048, &v25, v7);
LABEL_15:
    if ( ClassAttribute >= 0 )
    {
      ClassAttribute = LsaDbpGetCurrentOwnerAndPrimaryGroup(&v26, &v27);
      if ( ClassAttribute < 0 )
      {
        v4 = v26;
        v5 = v27;
      }
      else
      {
        Sacl = LsaDbpGetSacl(v7);
        Dacl = LsaDbpGetDacl(v7);
        v5 = v27;
        v20 = Dacl;
        if ( v27 )
          PrimaryGroup = v27->PrimaryGroup;
        else
          PrimaryGroup = (PSID)LsapGetWellKnownSid(16);
        v4 = v26;
        if ( v26 )
          Owner = v26->Owner;
        else
          Owner = (PSID)LsapGetWellKnownSid(16);
        ClassAttribute = LsaDbpMakeNewSelfRelativeSecurityDescriptor(Owner, PrimaryGroup, v20, Sacl, a3, v28);
      }
    }
    if ( v7 && *((_DWORD *)v7 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    if ( v4 )
      LsapFreeLsaHeap(v4, v8, v9);
    if ( v5 )
      LsapFreeLsaHeap(v5, v8, v9);
  }
  return (unsigned int)ClassAttribute;
}

```

## disassembly

```asm
0x1800115a8  push    rbp
0x1800115aa  push    rbx
0x1800115ab  push    rsi
0x1800115ac  push    rdi
0x1800115ad  push    r12
0x1800115af  push    r13
0x1800115b1  push    r14
0x1800115b3  push    r15
0x1800115b5  sub     rsp, 68h
0x1800115b9  lea     rbp, [rsp+30h]
0x1800115be  mov     rax, cs:__security_cookie
0x1800115c5  xor     rax, rbp
0x1800115c8  mov     [rbp+70h+var_48], rax
0x1800115cc  mov     r13, r8
0x1800115cf  mov     [rbp+70h+var_58], rdx
0x1800115d3  xor     esi, esi
0x1800115d5  mov     [rbp+70h+var_70], 0
0x1800115dc  xor     r14d, r14d
0x1800115df  mov     [rbp+70h+var_68], rsi
0x1800115e3  lea     r8, [rbp+70h+var_70]
0x1800115e7  mov     [rbp+70h+var_60], r14
0x1800115eb  mov     edx, 900E0h
0x1800115f0  xor     r9d, r9d
0x1800115f3  mov     r12d, ecx
0x1800115f6  xor     ebx, ebx
0x1800115f8  call    cs:__imp_SampGetClassAttribute
0x1800115fe  mov     r15d, eax
0x180011601  cmp     eax, 0C0000023h
0x180011606  jnz     loc_1800116BD
0x18001160c  mov     edi, [rbp+70h+var_70]
0x18001160f  test    rdi, rdi
0x180011612  jz      short loc_180011675
0x180011614  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001161b  ja      short loc_180011675
0x18001161d  mov     rcx, cs:g_ulAdditionalProbeSize
0x180011624  add     rcx, 8
0x180011628  add     rcx, rdi
0x18001162b  cmp     rcx, rdi
0x18001162e  jb      short loc_180011675
0x180011630  call    VerifyStackAvailable
0x180011635  test    eax, eax
0x180011637  jz      short loc_180011675
0x180011639  lea     rax, [rdi+8]
0x18001163d  lea     rcx, [rax+0Fh]
0x180011641  cmp     rcx, rax
0x180011644  ja      short loc_180011650
0x180011646  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180011650  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180011654  mov     rax, rcx
0x180011657  call    _alloca_probe
0x18001165c  sub     rsp, rcx
0x18001165f  lea     rbx, [rsp+0A0h+var_70]
0x180011664  test    rbx, rbx
0x180011667  jz      short loc_180011675
0x180011669  mov     dword ptr [rbx], 6B637453h
0x18001166f  add     rbx, 8
0x180011673  jnz     short loc_18001169C
0x180011675  lea     rcx, [rdi+8]
0x180011679  cmp     rcx, rdi
0x18001167c  jb      short loc_18001169C
0x18001167e  mov     rax, cs:g_pfnAllocate
0x180011685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001168a  mov     rbx, rax
0x18001168d  test    rax, rax
0x180011690  jz      short loc_18001169C
0x180011692  mov     dword ptr [rax], 70616548h
0x180011698  add     rbx, 8
0x18001169c  test    rbx, rbx
0x18001169f  jz      loc_18001178A
0x1800116a5  mov     r9, rbx
0x1800116a8  lea     r8, [rbp+70h+var_70]
0x1800116ac  mov     edx, 900E0h
0x1800116b1  mov     ecx, r12d
0x1800116b4  call    cs:__imp_SampGetClassAttribute
0x1800116ba  mov     r15d, eax
0x1800116bd  test    r15d, r15d
0x1800116c0  js      loc_180011751
0x1800116c6  lea     rdx, [rbp+70h+var_60]; struct _TOKEN_PRIMARY_GROUP **
0x1800116ca  lea     rcx, [rbp+70h+var_68]; struct _TOKEN_OWNER **
0x1800116ce  call    ?LsaDbpGetCurrentOwnerAndPrimaryGroup@@YAJPEAPEAU_TOKEN_OWNER@@PEAPEAU_TOKEN_PRIMARY_GROUP@@@Z; LsaDbpGetCurrentOwnerAndPrimaryGroup(_TOKEN_OWNER * *,_TOKEN_PRIMARY_GROUP * *)
0x1800116d3  mov     r15d, eax
0x1800116d6  test    eax, eax
0x1800116d8  js      short loc_180011749
0x1800116da  mov     rcx, rbx; void *
0x1800116dd  call    ?LsaDbpGetSacl@@YAPEAU_ACL@@PEAX@Z; LsaDbpGetSacl(void *)
0x1800116e2  mov     rcx, rbx; void *
0x1800116e5  mov     r15, rax
0x1800116e8  call    ?LsaDbpGetDacl@@YAPEAU_ACL@@PEAX@Z; LsaDbpGetDacl(void *)
0x1800116ed  mov     r14, [rbp+70h+var_60]
0x1800116f1  mov     r12, rax
0x1800116f4  test    r14, r14
0x1800116f7  jz      short loc_1800116FE
0x1800116f9  mov     rdi, [r14]
0x1800116fc  jmp     short loc_18001170C
0x1800116fe  mov     ecx, 10h
0x180011703  call    cs:__imp_LsapGetWellKnownSid
0x180011709  mov     rdi, rax
0x18001170c  mov     rsi, [rbp+70h+var_68]
0x180011710  test    rsi, rsi
0x180011713  jz      short loc_18001171A
0x180011715  mov     rax, [rsi]
0x180011718  jmp     short loc_180011725
0x18001171a  mov     ecx, 10h
0x18001171f  call    cs:__imp_LsapGetWellKnownSid
0x180011725  mov     rcx, [rbp+70h+var_58]
0x180011729  mov     r9, r15; pSacl
0x18001172c  mov     [rsp+0A0h+var_78], rcx; void **
0x180011731  mov     r8, r12; pDacl
0x180011734  mov     rcx, rax; pOwner
0x180011737  mov     [rsp+0A0h+lpdwBufferLength], r13; lpdwBufferLength
0x18001173c  mov     rdx, rdi; pGroup
0x18001173f  call    ?LsaDbpMakeNewSelfRelativeSecurityDescriptor@@YAJPEAX0PEAU_ACL@@1PEAKPEAPEAX@Z; LsaDbpMakeNewSelfRelativeSecurityDescriptor(void *,void *,_ACL *,_ACL *,ulong *,void * *)
0x180011744  mov     r15d, eax
0x180011747  jmp     short loc_180011751
0x180011749  mov     rsi, [rbp+70h+var_68]
0x18001174d  mov     r14, [rbp+70h+var_60]
0x180011751  test    rbx, rbx
0x180011754  jz      short loc_18001176E
0x180011756  lea     rcx, [rbx-8]
0x18001175a  cmp     dword ptr [rcx], 70616548h
0x180011760  jnz     short loc_18001176E
0x180011762  mov     rax, cs:g_pfnFree
0x180011769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001176e  test    rsi, rsi
0x180011771  jz      short loc_18001177C
0x180011773  mov     rcx, rsi
0x180011776  call    cs:__imp_LsapFreeLsaHeap
0x18001177c  test    r14, r14
0x18001177f  jz      short loc_18001178A
0x180011781  mov     rcx, r14
0x180011784  call    cs:__imp_LsapFreeLsaHeap
0x18001178a  mov     eax, r15d
0x18001178d  mov     rcx, [rbp+70h+var_48]
0x180011791  xor     rcx, rbp; StackCookie
0x180011794  call    __security_check_cookie
0x180011799  lea     rsp, [rbp+38h]
0x18001179d  pop     r15
0x18001179f  pop     r14
0x1800117a1  pop     r13
0x1800117a3  pop     r12
0x1800117a5  pop     rdi
0x1800117a6  pop     rsi
0x1800117a7  pop     rbx
0x1800117a8  pop     rbp
0x1800117a9  retn
```
