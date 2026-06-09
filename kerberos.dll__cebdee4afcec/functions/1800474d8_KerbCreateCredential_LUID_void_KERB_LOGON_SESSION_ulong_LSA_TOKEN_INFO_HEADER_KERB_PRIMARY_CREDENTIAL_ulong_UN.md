# KerbCreateCredential(_LUID *,void *,_KERB_LOGON_SESSION *,ulong,_LSA_TOKEN_INFO_HEADER * *,_KERB_PRIMARY_CREDENTIAL * *,ulong,_UNICODE_STRING *,_KERB_CREDENTIAL * *,_LARGE_INTEGER *)

- ea: `0x1800474d8`
- end: `0x180047b5a`
- name: `?KerbCreateCredential@@YAJPEAU_LUID@@PEAXPEAU_KERB_LOGON_SESSION@@KPEAPEAU_LSA_TOKEN_INFO_HEADER@@PEAPEAU_KERB_PRIMARY_CREDENTIAL@@KPEAU_UNICODE_STRING@@PEAPEAU_KERB_CREDENTIAL@@PEAT_LARGE_INTEGER@@@Z`
- size: `1666`
- prototype: `int(struct _LUID *, void *, struct _KERB_LOGON_SESSION *, unsigned int, struct _LSA_TOKEN_INFO_HEADER **, struct _KERB_PRIMARY_CREDENTIAL **, unsigned int, struct _UNICODE_STRING *, struct _KERB_CREDENTIAL **, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005d250`

## callees

- `0x1800068d0`
- `0x18000b300`
- `0x18000d9e4`
- `0x18000e720`
- `0x18002c31c`
- `0x180036ed4`
- `0x180037e30`
- `0x1800473c0`
- `0x1800474d8`
- `0x180047b60`
- `0x180065c48`
- `0x18006ba6c`
- `0x18006cb94`
- `0x180070680`
- `0x1800783b0`
- `0x18008a114`
- `0x18008b2f4`
- `0x18008b70c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800475d2`
- `ntdll!NtQueryInformationToken` at `0x1800475d2`
- `ntdll!NtDuplicateObject` at `0x180047a46`
- `ntdll!NtDuplicateObject` at `0x180047a46`
- `ntdll!RtlEnterCriticalSection` at `0x180047606`
- `ntdll!RtlEnterCriticalSection` at `0x18004769c`
- `ntdll!RtlEnterCriticalSection` at `0x1800478dc`
- `ntdll!RtlEnterCriticalSection` at `0x180047a82`
- `ntdll!RtlEnterCriticalSection` at `0x180047606`
- `ntdll!RtlEnterCriticalSection` at `0x18004769c`
- `ntdll!RtlEnterCriticalSection` at `0x1800478dc`
- `ntdll!RtlEnterCriticalSection` at `0x180047a82`
- `ntdll!RtlLeaveCriticalSection` at `0x18004765c`
- `ntdll!RtlLeaveCriticalSection` at `0x180047673`
- `ntdll!RtlLeaveCriticalSection` at `0x1800476b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800478f8`
- `ntdll!RtlLeaveCriticalSection` at `0x180047aba`
- `ntdll!RtlLeaveCriticalSection` at `0x18004765c`
- `ntdll!RtlLeaveCriticalSection` at `0x180047673`
- `ntdll!RtlLeaveCriticalSection` at `0x1800476b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800478f8`
- `ntdll!RtlLeaveCriticalSection` at `0x180047aba`

## string_xrefs

- `0x1800475ad`: `KerbCreateCredential`
- `0x180047b1a`: `KerbCreateCredential`
- `0x1800475de`: `KerbCreateCredential failed to query token: %#x\n`
- `0x180047a52`: `KerbCreateCredential failed to duplicate client token: %#x\n`
- `0x180047ae7`: `KerbCreateCredential name not found\n`

## pseudocode

```c
__int64 __fastcall KerbCreateCredential(
        struct _LUID *a1,
        void *a2,
        struct _KERB_LOGON_SESSION *a3,
        unsigned int a4,
        struct _LSA_TOKEN_INFO_HEADER **a5,
        struct _KERB_PRIMARY_CREDENTIAL **a6,
        unsigned int a7,
        struct _UNICODE_STRING *a8,
        struct _KERB_CREDENTIAL **a9,
        union _LARGE_INTEGER *a10)
{
  void *v12; // rbx
  struct _KERB_CREDENTIAL *v13; // rdi
  NTSTATUS v14; // eax
  int KdcBinding; // ebx
  const char *v16; // r9
  __int64 v17; // r8
  __int64 v18; // rcx
  struct _KERB_CREDENTIAL *v19; // rbx
  int v21; // r14d
  struct _KERB_PRIMARY_CREDENTIAL **v22; // rcx
  struct _UNICODE_STRING *v23; // rax
  struct _KERB_TABLE_ENTRY *v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // eax
  struct _LUID *v27; // rax
  _KerberosSystemRole *v28; // rcx
  __int64 *CorrelationId; // rax
  char v30; // r14
  int v31; // ecx
  struct _KERB_CREDENTIAL **v32; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  ULONG TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  struct _KERB_TABLE_ENTRY *v36; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+70h] [rbp-90h]
  struct _KERB_CREDENTIAL *Credential; // [rsp+78h] [rbp-88h] BYREF
  union _LARGE_INTEGER *v40; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING *v41; // [rsp+88h] [rbp-78h]
  struct _KERB_CREDENTIAL **v42; // [rsp+90h] [rbp-70h]
  struct _KERB_PRIMARY_CREDENTIAL **v43; // [rsp+98h] [rbp-68h]
  HANDLE SourceHandle; // [rsp+A0h] [rbp-60h]
  _BYTE v45[32]; // [rsp+A8h] [rbp-58h] BYREF
  int TokenInformation; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v47; // [rsp+CCh] [rbp-34h]
  __int128 v48; // [rsp+DCh] [rbp-24h]
  _DWORD v49[5]; // [rsp+ECh] [rbp-14h] BYREF

  v36 = (struct _KERB_TABLE_ENTRY *)a5;
  v12 = a2;
  v13 = 0;
  v41 = a8;
  v42 = a9;
  v40 = a10;
  SourceHandle = a2;
  v43 = a6;
  v38 = 0;
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  TokenInformation = 0;
  v47 = 0;
  TokenInformationLength = 56;
  v48 = 0;
  memset(v49, 0, sizeof(v49));
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl'::`2'::impl,
    a2);
  if ( a4 && (a4 & 0xFFFFFFAC) == 0 )
  {
    if ( !*a6 )
    {
      v14 = NtQueryInformationToken(
              v12,
              TokenStatistics,
              &TokenInformation,
              TokenInformationLength,
              &TokenInformationLength);
      KdcBinding = v14;
      if ( v14 < 0 )
      {
        v16 = "KerbCreateCredential failed to query token: %#x\n";
        v17 = 1857;
        v18 = 1;
LABEL_6:
        LODWORD(ReturnLength) = v14;
        KerbTracerT::Log(v18, "KerbCreateCredential", v17, v16, ReturnLength);
LABEL_67:
        if ( v13 )
          KerbFreeCredential(v13);
        if ( KdcBinding == -1073741772 )
        {
          KerbTracerT::Log(2, "KerbCreateCredential", 2197, "KerbCreateCredential name not found\n");
          KdcBinding = -2146893042;
        }
        goto LABEL_72;
      }
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a3 + 2);
    Credential = KerbLocateCredential(
                   a1,
                   a4,
                   *(struct _LSA_TOKEN_INFO_HEADER **)v36,
                   (struct _LUID *)&v49[3],
                   (PCUNICODE_STRING)*a6,
                   a7,
                   v41);
    v19 = Credential;
    if ( Credential )
    {
      *v40 = *(union _LARGE_INTEGER *)((char *)a3 + 72);
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a3 + 2);
      *v42 = v19;
      return 0;
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a3 + 2);
    KdcBinding = KerbAllocateCredential(&Credential);
    if ( KdcBinding < 0 )
    {
      v13 = Credential;
      goto LABEL_67;
    }
    v13 = Credential;
    *(struct _LUID *)((char *)Credential + 28) = *a1;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a3 + 2);
    v21 = *((_DWORD *)a3 + 226);
    *v40 = *(union _LARGE_INTEGER *)((char *)a3 + 72);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a3 + 2);
    v22 = v43;
    *((_QWORD *)v13 + 9) = *v43;
    v23 = v41;
    *v22 = 0;
    v24 = v36;
    *((struct _UNICODE_STRING *)v13 + 3) = *v23;
    v23->Buffer = 0;
    *((_QWORD *)v13 + 12) = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    *((_DWORD *)v13 + 16) = a4 | a7;
    if ( (a4 & 3) == 0 )
    {
      KerbTracerT::Log(1, "KerbCreateCredential", 1923, "Invalid credential use flags: 0x%x", a4);
      KdcBinding = -1073741811;
      goto LABEL_67;
    }
    if ( Ntlmless::Kerberos::IsEnabled(v24) && (_BYTE)KerbGlobalRoles )
    {
      v25 = *((_QWORD *)v13 + 9);
      if ( !v25 )
      {
        v26 = a7;
        if ( (a7 & 0x20000000) == 0 && (v21 & 0x10000000) != 0 )
        {
          KerbTracerT::Log(2, "KerbCreateCredential", 1949, "kerberos SSO auth for local users is not yet supported");
          goto LABEL_17;
        }
LABEL_22:
        if ( *((_QWORD *)v13 + 9) || (v26 & 0x20000000) != 0 )
        {
          KerbTracerT::Log(3, "KerbCreateCredential", 2137, "Got supplied credentials\n");
          goto LABEL_59;
        }
        if ( (a4 & 2) != 0 )
        {
          if ( (v21 & 0xF000) != 0 )
          {
            if ( (v21 & 0x100) == 0 )
            {
              KerbTracerT::Log(
                2,
                "KerbCreateCredential",
                1974,
                "Cant go off box w/ non-fwdble logon session & no supp creds\n");
              goto LABEL_17;
            }
            KerbTracerT::Log(8, "KerbCreateCredential", 1985, "Acquiring cred, S4U required\n");
            *((_DWORD *)v13 + 16) |= 0x1000000u;
          }
          else if ( (v21 & 0x10000004) != 0 )
          {
            *((_DWORD *)v13 + 16) |= 0x8000000u;
          }
          else
          {
            v27 = a1;
            if ( (v21 & 1) == 0 )
            {
              *((_DWORD *)v13 + 16) |= 0x80800000;
              goto LABEL_30;
            }
            if ( a1->LowPart != 997 || a1->HighPart )
            {
              if ( (v21 & 2) != 0 )
              {
                KerbTracerT::Log(
                  2,
                  "KerbCreateCredential",
                  2006,
                  "Trying to acquire cred handle w/ no supplied creds for ls (%p) no pass or TGT\n",
                  (const void *)WORD1(a3));
                goto LABEL_17;
              }
              goto LABEL_30;
            }
            KerbTracerT::Log(1, "KerbCreateCredential", 2028, "Missing case for session FLAGs %x\n", v21);
          }
        }
        v27 = a1;
LABEL_30:
        if ( (a4 & 1) != 0 && KerbShouldFurtherProcessInboundCredRequest(v27) )
        {
          if ( (v21 & 1) != 0 )
          {
            if ( (v21 & 6) != 0 )
            {
              if ( !*((_DWORD *)a3 + 224) )
              {
                KerbTracerT::Log(
                  2,
                  "KerbCreateCredential",
                  2043,
                  "Trying to get inbound cred with no supplied creds, no pwd or tgt, or local only\n");
                goto LABEL_17;
              }
            }
            else
            {
              RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a3 + 2);
              KdcBinding = KerbDuplicateStringEx(&String1, (const struct _UNICODE_STRING *)((char *)a3 + 136));
              RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a3 + 2);
              if ( KdcBinding < 0 )
                goto LABEL_67;
            }
            if ( String1.Length && !_KerberosSystemRole::IsAnyKdc(v28) && !KerbIsThisOurDomain(&String1) )
            {
              v36 = 0;
              KdcBinding = KerbGetKdcBinding(&String1, 0, 0, 0, 0, &v36);
              if ( v36 )
                _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbBindingCache, v36);
              if ( KdcBinding < 0 )
              {
                KerbTracerT::Log(1, "KerbCreateCredential", 2123, "Didn't find KDC for domain %wZ", &String1);
                KdcBinding = -2146893039;
                if ( (Microsoft_Windows_Security_KerberosEnableBits & 4) != 0 )
                {
                  CorrelationId = (__int64 *)KerbTracerT::GetCorrelationId(v45);
                  v30 = 1;
                  McTemplateU0zqz_EtwEventWriteTransfer(
                    v31,
                    (unsigned int)FailureLocatingDc,
                    String1.Buffer,
                    -2146893039,
                    *CorrelationId);
                }
                else
                {
                  v30 = 0;
                }
                if ( (v30 & 1) != 0 )
                  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v45);
                goto LABEL_67;
              }
            }
          }
          else
          {
            *((_DWORD *)v13 + 16) |= 0x80800000;
          }
        }
LABEL_59:
        if ( !*(_QWORD *)&v49[3]
          || (v14 = NtDuplicateObject(
                      (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                      SourceHandle,
                      (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                      (PHANDLE)v13 + 13,
                      0,
                      0,
                      2u),
              KdcBinding = v14,
              v14 >= 0) )
        {
          *((_QWORD *)v13 + 14) = *(_QWORD *)&v49[3];
          ++*((_DWORD *)v13 + 4);
          *((_DWORD *)v13 + 22) = 1097101891;
          RtlEnterCriticalSection(&stru_180144A70);
          v32 = (struct _KERB_CREDENTIAL **)qword_180144A68;
          if ( *(_UNKNOWN **)qword_180144A68 != &KerbCredentialList )
            __fastfail(3u);
          *(_QWORD *)v13 = &KerbCredentialList;
          *((_QWORD *)v13 + 1) = v32;
          *v32 = v13;
          qword_180144A68 = (__int64)v13;
          RtlLeaveCriticalSection(&stru_180144A70);
          *v42 = v13;
          if ( KdcBinding >= 0 )
            goto LABEL_72;
          goto LABEL_67;
        }
        v16 = "KerbCreateCredential failed to duplicate client token: %#x\n";
        v17 = 2155;
        v18 = 2;
        goto LABEL_6;
      }
      if ( (*(_DWORD *)(v25 + 408) & 0x1000000) != 0 )
      {
        KerbTracerT::Log(2, "KerbCreateCredential", 1938, "kerberos auth for local users is not yet supported");
LABEL_17:
        KdcBinding = -2146893042;
        goto LABEL_67;
      }
    }
    v26 = a7;
    goto LABEL_22;
  }
  KerbTracerT::Log(1, "KerbCreateCredential", 1824, "Invalid credential use flags: 0x%x", a4);
  KdcBinding = -1073741811;
LABEL_72:
  KerbFreeString((__int64)&String1);
  return (unsigned int)KdcBinding;
}

```

## disassembly

```asm
0x1800474d8  push    rbp
0x1800474da  push    rbx
0x1800474db  push    rsi
0x1800474dc  push    rdi
0x1800474dd  push    r12
0x1800474df  push    r13
0x1800474e1  push    r14
0x1800474e3  push    r15
0x1800474e5  lea     rbp, [rsp-18h]
0x1800474ea  sub     rsp, 118h
0x1800474f1  mov     rax, cs:__security_cookie
0x1800474f8  xor     rax, rsp
0x1800474fb  mov     [rbp+50h+var_50], rax
0x1800474ff  mov     rax, [rbp+50h+arg_20]
0x180047506  xor     esi, esi
0x180047508  mov     r14, [rbp+50h+arg_28]
0x18004750f  xorps   xmm0, xmm0
0x180047512  mov     [rsp+150h+var_F8], rax
0x180047517  mov     r12d, r9d
0x18004751a  mov     eax, [rbp+50h+arg_30]
0x180047520  mov     r15, r8
0x180047523  mov     [rsp+150h+var_110], eax
0x180047527  mov     rbx, rdx
0x18004752a  mov     rax, [rbp+50h+arg_38]
0x180047531  mov     edi, esi
0x180047533  mov     [rbp+50h+var_C8], rax
0x180047537  mov     rax, [rbp+50h+arg_40]
0x18004753e  mov     [rbp+50h+var_C0], rax
0x180047542  mov     rax, [rbp+50h+arg_48]
0x180047549  mov     [rbp+50h+var_D0], rax
0x18004754d  xor     eax, eax
0x18004754f  mov     dword ptr [rbp+50h+var_64+10h], eax
0x180047552  mov     [rbp+50h+SourceHandle], rdx
0x180047556  mov     [rsp+150h+var_108], rcx
0x18004755b  mov     [rbp+50h+var_B8], r14
0x18004755f  mov     [rsp+150h+var_E0], esi
0x180047563  mov     qword ptr [rsp+150h+String1.Length], rsi
0x180047568  mov     [rsp+150h+String1.Buffer], rsi
0x18004756d  mov     [rbp+50h+TokenInformation], esi
0x180047570  movups  [rbp+50h+var_84], xmm0
0x180047574  mov     [rsp+150h+TokenInformationLength], 38h ; '8'
0x18004757c  movups  [rbp+50h+var_74], xmm0
0x180047580  movups  xmmword ptr [rbp+50h+var_64], xmm0
0x180047584  lea     r13d, [rsi+1]
0x180047588  mov     dl, r13b
0x18004758b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstantHAADJ@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstantHAADJ@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ> `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl(void)'::`2'::impl
0x180047592  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_InstantHAADJ@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180047597  test    r12d, r12d
0x18004759a  jz      loc_180047B08
0x1800475a0  test    r12d, 0FFFFFFACh
0x1800475a7  jnz     loc_180047B08
0x1800475ad  lea     rsi, aKerbcreatecred; "KerbCreateCredential"
0x1800475b4  cmp     [r14], rdi
0x1800475b7  jnz     short loc_1800475FF
0x1800475b9  mov     r9d, [rsp+150h+TokenInformationLength]; TokenInformationLength
0x1800475be  lea     rax, [rsp+150h+TokenInformationLength]
0x1800475c3  lea     r8, [rbp+50h+TokenInformation]; TokenInformation
0x1800475c7  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x1800475cc  lea     edx, [rdi+0Ah]; TokenInformationClass
0x1800475cf  mov     rcx, rbx; TokenHandle
0x1800475d2  call    cs:__imp_NtQueryInformationToken
0x1800475d8  mov     ebx, eax
0x1800475da  test    eax, eax
0x1800475dc  jns     short loc_1800475FF
0x1800475de  lea     r9, aKerbcreatecred_1; "KerbCreateCredential failed to query to"...
0x1800475e5  mov     r8d, 741h
0x1800475eb  mov     ecx, r13d
0x1800475ee  mov     rdx, rsi
0x1800475f1  mov     dword ptr [rsp+150h+ReturnLength], eax
0x1800475f5  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800475fa  jmp     loc_180047AD2
0x1800475ff  lea     r13, [r15+50h]
0x180047603  mov     rcx, r13; CriticalSection
0x180047606  call    cs:__imp_RtlEnterCriticalSection
0x18004760c  mov     rax, [rbp+50h+var_C8]
0x180047610  lea     r9, [rbp+50h+var_64+0Ch]; struct _LUID *
0x180047614  mov     r8, [rsp+150h+var_F8]
0x180047619  mov     edx, r12d; unsigned int
0x18004761c  mov     rdi, [rsp+150h+var_108]
0x180047621  mov     qword ptr [rsp+150h+Options], rax; struct _UNICODE_STRING *
0x180047626  mov     rcx, rdi; struct _LUID *
0x180047629  mov     eax, [rsp+150h+var_110]
0x18004762d  mov     r8, [r8]; struct _LSA_TOKEN_INFO_HEADER *
0x180047630  mov     [rsp+150h+HandleAttributes], eax; unsigned int
0x180047634  mov     rax, [r14]
0x180047637  mov     [rsp+150h+ReturnLength], rax; PCUNICODE_STRING
0x18004763c  call    ?KerbLocateCredential@@YAPEAU_KERB_CREDENTIAL@@PEAU_LUID@@KPEAU_LSA_TOKEN_INFO_HEADER@@0PEAU_KERB_PRIMARY_CREDENTIAL@@KPEAU_UNICODE_STRING@@@Z; KerbLocateCredential(_LUID *,ulong,_LSA_TOKEN_INFO_HEADER *,_LUID *,_KERB_PRIMARY_CREDENTIAL *,ulong,_UNICODE_STRING *)
0x180047641  mov     [rsp+150h+var_D8], rax
0x180047646  mov     rbx, rax
0x180047649  test    rax, rax
0x18004764c  jz      short loc_180047670
0x18004764e  mov     rcx, [r15+48h]
0x180047652  mov     rdx, [rbp+50h+var_D0]
0x180047656  mov     [rdx], rcx
0x180047659  mov     rcx, r13; CriticalSection
0x18004765c  call    cs:__imp_RtlLeaveCriticalSection
0x180047662  mov     rax, [rbp+50h+var_C0]
0x180047666  mov     [rax], rbx
0x180047669  xor     eax, eax
0x18004766b  jmp     loc_180047B3A
0x180047670  mov     rcx, r13; CriticalSection
0x180047673  call    cs:__imp_RtlLeaveCriticalSection
0x180047679  lea     rcx, [rsp+150h+var_D8]; struct _KERB_CREDENTIAL **
0x18004767e  call    ?KerbAllocateCredential@@YAJPEAPEAU_KERB_CREDENTIAL@@@Z; KerbAllocateCredential(_KERB_CREDENTIAL * *)
0x180047683  mov     ebx, eax
0x180047685  test    eax, eax
0x180047687  js      loc_180047ACD
0x18004768d  mov     rax, [rdi]
0x180047690  mov     rcx, r13; CriticalSection
0x180047693  mov     rdi, [rsp+150h+var_D8]
0x180047698  mov     [rdi+1Ch], rax
0x18004769c  call    cs:__imp_RtlEnterCriticalSection
0x1800476a2  mov     rdx, [rbp+50h+var_D0]
0x1800476a6  mov     rcx, r13; CriticalSection
0x1800476a9  mov     rax, [r15+48h]
0x1800476ad  mov     r14d, [r15+388h]
0x1800476b4  mov     [rdx], rax
0x1800476b7  call    cs:__imp_RtlLeaveCriticalSection
0x1800476bd  mov     rcx, [rbp+50h+var_B8]
0x1800476c1  xor     edx, edx
0x1800476c3  mov     rax, [rcx]
0x1800476c6  mov     [rdi+48h], rax
0x1800476ca  mov     rax, [rbp+50h+var_C8]
0x1800476ce  mov     [rcx], rdx
0x1800476d1  mov     rcx, [rsp+150h+var_F8]; this
0x1800476d6  movups  xmm0, xmmword ptr [rax]
0x1800476d9  movdqu  xmmword ptr [rdi+30h], xmm0
0x1800476de  mov     [rax+8], rdx
0x1800476e2  mov     rax, [rcx]
0x1800476e5  mov     [rdi+60h], rax
0x1800476e9  mov     eax, [rsp+150h+var_110]
0x1800476ed  or      eax, r12d
0x1800476f0  mov     [rcx], rdx
0x1800476f3  mov     [rdi+40h], eax
0x1800476f6  test    r12b, 3
0x1800476fa  jnz     short loc_180047725
0x1800476fc  lea     r9, aInvalidCredent; "Invalid credential use flags: 0x%x"
0x180047703  mov     dword ptr [rsp+150h+ReturnLength], r12d
0x180047708  mov     r8d, 783h
0x18004770e  mov     rdx, rsi
0x180047711  mov     ecx, 1
0x180047716  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004771b  mov     ebx, 0C000000Dh
0x180047720  jmp     loc_180047AD2
0x180047725  call    ?IsEnabled@Kerberos@Ntlmless@@YA_NXZ; Ntlmless::Kerberos::IsEnabled(void)
0x18004772a  xor     ecx, ecx
0x18004772c  test    al, al
0x18004772e  jz      short loc_180047791
0x180047730  cmp     byte ptr cs:?KerbGlobalRoles@@3U_KerberosSystemRole@@A, cl; _KerberosSystemRole KerbGlobalRoles
0x180047736  jz      short loc_180047791
0x180047738  mov     rax, [rdi+48h]
0x18004773c  test    rax, rax
0x18004773f  jz      short loc_180047771
0x180047741  test    dword ptr [rax+198h], 1000000h
0x18004774b  jz      short loc_180047791
0x18004774d  lea     r9, aKerberosAuthFo; "kerberos auth for local users is not ye"...
0x180047754  mov     r8d, 792h
0x18004775a  mov     rdx, rsi
0x18004775d  mov     ecx, 2
0x180047762  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180047767  mov     ebx, 8009030Eh
0x18004776c  jmp     loc_180047AD2
0x180047771  mov     eax, [rsp+150h+var_110]
0x180047775  bt      eax, 1Dh
0x180047779  jb      short loc_180047795
0x18004777b  bt      r14d, 1Ch
0x180047780  jnb     short loc_180047795
0x180047782  lea     r9, aKerberosSsoAut; "kerberos SSO auth for local users is no"...
0x180047789  mov     r8d, 79Dh
0x18004778f  jmp     short loc_18004775A
0x180047791  mov     eax, [rsp+150h+var_110]
0x180047795  cmp     [rdi+48h], rcx
0x180047799  jnz     loc_180047A00
0x18004779f  bt      eax, 1Dh
0x1800477a3  jb      loc_180047A00
0x1800477a9  mov     r10d, 2
0x1800477af  test    r10b, r12b
0x1800477b2  jz      short loc_1800477F5
0x1800477b4  test    r14d, 0F000h
0x1800477bb  jz      short loc_18004782D
0x1800477bd  mov     rdx, rsi
0x1800477c0  bt      r14d, 8
0x1800477c5  jb      short loc_1800477D9
0x1800477c7  lea     r9, aCantGoOffBoxWN; "Cant go off box w/ non-fwdble logon ses"...
0x1800477ce  mov     r8d, 7B6h
0x1800477d4  mov     ecx, r10d
0x1800477d7  jmp     short loc_180047762
0x1800477d9  lea     r9, aAcquiringCredS; "Acquiring cred, S4U required\n"
0x1800477e0  mov     r8d, 7C1h
0x1800477e6  mov     ecx, 8
0x1800477eb  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800477f0  bts     dword ptr [rdi+40h], 18h
0x1800477f5  mov     rax, [rsp+150h+var_108]
0x1800477fa  test    r12b, 1
0x1800477fe  jz      loc_180047A1A
0x180047804  mov     rcx, rax; struct _LUID *
0x180047807  call    ?KerbShouldFurtherProcessInboundCredRequest@@YA_NPEAU_LUID@@@Z; KerbShouldFurtherProcessInboundCredRequest(_LUID *)
0x18004780c  xor     r12d, r12d
0x18004780f  test    al, al
0x180047811  jz      loc_180047A1D
0x180047817  test    r14b, 1
0x18004781b  jnz     loc_1800478B8
0x180047821  or      dword ptr [rdi+40h], 80800000h
0x180047828  jmp     loc_180047A1D
0x18004782d  test    r14d, 10000004h
0x180047834  jz      short loc_18004783D
0x180047836  bts     dword ptr [rdi+40h], 1Bh
0x18004783b  jmp     short loc_1800477F5
0x18004783d  mov     rax, [rsp+150h+var_108]
0x180047842  test    r14b, 1
0x180047846  jz      short loc_1800478AC
0x180047848  cmp     dword ptr [rax], 3E5h
0x18004784e  jnz     short loc_180047879
0x180047850  cmp     [rax+4], ecx
0x180047853  jnz     short loc_180047879
0x180047855  lea     r9, aMissingCaseFor; "Missing case for session FLAGs %x\n"
0x18004785c  mov     dword ptr [rsp+150h+ReturnLength], r14d
0x180047861  mov     r8d, 7ECh
0x180047867  mov     rdx, rsi
0x18004786a  mov     ecx, 1
0x18004786f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180047874  jmp     loc_1800477F5
0x180047879  test    r10b, r14b
0x18004787c  jz      loc_1800477FA
0x180047882  shr     r15, 10h
0x180047886  lea     r9, aTryingToAcquir_1; "Trying to acquire cred handle w/ no sup"...
0x18004788d  movzx   eax, r15w
0x180047891  mov     r8d, 7D6h
0x180047897  mov     rdx, rsi
0x18004789a  mov     [rsp+150h+ReturnLength], rax
0x18004789f  mov     ecx, r10d
0x1800478a2  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800478a7  jmp     loc_180047767
0x1800478ac  or      dword ptr [rdi+40h], 80800000h
0x1800478b3  jmp     loc_1800477FA
0x1800478b8  test    r14b, 6
0x1800478bc  jz      short loc_1800478D9
0x1800478be  cmp     [r15+380h], r12d
0x1800478c5  jnz     short loc_180047906
0x1800478c7  lea     r9, aTryingToGetInb; "Trying to get inbound cred with no supp"...
0x1800478ce  mov     r8d, 7FBh
0x1800478d4  jmp     loc_18004775A
0x1800478d9  mov     rcx, r13; CriticalSection
0x1800478dc  call    cs:__imp_RtlEnterCriticalSection
0x1800478e2  lea     rdx, [r15+88h]; struct _UNICODE_STRING *
0x1800478e9  lea     rcx, [rsp+150h+String1]; struct _UNICODE_STRING *
0x1800478ee  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800478f3  mov     rcx, r13; CriticalSection
0x1800478f6  mov     ebx, eax
0x1800478f8  call    cs:__imp_RtlLeaveCriticalSection
0x1800478fe  test    ebx, ebx
0x180047900  js      loc_180047AD2
0x180047906  cmp     [rsp+150h+String1.Length], r12w
0x18004790c  jz      loc_180047A1D
0x180047912  call    ?IsAnyKdc@_KerberosSystemRole@@QEAA_NXZ; _KerberosSystemRole::IsAnyKdc(void)
0x180047917  test    al, al
0x180047919  jnz     loc_180047A1D
0x18004791f  lea     rcx, [rsp+150h+String1]; String1
0x180047924  call    ?KerbIsThisOurDomain@@YAEPEAU_UNICODE_STRING@@@Z; KerbIsThisOurDomain(_UNICODE_STRING *)
0x180047929  test    al, al
0x18004792b  jnz     loc_180047A1D
0x180047931  lea     rax, [rsp+150h+var_F8]
0x180047936  mov     [rsp+150h+var_F8], r12
0x18004793b  mov     qword ptr [rsp+150h+HandleAttributes], rax; struct _KERB_BINDING_CACHE_ENTRY **
0x180047940  lea     rcx, [rsp+150h+String1]; String1
0x180047945  xor     r9d, r9d; unsigned __int8
0x180047948  mov     byte ptr [rsp+150h+ReturnLength], r12b; unsigned __int8
0x18004794d  xor     r8d, r8d; unsigned int
0x180047950  xor     edx, edx; String2
0x180047952  call    ?KerbGetKdcBinding@@YAJPEAU_UNICODE_STRING@@0KEEPEAPEAU_KERB_BINDING_CACHE_ENTRY@@@Z; KerbGetKdcBinding(_UNICODE_STRING *,_UNICODE_STRING *,ulong,uchar,uchar,_KERB_BINDING_CACHE_ENTRY * *)
0x180047957  mov     rdx, [rsp+150h+var_F8]; struct _KERB_TABLE_ENTRY *
0x18004795c  mov     r14d, eax
0x18004795f  shr     r14d, 1Fh
0x180047963  mov     ebx, eax
0x180047965  xor     r14b, 1
0x180047969  test    rdx, rdx
0x18004796c  jz      short loc_18004797A
0x18004796e  lea     rcx, ?KerbBindingCache@@3U_KERB_TABLE@@A; this
0x180047975  call    ?Dereference@_KERB_TABLE@@QEAAEPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Dereference(_KERB_TABLE_ENTRY *)
0x18004797a  test    r14b, r14b
0x18004797d  jnz     loc_180047A1D
0x180047983  lea     rax, [rsp+150h+String1]
0x180047988  mov     r8d, 84Bh
0x18004798e  lea     r9, aDidnTFindKdcFo; "Didn't find KDC for domain %wZ"
0x180047995  mov     [rsp+150h+ReturnLength], rax
0x18004799a  mov     rdx, rsi
0x18004799d  mov     ecx, 1
0x1800479a2  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800479a7  test    cs:Microsoft_Windows_Security_KerberosEnableBits, 4
0x1800479ae  mov     ebx, 80090311h
0x1800479b3  jz      short loc_1800479E5
0x1800479b5  lea     rcx, [rbp+50h+var_A8]
0x1800479b9  call    ?GetCorrelationId@KerbTracerT@@SA?BV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ; KerbTracerT::GetCorrelationId(void)
0x1800479be  mov     r8, [rsp+150h+String1.Buffer]
0x1800479c3  lea     rdx, FailureLocatingDc
0x1800479ca  mov     r9d, 80090311h
0x1800479d0  mov     r14d, 1
0x1800479d6  mov     rax, [rax]
0x1800479d9  mov     [rsp+150h+ReturnLength], rax
0x1800479de  call    McTemplateU0zqz_EtwEventWriteTransfer
  ... truncated ...
```
