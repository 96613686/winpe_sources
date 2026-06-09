# KerbAddCredmanCredToLogonSession(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_PRIMARY_CREDENTIAL * *,ulong,_KERB_CREDMAN_CRED * *)

- ea: `0x1800627b0`
- end: `0x180062d20`
- name: `?KerbAddCredmanCredToLogonSession@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAPEAU_KERB_PRIMARY_CREDENTIAL@@KPEAPEAU_KERB_CREDMAN_CRED@@@Z`
- size: `1392`
- prototype: `__int64 __usercall@<rax>(struct _KERB_LOGON_SESSION *@<rcx>, struct _KERB_CREDENTIAL *@<rdx>, struct _KERB_PRIMARY_CREDENTIAL **@<r8>, unsigned int@<r9d>, struct _KERB_CREDMAN_CRED **)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180062d28`
- `0x1800a3ed0`
- `0x1800c5640`

## callees

- `0x18000b300`
- `0x180012240`
- `0x180047f2c`
- `0x180058f14`
- `0x1800627b0`
- `0x18006517c`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800629e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062a00`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062a1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800629e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062a00`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062a1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180062abc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180062abc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062bc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062bc4`
- `ntdll!RtlEqualUnicodeString` at `0x180062823`
- `ntdll!RtlEqualUnicodeString` at `0x18006283f`
- `ntdll!RtlEqualUnicodeString` at `0x180062823`
- `ntdll!RtlEqualUnicodeString` at `0x18006283f`
- `ntdll!RtlEnterCriticalSection` at `0x1800627f2`
- `ntdll!RtlEnterCriticalSection` at `0x180062a2f`
- `ntdll!RtlEnterCriticalSection` at `0x180062bdf`
- `ntdll!RtlEnterCriticalSection` at `0x180062cb4`
- `ntdll!RtlEnterCriticalSection` at `0x180062cfd`
- `ntdll!RtlEnterCriticalSection` at `0x1800627f2`
- `ntdll!RtlEnterCriticalSection` at `0x180062a2f`
- `ntdll!RtlEnterCriticalSection` at `0x180062bdf`
- `ntdll!RtlEnterCriticalSection` at `0x180062cb4`
- `ntdll!RtlEnterCriticalSection` at `0x180062cfd`
- `ntdll!RtlLeaveCriticalSection` at `0x180062a46`
- `ntdll!RtlLeaveCriticalSection` at `0x180062a9c`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c04`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c74`
- `ntdll!RtlLeaveCriticalSection` at `0x180062a46`
- `ntdll!RtlLeaveCriticalSection` at `0x180062a9c`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c04`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c74`
- `CRYPT32!CertCompareCertificate` at `0x18006289a`
- `CRYPT32!CertCompareCertificate` at `0x18006289a`

## pseudocode

```c
__int64 __fastcall KerbAddCredmanCredToLogonSession(
        struct _KERB_LOGON_SESSION *a1,
        struct _KERB_CREDENTIAL *a2,
        const UNICODE_STRING **a3,
        int a4,
        struct _UNICODE_STRING **CriticalSection)
{
  char v8; // r15
  char v9; // bp
  char *v11; // r14
  UNICODE_STRING *v12; // rbx
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // r8
  PWSTR v16; // rax
  struct _UNICODE_STRING *v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rdx
  __int64 v20; // rcx
  int TicketGrantingTicket; // ebp
  const void *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  HLOCAL v27; // rax
  struct _RTL_CRITICAL_SECTION *v28; // rcx
  struct _UNICODE_STRING *v30; // rbx
  PWSTR v31; // rcx
  PWSTR v32; // rcx
  struct _UNICODE_STRING *v33; // rbx
  WCHAR *v34; // rax
  struct _UNICODE_STRING *v35; // rax
  __int64 v36; // rdx
  _QWORD *Buffer; // rcx
  __int64 v38; // rcx
  PRTL_CRITICAL_SECTION CriticalSectiona; // [rsp+C0h] [rbp+28h]

  v8 = 0;
  v9 = 0;
  *CriticalSection = 0;
  CriticalSectiona = (PRTL_CRITICAL_SECTION)((char *)a1 + 24);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
  v11 = (char *)a1 + 8;
  v12 = (UNICODE_STRING *)*((_QWORD *)a1 + 1);
  if ( v12 == (UNICODE_STRING *)((char *)a1 + 8) )
  {
LABEL_30:
    *CriticalSection = 0;
    if ( KerbGlobalPackageState == 1 )
    {
      v27 = (HLOCAL)((__int64 (__fastcall *)(__int64))LsaFunctions->AllocateLsaHeap)(72);
    }
    else
    {
      v27 = LocalAlloc(0, 0x48u);
      if ( v27 )
      {
        *(_OWORD *)v27 = 0;
        *((_OWORD *)v27 + 1) = 0;
        *((_OWORD *)v27 + 2) = 0;
        *((_OWORD *)v27 + 3) = 0;
        *((_QWORD *)v27 + 8) = 0;
        *CriticalSection = (struct _UNICODE_STRING *)v27;
        goto LABEL_39;
      }
    }
    *CriticalSection = (struct _UNICODE_STRING *)v27;
    if ( !v27 )
    {
      TicketGrantingTicket = -1073741670;
LABEL_34:
      v28 = CriticalSectiona;
      goto LABEL_35;
    }
LABEL_39:
    TicketGrantingTicket = KerbDuplicateStringEx((struct _UNICODE_STRING *)v27 + 2, *a3);
    if ( TicketGrantingTicket >= 0 )
    {
      TicketGrantingTicket = KerbDuplicateStringEx(*CriticalSection + 3, *a3 + 1);
      if ( TicketGrantingTicket >= 0 )
      {
        *(_QWORD *)&(*CriticalSection)[4].Length = *a3;
        *a3 = 0;
        LODWORD((*CriticalSection)[1].Buffer) |= a4;
        v33 = *CriticalSection;
        ++*(_DWORD *)&(*CriticalSection)[1].Length;
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
        v34 = (WCHAR *)*((_QWORD *)a1 + 2);
        if ( *(char **)v34 != v11 )
          goto LABEL_71;
        *(_QWORD *)&v33->Length = v11;
        v33->Buffer = v34;
        *(_QWORD *)v34 = v33;
        *((_QWORD *)a1 + 2) = v33;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
        v35 = *CriticalSection;
        v36 = *(_QWORD *)&(*CriticalSection)->Length;
        if ( v36 )
        {
          Buffer = v35->Buffer;
          if ( Buffer )
          {
            if ( *(struct _UNICODE_STRING **)(v36 + 8) != v35 )
              goto LABEL_71;
            if ( (struct _UNICODE_STRING *)*Buffer != v35 )
              goto LABEL_71;
            *Buffer = v36;
            *(_QWORD *)(v36 + 8) = Buffer;
            v38 = *(_QWORD *)v11;
            if ( *(char **)(*(_QWORD *)v11 + 8LL) != v11 )
              goto LABEL_71;
            *(_QWORD *)&v35->Length = v38;
            v35->Buffer = (PWSTR)v11;
            *(_QWORD *)(v38 + 8) = v35;
            *(_QWORD *)v11 = v35;
          }
        }
        ++*(_DWORD *)&v35[1].Length;
        goto LABEL_66;
      }
    }
    v30 = *CriticalSection;
    KerbFreePrimaryCredentials(*(struct _KERB_PRIMARY_CREDENTIAL **)&(*CriticalSection)[4].Length, 1);
    if ( v30 != (struct _UNICODE_STRING *)-48LL )
    {
      v31 = v30[3].Buffer;
      if ( v31 )
      {
        if ( KerbGlobalPackageState == 1 )
          ((void (*)(void))LsaFunctions->FreeLsaHeap)();
        else
          LocalFree(v31);
      }
      v30[3] = 0;
    }
    if ( v30 != (struct _UNICODE_STRING *)-32LL )
    {
      v32 = v30[2].Buffer;
      if ( v32 )
      {
        if ( KerbGlobalPackageState == 1 )
          ((void (*)(void))LsaFunctions->FreeLsaHeap)();
        else
          LocalFree(v32);
      }
      v30[2] = 0;
    }
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(struct _UNICODE_STRING *))LsaFunctions->FreeLsaHeap)(v30);
    else
      LocalFree(v30);
    *CriticalSection = 0;
    goto LABEL_34;
  }
  do
  {
    if ( v9 )
      goto LABEL_17;
    if ( RtlEqualUnicodeString(*a3, v12 + 2, 1u) && RtlEqualUnicodeString(*a3 + 1, v12 + 3, 1u) )
    {
      v13 = *(_QWORD *)&v12[4].Length;
      v14 = (__int64)(*a3)[25].Buffer & 1;
      if ( (*(_BYTE *)(v13 + 408) & 1) != 0 )
      {
        if ( !v14 )
          goto LABEL_15;
      }
      else if ( v14 )
      {
        goto LABEL_15;
      }
      v15 = *(_QWORD *)(v13 + 280);
      v16 = (*a3)[17].Buffer;
      if ( !v15 )
      {
        if ( v16 )
          goto LABEL_15;
        goto LABEL_14;
      }
      if ( v16
        && CertCompareCertificate(
             1u,
             *(PCERT_INFO *)(*((_QWORD *)v16 + 4) + 24LL),
             *(PCERT_INFO *)(*(_QWORD *)(v15 + 32) + 24LL)) )
      {
        v8 = 1;
LABEL_14:
        v9 = 1;
        *CriticalSection = v12;
      }
    }
LABEL_15:
    v12 = *(UNICODE_STRING **)&v12->Length;
  }
  while ( v12 != (UNICODE_STRING *)v11 );
  if ( !v9 )
    goto LABEL_30;
LABEL_17:
  v17 = *CriticalSection;
  v18 = *(_QWORD *)&(*CriticalSection)->Length;
  if ( v18 )
  {
    v19 = v17->Buffer;
    if ( v19 )
    {
      if ( *(struct _UNICODE_STRING **)(v18 + 8) == v17 && (struct _UNICODE_STRING *)*v19 == v17 )
      {
        *v19 = v18;
        *(_QWORD *)(v18 + 8) = v19;
        v20 = *(_QWORD *)v11;
        if ( *(char **)(*(_QWORD *)v11 + 8LL) == v11 )
        {
          *(_QWORD *)&v17->Length = v20;
          v17->Buffer = (PWSTR)v11;
          *(_QWORD *)(v20 + 8) = v17;
          *(_QWORD *)v11 = v17;
          goto LABEL_23;
        }
      }
LABEL_71:
      __fastfail(3u);
    }
  }
LABEL_23:
  ++*(_DWORD *)&v17[1].Length;
  TicketGrantingTicket = 0;
  v22 = (const void *)((unsigned int)*CriticalSection >> 16);
  if ( !*CriticalSection )
    v22 = 0;
  KerbTracerT::Log(8, "KerbAddCredmanCredToLogonSession", 1523, "credman found match %p\n", v22);
  if ( v8
    || (v23 = *(_QWORD *)&(*CriticalSection)[4].Length, (*(_BYTE *)(v23 + 408) & 1) != 0)
    || KerbCompareKeys(
         *(struct _KERB_STORED_CREDENTIAL **)(v23 + 144),
         *(struct _KERB_STORED_CREDENTIAL **)&(*a3)[9].Length) )
  {
    KerbFreePrimaryCredentials((struct _KERB_PRIMARY_CREDENTIAL *)*a3, 1);
    *a3 = 0;
  }
  else
  {
    KerbTracerT::Log(1, "KerbAddCredmanCredToLogonSession", 1545, "Changing credman cred password\n");
    KerbFreePrimaryCredentials(*(struct _KERB_PRIMARY_CREDENTIAL **)&(*CriticalSection)[4].Length, 0);
    KerbTransferPrimaryCredentials(
      *(struct _KERB_PRIMARY_CREDENTIAL **)&(*CriticalSection)[4].Length,
      (struct _KERB_PRIMARY_CREDENTIAL *)*a3);
    v24 = *(_QWORD *)&(*CriticalSection)[4].Length + 160LL;
    *(_QWORD *)(v24 + 8) = v24;
    *(_QWORD *)v24 = v24;
    GetSystemTimeAsFileTime((LPFILETIME)(v24 + 16));
    v25 = *(_QWORD *)&(*CriticalSection)[4].Length + 240LL;
    *(_QWORD *)(v25 + 8) = v25;
    *(_QWORD *)v25 = v25;
    GetSystemTimeAsFileTime((LPFILETIME)(v25 + 16));
    v26 = *(_QWORD *)&(*CriticalSection)[4].Length + 200LL;
    *(_QWORD *)(v26 + 8) = v26;
    *(_QWORD *)v26 = v26;
    GetSystemTimeAsFileTime((LPFILETIME)(v26 + 16));
    *a3 = 0;
    RtlEnterCriticalSection(&KerbGlobalCredentialsLock);
    LODWORD((*CriticalSection)[1].Buffer) &= ~0x80000000;
    RtlLeaveCriticalSection(&KerbGlobalCredentialsLock);
  }
LABEL_66:
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
  if ( SLODWORD((*CriticalSection)[1].Buffer) >= 0 )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
    TicketGrantingTicket = KerbGetTicketGrantingTicket(
                             a1,
                             a2,
                             (struct _KERB_CREDMAN_CRED *)*CriticalSection,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
    if ( TicketGrantingTicket < 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbAddCredmanCredToLogonSession",
        1647,
        "Failed to get TGT for credman cred  - %x\n",
        TicketGrantingTicket);
      if ( TicketGrantingTicket == -1073741730 )
        return (unsigned int)-2146893053;
      return (unsigned int)TicketGrantingTicket;
    }
    RtlEnterCriticalSection(&KerbGlobalCredentialsLock);
    LODWORD((*CriticalSection)[1].Buffer) |= 0x80800000;
    v28 = &KerbGlobalCredentialsLock;
LABEL_35:
    RtlLeaveCriticalSection(v28);
  }
  return (unsigned int)TicketGrantingTicket;
}

```

## disassembly

```asm
0x1800627b0  mov     [rsp+arg_8], rdx
0x1800627b5  push    rbx
0x1800627b6  push    rbp
0x1800627b7  push    rsi
0x1800627b8  push    rdi
0x1800627b9  push    r12
0x1800627bb  push    r13
0x1800627bd  push    r14
0x1800627bf  push    r15
0x1800627c1  sub     rsp, 58h
0x1800627c5  mov     r12d, r9d
0x1800627c8  mov     rsi, r8
0x1800627cb  mov     r13, rcx
0x1800627ce  xor     r15b, r15b
0x1800627d1  xor     bpl, bpl
0x1800627d4  mov     rdi, [rsp+98h+CriticalSection]
0x1800627dc  mov     qword ptr [rdi], 0
0x1800627e3  lea     rax, [rcx+18h]
0x1800627e7  mov     [rsp+98h+CriticalSection], rax
0x1800627ef  mov     rcx, rax; CriticalSection
0x1800627f2  call    cs:__imp_RtlEnterCriticalSection
0x1800627f8  lea     r14, [r13+8]
0x1800627fc  mov     rbx, [r14]
0x1800627ff  cmp     rbx, r14
0x180062802  jz      loc_180062A63
0x180062808  nop     dword ptr [rax+rax+00000000h]
0x180062810  test    bpl, bpl
0x180062813  jnz     loc_1800628C9
0x180062819  lea     rdx, [rbx+20h]; String2
0x18006281d  mov     r8b, 1; CaseInsensitive
0x180062820  mov     rcx, [rsi]; String1
0x180062823  call    cs:__imp_RtlEqualUnicodeString
0x180062829  test    al, al
0x18006282b  jz      loc_1800628B4
0x180062831  lea     rdx, [rbx+30h]; String2
0x180062835  mov     rcx, [rsi]
0x180062838  add     rcx, 10h; String1
0x18006283c  mov     r8b, 1; CaseInsensitive
0x18006283f  call    cs:__imp_RtlEqualUnicodeString
0x180062845  test    al, al
0x180062847  jz      short loc_1800628B4
0x180062849  mov     r8, [rbx+40h]
0x18006284d  mov     rcx, [rsi]
0x180062850  mov     eax, [rcx+198h]
0x180062856  and     eax, 1
0x180062859  test    byte ptr [r8+198h], 1
0x180062861  jz      short loc_180062869
0x180062863  test    eax, eax
0x180062865  jz      short loc_1800628B4
0x180062867  jmp     short loc_18006286D
0x180062869  test    eax, eax
0x18006286b  jnz     short loc_1800628B4
0x18006286d  mov     r8, [r8+118h]
0x180062874  mov     rax, [rcx+118h]
0x18006287b  test    r8, r8
0x18006287e  jz      short loc_1800628A9
0x180062880  test    rax, rax
0x180062883  jz      short loc_1800628B4
0x180062885  mov     r8, [r8+20h]
0x180062889  mov     rdx, [rax+20h]
0x18006288d  mov     r8, [r8+18h]; pCertId2
0x180062891  mov     rdx, [rdx+18h]; pCertId1
0x180062895  mov     ecx, 1; dwCertEncodingType
0x18006289a  call    cs:__imp_CertCompareCertificate
0x1800628a0  test    eax, eax
0x1800628a2  jz      short loc_1800628B4
0x1800628a4  mov     r15b, 1
0x1800628a7  jmp     short loc_1800628AE
0x1800628a9  test    rax, rax
0x1800628ac  jnz     short loc_1800628B4
0x1800628ae  mov     bpl, 1
0x1800628b1  mov     [rdi], rbx
0x1800628b4  mov     rbx, [rbx]
0x1800628b7  cmp     rbx, r14
0x1800628ba  jnz     loc_180062810
0x1800628c0  test    bpl, bpl
0x1800628c3  jz      loc_180062A63
0x1800628c9  mov     rax, [rdi]
0x1800628cc  mov     rcx, [rax]
0x1800628cf  test    rcx, rcx
0x1800628d2  jz      short loc_180062912
0x1800628d4  mov     rdx, [rax+8]
0x1800628d8  test    rdx, rdx
0x1800628db  jz      short loc_180062912
0x1800628dd  cmp     [rcx+8], rax
0x1800628e1  jnz     loc_180062D19
0x1800628e7  cmp     [rdx], rax
0x1800628ea  jnz     loc_180062D19
0x1800628f0  mov     [rdx], rcx
0x1800628f3  mov     [rcx+8], rdx
0x1800628f7  mov     rcx, [r14]
0x1800628fa  cmp     [rcx+8], r14
0x1800628fe  jnz     loc_180062D19
0x180062904  mov     [rax], rcx
0x180062907  mov     [rax+8], r14
0x18006290b  mov     [rcx+8], rax
0x18006290f  mov     [r14], rax
0x180062912  inc     dword ptr [rax+10h]
0x180062915  xor     r14d, r14d
0x180062918  mov     ebp, r14d
0x18006291b  mov     rdx, [rdi]
0x18006291e  mov     rax, rdx
0x180062921  shr     rax, 10h
0x180062925  movzx   ecx, ax
0x180062928  test    rdx, rdx
0x18006292b  cmovz   ecx, r14d
0x18006292f  mov     [rsp+98h+var_78], rcx
0x180062934  lea     r9, aCredmanFoundMa; "credman found match %p\n"
0x18006293b  mov     r8d, 5F3h
0x180062941  lea     rdx, aKerbaddcredman; "KerbAddCredmanCredToLogonSession"
0x180062948  mov     ecx, 8
0x18006294d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180062952  test    r15b, r15b
0x180062955  jnz     loc_180062A51
0x18006295b  mov     rax, [rdi]
0x18006295e  mov     rcx, [rax+40h]
0x180062962  test    byte ptr [rcx+198h], 1
0x180062969  jnz     loc_180062A51
0x18006296f  mov     rdx, [rsi]
0x180062972  mov     rdx, [rdx+90h]; struct _KERB_STORED_CREDENTIAL *
0x180062979  mov     rcx, [rcx+90h]; struct _KERB_STORED_CREDENTIAL *
0x180062980  call    ?KerbCompareKeys@@YA_NPEAU_KERB_STORED_CREDENTIAL@@0@Z; KerbCompareKeys(_KERB_STORED_CREDENTIAL *,_KERB_STORED_CREDENTIAL *)
0x180062985  test    al, al
0x180062987  jnz     loc_180062A51
0x18006298d  lea     r9, aChangingCredma; "Changing credman cred password\n"
0x180062994  mov     r8d, 609h
0x18006299a  lea     rdx, aKerbaddcredman; "KerbAddCredmanCredToLogonSession"
0x1800629a1  mov     ecx, 1
0x1800629a6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800629ab  mov     rcx, [rdi]
0x1800629ae  xor     edx, edx; unsigned __int8
0x1800629b0  mov     rcx, [rcx+40h]; this
0x1800629b4  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x1800629b9  mov     rcx, [rdi]
0x1800629bc  mov     rdx, [rsi]; struct _KERB_PRIMARY_CREDENTIAL *
0x1800629bf  mov     rcx, [rcx+40h]; this
0x1800629c3  call    ?KerbTransferPrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@0@Z; KerbTransferPrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,_KERB_PRIMARY_CREDENTIAL *)
0x1800629c8  mov     rax, [rdi]
0x1800629cb  mov     rcx, [rax+40h]
0x1800629cf  add     rcx, 0A0h
0x1800629d6  mov     [rcx+8], rcx
0x1800629da  mov     [rcx], rcx
0x1800629dd  add     rcx, 10h; lpSystemTimeAsFileTime
0x1800629e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800629e7  mov     rax, [rdi]
0x1800629ea  mov     rcx, [rax+40h]
0x1800629ee  add     rcx, 0F0h
0x1800629f5  mov     [rcx+8], rcx
0x1800629f9  mov     [rcx], rcx
0x1800629fc  add     rcx, 10h; lpSystemTimeAsFileTime
0x180062a00  call    cs:__imp_GetSystemTimeAsFileTime
0x180062a06  mov     rax, [rdi]
0x180062a09  mov     rcx, [rax+40h]
0x180062a0d  add     rcx, 0C8h
0x180062a14  mov     [rcx+8], rcx
0x180062a18  mov     [rcx], rcx
0x180062a1b  add     rcx, 10h; lpSystemTimeAsFileTime
0x180062a1f  call    cs:__imp_GetSystemTimeAsFileTime
0x180062a25  mov     [rsi], r14
0x180062a28  lea     rcx, ?KerbGlobalCredentialsLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180062a2f  call    cs:__imp_RtlEnterCriticalSection
0x180062a35  mov     rax, [rdi]
0x180062a38  and     dword ptr [rax+18h], 7FFFFFFFh
0x180062a3f  lea     rcx, ?KerbGlobalCredentialsLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180062a46  call    cs:__imp_RtlLeaveCriticalSection
0x180062a4c  jmp     loc_180062C59
0x180062a51  mov     dl, 1; unsigned __int8
0x180062a53  mov     rcx, [rsi]; this
0x180062a56  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x180062a5b  mov     [rsi], r14
0x180062a5e  jmp     loc_180062C59
0x180062a63  xor     r15d, r15d
0x180062a66  mov     [rdi], r15
0x180062a69  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180062a70  jnz     short loc_180062AB5
0x180062a72  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180062a79  mov     ecx, 48h ; 'H'
0x180062a7e  mov     rax, [rax+28h]
0x180062a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a87  mov     [rdi], rax
0x180062a8a  test    rax, rax
0x180062a8d  jnz     short loc_180062AE2
0x180062a8f  mov     ebp, 0C000009Ah
0x180062a94  mov     rcx, [rsp+98h+CriticalSection]; CriticalSection
0x180062a9c  call    cs:__imp_RtlLeaveCriticalSection
0x180062aa2  mov     eax, ebp
0x180062aa4  add     rsp, 58h
0x180062aa8  pop     r15
0x180062aaa  pop     r14
0x180062aac  pop     r13
0x180062aae  pop     r12
0x180062ab0  pop     rdi
0x180062ab1  pop     rsi
0x180062ab2  pop     rbp
0x180062ab3  pop     rbx
0x180062ab4  retn
0x180062ab5  mov     edx, 48h ; 'H'; uBytes
0x180062aba  xor     ecx, ecx; uFlags
0x180062abc  call    cs:__imp_LocalAlloc
0x180062ac2  test    rax, rax
0x180062ac5  jz      short loc_180062A87
0x180062ac7  xorps   xmm0, xmm0
0x180062aca  xor     ecx, ecx
0x180062acc  movups  xmmword ptr [rax], xmm0
0x180062acf  movups  xmmword ptr [rax+10h], xmm0
0x180062ad3  movups  xmmword ptr [rax+20h], xmm0
0x180062ad7  movups  xmmword ptr [rax+30h], xmm0
0x180062adb  mov     [rax+40h], rcx
0x180062adf  mov     [rdi], rax
0x180062ae2  lea     rcx, [rax+20h]; struct _UNICODE_STRING *
0x180062ae6  mov     rdx, [rsi]; struct _UNICODE_STRING *
0x180062ae9  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180062aee  mov     ebp, eax
0x180062af0  test    eax, eax
0x180062af2  js      short loc_180062B26
0x180062af4  mov     rdx, [rsi]
0x180062af7  add     rdx, 10h; struct _UNICODE_STRING *
0x180062afb  mov     rcx, [rdi]
0x180062afe  add     rcx, 30h ; '0'; struct _UNICODE_STRING *
0x180062b02  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180062b07  mov     ebp, eax
0x180062b09  test    eax, eax
0x180062b0b  js      short loc_180062B26
0x180062b0d  mov     rcx, [rdi]
0x180062b10  mov     rax, [rsi]
0x180062b13  mov     [rcx+40h], rax
0x180062b17  mov     [rsi], r15
0x180062b1a  mov     rax, [rdi]
0x180062b1d  or      [rax+18h], r12d
0x180062b21  jmp     loc_180062BD5
0x180062b26  mov     rbx, [rdi]
0x180062b29  mov     dl, 1; unsigned __int8
0x180062b2b  mov     rcx, [rbx+40h]; this
0x180062b2f  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x180062b34  lea     rsi, [rbx+30h]
0x180062b38  test    rsi, rsi
0x180062b3b  jz      short loc_180062B6D
0x180062b3d  mov     rcx, [rsi+8]; hMem
0x180062b41  test    rcx, rcx
0x180062b44  jz      short loc_180062B67
0x180062b46  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180062b4d  jnz     short loc_180062B61
0x180062b4f  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180062b56  mov     rax, [rax+30h]
0x180062b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b5f  jmp     short loc_180062B67
0x180062b61  call    cs:__imp_LocalFree
0x180062b67  xorps   xmm0, xmm0
0x180062b6a  movups  xmmword ptr [rsi], xmm0
0x180062b6d  lea     rsi, [rbx+20h]
0x180062b71  test    rsi, rsi
0x180062b74  jz      short loc_180062BA6
0x180062b76  mov     rcx, [rsi+8]; hMem
0x180062b7a  test    rcx, rcx
0x180062b7d  jz      short loc_180062BA0
0x180062b7f  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180062b86  jnz     short loc_180062B9A
0x180062b88  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180062b8f  mov     rax, [rax+30h]
0x180062b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b98  jmp     short loc_180062BA0
0x180062b9a  call    cs:__imp_LocalFree
0x180062ba0  xorps   xmm0, xmm0
0x180062ba3  movups  xmmword ptr [rsi], xmm0
0x180062ba6  mov     rcx, rbx; hMem
0x180062ba9  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180062bb0  jnz     short loc_180062BC4
0x180062bb2  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180062bb9  mov     rax, [rax+30h]
0x180062bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062bc2  jmp     short loc_180062BCA
0x180062bc4  call    cs:__imp_LocalFree
0x180062bca  mov     [rdi], r15
0x180062bcd  test    ebp, ebp
0x180062bcf  js      loc_180062A94
0x180062bd5  mov     rbx, [rdi]
0x180062bd8  inc     dword ptr [rbx+10h]
0x180062bdb  lea     rcx, [r14+10h]; CriticalSection
0x180062bdf  call    cs:__imp_RtlEnterCriticalSection
0x180062be5  mov     rax, [r14+8]
0x180062be9  cmp     [rax], r14
0x180062bec  jnz     loc_180062D19
0x180062bf2  mov     [rbx], r14
0x180062bf5  mov     [rbx+8], rax
0x180062bf9  mov     [rax], rbx
0x180062bfc  mov     [r14+8], rbx
0x180062c00  lea     rcx, [r14+10h]; CriticalSection
0x180062c04  call    cs:__imp_RtlLeaveCriticalSection
0x180062c0a  mov     rax, [rdi]
0x180062c0d  mov     rdx, [rax]
0x180062c10  test    rdx, rdx
0x180062c13  jz      short loc_180062C53
0x180062c15  mov     rcx, [rax+8]
0x180062c19  test    rcx, rcx
0x180062c1c  jz      short loc_180062C53
0x180062c1e  cmp     [rdx+8], rax
0x180062c22  jnz     loc_180062D19
0x180062c28  cmp     [rcx], rax
0x180062c2b  jnz     loc_180062D19
0x180062c31  mov     [rcx], rdx
  ... truncated ...
```
