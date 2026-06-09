# DsRolepCreateChildTrustObject

- ea: `0x18002139c`
- end: `0x1800217e9`
- name: `DsRolepCreateChildTrustObject`
- size: `1101`
- prototype: `__int64 __fastcall(void *, void *, void *, __int64, PCUNICODE_STRING String1, PTRUSTED_DOMAIN_AUTH_INFORMATION AuthenticationInformation, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021a70`

## callees

- `0x180016538`
- `0x180020dbc`
- `0x18002139c`
- `0x180021f68`
- `0x18002c012`

## import_xrefs

- `msvcrt!malloc` at `0x18002149b`
- `msvcrt!malloc` at `0x180021607`
- `msvcrt!malloc` at `0x180021657`
- `msvcrt!malloc` at `0x180021740`
- `msvcrt!malloc` at `0x18002149b`
- `msvcrt!malloc` at `0x180021607`
- `msvcrt!malloc` at `0x180021657`
- `msvcrt!malloc` at `0x180021740`
- `msvcrt!free` at `0x1800214dd`
- `msvcrt!free` at `0x180021649`
- `msvcrt!free` at `0x180021699`
- `msvcrt!free` at `0x180021784`
- `msvcrt!free` at `0x1800214dd`
- `msvcrt!free` at `0x180021649`
- `msvcrt!free` at `0x180021699`
- `msvcrt!free` at `0x180021784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214ed`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180021485`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180021485`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002144e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002144e`
- `ntdll!RtlEqualUnicodeString` at `0x180021541`
- `ntdll!RtlEqualUnicodeString` at `0x180021541`
- `ntdll!RtlEqualSid` at `0x18002152d`
- `ntdll!RtlEqualSid` at `0x18002152d`
- `ntdll!RtlNtStatusToDosError` at `0x180021582`
- `ntdll!RtlNtStatusToDosError` at `0x180021593`
- `ntdll!RtlNtStatusToDosError` at `0x18002178c`
- `ntdll!RtlNtStatusToDosError` at `0x18002179d`
- `ntdll!RtlNtStatusToDosError` at `0x180021582`
- `ntdll!RtlNtStatusToDosError` at `0x180021593`
- `ntdll!RtlNtStatusToDosError` at `0x18002178c`
- `ntdll!RtlNtStatusToDosError` at `0x18002179d`
- `ADVAPI32!LsaQueryTrustedDomainInfoByName` at `0x180021478`
- `ADVAPI32!LsaQueryTrustedDomainInfoByName` at `0x180021478`
- `ADVAPI32!LsaCreateTrustedDomainEx` at `0x1800216ef`
- `ADVAPI32!LsaCreateTrustedDomainEx` at `0x1800216ef`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800217c9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800217c9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180021573`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180021573`

## string_xrefs

- `0x1800214f3`: `Failed to impersonate caller, error %lu\n`
- `0x1800214cb`: `Failed to read trust info from parent for %ws: 0x%lx\n`
- `0x1800216ff`: `Child domain trust object already exists on child\n`
- `0x180021775`: `Child LsaCreateTrustedDomainEx on %ws failed with 0x%lx\n`

## pseudocode

```c
__int64 __fastcall DsRolepCreateChildTrustObject(
        void *a1,
        void *a2,
        void *a3,
        __int64 a4,
        PCUNICODE_STRING String1,
        PTRUSTED_DOMAIN_AUTH_INFORMATION AuthenticationInformation,
        char a7)
{
  USHORT v8; // ax
  void *v9; // r14
  int v11; // r14d
  PCUNICODE_STRING v12; // rbx
  PCUNICODE_STRING v13; // rsi
  int v14; // edi
  __int64 Length; // r13
  _WORD *v16; // rax
  _WORD *v17; // r14
  DWORD LastError; // eax
  void *v19; // rcx
  void *v20; // rdx
  ULONG v21; // eax
  __int64 v22; // rbx
  ULONG v23; // eax
  PWSTR v24; // rdx
  unsigned __int64 v25; // rcx
  _WORD *v26; // rax
  _WORD *v27; // rbx
  _WORD *v28; // rax
  _WORD *v29; // rbx
  unsigned int v30; // esi
  _WORD *v31; // rax
  _WORD *v32; // rbx
  __int64 v33; // rbx
  ULONG v34; // eax
  PVOID ObjectHandle; // [rsp+30h] [rbp-40h] BYREF
  struct _TRUSTED_DOMAIN_INFORMATION_EX Src; // [rsp+38h] [rbp-38h] BYREF
  PVOID Buffer; // [rsp+C8h] [rbp+58h] BYREF

  Buffer = 0;
  *(_QWORD *)&Src.TrustAttributes = 0;
  v8 = *(_WORD *)(a4 + 16);
  v9 = a3;
  memset(&Src, 0, 32);
  Src.Name.Length = v8;
  *(_DWORD *)&Src.Name.MaximumLength = *(_DWORD *)(a4 + 18);
  *(&Src.Name.MaximumLength + 2) = *(_WORD *)(a4 + 22);
  Src.Name.Buffer = *(PWSTR *)(a4 + 24);
  Src.FlatName = *(LSA_UNICODE_STRING *)a4;
  *(_OWORD *)&Src.Sid = *(unsigned __int64 *)(a4 + 64);
  ObjectHandle = 0;
  Src.TrustAttributes = 32;
  if ( (a7 & 1) == 0 )
  {
    v14 = 0;
    *(_QWORD *)&Src.TrustDirection = 0x200000003LL;
    v24 = String1[1].Buffer;
    v25 = ((unsigned __int64)String1[1].Length - 1) >> 1;
    if ( v24[v25] == 46 )
      v24[v25] = 0;
    goto LABEL_28;
  }
  v11 = 0;
  if ( a1 )
  {
    if ( !ImpersonateLoggedOnUser(a1) )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(4, "Failed to impersonate caller, error %lu\n", LastError);
      v12 = String1;
      v14 = -1073741790;
      v13 = String1 + 1;
LABEL_8:
      Length = v13->Length;
      v16 = malloc(Length + 2);
      v17 = v16;
      if ( v16 )
      {
        memcpy_0(v16, v12[1].Buffer, (unsigned int)Length);
        v17[(unsigned __int64)v13->Length >> 1] = 0;
        DsRolepLogPrintRoutine(4, "Failed to read trust info from parent for %ws: 0x%lx\n", v17, (unsigned int)v14);
        free(v17);
      }
      goto LABEL_22;
    }
    v11 = 1;
  }
  v12 = String1;
  v13 = String1 + 1;
  v14 = LsaQueryTrustedDomainInfoByName(a2, (PLSA_UNICODE_STRING)&String1[1], TrustedDomainInformationEx, &Buffer);
  if ( v11 )
    RevertToSelf();
  if ( v14 < 0 )
    goto LABEL_8;
  v19 = *(void **)&v12[4].Length;
  if ( v19
    && (v20 = (void *)*((_QWORD *)Buffer + 4)) != 0
    && RtlEqualSid(v19, v20)
    && !RtlEqualUnicodeString(v12, (PCUNICODE_STRING)Buffer, 1u) )
  {
    v21 = 0;
    *(_QWORD *)&Src.TrustDirection = 0;
    if ( (*((_BYTE *)Buffer + 40) & 1) != 0 )
      v21 = 2;
    Src.TrustDirection = v21;
    if ( (*((_BYTE *)Buffer + 40) & 2) != 0 )
      Src.TrustDirection = v21 | 1;
    Src.TrustType = *((_DWORD *)Buffer + 11);
    LsaFreeMemory(Buffer);
  }
  else
  {
    v14 = -1073741413;
  }
LABEL_22:
  if ( RtlNtStatusToDosError(v14) )
  {
    v22 = *(_QWORD *)(a4 + 24);
    v23 = RtlNtStatusToDosError(v14);
    DsRolepSetFailureMessage(v23, 3221254685LL, v22, 0, 0);
  }
  v9 = a3;
  if ( v14 >= 0 )
  {
LABEL_28:
    DsRolepLogPrintRoutine(4, "Creating trusted domain object on child\n");
    v26 = malloc(Src.Name.Length + 2LL);
    v27 = v26;
    if ( v26 )
    {
      memcpy_0(v26, Src.Name.Buffer, Src.Name.Length);
      v27[(unsigned __int64)Src.Name.Length >> 1] = 0;
      DsRolepLogPrintRoutine(4, "\tDnsDomain: %ws\n", v27, (unsigned int)v14);
      free(v27);
    }
    v28 = malloc(Src.FlatName.Length + 2LL);
    v29 = v28;
    if ( v28 )
    {
      memcpy_0(v28, Src.FlatName.Buffer, Src.FlatName.Length);
      v29[(unsigned __int64)Src.FlatName.Length >> 1] = 0;
      DsRolepLogPrintRoutine(4, "\tFlat name: %ws\n", v29, (unsigned int)v14);
      free(v29);
    }
    DsRolepLogPrintRoutine(4, "\tDirection: %lu\n", Src.TrustDirection);
    DsRolepLogPrintRoutine(4, "\tType: %lu\n", Src.TrustType);
    DsRolepLogPrintRoutine(4, "\tAttributes: 0x%lx\n", Src.TrustAttributes);
    v14 = LsaCreateTrustedDomainEx(v9, &Src, AuthenticationInformation, 0, &ObjectHandle);
  }
  if ( v14 == -1073741771 )
  {
    DsRolepLogPrintRoutine(4, "Child domain trust object already exists on child\n");
    v14 = DsRolepHandlePreExistingTrustObject(0, v9, &Src, 0, (__int64)&ObjectHandle);
  }
  if ( v14 >= 0 )
  {
    if ( ObjectHandle )
      LsaClose(ObjectHandle);
  }
  else
  {
    v30 = Src.Name.Length;
    v31 = malloc(Src.Name.Length + 2LL);
    v32 = v31;
    if ( v31 )
    {
      memcpy_0(v31, Src.Name.Buffer, v30);
      v32[(unsigned __int64)Src.Name.Length >> 1] = 0;
      DsRolepLogPrintRoutine(4, "Child LsaCreateTrustedDomainEx on %ws failed with 0x%lx\n", v32, (unsigned int)v14);
      free(v32);
    }
    if ( RtlNtStatusToDosError(v14) )
    {
      v33 = *(_QWORD *)(a4 + 24);
      v34 = RtlNtStatusToDosError(v14);
      DsRolepSetFailureMessage(v34, 3221254685LL, v33, 0, 0);
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002139c  mov     [rsp-38h+arg_0], rbx
0x1800213a1  mov     [rsp-38h+PolicyHandle], r8
0x1800213a6  push    rbp
0x1800213a7  push    rsi
0x1800213a8  push    rdi
0x1800213a9  push    r12
0x1800213ab  push    r13
0x1800213ad  push    r14
0x1800213af  push    r15
0x1800213b1  mov     rbp, rsp
0x1800213b4  sub     rsp, 70h
0x1800213b8  xor     eax, eax
0x1800213ba  mov     [rbp+Buffer], 0
0x1800213c2  test    [rbp+arg_30], 1
0x1800213c6  xorps   xmm0, xmm0
0x1800213c9  mov     [rbp+var_8], rax
0x1800213cd  mov     r12, r9
0x1800213d0  movzx   eax, word ptr [r9+10h]
0x1800213d5  mov     r14, r8
0x1800213d8  movups  xmmword ptr [rbp+Src], xmm0
0x1800213dc  mov     word ptr [rbp+Src], ax
0x1800213e0  mov     rdi, rdx
0x1800213e3  mov     eax, [r9+12h]
0x1800213e7  mov     r15d, 4
0x1800213ed  mov     dword ptr [rbp+Src+2], eax
0x1800213f0  movzx   eax, word ptr [r9+16h]
0x1800213f5  mov     word ptr [rbp+Src+6], ax
0x1800213f9  mov     rax, [r9+18h]
0x1800213fd  mov     [rbp+Src+8], rax
0x180021401  movzx   eax, word ptr [r9]
0x180021405  movups  xmmword ptr [rbp+var_28], xmm0
0x180021409  mov     word ptr [rbp+var_28], ax
0x18002140d  mov     eax, [r9+2]
0x180021411  mov     dword ptr [rbp+var_28+2], eax
0x180021414  movzx   eax, word ptr [r9+6]
0x180021419  mov     word ptr [rbp+var_28+6], ax
0x18002141d  mov     rax, [r9+8]
0x180021421  mov     [rbp+var_28+8], rax
0x180021425  mov     rax, [r9+40h]
0x180021429  movups  [rbp+var_18], xmm0
0x18002142d  mov     qword ptr [rbp+var_18], rax
0x180021431  mov     [rbp+ObjectHandle], 0
0x180021439  mov     dword ptr [rbp+var_8], 20h ; ' '
0x180021440  jz      loc_1800215C2
0x180021446  xor     r14d, r14d
0x180021449  test    rcx, rcx
0x18002144c  jz      short loc_180021460
0x18002144e  call    cs:__imp_ImpersonateLoggedOnUser
0x180021454  test    eax, eax
0x180021456  jz      loc_1800214ED
0x18002145c  lea     r14d, [r15-3]
0x180021460  mov     rbx, [rbp+String1]
0x180021464  lea     r9, [rbp+Buffer]; Buffer
0x180021468  mov     r8d, 6; InformationClass
0x18002146e  mov     rcx, rdi; PolicyHandle
0x180021471  lea     rsi, [rbx+10h]
0x180021475  mov     rdx, rsi; TrustedDomainName
0x180021478  call    cs:__imp_LsaQueryTrustedDomainInfoByName
0x18002147e  mov     edi, eax
0x180021480  test    r14d, r14d
0x180021483  jz      short loc_18002148B
0x180021485  call    cs:__imp_RevertToSelf
0x18002148b  test    edi, edi
0x18002148d  jns     loc_180021517
0x180021493  movzx   r13d, word ptr [rsi]
0x180021497  lea     rcx, [r13+2]; Size
0x18002149b  call    cs:__imp_malloc
0x1800214a1  mov     r14, rax
0x1800214a4  test    rax, rax
0x1800214a7  jz      short loc_1800214E3
0x1800214a9  mov     rdx, [rbx+18h]; Src
0x1800214ad  mov     r8d, r13d; Size
0x1800214b0  mov     rcx, rax; void *
0x1800214b3  call    memcpy_0
0x1800214b8  movzx   edx, word ptr [rsi]
0x1800214bb  xor     ecx, ecx
0x1800214bd  shr     rdx, 1
0x1800214c0  mov     r9d, edi
0x1800214c3  mov     r8, r14
0x1800214c6  mov     [r14+rdx*2], cx
0x1800214cb  lea     rdx, aFailedToReadTr; "Failed to read trust info from parent f"...
0x1800214d2  mov     ecx, r15d
0x1800214d5  call    DsRolepLogPrintRoutine
0x1800214da  mov     rcx, r14; Block
0x1800214dd  call    cs:__imp_free
0x1800214e3  test    edi, edi
0x1800214e5  js      loc_180021580
0x1800214eb  jmp     short loc_18002154B
0x1800214ed  call    cs:__imp_GetLastError
0x1800214f3  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x1800214fa  mov     ecx, r15d
0x1800214fd  mov     r8d, eax
0x180021500  call    DsRolepLogPrintRoutine
0x180021505  mov     rbx, [rbp+String1]
0x180021509  mov     edi, 0C0000022h
0x18002150e  lea     rsi, [rbx+10h]
0x180021512  jmp     loc_180021493
0x180021517  mov     rcx, [rbx+40h]; Sid1
0x18002151b  test    rcx, rcx
0x18002151e  jz      short loc_18002157B
0x180021520  mov     rax, [rbp+Buffer]
0x180021524  mov     rdx, [rax+20h]; Sid2
0x180021528  test    rdx, rdx
0x18002152b  jz      short loc_18002157B
0x18002152d  call    cs:__imp_RtlEqualSid
0x180021533  test    al, al
0x180021535  jz      short loc_18002157B
0x180021537  mov     rdx, [rbp+Buffer]; String2
0x18002153b  mov     r8b, 1; CaseInsensitive
0x18002153e  mov     rcx, rbx; String1
0x180021541  call    cs:__imp_RtlEqualUnicodeString
0x180021547  test    al, al
0x180021549  jnz     short loc_18002157B
0x18002154b  mov     rcx, [rbp+Buffer]; Buffer
0x18002154f  xor     eax, eax
0x180021551  mov     qword ptr [rbp+var_18+8], rax
0x180021555  test    byte ptr [rcx+28h], 1
0x180021559  lea     edx, [rax+2]
0x18002155c  cmovnz  eax, edx
0x18002155f  mov     dword ptr [rbp+var_18+8], eax
0x180021562  test    [rcx+28h], dl
0x180021565  jz      short loc_18002156D
0x180021567  or      eax, 1
0x18002156a  mov     dword ptr [rbp+var_18+8], eax
0x18002156d  mov     eax, [rcx+2Ch]
0x180021570  mov     dword ptr [rbp+var_18+0Ch], eax
0x180021573  call    cs:__imp_LsaFreeMemory
0x180021579  jmp     short loc_180021580
0x18002157b  mov     edi, 0C000019Bh
0x180021580  mov     ecx, edi; Status
0x180021582  call    cs:__imp_RtlNtStatusToDosError
0x180021588  test    eax, eax
0x18002158a  jz      short loc_1800215B4
0x18002158c  mov     rbx, [r12+18h]
0x180021591  mov     ecx, edi; Status
0x180021593  call    cs:__imp_RtlNtStatusToDosError
0x180021599  xor     r9d, r9d
0x18002159c  mov     [rsp+70h+TrustedDomainHandle], 0
0x1800215a5  mov     ecx, eax
0x1800215a7  mov     r8, rbx
0x1800215aa  mov     edx, 0C000721Dh
0x1800215af  call    DsRolepSetFailureMessage
0x1800215b4  mov     r14, [rbp+PolicyHandle]
0x1800215b8  test    edi, edi
0x1800215ba  js      loc_1800216F7
0x1800215c0  jmp     short loc_1800215F0
0x1800215c2  mov     rax, [rbp+String1]
0x1800215c6  xor     edi, edi
0x1800215c8  mov     dword ptr [rbp+var_18+8], 3
0x1800215cf  movzx   ecx, word ptr [rax+10h]
0x1800215d3  lea     edx, [rdi+2]
0x1800215d6  dec     rcx
0x1800215d9  mov     dword ptr [rbp+var_18+0Ch], edx
0x1800215dc  mov     rdx, [rax+18h]
0x1800215e0  shr     rcx, 1
0x1800215e3  cmp     word ptr [rdx+rcx*2], 2Eh ; '.'
0x1800215e8  jnz     short loc_1800215F0
0x1800215ea  xor     eax, eax
0x1800215ec  mov     [rdx+rcx*2], ax
0x1800215f0  lea     rdx, aCreatingTruste; "Creating trusted domain object on child"...
0x1800215f7  mov     ecx, r15d
0x1800215fa  call    DsRolepLogPrintRoutine
0x1800215ff  movzx   esi, word ptr [rbp+Src]
0x180021603  lea     rcx, [rsi+2]; Size
0x180021607  call    cs:__imp_malloc
0x18002160d  mov     rbx, rax
0x180021610  test    rax, rax
0x180021613  jz      short loc_18002164F
0x180021615  mov     rdx, [rbp+Src+8]; Src
0x180021619  mov     r8d, esi; Size
0x18002161c  mov     rcx, rax; void *
0x18002161f  call    memcpy_0
0x180021624  movzx   edx, word ptr [rbp+Src]
0x180021628  xor     ecx, ecx
0x18002162a  shr     rdx, 1
0x18002162d  mov     r9d, edi
0x180021630  mov     r8, rbx
0x180021633  mov     [rbx+rdx*2], cx
0x180021637  lea     rdx, aDnsdomainWs; "\tDnsDomain: %ws\n"
0x18002163e  mov     ecx, r15d
0x180021641  call    DsRolepLogPrintRoutine
0x180021646  mov     rcx, rbx; Block
0x180021649  call    cs:__imp_free
0x18002164f  movzx   esi, word ptr [rbp+var_28]
0x180021653  lea     rcx, [rsi+2]; Size
0x180021657  call    cs:__imp_malloc
0x18002165d  mov     rbx, rax
0x180021660  test    rax, rax
0x180021663  jz      short loc_18002169F
0x180021665  mov     rdx, [rbp+var_28+8]; Src
0x180021669  mov     r8d, esi; Size
0x18002166c  mov     rcx, rax; void *
0x18002166f  call    memcpy_0
0x180021674  movzx   edx, word ptr [rbp+var_28]
0x180021678  xor     ecx, ecx
0x18002167a  shr     rdx, 1
0x18002167d  mov     r9d, edi
0x180021680  mov     r8, rbx
0x180021683  mov     [rbx+rdx*2], cx
0x180021687  lea     rdx, aFlatNameWs; "\tFlat name: %ws\n"
0x18002168e  mov     ecx, r15d
0x180021691  call    DsRolepLogPrintRoutine
0x180021696  mov     rcx, rbx; Block
0x180021699  call    cs:__imp_free
0x18002169f  mov     r8d, dword ptr [rbp+var_18+8]
0x1800216a3  lea     rdx, aDirectionLu; "\tDirection: %lu\n"
0x1800216aa  mov     ecx, r15d
0x1800216ad  call    DsRolepLogPrintRoutine
0x1800216b2  mov     r8d, dword ptr [rbp+var_18+0Ch]
0x1800216b6  lea     rdx, aTypeLu; "\tType: %lu\n"
0x1800216bd  mov     ecx, r15d
0x1800216c0  call    DsRolepLogPrintRoutine
0x1800216c5  mov     r8d, dword ptr [rbp+var_8]
0x1800216c9  lea     rdx, aAttributes0xLx; "\tAttributes: 0x%lx\n"
0x1800216d0  mov     ecx, r15d
0x1800216d3  call    DsRolepLogPrintRoutine
0x1800216d8  mov     r8, [rbp+AuthenticationInformation]; AuthenticationInformation
0x1800216dc  lea     rax, [rbp+ObjectHandle]
0x1800216e0  xor     r9d, r9d; DesiredAccess
0x1800216e3  mov     [rsp+70h+TrustedDomainHandle], rax; TrustedDomainHandle
0x1800216e8  lea     rdx, [rbp+Src]; TrustedDomainInformation
0x1800216ec  mov     rcx, r14; PolicyHandle
0x1800216ef  call    cs:__imp_LsaCreateTrustedDomainEx
0x1800216f5  mov     edi, eax
0x1800216f7  cmp     edi, 0C0000035h
0x1800216fd  jnz     short loc_180021730
0x1800216ff  lea     rdx, aChildDomainTru; "Child domain trust object already exist"...
0x180021706  mov     ecx, r15d
0x180021709  call    DsRolepLogPrintRoutine
0x18002170e  mov     r9, [rbp+AuthenticationInformation]
0x180021712  lea     rax, [rbp+ObjectHandle]
0x180021716  mov     [rsp+70h+var_48], rax; __int64
0x18002171b  lea     r8, [rbp+Src]; TrustedDomainInformation
0x18002171f  mov     rdx, r14; PolicyHandle
0x180021722  mov     byte ptr [rsp+70h+TrustedDomainHandle], 0; char
0x180021727  xor     ecx, ecx; hToken
0x180021729  call    DsRolepHandlePreExistingTrustObject
0x18002172e  mov     edi, eax
0x180021730  test    edi, edi
0x180021732  jns     loc_1800217C0
0x180021738  movzx   esi, word ptr [rbp+Src]
0x18002173c  lea     rcx, [rsi+2]; Size
0x180021740  call    cs:__imp_malloc
0x180021746  mov     rbx, rax
0x180021749  test    rax, rax
0x18002174c  jz      short loc_18002178A
0x18002174e  mov     rdx, [rbp+Src+8]; Src
0x180021752  mov     r8d, esi; Size
0x180021755  mov     rcx, rax; void *
0x180021758  call    memcpy_0
0x18002175d  movzx   r8d, word ptr [rbp+Src]
0x180021762  xor     edx, edx
0x180021764  shr     r8, 1
0x180021767  mov     r9d, edi
0x18002176a  mov     ecx, r15d
0x18002176d  mov     [rbx+r8*2], dx
0x180021772  mov     r8, rbx
0x180021775  lea     rdx, aChildLsacreate; "Child LsaCreateTrustedDomainEx on %ws f"...
0x18002177c  call    DsRolepLogPrintRoutine
0x180021781  mov     rcx, rbx; Block
0x180021784  call    cs:__imp_free
0x18002178a  mov     ecx, edi; Status
0x18002178c  call    cs:__imp_RtlNtStatusToDosError
0x180021792  test    eax, eax
0x180021794  jz      short loc_1800217CF
0x180021796  mov     rbx, [r12+18h]
0x18002179b  mov     ecx, edi; Status
0x18002179d  call    cs:__imp_RtlNtStatusToDosError
0x1800217a3  xor     r9d, r9d
0x1800217a6  mov     [rsp+70h+TrustedDomainHandle], 0
0x1800217af  mov     ecx, eax
0x1800217b1  mov     r8, rbx
0x1800217b4  mov     edx, 0C000721Dh
0x1800217b9  call    DsRolepSetFailureMessage
0x1800217be  jmp     short loc_1800217CF
0x1800217c0  mov     rcx, [rbp+ObjectHandle]; ObjectHandle
0x1800217c4  test    rcx, rcx
0x1800217c7  jz      short loc_1800217CF
0x1800217c9  call    cs:__imp_LsaClose
0x1800217cf  mov     rbx, [rsp+70h+arg_0]
0x1800217d7  mov     eax, edi
0x1800217d9  add     rsp, 70h
0x1800217dd  pop     r15
0x1800217df  pop     r14
0x1800217e1  pop     r13
0x1800217e3  pop     r12
0x1800217e5  pop     rdi
0x1800217e6  pop     rsi
0x1800217e7  pop     rbp
0x1800217e8  retn
```
