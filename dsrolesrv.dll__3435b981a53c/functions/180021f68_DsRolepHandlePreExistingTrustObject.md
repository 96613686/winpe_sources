# DsRolepHandlePreExistingTrustObject

- ea: `0x180021f68`
- end: `0x180022339`
- name: `DsRolepHandlePreExistingTrustObject`
- size: `977`
- prototype: `__int64 __usercall@<rax>(HANDLE hToken@<rcx>, LSA_HANDLE PolicyHandle@<rdx>, PTRUSTED_DOMAIN_INFORMATION_EX TrustedDomainInformation@<r8>, char, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002139c`
- `0x1800217f0`

## callees

- `0x18001e204`
- `0x18002043c`
- `0x1800204c4`
- `0x1800205ac`
- `0x180020628`
- `0x180020dbc`
- `0x180021f68`
- `0x18002c012`

## import_xrefs

- `msvcrt!malloc` at `0x18002206a`
- `msvcrt!malloc` at `0x18002216d`
- `msvcrt!malloc` at `0x1800222c9`
- `msvcrt!malloc` at `0x18002206a`
- `msvcrt!malloc` at `0x18002216d`
- `msvcrt!malloc` at `0x1800222c9`
- `msvcrt!free` at `0x1800220ae`
- `msvcrt!free` at `0x1800221b6`
- `msvcrt!free` at `0x18002230c`
- `msvcrt!free` at `0x1800220ae`
- `msvcrt!free` at `0x1800221b6`
- `msvcrt!free` at `0x18002230c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220f5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800221d5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800221d5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800220e7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800220e7`
- `ADVAPI32!LsaQueryInfoTrustedDomain` at `0x1800221cd`
- `ADVAPI32!LsaQueryInfoTrustedDomain` at `0x1800221ea`
- `ADVAPI32!LsaQueryInfoTrustedDomain` at `0x1800221cd`
- `ADVAPI32!LsaQueryInfoTrustedDomain` at `0x1800221ea`
- `ADVAPI32!LsaOpenTrustedDomainByName` at `0x180022056`
- `ADVAPI32!LsaOpenTrustedDomainByName` at `0x180022155`
- `ADVAPI32!LsaOpenTrustedDomainByName` at `0x180022056`
- `ADVAPI32!LsaOpenTrustedDomainByName` at `0x180022155`
- `ADVAPI32!LsaOpenTrustedDomain` at `0x180021fe3`
- `ADVAPI32!LsaOpenTrustedDomain` at `0x180021fe3`
- `ADVAPI32!LsaCreateTrustedDomainEx` at `0x1800222b5`
- `ADVAPI32!LsaCreateTrustedDomainEx` at `0x1800222b5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180022204`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180022204`
- `api-ms-win-security-lsapolicy-l1-1-1!LsaDelete` at `0x180022221`
- `api-ms-win-security-lsapolicy-l1-1-1!LsaDelete` at `0x180022221`

## string_xrefs

- `0x1800220fb`: `Failed to impersonate caller, error %lu\n`
- `0x180021ff2`: `Failed to find trust object by sid: 0x%lx\n`
- `0x18002224d`: `Failed to delete trust object: 0x%lx\n`
- `0x18002226d`: `Attempting to recreate trust object\n`

## pseudocode

```c
__int64 __fastcall DsRolepHandlePreExistingTrustObject(
        HANDLE hToken,
        LSA_HANDLE PolicyHandle,
        PTRUSTED_DOMAIN_INFORMATION_EX TrustedDomainInformation,
        struct _TRUSTED_DOMAIN_AUTH_INFORMATION *a4,
        char a5,
        PVOID *a6)
{
  NTSTATUS InfoTrustedDomain; // ebx
  PSID Sid; // rdx
  ACCESS_MASK v11; // r14d
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  __int64 Length; // r13
  _WORD *v15; // rax
  _WORD *v16; // r15
  PVOID v17; // rbx
  DWORD LastError; // eax
  LSA_UNICODE_STRING *p_FlatName; // r15
  NTSTATUS v20; // eax
  __int64 v21; // r13
  _WORD *v22; // rax
  _WORD *v23; // r14
  PVOID v24; // rcx
  NTSTATUS v25; // eax
  __int64 v26; // r9
  NTSTATUS TrustedDomain; // eax
  unsigned int v28; // esi
  __int64 v29; // r14
  _WORD *v30; // rax
  _WORD *v31; // rbx
  PVOID Buffer[2]; // [rsp+30h] [rbp-10h] BYREF
  PVOID TrustedDomainHandle; // [rsp+80h] [rbp+40h] BYREF
  PTRUSTED_DOMAIN_AUTH_INFORMATION AuthenticationInformation; // [rsp+98h] [rbp+58h]

  AuthenticationInformation = a4;
  TrustedDomainHandle = 0;
  InfoTrustedDomain = -1073741772;
  *a6 = 0;
  Sid = TrustedDomainInformation->Sid;
  v11 = (a5 != 0) + 0x10000;
  if ( Sid )
  {
    if ( hToken )
      v12 = ImpLsaOpenTrustedDomain(hToken, PolicyHandle, TrustedDomainInformation->Sid, v11, &TrustedDomainHandle);
    else
      v12 = LsaOpenTrustedDomain(PolicyHandle, Sid, v11, &TrustedDomainHandle);
    InfoTrustedDomain = v12;
    if ( v12 < 0
      && (DsRolepLogPrintRoutine(2, "Failed to find trust object by sid: 0x%lx\n", v12), InfoTrustedDomain == -1073741601) )
    {
      InfoTrustedDomain = -1073741772;
    }
    else if ( InfoTrustedDomain != -1073741772 )
    {
      goto LABEL_17;
    }
  }
  if ( !TrustedDomainInformation->Name.Length )
    goto LABEL_22;
  if ( hToken )
    v13 = ImpLsaOpenTrustedDomainByName(hToken, PolicyHandle, TrustedDomainInformation, v11, &TrustedDomainHandle);
  else
    v13 = LsaOpenTrustedDomainByName(PolicyHandle, &TrustedDomainInformation->Name, v11, &TrustedDomainHandle);
  InfoTrustedDomain = v13;
  if ( v13 < 0 )
  {
    Length = TrustedDomainInformation->Name.Length;
    v15 = malloc(Length + 2);
    v16 = v15;
    if ( v15 )
    {
      memcpy_0(v15, TrustedDomainInformation->Name.Buffer, (unsigned int)Length);
      v16[(unsigned __int64)TrustedDomainInformation->Name.Length >> 1] = 0;
      DsRolepLogPrintRoutine(2, "Failed to find trust object for %ws: 0x%lx\n", v16, (unsigned int)InfoTrustedDomain);
      free(v16);
    }
  }
  if ( InfoTrustedDomain == -1073741772 )
  {
LABEL_22:
    p_FlatName = &TrustedDomainInformation->FlatName;
    if ( !TrustedDomainInformation->FlatName.Length )
      goto LABEL_41;
    if ( hToken )
      v20 = ImpLsaOpenTrustedDomainByName(
              hToken,
              PolicyHandle,
              &TrustedDomainInformation->FlatName,
              v11,
              &TrustedDomainHandle);
    else
      v20 = LsaOpenTrustedDomainByName(PolicyHandle, &TrustedDomainInformation->FlatName, v11, &TrustedDomainHandle);
    InfoTrustedDomain = v20;
    if ( v20 < 0 )
    {
      v21 = p_FlatName->Length;
      v22 = malloc(v21 + 2);
      v23 = v22;
      if ( v22 )
      {
        memcpy_0(v22, TrustedDomainInformation->FlatName.Buffer, (unsigned int)v21);
        v23[(unsigned __int64)p_FlatName->Length >> 1] = 0;
        DsRolepLogPrintRoutine(2, "Failed to find trust object for %ws: 0x%lx\n", v23, (unsigned int)InfoTrustedDomain);
        free(v23);
      }
      goto LABEL_41;
    }
    goto LABEL_18;
  }
LABEL_17:
  if ( InfoTrustedDomain < 0 )
    goto LABEL_41;
LABEL_18:
  if ( a5 )
  {
    Buffer[0] = 0;
    if ( hToken )
    {
      v17 = TrustedDomainHandle;
      if ( ImpersonateLoggedOnUser(hToken) )
      {
        InfoTrustedDomain = LsaQueryInfoTrustedDomain(v17, TrustedDomainInformationEx, Buffer);
        RevertToSelf();
      }
      else
      {
        LastError = GetLastError();
        DsRolepLogPrintRoutine(4, "Failed to impersonate caller, error %lu\n", LastError);
        InfoTrustedDomain = -1073741790;
      }
    }
    else
    {
      InfoTrustedDomain = LsaQueryInfoTrustedDomain(TrustedDomainHandle, TrustedDomainInformationEx, Buffer);
    }
    if ( InfoTrustedDomain >= 0 )
    {
      v24 = Buffer[0];
      if ( (*((_BYTE *)Buffer[0] + 48) & 4) != 0 )
        TrustedDomainInformation->TrustAttributes |= 4u;
      LsaFreeMemory(v24);
      goto LABEL_35;
    }
LABEL_41:
    DsRolepLogPrintRoutine(2, "Couldn't find existing trust object: 0x%lx\n", (unsigned int)InfoTrustedDomain);
    goto LABEL_42;
  }
LABEL_35:
  if ( hToken )
    v25 = ImpLsaDelete(hToken, TrustedDomainHandle);
  else
    v25 = LsaDelete(TrustedDomainHandle);
  if ( v25 < 0 )
  {
    DsRolepLogPrintRoutine(2, "Failed to delete trust object: 0x%lx\n", (unsigned int)v25);
  }
  else
  {
    DsRolepEventWrite(DSROLERES_INCOMPATIBLE_TRUST_EVENT, L"u", TrustedDomainInformation, v26);
    dword_18004E218 |= 1u;
  }
LABEL_42:
  DsRolepLogPrintRoutine(4, "Attempting to recreate trust object\n");
  if ( hToken )
    TrustedDomain = ImpLsaCreateTrustedDomainEx(
                      hToken,
                      PolicyHandle,
                      TrustedDomainInformation,
                      AuthenticationInformation);
  else
    TrustedDomain = LsaCreateTrustedDomainEx(
                      PolicyHandle,
                      TrustedDomainInformation,
                      AuthenticationInformation,
                      0x10000u,
                      &TrustedDomainHandle);
  v28 = TrustedDomain;
  if ( TrustedDomain >= 0 )
  {
    *a6 = TrustedDomainHandle;
  }
  else
  {
    v29 = TrustedDomainInformation->Name.Length;
    v30 = malloc(v29 + 2);
    v31 = v30;
    if ( v30 )
    {
      memcpy_0(v30, TrustedDomainInformation->Name.Buffer, (unsigned int)v29);
      v31[(unsigned __int64)TrustedDomainInformation->Name.Length >> 1] = 0;
      DsRolepLogPrintRoutine(4, "Second Trust creationwith %ws failed with 0x%lx\n", v31, v28);
      free(v31);
    }
  }
  return v28;
}

```

## disassembly

```asm
0x180021f68  mov     [rsp-38h+arg_8], rbx
0x180021f6d  mov     [rsp-38h+AuthenticationInformation], r9
0x180021f72  push    rbp
0x180021f73  push    rsi
0x180021f74  push    rdi
0x180021f75  push    r12
0x180021f77  push    r13
0x180021f79  push    r14
0x180021f7b  push    r15
0x180021f7d  mov     rbp, rsp
0x180021f80  sub     rsp, 40h
0x180021f84  mov     rax, [rbp+arg_28]
0x180021f88  xor     r13d, r13d
0x180021f8b  mov     r12, rdx
0x180021f8e  mov     [rbp+TrustedDomainHandle], r13
0x180021f92  mov     rdi, r8
0x180021f95  mov     rsi, rcx
0x180021f98  mov     ebx, 0C0000034h
0x180021f9d  mov     [rax], r13
0x180021fa0  mov     al, [rbp+arg_20]
0x180021fa3  mov     rdx, [r8+20h]; TrustedDomainSid
0x180021fa7  neg     al
0x180021fa9  sbb     r14d, r14d
0x180021fac  neg     r14d
0x180021faf  add     r14d, 10000h
0x180021fb6  test    rdx, rdx
0x180021fb9  jz      short loc_18002201E
0x180021fbb  test    rcx, rcx
0x180021fbe  jz      short loc_180021FD9
0x180021fc0  lea     rax, [rbp+TrustedDomainHandle]
0x180021fc4  mov     r8, rdx
0x180021fc7  mov     rdx, r12
0x180021fca  mov     [rsp+40h+var_20], rax
0x180021fcf  mov     r9d, r14d
0x180021fd2  call    ImpLsaOpenTrustedDomain
0x180021fd7  jmp     short loc_180021FE9
0x180021fd9  lea     r9, [rbp+TrustedDomainHandle]; TrustedDomainHandle
0x180021fdd  mov     r8d, r14d; DesiredAccess
0x180021fe0  mov     rcx, r12; PolicyHandle
0x180021fe3  call    cs:__imp_LsaOpenTrustedDomain
0x180021fe9  mov     ebx, eax
0x180021feb  test    eax, eax
0x180021fed  jns     short loc_180022012
0x180021fef  mov     r8d, eax
0x180021ff2  lea     rdx, aFailedToFindTr; "Failed to find trust object by sid: 0x%"...
0x180021ff9  mov     ecx, 2
0x180021ffe  call    DsRolepLogPrintRoutine
0x180022003  cmp     ebx, 0C00000DFh
0x180022009  jnz     short loc_180022012
0x18002200b  mov     ebx, 0C0000034h
0x180022010  jmp     short loc_18002201E
0x180022012  cmp     ebx, 0C0000034h
0x180022018  jnz     loc_1800220C1
0x18002201e  cmp     [rdi], r13w
0x180022022  jbe     loc_180022119
0x180022028  test    rsi, rsi
0x18002202b  jz      short loc_180022049
0x18002202d  lea     rax, [rbp+TrustedDomainHandle]
0x180022031  mov     r9d, r14d
0x180022034  mov     r8, rdi
0x180022037  mov     [rsp+40h+var_20], rax
0x18002203c  mov     rdx, r12
0x18002203f  mov     rcx, rsi
0x180022042  call    ImpLsaOpenTrustedDomainByName
0x180022047  jmp     short loc_18002205C
0x180022049  lea     r9, [rbp+TrustedDomainHandle]; TrustedDomainHandle
0x18002204d  mov     r8d, r14d; DesiredAccess
0x180022050  mov     rdx, rdi; TrustedDomainName
0x180022053  mov     rcx, r12; PolicyHandle
0x180022056  call    cs:__imp_LsaOpenTrustedDomainByName
0x18002205c  mov     ebx, eax
0x18002205e  test    eax, eax
0x180022060  jns     short loc_1800220B9
0x180022062  movzx   r13d, word ptr [rdi]
0x180022066  lea     rcx, [r13+2]; Size
0x18002206a  call    cs:__imp_malloc
0x180022070  mov     r15, rax
0x180022073  test    rax, rax
0x180022076  jz      short loc_1800220B6
0x180022078  mov     rdx, [rdi+8]; Src
0x18002207c  mov     r8d, r13d; Size
0x18002207f  mov     rcx, rax; void *
0x180022082  call    memcpy_0
0x180022087  movzx   edx, word ptr [rdi]
0x18002208a  xor     r13d, r13d
0x18002208d  shr     rdx, 1
0x180022090  mov     r9d, ebx
0x180022093  mov     r8, r15
0x180022096  lea     ecx, [r13+2]
0x18002209a  mov     [r15+rdx*2], r13w
0x18002209f  lea     rdx, aFailedToFindTr_0; "Failed to find trust object for %ws: 0x"...
0x1800220a6  call    DsRolepLogPrintRoutine
0x1800220ab  mov     rcx, r15; Block
0x1800220ae  call    cs:__imp_free
0x1800220b4  jmp     short loc_1800220B9
0x1800220b6  xor     r13d, r13d
0x1800220b9  cmp     ebx, 0C0000034h
0x1800220bf  jz      short loc_180022119
0x1800220c1  test    ebx, ebx
0x1800220c3  js      loc_180022259
0x1800220c9  cmp     [rbp+arg_20], r13b
0x1800220cd  jz      loc_18002220A
0x1800220d3  mov     [rbp+Buffer], r13
0x1800220d7  test    rsi, rsi
0x1800220da  jz      loc_1800221DD
0x1800220e0  mov     rbx, [rbp+TrustedDomainHandle]
0x1800220e4  mov     rcx, rsi; hToken
0x1800220e7  call    cs:__imp_ImpersonateLoggedOnUser
0x1800220ed  test    eax, eax
0x1800220ef  jnz     loc_1800221C1
0x1800220f5  call    cs:__imp_GetLastError
0x1800220fb  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x180022102  mov     ecx, 4
0x180022107  mov     r8d, eax
0x18002210a  call    DsRolepLogPrintRoutine
0x18002210f  mov     ebx, 0C0000022h
0x180022114  jmp     loc_1800221F2
0x180022119  lea     r15, [rdi+10h]
0x18002211d  cmp     [r15], r13w
0x180022121  jbe     loc_180022259
0x180022127  test    rsi, rsi
0x18002212a  jz      short loc_180022148
0x18002212c  lea     rax, [rbp+TrustedDomainHandle]
0x180022130  mov     r9d, r14d
0x180022133  mov     r8, r15
0x180022136  mov     [rsp+40h+var_20], rax
0x18002213b  mov     rdx, r12
0x18002213e  mov     rcx, rsi
0x180022141  call    ImpLsaOpenTrustedDomainByName
0x180022146  jmp     short loc_18002215B
0x180022148  lea     r9, [rbp+TrustedDomainHandle]; TrustedDomainHandle
0x18002214c  mov     r8d, r14d; DesiredAccess
0x18002214f  mov     rdx, r15; TrustedDomainName
0x180022152  mov     rcx, r12; PolicyHandle
0x180022155  call    cs:__imp_LsaOpenTrustedDomainByName
0x18002215b  mov     ebx, eax
0x18002215d  test    eax, eax
0x18002215f  jns     loc_1800220C9
0x180022165  movzx   r13d, word ptr [r15]
0x180022169  lea     rcx, [r13+2]; Size
0x18002216d  call    cs:__imp_malloc
0x180022173  mov     r14, rax
0x180022176  test    rax, rax
0x180022179  jz      loc_180022256
0x18002217f  mov     rdx, [rdi+18h]; Src
0x180022183  mov     r8d, r13d; Size
0x180022186  mov     rcx, rax; void *
0x180022189  call    memcpy_0
0x18002218e  movzx   r8d, word ptr [r15]
0x180022192  lea     rdx, aFailedToFindTr_0; "Failed to find trust object for %ws: 0x"...
0x180022199  shr     r8, 1
0x18002219c  xor     r13d, r13d
0x18002219f  mov     r9d, ebx
0x1800221a2  mov     [r14+r8*2], r13w
0x1800221a7  lea     ecx, [r13+2]
0x1800221ab  mov     r8, r14
0x1800221ae  call    DsRolepLogPrintRoutine
0x1800221b3  mov     rcx, r14; Block
0x1800221b6  call    cs:__imp_free
0x1800221bc  jmp     loc_180022259
0x1800221c1  lea     r8, [rbp+Buffer]; Buffer
0x1800221c5  mov     edx, 6; InformationClass
0x1800221ca  mov     rcx, rbx; TrustedDomainHandle
0x1800221cd  call    cs:__imp_LsaQueryInfoTrustedDomain
0x1800221d3  mov     ebx, eax
0x1800221d5  call    cs:__imp_RevertToSelf
0x1800221db  jmp     short loc_1800221F2
0x1800221dd  mov     rcx, [rbp+TrustedDomainHandle]; TrustedDomainHandle
0x1800221e1  lea     r8, [rbp+Buffer]; Buffer
0x1800221e5  mov     edx, 6; InformationClass
0x1800221ea  call    cs:__imp_LsaQueryInfoTrustedDomain
0x1800221f0  mov     ebx, eax
0x1800221f2  test    ebx, ebx
0x1800221f4  js      short loc_180022259
0x1800221f6  mov     rcx, [rbp+Buffer]; Buffer
0x1800221fa  test    byte ptr [rcx+30h], 4
0x1800221fe  jz      short loc_180022204
0x180022200  or      dword ptr [rdi+30h], 4
0x180022204  call    cs:__imp_LsaFreeMemory
0x18002220a  test    rsi, rsi
0x18002220d  jz      short loc_18002221D
0x18002220f  mov     rdx, [rbp+TrustedDomainHandle]
0x180022213  mov     rcx, rsi
0x180022216  call    ImpLsaDelete
0x18002221b  jmp     short loc_180022227
0x18002221d  mov     rcx, [rbp+TrustedDomainHandle]; ObjectHandle
0x180022221  call    cs:__imp_LsaDelete
0x180022227  test    eax, eax
0x180022229  js      short loc_18002224A
0x18002222b  mov     r8, rdi
0x18002222e  lea     rdx, aU; "u"
0x180022235  lea     rcx, DSROLERES_INCOMPATIBLE_TRUST_EVENT
0x18002223c  call    DsRolepEventWrite
0x180022241  or      cs:dword_18004E218, 1
0x180022248  jmp     short loc_18002226D
0x18002224a  mov     r8d, eax
0x18002224d  lea     rdx, aFailedToDelete_2; "Failed to delete trust object: 0x%lx\n"
0x180022254  jmp     short loc_180022263
0x180022256  xor     r13d, r13d
0x180022259  mov     r8d, ebx
0x18002225c  lea     rdx, aCouldnTFindExi; "Couldn't find existing trust object: 0x"...
0x180022263  mov     ecx, 2
0x180022268  call    DsRolepLogPrintRoutine
0x18002226d  lea     rdx, aAttemptingToRe; "Attempting to recreate trust object\n"
0x180022274  mov     ecx, 4
0x180022279  call    DsRolepLogPrintRoutine
0x18002227e  lea     rax, [rbp+TrustedDomainHandle]
0x180022282  test    rsi, rsi
0x180022285  jz      short loc_1800222A0
0x180022287  mov     r9, [rbp+AuthenticationInformation]
0x18002228b  mov     r8, rdi
0x18002228e  mov     rdx, r12
0x180022291  mov     [rsp+40h+var_18], rax
0x180022296  mov     rcx, rsi
0x180022299  call    ImpLsaCreateTrustedDomainEx
0x18002229e  jmp     short loc_1800222BB
0x1800222a0  mov     r8, [rbp+AuthenticationInformation]; AuthenticationInformation
0x1800222a4  mov     r9d, 10000h; DesiredAccess
0x1800222aa  mov     rdx, rdi; TrustedDomainInformation
0x1800222ad  mov     [rsp+40h+var_20], rax; TrustedDomainHandle
0x1800222b2  mov     rcx, r12; PolicyHandle
0x1800222b5  call    cs:__imp_LsaCreateTrustedDomainEx
0x1800222bb  mov     esi, eax
0x1800222bd  test    eax, eax
0x1800222bf  jns     short loc_180022314
0x1800222c1  movzx   r14d, word ptr [rdi]
0x1800222c5  lea     rcx, [r14+2]; Size
0x1800222c9  call    cs:__imp_malloc
0x1800222cf  mov     rbx, rax
0x1800222d2  test    rax, rax
0x1800222d5  jz      short loc_18002231F
0x1800222d7  mov     rdx, [rdi+8]; Src
0x1800222db  mov     r8d, r14d; Size
0x1800222de  mov     rcx, rax; void *
0x1800222e1  call    memcpy_0
0x1800222e6  movzx   r8d, word ptr [rdi]
0x1800222ea  lea     rdx, aSecondTrustCre; "Second Trust creationwith %ws failed wi"...
0x1800222f1  shr     r8, 1
0x1800222f4  mov     r9d, esi
0x1800222f7  mov     ecx, 4
0x1800222fc  mov     [rbx+r8*2], r13w
0x180022301  mov     r8, rbx
0x180022304  call    DsRolepLogPrintRoutine
0x180022309  mov     rcx, rbx; Block
0x18002230c  call    cs:__imp_free
0x180022312  jmp     short loc_18002231F
0x180022314  mov     rcx, [rbp+arg_28]
0x180022318  mov     rax, [rbp+TrustedDomainHandle]
0x18002231c  mov     [rcx], rax
0x18002231f  mov     rbx, [rsp+40h+arg_8]
0x180022327  mov     eax, esi
0x180022329  add     rsp, 40h
0x18002232d  pop     r15
0x18002232f  pop     r14
0x180022331  pop     r13
0x180022333  pop     r12
0x180022335  pop     rdi
0x180022336  pop     rsi
0x180022337  pop     rbp
0x180022338  retn
```
