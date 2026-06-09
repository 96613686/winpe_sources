# KerbPurgeTicketEx(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800a3040`
- end: `0x1800a3697`
- name: `?KerbPurgeTicketEx@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `1623`
- prototype: `__int64 __fastcall(void **, char *, unsigned __int64, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009afc`
- `0x18000a630`
- `0x18004f220`
- `0x18007108c`
- `0x18008b70c`
- `0x180097fdc`
- `0x18009ea84`
- `0x1800a2b78`
- `0x1800a3040`
- `0x1800b4100`
- `0x1800b4630`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3427`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800a341a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800a341a`
- `ntdll!RtlEqualUnicodeString` at `0x1800a3560`
- `ntdll!RtlEqualUnicodeString` at `0x1800a357c`
- `ntdll!RtlEqualUnicodeString` at `0x1800a35f9`
- `ntdll!RtlEqualUnicodeString` at `0x1800a3611`
- `ntdll!RtlEqualUnicodeString` at `0x1800a3560`
- `ntdll!RtlEqualUnicodeString` at `0x1800a357c`
- `ntdll!RtlEqualUnicodeString` at `0x1800a35f9`
- `ntdll!RtlEqualUnicodeString` at `0x1800a3611`
- `ntdll!RtlEnterCriticalSection` at `0x1800a34dc`
- `ntdll!RtlEnterCriticalSection` at `0x1800a35ca`
- `ntdll!RtlEnterCriticalSection` at `0x1800a34dc`
- `ntdll!RtlEnterCriticalSection` at `0x1800a35ca`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a350f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3658`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3677`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a350f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3658`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3677`

## string_xrefs

- `0x1800a307d`: `Purging ticket cache Ex\n`
- `0x1800a342d`: `KerbPurgeTicketEx CheckTokenMembership failed with %#x\n`

## pseudocode

```c
__int64 __fastcall KerbPurgeTicketEx(
        void **a1,
        char *a2,
        unsigned __int64 a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        int *a7)
{
  unsigned __int64 v7; // r14
  signed int v10; // ebx
  unsigned int v11; // r8d
  int *v12; // rdi
  unsigned __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  struct _LUID *v22; // rbx
  struct _KERB_LOGON_SESSION *LogonSession; // rsi
  DWORD LastError; // eax
  struct _KERB_DOMAIN_CACHE *v25; // rcx
  _QWORD *i; // rdi
  struct _KERB_PRIMARY_CREDENTIAL *v27; // rcx
  char v28; // al
  char v29; // r13
  char v30; // r14
  const UNICODE_STRING *v31; // rbx
  struct _UNICODE_STRING *v32; // rdx
  struct _UNICODE_STRING *v33; // r8
  int v34; // eax
  _QWORD *v35; // rdi
  UNICODE_STRING *v36; // rcx
  struct _UNICODE_STRING *v37; // rdx
  struct _UNICODE_STRING *v38; // r8
  const UNICODE_STRING *v39; // [rsp+30h] [rbp-D0h]
  PCUNICODE_STRING String2; // [rsp+38h] [rbp-C8h]
  struct _UNICODE_STRING *v41; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING *v42; // [rsp+48h] [rbp-B8h]
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+54h] [rbp-ACh]
  int v45; // [rsp+5Ch] [rbp-A4h]
  __int16 v46; // [rsp+60h] [rbp-A0h]
  __int16 v47; // [rsp+62h] [rbp-9Eh]
  __int64 v48; // [rsp+68h] [rbp-98h]
  __int16 v49; // [rsp+70h] [rbp-90h]
  __int16 v50; // [rsp+72h] [rbp-8Eh]
  __int64 v51; // [rsp+78h] [rbp-88h]
  __int16 v52; // [rsp+80h] [rbp-80h]
  __int16 v53; // [rsp+82h] [rbp-7Eh]
  __int64 v54; // [rsp+88h] [rbp-78h]
  __int16 v55; // [rsp+90h] [rbp-70h]
  __int16 v56; // [rsp+92h] [rbp-6Eh]
  __int64 v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  __int64 v60; // [rsp+B0h] [rbp-50h]
  int v61; // [rsp+B8h] [rbp-48h]
  int v62; // [rsp+BCh] [rbp-44h]
  struct _LUID v63[2]; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE TokenHandle[2]; // [rsp+D0h] [rbp-30h]
  __int128 v65; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v66; // [rsp+F0h] [rbp-10h]
  WINBOOL IsMember; // [rsp+158h] [rbp+58h] BYREF

  v7 = a4;
  *(_OWORD *)&v63[0].LowPart = 0;
  *(_OWORD *)TokenHandle = 0;
  memset_0(&v43, 0, 0x70u);
  KerbTracerT::Log(3, "KerbPurgeTicketEx", 5096, "Purging ticket cache Ex\n");
  v66 = 0;
  v65 = 0;
  if ( ((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v65) )
  {
    v11 = (BYTE8(v65) & 0x40) != 0 ? 80 : 112;
    if ( (unsigned int)v7 < v11 )
    {
LABEL_9:
      v10 = -1073741811;
      goto LABEL_10;
    }
    if ( (BYTE8(v65) & 0x40) != 0 )
    {
      v12 = &v43;
      v43 = *(_DWORD *)a2;
      v44 = *(_QWORD *)(a2 + 4);
      v45 = *((_DWORD *)a2 + 3);
      v46 = *((_WORD *)a2 + 8);
      v47 = *((_WORD *)a2 + 9);
      v48 = *((unsigned int *)a2 + 5);
      v49 = *((_WORD *)a2 + 12);
      v50 = *((_WORD *)a2 + 13);
      v51 = *((unsigned int *)a2 + 7);
      v52 = *((_WORD *)a2 + 16);
      v53 = *((_WORD *)a2 + 17);
      v54 = *((unsigned int *)a2 + 9);
      v55 = *((_WORD *)a2 + 20);
      v56 = *((_WORD *)a2 + 21);
      v57 = *((unsigned int *)a2 + 11);
      v58 = *((_QWORD *)a2 + 6);
      v59 = *((_QWORD *)a2 + 7);
      v60 = *((_QWORD *)a2 + 8);
      v61 = *((_DWORD *)a2 + 18);
      v62 = *((_DWORD *)a2 + 19);
    }
    else
    {
      v12 = (int *)a2;
    }
    v13 = *((_QWORD *)v12 + 3);
    v14 = *((unsigned __int16 *)v12 + 8);
    String2 = (PCUNICODE_STRING)(v12 + 4);
    if ( v13 )
    {
      if ( (_WORD)v14 )
      {
        if ( v13 >= a3 )
        {
          v13 -= a3;
          if ( !v13 )
            goto LABEL_9;
        }
        if ( v13 > v7 )
          goto LABEL_9;
        if ( v13 + v14 > v7 )
          goto LABEL_9;
        if ( v13 < v11 )
          goto LABEL_9;
        if ( (v13 & 1) != 0 )
          goto LABEL_9;
        *((_WORD *)v12 + 9) = v14;
        *((_QWORD *)v12 + 3) = &a2[v13];
        if ( (v14 & 1) != 0 )
          goto LABEL_9;
      }
      else
      {
        *((_QWORD *)v12 + 3) = 0;
      }
    }
    else if ( (_WORD)v14 )
    {
      goto LABEL_9;
    }
    v16 = *((_QWORD *)v12 + 5);
    v17 = *((unsigned __int16 *)v12 + 16);
    v39 = (const UNICODE_STRING *)(v12 + 8);
    if ( v16 )
    {
      if ( (_WORD)v17 )
      {
        if ( v16 >= a3 )
        {
          v16 -= a3;
          if ( !v16 )
            goto LABEL_9;
        }
        if ( v16 > v7 )
          goto LABEL_9;
        if ( v16 + v17 > v7 )
          goto LABEL_9;
        if ( v16 < v11 )
          goto LABEL_9;
        if ( (v16 & 1) != 0 )
          goto LABEL_9;
        *((_WORD *)v12 + 17) = v17;
        *((_QWORD *)v12 + 5) = &a2[v16];
        if ( (v17 & 1) != 0 )
          goto LABEL_9;
      }
      else
      {
        *((_QWORD *)v12 + 5) = 0;
      }
    }
    else if ( (_WORD)v17 )
    {
      goto LABEL_9;
    }
    v18 = *((_QWORD *)v12 + 7);
    v19 = *((unsigned __int16 *)v12 + 24);
    v41 = (struct _UNICODE_STRING *)(v12 + 12);
    if ( v18 )
    {
      if ( (_WORD)v19 )
      {
        if ( v18 >= a3 )
        {
          v18 -= a3;
          if ( !v18 )
            goto LABEL_9;
        }
        if ( v18 > v7 )
          goto LABEL_9;
        if ( v18 + v19 > v7 )
          goto LABEL_9;
        if ( v18 < v11 )
          goto LABEL_9;
        if ( (v18 & 1) != 0 )
          goto LABEL_9;
        *((_WORD *)v12 + 25) = v19;
        *((_QWORD *)v12 + 7) = &a2[v18];
        if ( (v19 & 1) != 0 )
          goto LABEL_9;
      }
      else
      {
        *((_QWORD *)v12 + 7) = 0;
      }
    }
    else if ( (_WORD)v19 )
    {
      goto LABEL_9;
    }
    v20 = *((_QWORD *)v12 + 9);
    v21 = *((unsigned __int16 *)v12 + 32);
    v42 = (struct _UNICODE_STRING *)(v12 + 16);
    if ( v20 )
    {
      if ( (_WORD)v21 )
      {
        if ( v20 >= a3 )
        {
          v20 -= a3;
          if ( !v20 )
            goto LABEL_9;
        }
        if ( v20 > v7 )
          goto LABEL_9;
        if ( v20 + v21 > v7 )
          goto LABEL_9;
        if ( v20 < v11 )
          goto LABEL_9;
        if ( (v20 & 1) != 0 )
          goto LABEL_9;
        *((_WORD *)v12 + 33) = v21;
        *((_QWORD *)v12 + 9) = &a2[v20];
        if ( (v21 & 1) != 0 )
          goto LABEL_9;
      }
      else
      {
        *((_QWORD *)v12 + 9) = 0;
      }
    }
    else if ( (_WORD)v21 )
    {
      goto LABEL_9;
    }
    v10 = ((__int64 (__fastcall *)(struct _LUID *))LsaFunctions->GetClientInfo)(v63);
    if ( v10 < 0 )
      goto LABEL_10;
    v22 = (struct _LUID *)(v12 + 1);
    if ( *(_QWORD *)(v12 + 1) )
    {
      if ( !LOBYTE(TokenHandle[0]) )
      {
        IsMember = 0;
        if ( !TokenHandle[1] )
        {
          v10 = -1073741670;
          goto LABEL_10;
        }
        if ( !CheckTokenMembership(TokenHandle[1], KerbGlobalAliasAdminsSid, &IsMember) )
        {
          LastError = GetLastError();
          KerbTracerT::Log(
            1,
            "KerbPurgeTicketEx",
            5218,
            "KerbPurgeTicketEx CheckTokenMembership failed with %#x\n",
            LastError);
          v10 = -1073741670;
          goto LABEL_10;
        }
        if ( !IsMember )
        {
          v10 = -1073741727;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v22 = v63;
    }
    LogonSession = KerbLocateLogonSession(v22, 0);
    if ( !LogonSession )
    {
      v10 = -1073741729;
      goto LABEL_10;
    }
    if ( (v12[3] & 1) != 0 )
    {
      KerbTracerT::Log(3, "KerbPurgeTicketEx", 5256, "Purging all tickets\n");
      KerbCleanupSpnCache();
      *((_DWORD *)LogonSession + 132) &= ~8u;
      if ( *((_DWORD *)LogonSession + 16) == 999 && !*((_DWORD *)LogonSession + 17) )
      {
        KerbPurgeCompoundedTickets();
        KerbCleanupDomainCache(v25);
        KerbFreeGlobalKdcProxyClientCertContext(LogonSession);
      }
      v10 = KerbPurgePrimaryCredentialsTickets((struct _KERB_LOGON_SESSION *)((char *)LogonSession + 120), 0, 0, 0);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)LogonSession + 24));
      for ( i = (_QWORD *)*((_QWORD *)LogonSession + 1); i != (_QWORD *)((char *)LogonSession + 8); i = (_QWORD *)*i )
      {
        v27 = (struct _KERB_PRIMARY_CREDENTIAL *)i[8];
        if ( v27 )
          v10 = KerbPurgePrimaryCredentialsTickets(v27, 0, 0, 0);
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)LogonSession + 24));
      KerbPurgeS4U2ProxyCache(LogonSession);
      goto LABEL_111;
    }
    if ( String2->Length || (v28 = 0, *((_WORD *)v12 + 16)) )
      v28 = 1;
    LOBYTE(IsMember) = v28;
    if ( *((_WORD *)v12 + 24) || (v29 = 0, *((_WORD *)v12 + 32)) )
      v29 = 1;
    v30 = 0;
    if ( !v28
      || (v31 = (const UNICODE_STRING *)(v12 + 8),
          RtlEqualUnicodeString((PCUNICODE_STRING)((char *)LogonSession + 120), String2, 1u))
      && RtlEqualUnicodeString((PCUNICODE_STRING)((char *)LogonSession + 136), v39, 1u) )
    {
      if ( v29 )
      {
        v32 = (struct _UNICODE_STRING *)(v12 + 12);
        v33 = (struct _UNICODE_STRING *)(v12 + 16);
      }
      else
      {
        v32 = 0;
        v33 = 0;
      }
      v34 = KerbPurgePrimaryCredentialsTickets((struct _KERB_LOGON_SESSION *)((char *)LogonSession + 120), v32, v33, 0);
      v10 = v34;
      if ( v34 < 0 )
      {
        if ( v34 != -1073741772 )
          goto LABEL_111;
      }
      else
      {
        v30 = 1;
      }
      v31 = (const UNICODE_STRING *)(v12 + 8);
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)LogonSession + 24));
    v35 = (_QWORD *)*((_QWORD *)LogonSession + 1);
    if ( v35 == (_QWORD *)((char *)LogonSession + 8) )
    {
LABEL_110:
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)LogonSession + 24));
      v10 = v30 == 0 ? 0xC0000034 : 0;
LABEL_111:
      KerbDereferenceLogonSession(LogonSession);
      goto LABEL_10;
    }
    while ( 1 )
    {
      v36 = (UNICODE_STRING *)v35[8];
      if ( !v36 )
        goto LABEL_108;
      if ( (_BYTE)IsMember )
      {
        if ( !RtlEqualUnicodeString(v36, String2, 1u)
          || !RtlEqualUnicodeString((PCUNICODE_STRING)(v35[8] + 16LL), v31, 1u) )
        {
          goto LABEL_108;
        }
        v36 = (UNICODE_STRING *)v35[8];
      }
      if ( v29 )
      {
        v37 = v41;
        v38 = v42;
      }
      else
      {
        v37 = 0;
        v38 = 0;
      }
      v10 = KerbPurgePrimaryCredentialsTickets((struct _KERB_PRIMARY_CREDENTIAL *)v36, v37, v38, 0);
      if ( v10 < 0 )
      {
        if ( v10 != -1073741772 )
        {
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)LogonSession + 24));
          goto LABEL_111;
        }
      }
      else
      {
        v30 = 1;
      }
LABEL_108:
      v35 = (_QWORD *)*v35;
      if ( v35 == (_QWORD *)((char *)LogonSession + 8) )
        goto LABEL_110;
      v31 = v39;
    }
  }
  v10 = -1073741595;
LABEL_10:
  *a5 = 0;
  *a6 = 0;
  *a7 = v10;
  return 0;
}

```

## disassembly

```asm
0x1800a3040  push    rbp
0x1800a3042  push    rbx
0x1800a3043  push    rsi
0x1800a3044  push    rdi
0x1800a3045  push    r12
0x1800a3047  push    r13
0x1800a3049  push    r14
0x1800a304b  push    r15
0x1800a304d  lea     rbp, [rsp-8]
0x1800a3052  sub     rsp, 108h
0x1800a3059  xorps   xmm0, xmm0
0x1800a305c  mov     r14d, r9d
0x1800a305f  mov     rbx, rdx
0x1800a3062  lea     rcx, [rsp+140h+var_F0]; void *
0x1800a3067  xor     edx, edx; Val
0x1800a3069  mov     rsi, r8
0x1800a306c  movups  xmmword ptr [rbp+40h+var_80.LowPart], xmm0
0x1800a3070  movups  xmmword ptr [rbp+40h+TokenHandle], xmm0
0x1800a3074  lea     r8d, [rdx+70h]; Size
0x1800a3078  call    memset_0
0x1800a307d  lea     r9, aPurgingTicketC_0; "Purging ticket cache Ex\n"
0x1800a3084  mov     r8d, 13E8h
0x1800a308a  lea     rdx, aKerbpurgeticke_1; "KerbPurgeTicketEx"
0x1800a3091  mov     ecx, 3
0x1800a3096  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a309b  xor     eax, eax
0x1800a309d  lea     rcx, [rbp+40h+var_60]
0x1800a30a1  mov     [rbp+40h+var_50], rax
0x1800a30a5  xorps   xmm0, xmm0
0x1800a30a8  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800a30af  movups  [rbp+40h+var_60], xmm0
0x1800a30b3  mov     rax, [rax+0C0h]
0x1800a30ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a30bf  xor     r10d, r10d
0x1800a30c2  test    al, al
0x1800a30c4  jnz     short loc_1800A30D0
0x1800a30c6  mov     ebx, 0C00000E5h
0x1800a30cb  jmp     loc_1800A31C1
0x1800a30d0  mov     ecx, dword ptr [rbp+40h+var_60+8]
0x1800a30d3  and     ecx, 40h
0x1800a30d6  mov     eax, ecx
0x1800a30d8  neg     eax
0x1800a30da  sbb     r8d, r8d
0x1800a30dd  and     r8d, 0FFFFFFE0h
0x1800a30e1  add     r8d, 70h ; 'p'
0x1800a30e5  cmp     r14d, r8d
0x1800a30e8  jb      loc_1800A31BC
0x1800a30ee  test    ecx, ecx
0x1800a30f0  jz      loc_1800A3199
0x1800a30f6  mov     eax, [rbx]
0x1800a30f8  lea     rdi, [rsp+140h+var_F0]
0x1800a30fd  mov     [rsp+140h+var_F0], eax
0x1800a3101  mov     rax, [rbx+4]
0x1800a3105  mov     [rsp+140h+var_EC], rax
0x1800a310a  mov     eax, [rbx+0Ch]
0x1800a310d  mov     [rsp+140h+var_E4], eax
0x1800a3111  movzx   eax, word ptr [rbx+10h]
0x1800a3115  mov     [rsp+140h+var_E0], ax
0x1800a311a  movzx   eax, word ptr [rbx+12h]
0x1800a311e  mov     [rsp+140h+var_DE], ax
0x1800a3123  mov     eax, [rbx+14h]
0x1800a3126  mov     [rsp+140h+var_D8], rax
0x1800a312b  movzx   eax, word ptr [rbx+18h]
0x1800a312f  mov     [rsp+140h+var_D0], ax
0x1800a3134  movzx   eax, word ptr [rbx+1Ah]
0x1800a3138  mov     [rsp+140h+var_CE], ax
0x1800a313d  mov     eax, [rbx+1Ch]
0x1800a3140  mov     [rsp+140h+var_C8], rax
0x1800a3145  movzx   eax, word ptr [rbx+20h]
0x1800a3149  mov     [rbp+40h+var_C0], ax
0x1800a314d  movzx   eax, word ptr [rbx+22h]
0x1800a3151  mov     [rbp+40h+var_BE], ax
0x1800a3155  mov     eax, [rbx+24h]
0x1800a3158  mov     [rbp+40h+var_B8], rax
0x1800a315c  movzx   eax, word ptr [rbx+28h]
0x1800a3160  mov     [rbp+40h+var_B0], ax
0x1800a3164  movzx   eax, word ptr [rbx+2Ah]
0x1800a3168  mov     [rbp+40h+var_AE], ax
0x1800a316c  mov     eax, [rbx+2Ch]
0x1800a316f  mov     [rbp+40h+var_A8], rax
0x1800a3173  mov     rax, [rbx+30h]
0x1800a3177  mov     [rbp+40h+var_A0], rax
0x1800a317b  mov     rax, [rbx+38h]
0x1800a317f  mov     [rbp+40h+var_98], rax
0x1800a3183  mov     rax, [rbx+40h]
0x1800a3187  mov     [rbp+40h+var_90], rax
0x1800a318b  mov     eax, [rbx+48h]
0x1800a318e  mov     [rbp+40h+var_88], eax
0x1800a3191  mov     eax, [rbx+4Ch]
0x1800a3194  mov     [rbp+40h+var_84], eax
0x1800a3197  jmp     short loc_1800A319C
0x1800a3199  mov     rdi, rbx
0x1800a319c  lea     rax, [rdi+10h]
0x1800a31a0  mov     r11d, 1
0x1800a31a6  mov     rcx, [rax+8]
0x1800a31aa  movzx   edx, word ptr [rax]
0x1800a31ad  mov     [rsp+140h+String2], rax
0x1800a31b2  test    rcx, rcx
0x1800a31b5  jnz     short loc_1800A31EE
0x1800a31b7  test    dx, dx
0x1800a31ba  jz      short loc_1800A322F
0x1800a31bc  mov     ebx, 0C000000Dh
0x1800a31c1  mov     rax, [rbp+40h+arg_20]
0x1800a31c5  mov     [rax], r10
0x1800a31c8  mov     rax, [rbp+40h+arg_28]
0x1800a31cc  mov     [rax], r10d
0x1800a31cf  mov     rax, [rbp+40h+arg_30]
0x1800a31d6  mov     [rax], ebx
0x1800a31d8  xor     eax, eax
0x1800a31da  add     rsp, 108h
0x1800a31e1  pop     r15
0x1800a31e3  pop     r14
0x1800a31e5  pop     r13
0x1800a31e7  pop     r12
0x1800a31e9  pop     rdi
0x1800a31ea  pop     rsi
0x1800a31eb  pop     rbx
0x1800a31ec  pop     rbp
0x1800a31ed  retn
0x1800a31ee  test    dx, dx
0x1800a31f1  jnz     short loc_1800A31F9
0x1800a31f3  mov     [rdi+18h], r10
0x1800a31f7  jmp     short loc_1800A322F
0x1800a31f9  cmp     rcx, rsi
0x1800a31fc  jb      short loc_1800A3203
0x1800a31fe  sub     rcx, rsi
0x1800a3201  jz      short loc_1800A31BC
0x1800a3203  cmp     rcx, r14
0x1800a3206  ja      short loc_1800A31BC
0x1800a3208  lea     rax, [rcx+rdx]
0x1800a320c  cmp     rax, r14
0x1800a320f  ja      short loc_1800A31BC
0x1800a3211  mov     eax, r8d
0x1800a3214  cmp     rcx, rax
0x1800a3217  jb      short loc_1800A31BC
0x1800a3219  test    r11b, cl
0x1800a321c  jnz     short loc_1800A31BC
0x1800a321e  mov     [rdi+12h], dx
0x1800a3222  lea     rax, [rcx+rbx]
0x1800a3226  mov     [rdi+18h], rax
0x1800a322a  test    r11b, dl
0x1800a322d  jnz     short loc_1800A31BC
0x1800a322f  lea     r13, [rdi+20h]
0x1800a3233  mov     rcx, [r13+8]
0x1800a3237  movzx   edx, word ptr [r13+0]
0x1800a323c  mov     [rsp+140h+var_110], r13
0x1800a3241  test    rcx, rcx
0x1800a3244  jnz     short loc_1800A3250
0x1800a3246  test    dx, dx
0x1800a3249  jz      short loc_1800A32A9
0x1800a324b  jmp     loc_1800A31BC
0x1800a3250  test    dx, dx
0x1800a3253  jnz     short loc_1800A325B
0x1800a3255  mov     [rdi+28h], r10
0x1800a3259  jmp     short loc_1800A32A9
0x1800a325b  cmp     rcx, rsi
0x1800a325e  jb      short loc_1800A3269
0x1800a3260  sub     rcx, rsi
0x1800a3263  jz      loc_1800A31BC
0x1800a3269  cmp     rcx, r14
0x1800a326c  ja      loc_1800A31BC
0x1800a3272  lea     rax, [rcx+rdx]
0x1800a3276  cmp     rax, r14
0x1800a3279  ja      loc_1800A31BC
0x1800a327f  mov     eax, r8d
0x1800a3282  cmp     rcx, rax
0x1800a3285  jb      loc_1800A31BC
0x1800a328b  test    r11b, cl
0x1800a328e  jnz     loc_1800A31BC
0x1800a3294  mov     [rdi+22h], dx
0x1800a3298  lea     rax, [rcx+rbx]
0x1800a329c  mov     [rdi+28h], rax
0x1800a32a0  test    r11b, dl
0x1800a32a3  jnz     loc_1800A31BC
0x1800a32a9  mov     rcx, [rdi+38h]
0x1800a32ad  lea     r12, [rdi+30h]
0x1800a32b1  movzx   edx, word ptr [r12]
0x1800a32b6  mov     [rsp+140h+var_100], r12
0x1800a32bb  test    rcx, rcx
0x1800a32be  jnz     short loc_1800A32CA
0x1800a32c0  test    dx, dx
0x1800a32c3  jz      short loc_1800A3323
0x1800a32c5  jmp     loc_1800A31BC
0x1800a32ca  test    dx, dx
0x1800a32cd  jnz     short loc_1800A32D5
0x1800a32cf  mov     [rdi+38h], r10
0x1800a32d3  jmp     short loc_1800A3323
0x1800a32d5  cmp     rcx, rsi
0x1800a32d8  jb      short loc_1800A32E3
0x1800a32da  sub     rcx, rsi
0x1800a32dd  jz      loc_1800A31BC
0x1800a32e3  cmp     rcx, r14
0x1800a32e6  ja      loc_1800A31BC
0x1800a32ec  lea     rax, [rcx+rdx]
0x1800a32f0  cmp     rax, r14
0x1800a32f3  ja      loc_1800A31BC
0x1800a32f9  mov     eax, r8d
0x1800a32fc  cmp     rcx, rax
0x1800a32ff  jb      loc_1800A31BC
0x1800a3305  test    r11b, cl
0x1800a3308  jnz     loc_1800A31BC
0x1800a330e  mov     [rdi+32h], dx
0x1800a3312  lea     rax, [rcx+rbx]
0x1800a3316  mov     [rdi+38h], rax
0x1800a331a  test    r11b, dl
0x1800a331d  jnz     loc_1800A31BC
0x1800a3323  mov     rcx, [rdi+48h]
0x1800a3327  lea     r15, [rdi+40h]
0x1800a332b  movzx   edx, word ptr [r15]
0x1800a332f  mov     [rsp+140h+var_F8], r15
0x1800a3334  test    rcx, rcx
0x1800a3337  jnz     short loc_1800A3343
0x1800a3339  test    dx, dx
0x1800a333c  jz      short loc_1800A339C
0x1800a333e  jmp     loc_1800A31BC
0x1800a3343  test    dx, dx
0x1800a3346  jnz     short loc_1800A334E
0x1800a3348  mov     [rdi+48h], r10
0x1800a334c  jmp     short loc_1800A339C
0x1800a334e  cmp     rcx, rsi
0x1800a3351  jb      short loc_1800A335C
0x1800a3353  sub     rcx, rsi
0x1800a3356  jz      loc_1800A31BC
0x1800a335c  cmp     rcx, r14
0x1800a335f  ja      loc_1800A31BC
0x1800a3365  lea     rax, [rcx+rdx]
0x1800a3369  cmp     rax, r14
0x1800a336c  ja      loc_1800A31BC
0x1800a3372  mov     eax, r8d
0x1800a3375  cmp     rcx, rax
0x1800a3378  jb      loc_1800A31BC
0x1800a337e  test    r11b, cl
0x1800a3381  jnz     loc_1800A31BC
0x1800a3387  mov     [rdi+42h], dx
0x1800a338b  lea     rax, [rcx+rbx]
0x1800a338f  mov     [rdi+48h], rax
0x1800a3393  test    r11b, dl
0x1800a3396  jnz     loc_1800A31BC
0x1800a339c  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800a33a3  lea     rcx, [rbp+40h+var_80]
0x1800a33a7  mov     rax, [rax+80h]
0x1800a33ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a33b3  xor     r10d, r10d
0x1800a33b6  mov     ebx, eax
0x1800a33b8  test    eax, eax
0x1800a33ba  js      loc_1800A31C1
0x1800a33c0  mov     eax, [rdi+8]
0x1800a33c3  lea     rbx, [rdi+4]
0x1800a33c7  or      eax, [rbx]
0x1800a33c9  jnz     short loc_1800A33F2
0x1800a33cb  lea     rbx, [rbp+40h+var_80]
0x1800a33cf  xor     edx, edx; unsigned __int8
0x1800a33d1  mov     rcx, rbx; struct _LUID *
0x1800a33d4  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x1800a33d9  xor     r10d, r10d
0x1800a33dc  mov     rsi, rax
0x1800a33df  test    rax, rax
0x1800a33e2  jnz     loc_1800A3470
0x1800a33e8  mov     ebx, 0C000005Fh
0x1800a33ed  jmp     loc_1800A31C1
0x1800a33f2  cmp     byte ptr [rbp+40h+TokenHandle], r10b
0x1800a33f6  jnz     short loc_1800A33CF
0x1800a33f8  mov     rcx, [rbp+40h+TokenHandle+8]; TokenHandle
0x1800a33fc  mov     [rbp+40h+IsMember], r10d
0x1800a3400  test    rcx, rcx
0x1800a3403  jnz     short loc_1800A340F
0x1800a3405  mov     ebx, 0C000009Ah
0x1800a340a  jmp     loc_1800A31C1
0x1800a340f  mov     rdx, cs:?KerbGlobalAliasAdminsSid@@3PEAXEA; SidToCheck
0x1800a3416  lea     r8, [rbp+40h+IsMember]; IsMember
0x1800a341a  call    cs:__imp_CheckTokenMembership
0x1800a3420  xor     r10d, r10d
0x1800a3423  test    eax, eax
0x1800a3425  jnz     short loc_1800A345C
0x1800a3427  call    cs:__imp_GetLastError
0x1800a342d  lea     r9, aKerbpurgeticke; "KerbPurgeTicketEx CheckTokenMembership "...
0x1800a3434  mov     r8d, 1462h
0x1800a343a  lea     rdx, aKerbpurgeticke_1; "KerbPurgeTicketEx"
0x1800a3441  mov     [rsp+140h+var_120], eax
0x1800a3445  mov     ecx, 1
0x1800a344a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a344f  mov     ebx, 0C000009Ah
0x1800a3454  xor     r10d, r10d
0x1800a3457  jmp     loc_1800A31C1
0x1800a345c  cmp     [rbp+40h+IsMember], r10d
0x1800a3460  jnz     loc_1800A33CF
0x1800a3466  mov     ebx, 0C0000061h
0x1800a346b  jmp     loc_1800A31C1
0x1800a3470  test    byte ptr [rdi+0Ch], 1
0x1800a3474  jz      loc_1800A3522
0x1800a347a  lea     r9, aPurgingAllTick; "Purging all tickets\n"
0x1800a3481  mov     r8d, 1488h
0x1800a3487  lea     rdx, aKerbpurgeticke_1; "KerbPurgeTicketEx"
0x1800a348e  mov     ecx, 3
0x1800a3493  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a3498  call    ?KerbCleanupSpnCache@@YAXXZ; KerbCleanupSpnCache(void)
0x1800a349d  and     dword ptr [rsi+210h], 0FFFFFFF7h
0x1800a34a4  cmp     dword ptr [rsi+40h], 3E7h
0x1800a34ab  jnz     short loc_1800A34C5
0x1800a34ad  cmp     dword ptr [rsi+44h], 0
  ... truncated ...
```
