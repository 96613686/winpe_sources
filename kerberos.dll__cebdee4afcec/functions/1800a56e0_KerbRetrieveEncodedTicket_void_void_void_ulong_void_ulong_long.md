# KerbRetrieveEncodedTicket(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800a56e0`
- end: `0x1800a5ec8`
- name: `?KerbRetrieveEncodedTicket@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `2024`
- prototype: `__int64 __fastcall(void **, char *, unsigned __int64, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `25`
- tags: `loader_planting, service_task`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x180009afc`
- `0x180009c60`
- `0x180009fe4`
- `0x18000a630`
- `0x180010030`
- `0x180016600`
- `0x18002a2bc`
- `0x18002bd40`
- `0x18002f8b0`
- `0x1800376ec`
- `0x180037aa0`
- `0x18005d250`
- `0x18005db10`
- `0x18005de50`
- `0x180062d28`
- `0x18006ba6c`
- `0x18006d608`
- `0x180070680`
- `0x18007108c`
- `0x18008b70c`
- `0x1800a56e0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800a5bed`
- `ntdll!RtlEqualUnicodeString` at `0x1800a5bed`
- `ntdll!NtQueryInformationToken` at `0x1800a5d7d`
- `ntdll!NtQueryInformationToken` at `0x1800a5d7d`
- `ntdll!RtlEnterCriticalSection` at `0x1800a5b60`
- `ntdll!RtlEnterCriticalSection` at `0x1800a5b60`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a5c79`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a5c79`
- `LSASRV!LsaIReferenceCredHandle` at `0x1800a58bc`
- `LSASRV!LsaIReferenceCredHandle` at `0x1800a58bc`
- `LSASRV!LsaIDereferenceCredHandle` at `0x1800a5e97`
- `LSASRV!LsaIDereferenceCredHandle` at `0x1800a5e97`

## string_xrefs

- `0x1800a5d4d`: `KerbRetrieveEncodedTicket failed to get outbound ticket: KerbGetServiceTicket failed with 0x%x\n`

## pseudocode

```c
__int64 __fastcall KerbRetrieveEncodedTicket(
        void **a1,
        char *a2,
        unsigned __int64 a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        int *a7)
{
  unsigned __int64 v9; // r12
  struct _KERB_LOGON_SESSION *LogonSession; // r13
  NTSTATUS v11; // ebx
  int v12; // edi
  unsigned int v13; // r14d
  int v14; // ecx
  int *v15; // rdi
  unsigned __int64 v16; // rcx
  int v17; // esi
  __int64 v18; // rdx
  bool v19; // zf
  __int64 v20; // rcx
  const void *v21; // rcx
  const void *v22; // rax
  int ServiceTicket; // eax
  const char *v24; // r9
  __int64 v25; // r8
  __int64 v26; // rcx
  struct _LUID *v27; // r14
  unsigned int v28; // eax
  unsigned int v29; // ecx
  Ntlmless::Kerberos *v30; // rcx
  char *v31; // rbx
  Ntlmless::Kerberos *v32; // rcx
  Ntlmless::Kerberos *v33; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *v34; // r10
  struct _KERB_TICKET_CACHE_ENTRY *v35; // rax
  unsigned int v36; // eax
  __int64 v37; // r10
  int v38; // eax
  unsigned __int8 *v39; // rdi
  unsigned int v40; // r9d
  int v41; // r8d
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  unsigned int v44; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v45; // [rsp+88h] [rbp-78h]
  struct _KERB_TICKET_CACHE_ENTRY *v46; // [rsp+90h] [rbp-70h] BYREF
  struct _KERB_CREDENTIAL *v47; // [rsp+98h] [rbp-68h] BYREF
  struct _KERB_INTERNAL_NAME *v48; // [rsp+A0h] [rbp-60h] BYREF
  int TokenInformation; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v50; // [rsp+ACh] [rbp-54h] BYREF
  int v51; // [rsp+B0h] [rbp-50h]
  ULONG v52; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned __int8 *v53; // [rsp+B8h] [rbp-48h] BYREF
  struct _KERB_CREDMAN_CRED *v54; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v55; // [rsp+C8h] [rbp-38h] BYREF
  struct _KERB_CREDENTIAL *v56; // [rsp+D8h] [rbp-28h] BYREF
  struct _LUID v57; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v58; // [rsp+E8h] [rbp-18h] BYREF
  void **v59; // [rsp+F0h] [rbp-10h]
  unsigned int *v60; // [rsp+F8h] [rbp-8h]
  int *v61; // [rsp+100h] [rbp+0h]
  __int128 v62; // [rsp+108h] [rbp+8h] BYREF
  HANDLE TokenHandle[2]; // [rsp+118h] [rbp+18h]
  __int128 v64; // [rsp+128h] [rbp+28h] BYREF
  __int64 v65; // [rsp+138h] [rbp+38h]
  int v66; // [rsp+140h] [rbp+40h] BYREF
  __int64 v67; // [rsp+144h] [rbp+44h]
  __int16 v68; // [rsp+150h] [rbp+50h]
  __int16 v69; // [rsp+152h] [rbp+52h]
  __int64 v70; // [rsp+158h] [rbp+58h]
  int v71; // [rsp+160h] [rbp+60h]
  int v72; // [rsp+164h] [rbp+64h]
  int v73; // [rsp+168h] [rbp+68h]
  __int128 v74; // [rsp+180h] [rbp+80h] BYREF

  v59 = a5;
  v60 = a6;
  v9 = a4;
  v61 = a7;
  v57 = 0;
  v62 = 0;
  LogonSession = 0;
  v47 = 0;
  *(_OWORD *)TokenHandle = 0;
  v46 = 0;
  v45 = 0;
  v53 = 0;
  v50 = 0;
  v48 = 0;
  v55 = 0;
  v44 = 0;
  v54 = 0;
  v74 = 0;
  TokenInformation = 0;
  v52 = 0;
  v58 = 0;
  v51 = 0;
  KerbTracerT::Log(3, "KerbRetrieveEncodedTicket", 5516, "Retrieving encoded ticket\n");
  v65 = 0;
  v64 = 0;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v64) )
  {
    v11 = -1073741595;
LABEL_96:
    v39 = v45;
    goto LABEL_97;
  }
  v12 = BYTE8(v64) & 0x40;
  v13 = v12 != 0 ? 40 : 64;
  if ( (unsigned int)v9 < v13 )
    goto LABEL_95;
  memset_0(&v66, 0, 0x40u);
  if ( v12 )
  {
    v14 = *((_DWORD *)a2 + 6);
    v66 = *(_DWORD *)a2;
    v67 = *(_QWORD *)(a2 + 4);
    v71 = *((_DWORD *)a2 + 5);
    v73 = *((_DWORD *)a2 + 7);
    v68 = *((_WORD *)a2 + 6);
    v69 = *((_WORD *)a2 + 7);
    v70 = *((unsigned int *)a2 + 4);
    v72 = v14;
    if ( (v14 & 4) != 0 )
    {
      v11 = -1073741637;
      goto LABEL_96;
    }
    v15 = &v66;
  }
  else
  {
    v15 = (int *)a2;
  }
  v16 = *((_QWORD *)v15 + 3);
  v17 = 1;
  v18 = *((unsigned __int16 *)v15 + 8);
  if ( !v16 )
  {
    v19 = (_WORD)v18 == 0;
    goto LABEL_11;
  }
  if ( !(_WORD)v18 )
  {
    *((_QWORD *)v15 + 3) = 0;
    goto LABEL_15;
  }
  if ( v16 >= a3 && (v16 -= a3) == 0 || v16 > v9 || v16 + v18 > v9 || v16 < v13 || (v16 & 1) != 0 )
  {
LABEL_95:
    v11 = -1073741811;
    goto LABEL_96;
  }
  *((_WORD *)v15 + 9) = v18;
  *((_QWORD *)v15 + 3) = &a2[v16];
  v19 = (v18 & 1) == 0;
LABEL_11:
  if ( !v19 )
  {
    v11 = -1073741811;
    goto LABEL_96;
  }
LABEL_15:
  v11 = ((__int64 (__fastcall *)(__int128 *))LsaFunctions->GetClientInfo)(&v62);
  if ( v11 < 0 )
    goto LABEL_96;
  if ( (v15[9] & 4) != 0 )
  {
    v20 = *((_QWORD *)v15 + 7);
    v56 = 0;
    v11 = LsaIReferenceCredHandle(v20, &v74, &v56);
    if ( v11 < 0 )
    {
      if ( *((_QWORD *)v15 + 6) )
        v21 = (const void *)*((unsigned __int16 *)v15 + 25);
      else
        v21 = 0;
      if ( *((_QWORD *)v15 + 7) )
        v22 = (const void *)*((unsigned __int16 *)v15 + 29);
      else
        v22 = 0;
      KerbTracerT::Log(
        1,
        "KerbRetrieveEncodedTicket",
        5621,
        "KerbRetrieveEncodedTicket failed to validate credential %p:%p , status0x%x\n",
        v22,
        v21,
        v11);
      goto LABEL_96;
    }
    ServiceTicket = KerbReferenceCredentialEx(v56, 0x80000002, 0, 0, &v47);
    v11 = ServiceTicket;
    if ( ServiceTicket < 0 )
    {
      v24 = "KerbRetrieveEncodedTicket failed to locate credential: 0x%x\n";
      v25 = 5638;
      v26 = 2;
LABEL_34:
      LODWORD(ReturnLength) = ServiceTicket;
      KerbTracerT::Log(v26, "KerbRetrieveEncodedTicket", v25, v24, ReturnLength);
      goto LABEL_96;
    }
    v27 = &v57;
    v57 = *(struct _LUID *)((char *)v47 + 28);
  }
  else
  {
    v27 = (struct _LUID *)(v15 + 1);
    if ( *(_QWORD *)(v15 + 1) )
    {
      if ( !LOBYTE(TokenHandle[0]) )
      {
        v11 = -1073741727;
        goto LABEL_96;
      }
    }
    else
    {
      v27 = (struct _LUID *)&v62;
    }
  }
  if ( !v47 )
  {
    v11 = SpAcquireCredentialsHandle(0, 2u, 0, 0, (__int64)&v47, (__int64)&v58);
    if ( v11 < 0 )
      goto LABEL_96;
    v51 = 1;
  }
  LogonSession = KerbLocateLogonSession(v27, 0);
  if ( !LogonSession )
  {
    v11 = -1073741729;
    goto LABEL_96;
  }
  v11 = KerbProcessTargetNames((const struct _UNICODE_STRING *)v15 + 1, 0, 0, 0, 1, &v44, &v48, &v55);
  if ( v11 < 0 )
    goto LABEL_96;
  v28 = v15[9];
  v29 = v44;
  if ( (v28 & 0x40) != 0 )
  {
    v29 = v44 | 0x40000;
    v28 = v28 & 0xFFFFFFDD | 0x20;
    v44 |= 0x40000u;
    v15[9] = v28;
  }
  if ( (v28 & 0x20) != 0 )
  {
    if ( (v28 & 1) != 0 )
    {
      KerbTracerT::Log(1, "KerbRetrieveEncodedTicket", 5750, "KerbRetrieveEncodedTicket invalid options %#x\n", v28);
      v11 = -1073741637;
      goto LABEL_96;
    }
    v44 = v29 | 0x20;
  }
  ServiceTicket = KerbCheckCredMgrForGivenTarget(
                    LogonSession,
                    v47,
                    (struct _UNICODE_STRING *)v15 + 1,
                    v48,
                    0,
                    &v55,
                    0,
                    &v54,
                    0,
                    0);
  v11 = ServiceTicket;
  if ( ServiceTicket < 0 )
  {
    v24 = "KerbRetrieveEncodedTicket failed to get outbound ticket, KerbCheckCredMgrForGivenTarget failed with 0x%x\n";
    v25 = 5773;
    v26 = 1;
    goto LABEL_34;
  }
  v31 = 0;
  if ( Ntlmless::Kerberos::IsEnabled(v30) && (!v47 || (v31 = (char *)*((_QWORD *)v47 + 9)) == 0) )
    v31 = (char *)LogonSession + 120;
  if ( (v15[9] & 1) != 0 )
  {
    v44 |= 1u;
  }
  else if ( (v15[9] & 0x40) == 0 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
    if ( !Ntlmless::Kerberos::IsEnabled(v33) && (!v47 || (v31 = (char *)*((_QWORD *)v47 + 9)) == 0) )
      v31 = (char *)LogonSession + 120;
    v46 = KerbLocateTicketCacheEntryEx((struct _KERB_TICKET_CACHE *)(v31 + 240), v48, &v55, v15[10]);
    v34 = v46;
    if ( v46 )
      goto LABEL_72;
    v46 = KerbLocateTicketCacheEntryEx((struct _KERB_TICKET_CACHE *)(v31 + 160), v48, &v55, v15[10]);
    v34 = v46;
    if ( v46 || *((_WORD *)v48 + 1) != 2 )
      goto LABEL_72;
    if ( !RtlEqualUnicodeString((PCUNICODE_STRING)((char *)v48 + 8), &KerbGlobalKdcServiceName, 1u) )
      goto LABEL_71;
    v35 = KerbLocateTicketCacheEntryByRealm((struct _KERB_TICKET_CACHE *)(v31 + 240), &v55, 1u);
    v46 = v35;
    v34 = v35;
    if ( !v35 )
      goto LABEL_72;
    if ( KerbEqualKdcNames(v48, *((struct _KERB_INTERNAL_NAME **)v35 + 4)) )
    {
LABEL_71:
      v34 = v46;
    }
    else
    {
      KerbDereferenceTicketCacheEntry(v46);
      v34 = 0;
      v46 = 0;
    }
LABEL_72:
    if ( v34 )
    {
      v36 = KerbConvertKdcOptionsToTicketFlags(v15[8]);
      if ( (v36 & *(_DWORD *)(v37 + 160)) != v36 || (v38 = v15[10]) != 0 && *(_DWORD *)(v37 + 308) != v38 )
      {
        KerbDereferenceTicketCacheEntry((struct _KERB_TICKET_CACHE_ENTRY *)v37);
        v46 = 0;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
  }
  if ( !v46 )
  {
    if ( (v15[9] & 2) != 0 )
    {
      v39 = v45;
      v11 = -1073741772;
LABEL_100:
      if ( v54 )
        KerbDereferenceCredmanCred(v54, (struct _KERB_LOGON_SESSION *)((char *)LogonSession + 8));
      KerbDereferenceLogonSession(LogonSession);
      goto LABEL_103;
    }
    if ( Ntlmless::Kerberos::IsEnabled(v32) && (*((_DWORD *)v31 + 102) & 0x1000000) != 0 )
    {
      v40 = v44 | 0x20000000;
      v44 |= 0x20000000u;
    }
    else
    {
      v40 = v44;
    }
    ServiceTicket = KerbGetServiceTicketEx(
                      LogonSession,
                      v47,
                      v54,
                      0,
                      0,
                      v48,
                      &v55,
                      (KerbGlobalUseForestSearch != 0 ? 1179648 : 0x100000) | v40,
                      v15[8],
                      v15[10],
                      0,
                      0,
                      0,
                      &v46,
                      0,
                      0);
    v11 = ServiceTicket;
    if ( ServiceTicket < 0 )
    {
      v24 = "KerbRetrieveEncodedTicket failed to get outbound ticket: KerbGetServiceTicket failed with 0x%x\n";
      v25 = 5973;
      v26 = 2;
      goto LABEL_34;
    }
  }
  v11 = NtQueryInformationToken(TokenHandle[1], TokenElevationType, &TokenInformation, 4u, &v52);
  if ( v11 < 0 )
    goto LABEL_96;
  KerbTelemetry::KerbRetrieveTicket(*((KerbTelemetry **)v46 + 4), (struct _KERB_INTERNAL_NAME *)1, v41);
  if ( !LOBYTE(TokenHandle[0]) && !KerbGlobalAllowTgtSessionKey )
    v17 = 0;
  v11 = KerbPackExternalTicket(v46, v15[9] & 8, v17, TokenInformation == 3, &v50, &v53);
  if ( v11 < 0 )
  {
    v39 = v53;
  }
  else
  {
    v39 = 0;
    *v59 = v53;
    *v60 = v50;
  }
LABEL_97:
  if ( v46 )
    KerbDereferenceTicketCacheEntry(v46);
  if ( LogonSession )
    goto LABEL_100;
LABEL_103:
  if ( v47 )
  {
    if ( v51 )
      SpFreeCredentialsHandle(v47);
    else
      KerbDereferenceCredential(v47);
  }
  if ( v39 )
    ((void (__fastcall *)(_QWORD, unsigned __int8 *))LsaFunctions->FreeClientBuffer)(0, v39);
  KerbFreeString(&v55);
  KerbFreeKdcName(&v48);
  if ( v74 != 0 )
    LsaIDereferenceCredHandle(&v74);
  *v61 = v11;
  return 0;
}

```

## disassembly

```asm
0x1800a56e0  push    rbp
0x1800a56e2  push    rbx
0x1800a56e3  push    rsi
0x1800a56e4  push    rdi
0x1800a56e5  push    r12
0x1800a56e7  push    r13
0x1800a56e9  push    r14
0x1800a56eb  push    r15
0x1800a56ed  lea     rbp, [rsp-0A8h]
0x1800a56f5  sub     rsp, 1A8h
0x1800a56fc  mov     rax, cs:__security_cookie
0x1800a5703  xor     rax, rsp
0x1800a5706  mov     [rbp+0E0h+var_50], rax
0x1800a570d  mov     rax, [rbp+0E0h+arg_20]
0x1800a5714  xor     esi, esi
0x1800a5716  xorps   xmm0, xmm0
0x1800a5719  mov     [rbp+0E0h+var_F0], rax
0x1800a571d  mov     rax, [rbp+0E0h+arg_28]
0x1800a5724  mov     r15, r8
0x1800a5727  mov     [rbp+0E0h+var_E8], rax
0x1800a572b  mov     rbx, rdx
0x1800a572e  mov     rax, [rbp+0E0h+arg_30]
0x1800a5735  lea     rdx, aKerbretrieveen_1; "KerbRetrieveEncodedTicket"
0x1800a573c  mov     r12d, r9d
0x1800a573f  lea     ecx, [rsi+3]
0x1800a5742  lea     r9, aRetrievingEnco; "Retrieving encoded ticket\n"
0x1800a5749  mov     [rbp+0E0h+var_E0], rax
0x1800a574d  mov     r8d, 158Ch
0x1800a5753  mov     qword ptr [rbp+0E0h+var_100.LowPart], rsi
0x1800a5757  movups  [rbp+0E0h+var_D8], xmm0
0x1800a575b  mov     r13d, esi
0x1800a575e  mov     [rbp+0E0h+var_148], rsi
0x1800a5762  movups  xmmword ptr [rbp+0E0h+TokenHandle], xmm0
0x1800a5766  mov     [rbp+0E0h+var_150], rsi
0x1800a576a  mov     [rbp+0E0h+var_158], rsi
0x1800a576e  mov     [rbp+0E0h+var_128], rsi
0x1800a5772  mov     [rbp+0E0h+var_134], esi
0x1800a5775  mov     [rbp+0E0h+var_140], rsi
0x1800a5779  movups  xmmword ptr [rbp+0E0h+var_118.Length], xmm0
0x1800a577d  mov     [rbp+0E0h+var_160], esi
0x1800a5780  mov     [rbp+0E0h+var_120], rsi
0x1800a5784  movups  [rbp+0E0h+var_60], xmm0
0x1800a578b  mov     [rbp+0E0h+TokenInformation], esi
0x1800a578e  mov     [rbp+0E0h+var_12C], esi
0x1800a5791  mov     [rbp+0E0h+var_F8], rsi
0x1800a5795  mov     [rbp+0E0h+var_130], esi
0x1800a5798  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a579d  xor     eax, eax
0x1800a579f  lea     rcx, [rbp+0E0h+var_B8]
0x1800a57a3  mov     [rbp+0E0h+var_A8], rax
0x1800a57a7  xorps   xmm0, xmm0
0x1800a57aa  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800a57b1  movups  [rbp+0E0h+var_B8], xmm0
0x1800a57b5  mov     rax, [rax+0C0h]
0x1800a57bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a57c1  test    al, al
0x1800a57c3  jnz     short loc_1800A57CF
0x1800a57c5  mov     ebx, 0C00000E5h
0x1800a57ca  jmp     loc_1800A5E03
0x1800a57cf  mov     edi, dword ptr [rbp+0E0h+var_B8+8]
0x1800a57d2  and     edi, 40h
0x1800a57d5  mov     eax, edi
0x1800a57d7  neg     eax
0x1800a57d9  sbb     r14d, r14d
0x1800a57dc  and     r14d, 0FFFFFFE8h
0x1800a57e0  add     r14d, 40h ; '@'
0x1800a57e4  cmp     r12d, r14d
0x1800a57e7  jb      loc_1800A5DFE
0x1800a57ed  xor     edx, edx; Val
0x1800a57ef  lea     rcx, [rbp+0E0h+var_A0]; void *
0x1800a57f3  lea     r8d, [rdx+40h]; Size
0x1800a57f7  call    memset_0
0x1800a57fc  test    edi, edi
0x1800a57fe  jz      short loc_1800A584B
0x1800a5800  mov     eax, [rbx]
0x1800a5802  mov     ecx, [rbx+18h]
0x1800a5805  mov     [rbp+0E0h+var_A0], eax
0x1800a5808  mov     rax, [rbx+4]
0x1800a580c  mov     [rbp+0E0h+var_9C], rax
0x1800a5810  mov     eax, [rbx+14h]
0x1800a5813  mov     [rbp+0E0h+var_80], eax
0x1800a5816  mov     eax, [rbx+1Ch]
0x1800a5819  mov     [rbp+0E0h+var_78], eax
0x1800a581c  movzx   eax, word ptr [rbx+0Ch]
0x1800a5820  mov     [rbp+0E0h+var_90], ax
0x1800a5824  movzx   eax, word ptr [rbx+0Eh]
0x1800a5828  mov     [rbp+0E0h+var_8E], ax
0x1800a582c  mov     eax, [rbx+10h]
0x1800a582f  mov     [rbp+0E0h+var_88], rax
0x1800a5833  mov     [rbp+0E0h+var_7C], ecx
0x1800a5836  test    cl, 4
0x1800a5839  jz      short loc_1800A5845
0x1800a583b  mov     ebx, 0C00000BBh
0x1800a5840  jmp     loc_1800A5E03
0x1800a5845  lea     rdi, [rbp+0E0h+var_A0]
0x1800a5849  jmp     short loc_1800A584E
0x1800a584b  mov     rdi, rbx
0x1800a584e  mov     rcx, [rdi+18h]
0x1800a5852  mov     esi, 1
0x1800a5857  movzx   edx, word ptr [rdi+10h]
0x1800a585b  test    rcx, rcx
0x1800a585e  jnz     short loc_1800A5872
0x1800a5860  xor     r12d, r12d
0x1800a5863  test    dx, dx
0x1800a5866  jz      short loc_1800A587E
0x1800a5868  mov     ebx, 0C000000Dh
0x1800a586d  jmp     loc_1800A5E06
0x1800a5872  test    dx, dx
0x1800a5875  jnz     short loc_1800A58D8
0x1800a5877  xor     r12d, r12d
0x1800a587a  mov     [rdi+18h], r12
0x1800a587e  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800a5885  lea     rcx, [rbp+0E0h+var_D8]
0x1800a5889  mov     rax, [rax+80h]
0x1800a5890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5895  mov     ebx, eax
0x1800a5897  test    eax, eax
0x1800a5899  js      loc_1800A5E06
0x1800a589f  test    byte ptr [rdi+24h], 4
0x1800a58a3  jz      loc_1800A5A23
0x1800a58a9  mov     rcx, [rdi+38h]
0x1800a58ad  lea     r8, [rbp+0E0h+var_108]
0x1800a58b1  lea     rdx, [rbp+0E0h+var_60]
0x1800a58b8  mov     [rbp+0E0h+var_108], r12
0x1800a58bc  call    cs:__imp_LsaIReferenceCredHandle
0x1800a58c2  mov     ebx, eax
0x1800a58c4  test    eax, eax
0x1800a58c6  jns     loc_1800A5968
0x1800a58cc  cmp     [rdi+30h], r12
0x1800a58d0  jz      short loc_1800A5928
0x1800a58d2  movzx   ecx, word ptr [rdi+32h]
0x1800a58d6  jmp     short loc_1800A592B
0x1800a58d8  cmp     rcx, r15
0x1800a58db  jb      short loc_1800A58E6
0x1800a58dd  sub     rcx, r15
0x1800a58e0  jz      loc_1800A5DFE
0x1800a58e6  cmp     rcx, r12
0x1800a58e9  ja      loc_1800A5DFE
0x1800a58ef  lea     rax, [rcx+rdx]
0x1800a58f3  cmp     rax, r12
0x1800a58f6  ja      loc_1800A5DFE
0x1800a58fc  mov     eax, r14d
0x1800a58ff  cmp     rcx, rax
0x1800a5902  jb      loc_1800A5DFE
0x1800a5908  test    sil, cl
0x1800a590b  jnz     loc_1800A5DFE
0x1800a5911  lea     rax, [rbx+rcx]
0x1800a5915  mov     [rdi+12h], dx
0x1800a5919  xor     r12d, r12d
0x1800a591c  mov     [rdi+18h], rax
0x1800a5920  test    sil, dl
0x1800a5923  jmp     loc_1800A5866
0x1800a5928  mov     rcx, r12
0x1800a592b  cmp     [rdi+38h], r12
0x1800a592f  jz      short loc_1800A5937
0x1800a5931  movzx   eax, word ptr [rdi+3Ah]
0x1800a5935  jmp     short loc_1800A593A
0x1800a5937  mov     rax, r12
0x1800a593a  mov     dword ptr [rsp+1E0h+var_1B0], ebx
0x1800a593e  lea     r9, aKerbretrieveen_3; "KerbRetrieveEncodedTicket failed to val"...
0x1800a5945  mov     [rsp+1E0h+var_1B8], rcx
0x1800a594a  lea     rdx, aKerbretrieveen_1; "KerbRetrieveEncodedTicket"
0x1800a5951  mov     ecx, esi
0x1800a5953  mov     [rsp+1E0h+ReturnLength], rax
0x1800a5958  mov     r8d, 15F5h
0x1800a595e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a5963  jmp     loc_1800A5E06
0x1800a5968  mov     rcx, [rbp+0E0h+var_108]; struct _KERB_CREDENTIAL *
0x1800a596c  lea     rax, [rbp+0E0h+var_148]
0x1800a5970  xor     r9d, r9d; int
0x1800a5973  mov     [rsp+1E0h+ReturnLength], rax; struct _KERB_CREDENTIAL **
0x1800a5978  xor     r8d, r8d; unsigned __int8
0x1800a597b  mov     edx, 80000002h; unsigned int
0x1800a5980  call    ?KerbReferenceCredentialEx@@YAJ_KKEHPEAPEAU_KERB_CREDENTIAL@@@Z; KerbReferenceCredentialEx(unsigned __int64,ulong,uchar,int,_KERB_CREDENTIAL * *)
0x1800a5985  mov     ebx, eax
0x1800a5987  test    eax, eax
0x1800a5989  jns     short loc_1800A59B2
0x1800a598b  lea     r9, aKerbretrieveen_2; "KerbRetrieveEncodedTicket failed to loc"...
0x1800a5992  mov     r8d, 1606h
0x1800a5998  mov     ecx, 2
0x1800a599d  lea     rdx, aKerbretrieveen_1; "KerbRetrieveEncodedTicket"
0x1800a59a4  mov     dword ptr [rsp+1E0h+ReturnLength], eax
0x1800a59a8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a59ad  jmp     loc_1800A5E06
0x1800a59b2  mov     rax, [rbp+0E0h+var_148]
0x1800a59b6  lea     r14, [rbp+0E0h+var_100]
0x1800a59ba  mov     rcx, [rax+1Ch]
0x1800a59be  mov     qword ptr [rbp+0E0h+var_100.LowPart], rcx
0x1800a59c2  mov     r15d, 2
0x1800a59c8  cmp     [rbp+0E0h+var_148], r12
0x1800a59cc  jnz     short loc_1800A5A07
0x1800a59ce  lea     rax, [rbp+0E0h+var_F8]
0x1800a59d2  xor     r9d, r9d
0x1800a59d5  mov     [rsp+1E0h+var_1A8], rax; __int64
0x1800a59da  mov     r8, r14
0x1800a59dd  lea     rax, [rbp+0E0h+var_148]
0x1800a59e1  mov     edx, r15d; unsigned int
0x1800a59e4  mov     [rsp+1E0h+var_1B0], rax; __int64
0x1800a59e9  xor     ecx, ecx; struct _UNICODE_STRING *
0x1800a59eb  mov     [rsp+1E0h+var_1B8], r12; int
0x1800a59f0  mov     [rsp+1E0h+ReturnLength], r12; int
0x1800a59f5  call    SpAcquireCredentialsHandle
0x1800a59fa  mov     ebx, eax
0x1800a59fc  test    eax, eax
0x1800a59fe  js      loc_1800A5E06
0x1800a5a04  mov     [rbp+0E0h+var_130], esi
0x1800a5a07  xor     edx, edx; unsigned __int8
0x1800a5a09  mov     rcx, r14; struct _LUID *
0x1800a5a0c  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x1800a5a11  mov     r13, rax
0x1800a5a14  test    rax, rax
0x1800a5a17  jnz     short loc_1800A5A45
0x1800a5a19  mov     ebx, 0C000005Fh
0x1800a5a1e  jmp     loc_1800A5E06
0x1800a5a23  mov     eax, [rdi+8]
0x1800a5a26  lea     r14, [rdi+4]
0x1800a5a2a  or      eax, [r14]
0x1800a5a2d  jnz     short loc_1800A5A35
0x1800a5a2f  lea     r14, [rbp+0E0h+var_D8]
0x1800a5a33  jmp     short loc_1800A59C2
0x1800a5a35  cmp     byte ptr [rbp+0E0h+TokenHandle], r12b
0x1800a5a39  jnz     short loc_1800A59C2
0x1800a5a3b  mov     ebx, 0C0000061h
0x1800a5a40  jmp     loc_1800A5E06
0x1800a5a45  lea     rax, [rbp+0E0h+var_118]
0x1800a5a49  xor     r9d, r9d; unsigned int
0x1800a5a4c  mov     [rsp+1E0h+var_1A8], rax; struct _UNICODE_STRING *
0x1800a5a51  lea     rcx, [rdi+10h]; struct _UNICODE_STRING *
0x1800a5a55  lea     rax, [rbp+0E0h+var_140]
0x1800a5a59  xor     r8d, r8d; PCUNICODE_STRING
0x1800a5a5c  mov     [rsp+1E0h+var_1B0], rax; struct _KERB_INTERNAL_NAME **
0x1800a5a61  xor     edx, edx; String
0x1800a5a63  lea     rax, [rbp+0E0h+var_160]
0x1800a5a67  mov     [rsp+1E0h+var_1B8], rax; unsigned int *
0x1800a5a6c  mov     byte ptr [rsp+1E0h+ReturnLength], sil; char
0x1800a5a71  call    ?KerbProcessTargetNames@@YAJPEBU_UNICODE_STRING@@00KEPEAKPEAPEAU_KERB_INTERNAL_NAME@@PEAU1@@Z; KerbProcessTargetNames(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong,uchar,ulong *,_KERB_INTERNAL_NAME * *,_UNICODE_STRING *)
0x1800a5a76  mov     ebx, eax
0x1800a5a78  test    eax, eax
0x1800a5a7a  js      loc_1800A5E06
0x1800a5a80  mov     eax, [rdi+24h]
0x1800a5a83  mov     ecx, [rbp+0E0h+var_160]
0x1800a5a86  test    al, 40h
0x1800a5a88  jz      short loc_1800A5A9A
0x1800a5a8a  bts     ecx, 12h
0x1800a5a8e  and     eax, 0FFFFFFFDh
0x1800a5a91  or      eax, 20h
0x1800a5a94  mov     [rbp+0E0h+var_160], ecx
0x1800a5a97  mov     [rdi+24h], eax
0x1800a5a9a  test    al, 20h
0x1800a5a9c  jz      short loc_1800A5AD2
0x1800a5a9e  test    sil, al
0x1800a5aa1  jz      short loc_1800A5ACC
0x1800a5aa3  lea     r9, aKerbretrieveen; "KerbRetrieveEncodedTicket invalid optio"...
0x1800a5aaa  mov     dword ptr [rsp+1E0h+ReturnLength], eax
0x1800a5aae  mov     r8d, 1676h
0x1800a5ab4  lea     rdx, aKerbretrieveen_1; "KerbRetrieveEncodedTicket"
0x1800a5abb  mov     ecx, esi
0x1800a5abd  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a5ac2  mov     ebx, 0C00000BBh
0x1800a5ac7  jmp     loc_1800A5E06
0x1800a5acc  or      ecx, 20h
0x1800a5acf  mov     [rbp+0E0h+var_160], ecx
0x1800a5ad2  mov     r9, [rbp+0E0h+var_140]; struct _KERB_INTERNAL_NAME *
0x1800a5ad6  lea     rax, [rbp+0E0h+var_120]
0x1800a5ada  mov     rdx, [rbp+0E0h+var_148]; struct _KERB_CREDENTIAL *
0x1800a5ade  lea     r8, [rdi+10h]; struct _UNICODE_STRING *
0x1800a5ae2  mov     [rsp+1E0h+var_198], r12; unsigned int *
0x1800a5ae7  mov     rcx, r13; struct _KERB_LOGON_SESSION *
0x1800a5aea  mov     [rsp+1E0h+var_1A0], r12; unsigned __int8 **
0x1800a5aef  mov     [rsp+1E0h+var_1A8], rax; struct _KERB_CREDMAN_CRED **
0x1800a5af4  lea     rax, [rbp+0E0h+var_118]
0x1800a5af8  mov     [rsp+1E0h+var_1B0], r12; struct _UNICODE_STRING *
0x1800a5afd  mov     [rsp+1E0h+var_1B8], rax; struct _UNICODE_STRING *
0x1800a5b02  mov     dword ptr [rsp+1E0h+ReturnLength], r12d; unsigned int
0x1800a5b07  call    ?KerbCheckCredMgrForGivenTarget@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@K22PEAPEAU_KERB_CREDMAN_CRED@@PEAPEAEPEAK@Z; KerbCheckCredMgrForGivenTarget(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_UNICODE_STRING *,_KERB_INTERNAL_NAME *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_CREDMAN_CRED * *,uchar * *,ulong *)
0x1800a5b0c  mov     ebx, eax
0x1800a5b0e  test    eax, eax
0x1800a5b10  jns     short loc_1800A5B26
0x1800a5b12  lea     r9, aKerbretrieveen_0; "KerbRetrieveEncodedTicket failed to get"...
0x1800a5b19  mov     r8d, 168Dh
0x1800a5b1f  mov     ecx, esi
0x1800a5b21  jmp     loc_1800A599D
0x1800a5b26  mov     rbx, r12
0x1800a5b29  call    ?IsEnabled@Kerberos@Ntlmless@@YA_NXZ; Ntlmless::Kerberos::IsEnabled(void)
0x1800a5b2e  test    al, al
0x1800a5b30  jz      short loc_1800A5B48
0x1800a5b32  mov     rbx, [rbp+0E0h+var_148]
0x1800a5b36  test    rbx, rbx
0x1800a5b39  jz      short loc_1800A5B44
0x1800a5b3b  mov     rbx, [rbx+48h]
0x1800a5b3f  test    rbx, rbx
0x1800a5b42  jnz     short loc_1800A5B48
0x1800a5b44  lea     rbx, [r13+78h]
0x1800a5b48  test    [rdi+24h], sil
0x1800a5b4c  jnz     loc_1800A5C84
0x1800a5b52  test    byte ptr [rdi+24h], 40h
0x1800a5b56  jnz     loc_1800A5C87
0x1800a5b5c  lea     rcx, [r13+50h]; CriticalSection
0x1800a5b60  call    cs:__imp_RtlEnterCriticalSection
0x1800a5b66  call    ?IsEnabled@Kerberos@Ntlmless@@YA_NXZ; Ntlmless::Kerberos::IsEnabled(void)
  ... truncated ...
```
