# NlpAddCacheEntry

- ea: `0x18004339c`
- end: `0x180043905`
- name: `NlpAddCacheEntry`
- size: `1385`
- prototype: `__int64 __usercall@<rax>(struct _NETLOGON_INTERACTIVE_INFO *@<rcx>, struct _NETLOGON_VALIDATION_SAM_INFO4 *@<rdx>, int, __int64, int, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001a470`
- `0x18003d430`

## callees

- `0x180011370`
- `0x1800205b4`
- `0x18002f014`
- `0x18002fb50`
- `0x180030844`
- `0x180035ea8`
- `0x180040c58`
- `0x1800415d8`
- `0x180041d88`
- `0x180041f64`
- `0x180042040`
- `0x180042424`
- `0x1800427d0`
- `0x180042dac`
- `0x1800432c8`
- `0x18004339c`
- `0x180045eac`
- `0x18006d010`

## import_xrefs

- `NtlmShared!MsvpMakeSecretPasswordNT5` at `0x180043535`
- `NtlmShared!MsvpMakeSecretPasswordNT5` at `0x180043535`
- `ntdll!RtlEqualSid` at `0x18004344a`
- `ntdll!RtlEqualSid` at `0x180043467`
- `ntdll!RtlEqualSid` at `0x18004344a`
- `ntdll!RtlEqualSid` at `0x180043467`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800437a1`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800437a1`
- `ntdll!DbgPrint` at `0x18004354e`
- `ntdll!DbgPrint` at `0x180043863`
- `ntdll!DbgPrint` at `0x18004354e`
- `ntdll!DbgPrint` at `0x180043863`
- `ntdll!RtlReleaseResource` at `0x180043494`
- `ntdll!RtlReleaseResource` at `0x180043875`
- `ntdll!RtlReleaseResource` at `0x180043494`
- `ntdll!RtlReleaseResource` at `0x180043875`
- `ntdll!RtlAcquireResourceShared` at `0x18004347f`
- `ntdll!RtlAcquireResourceShared` at `0x18004347f`

## string_xrefs

- `0x180043545`: `Failed to hash plaintext ntowf into cache verifier: 0x%08X\n`
- `0x1800435f8`: `Failed to hash encrypted secrets wrapper into cache verifier: 0x%08X\n`
- `0x18004385c`: `Bad supplemental credential - failing to add cache entry`

## pseudocode

```c
__int64 __fastcall NlpAddCacheEntry(
        struct _NETLOGON_INTERACTIVE_INFO *a1,
        PSID *a2,
        __int64 a3,
        __m128i *a4,
        unsigned int a5,
        _DWORD *a6,
        unsigned int a7,
        LONG a8)
{
  struct _LOGON_CACHE_ENTRY *v11; // rdi
  int AccountNamesInCacheEntry; // ebx
  LONG v14; // r8d
  __int64 v15; // r8
  int SecretPasswordNT5; // eax
  int v17; // eax
  __int64 v18; // r9
  int v19; // eax
  unsigned int v20; // r8d
  int v21; // eax
  __int64 v22; // rsi
  int v23; // r8d
  const char *v24; // rax
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  struct _LOGON_CACHE_ENTRY *v26; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28[3]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING v30; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v31; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v32[352]; // [rsp+90h] [rbp-70h] BYREF

  v29 = a3;
  v26 = 0;
  LODWORD(Size) = 0;
  v11 = 0;
  memset(v28, 0, sizeof(v28));
  v27 = 0;
  v30 = 0;
  v31 = 0;
  if ( !NlpCacheInitialized )
    return 0;
  if ( (a8 & 1) == 0 )
  {
    if ( !NlpSamInitialized )
    {
      AccountNamesInCacheEntry = NlSamInitialize();
      if ( AccountNamesInCacheEntry < 0 )
        goto LABEL_59;
    }
    if ( RtlEqualSid(NlpSamDomainId, a2[28]) || NlpSamLocalDomainId && RtlEqualSid(NlpSamLocalDomainId, a2[28]) )
      return 0;
  }
  RtlAcquireResourceShared(&NlpLogonCacheCritSec, 1u);
  if ( !HIDWORD(NlpCacheControl) )
  {
    RtlReleaseResource(&NlpLogonCacheCritSec);
    return 0;
  }
  v14 = a8 | 0x80;
  if ( (dword_180087A84 & 0x20) == 0 )
    v14 = a8;
  AccountNamesInCacheEntry = NlpBuildCacheEntry(
                               &a1->Identity.LogonDomainName,
                               (__int64)a2,
                               v14,
                               a5,
                               a4,
                               (_LARGE_INTEGER **)&v26,
                               (unsigned int *)&Size);
  if ( AccountNamesInCacheEntry >= 0 )
  {
    if ( a6 )
    {
      memset_0(v32, 0, sizeof(v32));
      if ( a7 < 0xC || *a6 != -65535 )
      {
        DbgPrint("Bad supplemental credential - failing to add cache entry");
        AccountNamesInCacheEntry = -1073741811;
        goto LABEL_58;
      }
      v17 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *, _DWORD *, _BYTE *))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj
                                                                                  + 136LL))(
              LocalhostNtLmCredIsoObj::IsoObj,
              a6,
              v32);
      AccountNamesInCacheEntry = v17;
      if ( v17 < 0 )
      {
        DbgPrint("Failed to convert supplemental credential to secrets wrapper: 0x%08X\n", (unsigned int)v17);
        goto LABEL_58;
      }
      v18 = NlpIterationCount;
      if ( (*((_BYTE *)v26 + 140) & 8) != 0 )
        v18 = 1;
      v19 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *, char *, _BYTE *, __int64, char *))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj
                                                                                                 + 80LL))(
              LocalhostNtLmCredIsoObj::IsoObj,
              (char *)a2 + 48,
              v32,
              v18,
              (char *)v26 + 96);
      AccountNamesInCacheEntry = v19;
      if ( v19 < 0 )
      {
        DbgPrint("Failed to hash encrypted secrets wrapper into cache verifier: 0x%08X\n", (unsigned int)v19);
        goto LABEL_58;
      }
    }
    else
    {
      v15 = NlpIterationCount;
      if ( (*((_BYTE *)v26 + 140) & 8) != 0 )
        v15 = 1;
      SecretPasswordNT5 = MsvpMakeSecretPasswordNT5(a2 + 6, &a1->NtOwfPassword, v15, (char *)v26 + 96);
      AccountNamesInCacheEntry = SecretPasswordNT5;
      if ( SecretPasswordNT5 < 0 )
      {
        DbgPrint("Failed to hash plaintext ntowf into cache verifier: 0x%08X\n", (unsigned int)SecretPasswordNT5);
        goto LABEL_58;
      }
    }
    if ( *((_DWORD *)v26 + 10) < 0x10004u || (v20 = 0x40000000, (*((_BYTE *)v26 + 140) & 8) == 0) )
      v20 = 0;
    AccountNamesInCacheEntry = NlpReadCacheEntry(
                                 &a1->Identity.LogonDomainName,
                                 &a1->Identity.UserName,
                                 v20,
                                 &v27,
                                 (struct _LOGON_CACHE_ENTRY **)&v28[1],
                                 v28);
    if ( AccountNamesInCacheEntry >= 0 )
    {
      v11 = *(struct _LOGON_CACHE_ENTRY **)&v28[1];
    }
    else
    {
      *(_QWORD *)&v28[1] = 0;
      if ( !a1->Identity.LogonDomainName.Length
        && (*((_DWORD *)v26 + 10) < 0x10004u || (*((_BYTE *)v26 + 140) & 8) == 0) )
      {
        AccountNamesInCacheEntry = NlpGetAccountNamesInCacheEntry(v26, &v30, &v31, 0, 0);
        if ( AccountNamesInCacheEntry < 0 )
          goto LABEL_58;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_905305d962583d6f838b30057de84013_Traceguids);
        }
        v21 = NlpReadCacheEntry(&v31, &v30, 0, &v27, (struct _LOGON_CACHE_ENTRY **)&v28[1], v28);
        v11 = *(struct _LOGON_CACHE_ENTRY **)&v28[1];
        AccountNamesInCacheEntry = v21;
        if ( v21 < 0 )
          v11 = 0;
        if ( v11 )
        {
LABEL_44:
          if ( NlpCompareCacheEntry(v26, Size, v11, v28[0]) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
            {
              WPP_SF_ZZ(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                (unsigned int)WPP_905305d962583d6f838b30057de84013_Traceguids,
                (_DWORD)a1,
                (__int64)&a1->Identity.UserName);
            }
            goto LABEL_58;
          }
LABEL_48:
          AccountNamesInCacheEntry = NlpEncryptCacheEntry(v26, Size);
          if ( AccountNamesInCacheEntry >= 0 )
          {
            RtlConvertSharedToExclusive(&NlpLogonCacheCritSec);
            v22 = v27;
            AccountNamesInCacheEntry = NlpWriteCacheEntry(v27, v26, Size);
            if ( AccountNamesInCacheEntry >= 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
              {
                v24 = "true";
                if ( !v11 )
                  v24 = "false";
                WPP_SF_dZZs(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  (unsigned int)"false",
                  v23,
                  v22,
                  (__int64)a1,
                  (__int64)&a1->Identity.UserName,
                  (__int64)v24);
              }
              *((_QWORD *)NlpCteTable + 4 * v22 + 2) = *((_QWORD *)v26 + 4);
              NlpAddEntryToActiveList(v22);
              NlpDisableExpiredCacheEntries(v22, a1, (struct _NETLOGON_VALIDATION_SAM_INFO4 *)a2);
              if ( v29 )
                NlpMarkUserSidAsUpdated(a1, a2, v29);
            }
          }
          goto LABEL_58;
        }
      }
      NlpGetFreeEntryIndex(&v27);
    }
    if ( !v11 )
      goto LABEL_48;
    goto LABEL_44;
  }
LABEL_58:
  RtlReleaseResource(&NlpLogonCacheCritSec);
LABEL_59:
  if ( v30.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( v31.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( v26 )
  {
    memset_0(v26, 0, (unsigned int)Size);
    ((void (__fastcall *)(struct _LOGON_CACHE_ENTRY *))qword_180088398)(v26);
  }
  if ( v11 )
  {
    memset_0(v11, 0, v28[0]);
    ((void (__fastcall *)(struct _LOGON_CACHE_ENTRY *))qword_180088398)(v11);
  }
  return (unsigned int)AccountNamesInCacheEntry;
}

```

## disassembly

```asm
0x18004339c  push    rbp
0x18004339e  push    rbx
0x18004339f  push    rsi
0x1800433a0  push    rdi
0x1800433a1  push    r12
0x1800433a3  push    r13
0x1800433a5  push    r14
0x1800433a7  push    r15
0x1800433a9  lea     rbp, [rsp-108h]
0x1800433b1  sub     rsp, 208h
0x1800433b8  mov     rax, cs:__security_cookie
0x1800433bf  xor     rax, rsp
0x1800433c2  mov     [rbp+140h+var_50], rax
0x1800433c9  mov     rsi, [rbp+140h+arg_28]
0x1800433d0  xor     ebx, ebx
0x1800433d2  cmp     cs:NlpCacheInitialized, bl
0x1800433d8  xorps   xmm0, xmm0
0x1800433db  xorps   xmm1, xmm1
0x1800433de  mov     [rsp+240h+var_1E0], r8
0x1800433e3  mov     r13, r9
0x1800433e6  mov     [rsp+240h+var_1F8], rbx
0x1800433eb  mov     r15, rdx
0x1800433ee  mov     qword ptr [rsp+240h+var_1EC+4], rbx
0x1800433f3  mov     r14, rcx
0x1800433f6  mov     dword ptr [rsp+240h+Size], ebx
0x1800433fa  mov     edi, ebx
0x1800433fc  mov     dword ptr [rsp+240h+var_1EC], ebx
0x180043400  mov     [rsp+240h+var_1F0], ebx
0x180043404  movups  xmmword ptr [rsp+240h+var_1D8.Length], xmm0
0x180043409  movups  xmmword ptr [rsp+240h+var_1C8.Length], xmm1
0x18004340e  jz      loc_18004349A
0x180043414  mov     r12d, [rbp+140h+arg_38]
0x18004341b  lea     eax, [rbx+1]
0x18004341e  test    al, r12b
0x180043421  jnz     short loc_180043476
0x180043423  cmp     cs:NlpSamInitialized, bl
0x180043429  jnz     short loc_18004343C
0x18004342b  call    NlSamInitialize
0x180043430  mov     ebx, eax
0x180043432  test    eax, eax
0x180043434  js      loc_18004387B
0x18004343a  xor     ebx, ebx
0x18004343c  mov     rdx, [r15+0E0h]; Sid2
0x180043443  mov     rcx, cs:NlpSamDomainId; Sid1
0x18004344a  call    cs:__imp_RtlEqualSid
0x180043450  test    al, al
0x180043452  jnz     short loc_18004349A
0x180043454  mov     rcx, cs:NlpSamLocalDomainId; Sid1
0x18004345b  test    rcx, rcx
0x18004345e  jz      short loc_180043471
0x180043460  mov     rdx, [r15+0E0h]; Sid2
0x180043467  call    cs:__imp_RtlEqualSid
0x18004346d  test    al, al
0x18004346f  jnz     short loc_18004349A
0x180043471  mov     eax, 1
0x180043476  mov     dl, al; Wait
0x180043478  lea     rcx, NlpLogonCacheCritSec; Resource
0x18004347f  call    cs:__imp_RtlAcquireResourceShared
0x180043485  cmp     dword ptr cs:NlpCacheControl+4, ebx
0x18004348b  jnz     short loc_1800434BF
0x18004348d  lea     rcx, NlpLogonCacheCritSec; Resource
0x180043494  call    cs:__imp_RtlReleaseResource
0x18004349a  xor     eax, eax
0x18004349c  mov     rcx, [rbp+140h+var_50]
0x1800434a3  xor     rcx, rsp; StackCookie
0x1800434a6  call    __security_check_cookie
0x1800434ab  add     rsp, 208h
0x1800434b2  pop     r15
0x1800434b4  pop     r14
0x1800434b6  pop     r13
0x1800434b8  pop     r12
0x1800434ba  pop     rdi
0x1800434bb  pop     rsi
0x1800434bc  pop     rbx
0x1800434bd  pop     rbp
0x1800434be  retn
0x1800434bf  mov     r9d, [rbp+140h+arg_20]
0x1800434c6  lea     rax, [rsp+240h+Size]
0x1800434cb  mov     [rsp+240h+var_210], rax; __int64
0x1800434d0  mov     r8d, r12d
0x1800434d3  bts     r8d, 7
0x1800434d8  lea     rax, [rsp+240h+var_1F8]
0x1800434dd  test    byte ptr cs:dword_180087A84, 20h
0x1800434e4  mov     rdx, r15
0x1800434e7  mov     [rsp+240h+var_218], rax; __int64
0x1800434ec  mov     rcx, r14; struct _UNICODE_STRING *
0x1800434ef  cmovz   r8d, r12d
0x1800434f3  mov     [rsp+240h+var_220], r13; void *
0x1800434f8  call    NlpBuildCacheEntry
0x1800434fd  xor     r13d, r13d
0x180043500  mov     ebx, eax
0x180043502  test    eax, eax
0x180043504  js      loc_18004386E
0x18004350a  test    rsi, rsi
0x18004350d  jnz     short loc_180043559
0x18004350f  mov     rax, [rsp+240h+var_1F8]
0x180043514  lea     ecx, [rsi+1]
0x180043517  mov     r8d, cs:?NlpIterationCount@@3KA; ulong NlpIterationCount
0x18004351e  lea     rdx, [r14+50h]
0x180043522  test    byte ptr [rax+8Ch], 8
0x180043529  lea     r9, [rax+60h]
0x18004352d  cmovnz  r8d, ecx
0x180043531  lea     rcx, [r15+30h]
0x180043535  call    cs:__imp_MsvpMakeSecretPasswordNT5
0x18004353b  mov     ebx, eax
0x18004353d  test    eax, eax
0x18004353f  jns     loc_180043604
0x180043545  lea     rcx, aFailedToHashPl; "Failed to hash plaintext ntowf into cac"...
0x18004354c  mov     edx, eax
0x18004354e  call    cs:__imp_DbgPrint
0x180043554  jmp     loc_18004386E
0x180043559  xor     edx, edx; Val
0x18004355b  lea     rcx, [rbp+140h+var_1B0]; void *
0x18004355f  mov     r8d, 160h; Size
0x180043565  call    memset_0
0x18004356a  cmp     [rbp+140h+arg_30], 0Ch
0x180043571  jb      loc_18004385C
0x180043577  cmp     dword ptr [rsi], 0FFFF0001h
0x18004357d  jnz     loc_18004385C
0x180043583  mov     rcx, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x18004358a  lea     r8, [rbp+140h+var_1B0]
0x18004358e  mov     rdx, rsi
0x180043591  mov     rax, [rcx]
0x180043594  mov     rax, [rax+88h]
0x18004359b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435a0  mov     ebx, eax
0x1800435a2  test    eax, eax
0x1800435a4  jns     short loc_1800435AF
0x1800435a6  lea     rcx, aFailedToConver; "Failed to convert supplemental credenti"...
0x1800435ad  jmp     short loc_18004354C
0x1800435af  mov     rcx, [rsp+240h+var_1F8]
0x1800435b4  lea     rdx, [r15+30h]
0x1800435b8  mov     r10, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x1800435bf  mov     r9d, cs:?NlpIterationCount@@3KA; ulong NlpIterationCount
0x1800435c6  test    byte ptr [rcx+8Ch], 8
0x1800435cd  lea     r8, [rcx+60h]
0x1800435d1  mov     rax, [r10]
0x1800435d4  mov     ecx, 1
0x1800435d9  cmovnz  r9d, ecx
0x1800435dd  mov     [rsp+240h+var_220], r8
0x1800435e2  lea     r8, [rbp+140h+var_1B0]
0x1800435e6  mov     rcx, r10
0x1800435e9  mov     rax, [rax+50h]
0x1800435ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435f2  mov     ebx, eax
0x1800435f4  test    eax, eax
0x1800435f6  jns     short loc_180043604
0x1800435f8  lea     rcx, aFailedToHashEn; "Failed to hash encrypted secrets wrappe"...
0x1800435ff  jmp     loc_18004354C
0x180043604  mov     rax, [rsp+240h+var_1F8]
0x180043609  mov     esi, 10004h
0x18004360e  cmp     [rax+28h], esi
0x180043611  jb      short loc_180043622
0x180043613  test    byte ptr [rax+8Ch], 8
0x18004361a  mov     r8d, 40000000h
0x180043620  jnz     short loc_180043625
0x180043622  mov     r8d, r13d; unsigned int
0x180043625  lea     rax, [rsp+240h+var_1EC]
0x18004362a  mov     rcx, r14; struct _UNICODE_STRING *
0x18004362d  mov     [rsp+240h+var_218], rax; unsigned int *
0x180043632  lea     r12, [r14+20h]
0x180043636  lea     rax, [rsp+240h+var_1EC+4]
0x18004363b  mov     rdx, r12; struct _UNICODE_STRING *
0x18004363e  lea     r9, [rsp+240h+var_1F0]; unsigned int *
0x180043643  mov     [rsp+240h+var_220], rax; struct _LOGON_CACHE_ENTRY **
0x180043648  call    ?NlpReadCacheEntry@@YAJPEAU_UNICODE_STRING@@0KPEAKPEAPEAU_LOGON_CACHE_ENTRY@@1@Z; NlpReadCacheEntry(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,_LOGON_CACHE_ENTRY * *,ulong *)
0x18004364d  mov     ebx, eax
0x18004364f  test    eax, eax
0x180043651  jns     loc_180043718
0x180043657  mov     qword ptr [rsp+240h+var_1EC+4], r13
0x18004365c  cmp     [r14], r13w
0x180043660  jnz     loc_18004370C
0x180043666  mov     rcx, [rsp+240h+var_1F8]; struct _LOGON_CACHE_ENTRY *
0x18004366b  cmp     [rcx+28h], esi
0x18004366e  jb      short loc_18004367D
0x180043670  test    byte ptr [rcx+8Ch], 8
0x180043677  jnz     loc_18004370C
0x18004367d  xor     r9d, r9d; struct _UNICODE_STRING *
0x180043680  mov     [rsp+240h+var_220], r13; struct _UNICODE_STRING *
0x180043685  lea     r8, [rsp+240h+var_1C8]; struct _UNICODE_STRING *
0x18004368a  lea     rdx, [rsp+240h+var_1D8]; struct _UNICODE_STRING *
0x18004368f  call    ?NlpGetAccountNamesInCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@PEAU_UNICODE_STRING@@111@Z; NlpGetAccountNamesInCacheEntry(_LOGON_CACHE_ENTRY *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180043694  mov     ebx, eax
0x180043696  test    eax, eax
0x180043698  js      loc_18004386E
0x18004369e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800436a5  lea     rsi, WPP_GLOBAL_Control
0x1800436ac  cmp     rcx, rsi
0x1800436af  jz      short loc_1800436CF
0x1800436b1  test    dword ptr [rcx+1Ch], 4000h
0x1800436b8  jz      short loc_1800436CF
0x1800436ba  mov     rcx, [rcx+10h]
0x1800436be  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x1800436c5  mov     edx, 17h
0x1800436ca  call    WPP_SF_
0x1800436cf  lea     rax, [rsp+240h+var_1EC]
0x1800436d4  xor     r8d, r8d; unsigned int
0x1800436d7  mov     [rsp+240h+var_218], rax; unsigned int *
0x1800436dc  lea     r9, [rsp+240h+var_1F0]; unsigned int *
0x1800436e1  lea     rax, [rsp+240h+var_1EC+4]
0x1800436e6  lea     rdx, [rsp+240h+var_1D8]; struct _UNICODE_STRING *
0x1800436eb  mov     [rsp+240h+var_220], rax; struct _LOGON_CACHE_ENTRY **
0x1800436f0  lea     rcx, [rsp+240h+var_1C8]; struct _UNICODE_STRING *
0x1800436f5  call    ?NlpReadCacheEntry@@YAJPEAU_UNICODE_STRING@@0KPEAKPEAPEAU_LOGON_CACHE_ENTRY@@1@Z; NlpReadCacheEntry(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,_LOGON_CACHE_ENTRY * *,ulong *)
0x1800436fa  mov     rdi, qword ptr [rsp+240h+var_1EC+4]
0x1800436ff  test    eax, eax
0x180043701  mov     ebx, eax
0x180043703  cmovs   rdi, r13
0x180043707  test    rdi, rdi
0x18004370a  jnz     short loc_180043729
0x18004370c  lea     rcx, [rsp+240h+var_1F0]; unsigned int *
0x180043711  call    ?NlpGetFreeEntryIndex@@YAXPEAK@Z; NlpGetFreeEntryIndex(ulong *)
0x180043716  jmp     short loc_18004371D
0x180043718  mov     rdi, qword ptr [rsp+240h+var_1EC+4]
0x18004371d  test    rdi, rdi
0x180043720  jz      short loc_180043782
0x180043722  lea     rsi, WPP_GLOBAL_Control
0x180043729  mov     r9d, dword ptr [rsp+240h+var_1EC]; unsigned int
0x18004372e  mov     r8, rdi; struct _LOGON_CACHE_ENTRY *
0x180043731  mov     edx, dword ptr [rsp+240h+Size]; unsigned int
0x180043735  mov     rcx, [rsp+240h+var_1F8]; struct _LOGON_CACHE_ENTRY *
0x18004373a  call    ?NlpCompareCacheEntry@@YAEPEAU_LOGON_CACHE_ENTRY@@K0K@Z; NlpCompareCacheEntry(_LOGON_CACHE_ENTRY *,ulong,_LOGON_CACHE_ENTRY *,ulong)
0x18004373f  test    al, al
0x180043741  jz      short loc_180043782
0x180043743  mov     rcx, cs:WPP_GLOBAL_Control
0x18004374a  cmp     rcx, rsi
0x18004374d  jz      loc_18004386E
0x180043753  test    dword ptr [rcx+1Ch], 4000h
0x18004375a  jz      loc_18004386E
0x180043760  mov     rcx, [rcx+10h]
0x180043764  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x18004376b  mov     edx, 18h
0x180043770  mov     [rsp+240h+var_220], r12
0x180043775  mov     r9, r14
0x180043778  call    WPP_SF_ZZ
0x18004377d  jmp     loc_18004386E
0x180043782  mov     edx, dword ptr [rsp+240h+Size]; unsigned int
0x180043786  mov     rcx, [rsp+240h+var_1F8]; struct _LOGON_CACHE_ENTRY *
0x18004378b  call    ?NlpEncryptCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@K@Z; NlpEncryptCacheEntry(_LOGON_CACHE_ENTRY *,ulong)
0x180043790  mov     ebx, eax
0x180043792  test    eax, eax
0x180043794  js      loc_18004386E
0x18004379a  lea     rcx, NlpLogonCacheCritSec; Resource
0x1800437a1  call    cs:__imp_RtlConvertSharedToExclusive
0x1800437a7  mov     esi, [rsp+240h+var_1F0]
0x1800437ab  mov     r8d, dword ptr [rsp+240h+Size]; unsigned int
0x1800437b0  mov     ecx, esi; unsigned int
0x1800437b2  mov     rdx, [rsp+240h+var_1F8]; struct _LOGON_CACHE_ENTRY *
0x1800437b7  call    ?NlpWriteCacheEntry@@YAJKPEAU_LOGON_CACHE_ENTRY@@K@Z; NlpWriteCacheEntry(ulong,_LOGON_CACHE_ENTRY *,ulong)
0x1800437bc  mov     ebx, eax
0x1800437be  test    eax, eax
0x1800437c0  js      loc_18004386E
0x1800437c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800437cd  lea     rax, WPP_GLOBAL_Control
0x1800437d4  cmp     rcx, rax
0x1800437d7  jz      short loc_180043812
0x1800437d9  test    dword ptr [rcx+1Ch], 4000h
0x1800437e0  jz      short loc_180043812
0x1800437e2  mov     rcx, [rcx+10h]
0x1800437e6  lea     rdx, aFalse; "false"
0x1800437ed  test    rdi, rdi
0x1800437f0  lea     rax, aTrue_0; "true"
0x1800437f7  mov     r9d, esi
0x1800437fa  cmovz   rax, rdx
0x1800437fe  mov     [rsp+240h+var_210], rax
0x180043803  mov     [rsp+240h+var_218], r12
0x180043808  mov     [rsp+240h+var_220], r14
0x18004380d  call    WPP_SF_dZZs
0x180043812  mov     rax, [rsp+240h+var_1F8]
0x180043817  mov     r9, rsi
0x18004381a  shl     r9, 5
0x18004381e  mov     rcx, [rax+20h]
0x180043822  mov     rax, cs:?NlpCteTable@@3PEAU_NLP_CTE@@EA; _NLP_CTE * NlpCteTable
0x180043829  mov     [r9+rax+10h], rcx
0x18004382e  mov     ecx, esi; unsigned int
0x180043830  call    ?NlpAddEntryToActiveList@@YAXK@Z; NlpAddEntryToActiveList(ulong)
0x180043835  mov     r8, r15; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x180043838  mov     rdx, r14; struct _NETLOGON_INTERACTIVE_INFO *
0x18004383b  mov     ecx, esi; unsigned int
0x18004383d  call    ?NlpDisableExpiredCacheEntries@@YAXKPEAU_NETLOGON_INTERACTIVE_INFO@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z; NlpDisableExpiredCacheEntries(ulong,_NETLOGON_INTERACTIVE_INFO *,_NETLOGON_VALIDATION_SAM_INFO4 *)
0x180043842  mov     rax, [rsp+240h+var_1E0]
0x180043847  test    rax, rax
0x18004384a  jz      short loc_18004386E
0x18004384c  mov     r8, rax
0x18004384f  mov     rdx, r15
0x180043852  mov     rcx, r14
0x180043855  call    NlpMarkUserSidAsUpdated
0x18004385a  jmp     short loc_18004386E
0x18004385c  lea     rcx, aBadSupplementa; "Bad supplemental credential - failing t"...
0x180043863  call    cs:__imp_DbgPrint
0x180043869  mov     ebx, 0C000000Dh
0x18004386e  lea     rcx, NlpLogonCacheCritSec; Resource
0x180043875  call    cs:__imp_RtlReleaseResource
0x18004387b  mov     rcx, [rsp+240h+var_1D8.Buffer]
0x180043880  test    rcx, rcx
0x180043883  jz      short loc_180043898
0x180043885  mov     rax, cs:LsaFunctions
0x18004388c  mov     rax, [rax+188h]
0x180043893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043898  mov     rcx, [rbp+140h+var_1C8.Buffer]
  ... truncated ...
```
