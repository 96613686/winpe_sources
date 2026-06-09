# CAppImport::ImportApplication(ushort *,ushort *,ushort *,ushort *,ushort *,ulong,_GUID const &,ulong,ulong *,ulong * *,ushort * * *,ulong *,_GUID * *,ushort * * *,ulong * *,long * *)

- ea: `0x18003c380`
- end: `0x18003ca9a`
- name: `?ImportApplication@CAppImport@@UEAAJPEAG0000KAEBU_GUID@@KPEAKPEAPEAKPEAPEAPEAG2PEAPEAU2@43PEAPEAJ@Z`
- size: `1818`
- prototype: `int(CAppImport *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, const struct _GUID *, unsigned int, unsigned int *, unsigned int **, unsigned __int16 ***, unsigned int *, struct _GUID **, unsigned __int16 ***, unsigned int **, int **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a01c`
- `0x18000ae48`
- `0x18000ae78`
- `0x18000f19c`
- `0x18002f9c8`
- `0x18002fbb8`
- `0x180032c98`
- `0x18003a57c`
- `0x18003c380`
- `0x18003caa0`
- `0x18003d4bc`
- `0x18003e498`
- `0x18003e5e4`
- `0x1800426b4`
- `0x180042a70`
- `0x180044b28`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c9f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c9f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c752`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c8c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c8d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c93c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c752`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c8c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c8d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c93c`

## pseudocode

```c
__int64 __fastcall CAppImport::ImportApplication(
        struct _GUID *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        const struct _GUID *a8,
        unsigned int a9,
        unsigned int *a10,
        unsigned int **a11,
        unsigned __int16 ***a12,
        unsigned int *a13,
        struct _GUID **a14,
        unsigned __int16 ***a15,
        unsigned int **a16,
        int **a17)
{
  unsigned __int16 ***v18; // r12
  struct _GUID **v19; // r14
  unsigned __int16 ***v20; // r15
  unsigned int **v21; // rcx
  unsigned int *v22; // rax
  CAppImport *v23; // rbx
  CAppImport *v24; // rcx
  int v25; // eax
  int v26; // eax
  unsigned __int16 *v27; // rdx
  CAppImport *v28; // rdi
  int v29; // eax
  unsigned __int16 *v30; // rdx
  CAppImport *v31; // rdi
  __int64 v32; // rcx
  __int64 v33; // rsi
  unsigned int v34; // r13d
  __int64 v35; // r12
  __int64 v36; // rdi
  __int64 v37; // rax
  unsigned __int64 v38; // r15
  unsigned __int16 *v39; // rax
  unsigned __int16 ***v40; // rdx
  unsigned __int16 *v41; // r9
  __int64 v42; // rcx
  __int64 v43; // rsi
  unsigned int *v44; // rax
  unsigned int **v45; // r13
  unsigned int v46; // ebx
  __int64 v47; // rdi
  __int64 v48; // rax
  unsigned __int64 v49; // r15
  unsigned int v50; // ebx
  int v52; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+68h] [rbp-98h] BYREF
  __int64 v54; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v55; // [rsp+78h] [rbp-88h] BYREF
  int v56; // [rsp+80h] [rbp-80h] BYREF
  int v57; // [rsp+84h] [rbp-7Ch]
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp-68h] BYREF
  CAppImport *v61; // [rsp+A0h] [rbp-60h]
  unsigned __int16 ***v62; // [rsp+A8h] [rbp-58h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  int **v65; // [rsp+C0h] [rbp-40h]
  unsigned int *v66; // [rsp+C8h] [rbp-38h]
  unsigned int **v67; // [rsp+D0h] [rbp-30h]
  unsigned int *v68; // [rsp+D8h] [rbp-28h]
  void *ppInterface; // [rsp+E0h] [rbp-20h] BYREF
  int v70; // [rsp+E8h] [rbp-18h]
  __int64 v71; // [rsp+F0h] [rbp-10h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  GUID *v73; // [rsp+100h] [rbp+0h]
  unsigned int **v74; // [rsp+108h] [rbp+8h]
  struct _GUID **v75; // [rsp+110h] [rbp+10h]
  unsigned __int16 ***v76; // [rsp+118h] [rbp+18h]
  _BYTE v77[320]; // [rsp+120h] [rbp+20h] BYREF

  v18 = a12;
  v19 = a14;
  v20 = a15;
  v63 = (__int64)a5;
  v72 = (__int64)a6;
  v68 = a10;
  v66 = a13;
  pv = 0;
  String1 = 0;
  String2 = 0;
  v54 = 0;
  v53 = 0;
  ppInterface = 0;
  v70 = 0;
  v71 = 0;
  v56 = 0;
  v61 = (CAppImport *)this;
  v55 = a2;
  v67 = a11;
  v64 = (__int64)a4;
  v76 = a12;
  v75 = a14;
  v62 = a15;
  v74 = a16;
  v65 = a17;
  v73 = this + 6;
  CPackageDefinitionFile::CPackageDefinitionFile((CPackageDefinitionFile *)v77, this + 6);
  if ( a10 )
    *v68 = 0;
  v21 = v67;
  if ( v67 )
    *v67 = 0;
  if ( a12 )
    *a12 = 0;
  v22 = v66;
  if ( v66 )
    *v66 = 0;
  if ( a14 )
    *a14 = 0;
  if ( a15 )
    *a15 = 0;
  if ( a16 )
    *a16 = 0;
  if ( a17 )
    *a17 = 0;
  if ( !a3 || !a10 || !v21 || !a12 || !v22 || !a14 || !a15 || !a16 || !a17 )
  {
    CPackageDefinitionFile::~CPackageDefinitionFile((CPackageDefinitionFile *)v77);
    CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
    return 2147942487LL;
  }
  v23 = v61;
  v24 = v61;
  v57 = 0;
  *((_DWORD *)v61 + 20) = 0;
  v52 = CAppImport::VerifyAppInstall(v24, a8);
  if ( !v52 )
  {
    v52 = CImpersonate::ImpersonateClient(&ppInterface);
    if ( !v52 )
    {
      if ( RegScanUtil::sm_wszDir )
      {
        RegScanUtil::ScanFiles(1, 0);
        CoTaskMemFree(RegScanUtil::sm_wszDir);
        RegScanUtil::sm_wszDir = 0;
        RegScanUtil::DeleteFileRefs();
      }
      if ( !v55 || !*v55 )
      {
        v55 = 0;
        v52 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, unsigned __int16 *, unsigned __int16 **))(*((_QWORD *)v23 + 1) + 40LL))(
                (__int64)v23 + 8,
                a8,
                a3,
                &v55);
        if ( v52 < 0 )
          goto LABEL_47;
        v57 = 1;
      }
      v25 = IsAplFile(a3, &v56);
      v52 = v25;
      if ( v25 >= 0 )
      {
        v26 = v56;
      }
      else
      {
        if ( v25 != -2147217387 )
          goto LABEL_47;
        v26 = 0;
      }
      if ( (a7 & 0x10000) != 0 )
      {
        if ( !v26 )
          goto LABEL_40;
        v30 = a3;
        v31 = v61;
        v52 = CAppImport::VerifyAndCopyApplicationFile(
                v61,
                v30,
                v55,
                0,
                a7,
                &String2,
                &String1,
                (unsigned __int16 **)&pv);
        if ( !v52 )
        {
          v29 = CAppImport::ImportApplicationFromAPL(v31, (LPCWSTR)pv, v64, v63, v72, a7, (__int64)&v54, (__int64)&v53);
          goto LABEL_46;
        }
      }
      else
      {
        if ( v26 )
        {
LABEL_40:
          v52 = -2146368504;
          goto LABEL_47;
        }
        v27 = a3;
        v28 = v61;
        v52 = CAppImport::VerifyAndCopyApplicationFile(
                v61,
                v27,
                v55,
                1,
                a7,
                &String2,
                &String1,
                (unsigned __int16 **)&pv);
        if ( !v52 )
        {
          v29 = CAppImport::ImportApplicationFromPDF(
                  (__int64)v28,
                  String1,
                  String2,
                  (unsigned __int16 *)pv,
                  v64,
                  v63,
                  a7,
                  (__int64)&v54,
                  (__int64)&v53);
LABEL_46:
          v52 = v29;
        }
      }
    }
  }
LABEL_47:
  v32 = v53;
  *v73 = GUID_DefaultAppPartition;
  if ( v32 )
  {
    v33 = *(unsigned int *)(v32 + 16);
    if ( (_DWORD)v33 )
    {
      *a14 = (struct _GUID *)CoTaskMemAlloc(16LL * (unsigned int)v33);
      *a16 = (unsigned int *)CoTaskMemAlloc(4 * v33);
      *v65 = (int *)CoTaskMemAlloc(4 * v33);
      *a15 = (unsigned __int16 **)CoTaskMemAlloc(8 * v33);
      v34 = 0;
      v35 = 0;
      v36 = 0;
      do
      {
        if ( *v19 )
          (*v19)[v36] = *(struct _GUID *)*(_QWORD *)(8 * v35 + *(_QWORD *)(v53 + 8));
        if ( *v74 )
          (*v74)[v36] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v53 + 8) + 8 * v35) + 36LL);
        if ( *v65 )
          (*v65)[v36] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v53 + 8) + 8 * v35) + 104LL);
        if ( *v20 )
        {
          v37 = -1;
          do
            ++v37;
          while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v53 + 8) + 8 * v35) + 16LL) + 2 * v37) );
          v38 = v37 + 1;
          v39 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v37 + 1));
          v40 = v62;
          (*v62)[v36] = v39;
          v41 = (*v40)[v36];
          if ( v41 )
          {
            StringCchCopyW(v41, v38, *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(v53 + 8) + 8 * v35) + 16LL));
            v20 = v62;
          }
          else
          {
            v20 = v40;
          }
        }
        v19 = v75;
        ++v34;
        ++v35;
        ++v36;
      }
      while ( v34 < (unsigned int)v33 );
      v18 = v76;
      *v66 = v33;
    }
  }
  v42 = v54;
  if ( v54 )
  {
    v43 = *(unsigned int *)(v54 + 16);
    if ( (_DWORD)v43 )
    {
      v44 = (unsigned int *)CoTaskMemAlloc(4 * v43);
      v45 = v67;
      *v67 = v44;
      *v18 = (unsigned __int16 **)CoTaskMemAlloc(8 * v43);
      v46 = 0;
      do
      {
        v47 = 8LL * (int)v46;
        if ( *v45 )
          (*v45)[v46] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v54 + 8) + 8LL * (int)v46) + 12LL);
        if ( *v18 )
        {
          v48 = -1;
          do
            ++v48;
          while ( *(_WORD *)(**(_QWORD **)(v47 + *(_QWORD *)(v54 + 8)) + 2 * v48) );
          v49 = v48 + 1;
          (*v18)[v46] = (unsigned __int16 *)CoTaskMemAlloc(2 * (v48 + 1));
          if ( (*v18)[v46] )
            StringCchCopyW((*v18)[v46], v49, **(const unsigned __int16 ***)(v47 + *(_QWORD *)(v54 + 8)));
        }
        ++v46;
      }
      while ( v46 < (unsigned int)v43 );
      v42 = v54;
      *v68 = v43;
    }
    if ( v42 )
    {
      CArray<DllInfo *,DllInfo * const &>::SetSize(v42, 0);
      if ( v54 )
      {
        (**(void (__fastcall ***)(__int64, __int64))v54)(v54, 1);
        v54 = 0;
      }
    }
  }
  if ( v53 )
  {
    CArray<CompInfo *,CompInfo * const &>::SetSize(v53, 0);
    if ( v53 )
    {
      (**(void (__fastcall ***)(__int64, __int64))v53)(v53, 1);
      v53 = 0;
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( String1 )
    CoTaskMemFree(String1);
  CoTaskMemFree(String2);
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, &v52);
  if ( v57 )
    CoTaskMemFree(v55);
  v50 = v52;
  if ( !v52 )
  {
    if ( *((_DWORD *)v61 + 20) )
      v50 = 1115152;
  }
  CPackageDefinitionFile::~CPackageDefinitionFile((CPackageDefinitionFile *)v77);
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return v50;
}

```

## disassembly

```asm
0x18003c380  push    rbp
0x18003c382  push    rbx
0x18003c383  push    rsi
0x18003c384  push    rdi
0x18003c385  push    r12
0x18003c387  push    r13
0x18003c389  push    r14
0x18003c38b  push    r15
0x18003c38d  lea     rbp, [rsp-178h]
0x18003c395  sub     rsp, 278h
0x18003c39c  mov     rax, cs:__security_cookie
0x18003c3a3  xor     rax, rsp
0x18003c3a6  mov     [rbp+1B0h+var_50], rax
0x18003c3ad  mov     rax, [rbp+1B0h+arg_20]
0x18003c3b4  mov     rdi, r8
0x18003c3b7  mov     r13, [rbp+1B0h+arg_50]
0x18003c3be  mov     r12, [rbp+1B0h+arg_58]
0x18003c3c5  mov     r14, [rbp+1B0h+arg_68]
0x18003c3cc  mov     r15, [rbp+1B0h+arg_70]
0x18003c3d3  mov     rbx, [rbp+1B0h+arg_80]
0x18003c3da  mov     rsi, [rbp+1B0h+arg_38]
0x18003c3e1  mov     [rbp+1B0h+var_200], rax
0x18003c3e5  mov     rax, [rbp+1B0h+arg_28]
0x18003c3ec  mov     [rbp+1B0h+var_1B8], rax
0x18003c3f0  mov     rax, [rbp+1B0h+arg_48]
0x18003c3f7  mov     [rbp+1B0h+var_1D8], rax
0x18003c3fb  mov     rax, [rbp+1B0h+arg_60]
0x18003c402  mov     [rbp+1B0h+var_1E8], rax
0x18003c406  xor     eax, eax
0x18003c408  mov     [rbp+1B0h+pv], rax
0x18003c40c  mov     [rbp+1B0h+String1], rax
0x18003c410  mov     [rbp+1B0h+String2], rax
0x18003c414  mov     [rsp+2B0h+var_240], rax
0x18003c419  mov     [rsp+2B0h+var_248], rax
0x18003c41e  mov     [rbp+1B0h+ppInterface], rax
0x18003c422  mov     [rbp+1B0h+var_1C8], eax
0x18003c425  mov     [rbp+1B0h+var_1C0], rax
0x18003c429  mov     [rbp+1B0h+var_230], eax
0x18003c42c  lea     rax, [rcx+60h]
0x18003c430  mov     [rbp+1B0h+var_210], rcx
0x18003c434  lea     rcx, [rbp+1B0h+var_190]; this
0x18003c438  mov     [rsp+2B0h+var_238], rdx
0x18003c43d  mov     rdx, rax; struct _GUID *
0x18003c440  mov     [rbp+1B0h+var_1E0], r13
0x18003c444  mov     r13, [rbp+1B0h+arg_78]
0x18003c44b  mov     [rbp+1B0h+var_1F8], r9
0x18003c44f  mov     [rbp+1B0h+var_198], r12
0x18003c453  mov     [rbp+1B0h+var_1A0], r14
0x18003c457  mov     [rbp+1B0h+var_208], r15
0x18003c45b  mov     [rbp+1B0h+var_1A8], r13
0x18003c45f  mov     [rbp+1B0h+var_1F0], rbx
0x18003c463  mov     [rbp+1B0h+var_1B0], rax
0x18003c467  call    ??0CPackageDefinitionFile@@QEAA@AEBU_GUID@@@Z; CPackageDefinitionFile::CPackageDefinitionFile(_GUID const &)
0x18003c46c  mov     rdx, [rbp+1B0h+var_1D8]
0x18003c470  xor     r8d, r8d
0x18003c473  test    rdx, rdx
0x18003c476  jz      short loc_18003C47B
0x18003c478  mov     [rdx], r8d
0x18003c47b  mov     rcx, [rbp+1B0h+var_1E0]
0x18003c47f  test    rcx, rcx
0x18003c482  jz      short loc_18003C487
0x18003c484  mov     [rcx], r8
0x18003c487  test    r12, r12
0x18003c48a  jz      short loc_18003C490
0x18003c48c  mov     [r12], r8
0x18003c490  mov     rax, [rbp+1B0h+var_1E8]
0x18003c494  test    rax, rax
0x18003c497  jz      short loc_18003C49C
0x18003c499  mov     [rax], r8d
0x18003c49c  test    r14, r14
0x18003c49f  jz      short loc_18003C4A4
0x18003c4a1  mov     [r14], r8
0x18003c4a4  test    r15, r15
0x18003c4a7  jz      short loc_18003C4AC
0x18003c4a9  mov     [r15], r8
0x18003c4ac  test    r13, r13
0x18003c4af  jz      short loc_18003C4B5
0x18003c4b1  mov     [r13+0], r8
0x18003c4b5  test    rbx, rbx
0x18003c4b8  jz      short loc_18003C4BD
0x18003c4ba  mov     [rbx], r8
0x18003c4bd  test    rdi, rdi
0x18003c4c0  jz      loc_18003CA60
0x18003c4c6  test    rdx, rdx
0x18003c4c9  jz      loc_18003CA60
0x18003c4cf  test    rcx, rcx
0x18003c4d2  jz      loc_18003CA60
0x18003c4d8  test    r12, r12
0x18003c4db  jz      loc_18003CA60
0x18003c4e1  test    rax, rax
0x18003c4e4  jz      loc_18003CA60
0x18003c4ea  test    r14, r14
0x18003c4ed  jz      loc_18003CA60
0x18003c4f3  test    r15, r15
0x18003c4f6  jz      loc_18003CA60
0x18003c4fc  test    r13, r13
0x18003c4ff  jz      loc_18003CA60
0x18003c505  test    rbx, rbx
0x18003c508  jz      loc_18003CA60
0x18003c50e  mov     rbx, [rbp+1B0h+var_210]
0x18003c512  mov     rdx, rsi; struct _GUID *
0x18003c515  mov     rcx, rbx; this
0x18003c518  mov     [rbp+1B0h+var_22C], r8d
0x18003c51c  mov     [rbx+50h], r8d
0x18003c520  call    ?VerifyAppInstall@CAppImport@@AEAAJAEBU_GUID@@@Z; CAppImport::VerifyAppInstall(_GUID const &)
0x18003c525  mov     [rsp+2B0h+var_250], eax
0x18003c529  test    eax, eax
0x18003c52b  jnz     loc_18003C724
0x18003c531  lea     rcx, [rbp+1B0h+ppInterface]; ppInterface
0x18003c535  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x18003c53a  xor     edx, edx
0x18003c53c  mov     [rsp+2B0h+var_250], eax
0x18003c540  test    eax, eax
0x18003c542  jnz     loc_18003C724
0x18003c548  cmp     cs:?sm_wszDir@RegScanUtil@@0PEAGEA, rdx; ushort * RegScanUtil::sm_wszDir
0x18003c54f  jz      short loc_18003C578
0x18003c551  lea     ecx, [rax+1]
0x18003c554  call    ?ScanFiles@RegScanUtil@@CAXW4FILE_SCAN_ENUM@1@@Z; RegScanUtil::ScanFiles(RegScanUtil::FILE_SCAN_ENUM)
0x18003c559  mov     rcx, cs:?sm_wszDir@RegScanUtil@@0PEAGEA; pv
0x18003c560  call    cs:__imp_CoTaskMemFree
0x18003c566  mov     cs:?sm_wszDir@RegScanUtil@@0PEAGEA, 0; ushort * RegScanUtil::sm_wszDir
0x18003c571  call    ?DeleteFileRefs@RegScanUtil@@CAXXZ; RegScanUtil::DeleteFileRefs(void)
0x18003c576  xor     edx, edx
0x18003c578  mov     rcx, [rsp+2B0h+var_238]
0x18003c57d  test    rcx, rcx
0x18003c580  jz      short loc_18003C587
0x18003c582  cmp     dx, [rcx]
0x18003c585  jnz     short loc_18003C5BA
0x18003c587  lea     rcx, [rbx+8]
0x18003c58b  mov     [rsp+2B0h+var_238], rdx
0x18003c590  mov     rax, [rcx]
0x18003c593  lea     r9, [rsp+2B0h+var_238]
0x18003c598  mov     r8, rdi
0x18003c59b  mov     rdx, rsi
0x18003c59e  mov     rax, [rax+28h]
0x18003c5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5a7  mov     [rsp+2B0h+var_250], eax
0x18003c5ab  test    eax, eax
0x18003c5ad  js      loc_18003C724
0x18003c5b3  mov     [rbp+1B0h+var_22C], 1
0x18003c5ba  lea     rdx, [rbp+1B0h+var_230]; int *
0x18003c5be  mov     rcx, rdi; unsigned __int16 *
0x18003c5c1  call    ?IsAplFile@@YAJPEBGPEAH@Z; IsAplFile(ushort const *,int *)
0x18003c5c6  xor     ecx, ecx
0x18003c5c8  mov     [rsp+2B0h+var_250], eax
0x18003c5cc  test    eax, eax
0x18003c5ce  jns     short loc_18003C5DF
0x18003c5d0  cmp     eax, 80041015h
0x18003c5d5  jnz     loc_18003C724
0x18003c5db  mov     eax, ecx
0x18003c5dd  jmp     short loc_18003C5E2
0x18003c5df  mov     eax, [rbp+1B0h+var_230]
0x18003c5e2  mov     ebx, [rbp+1B0h+arg_30]
0x18003c5e8  bt      ebx, 10h
0x18003c5ec  jb      loc_18003C68B
0x18003c5f2  test    eax, eax
0x18003c5f4  jz      short loc_18003C603
0x18003c5f6  mov     [rsp+2B0h+var_250], 80110408h
0x18003c5fe  jmp     loc_18003C724
0x18003c603  mov     r8, [rsp+2B0h+var_238]; unsigned __int16 *
0x18003c608  lea     rax, [rbp+1B0h+pv]
0x18003c60c  mov     [rsp+2B0h+var_278], rax; unsigned __int16 **
0x18003c611  mov     rdx, rdi; unsigned __int16 *
0x18003c614  mov     rdi, [rbp+1B0h+var_210]
0x18003c618  lea     rax, [rbp+1B0h+String1]
0x18003c61c  mov     [rsp+2B0h+var_280], rax; unsigned __int16 **
0x18003c621  mov     r9d, 1; int
0x18003c627  lea     rax, [rbp+1B0h+String2]
0x18003c62b  mov     rcx, rdi; this
0x18003c62e  mov     [rsp+2B0h+var_288], rax; unsigned __int16 **
0x18003c633  mov     dword ptr [rsp+2B0h+lpFileName], ebx; unsigned int
0x18003c637  call    ?VerifyAndCopyApplicationFile@CAppImport@@AEAAJPEAG0HKPEAPEAG11@Z; CAppImport::VerifyAndCopyApplicationFile(ushort *,ushort *,int,ulong,ushort * *,ushort * *,ushort * *)
0x18003c63c  mov     [rsp+2B0h+var_250], eax
0x18003c640  test    eax, eax
0x18003c642  jnz     loc_18003C724
0x18003c648  mov     r9, [rbp+1B0h+pv]; unsigned __int16 *
0x18003c64c  lea     rax, [rsp+2B0h+var_248]
0x18003c651  mov     r8, [rbp+1B0h+String2]; String2
0x18003c655  mov     rcx, rdi; __int64
0x18003c658  mov     rdx, [rbp+1B0h+String1]; String1
0x18003c65c  mov     qword ptr [rsp+2B0h+var_270], rax; __int64
0x18003c661  lea     rax, [rsp+2B0h+var_240]
0x18003c666  mov     [rsp+2B0h+var_278], rax; __int64
0x18003c66b  mov     rax, [rbp+1B0h+var_200]
0x18003c66f  mov     dword ptr [rsp+2B0h+var_280], ebx; int
0x18003c673  mov     [rsp+2B0h+var_288], rax; __int64
0x18003c678  mov     rax, [rbp+1B0h+var_1F8]
0x18003c67c  mov     [rsp+2B0h+lpFileName], rax; __int64
0x18003c681  call    ?ImportApplicationFromPDF@CAppImport@@AEAAJPEAG0000KPEAPEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAPEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@@Z; CAppImport::ImportApplicationFromPDF(ushort *,ushort *,ushort *,ushort *,ushort *,ulong,CArray<FileInfo *,FileInfo * const &> * *,CArray<CompInfo *,CompInfo * const &> * *)
0x18003c686  jmp     loc_18003C720
0x18003c68b  test    eax, eax
0x18003c68d  jz      loc_18003C5F6
0x18003c693  mov     r8, [rsp+2B0h+var_238]; unsigned __int16 *
0x18003c698  lea     rax, [rbp+1B0h+pv]
0x18003c69c  mov     [rsp+2B0h+var_278], rax; unsigned __int16 **
0x18003c6a1  mov     rdx, rdi; unsigned __int16 *
0x18003c6a4  mov     rdi, [rbp+1B0h+var_210]
0x18003c6a8  lea     rax, [rbp+1B0h+String1]
0x18003c6ac  mov     [rsp+2B0h+var_280], rax; unsigned __int16 **
0x18003c6b1  xor     r9d, r9d; int
0x18003c6b4  lea     rax, [rbp+1B0h+String2]
0x18003c6b8  mov     rcx, rdi; this
0x18003c6bb  mov     [rsp+2B0h+var_288], rax; unsigned __int16 **
0x18003c6c0  mov     dword ptr [rsp+2B0h+lpFileName], ebx; unsigned int
0x18003c6c4  call    ?VerifyAndCopyApplicationFile@CAppImport@@AEAAJPEAG0HKPEAPEAG11@Z; CAppImport::VerifyAndCopyApplicationFile(ushort *,ushort *,int,ulong,ushort * *,ushort * *,ushort * *)
0x18003c6c9  mov     [rsp+2B0h+var_250], eax
0x18003c6cd  test    eax, eax
0x18003c6cf  jnz     short loc_18003C724
0x18003c6d1  mov     r9, [rbp+1B0h+String2]
0x18003c6d5  lea     rax, [rsp+2B0h+var_248]
0x18003c6da  mov     r8, [rbp+1B0h+String1]
0x18003c6de  mov     rdx, rsi
0x18003c6e1  mov     [rsp+2B0h+var_260], rax; __int64
0x18003c6e6  mov     rcx, rdi; this
0x18003c6e9  lea     rax, [rsp+2B0h+var_240]
0x18003c6ee  mov     [rsp+2B0h+var_268], rax; __int64
0x18003c6f3  mov     rax, [rbp+1B0h+var_1B8]
0x18003c6f7  mov     [rsp+2B0h+var_270], ebx; unsigned int
0x18003c6fb  mov     [rsp+2B0h+var_278], rax; __int64
0x18003c700  mov     rax, [rbp+1B0h+var_200]
0x18003c704  mov     [rsp+2B0h+var_280], rax; __int64
0x18003c709  mov     rax, [rbp+1B0h+var_1F8]
0x18003c70d  mov     [rsp+2B0h+var_288], rax; __int64
0x18003c712  mov     rax, [rbp+1B0h+pv]
0x18003c716  mov     [rsp+2B0h+lpFileName], rax; lpFileName
0x18003c71b  call    ?ImportApplicationFromAPL@CAppImport@@AEAAJAEBU_GUID@@PEAG11111KPEAPEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAPEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@@Z; CAppImport::ImportApplicationFromAPL(_GUID const &,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ulong,CArray<FileInfo *,FileInfo * const &> * *,CArray<CompInfo *,CompInfo * const &> * *)
0x18003c720  mov     [rsp+2B0h+var_250], eax
0x18003c724  mov     rax, [rbp+1B0h+var_1B0]
0x18003c728  movups  xmm0, xmmword ptr cs:GUID_DefaultAppPartition.Data1
0x18003c72f  mov     rcx, [rsp+2B0h+var_248]
0x18003c734  movdqu  xmmword ptr [rax], xmm0
0x18003c738  test    rcx, rcx
0x18003c73b  jz      loc_18003C89E
0x18003c741  mov     esi, [rcx+10h]
0x18003c744  test    esi, esi
0x18003c746  jz      loc_18003C89E
0x18003c74c  mov     ecx, esi
0x18003c74e  shl     rcx, 4; cb
0x18003c752  call    cs:__imp_CoTaskMemAlloc
0x18003c758  lea     rbx, ds:0[rsi*4]
0x18003c760  mov     [r14], rax
0x18003c763  mov     rcx, rbx; cb
0x18003c766  call    cs:__imp_CoTaskMemAlloc
0x18003c76c  mov     rcx, rbx; cb
0x18003c76f  mov     [r13+0], rax
0x18003c773  call    cs:__imp_CoTaskMemAlloc
0x18003c779  mov     rcx, [rbp+1B0h+var_1F0]
0x18003c77d  mov     [rcx], rax
0x18003c780  lea     rcx, ds:0[rsi*8]; cb
0x18003c788  call    cs:__imp_CoTaskMemAlloc
0x18003c78e  xor     r8d, r8d
0x18003c791  mov     [r15], rax
0x18003c794  mov     r13d, r8d
0x18003c797  mov     r12d, r8d
0x18003c79a  mov     edi, r8d
0x18003c79d  mov     rdx, [r14]
0x18003c7a0  lea     rbx, ds:0[r12*8]
0x18003c7a8  test    rdx, rdx
0x18003c7ab  jz      short loc_18003C7C8
0x18003c7ad  mov     rax, [rsp+2B0h+var_248]
0x18003c7b2  mov     rcx, [rax+8]
0x18003c7b6  mov     rax, [rbx+rcx]
0x18003c7ba  movups  xmm0, xmmword ptr [rax]
0x18003c7bd  mov     rax, rdi
0x18003c7c0  add     rax, rax
0x18003c7c3  movdqu  xmmword ptr [rdx+rax*8], xmm0
0x18003c7c8  mov     rax, [rbp+1B0h+var_1A8]
0x18003c7cc  mov     r14, rdi
0x18003c7cf  mov     rdx, [rax]
0x18003c7d2  test    rdx, rdx
0x18003c7d5  jz      short loc_18003C7EA
0x18003c7d7  mov     rax, [rsp+2B0h+var_248]
0x18003c7dc  mov     rcx, [rax+8]
0x18003c7e0  mov     rax, [rcx+rbx]
0x18003c7e4  mov     ecx, [rax+24h]
0x18003c7e7  mov     [rdx+rdi*4], ecx
0x18003c7ea  mov     rax, [rbp+1B0h+var_1F0]
0x18003c7ee  mov     rdx, [rax]
0x18003c7f1  test    rdx, rdx
0x18003c7f4  jz      short loc_18003C80A
0x18003c7f6  mov     rax, [rsp+2B0h+var_248]
0x18003c7fb  mov     rcx, [rax+8]
0x18003c7ff  mov     rax, [rcx+rbx]
0x18003c803  mov     ecx, [rax+68h]
0x18003c806  mov     [rdx+r14*4], ecx
0x18003c80a  cmp     [r15], r8
0x18003c80d  jz      short loc_18003C87E
0x18003c80f  mov     rax, [rsp+2B0h+var_248]
0x18003c814  mov     rcx, [rax+8]
0x18003c818  mov     rax, [rcx+rbx]
0x18003c81c  mov     rcx, [rax+10h]
0x18003c820  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c824  inc     rax
0x18003c827  cmp     [rcx+rax*2], r8w
0x18003c82c  jnz     short loc_18003C824
0x18003c82e  lea     r15, [rax+1]
0x18003c832  lea     rcx, [r15+r15]; cb
0x18003c836  call    cs:__imp_CoTaskMemAlloc
0x18003c83c  mov     rdx, [rbp+1B0h+var_208]
0x18003c840  xor     r8d, r8d
  ... truncated ...
```
