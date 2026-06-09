# FTCache::Match(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)

- ea: `0x18002901c`
- end: `0x180029344`
- name: `?Match@FTCache@@QEAAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z`
- size: `808`
- prototype: `int __high(enum LSA_ROUTING_MATCH_TYPE, void *, unsigned __int8, struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180026674`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x18002901c`
- `0x18002934c`
- `0x1800294ac`
- `0x1800295ac`
- `0x18002970c`
- `0x180029928`
- `0x180029c4c`
- `0x18002a15c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292f5`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x1800292df`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x1800292df`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18002916c`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18002916c`
- `LSASRV!LsapRemoveTrailingDot` at `0x180029119`
- `LSASRV!LsapRemoveTrailingDot` at `0x180029119`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18002930a`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18002930a`
- `ntdll!RtlValidSid` at `0x180029131`
- `ntdll!RtlValidSid` at `0x180029131`

## pseudocode

```c
__int64 __fastcall FTCache::Match(
        __int64 a1,
        int a2,
        struct _UNICODE_STRING *a3,
        unsigned __int8 a4,
        struct _UNICODE_STRING *a5,
        void **a6)
{
  struct _UNICODE_STRING *v8; // r13
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  struct _UNICODE_STRING *v11; // r12
  void **v12; // r14
  USHORT MaximumLength; // dx
  __int64 v14; // rcx
  int v16; // eax
  unsigned __int64 v17; // rcx
  int v18; // ebx
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int matched; // eax
  FTCache *v23; // rdi
  struct _SID *v24; // [rsp+38h] [rbp-30h]
  __int64 v25; // [rsp+70h] [rbp+8h] BYREF
  FTCache *v26; // [rsp+80h] [rbp+18h]
  unsigned __int8 v27; // [rsp+88h] [rbp+20h]

  v27 = a4;
  v25 = a1;
  v26 = g_FTCache;
  v8 = 0;
  LOBYTE(v25) = a4 == 0;
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( (*((_BYTE *)v9 + 28) & 8) != 0 )
    {
      v10 = 159;
LABEL_26:
      WPP_SF_(v9[2], v10, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      return 3221225485LL;
    }
    return 3221225485LL;
  }
  v11 = a5;
  if ( a5 )
  {
    *a5 = 0;
    v9 = WPP_GLOBAL_Control;
  }
  v12 = a6;
  if ( a6 )
  {
    *a6 = 0;
    v9 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( a2 != 1 && a2 != 2 && (unsigned int)(a2 - 3) >= 2 )
    {
      if ( (*((_BYTE *)v9 + 28) & 8) != 0 )
      {
        v10 = 162;
        goto LABEL_26;
      }
      return 3221225485LL;
    }
    MaximumLength = a3->MaximumLength;
    if ( MaximumLength < a3->Length || ((a3->Length | MaximumLength) & 1) != 0 || a3->Length && !a3->Buffer )
    {
      if ( (*((_BYTE *)v9 + 28) & 8) != 0 )
      {
        v10 = 161;
        goto LABEL_26;
      }
      return 3221225485LL;
    }
    v24 = 0;
    v8 = a3;
    LsapRemoveTrailingDot(a3, 0);
  }
  else
  {
    if ( !RtlValidSid(a3) )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v10 = 160;
        goto LABEL_26;
      }
      return 3221225485LL;
    }
    v24 = (struct _SID *)a3;
  }
  LsapDbExpAcquireReadLockTrustedDomainList(v14);
  v16 = FTCache::RebuildCachesIfNecessary(v26, v27, v27 == 0);
  v18 = v16;
  if ( v16 >= 0 )
  {
    if ( !a2 )
    {
      matched = FTCache::MatchSid(v26, v24, (unsigned __int8 *)&v25, v11, v12);
      goto LABEL_43;
    }
    v19 = a2 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
      {
        matched = FTCache::MatchUpn(v26, v8, (unsigned __int8 *)&v25, v11, v12);
        goto LABEL_43;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        matched = FTCache::MatchSpn(v26, v8, (unsigned __int8 *)&v25, v11, v12);
        goto LABEL_43;
      }
      if ( v21 == 1 )
      {
        matched = FTCache::MatchNamespace(v26, v8, (unsigned __int8 *)&v25, v11, v12);
LABEL_43:
        v18 = matched;
      }
    }
    else
    {
      v23 = v26;
      v18 = FTCache::MatchDnsName(v26, v8, (unsigned __int8 *)&v25, v11, v12);
      if ( v18 == -1073741198 )
      {
        matched = FTCache::MatchNetbiosName(v23, v8, (unsigned __int8 *)&v25, v11, v12);
        goto LABEL_43;
      }
    }
    if ( v18 >= 0 )
    {
      v17 = (_BYTE)v25 == 0;
      if ( (_DWORD)v17 != (v27 == 0) )
      {
        v18 = -1073741198;
        if ( v11 )
        {
          LsaIFree_LSAPR_UNICODE_STRING_BUFFER(v11);
          *v11 = 0;
        }
        if ( v12 )
        {
          LocalFree(*v12);
          *v12 = 0;
        }
      }
    }
    goto LABEL_50;
  }
  v17 = (unsigned __int64)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      163,
      &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
      (unsigned int)v16);
LABEL_50:
  LsapDbExpReleaseLockTrustedDomainList(v17);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      164,
      &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
      (unsigned int)v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18002901c  mov     [rsp+arg_18], r9b
0x180029021  mov     [rsp+arg_0], rcx
0x180029026  push    rbx
0x180029027  push    rdi
0x180029028  push    r12
0x18002902a  push    r13
0x18002902c  push    r14
0x18002902e  sub     rsp, 40h
0x180029032  mov     rbx, r8
0x180029035  mov     edi, edx
0x180029037  mov     rax, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x18002903e  mov     [rsp+68h+arg_10], rax
0x180029046  xor     r13d, r13d
0x180029049  test    r9b, r9b
0x18002904c  setz    byte ptr [rsp+68h+arg_0]
0x180029051  mov     rcx, cs:WPP_GLOBAL_Control
0x180029058  test    byte ptr [rcx+1Ch], 8
0x18002905c  jz      short loc_18002907A
0x18002905e  mov     edx, 9Eh
0x180029063  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002906a  mov     rcx, [rcx+10h]
0x18002906e  call    WPP_SF_
0x180029073  mov     rcx, cs:WPP_GLOBAL_Control
0x18002907a  test    rbx, rbx
0x18002907d  jnz     short loc_180029093
0x18002907f  test    byte ptr [rcx+1Ch], 8
0x180029083  jz      loc_18002915D
0x180029089  mov     edx, 9Fh
0x18002908e  jmp     loc_18002914D
0x180029093  mov     r12, [rsp+68h+arg_20]
0x18002909b  test    r12, r12
0x18002909e  jz      short loc_1800290AF
0x1800290a0  xorps   xmm0, xmm0
0x1800290a3  movups  xmmword ptr [r12], xmm0
0x1800290a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290af  mov     r14, [rsp+68h+arg_28]
0x1800290b7  test    r14, r14
0x1800290ba  jz      short loc_1800290C6
0x1800290bc  mov     [r14], r13
0x1800290bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290c6  mov     edx, edi
0x1800290c8  test    edi, edi
0x1800290ca  jz      short loc_18002912E
0x1800290cc  sub     edx, 1
0x1800290cf  jz      short loc_1800290ED
0x1800290d1  sub     edx, 1
0x1800290d4  jz      short loc_1800290ED
0x1800290d6  sub     edx, 1
0x1800290d9  jz      short loc_1800290ED
0x1800290db  cmp     edx, 1
0x1800290de  jz      short loc_1800290ED
0x1800290e0  test    byte ptr [rcx+1Ch], 8
0x1800290e4  jz      short loc_18002915D
0x1800290e6  mov     edx, 0A2h
0x1800290eb  jmp     short loc_18002914D
0x1800290ed  movzx   edx, word ptr [rbx+2]
0x1800290f1  cmp     dx, [rbx]
0x1800290f4  jb      short loc_180029121
0x1800290f6  or      dx, [rbx]
0x1800290f9  bt      dx, r13w
0x1800290fe  jb      short loc_180029121
0x180029100  cmp     [rbx], r13w
0x180029104  jz      short loc_18002910C
0x180029106  cmp     [rbx+8], r13
0x18002910a  jz      short loc_180029121
0x18002910c  mov     [rsp+68h+var_30], r13
0x180029111  mov     r13, rbx
0x180029114  xor     edx, edx
0x180029116  mov     rcx, rbx
0x180029119  call    cs:__imp_LsapRemoveTrailingDot
0x18002911f  jmp     short loc_18002916C
0x180029121  test    byte ptr [rcx+1Ch], 8
0x180029125  jz      short loc_18002915D
0x180029127  mov     edx, 0A1h
0x18002912c  jmp     short loc_18002914D
0x18002912e  mov     rcx, rbx; Sid
0x180029131  call    cs:__imp_RtlValidSid
0x180029137  test    al, al
0x180029139  jnz     short loc_180029167
0x18002913b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029142  test    byte ptr [rcx+1Ch], 8
0x180029146  jz      short loc_18002915D
0x180029148  mov     edx, 0A0h
0x18002914d  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180029154  mov     rcx, [rcx+10h]
0x180029158  call    WPP_SF_
0x18002915d  mov     eax, 0C000000Dh
0x180029162  jmp     loc_180029337
0x180029167  mov     [rsp+68h+var_30], rbx
0x18002916c  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180029172  xor     r8d, r8d
0x180029175  movzx   eax, [rsp+68h+arg_18]
0x18002917d  test    al, al
0x18002917f  setz    r8b; int
0x180029183  mov     edx, eax; int
0x180029185  mov     rcx, [rsp+68h+arg_10]; this
0x18002918d  call    ?RebuildCachesIfNecessary@FTCache@@AEAAJHH@Z; FTCache::RebuildCachesIfNecessary(int,int)
0x180029192  mov     ebx, eax
0x180029194  test    eax, eax
0x180029196  jns     short loc_1800291C6
0x180029198  mov     rcx, cs:WPP_GLOBAL_Control
0x18002919f  test    byte ptr [rcx+1Ch], 8
0x1800291a3  jz      loc_18002930A
0x1800291a9  mov     edx, 0A3h
0x1800291ae  mov     r9d, eax
0x1800291b1  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800291b8  mov     rcx, [rcx+10h]
0x1800291bc  call    WPP_SF_d
0x1800291c1  jmp     loc_18002930A
0x1800291c6  test    edi, edi
0x1800291c8  jz      loc_180029290
0x1800291ce  sub     edi, 1
0x1800291d1  jz      short loc_180029249
0x1800291d3  sub     edi, 1
0x1800291d6  jz      short loc_18002922A
0x1800291d8  sub     edi, 1
0x1800291db  jz      short loc_180029208
0x1800291dd  cmp     edi, 1
0x1800291e0  jnz     loc_1800292B5
0x1800291e6  mov     [rsp+68h+var_48], r14; void **
0x1800291eb  mov     r9, r12; struct _UNICODE_STRING *
0x1800291ee  lea     r8, [rsp+68h+arg_0]; unsigned __int8 *
0x1800291f3  mov     rdx, r13; struct _UNICODE_STRING *
0x1800291f6  mov     rcx, [rsp+68h+arg_10]; this
0x1800291fe  call    ?MatchNamespace@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z; FTCache::MatchNamespace(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)
0x180029203  jmp     loc_1800292AF
0x180029208  mov     [rsp+68h+var_48], r14; void **
0x18002920d  mov     r9, r12; struct _UNICODE_STRING *
0x180029210  lea     r8, [rsp+68h+arg_0]; unsigned __int8 *
0x180029215  mov     rdx, r13; struct _UNICODE_STRING *
0x180029218  mov     rcx, [rsp+68h+arg_10]; this
0x180029220  call    ?MatchSpn@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z; FTCache::MatchSpn(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)
0x180029225  jmp     loc_1800292AF
0x18002922a  mov     [rsp+68h+var_48], r14; void **
0x18002922f  mov     r9, r12; struct _UNICODE_STRING *
0x180029232  lea     r8, [rsp+68h+arg_0]; unsigned __int8 *
0x180029237  mov     rdx, r13; struct _UNICODE_STRING *
0x18002923a  mov     rcx, [rsp+68h+arg_10]; this
0x180029242  call    ?MatchUpn@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z; FTCache::MatchUpn(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)
0x180029247  jmp     short loc_1800292AF
0x180029249  mov     [rsp+68h+var_48], r14; void **
0x18002924e  mov     r9, r12; struct _UNICODE_STRING *
0x180029251  lea     r8, [rsp+68h+arg_0]; unsigned __int8 *
0x180029256  mov     rdx, r13; struct _UNICODE_STRING *
0x180029259  mov     rdi, [rsp+68h+arg_10]
0x180029261  mov     rcx, rdi; this
0x180029264  call    ?MatchDnsName@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z; FTCache::MatchDnsName(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)
0x180029269  mov     ebx, eax
0x18002926b  mov     [rsp+68h+var_38], eax
0x18002926f  cmp     eax, 0C0000272h
0x180029274  jnz     short loc_1800292B5
0x180029276  mov     [rsp+68h+var_48], r14; void **
0x18002927b  mov     r9, r12; struct _UNICODE_STRING *
0x18002927e  lea     r8, [rsp+68h+arg_0]; unsigned __int8 *
0x180029283  mov     rdx, r13; struct _UNICODE_STRING *
0x180029286  mov     rcx, rdi; this
0x180029289  call    ?MatchNetbiosName@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z; FTCache::MatchNetbiosName(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)
0x18002928e  jmp     short loc_1800292AF
0x180029290  mov     [rsp+68h+var_48], r14; void **
0x180029295  mov     r9, r12; struct _UNICODE_STRING *
0x180029298  lea     r8, [rsp+68h+arg_0]; unsigned __int8 *
0x18002929d  mov     rdx, [rsp+68h+var_30]; struct _SID *
0x1800292a2  mov     rcx, [rsp+68h+arg_10]; this
0x1800292aa  call    ?MatchSid@FTCache@@AEAAJPEAU_SID@@PEAEPEAU_UNICODE_STRING@@PEAPEAX@Z; FTCache::MatchSid(_SID *,uchar *,_UNICODE_STRING *,void * *)
0x1800292af  mov     ebx, eax
0x1800292b1  mov     [rsp+68h+var_38], eax
0x1800292b5  test    ebx, ebx
0x1800292b7  js      short loc_18002930A
0x1800292b9  xor     ecx, ecx
0x1800292bb  cmp     byte ptr [rsp+68h+arg_0], cl
0x1800292bf  setz    cl
0x1800292c2  xor     eax, eax
0x1800292c4  cmp     [rsp+68h+arg_18], al
0x1800292cb  setz    al
0x1800292ce  cmp     ecx, eax
0x1800292d0  jz      short loc_18002930A
0x1800292d2  mov     ebx, 0C0000272h
0x1800292d7  test    r12, r12
0x1800292da  jz      short loc_1800292ED
0x1800292dc  mov     rcx, r12
0x1800292df  call    cs:__imp_LsaIFree_LSAPR_UNICODE_STRING_BUFFER
0x1800292e5  xorps   xmm0, xmm0
0x1800292e8  movups  xmmword ptr [r12], xmm0
0x1800292ed  test    r14, r14
0x1800292f0  jz      short loc_18002930A
0x1800292f2  mov     rcx, [r14]; hMem
0x1800292f5  call    cs:__imp_LocalFree
0x1800292fb  mov     qword ptr [r14], 0
0x180029302  jmp     short loc_18002930A
0x180029304  mov     ebx, eax
0x180029306  mov     [rsp+68h+var_38], eax
0x18002930a  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180029310  mov     rcx, cs:WPP_GLOBAL_Control
0x180029317  test    byte ptr [rcx+1Ch], 8
0x18002931b  jz      short loc_180029335
0x18002931d  mov     edx, 0A4h
0x180029322  mov     r9d, ebx
0x180029325  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002932c  mov     rcx, [rcx+10h]
0x180029330  call    WPP_SF_d
0x180029335  mov     eax, ebx
0x180029337  add     rsp, 40h
0x18002933b  pop     r14
0x18002933d  pop     r13
0x18002933f  pop     r12
0x180029341  pop     rdi
0x180029342  pop     rbx
0x180029343  retn
```
