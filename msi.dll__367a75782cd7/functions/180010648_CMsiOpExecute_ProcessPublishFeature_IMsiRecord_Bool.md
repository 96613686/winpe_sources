# CMsiOpExecute::ProcessPublishFeature(IMsiRecord &,Bool)

- ea: `0x180010648`
- end: `0x18001106d`
- name: `?ProcessPublishFeature@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiRecord@@W4Bool@@@Z`
- size: `2597`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18012c510`
- `0x1801f5c40`

## callees

- `0x18000f1bc`
- `0x18001036c`
- `0x180010648`
- `0x180012604`
- `0x180012620`
- `0x180025904`
- `0x180031f90`
- `0x18004b560`
- `0x180066074`
- `0x180066db0`
- `0x180068680`
- `0x180076e28`
- `0x18007bf88`
- `0x1800c2854`
- `0x1801386fc`
- `0x18013a90c`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180010bd8`
- `KERNEL32!GetCurrentThreadId` at `0x180010be6`
- `KERNEL32!GetCurrentThreadId` at `0x180010c56`
- `KERNEL32!GetCurrentThreadId` at `0x180010ee3`
- `KERNEL32!GetCurrentThreadId` at `0x180010ef1`
- `KERNEL32!GetCurrentThreadId` at `0x180010f3d`
- `KERNEL32!GetCurrentThreadId` at `0x180010bd8`
- `KERNEL32!GetCurrentThreadId` at `0x180010be6`
- `KERNEL32!GetCurrentThreadId` at `0x180010c56`
- `KERNEL32!GetCurrentThreadId` at `0x180010ee3`
- `KERNEL32!GetCurrentThreadId` at `0x180010ef1`
- `KERNEL32!GetCurrentThreadId` at `0x180010f3d`

## string_xrefs

- `0x180010b74`: `Installer\Features`
- `0x18001084d`: `Installer\Features\`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::ProcessPublishFeature(CMsiOpExecute *a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r15
  __int64 v6; // rdi
  __int64 v7; // rbx
  struct IMsiRecord *SharedRecord; // rsi
  struct IMsiServices *v9; // rcx
  struct IMsiRecord *SecureSecurityDescriptor; // rsi
  const struct IMsiString *ProductKey; // rsi
  const unsigned __int16 *v12; // rax
  const struct IMsiString *PackedGUID; // r14
  char v14; // si
  char v15; // al
  __int64 v16; // rdx
  __int64 v17; // r8
  void *v18; // r9
  struct IMsiServices *v19; // rcx
  __int64 v20; // rdx
  void *v21; // rax
  void *v22; // rsi
  __int64 (__fastcall *v23)(void *, __int64, _QWORD, __int64); // r15
  __int64 v24; // rax
  __int64 v25; // rax
  struct IMsiString *v26; // r15
  __int64 v27; // rdx
  __int64 (__fastcall *v28)(struct IMsiString *, __int64, int *); // rsi
  __int64 v29; // rax
  __int64 v30; // rax
  struct IMsiString *v31; // r15
  __int64 (__fastcall *v32)(struct IMsiString *, __int64, void **); // rsi
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 (__fastcall *v37)(__int64, __int64, __int64, void *); // rax
  const wchar_t *v38; // rax
  size_t *v39; // r8
  __int16 *v40; // rsi
  void *v41; // rcx
  unsigned int v42; // esi
  __int64 v43; // rsi
  bool v44; // zf
  bool v45; // cc
  __int64 v46; // rax
  __int64 v47; // r15
  struct IMsiRecord *ProductInstalledFeaturesKey; // rsi
  unsigned int v49; // esi
  __int64 v50; // rdx
  __int64 v51; // rax
  struct IMsiString *v52; // rsi
  __int64 v53; // rax
  __int64 v54; // rcx
  unsigned int v55; // r15d
  size_t v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+38h] [rbp-C8h]
  _BYTE v58[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct IMsiRecord *v59; // [rsp+48h] [rbp-B8h] BYREF
  struct IMsiString *v60; // [rsp+50h] [rbp-B0h] BYREF
  struct IMsiStream *v61; // [rsp+58h] [rbp-A8h] BYREF
  void *v62; // [rsp+60h] [rbp-A0h] BYREF
  void *v63; // [rsp+68h] [rbp-98h] BYREF
  void *v64; // [rsp+70h] [rbp-90h] BYREF
  void *v65; // [rsp+78h] [rbp-88h] BYREF
  int v66; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v67; // [rsp+84h] [rbp-7Ch]
  __int64 v68; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v69; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v70; // [rsp+98h] [rbp-68h]
  __int128 v71; // [rsp+A0h] [rbp-60h]
  __int64 v72; // [rsp+B0h] [rbp-50h]
  __int64 v73; // [rsp+B8h] [rbp-48h]
  const wchar_t *v74; // [rsp+C0h] [rbp-40h]
  __int64 v75; // [rsp+C8h] [rbp-38h]
  __int64 v76; // [rsp+D0h] [rbp-30h]
  __int16 v77; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t pszDest[55]; // [rsp+E2h] [rbp-1Eh] BYREF

  v44 = (*((_BYTE *)a1 + 864) & 0x20) == 0;
  v3 = a2;
  v67 = a3;
  v68 = a2;
  if ( v44 )
    return 1;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 72LL))(a2, 1);
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 72LL))(v3, 2);
  SharedRecord = CMsiOpExecute::GetSharedRecord(a1, 1);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)SharedRecord + 120LL))(SharedRecord, 1, v6);
  if ( (unsigned int)CMsiOpExecute::Message(a1, 150994944, SharedRecord) == 2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return 2;
  }
  v9 = *(struct IMsiServices **)a1;
  v61 = 0;
  SecureSecurityDescriptor = GetSecureSecurityDescriptor(v9, &v61, 0);
  v59 = SecureSecurityDescriptor;
  if ( SecureSecurityDescriptor )
  {
    CMsiOpExecute::Message(a1, 0x1000000, SecureSecurityDescriptor);
LABEL_7:
    if ( v59 )
      (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v59 + 16LL))(v59);
    if ( v61 )
      (*(void (__fastcall **)(struct IMsiStream *))(*(_QWORD *)v61 + 16LL))(v61);
    goto LABEL_11;
  }
  ProductKey = CMsiOpExecute::GetProductKey(a1);
  v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ProductKey + 80LL))(ProductKey);
  PackedGUID = GetPackedGUID(v12);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ProductKey + 16LL))(ProductKey);
  v14 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 56LL))(v3, 3);
  v18 = &MsiString::s_NullString;
  if ( (v15 & 1) != 0 )
  {
    v14 = 1;
    if ( (*((_DWORD *)a1 + 216) & 0x20000000) != 0 )
    {
      v64 = &MsiString::s_NullString;
      (*(void (__fastcall **)(void *, const unsigned __int16 *, void **))(MsiString::s_NullString + 96LL))(
        &MsiString::s_NullString,
        L"Installer\\Features\\",
        &v64);
      (*(void (__fastcall **)(void *, const struct IMsiString *, void **))(*(_QWORD *)v64 + 152LL))(
        v64,
        PackedGUID,
        &v64);
      v19 = *(struct IMsiServices **)a1;
      v20 = *((unsigned int *)a1 + 156);
      v60 = 0;
      v21 = (void *)(*(__int64 (__fastcall **)(struct IMsiServices *, __int64, __int64))(*(_QWORD *)v19 + 192LL))(
                      v19,
                      v20,
                      0xFFFFFFFFLL);
      v62 = v21;
      v22 = v21;
      if ( !v21
        || (v23 = *(__int64 (__fastcall **)(void *, __int64, _QWORD, __int64))(*(_QWORD *)v21 + 112LL),
            v24 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v64 + 80LL))(v64),
            v25 = v23(v22, v24, 0, 0xFFFFFFFFLL),
            !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v60, v25)) )
      {
        CMsiOpExecute::Message(a1, 0x1000000, &off_180305DB0);
        if ( v60 )
          (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 16LL))(v60);
        if ( v22 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
        v41 = v64;
        goto LABEL_32;
      }
      v26 = v60;
      v27 = *(_QWORD *)v6;
      v63 = &MsiString::s_NullString;
      v66 = 0;
      v28 = *(__int64 (__fastcall **)(struct IMsiString *, __int64, int *))(*(_QWORD *)v60 + 128LL);
      v29 = (*(__int64 (__fastcall **)(__int64))(v27 + 80))(v6);
      v30 = v28(v26, v29, &v66);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v59, v30) )
      {
LABEL_17:
        CMsiOpExecute::Message(a1, 0x1000000, v59);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v63 + 16LL))(v63);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v60);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v62);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v64 + 16LL))(v64);
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)PackedGUID + 16LL))(PackedGUID);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v59);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v61);
LABEL_11:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        return 3;
      }
      if ( v66 != 1 )
        goto LABEL_23;
      v31 = v60;
      v32 = *(__int64 (__fastcall **)(struct IMsiString *, __int64, void **))(*(_QWORD *)v60 + 40LL);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v63 + 16LL))(v63);
      v33 = *(_QWORD *)v6;
      v63 = &MsiString::s_NullString;
      v34 = (*(__int64 (__fastcall **)(__int64))(v33 + 80))(v6);
      v35 = v32(v31, v34, &v63);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v59, v35) )
        goto LABEL_17;
      if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v63 + 56LL))(v63)
        && *(_WORD *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v63 + 80LL))(v63) == 6 )
      {
LABEL_23:
        v14 = 1;
      }
      else
      {
        v14 = 0;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v63 + 16LL))(v63);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v60);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v62);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v64 + 16LL))(v64);
      v3 = v68;
    }
  }
  v36 = *(_QWORD *)v7;
  if ( v14 )
  {
    v37 = *(__int64 (__fastcall **)(__int64, __int64, __int64, void *))(v36 + 80);
    v77 = 6;
    v38 = (const wchar_t *)v37(v7, v16, v17, v18);
    StringCopyWorkerW(pszDest, 0x35u, v39, v38, v56);
    v40 = &v77;
  }
  else if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64, void *))(v36 + 56))(v7, v16, v17, v18) )
  {
    v40 = (__int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 80LL))(v7);
  }
  else
  {
    v40 = 0;
  }
  v69 = L"%s\\%s";
  v70 = L"Installer\\Features";
  v71 = (unsigned __int64)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)PackedGUID + 80LL))(PackedGUID);
  v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 80LL))(v6);
  v73 = (__int64)v40;
  v74 = L"s";
  v75 = 0;
  v76 = 0;
  CElevate::CElevate((CElevate *)&v62, 1);
  if ( !CSkipKeyProtectionCheck::m_dwCurrentThreadId )
  {
    CSkipKeyProtectionCheck::m_dwCurrentThreadId = GetCurrentThreadId();
LABEL_39:
    ++CSkipKeyProtectionCheck::m_iSkipKeyProctionCnt;
    goto LABEL_40;
  }
  if ( GetCurrentThreadId() == CSkipKeyProtectionCheck::m_dwCurrentThreadId )
    goto LABEL_39;
LABEL_40:
  v42 = CMsiOpExecute::ProcessRegInfo(a1, &v69, *((_QWORD *)a1 + 78), v67, v61, 0, -1, 0);
  if ( v42 != 1 || ((*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 56LL))(v3, 3) & 2) == 0 )
  {
    CSkipKeyProtectionCheck::~CSkipKeyProtectionCheck((CSkipKeyProtectionCheck *)v58);
    CElevate::~CElevate((CElevate *)&v62);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)PackedGUID + 16LL))(PackedGUID);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v59);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v61);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return v42;
  }
  if ( GetCurrentThreadId() == CSkipKeyProtectionCheck::m_dwCurrentThreadId
    && --CSkipKeyProtectionCheck::m_iSkipKeyProctionCnt <= 0 )
  {
    CSkipKeyProtectionCheck::m_dwCurrentThreadId = 0;
  }
  CElevate::~CElevate((CElevate *)&v62);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7) )
  {
    v62 = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *, __int64, void **))(MsiString::s_NullString + 128LL))(
      &MsiString::s_NullString,
      2,
      &v62);
    v43 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v62 + 168LL))(v62, v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v7 = v43;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v62 + 16LL))(v62);
  }
  v44 = *((_DWORD *)a1 + 224) == 21;
  v45 = *((_DWORD *)a1 + 224) < 21;
  v65 = &MsiString::s_NullString;
  if ( v45 || v44 && *((int *)a1 + 225) < 3 )
  {
    v49 = 4;
    while ( !(*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v49) )
    {
      v50 = v49++;
      v51 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 80LL))(v3, v50);
      PackGUID(v51, &v69, 21);
      MsiString::operator+=(&v65, &v69);
    }
  }
  else
  {
    v46 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 80LL))(v3, 4);
    (*(void (__fastcall **)(void *, __int64, void **))(*(_QWORD *)v65 + 144LL))(v65, v46, &v65);
  }
  (*(void (__fastcall **)(void *, __int64, void **))(*(_QWORD *)v65 + 152LL))(v65, v7, &v65);
  v47 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v65 + 80LL))(v65);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v60 = (struct IMsiString *)&MsiString::s_NullString;
  ProductInstalledFeaturesKey = CMsiOpExecute::GetProductInstalledFeaturesKey(a1, &v60);
  if ( v59 )
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v59 + 16LL))(v59);
  v59 = ProductInstalledFeaturesKey;
  if ( ProductInstalledFeaturesKey )
  {
    CMsiOpExecute::Message(a1, 0x1000000, ProductInstalledFeaturesKey);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 16LL))(v60);
    v41 = v65;
LABEL_32:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)PackedGUID + 16LL))(PackedGUID);
    goto LABEL_7;
  }
  v52 = v60;
  v69 = L"%s";
  v70 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 80LL))(v60);
  v53 = *(_QWORD *)v6;
  v71 = 0;
  v72 = (*(__int64 (__fastcall **)(__int64))(v53 + 80))(v6);
  v54 = -(__int64)(*(_WORD *)v47 != 0);
  v74 = L"s";
  v73 = v47 & v54;
  v75 = 0;
  v76 = 0;
  CElevate::CElevate((CElevate *)&v68, 1);
  if ( CSkipKeyProtectionCheck::m_dwCurrentThreadId )
  {
    if ( GetCurrentThreadId() != CSkipKeyProtectionCheck::m_dwCurrentThreadId )
      goto LABEL_62;
  }
  else
  {
    CSkipKeyProtectionCheck::m_dwCurrentThreadId = GetCurrentThreadId();
  }
  ++CSkipKeyProtectionCheck::m_iSkipKeyProctionCnt;
LABEL_62:
  LOBYTE(v57) = 0;
  v55 = CMsiOpExecute::ProcessRegInfo(a1, &v69, *((_QWORD *)a1 + 89), v67, v61, 0, -1, v57);
  if ( GetCurrentThreadId() == CSkipKeyProtectionCheck::m_dwCurrentThreadId
    && --CSkipKeyProtectionCheck::m_iSkipKeyProctionCnt <= 0 )
  {
    CSkipKeyProtectionCheck::m_dwCurrentThreadId = 0;
  }
  CElevate::~CElevate((CElevate *)&v68);
  (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v52 + 16LL))(v52);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v65 + 16LL))(v65);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)PackedGUID + 16LL))(PackedGUID);
  if ( v59 )
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v59 + 16LL))(v59);
  if ( v61 )
    (*(void (__fastcall **)(struct IMsiStream *))(*(_QWORD *)v61 + 16LL))(v61);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v55;
}

```

## disassembly

```asm
0x180010648  mov     [rsp-8+arg_18], rbx
0x18001064d  push    rbp
0x18001064e  push    rsi
0x18001064f  push    rdi
0x180010650  push    r12
0x180010652  push    r13
0x180010654  push    r14
0x180010656  push    r15
0x180010658  lea     rbp, [rsp-60h]
0x18001065d  sub     rsp, 160h
0x180010664  mov     rax, cs:__security_cookie
0x18001066b  xor     rax, rsp
0x18001066e  mov     [rbp+90h+var_40], rax
0x180010672  test    byte ptr [rcx+360h], 20h
0x180010679  mov     r15, rdx
0x18001067c  mov     [rbp+90h+var_10C], r8d
0x180010680  mov     r12, rcx
0x180010683  mov     [rbp+90h+var_108], rdx
0x180010687  jnz     short loc_180010693
0x180010689  mov     eax, 1
0x18001068e  jmp     loc_180011046
0x180010693  mov     rax, [rdx]
0x180010696  mov     r13d, 1
0x18001069c  mov     edx, r13d
0x18001069f  mov     rcx, r15
0x1800106a2  mov     rax, [rax+48h]
0x1800106a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106ab  mov     rdi, rax
0x1800106ae  lea     r14d, [r13+1]
0x1800106b2  mov     rax, [r15]
0x1800106b5  mov     edx, r14d
0x1800106b8  mov     rcx, r15
0x1800106bb  mov     rax, [rax+48h]
0x1800106bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106c4  mov     edx, r13d; int
0x1800106c7  mov     rcx, r12; this
0x1800106ca  mov     rbx, rax
0x1800106cd  call    ?GetSharedRecord@CMsiOpExecute@@IEAAAEAVIMsiRecord@@H@Z; CMsiOpExecute::GetSharedRecord(int)
0x1800106d2  mov     rsi, rax
0x1800106d5  mov     r8, rdi
0x1800106d8  mov     edx, r13d
0x1800106db  mov     rcx, [rax]
0x1800106de  mov     rax, [rcx+78h]
0x1800106e2  mov     rcx, rsi
0x1800106e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106ea  mov     r8, rsi
0x1800106ed  mov     edx, 9000000h
0x1800106f2  mov     rcx, r12
0x1800106f5  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1800106fa  cmp     eax, r14d
0x1800106fd  jnz     short loc_180010725
0x1800106ff  mov     rcx, [rbx]
0x180010702  mov     rax, [rcx+10h]
0x180010706  mov     rcx, rbx
0x180010709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001070e  mov     rcx, [rdi]
0x180010711  mov     rax, [rcx+10h]
0x180010715  mov     rcx, rdi
0x180010718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001071d  mov     eax, r14d
0x180010720  jmp     loc_180011046
0x180010725  mov     rcx, [r12]; struct IMsiServices *
0x180010729  lea     rdx, [rsp+190h+var_138]; struct IMsiStream **
0x18001072e  xor     r8d, r8d; bool
0x180010731  mov     [rsp+190h+var_148], 0
0x18001073a  mov     [rsp+190h+var_138], 0
0x180010743  call    ?GetSecureSecurityDescriptor@@YAPEAVIMsiRecord@@AEAVIMsiServices@@AEAPEAVIMsiStream@@_N@Z; GetSecureSecurityDescriptor(IMsiServices &,IMsiStream * &,bool)
0x180010748  mov     rcx, [rsp+190h+var_148]
0x18001074d  mov     rsi, rax
0x180010750  test    rcx, rcx
0x180010753  jz      short loc_180010761
0x180010755  mov     rdx, [rcx]
0x180010758  mov     rax, [rdx+10h]
0x18001075c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010761  mov     [rsp+190h+var_148], rsi
0x180010766  mov     rcx, r12; this
0x180010769  test    rsi, rsi
0x18001076c  jz      short loc_1800107CF
0x18001076e  mov     r8, rsi
0x180010771  mov     edx, 1000000h
0x180010776  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x18001077b  mov     rcx, [rsp+190h+var_148]
0x180010780  test    rcx, rcx
0x180010783  jz      short loc_180010791
0x180010785  mov     rax, [rcx]
0x180010788  mov     rax, [rax+10h]
0x18001078c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010791  mov     rcx, [rsp+190h+var_138]
0x180010796  test    rcx, rcx
0x180010799  jz      short loc_1800107A7
0x18001079b  mov     rax, [rcx]
0x18001079e  mov     rax, [rax+10h]
0x1800107a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107a7  mov     rax, [rbx]
0x1800107aa  mov     rcx, rbx
0x1800107ad  mov     rax, [rax+10h]
0x1800107b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107b6  mov     rax, [rdi]
0x1800107b9  mov     rcx, rdi
0x1800107bc  mov     rax, [rax+10h]
0x1800107c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c5  mov     eax, 3
0x1800107ca  jmp     loc_180011046
0x1800107cf  call    ?GetProductKey@CMsiOpExecute@@IEAAAEBVIMsiString@@XZ; CMsiOpExecute::GetProductKey(void)
0x1800107d4  mov     rsi, rax
0x1800107d7  mov     rcx, [rax]
0x1800107da  mov     rax, [rcx+50h]
0x1800107de  mov     rcx, rsi
0x1800107e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e6  mov     rcx, rax; unsigned __int16 *
0x1800107e9  call    ?GetPackedGUID@@YAAEBVIMsiString@@PEBG@Z; GetPackedGUID(ushort const *)
0x1800107ee  mov     rcx, [rsi]
0x1800107f1  mov     r14, rax
0x1800107f4  mov     rax, [rcx+10h]
0x1800107f8  mov     rcx, rsi
0x1800107fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010800  mov     rax, [r15]
0x180010803  mov     edx, 3
0x180010808  mov     rcx, r15
0x18001080b  xor     sil, sil
0x18001080e  mov     rax, [rax+38h]
0x180010812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010817  lea     r9, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18001081e  mov     ecx, 6
0x180010823  test    r13b, al
0x180010826  jz      loc_180010AA7
0x18001082c  test    dword ptr [r12+360h], 20000000h
0x180010838  mov     sil, r13b
0x18001083b  jz      loc_180010AA7
0x180010841  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180010848  lea     r8, [rsp+190h+var_120]
0x18001084d  lea     rdx, aInstallerFeatu; "Installer\\Features\\"
0x180010854  mov     [rsp+190h+var_120], r9
0x180010859  mov     rcx, r9
0x18001085c  mov     rax, [rax+60h]
0x180010860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010865  mov     rcx, [rsp+190h+var_120]
0x18001086a  lea     r8, [rsp+190h+var_120]
0x18001086f  mov     rdx, r14
0x180010872  mov     rax, [rcx]
0x180010875  mov     rax, [rax+98h]
0x18001087c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010881  mov     rcx, [r12]
0x180010885  or      r8d, 0FFFFFFFFh
0x180010889  mov     edx, [r12+270h]
0x180010891  mov     [rsp+190h+var_140], 0
0x18001089a  mov     rax, [rcx]
0x18001089d  mov     rax, [rax+0C0h]
0x1800108a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a9  mov     [rsp+190h+var_130], rax
0x1800108ae  mov     rsi, rax
0x1800108b1  test    rax, rax
0x1800108b4  jz      loc_180010ADD
0x1800108ba  mov     rax, [rax]
0x1800108bd  mov     rcx, [rsp+190h+var_120]
0x1800108c2  mov     r15, [rax+70h]
0x1800108c6  mov     rdx, [rcx]
0x1800108c9  mov     rax, [rdx+50h]
0x1800108cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108d2  mov     rdx, rax
0x1800108d5  or      r9d, 0FFFFFFFFh
0x1800108d9  mov     rax, r15
0x1800108dc  xor     r8d, r8d
0x1800108df  mov     rcx, rsi
0x1800108e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e7  mov     rdx, rax
0x1800108ea  lea     rcx, [rsp+190h+var_140]
0x1800108ef  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800108f4  cmp     qword ptr [rax], 0
0x1800108f8  jz      loc_180010ADD
0x1800108fe  mov     r15, [rsp+190h+var_140]
0x180010903  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18001090a  mov     rdx, [rdi]
0x18001090d  mov     rcx, rdi
0x180010910  mov     [rsp+190h+var_128], rax
0x180010915  mov     [rbp+90h+var_110], 0
0x18001091c  mov     rax, [r15]
0x18001091f  mov     rsi, [rax+80h]
0x180010926  mov     rax, [rdx+50h]
0x18001092a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001092f  mov     rdx, rax
0x180010932  lea     r8, [rbp+90h+var_110]
0x180010936  mov     rax, rsi
0x180010939  mov     rcx, r15
0x18001093c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010941  mov     rdx, rax
0x180010944  lea     rcx, [rsp+190h+var_148]
0x180010949  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18001094e  cmp     qword ptr [rax], 0
0x180010952  jz      short loc_1800109C4
0x180010954  mov     r8, [rsp+190h+var_148]
0x180010959  mov     edx, 1000000h
0x18001095e  mov     rcx, r12
0x180010961  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x180010966  mov     rcx, [rsp+190h+var_128]
0x18001096b  mov     rax, [rcx]
0x18001096e  mov     rax, [rax+10h]
0x180010972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010977  lea     rcx, [rsp+190h+var_140]
0x18001097c  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180010981  lea     rcx, [rsp+190h+var_130]
0x180010986  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18001098b  mov     rcx, [rsp+190h+var_120]
0x180010990  mov     rax, [rcx]
0x180010993  mov     rax, [rax+10h]
0x180010997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099c  mov     rax, [r14]
0x18001099f  mov     rcx, r14
0x1800109a2  mov     rax, [rax+10h]
0x1800109a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ab  lea     rcx, [rsp+190h+var_148]
0x1800109b0  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800109b5  lea     rcx, [rsp+190h+var_138]
0x1800109ba  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800109bf  jmp     loc_1800107A7
0x1800109c4  cmp     [rbp+90h+var_110], r13d
0x1800109c8  jnz     loc_180010A65
0x1800109ce  mov     r15, [rsp+190h+var_140]
0x1800109d3  mov     rcx, [rsp+190h+var_128]
0x1800109d8  mov     rax, [r15]
0x1800109db  mov     rsi, [rax+28h]
0x1800109df  mov     rax, [rcx]
0x1800109e2  mov     rax, [rax+10h]
0x1800109e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109eb  mov     rdx, [rdi]
0x1800109ee  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800109f5  mov     [rsp+190h+var_128], rax
0x1800109fa  mov     rcx, rdi
0x1800109fd  mov     rax, [rdx+50h]
0x180010a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a06  mov     rdx, rax
0x180010a09  lea     r8, [rsp+190h+var_128]
0x180010a0e  mov     rax, rsi
0x180010a11  mov     rcx, r15
0x180010a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a19  mov     rdx, rax
0x180010a1c  lea     rcx, [rsp+190h+var_148]
0x180010a21  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180010a26  cmp     qword ptr [rax], 0
0x180010a2a  jnz     loc_180010954
0x180010a30  mov     rcx, [rsp+190h+var_128]
0x180010a35  mov     rax, [rcx]
0x180010a38  mov     rax, [rax+38h]
0x180010a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a41  test    eax, eax
0x180010a43  jz      short loc_180010A60
0x180010a45  mov     rcx, [rsp+190h+var_128]
0x180010a4a  mov     rax, [rcx]
0x180010a4d  mov     rax, [rax+50h]
0x180010a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a56  mov     ecx, 6
0x180010a5b  cmp     [rax], cx
0x180010a5e  jz      short loc_180010A65
0x180010a60  xor     sil, sil
0x180010a63  jmp     short loc_180010A68
0x180010a65  mov     sil, r13b
0x180010a68  mov     rcx, [rsp+190h+var_128]
0x180010a6d  mov     rax, [rcx]
0x180010a70  mov     rax, [rax+10h]
0x180010a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a79  lea     rcx, [rsp+190h+var_140]
0x180010a7e  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180010a83  lea     rcx, [rsp+190h+var_130]
0x180010a88  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180010a8d  mov     rcx, [rsp+190h+var_120]
0x180010a92  mov     rax, [rcx]
0x180010a95  mov     rax, [rax+10h]
0x180010a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a9e  mov     r15, [rbp+90h+var_108]
0x180010aa2  mov     ecx, 6
0x180010aa7  mov     rax, [rbx]
0x180010aaa  test    sil, sil
0x180010aad  jz      loc_180010B40
0x180010ab3  mov     rax, [rax+50h]
0x180010ab7  mov     [rbp+90h+var_B0], cx
0x180010abb  mov     rcx, rbx
0x180010abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac3  mov     r9, rax; pszSrc
0x180010ac6  lea     rcx, [rbp+90h+pszDest]; pszDest
0x180010aca  mov     edx, 35h ; '5'; cchDest
0x180010acf  call    StringCopyWorkerW
0x180010ad4  lea     rsi, [rbp+90h+var_B0]
0x180010ad8  jmp     loc_180010B66
0x180010add  lea     r8, off_180305DB0
0x180010ae4  mov     edx, 1000000h
0x180010ae9  mov     rcx, r12
0x180010aec  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x180010af1  mov     rcx, [rsp+190h+var_140]
0x180010af6  test    rcx, rcx
0x180010af9  jz      short loc_180010B07
0x180010afb  mov     rax, [rcx]
0x180010afe  mov     rax, [rax+10h]
0x180010b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b07  test    rsi, rsi
0x180010b0a  jz      short loc_180010B1B
0x180010b0c  mov     rax, [rsi]
0x180010b0f  mov     rcx, rsi
0x180010b12  mov     rax, [rax+10h]
0x180010b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b1b  mov     rcx, [rsp+190h+var_120]
  ... truncated ...
```
