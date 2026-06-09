# AllocateAndInitializeUserSid(ushort const *,void * *,ulong &)

- ea: `0x18023f13c`
- end: `0x18023f511`
- name: `?AllocateAndInitializeUserSid@@YAHPEBGPEAPEAXAEAK@Z`
- size: `981`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180242568`

## callees

- `0x180018ee0`
- `0x180027634`
- `0x18008c93c`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18023f13c`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!GetSidLengthRequired` at `0x18023f3e7`
- `ADVAPI32!GetSidLengthRequired` at `0x18023f3e7`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x18023f3d9`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x18023f3d9`
- `ADVAPI32!LookupAccountNameW` at `0x18023f3b0`
- `ADVAPI32!LookupAccountNameW` at `0x18023f46f`
- `ADVAPI32!LookupAccountNameW` at `0x18023f3b0`
- `ADVAPI32!LookupAccountNameW` at `0x18023f46f`
- `ADVAPI32!CopySid` at `0x18023f41c`
- `ADVAPI32!CopySid` at `0x18023f41c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18023f255`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18023f255`
- `ADVAPI32!GetLengthSid` at `0x18023f36c`
- `ADVAPI32!GetLengthSid` at `0x18023f36c`
- `ADVAPI32!FreeSid` at `0x18023f48c`
- `ADVAPI32!FreeSid` at `0x18023f48c`
- `KERNEL32!GetLastError` at `0x18023f3be`
- `KERNEL32!GetLastError` at `0x18023f3be`
- `KERNEL32!SetLastError` at `0x18023f431`
- `KERNEL32!SetLastError` at `0x18023f431`

## string_xrefs

- `0x18023f1f2`: `Using well known SID for System`
- `0x18023f2b0`: `Using well known SID for Administrators`
- `0x18023f31f`: `Using well known SID for Everyone`
- `0x18023f4a6`: `Finished allocating new user SID`

## pseudocode

```c
__int64 __fastcall AllocateAndInitializeUserSid(const unsigned __int16 *a1, void **a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  DWORD v7; // r9d
  BYTE v8; // dl
  DWORD v9; // r8d
  struct _SID_IDENTIFIER_AUTHORITY *p_pIdentifierAuthority; // rcx
  int v12; // r14d
  DWORD LastError; // esi
  bool v14; // cl
  UCHAR *SidSubAuthorityCount; // rax
  void *v16; // rax
  bool v17; // cl
  unsigned int pSid; // [rsp+50h] [rbp-B0h]
  void *v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+68h] [rbp-98h] BYREF
  PSID pSourceSid; // [rsp+70h] [rbp-90h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+78h] [rbp-88h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+7Ch] [rbp-84h] BYREF
  int v25; // [rsp+84h] [rbp-7Ch] BYREF
  __int16 v26; // [rsp+88h] [rbp-78h]
  _BYTE Sid[80]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+E0h] [rbp-20h] BYREF

  cchReferencedDomainName = 260;
  peUse = SidTypeUnknown;
  *a3 = 80;
  pSourceSid = Sid;
  MsiString::MsiString((MsiString *)&v20, a1);
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v6 = 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v20 + 200LL))(
         v20,
         1,
         L"SYSTEM") )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Using well known SID for System",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSid,
        v19);
    v7 = 0;
    v8 = 1;
    v9 = 18;
LABEL_5:
    p_pIdentifierAuthority = &pIdentifierAuthority;
LABEL_6:
    if ( !AllocateAndInitializeSid(p_pIdentifierAuthority, v8, v9, v7, 0, 0, 0, 0, 0, 0, &pSourceSid) )
    {
LABEL_7:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      return 0;
    }
    *a3 = GetLengthSid(pSourceSid);
    v12 = 1;
    goto LABEL_19;
  }
  if ( (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v20 + 200LL))(
         v20,
         1,
         L"Administrators") )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Using well known SID for Administrators",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSid,
        v19);
    v7 = 544;
    v9 = 32;
    v8 = 2;
    goto LABEL_5;
  }
  if ( (*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v20 + 200LL))(v20, 1, L"Everyone") )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Using well known SID for Everyone",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSid,
        v19);
    v7 = 0;
    v25 = 0;
    v9 = 0;
    v26 = 256;
    v8 = 1;
    p_pIdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v25;
    goto LABEL_6;
  }
  v12 = 0;
  StartImpersonating();
  v6 = LookupAccountNameW(0, a1, Sid, a3, ReferencedDomainName, &cchReferencedDomainName, &peUse);
  LastError = GetLastError();
  StopImpersonating(v14);
  if ( v6 )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(Sid);
    *a3 = GetSidLengthRequired(*SidSubAuthorityCount);
  }
  else if ( LastError != 122 )
  {
    SetLastError(LastError);
    goto LABEL_7;
  }
LABEL_19:
  v16 = operator new(*a3);
  *a2 = v16;
  cchReferencedDomainName = 260;
  if ( v6 )
  {
    CopySid(*a3, v16, pSourceSid);
  }
  else
  {
    StartImpersonating();
    v6 = LookupAccountNameW(0, a1, *a2, a3, ReferencedDomainName, &cchReferencedDomainName, &peUse);
    StopImpersonating(v17);
  }
  if ( v12 )
    FreeSid(pSourceSid);
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      "Finished allocating new user SID",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      pSid,
      v19);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return v6;
}

```

## disassembly

```asm
0x18023f13c  mov     [rsp-8+arg_18], rbx
0x18023f141  push    rbp
0x18023f142  push    rsi
0x18023f143  push    rdi
0x18023f144  push    r12
0x18023f146  push    r13
0x18023f148  push    r14
0x18023f14a  push    r15
0x18023f14c  lea     rbp, [rsp-200h]
0x18023f154  sub     rsp, 300h
0x18023f15b  mov     rax, cs:__security_cookie
0x18023f162  xor     rax, rsp
0x18023f165  mov     [rbp+230h+var_40], rax
0x18023f16c  mov     r15, rdx
0x18023f16f  mov     [rsp+330h+cchReferencedDomainName], 104h
0x18023f177  mov     rdx, rcx; unsigned __int16 *
0x18023f17a  mov     [rsp+330h+peUse], 8
0x18023f182  mov     r12, rcx
0x18023f185  mov     dword ptr [r8], 50h ; 'P'
0x18023f18c  lea     rax, [rbp+230h+Sid]
0x18023f190  mov     rdi, r8
0x18023f193  lea     rcx, [rsp+330h+var_2D0]; this
0x18023f198  mov     [rsp+330h+pSourceSid], rax
0x18023f19d  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18023f1a2  mov     rcx, [rsp+330h+var_2D0]
0x18023f1a7  lea     r8, aSystem; "SYSTEM"
0x18023f1ae  xor     r13d, r13d
0x18023f1b1  mov     word ptr [rbp+230h+pIdentifierAuthority.Value+4], 500h
0x18023f1b7  mov     dword ptr [rsp+330h+pIdentifierAuthority.Value], r13d
0x18023f1bc  mov     rax, [rcx]
0x18023f1bf  lea     ebx, [r13+1]
0x18023f1c3  mov     edx, ebx
0x18023f1c5  mov     rax, [rax+0C8h]
0x18023f1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023f1d1  lea     rsi, aNull_0; "(NULL)"
0x18023f1d8  lea     r14d, [r13+9]
0x18023f1dc  test    eax, eax
0x18023f1de  jz      loc_18023F281
0x18023f1e4  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18023f1eb  jz      short loc_18023F21F
0x18023f1ed  mov     qword ptr [rsp+330h+nSubAuthority7], rsi; char *
0x18023f1f2  lea     r9, aUsingWellKnown_0; "Using well known SID for System"
0x18023f1f9  mov     qword ptr [rsp+330h+nSubAuthority6], rsi; char *
0x18023f1fe  xor     edx, edx; unsigned __int16
0x18023f200  mov     qword ptr [rsp+330h+nSubAuthority5], rsi; char *
0x18023f205  xor     r8d, r8d; int
0x18023f208  mov     qword ptr [rsp+330h+nSubAuthority4], rsi; char *
0x18023f20d  mov     ecx, r14d; int
0x18023f210  mov     qword ptr [rsp+330h+nSubAuthority3], rsi; char *
0x18023f215  mov     qword ptr [rsp+330h+nSubAuthority2], rsi; char *
0x18023f21a  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023f21f  xor     r9d, r9d; nSubAuthority1
0x18023f222  mov     dl, bl; nSubAuthorityCount
0x18023f224  lea     r8d, [r9+12h]; nSubAuthority0
0x18023f228  lea     rcx, [rsp+330h+pIdentifierAuthority]; pIdentifierAuthority
0x18023f22d  lea     rax, [rsp+330h+pSourceSid]
0x18023f232  mov     [rsp+330h+pSid], rax; pSid
0x18023f237  mov     [rsp+330h+nSubAuthority7], r13d; nSubAuthority7
0x18023f23c  mov     [rsp+330h+nSubAuthority6], r13d; nSubAuthority6
0x18023f241  mov     [rsp+330h+nSubAuthority5], r13d; nSubAuthority5
0x18023f246  mov     [rsp+330h+nSubAuthority4], r13d; nSubAuthority4
0x18023f24b  mov     [rsp+330h+nSubAuthority3], r13d; nSubAuthority3
0x18023f250  mov     [rsp+330h+nSubAuthority2], r13d; nSubAuthority2
0x18023f255  call    cs:__imp_AllocateAndInitializeSid
0x18023f25c  nop     dword ptr [rax+rax+00h]
0x18023f261  test    eax, eax
0x18023f263  jnz     loc_18023F367
0x18023f269  mov     rcx, [rsp+330h+var_2D0]
0x18023f26e  mov     rax, [rcx]
0x18023f271  mov     rax, [rax+10h]
0x18023f275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023f27a  xor     eax, eax
0x18023f27c  jmp     loc_18023F4E6
0x18023f281  mov     rcx, [rsp+330h+var_2D0]
0x18023f286  lea     r8, aAdministrators; "Administrators"
0x18023f28d  mov     edx, ebx
0x18023f28f  mov     rax, [rcx]
0x18023f292  mov     rax, [rax+0C8h]
0x18023f299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023f29e  test    eax, eax
0x18023f2a0  jz      short loc_18023F2F0
0x18023f2a2  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18023f2a9  jz      short loc_18023F2DD
0x18023f2ab  mov     qword ptr [rsp+330h+nSubAuthority7], rsi; char *
0x18023f2b0  lea     r9, aUsingWellKnown_1; "Using well known SID for Administrators"
0x18023f2b7  mov     qword ptr [rsp+330h+nSubAuthority6], rsi; char *
0x18023f2bc  xor     edx, edx; unsigned __int16
0x18023f2be  mov     qword ptr [rsp+330h+nSubAuthority5], rsi; char *
0x18023f2c3  xor     r8d, r8d; int
0x18023f2c6  mov     qword ptr [rsp+330h+nSubAuthority4], rsi; char *
0x18023f2cb  mov     ecx, r14d; int
0x18023f2ce  mov     qword ptr [rsp+330h+nSubAuthority3], rsi; char *
0x18023f2d3  mov     qword ptr [rsp+330h+nSubAuthority2], rsi; char *
0x18023f2d8  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023f2dd  mov     r9d, 220h
0x18023f2e3  mov     r8d, 20h ; ' '
0x18023f2e9  mov     dl, 2
0x18023f2eb  jmp     loc_18023F228
0x18023f2f0  mov     rcx, [rsp+330h+var_2D0]
0x18023f2f5  lea     r8, aEveryone; "Everyone"
0x18023f2fc  mov     edx, ebx
0x18023f2fe  mov     rax, [rcx]
0x18023f301  mov     rax, [rax+0C8h]
0x18023f308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023f30d  test    eax, eax
0x18023f30f  jz      short loc_18023F37F
0x18023f311  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18023f318  jz      short loc_18023F34C
0x18023f31a  mov     qword ptr [rsp+330h+nSubAuthority7], rsi; char *
0x18023f31f  lea     r9, aUsingWellKnown; "Using well known SID for Everyone"
0x18023f326  mov     qword ptr [rsp+330h+nSubAuthority6], rsi; char *
0x18023f32b  xor     edx, edx; unsigned __int16
0x18023f32d  mov     qword ptr [rsp+330h+nSubAuthority5], rsi; char *
0x18023f332  xor     r8d, r8d; int
0x18023f335  mov     qword ptr [rsp+330h+nSubAuthority4], rsi; char *
0x18023f33a  mov     ecx, r14d; int
0x18023f33d  mov     qword ptr [rsp+330h+nSubAuthority3], rsi; char *
0x18023f342  mov     qword ptr [rsp+330h+nSubAuthority2], rsi; char *
0x18023f347  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023f34c  xor     r9d, r9d
0x18023f34f  mov     [rbp+230h+var_2AC], r13d
0x18023f353  xor     r8d, r8d
0x18023f356  mov     [rbp+230h+var_2A8], 100h
0x18023f35c  mov     dl, bl
0x18023f35e  lea     rcx, [rbp+230h+var_2AC]
0x18023f362  jmp     loc_18023F22D
0x18023f367  mov     rcx, [rsp+330h+pSourceSid]; pSid
0x18023f36c  call    cs:__imp_GetLengthSid
0x18023f373  nop     dword ptr [rax+rax+00h]
0x18023f378  mov     [rdi], eax
0x18023f37a  mov     r14d, ebx
0x18023f37d  jmp     short loc_18023F3FC
0x18023f37f  mov     r14d, r13d
0x18023f382  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18023f387  lea     rax, [rsp+330h+peUse]
0x18023f38c  mov     r9, rdi; cbSid
0x18023f38f  mov     qword ptr [rsp+330h+nSubAuthority4], rax; peUse
0x18023f394  lea     r8, [rbp+230h+Sid]; Sid
0x18023f398  lea     rax, [rsp+330h+cchReferencedDomainName]
0x18023f39d  mov     rdx, r12; lpAccountName
0x18023f3a0  mov     qword ptr [rsp+330h+nSubAuthority3], rax; cchReferencedDomainName
0x18023f3a5  xor     ecx, ecx; lpSystemName
0x18023f3a7  lea     rax, [rbp+230h+ReferencedDomainName]
0x18023f3ab  mov     qword ptr [rsp+330h+nSubAuthority2], rax; ReferencedDomainName
0x18023f3b0  call    cs:__imp_LookupAccountNameW
0x18023f3b7  nop     dword ptr [rax+rax+00h]
0x18023f3bc  mov     ebx, eax
0x18023f3be  call    cs:__imp_GetLastError
0x18023f3c5  nop     dword ptr [rax+rax+00h]
0x18023f3ca  mov     esi, eax
0x18023f3cc  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18023f3d1  test    ebx, ebx
0x18023f3d3  jz      short loc_18023F42A
0x18023f3d5  lea     rcx, [rbp+230h+Sid]; pSid
0x18023f3d9  call    cs:__imp_GetSidSubAuthorityCount
0x18023f3e0  nop     dword ptr [rax+rax+00h]
0x18023f3e5  mov     cl, [rax]; nSubAuthorityCount
0x18023f3e7  call    cs:__imp_GetSidLengthRequired
0x18023f3ee  nop     dword ptr [rax+rax+00h]
0x18023f3f3  mov     [rdi], eax
0x18023f3f5  lea     rsi, aNull_0; "(NULL)"
0x18023f3fc  mov     ecx, [rdi]; unsigned __int64
0x18023f3fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18023f403  mov     [r15], rax
0x18023f406  mov     [rsp+330h+cchReferencedDomainName], 104h
0x18023f40e  test    ebx, ebx
0x18023f410  jz      short loc_18023F442
0x18023f412  mov     r8, [rsp+330h+pSourceSid]; pSourceSid
0x18023f417  mov     rdx, rax; pDestinationSid
0x18023f41a  mov     ecx, [rdi]; nDestinationSidLength
0x18023f41c  call    cs:__imp_CopySid
0x18023f423  nop     dword ptr [rax+rax+00h]
0x18023f428  jmp     short loc_18023F482
0x18023f42a  cmp     esi, 7Ah ; 'z'
0x18023f42d  jz      short loc_18023F3F5
0x18023f42f  mov     ecx, esi; dwErrCode
0x18023f431  call    cs:__imp_SetLastError
0x18023f438  nop     dword ptr [rax+rax+00h]
0x18023f43d  jmp     loc_18023F269
0x18023f442  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18023f447  mov     r8, [r15]; Sid
0x18023f44a  lea     rax, [rsp+330h+peUse]
0x18023f44f  mov     qword ptr [rsp+330h+nSubAuthority4], rax; peUse
0x18023f454  mov     r9, rdi; cbSid
0x18023f457  lea     rax, [rsp+330h+cchReferencedDomainName]
0x18023f45c  mov     rdx, r12; lpAccountName
0x18023f45f  mov     qword ptr [rsp+330h+nSubAuthority3], rax; cchReferencedDomainName
0x18023f464  xor     ecx, ecx; lpSystemName
0x18023f466  lea     rax, [rbp+230h+ReferencedDomainName]
0x18023f46a  mov     qword ptr [rsp+330h+nSubAuthority2], rax; ReferencedDomainName
0x18023f46f  call    cs:__imp_LookupAccountNameW
0x18023f476  nop     dword ptr [rax+rax+00h]
0x18023f47b  mov     ebx, eax
0x18023f47d  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18023f482  test    r14d, r14d
0x18023f485  jz      short loc_18023F498
0x18023f487  mov     rcx, [rsp+330h+pSourceSid]; pSid
0x18023f48c  call    cs:__imp_FreeSid
0x18023f493  nop     dword ptr [rax+rax+00h]
0x18023f498  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18023f49f  jz      short loc_18023F4D3
0x18023f4a1  mov     qword ptr [rsp+330h+nSubAuthority7], rsi; char *
0x18023f4a6  lea     r9, aFinishedAlloca; "Finished allocating new user SID"
0x18023f4ad  mov     qword ptr [rsp+330h+nSubAuthority6], rsi; char *
0x18023f4b2  xor     edx, edx; unsigned __int16
0x18023f4b4  mov     qword ptr [rsp+330h+nSubAuthority5], rsi; char *
0x18023f4b9  xor     r8d, r8d; int
0x18023f4bc  mov     qword ptr [rsp+330h+nSubAuthority4], rsi; char *
0x18023f4c1  mov     qword ptr [rsp+330h+nSubAuthority3], rsi; char *
0x18023f4c6  lea     ecx, [rdx+9]; int
0x18023f4c9  mov     qword ptr [rsp+330h+nSubAuthority2], rsi; char *
0x18023f4ce  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18023f4d3  mov     rcx, [rsp+330h+var_2D0]
0x18023f4d8  mov     rax, [rcx]
0x18023f4db  mov     rax, [rax+10h]
0x18023f4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023f4e4  mov     eax, ebx
0x18023f4e6  mov     rcx, [rbp+230h+var_40]
0x18023f4ed  xor     rcx, rsp; StackCookie
0x18023f4f0  call    __security_check_cookie
0x18023f4f5  mov     rbx, [rsp+330h+arg_18]
0x18023f4fd  add     rsp, 300h
0x18023f504  pop     r15
0x18023f506  pop     r14
0x18023f508  pop     r13
0x18023f50a  pop     r12
0x18023f50c  pop     rdi
0x18023f50d  pop     rsi
0x18023f50e  pop     rbp
0x18023f50f  retn
```
