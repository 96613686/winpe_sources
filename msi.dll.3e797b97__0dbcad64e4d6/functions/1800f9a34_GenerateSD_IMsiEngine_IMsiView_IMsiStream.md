# GenerateSD(IMsiEngine &,IMsiView &,IMsiStream * &)

- ea: `0x1800f9a34`
- end: `0x1800fa0bd`
- name: `?GenerateSD@@YAPEAVIMsiRecord@@AEAVIMsiEngine@@AEAVIMsiView@@AEAPEAVIMsiStream@@@Z`
- size: `1673`
- prototype: `struct IMsiRecord *__fastcall(struct IMsiEngine *, struct IMsiView *, struct IMsiStream **)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800171d0`
- `0x1800d28e0`
- `0x1802170b0`
- `0x180223a28`

## callees

- `0x180003b10`
- `0x18000c4bc`
- `0x180018ee0`
- `0x180019cc0`
- `0x18002e870`
- `0x1800817f8`
- `0x18008c93c`
- `0x18009ad3c`
- `0x1800d7428`
- `0x1800f9a34`
- `0x18013fa30`
- `0x18014fcb8`
- `0x180241a2c`
- `0x180242568`
- `0x1802651d2`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetEntriesInAclW` at `0x1800f9ec1`
- `ADVAPI32!SetEntriesInAclW` at `0x1800f9ec1`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x1800f9dec`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x1800f9ea7`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x1800f9dec`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x1800f9ea7`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800f9f38`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800f9f38`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800f9ef9`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800f9ef9`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800f9f24`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800f9f24`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800f9f4c`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800f9f4c`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800fa070`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800fa070`
- `KERNEL32!GetLastError` at `0x1800f9f09`
- `KERNEL32!GetLastError` at `0x1800f9f09`
- `KERNEL32!LocalFree` at `0x1800f9f95`
- `KERNEL32!LocalFree` at `0x1800f9f95`

## string_xrefs

- `0x1800f9c99`: `SID WARNING: User account '%s' resolved to an empty string!`

## pseudocode

```c
struct IMsiRecord *__fastcall GenerateSD(struct IMsiEngine *a1, struct IMsiView *a2, struct IMsiStream **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v5)(struct IMsiEngine *); // rax
  struct IMsiString *v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  struct _EXPLICIT_ACCESS_W *v9; // r12
  char *v10; // r13
  struct IMsiRecord *v11; // r15
  ULONG v12; // eax
  unsigned __int64 v13; // rdi
  __int64 v14; // rax
  bool v15; // cf
  unsigned __int64 v16; // rax
  unsigned __int64 *v17; // rax
  __int64 v18; // rdi
  struct IMsiEngine *v19; // r14
  __int64 v20; // rax
  const struct IMsiString *v21; // r15
  const struct IMsiString *v22; // r14
  struct IMsiString *v23; // rax
  __int64 v24; // rcx
  int v25; // r14d
  const unsigned __int16 *v26; // rax
  __int64 v27; // rax
  struct IMsiStream **v28; // rax
  int v29; // eax
  unsigned __int64 v30; // r15
  __int64 v31; // r14
  char *v32; // rdx
  DWORD v33; // eax
  __int64 v34; // r8
  struct IMsiStream **v35; // rdi
  const struct IMsiString **v36; // rax
  unsigned int v37; // eax
  __int64 v38; // rdi
  __int64 v39; // r14
  __int64 v40; // rax
  DWORD LastError; // eax
  struct IMsiRecord *v42; // rax
  DWORD SecurityDescriptorLength; // eax
  PSECURITY_DESCRIPTOR v44; // rdx
  void *v46; // rax
  ULONG cCountOfExplicitEntries; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+64h] [rbp-9Ch]
  unsigned int v49; // [rsp+68h] [rbp-98h]
  DWORD dwBufferLength; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h] BYREF
  struct IMsiEngine *v53; // [rsp+80h] [rbp-80h]
  PACL NewAcl; // [rsp+88h] [rbp-78h] BYREF
  struct IMsiView *v55; // [rsp+90h] [rbp-70h] BYREF
  struct IMsiString *v56; // [rsp+98h] [rbp-68h]
  struct IMsiStream **v57; // [rsp+A0h] [rbp-60h]
  _OWORD pSecurityDescriptor[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-38h]
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+D0h] [rbp-30h] BYREF
  int v61; // [rsp+D8h] [rbp-28h]
  _BYTE v62[512]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = *(_QWORD *)a1;
  v57 = a3;
  v55 = a2;
  v53 = a1;
  v5 = *(__int64 (__fastcall **)(struct IMsiEngine *))(v3 + 56);
  v49 = 0;
  v51 = 0;
  v52 = 0;
  v6 = (struct IMsiString *)&MsiString::s_NullString;
  v7 = v5(a1);
  memset_0(v62, 0, sizeof(v62));
  v61 = 512;
  pSelfRelativeSecurityDescriptor = v62;
  v8 = *(_QWORD *)a2;
  v9 = 0;
  NewAcl = 0;
  v10 = 0;
  cCountOfExplicitEntries = 0;
  v11 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiView *, ULONG *))(v8 + 72))(
                               a2,
                               &cCountOfExplicitEntries);
  if ( v11 )
    goto LABEL_39;
  v12 = cCountOfExplicitEntries;
  if ( !cCountOfExplicitEntries )
    goto LABEL_39;
  ++cCountOfExplicitEntries;
  v9 = (struct _EXPLICIT_ACCESS_W *)operator new(saturated_mul((int)(v12 + 1), 0x30u));
  if ( v9 )
  {
    memset_0(v9, 0, 48LL * (int)cCountOfExplicitEntries);
    v13 = (int)cCountOfExplicitEntries;
    v14 = 88LL * (int)cCountOfExplicitEntries;
    if ( !is_mul_ok((int)cCountOfExplicitEntries, 0x58u) )
      v14 = -1;
    v15 = __CFADD__(v14, 8);
    v16 = v14 + 8;
    if ( v15 )
      v16 = -1;
    v17 = (unsigned __int64 *)operator new(v16);
    if ( v17 )
    {
      v10 = (char *)(v17 + 1);
      *v17 = v13;
      `vector constructor iterator'(v17 + 1, 0x58u, v13, CTempBuffer<char,72>::CTempBuffer<char,72>);
      if ( v10 )
      {
        v18 = (__int64)v57;
        v48 = 0;
LABEL_11:
        v19 = v53;
        while ( 1 )
        {
          v20 = (*(__int64 (__fastcall **)(struct IMsiView *))(*(_QWORD *)v55 + 56LL))(v55);
          if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v52, v20) )
            break;
          v21 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 72LL))(v52, 2);
          v22 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 72LL))(v52, 1);
          v23 = FormatUser(v53, v22, v21);
          v24 = *(_QWORD *)v6;
          v56 = v23;
          (*(void (__fastcall **)(struct IMsiString *))(v24 + 16))(v6);
          v6 = v56;
          (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v22 + 16LL))(v22);
          (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v21 + 16LL))(v21);
          if ( !(*(unsigned int (__fastcall **)(struct IMsiString *))(*(_QWORD *)v6 + 56LL))(v6) )
          {
            v25 = v49;
            if ( g_dmDiagnosticMode )
            {
              v25 = v49 | 1;
              v49 |= 1u;
              v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 72LL))(v52, 2);
              v26 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 80LL))(v18);
              DebugString(
                10,
                0,
                0,
                L"SID WARNING: User account '%s' resolved to an empty string!",
                v26,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            }
            if ( (v25 & 1) != 0 )
            {
              v27 = *(_QWORD *)v18;
              v49 = v25 & 0xFFFFFFFE;
              (*(void (__fastcall **)(__int64))(v27 + 16))(v18);
            }
          }
          v28 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v51);
          v19 = v53;
          v11 = LookupSid(v53, v6, v28);
          if ( v11 )
            goto LABEL_39;
          if ( v51 )
          {
            v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 32LL))(v51);
            v30 = v29;
            v31 = 88LL * v48;
            if ( v29 <= *(_DWORD *)&v10[v31 + 8] )
              goto LABEL_27;
            if ( *(int *)&v10[v31 + 8] > 72 )
              operator delete(*(void **)&v10[v31]);
            v32 = (int)v30 <= 72 ? &v10[v31 + 16] : (char *)operator new(v30);
            *(_QWORD *)&v10[v31] = v32;
            *(_DWORD *)&v10[v31 + 8] = v32 != 0 ? v30 : 0;
            if ( v32 )
            {
LABEL_27:
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v51 + 64LL))(
                v51,
                *(_QWORD *)&v10[v31],
                (unsigned int)v30);
              v33 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 56LL))(v52, 3);
              v34 = v48;
              v9[v34].grfAccessMode = v33 != 0 ? GRANT_ACCESS : DENY_ACCESS;
              v9[v34].grfAccessPermissions = v33;
              v9[v34].grfInheritance = 3;
              BuildTrusteeWithSidW(&v9[v34].Trustee, *(PSID *)&v10[v31]);
              ++v48;
              goto LABEL_11;
            }
            goto LABEL_37;
          }
        }
        v35 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v51);
        v36 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v55, L"SYSTEM");
        v11 = LookupSid(v19, *v36, v35);
        (*(void (__fastcall **)(struct IMsiView *))(*(_QWORD *)v55 + 16LL))(v55);
        if ( v11 )
          goto LABEL_39;
        v37 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 32LL))(v51);
        v38 = v48;
        v39 = 88LL * v48;
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v51 + 64LL))(v51, *(_QWORD *)&v10[v39], v37);
        v40 = v38;
        v9[v40].grfAccessMode = GRANT_ACCESS;
        v9[v40].grfAccessPermissions = 0x10000000;
        v9[v40].grfInheritance = 3;
        BuildTrusteeWithSidW(&v9[v38].Trustee, *(PSID *)&v10[v39]);
        LastError = SetEntriesInAclW(cCountOfExplicitEntries, v9, 0, &NewAcl);
        if ( LastError )
        {
LABEL_30:
          v42 = PostError(2608, LastError);
          goto LABEL_38;
        }
        memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
        v59 = 0;
        if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
          && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0)
          && IsValidSecurityDescriptor(pSecurityDescriptor) )
        {
          SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
          dwBufferLength = SecurityDescriptorLength;
          if ( SecurityDescriptorLength <= 0x200 )
          {
            v44 = pSelfRelativeSecurityDescriptor;
          }
          else
          {
            CTempBuffer<char,512>::SetSize(&pSelfRelativeSecurityDescriptor, SecurityDescriptorLength);
            v44 = pSelfRelativeSecurityDescriptor;
            if ( !pSelfRelativeSecurityDescriptor )
              goto LABEL_37;
          }
          if ( MakeSelfRelativeSD(pSecurityDescriptor, v44, &dwBufferLength) )
          {
            v46 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD, struct IMsiStream **))(*(_QWORD *)v7 + 280LL))(
                            v7,
                            dwBufferLength,
                            v57);
            if ( v46 )
            {
              memcpy_0(v46, pSelfRelativeSecurityDescriptor, dwBufferLength);
              goto LABEL_39;
            }
            goto LABEL_37;
          }
        }
        LastError = GetLastError();
        goto LABEL_30;
      }
    }
  }
LABEL_37:
  v42 = PostError(2402);
LABEL_38:
  v11 = v42;
LABEL_39:
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v9 )
    operator delete(v9);
  if ( v10 )
  {
    `vector destructor iterator'(v10, 0x58u, *((_QWORD *)v10 - 1), CTempBuffer<char,72>::~CTempBuffer<char,72>);
    operator delete(v10 - 8);
  }
  if ( v61 > 512 )
    operator delete(pSelfRelativeSecurityDescriptor);
  (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  return v11;
}

```

## disassembly

```asm
0x1800f9a34  mov     [rsp-8+arg_18], rbx
0x1800f9a39  push    rbp
0x1800f9a3a  push    rsi
0x1800f9a3b  push    rdi
0x1800f9a3c  push    r12
0x1800f9a3e  push    r13
0x1800f9a40  push    r14
0x1800f9a42  push    r15
0x1800f9a44  lea     rbp, [rsp-1F0h]
0x1800f9a4c  sub     rsp, 2F0h
0x1800f9a53  mov     rax, cs:__security_cookie
0x1800f9a5a  xor     rax, rsp
0x1800f9a5d  mov     [rbp+220h+var_40], rax
0x1800f9a64  mov     rax, [rcx]
0x1800f9a67  xor     r14d, r14d
0x1800f9a6a  mov     [rbp+220h+var_280], r8
0x1800f9a6e  mov     rdi, rdx
0x1800f9a71  mov     [rbp+220h+var_290], rdx
0x1800f9a75  mov     [rbp+220h+var_2A0], rcx
0x1800f9a79  mov     rax, [rax+38h]
0x1800f9a7d  mov     [rsp+320h+var_2B8], r14d
0x1800f9a82  mov     [rsp+320h+var_2B0], r14
0x1800f9a87  mov     [rsp+320h+var_2A8], r14
0x1800f9a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9a91  xor     edx, edx; Val
0x1800f9a93  lea     rcx, [rbp+220h+var_240]; void *
0x1800f9a97  mov     r8d, 200h; Size
0x1800f9a9d  lea     rsi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f9aa4  mov     rbx, rax
0x1800f9aa7  call    memset_0
0x1800f9aac  lea     rax, [rbp+220h+var_240]
0x1800f9ab0  mov     [rbp+220h+var_248], 200h
0x1800f9ab7  mov     [rbp+220h+pSelfRelativeSecurityDescriptor], rax
0x1800f9abb  lea     rdx, [rsp+320h+cCountOfExplicitEntries]
0x1800f9ac0  mov     rax, [rdi]
0x1800f9ac3  xor     r12d, r12d
0x1800f9ac6  mov     rcx, rdi
0x1800f9ac9  mov     [rbp+220h+NewAcl], r12
0x1800f9acd  xor     r13d, r13d
0x1800f9ad0  mov     [rsp+320h+cCountOfExplicitEntries], r12d
0x1800f9ad5  mov     rax, [rax+48h]
0x1800f9ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9ade  mov     r15, rax
0x1800f9ae1  test    rax, rax
0x1800f9ae4  jnz     loc_1800F9F8C
0x1800f9aea  mov     eax, [rsp+320h+cCountOfExplicitEntries]
0x1800f9aee  test    eax, eax
0x1800f9af0  jz      loc_1800F9F8C
0x1800f9af6  inc     eax
0x1800f9af8  movsxd  rcx, eax
0x1800f9afb  mov     [rsp+320h+cCountOfExplicitEntries], eax
0x1800f9aff  lea     eax, [r14+30h]
0x1800f9b03  mul     rcx
0x1800f9b06  lea     r14, [r12-1]
0x1800f9b0b  cmovb   rax, r14
0x1800f9b0f  mov     rcx, rax; unsigned __int64
0x1800f9b12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f9b17  mov     r12, rax
0x1800f9b1a  test    rax, rax
0x1800f9b1d  jz      loc_1800F9F7F
0x1800f9b23  movsxd  rax, [rsp+320h+cCountOfExplicitEntries]
0x1800f9b28  xor     edx, edx; Val
0x1800f9b2a  mov     rcx, r12; void *
0x1800f9b2d  lea     r8, [rax+rax*2]
0x1800f9b31  shl     r8, 4; Size
0x1800f9b35  call    memset_0
0x1800f9b3a  movsxd  rdi, [rsp+320h+cCountOfExplicitEntries]
0x1800f9b3f  lea     eax, [r13+58h]
0x1800f9b43  mul     rdi
0x1800f9b46  cmovb   rax, r14
0x1800f9b4a  add     rax, 8
0x1800f9b4e  cmovb   rax, r14
0x1800f9b52  mov     rcx, rax; unsigned __int64
0x1800f9b55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f9b5a  test    rax, rax
0x1800f9b5d  jz      loc_1800F9F7F
0x1800f9b63  lea     r13, [rax+8]
0x1800f9b67  mov     [rax], rdi
0x1800f9b6a  mov     rcx, r13; void *
0x1800f9b6d  lea     r9, ??0?$CTempBuffer@D$0EI@@@QEAA@XZ; void *(*)(void *)
0x1800f9b74  mov     r8, rdi; unsigned __int64
0x1800f9b77  lea     edx, [r15+58h]; unsigned __int64
0x1800f9b7b  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800f9b80  test    r13, r13
0x1800f9b83  jz      loc_1800F9F7F
0x1800f9b89  mov     rdi, [rbp+220h+var_280]
0x1800f9b8d  mov     [rsp+320h+var_2BC], r15d
0x1800f9b92  mov     r14, [rbp+220h+var_2A0]
0x1800f9b96  mov     rcx, [rbp+220h+var_290]
0x1800f9b9a  mov     rax, [rcx]
0x1800f9b9d  mov     rax, [rax+38h]
0x1800f9ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9ba6  mov     rdx, rax
0x1800f9ba9  lea     rcx, [rsp+320h+var_2A8]
0x1800f9bae  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800f9bb3  cmp     qword ptr [rax], 0
0x1800f9bb7  jz      loc_1800F9E01
0x1800f9bbd  mov     rcx, [rsp+320h+var_2A8]
0x1800f9bc2  mov     edx, 2
0x1800f9bc7  mov     rax, [rcx]
0x1800f9bca  mov     rax, [rax+48h]
0x1800f9bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9bd3  mov     rcx, [rsp+320h+var_2A8]
0x1800f9bd8  mov     r15, rax
0x1800f9bdb  mov     rdx, [rcx]
0x1800f9bde  mov     rax, [rdx+48h]
0x1800f9be2  mov     edx, 1
0x1800f9be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9bec  mov     rcx, [rbp+220h+var_2A0]; struct IMsiEngine *
0x1800f9bf0  mov     r8, r15; struct IMsiString *
0x1800f9bf3  mov     rdx, rax; struct IMsiString *
0x1800f9bf6  mov     r14, rax
0x1800f9bf9  call    ?FormatUser@@YAAEBVIMsiString@@AEAVIMsiEngine@@AEBV1@1@Z; FormatUser(IMsiEngine &,IMsiString const &,IMsiString const &)
0x1800f9bfe  mov     rcx, [rsi]
0x1800f9c01  mov     [rbp+220h+var_288], rax
0x1800f9c05  mov     rax, [rcx+10h]
0x1800f9c09  mov     rcx, rsi
0x1800f9c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c11  mov     rcx, [r14]
0x1800f9c14  mov     rsi, [rbp+220h+var_288]
0x1800f9c18  mov     rax, [rcx+10h]
0x1800f9c1c  mov     rcx, r14
0x1800f9c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c24  mov     rcx, [r15]
0x1800f9c27  mov     rax, [rcx+10h]
0x1800f9c2b  mov     rcx, r15
0x1800f9c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c33  mov     rax, [rsi]
0x1800f9c36  mov     rcx, rsi
0x1800f9c39  mov     r15, rsi
0x1800f9c3c  mov     rax, [rax+38h]
0x1800f9c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c45  test    eax, eax
0x1800f9c47  jnz     loc_1800F9CEB
0x1800f9c4d  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1800f9c53  mov     r14d, [rsp+320h+var_2B8]
0x1800f9c58  jz      short loc_1800F9CCD
0x1800f9c5a  mov     rcx, [rsp+320h+var_2A8]
0x1800f9c5f  or      r14d, 1
0x1800f9c63  mov     edx, 2
0x1800f9c68  mov     [rsp+320h+var_2B8], r14d
0x1800f9c6d  mov     rax, [rcx]
0x1800f9c70  mov     rax, [rax+48h]
0x1800f9c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c79  mov     rdi, rax
0x1800f9c7c  mov     rcx, rdi
0x1800f9c7f  mov     rax, [rax]
0x1800f9c82  mov     rax, [rax+50h]
0x1800f9c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c8b  lea     rcx, aNull; "(NULL)"
0x1800f9c92  xor     edx, edx; unsigned __int16
0x1800f9c94  mov     [rsp+320h+var_2C8], rdx; void *
0x1800f9c99  lea     r9, aSidWarningUser; "SID WARNING: User account '%s' resolved"...
0x1800f9ca0  mov     [rsp+320h+var_2D0], edx; unsigned int
0x1800f9ca4  xor     r8d, r8d; int
0x1800f9ca7  mov     [rsp+320h+var_2D8], rcx; unsigned __int16 *
0x1800f9cac  mov     [rsp+320h+var_2E0], rcx; unsigned __int16 *
0x1800f9cb1  mov     [rsp+320h+var_2E8], rcx; unsigned __int16 *
0x1800f9cb6  mov     [rsp+320h+var_2F0], rcx; unsigned __int16 *
0x1800f9cbb  mov     [rsp+320h+var_2F8], rcx; unsigned __int16 *
0x1800f9cc0  lea     ecx, [rdx+0Ah]; int
0x1800f9cc3  mov     [rsp+320h+var_300], rax; unsigned __int16 *
0x1800f9cc8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f9ccd  test    r14b, 1
0x1800f9cd1  jz      short loc_1800F9CEB
0x1800f9cd3  mov     rax, [rdi]
0x1800f9cd6  and     r14d, 0FFFFFFFEh
0x1800f9cda  mov     rcx, rdi
0x1800f9cdd  mov     [rsp+320h+var_2B8], r14d
0x1800f9ce2  mov     rax, [rax+10h]
0x1800f9ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9ceb  lea     rcx, [rsp+320h+var_2B0]
0x1800f9cf0  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1800f9cf5  mov     r14, [rbp+220h+var_2A0]
0x1800f9cf9  mov     r8, rax; struct IMsiStream **
0x1800f9cfc  mov     rcx, r14; struct IMsiEngine *
0x1800f9cff  mov     rdx, r15; struct IMsiString *
0x1800f9d02  call    ?LookupSid@@YAPEAVIMsiRecord@@AEAVIMsiEngine@@AEBVIMsiString@@AEAPEAVIMsiStream@@@Z; LookupSid(IMsiEngine &,IMsiString const &,IMsiStream * &)
0x1800f9d07  mov     r15, rax
0x1800f9d0a  test    rax, rax
0x1800f9d0d  jnz     loc_1800F9F8C
0x1800f9d13  mov     rcx, [rsp+320h+var_2B0]
0x1800f9d18  test    rcx, rcx
0x1800f9d1b  jz      loc_1800F9B96
0x1800f9d21  mov     rax, [rcx]
0x1800f9d24  mov     rax, [rax+20h]
0x1800f9d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9d2d  movsxd  r15, eax
0x1800f9d30  movsxd  rax, [rsp+320h+var_2BC]
0x1800f9d35  imul    r14, rax, 58h ; 'X'
0x1800f9d39  cmp     r15d, [r14+r13+8]
0x1800f9d3e  jle     short loc_1800F9D88
0x1800f9d40  cmp     dword ptr [r14+r13+8], 48h ; 'H'
0x1800f9d46  jle     short loc_1800F9D51
0x1800f9d48  mov     rcx, [r14+r13]; void *
0x1800f9d4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f9d51  cmp     r15d, 48h ; 'H'
0x1800f9d55  jle     short loc_1800F9D64
0x1800f9d57  mov     rcx, r15; unsigned __int64
0x1800f9d5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f9d5f  mov     rdx, rax
0x1800f9d62  jmp     short loc_1800F9D6B
0x1800f9d64  lea     rdx, [r14+10h]
0x1800f9d68  add     rdx, r13
0x1800f9d6b  mov     rax, rdx
0x1800f9d6e  mov     [r14+r13], rdx
0x1800f9d72  neg     rax
0x1800f9d75  sbb     ecx, ecx
0x1800f9d77  and     ecx, r15d
0x1800f9d7a  mov     [r14+r13+8], ecx
0x1800f9d7f  test    rdx, rdx
0x1800f9d82  jz      loc_1800F9F7F
0x1800f9d88  mov     rcx, [rsp+320h+var_2B0]
0x1800f9d8d  mov     r8d, r15d
0x1800f9d90  mov     rdx, [r14+r13]
0x1800f9d94  mov     rax, [rcx]
0x1800f9d97  mov     rax, [rax+40h]
0x1800f9d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9da0  mov     rcx, [rsp+320h+var_2A8]
0x1800f9da5  mov     r15d, 3
0x1800f9dab  mov     edx, r15d
0x1800f9dae  mov     rax, [rcx]
0x1800f9db1  mov     rax, [rax+38h]
0x1800f9db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9dba  movsxd  rcx, [rsp+320h+var_2BC]
0x1800f9dbf  lea     r8, [rcx+rcx*2]
0x1800f9dc3  mov     ecx, eax
0x1800f9dc5  shl     r8, 4
0x1800f9dc9  neg     ecx
0x1800f9dcb  sbb     edx, edx
0x1800f9dcd  and     edx, 0FFFFFFFEh
0x1800f9dd0  lea     rcx, [r8+10h]
0x1800f9dd4  add     edx, r15d
0x1800f9dd7  add     rcx, r12; pTrustee
0x1800f9dda  mov     [r8+r12+4], edx
0x1800f9ddf  mov     [r8+r12], eax
0x1800f9de3  mov     [r8+r12+8], r15d
0x1800f9de8  mov     rdx, [r14+r13]; pSid
0x1800f9dec  call    cs:__imp_BuildTrusteeWithSidW
0x1800f9df3  nop     dword ptr [rax+rax+00h]
0x1800f9df8  inc     [rsp+320h+var_2BC]
0x1800f9dfc  jmp     loc_1800F9B92
0x1800f9e01  lea     rcx, [rsp+320h+var_2B0]
0x1800f9e06  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1800f9e0b  lea     rdx, aSystem; "SYSTEM"
0x1800f9e12  mov     rdi, rax
0x1800f9e15  lea     rcx, [rbp+220h+var_290]; this
0x1800f9e19  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1800f9e1e  mov     r8, rdi; struct IMsiStream **
0x1800f9e21  mov     rcx, r14; struct IMsiEngine *
0x1800f9e24  mov     rdx, [rax]; struct IMsiString *
0x1800f9e27  call    ?LookupSid@@YAPEAVIMsiRecord@@AEAVIMsiEngine@@AEBVIMsiString@@AEAPEAVIMsiStream@@@Z; LookupSid(IMsiEngine &,IMsiString const &,IMsiStream * &)
0x1800f9e2c  mov     rcx, [rbp+220h+var_290]
0x1800f9e30  mov     r15, rax
0x1800f9e33  mov     rax, [rcx]
0x1800f9e36  mov     rax, [rax+10h]
0x1800f9e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9e3f  test    r15, r15
0x1800f9e42  jnz     loc_1800F9F8C
0x1800f9e48  mov     rcx, [rsp+320h+var_2B0]
0x1800f9e4d  mov     rax, [rcx]
0x1800f9e50  mov     rax, [rax+20h]
0x1800f9e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9e59  mov     rcx, [rsp+320h+var_2B0]
0x1800f9e5e  mov     r8d, eax
0x1800f9e61  movsxd  rdi, [rsp+320h+var_2BC]
0x1800f9e66  imul    r14, rdi, 58h ; 'X'
0x1800f9e6a  mov     rdx, [rcx]
0x1800f9e6d  mov     rax, [rdx+40h]
0x1800f9e71  mov     rdx, [r14+r13]
0x1800f9e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9e7a  lea     rax, [rdi+rdi*2]
0x1800f9e7e  shl     rax, 4
0x1800f9e82  lea     edi, [r15+1]
0x1800f9e86  lea     rcx, [rax+10h]
0x1800f9e8a  mov     [rax+r12+4], edi
0x1800f9e8f  mov     dword ptr [rax+r12], 10000000h
0x1800f9e97  add     rcx, r12; pTrustee
0x1800f9e9a  mov     dword ptr [rax+r12+8], 3
0x1800f9ea3  mov     rdx, [r14+r13]; pSid
0x1800f9ea7  call    cs:__imp_BuildTrusteeWithSidW
0x1800f9eae  nop     dword ptr [rax+rax+00h]
0x1800f9eb3  mov     ecx, [rsp+320h+cCountOfExplicitEntries]; cCountOfExplicitEntries
0x1800f9eb7  lea     r9, [rbp+220h+NewAcl]; NewAcl
0x1800f9ebb  xor     r8d, r8d; OldAcl
0x1800f9ebe  mov     rdx, r12; pListOfExplicitEntries
0x1800f9ec1  call    cs:__imp_SetEntriesInAclW
0x1800f9ec8  nop     dword ptr [rax+rax+00h]
0x1800f9ecd  test    eax, eax
0x1800f9ecf  jz      short loc_1800F9EE2
0x1800f9ed1  mov     edx, eax; int
0x1800f9ed3  mov     ecx, 0A30h; int
0x1800f9ed8  call    ?PostError@@YAPEAVIMsiRecord@@HH@Z; PostError(int,int)
0x1800f9edd  jmp     loc_1800F9F89
0x1800f9ee2  xorps   xmm0, xmm0
0x1800f9ee5  lea     rcx, [rbp+220h+pSecurityDescriptor]; pSecurityDescriptor
0x1800f9ee9  xor     eax, eax
0x1800f9eeb  mov     edx, edi; dwRevision
0x1800f9eed  movups  [rbp+220h+pSecurityDescriptor], xmm0
0x1800f9ef1  mov     [rbp+220h+var_258], rax
  ... truncated ...
```
