# GenerateSD(IMsiEngine &,IMsiView &,IMsiStream * &)

- ea: `0x18005e7dc`
- end: `0x18005ee28`
- name: `?GenerateSD@@YAPEAVIMsiRecord@@AEAVIMsiEngine@@AEAVIMsiView@@AEAPEAVIMsiStream@@@Z`
- size: `1612`
- prototype: `struct IMsiRecord *__fastcall(struct IMsiEngine *, struct IMsiView *, struct IMsiStream **)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005f6c0`
- `0x1800c4be0`
- `0x18020d83c`
- `0x180219dc8`

## callees

- `0x180025a18`
- `0x18002b35c`
- `0x180035a8c`
- `0x18004295c`
- `0x18005e7dc`
- `0x180061334`
- `0x1800620e4`
- `0x18006c0cc`
- `0x180076e28`
- `0x1800c9830`
- `0x18013a830`
- `0x18014a65c`
- `0x1802378bc`
- `0x1802383f4`
- `0x18025ab12`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetEntriesInAclW` at `0x18005ec5d`
- `ADVAPI32!SetEntriesInAclW` at `0x18005ec5d`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18005eb94`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18005ec49`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18005eb94`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18005ec49`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18005ecbc`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18005ecbc`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18005ec8f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18005ec8f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18005ecae`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18005ecae`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18005ecca`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18005ecca`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18005ede1`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18005ede1`
- `KERNEL32!GetLastError` at `0x18005ec99`
- `KERNEL32!GetLastError` at `0x18005ec99`
- `KERNEL32!LocalFree` at `0x18005ed0d`
- `KERNEL32!LocalFree` at `0x18005ed0d`

## string_xrefs

- `0x18005ea41`: `SID WARNING: User account '%s' resolved to an empty string!`

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
  unsigned int v13; // eax
  unsigned __int64 v14; // kr00_8
  unsigned __int64 v15; // rdi
  __int64 v16; // rax
  bool v17; // cf
  unsigned int v18; // eax
  _QWORD *v19; // rax
  __int64 v20; // rdi
  struct IMsiEngine *v21; // r14
  __int64 v22; // rax
  const struct IMsiString *v23; // r15
  const struct IMsiString *v24; // r14
  struct IMsiString *v25; // rax
  __int64 v26; // rcx
  int v27; // r14d
  const unsigned __int16 *v28; // rax
  __int64 v29; // rax
  struct IMsiStream **v30; // rax
  signed int v31; // r15d
  __int64 v32; // r14
  __int64 v33; // rdx
  DWORD v34; // eax
  __int64 v35; // r8
  struct IMsiStream **v36; // rdi
  const struct IMsiString **v37; // rax
  unsigned int v38; // eax
  __int64 v39; // rdi
  __int64 v40; // r14
  __int64 v41; // rax
  DWORD LastError; // eax
  struct IMsiRecord *v43; // rax
  DWORD SecurityDescriptorLength; // eax
  PSECURITY_DESCRIPTOR v45; // rdx
  void *v47; // rax
  ULONG cCountOfExplicitEntries; // [rsp+60h] [rbp-A0h] BYREF
  int v49; // [rsp+64h] [rbp-9Ch]
  unsigned int v50; // [rsp+68h] [rbp-98h]
  DWORD dwBufferLength; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  struct IMsiEngine *v54; // [rsp+80h] [rbp-80h]
  PACL NewAcl; // [rsp+88h] [rbp-78h] BYREF
  struct IMsiView *v56; // [rsp+90h] [rbp-70h] BYREF
  struct IMsiString *v57; // [rsp+98h] [rbp-68h]
  struct IMsiStream **v58; // [rsp+A0h] [rbp-60h]
  _OWORD pSecurityDescriptor[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v60; // [rsp+C8h] [rbp-38h]
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+D0h] [rbp-30h] BYREF
  int v62; // [rsp+D8h] [rbp-28h]
  _BYTE v63[512]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = *(_QWORD *)a1;
  v58 = a3;
  v56 = a2;
  v54 = a1;
  v5 = *(__int64 (__fastcall **)(struct IMsiEngine *))(v3 + 56);
  v50 = 0;
  v52 = 0;
  v53 = 0;
  v6 = (struct IMsiString *)&MsiString::s_NullString;
  v7 = v5(a1);
  memset_0(v63, 0, sizeof(v63));
  v62 = 512;
  pSelfRelativeSecurityDescriptor = v63;
  v8 = *(_QWORD *)a2;
  v9 = 0;
  NewAcl = 0;
  v10 = 0;
  cCountOfExplicitEntries = 0;
  v11 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiView *, ULONG *))(v8 + 72))(
                               a2,
                               &cCountOfExplicitEntries);
  if ( v11 )
    goto LABEL_41;
  v12 = cCountOfExplicitEntries;
  if ( !cCountOfExplicitEntries )
    goto LABEL_41;
  ++cCountOfExplicitEntries;
  v14 = (int)(v12 + 1);
  v13 = 48 * (v12 + 1);
  if ( !is_mul_ok(v14, 0x30u) )
    v13 = -1;
  v9 = (struct _EXPLICIT_ACCESS_W *)operator new(v13);
  if ( v9 )
  {
    memset_0(v9, 0, 48LL * (int)cCountOfExplicitEntries);
    v15 = (int)cCountOfExplicitEntries;
    v16 = 88LL * (int)cCountOfExplicitEntries;
    if ( !is_mul_ok((int)cCountOfExplicitEntries, 0x58u) )
      v16 = -1;
    v17 = __CFADD__(v16, 8);
    v18 = v16 + 8;
    if ( v17 )
      v18 = -1;
    v19 = (_QWORD *)operator new(v18);
    if ( v19 )
    {
      v10 = (char *)(v19 + 1);
      *v19 = v15;
      `vector constructor iterator'(v19 + 1, 0x58u, v15, (void *(*)(void *))CTempBuffer<char,72>::CTempBuffer<char,72>);
      if ( v10 )
      {
        v20 = (__int64)v58;
        v49 = 0;
LABEL_13:
        v21 = v54;
        while ( 1 )
        {
          v22 = (*(__int64 (__fastcall **)(struct IMsiView *))(*(_QWORD *)v56 + 56LL))(v56);
          if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v53, v22) )
            break;
          v23 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 72LL))(v53, 2);
          v24 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 72LL))(v53, 1);
          v25 = FormatUser(v54, v24, v23);
          v26 = *(_QWORD *)v6;
          v57 = v25;
          (*(void (__fastcall **)(struct IMsiString *))(v26 + 16))(v6);
          v6 = v57;
          (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v24 + 16LL))(v24);
          (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v23 + 16LL))(v23);
          if ( !(*(unsigned int (__fastcall **)(struct IMsiString *))(*(_QWORD *)v6 + 56LL))(v6) )
          {
            v27 = v50;
            if ( g_dmDiagnosticMode )
            {
              v27 = v50 | 1;
              v50 |= 1u;
              v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 72LL))(v53, 2);
              v28 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 80LL))(v20);
              DebugString(
                10,
                0,
                0,
                L"SID WARNING: User account '%s' resolved to an empty string!",
                v28,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            }
            if ( (v27 & 1) != 0 )
            {
              v29 = *(_QWORD *)v20;
              v50 = v27 & 0xFFFFFFFE;
              (*(void (__fastcall **)(__int64))(v29 + 16))(v20);
            }
          }
          v30 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v52);
          v21 = v54;
          v11 = LookupSid(v54, v6, v30);
          if ( v11 )
            goto LABEL_41;
          if ( v52 )
          {
            v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
            v32 = 88LL * v49;
            if ( v31 <= *(_DWORD *)&v10[v32 + 8] )
              goto LABEL_29;
            if ( *(int *)&v10[v32 + 8] > 72 )
              operator delete(*(void **)&v10[v32]);
            v33 = v31 <= 72 ? (__int64)&v10[v32 + 16] : operator new(v31);
            *(_QWORD *)&v10[v32] = v33;
            *(_DWORD *)&v10[v32 + 8] = v33 != 0 ? v31 : 0;
            if ( v33 )
            {
LABEL_29:
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v52 + 64LL))(
                v52,
                *(_QWORD *)&v10[v32],
                (unsigned int)v31);
              v34 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 56LL))(v53, 3);
              v35 = v49;
              v9[v35].grfAccessMode = v34 != 0 ? GRANT_ACCESS : DENY_ACCESS;
              v9[v35].grfAccessPermissions = v34;
              v9[v35].grfInheritance = 3;
              BuildTrusteeWithSidW(&v9[v35].Trustee, *(PSID *)&v10[v32]);
              ++v49;
              goto LABEL_13;
            }
            goto LABEL_39;
          }
        }
        v36 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v52);
        v37 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v56, L"SYSTEM");
        v11 = LookupSid(v21, *v37, v36);
        (*(void (__fastcall **)(struct IMsiView *))(*(_QWORD *)v56 + 16LL))(v56);
        if ( v11 )
          goto LABEL_41;
        v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
        v39 = v49;
        v40 = 88LL * v49;
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v52 + 64LL))(v52, *(_QWORD *)&v10[v40], v38);
        v41 = v39;
        v9[v41].grfAccessMode = GRANT_ACCESS;
        v9[v41].grfAccessPermissions = 0x10000000;
        v9[v41].grfInheritance = 3;
        BuildTrusteeWithSidW(&v9[v39].Trustee, *(PSID *)&v10[v40]);
        LastError = SetEntriesInAclW(cCountOfExplicitEntries, v9, 0, &NewAcl);
        if ( LastError )
        {
LABEL_32:
          v43 = PostError(2608, LastError);
          goto LABEL_40;
        }
        memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
        v60 = 0;
        if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
          && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0)
          && IsValidSecurityDescriptor(pSecurityDescriptor) )
        {
          SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
          dwBufferLength = SecurityDescriptorLength;
          if ( SecurityDescriptorLength <= 0x200 )
          {
            v45 = pSelfRelativeSecurityDescriptor;
          }
          else
          {
            CTempBuffer<char,512>::SetSize(&pSelfRelativeSecurityDescriptor, SecurityDescriptorLength);
            v45 = pSelfRelativeSecurityDescriptor;
            if ( !pSelfRelativeSecurityDescriptor )
              goto LABEL_39;
          }
          if ( MakeSelfRelativeSD(pSecurityDescriptor, v45, &dwBufferLength) )
          {
            v47 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD, struct IMsiStream **))(*(_QWORD *)v7 + 280LL))(
                            v7,
                            dwBufferLength,
                            v58);
            if ( v47 )
            {
              memcpy_0(v47, pSelfRelativeSecurityDescriptor, dwBufferLength);
              goto LABEL_41;
            }
            goto LABEL_39;
          }
        }
        LastError = GetLastError();
        goto LABEL_32;
      }
    }
  }
LABEL_39:
  v43 = PostError(2402);
LABEL_40:
  v11 = v43;
LABEL_41:
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v9 )
    operator delete(v9);
  if ( v10 )
  {
    `vector destructor iterator'(
      v10,
      0x58u,
      *((_QWORD *)v10 - 1),
      (void (*)(void *))CTempBuffer<char,72>::~CTempBuffer<char,72>);
    operator delete(v10 - 8);
  }
  if ( v62 > 512 )
    operator delete(pSelfRelativeSecurityDescriptor);
  (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  return v11;
}

```

## disassembly

```asm
0x18005e7dc  mov     [rsp-8+arg_18], rbx
0x18005e7e1  push    rbp
0x18005e7e2  push    rsi
0x18005e7e3  push    rdi
0x18005e7e4  push    r12
0x18005e7e6  push    r13
0x18005e7e8  push    r14
0x18005e7ea  push    r15
0x18005e7ec  lea     rbp, [rsp-1F0h]
0x18005e7f4  sub     rsp, 2F0h
0x18005e7fb  mov     rax, cs:__security_cookie
0x18005e802  xor     rax, rsp
0x18005e805  mov     [rbp+220h+var_40], rax
0x18005e80c  mov     rax, [rcx]
0x18005e80f  xor     r14d, r14d
0x18005e812  mov     [rbp+220h+var_280], r8
0x18005e816  mov     rdi, rdx
0x18005e819  mov     [rbp+220h+var_290], rdx
0x18005e81d  mov     [rbp+220h+var_2A0], rcx
0x18005e821  mov     rax, [rax+38h]
0x18005e825  mov     [rsp+320h+var_2B8], r14d
0x18005e82a  mov     [rsp+320h+var_2B0], r14
0x18005e82f  mov     [rsp+320h+var_2A8], r14
0x18005e834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e839  xor     edx, edx; Val
0x18005e83b  lea     rcx, [rbp+220h+var_240]; void *
0x18005e83f  mov     r8d, 200h; Size
0x18005e845  lea     rsi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18005e84c  mov     rbx, rax
0x18005e84f  call    memset_0
0x18005e854  lea     rax, [rbp+220h+var_240]
0x18005e858  mov     [rbp+220h+var_248], 200h
0x18005e85f  mov     [rbp+220h+pSelfRelativeSecurityDescriptor], rax
0x18005e863  lea     rdx, [rsp+320h+cCountOfExplicitEntries]
0x18005e868  mov     rax, [rdi]
0x18005e86b  xor     r12d, r12d
0x18005e86e  mov     rcx, rdi
0x18005e871  mov     [rbp+220h+NewAcl], r12
0x18005e875  xor     r13d, r13d
0x18005e878  mov     [rsp+320h+cCountOfExplicitEntries], r12d
0x18005e87d  mov     rax, [rax+48h]
0x18005e881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e886  mov     r15, rax
0x18005e889  test    rax, rax
0x18005e88c  jnz     loc_18005ED04
0x18005e892  mov     eax, [rsp+320h+cCountOfExplicitEntries]
0x18005e896  test    eax, eax
0x18005e898  jz      loc_18005ED04
0x18005e89e  inc     eax
0x18005e8a0  movsxd  rcx, eax
0x18005e8a3  mov     [rsp+320h+cCountOfExplicitEntries], eax
0x18005e8a7  lea     eax, [r14+30h]
0x18005e8ab  mul     rcx
0x18005e8ae  lea     r14, [r12-1]
0x18005e8b3  cmovb   rax, r14
0x18005e8b7  mov     rcx, rax; unsigned __int64
0x18005e8ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e8bf  mov     r12, rax
0x18005e8c2  test    rax, rax
0x18005e8c5  jz      loc_18005ECF7
0x18005e8cb  movsxd  rax, [rsp+320h+cCountOfExplicitEntries]
0x18005e8d0  xor     edx, edx; Val
0x18005e8d2  mov     rcx, r12; void *
0x18005e8d5  lea     r8, [rax+rax*2]
0x18005e8d9  shl     r8, 4; Size
0x18005e8dd  call    memset_0
0x18005e8e2  movsxd  rdi, [rsp+320h+cCountOfExplicitEntries]
0x18005e8e7  lea     eax, [r13+58h]
0x18005e8eb  mul     rdi
0x18005e8ee  cmovb   rax, r14
0x18005e8f2  add     rax, 8
0x18005e8f6  cmovb   rax, r14
0x18005e8fa  mov     rcx, rax; unsigned __int64
0x18005e8fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e902  test    rax, rax
0x18005e905  jz      loc_18005ECF7
0x18005e90b  lea     r13, [rax+8]
0x18005e90f  mov     [rax], rdi
0x18005e912  mov     rcx, r13; void *
0x18005e915  lea     r9, ??0?$CTempBuffer@D$0EI@@@QEAA@XZ; void *(*)(void *)
0x18005e91c  mov     r8, rdi; unsigned __int64
0x18005e91f  lea     edx, [r15+58h]; unsigned __int64
0x18005e923  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18005e928  test    r13, r13
0x18005e92b  jz      loc_18005ECF7
0x18005e931  mov     rdi, [rbp+220h+var_280]
0x18005e935  mov     [rsp+320h+var_2BC], r15d
0x18005e93a  mov     r14, [rbp+220h+var_2A0]
0x18005e93e  mov     rcx, [rbp+220h+var_290]
0x18005e942  mov     rax, [rcx]
0x18005e945  mov     rax, [rax+38h]
0x18005e949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e94e  mov     rdx, rax
0x18005e951  lea     rcx, [rsp+320h+var_2A8]
0x18005e956  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18005e95b  cmp     qword ptr [rax], 0
0x18005e95f  jz      loc_18005EBA3
0x18005e965  mov     rcx, [rsp+320h+var_2A8]
0x18005e96a  mov     edx, 2
0x18005e96f  mov     rax, [rcx]
0x18005e972  mov     rax, [rax+48h]
0x18005e976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e97b  mov     rcx, [rsp+320h+var_2A8]
0x18005e980  mov     r15, rax
0x18005e983  mov     rdx, [rcx]
0x18005e986  mov     rax, [rdx+48h]
0x18005e98a  mov     edx, 1
0x18005e98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e994  mov     rcx, [rbp+220h+var_2A0]; struct IMsiEngine *
0x18005e998  mov     r8, r15; struct IMsiString *
0x18005e99b  mov     rdx, rax; struct IMsiString *
0x18005e99e  mov     r14, rax
0x18005e9a1  call    ?FormatUser@@YAAEBVIMsiString@@AEAVIMsiEngine@@AEBV1@1@Z; FormatUser(IMsiEngine &,IMsiString const &,IMsiString const &)
0x18005e9a6  mov     rcx, [rsi]
0x18005e9a9  mov     [rbp+220h+var_288], rax
0x18005e9ad  mov     rax, [rcx+10h]
0x18005e9b1  mov     rcx, rsi
0x18005e9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9b9  mov     rcx, [r14]
0x18005e9bc  mov     rsi, [rbp+220h+var_288]
0x18005e9c0  mov     rax, [rcx+10h]
0x18005e9c4  mov     rcx, r14
0x18005e9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9cc  mov     rcx, [r15]
0x18005e9cf  mov     rax, [rcx+10h]
0x18005e9d3  mov     rcx, r15
0x18005e9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9db  mov     rax, [rsi]
0x18005e9de  mov     rcx, rsi
0x18005e9e1  mov     r15, rsi
0x18005e9e4  mov     rax, [rax+38h]
0x18005e9e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9ed  test    eax, eax
0x18005e9ef  jnz     loc_18005EA93
0x18005e9f5  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18005e9fb  mov     r14d, [rsp+320h+var_2B8]
0x18005ea00  jz      short loc_18005EA75
0x18005ea02  mov     rcx, [rsp+320h+var_2A8]
0x18005ea07  or      r14d, 1
0x18005ea0b  mov     edx, 2
0x18005ea10  mov     [rsp+320h+var_2B8], r14d
0x18005ea15  mov     rax, [rcx]
0x18005ea18  mov     rax, [rax+48h]
0x18005ea1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea21  mov     rdi, rax
0x18005ea24  mov     rcx, rdi
0x18005ea27  mov     rax, [rax]
0x18005ea2a  mov     rax, [rax+50h]
0x18005ea2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea33  lea     rcx, aNull; "(NULL)"
0x18005ea3a  xor     edx, edx; unsigned __int16
0x18005ea3c  mov     [rsp+320h+var_2C8], rdx; void *
0x18005ea41  lea     r9, aSidWarningUser; "SID WARNING: User account '%s' resolved"...
0x18005ea48  mov     [rsp+320h+var_2D0], edx; unsigned int
0x18005ea4c  xor     r8d, r8d; int
0x18005ea4f  mov     [rsp+320h+var_2D8], rcx; unsigned __int16 *
0x18005ea54  mov     [rsp+320h+var_2E0], rcx; unsigned __int16 *
0x18005ea59  mov     [rsp+320h+var_2E8], rcx; unsigned __int16 *
0x18005ea5e  mov     [rsp+320h+var_2F0], rcx; unsigned __int16 *
0x18005ea63  mov     [rsp+320h+var_2F8], rcx; unsigned __int16 *
0x18005ea68  lea     ecx, [rdx+0Ah]; int
0x18005ea6b  mov     [rsp+320h+var_300], rax; unsigned __int16 *
0x18005ea70  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18005ea75  test    r14b, 1
0x18005ea79  jz      short loc_18005EA93
0x18005ea7b  mov     rax, [rdi]
0x18005ea7e  and     r14d, 0FFFFFFFEh
0x18005ea82  mov     rcx, rdi
0x18005ea85  mov     [rsp+320h+var_2B8], r14d
0x18005ea8a  mov     rax, [rax+10h]
0x18005ea8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea93  lea     rcx, [rsp+320h+var_2B0]
0x18005ea98  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18005ea9d  mov     r14, [rbp+220h+var_2A0]
0x18005eaa1  mov     r8, rax; struct IMsiStream **
0x18005eaa4  mov     rcx, r14; struct IMsiEngine *
0x18005eaa7  mov     rdx, r15; struct IMsiString *
0x18005eaaa  call    ?LookupSid@@YAPEAVIMsiRecord@@AEAVIMsiEngine@@AEBVIMsiString@@AEAPEAVIMsiStream@@@Z; LookupSid(IMsiEngine &,IMsiString const &,IMsiStream * &)
0x18005eaaf  mov     r15, rax
0x18005eab2  test    rax, rax
0x18005eab5  jnz     loc_18005ED04
0x18005eabb  mov     rcx, [rsp+320h+var_2B0]
0x18005eac0  test    rcx, rcx
0x18005eac3  jz      loc_18005E93E
0x18005eac9  mov     rax, [rcx]
0x18005eacc  mov     rax, [rax+20h]
0x18005ead0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ead5  movsxd  r15, eax
0x18005ead8  movsxd  rax, [rsp+320h+var_2BC]
0x18005eadd  imul    r14, rax, 58h ; 'X'
0x18005eae1  cmp     r15d, [r14+r13+8]
0x18005eae6  jle     short loc_18005EB30
0x18005eae8  cmp     dword ptr [r14+r13+8], 48h ; 'H'
0x18005eaee  jle     short loc_18005EAF9
0x18005eaf0  mov     rcx, [r14+r13]; void *
0x18005eaf4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005eaf9  cmp     r15d, 48h ; 'H'
0x18005eafd  jle     short loc_18005EB0C
0x18005eaff  mov     rcx, r15; unsigned __int64
0x18005eb02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005eb07  mov     rdx, rax
0x18005eb0a  jmp     short loc_18005EB13
0x18005eb0c  lea     rdx, [r14+10h]
0x18005eb10  add     rdx, r13
0x18005eb13  mov     rax, rdx
0x18005eb16  mov     [r14+r13], rdx
0x18005eb1a  neg     rax
0x18005eb1d  sbb     ecx, ecx
0x18005eb1f  and     ecx, r15d
0x18005eb22  mov     [r14+r13+8], ecx
0x18005eb27  test    rdx, rdx
0x18005eb2a  jz      loc_18005ECF7
0x18005eb30  mov     rcx, [rsp+320h+var_2B0]
0x18005eb35  mov     r8d, r15d
0x18005eb38  mov     rdx, [r14+r13]
0x18005eb3c  mov     rax, [rcx]
0x18005eb3f  mov     rax, [rax+40h]
0x18005eb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb48  mov     rcx, [rsp+320h+var_2A8]
0x18005eb4d  mov     r15d, 3
0x18005eb53  mov     edx, r15d
0x18005eb56  mov     rax, [rcx]
0x18005eb59  mov     rax, [rax+38h]
0x18005eb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb62  movsxd  rcx, [rsp+320h+var_2BC]
0x18005eb67  lea     r8, [rcx+rcx*2]
0x18005eb6b  mov     ecx, eax
0x18005eb6d  shl     r8, 4
0x18005eb71  neg     ecx
0x18005eb73  sbb     edx, edx
0x18005eb75  and     edx, 0FFFFFFFEh
0x18005eb78  lea     rcx, [r8+10h]
0x18005eb7c  add     edx, r15d
0x18005eb7f  add     rcx, r12; pTrustee
0x18005eb82  mov     [r8+r12+4], edx
0x18005eb87  mov     [r8+r12], eax
0x18005eb8b  mov     [r8+r12+8], r15d
0x18005eb90  mov     rdx, [r14+r13]; pSid
0x18005eb94  call    cs:__imp_BuildTrusteeWithSidW
0x18005eb9a  inc     [rsp+320h+var_2BC]
0x18005eb9e  jmp     loc_18005E93A
0x18005eba3  lea     rcx, [rsp+320h+var_2B0]
0x18005eba8  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18005ebad  lea     rdx, aSystem; "SYSTEM"
0x18005ebb4  mov     rdi, rax
0x18005ebb7  lea     rcx, [rbp+220h+var_290]; this
0x18005ebbb  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18005ebc0  mov     r8, rdi; struct IMsiStream **
0x18005ebc3  mov     rcx, r14; struct IMsiEngine *
0x18005ebc6  mov     rdx, [rax]; struct IMsiString *
0x18005ebc9  call    ?LookupSid@@YAPEAVIMsiRecord@@AEAVIMsiEngine@@AEBVIMsiString@@AEAPEAVIMsiStream@@@Z; LookupSid(IMsiEngine &,IMsiString const &,IMsiStream * &)
0x18005ebce  mov     rcx, [rbp+220h+var_290]
0x18005ebd2  mov     r15, rax
0x18005ebd5  mov     rax, [rcx]
0x18005ebd8  mov     rax, [rax+10h]
0x18005ebdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ebe1  test    r15, r15
0x18005ebe4  jnz     loc_18005ED04
0x18005ebea  mov     rcx, [rsp+320h+var_2B0]
0x18005ebef  mov     rax, [rcx]
0x18005ebf2  mov     rax, [rax+20h]
0x18005ebf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ebfb  mov     rcx, [rsp+320h+var_2B0]
0x18005ec00  mov     r8d, eax
0x18005ec03  movsxd  rdi, [rsp+320h+var_2BC]
0x18005ec08  imul    r14, rdi, 58h ; 'X'
0x18005ec0c  mov     rdx, [rcx]
0x18005ec0f  mov     rax, [rdx+40h]
0x18005ec13  mov     rdx, [r14+r13]
0x18005ec17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec1c  lea     rax, [rdi+rdi*2]
0x18005ec20  shl     rax, 4
0x18005ec24  lea     edi, [r15+1]
0x18005ec28  lea     rcx, [rax+10h]
0x18005ec2c  mov     [rax+r12+4], edi
0x18005ec31  mov     dword ptr [rax+r12], 10000000h
0x18005ec39  add     rcx, r12; pTrustee
0x18005ec3c  mov     dword ptr [rax+r12+8], 3
0x18005ec45  mov     rdx, [r14+r13]; pSid
0x18005ec49  call    cs:__imp_BuildTrusteeWithSidW
0x18005ec4f  mov     ecx, [rsp+320h+cCountOfExplicitEntries]; cCountOfExplicitEntries
0x18005ec53  lea     r9, [rbp+220h+NewAcl]; NewAcl
0x18005ec57  xor     r8d, r8d; OldAcl
0x18005ec5a  mov     rdx, r12; pListOfExplicitEntries
0x18005ec5d  call    cs:__imp_SetEntriesInAclW
0x18005ec63  test    eax, eax
0x18005ec65  jz      short loc_18005EC78
0x18005ec67  mov     edx, eax; int
0x18005ec69  mov     ecx, 0A30h; int
0x18005ec6e  call    ?PostError@@YAPEAVIMsiRecord@@HH@Z; PostError(int,int)
0x18005ec73  jmp     loc_18005ED01
0x18005ec78  xorps   xmm0, xmm0
0x18005ec7b  lea     rcx, [rbp+220h+pSecurityDescriptor]; pSecurityDescriptor
0x18005ec7f  xor     eax, eax
0x18005ec81  mov     edx, edi; dwRevision
0x18005ec83  movups  [rbp+220h+pSecurityDescriptor], xmm0
0x18005ec87  mov     [rbp+220h+var_258], rax
0x18005ec8b  movups  [rbp+220h+var_268], xmm0
0x18005ec8f  call    cs:__imp_InitializeSecurityDescriptor
0x18005ec95  test    eax, eax
  ... truncated ...
```
