# CCOMComponentRegistrar::ParseTypeLibs(ulong,_GUID,InstallList *,ulong)

- ea: `0x18000b640`
- end: `0x18000bf50`
- name: `?ParseTypeLibs@CCOMComponentRegistrar@@EEAAJKU_GUID@@PEAUInstallList@@K@Z`
- size: `2320`
- prototype: `__int64 __usercall@<rax>(CCOMComponentRegistrar *__hidden this@<rcx>, unsigned int@<edx>, struct _GUID *__struct_ptr@<r8>, struct InstallList *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005944`
- `0x180009f84`
- `0x18000b640`
- `0x18000d9d4`
- `0x18002c09c`
- `0x18002c240`
- `0x18002cb28`
- `0x18002cf68`
- `0x18002cfa0`
- `0x18002d148`
- `0x180030dec`
- `0x180031b2c`
- `0x180031c68`
- `0x18005583a`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b8fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b8fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7f6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b76c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b76c`
- `KERNEL32!OpenFile` at `0x18000b716`
- `KERNEL32!OpenFile` at `0x18000b716`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18000b9b2`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18000b9d2`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18000b9b2`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18000b9d2`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18000b935`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18000b935`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bbf4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bbf4`

## string_xrefs

- `0x18000b7cd`: `com\complus\src\comcat\registrar\comcomponentregistrar.cpp`
- `0x18000b8ab`: `com\complus\src\comcat\registrar\comcomponentregistrar.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCOMComponentRegistrar::ParseTypeLibs(
        CCOMComponentRegistrar *this,
        int a2,
        struct _GUID *a3,
        struct InstallList *a4,
        unsigned int a5)
{
  int v6; // esi
  int v7; // eax
  signed int v8; // r13d
  __int64 v9; // r14
  CHAR *v10; // rax
  HFILE v11; // ebx
  HANDLE FileW; // rax
  struct FileInfo1 *v13; // rdx
  __int64 v14; // rcx
  unsigned int i; // r15d
  __int64 v16; // rax
  ITypeLib **v17; // rax
  ITypeLib **v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // r14
  __int64 v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdx
  struct CComPlusObject *v26; // r12
  unsigned int j; // ecx
  __int64 v28; // rax
  int v29; // ebx
  unsigned int v30; // eax
  BOOL v31; // r13d
  unsigned int k; // r15d
  int v33; // eax
  int v34; // edx
  __int64 v35; // rbx
  _QWORD *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r14
  unsigned int m; // ebx
  int v40; // eax
  bool v42; // zf
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-1D8h]
  signed int v44; // [rsp+50h] [rbp-1A8h]
  unsigned int v45; // [rsp+54h] [rbp-1A4h]
  __int64 v46; // [rsp+58h] [rbp-1A0h]
  int v47; // [rsp+60h] [rbp-198h] BYREF
  struct CComPlusObject *v48; // [rsp+68h] [rbp-190h] BYREF
  unsigned int v49; // [rsp+70h] [rbp-188h] BYREF
  unsigned int v50; // [rsp+74h] [rbp-184h] BYREF
  int v51; // [rsp+78h] [rbp-180h] BYREF
  __int64 v52; // [rsp+80h] [rbp-178h] BYREF
  __int64 v53; // [rsp+88h] [rbp-170h] BYREF
  unsigned int v54; // [rsp+90h] [rbp-168h] BYREF
  unsigned int v55; // [rsp+94h] [rbp-164h] BYREF
  int v56[2]; // [rsp+98h] [rbp-160h] BYREF
  int v57; // [rsp+A0h] [rbp-158h]
  int v58; // [rsp+A4h] [rbp-154h]
  LPCOLESTR szFile; // [rsp+A8h] [rbp-150h] BYREF
  _BYTE v60[24]; // [rsp+B0h] [rbp-148h] BYREF
  __int64 v61; // [rsp+C8h] [rbp-130h]
  __int64 v62; // [rsp+D0h] [rbp-128h]
  int v63; // [rsp+D8h] [rbp-120h]
  int v64; // [rsp+DCh] [rbp-11Ch]
  int v65; // [rsp+E0h] [rbp-118h]
  BSTR bstrString; // [rsp+E8h] [rbp-110h] BYREF
  int v67; // [rsp+F0h] [rbp-108h] BYREF
  __int64 v68; // [rsp+F8h] [rbp-100h] BYREF
  struct InstallList *v69; // [rsp+100h] [rbp-F8h]
  __int128 v70; // [rsp+108h] [rbp-F0h] BYREF
  __int128 v71; // [rsp+120h] [rbp-D8h] BYREF
  _OFSTRUCT ReOpenBuff; // [rsp+130h] [rbp-C8h] BYREF

  v69 = a4;
  v65 = a2;
  v6 = 0;
  memset_0(&ReOpenBuff, 0, sizeof(ReOpenBuff));
  v54 = 0;
  v58 = 0;
  v7 = *((_DWORD *)this + 22);
  v57 = v7;
  v8 = 0;
  v44 = 0;
  while ( v8 < v7 )
  {
    v9 = v8;
    v46 = v8;
    *(_QWORD *)v60 = **(_QWORD **)(*((_QWORD *)this + 10) + 8LL * v8);
    *(_OWORD *)&v60[8] = 0;
    LODWORD(v61) = 1;
    v10 = Str::operator char const *(v60);
    v11 = OpenFile(v10, &ReOpenBuff, 0x4000u);
    Str::~Str((Str *)v60);
    if ( v11 == -1 || ReOpenBuff.nErrCode == 2 )
    {
      FileW = CreateFileW(**(LPCWSTR **)(*((_QWORD *)this + 10) + 8LL * v8), 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        *(_DWORD *)v60 = 0;
        *(_WORD *)&v60[4] = 22;
        *(_DWORD *)&v60[8] = -2147478162;
        *(_QWORD *)&v60[16] = **(_QWORD **)(*((_QWORD *)this + 10) + 8LL * v8);
        v61 = 0;
        v62 = 0;
        v63 = 0;
        v64 = 1;
        CError::WriteToLog(
          (CError *)v60,
          L"com\\complus\\src\\comcat\\registrar\\comcomponentregistrar.cpp",
          0x420u,
          *(const unsigned __int16 **)&v60[16]);
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v8) + 12LL) |= 0x100u;
        goto LABEL_22;
      }
      CloseHandle(FileW);
    }
    v13 = *(struct FileInfo1 **)(*((_QWORD *)this + 10) + 8LL * v8);
    if ( *((_DWORD *)v13 + 2) == 1 )
    {
      v56[0] = -2147467259;
      v6 = CCOMComponentRegistrar::TestUserDll(this, v13, 0xFu, &v54, v56);
      if ( v6 < 0 )
        return (unsigned int)v6;
      if ( (v54 & 1) == 0 )
      {
        *(_DWORD *)v60 = 0;
        *(_WORD *)&v60[4] = 22;
        *(_DWORD *)&v60[8] = -2147478160;
        *(_QWORD *)&v60[16] = **(_QWORD **)(*((_QWORD *)this + 10) + 8LL * v8);
        v61 = 0;
        v62 = 0;
        v63 = 0;
        v64 = 1;
        CError::WriteToLog(
          (CError *)v60,
          L"com\\complus\\src\\comcat\\registrar\\comcomponentregistrar.cpp",
          0x439u,
          *(const unsigned __int16 **)&v60[16]);
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v8) + 12LL) |= 0x80u;
        goto LABEL_22;
      }
      v14 = *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v8);
      *(_DWORD *)(v14 + 12) |= 1u;
    }
    for ( i = 0; ; ++i )
    {
      v45 = i;
      v16 = *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v9);
      if ( (signed int)i < *(_DWORD *)(v16 + 32) )
      {
        v18 = *(ITypeLib ***)(*(_QWORD *)(v16 + 24) + 16LL * (int)i + 8);
        goto LABEL_24;
      }
      v17 = (ITypeLib **)CoTaskMemAlloc(0x28u);
      v18 = v17;
      *(_QWORD *)v56 = v17;
      if ( !v17 )
        return 2147942414LL;
      *v17 = 0;
      v17[2] = 0;
      v17[3] = 0;
      *((_DWORD *)v17 + 8) = 0;
      CString::CString((CString *)&szFile);
      if ( (*(unsigned int (__fastcall **)(CCOMComponentRegistrar *, _QWORD, _QWORD, LPCOLESTR *))(*(_QWORD *)this + 96LL))(
             this,
             (unsigned int)v8,
             i,
             &szFile)
        || (unsigned int)CComPlusTypelib::Load(v18, szFile) )
      {
        break;
      }
      v19 = *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v9);
      *(_DWORD *)(v19 + 12) |= 0x10u;
      v20 = *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v9);
      v21 = *(int *)(v20 + 32);
      if ( (int)v21 >= 0 )
      {
        CArray<CPtr<CComPlusTypelib>,CComPlusTypelib *>::SetSize(v20 + 16, v21 + 1);
        *(_QWORD *)(*(_QWORD *)(v20 + 24) + 16 * v21 + 8) = v18;
      }
      CString::~CString((CString *)&szFile);
      v9 = v46;
LABEL_24:
      if ( (*(int (__fastcall **)(CCOMComponentRegistrar *, _QWORD, _QWORD))(*(_QWORD *)this + 112LL))(
             this,
             (unsigned int)v8,
             i) < 0 )
        goto LABEL_32;
      v49 = 0;
      if ( (unsigned int)CComPlusTypelib::GetChildCount((CComPlusTypelib *)v18, &v49, 0) )
        goto LABEL_32;
      if ( v49 )
      {
        v22 = *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v9);
        *(_DWORD *)(v22 + 12) |= 8u;
      }
      v23 = 0;
LABEL_29:
      v56[0] = v23;
      if ( v23 >= v49 )
        continue;
      v47 = 1;
      v48 = 0;
      if ( (unsigned int)CComPlusTypelib::GetChild((CComPlusTypelib *)v18, v23, &v48, 0) )
        goto LABEL_31;
      v71 = 0;
      v26 = v48;
      if ( (*(unsigned int (__fastcall **)(struct CComPlusObject *, __int128 *))(*(_QWORD *)v48 + 48LL))(v48, &v71) )
        goto LABEL_31;
      if ( v69 )
      {
        *(_OWORD *)v60 = v71;
        for ( j = 0; ; ++j )
        {
          if ( j >= a5 )
            goto LABEL_88;
          v28 = *(_QWORD *)((char *)v69 + 20 * j) - *(_QWORD *)v60;
          if ( !v28 )
            v28 = *(_QWORD *)((char *)v69 + 20 * j + 8) - *(_QWORD *)&v60[8];
          if ( !v28 )
            break;
        }
        *((_DWORD *)v69 + 5 * j + 4) = 1;
      }
      bstrString = 0;
      if ( (*(unsigned int (__fastcall **)(struct CComPlusObject *, BSTR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v26 + 40LL))(
             v26,
             &bstrString,
             0,
             0,
             0)
        || (v53 = 0,
            dwCreationDisposition[0] = v8,
            v29 = (*(__int64 (__fastcall **)(CCOMComponentRegistrar *, __int128 *, BSTR, _QWORD, DWORD *, signed int, unsigned int, __int64 *, GUID *))(*(_QWORD *)this + 104LL))(
                    this,
                    &v71,
                    bstrString,
                    (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8 * v9) + 12LL) & 0x200000 | 0x2000u) >> 13,
                    *(DWORD **)dwCreationDisposition,
                    v8,
                    i,
                    &v53,
                    &GUID_NULL),
            SysFreeString(bstrString),
            v29 < 0)
        || (v30 = (*(__int64 (__fastcall **)(struct CComPlusObject *))(*(_QWORD *)v26 + 80LL))(v26), v30 > 1) )
      {
LABEL_31:
        CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v47);
        goto LABEL_32;
      }
      v31 = v30 == 0;
      v50 = 0;
      if ( (*(unsigned int (__fastcall **)(struct CComPlusObject *, unsigned int *))(*(_QWORD *)v26 + 32LL))(v26, &v50) )
      {
        CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v47);
        goto LABEL_51;
      }
      if ( v50 )
        *(_DWORD *)(v53 + 36) |= 8u;
      for ( k = 0; ; ++k )
      {
        if ( k >= v50 )
        {
          i = v45;
          v42 = !v31;
          v8 = v44;
          if ( !v42 )
          {
            *(_DWORD *)(v53 + 36) |= 2u;
            *(_DWORD *)(v53 + 24) = v44;
            *(_DWORD *)(v53 + 28) = v45;
          }
          v9 = v46;
LABEL_88:
          CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v47);
          v23 = v56[0] + 1;
          goto LABEL_29;
        }
        v51 = 1;
        v52 = 0;
        if ( !(*(unsigned int (__fastcall **)(struct CComPlusObject *, _QWORD, __int64 *))(*(_QWORD *)v26 + 16LL))(
                v26,
                k,
                &v52) )
          break;
        if ( v57 <= 1 )
          goto LABEL_58;
        if ( (v65 & 0x20) == 0 )
        {
          if ( *((_DWORD *)this + 34) )
            goto LABEL_58;
          v58 = 1;
        }
LABEL_82:
        CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v51);
      }
      v70 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v52 + 48LL))(v52, &v70) )
        goto LABEL_58;
      v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 80LL))(v52);
      if ( v33 )
      {
        if ( v33 != 1 )
          goto LABEL_58;
      }
      else
      {
        v31 = 1;
      }
      v34 = 0;
      v35 = v53;
      while ( v34 < *(_DWORD *)(v53 + 56) )
      {
        v36 = (_QWORD *)(*(_QWORD *)(v53 + 48) + 16LL * v34);
        v37 = v70 - *v36;
        if ( (_QWORD)v70 == *v36 )
          v37 = *((_QWORD *)&v70 + 1) - v36[1];
        if ( !v37 )
          goto LABEL_82;
        ++v34;
      }
      try
      {
        v38 = *(int *)(v53 + 56);
        if ( (int)v38 >= 0 )
        {
          CArray<_GUID,_GUID &>::SetSize(v53 + 40, v38 + 1);
          *(_OWORD *)(*(_QWORD *)(v35 + 48) + 16 * v38) = v70;
        }
      }
      catch ( ... )
      {
        CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v51);
        CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v47);
        return 2147942414LL;
      }
      v55 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 32LL))(v52, &v55) )
        goto LABEL_58;
      for ( m = 0; ; ++m )
      {
        if ( m >= v55 )
          goto LABEL_82;
        v67 = 1;
        v68 = 0;
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 16LL))(v52, m, &v68) )
          break;
        v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 80LL))(v68);
        if ( !v40 )
        {
          v31 = 1;
          CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v67);
          goto LABEL_82;
        }
        if ( v40 != 1 )
          break;
        CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v67);
      }
      CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v67);
LABEL_58:
      CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v51);
      CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v47);
      v9 = v46;
      i = v45;
LABEL_51:
      v8 = v44;
LABEL_32:
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8 * v9) + 12LL) |= 0x400u;
      v24 = *((_DWORD *)this + 30);
      while ( (--v24 & 0x80000000) == 0 )
      {
        v25 = *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * v24);
        if ( v8 == *(_DWORD *)(v25 + 24) && i == *(_DWORD *)(v25 + 28) )
          CArray<CompInfo1 *,CompInfo1 * const &>::RemoveAt((char *)this + 104, v24);
      }
    }
    CComPlusTypelib::`scalar deleting destructor'((CComPlusTypelib *)v18);
    CString::~CString((CString *)&szFile);
    v6 = 0;
LABEL_22:
    v44 = ++v8;
    v7 = v57;
  }
  if ( !*((_DWORD *)this + 34) )
    *((_DWORD *)this + 34) = v58;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b640  mov     [rsp+arg_8], rbx
0x18000b645  mov     [rsp+arg_10], rsi
0x18000b64a  push    rdi
0x18000b64b  push    r12
0x18000b64d  push    r13
0x18000b64f  push    r14
0x18000b651  push    r15
0x18000b653  sub     rsp, 1D0h
0x18000b65a  mov     rax, cs:__security_cookie
0x18000b661  xor     rax, rsp
0x18000b664  mov     [rsp+1F8h+var_38], rax
0x18000b66c  mov     [rsp+1F8h+var_F8], r9
0x18000b674  mov     [rsp+1F8h+var_118], edx
0x18000b67b  mov     rdi, rcx
0x18000b67e  xor     ebx, ebx
0x18000b680  mov     esi, ebx
0x18000b682  xor     edx, edx; Val
0x18000b684  mov     r8d, 88h; Size
0x18000b68a  lea     rcx, [rsp+1F8h+ReOpenBuff]; void *
0x18000b692  call    memset_0
0x18000b697  mov     [rsp+1F8h+var_168], ebx
0x18000b69e  mov     [rsp+1F8h+var_154], ebx
0x18000b6a5  mov     eax, [rdi+58h]
0x18000b6a8  mov     [rsp+1F8h+var_158], eax
0x18000b6af  mov     r13d, ebx
0x18000b6b2  mov     [rsp+1F8h+var_1A8], ebx
0x18000b6b6  lea     r15d, [rbx+1]
0x18000b6ba  mov     r12d, 2
0x18000b6c0  cmp     r13d, eax
0x18000b6c3  jge     loc_18000BF0C
0x18000b6c9  movsxd  r14, r13d
0x18000b6cc  mov     [rsp+1F8h+var_1A0], r14
0x18000b6d1  mov     rax, [rdi+50h]
0x18000b6d5  mov     rcx, [rax+r14*8]
0x18000b6d9  mov     rax, [rcx]
0x18000b6dc  mov     qword ptr [rsp+1F8h+var_148], rax
0x18000b6e4  xorps   xmm0, xmm0
0x18000b6e7  movdqu  [rsp+1F8h+var_148+8], xmm0
0x18000b6f0  mov     dword ptr [rsp+1F8h+var_130], r15d
0x18000b6f8  lea     rcx, [rsp+1F8h+var_148]
0x18000b700  call    ??BStr@@QEAAPEBDXZ; Str::operator char const *(void)
0x18000b705  mov     rcx, rax; lpFileName
0x18000b708  mov     r8d, 4000h; uStyle
0x18000b70e  lea     rdx, [rsp+1F8h+ReOpenBuff]; lpReOpenBuff
0x18000b716  call    cs:__imp_OpenFile
0x18000b71c  mov     ebx, eax
0x18000b71e  lea     rcx, [rsp+1F8h+var_148]; this
0x18000b726  call    ??1Str@@QEAA@XZ; Str::~Str(void)
0x18000b72b  cmp     ebx, 0FFFFFFFFh
0x18000b72e  jz      short loc_18000B73F
0x18000b730  cmp     [rsp+1F8h+ReOpenBuff.nErrCode], r12w
0x18000b739  jnz     loc_18000B7FE
0x18000b73f  mov     rax, [rdi+50h]
0x18000b743  mov     rcx, [rax+r14*8]
0x18000b747  xor     ebx, ebx
0x18000b749  mov     [rsp+1F8h+hTemplateFile], rbx; hTemplateFile
0x18000b74e  mov     [rsp+1F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000b756  mov     [rsp+1F8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000b75e  xor     r9d, r9d; lpSecurityAttributes
0x18000b761  mov     r8d, r15d; dwShareMode
0x18000b764  mov     edx, 80000000h; dwDesiredAccess
0x18000b769  mov     rcx, [rcx]; lpFileName
0x18000b76c  call    cs:__imp_CreateFileW
0x18000b772  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b776  jnz     short loc_18000B7F3
0x18000b778  mov     dword ptr [rsp+1F8h+var_148], ebx
0x18000b77f  lea     eax, [rbx+16h]
0x18000b782  mov     word ptr [rsp+1F8h+var_148+4], ax
0x18000b78a  mov     dword ptr [rsp+1F8h+var_148+8], 8000156Eh
0x18000b795  mov     rax, [rdi+50h]
0x18000b799  mov     rcx, [rax+r14*8]
0x18000b79d  mov     r9, [rcx]; unsigned __int16 *
0x18000b7a0  mov     [rsp+1F8h+var_138], r9
0x18000b7a8  mov     [rsp+1F8h+var_130], rbx
0x18000b7b0  mov     [rsp+1F8h+var_128], rbx
0x18000b7b8  mov     [rsp+1F8h+var_120], ebx
0x18000b7bf  mov     [rsp+1F8h+var_11C], r15d
0x18000b7c7  mov     r8d, 420h; unsigned int
0x18000b7cd  lea     rdx, aComComplusSrcC_3; "com\\complus\\src\\comcat\\registrar\\c"...
0x18000b7d4  lea     rcx, [rsp+1F8h+var_148]; this
0x18000b7dc  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000b7e1  mov     rax, [rdi+50h]
0x18000b7e5  mov     rcx, [rax+r14*8]
0x18000b7e9  bts     dword ptr [rcx+0Ch], 8
0x18000b7ee  jmp     loc_18000B9E0
0x18000b7f3  mov     rcx, rax; hObject
0x18000b7f6  call    cs:__imp_CloseHandle
0x18000b7fc  jmp     short loc_18000B800
0x18000b7fe  xor     ebx, ebx
0x18000b800  mov     rax, [rdi+50h]
0x18000b804  mov     rdx, [rax+r14*8]; struct FileInfo1 *
0x18000b808  cmp     [rdx+8], r15d
0x18000b80c  jnz     loc_18000B8DD
0x18000b812  mov     [rsp+1F8h+var_160], 80004005h
0x18000b81d  lea     rax, [rsp+1F8h+var_160]
0x18000b825  mov     qword ptr [rsp+1F8h+dwCreationDisposition], rax; int *
0x18000b82a  lea     r9, [rsp+1F8h+var_168]; unsigned int *
0x18000b832  mov     r8d, 0Fh; unsigned int
0x18000b838  mov     rcx, rdi; this
0x18000b83b  call    ?TestUserDll@CCOMComponentRegistrar@@AEAAJPEAUFileInfo1@@KPEAKPEAJ@Z; CCOMComponentRegistrar::TestUserDll(FileInfo1 *,ulong,ulong *,long *)
0x18000b840  mov     esi, eax
0x18000b842  test    eax, eax
0x18000b844  js      loc_18000BF21
0x18000b84a  test    byte ptr [rsp+1F8h+var_168], r15b
0x18000b852  jnz     short loc_18000B8D1
0x18000b854  mov     dword ptr [rsp+1F8h+var_148], ebx
0x18000b85b  mov     eax, 16h
0x18000b860  mov     word ptr [rsp+1F8h+var_148+4], ax
0x18000b868  mov     dword ptr [rsp+1F8h+var_148+8], 80001570h
0x18000b873  mov     rcx, [rdi+50h]
0x18000b877  mov     rdx, [rcx+r14*8]
0x18000b87b  mov     r9, [rdx]; unsigned __int16 *
0x18000b87e  mov     [rsp+1F8h+var_138], r9
0x18000b886  mov     [rsp+1F8h+var_130], rbx
0x18000b88e  mov     [rsp+1F8h+var_128], rbx
0x18000b896  mov     [rsp+1F8h+var_120], ebx
0x18000b89d  mov     [rsp+1F8h+var_11C], r15d
0x18000b8a5  mov     r8d, 439h; unsigned int
0x18000b8ab  lea     rdx, aComComplusSrcC_3; "com\\complus\\src\\comcat\\registrar\\c"...
0x18000b8b2  lea     rcx, [rsp+1F8h+var_148]; this
0x18000b8ba  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000b8bf  mov     rax, [rdi+50h]
0x18000b8c3  mov     rcx, [rax+r14*8]
0x18000b8c7  bts     dword ptr [rcx+0Ch], 7
0x18000b8cc  jmp     loc_18000B9E0
0x18000b8d1  mov     rax, [rdi+50h]
0x18000b8d5  mov     rcx, [rax+r14*8]
0x18000b8d9  or      [rcx+0Ch], r15d
0x18000b8dd  mov     r15d, ebx
0x18000b8e0  mov     [rsp+1F8h+var_1A4], r15d
0x18000b8e5  mov     rax, [rdi+50h]
0x18000b8e9  mov     rax, [rax+r14*8]
0x18000b8ed  cmp     r15d, [rax+20h]
0x18000b8f1  jl      loc_18000B9F4
0x18000b8f7  mov     ecx, 28h ; '('; cb
0x18000b8fc  call    cs:__imp_CoTaskMemAlloc
0x18000b902  mov     rsi, rax
0x18000b905  mov     qword ptr [rsp+1F8h+var_160], rax
0x18000b90d  test    rax, rax
0x18000b910  jz      loc_18000BEAB
0x18000b916  mov     [rax], rbx
0x18000b919  mov     [rax+10h], rbx
0x18000b91d  mov     [rax+18h], rbx
0x18000b921  mov     [rax+20h], ebx
0x18000b924  test    rax, rax
0x18000b927  jz      loc_18000BEAB
0x18000b92d  lea     rcx, [rsp+1F8h+szFile]
0x18000b935  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x18000b93b  nop
0x18000b93c  mov     rax, [rdi]
0x18000b93f  lea     r9, [rsp+1F8h+szFile]
0x18000b947  mov     r8d, r15d
0x18000b94a  mov     edx, r13d
0x18000b94d  mov     rcx, rdi
0x18000b950  mov     rax, [rax+60h]
0x18000b954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b959  test    eax, eax
0x18000b95b  jnz     short loc_18000B9C1
0x18000b95d  mov     rdx, [rsp+1F8h+szFile]; szFile
0x18000b965  mov     rcx, rsi; pptlib
0x18000b968  call    ?Load@CComPlusTypelib@@QEAAJPEBG@Z; CComPlusTypelib::Load(ushort const *)
0x18000b96d  test    eax, eax
0x18000b96f  jnz     short loc_18000B9C1
0x18000b971  mov     rax, [rdi+50h]
0x18000b975  mov     rcx, [rax+r14*8]
0x18000b979  or      dword ptr [rcx+0Ch], 10h
0x18000b97d  mov     rax, [rdi+50h]
0x18000b981  mov     rbx, [rax+r14*8]
0x18000b985  movsxd  r14, dword ptr [rbx+20h]
0x18000b989  test    r14d, r14d
0x18000b98c  js      short loc_18000B9AA
0x18000b98e  lea     edx, [r14+1]
0x18000b992  lea     rcx, [rbx+10h]
0x18000b996  call    ?SetSize@?$CArray@V?$CPtr@VCComPlusTypelib@@@@PEAVCComPlusTypelib@@@@QEAAXHH@Z; CArray<CPtr<CComPlusTypelib>,CComPlusTypelib *>::SetSize(int,int)
0x18000b99b  mov     rcx, r14
0x18000b99e  add     rcx, rcx
0x18000b9a1  mov     rax, [rbx+18h]
0x18000b9a5  mov     [rax+rcx*8+8], rsi
0x18000b9aa  lea     rcx, [rsp+1F8h+szFile]
0x18000b9b2  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18000b9b8  mov     r14, [rsp+1F8h+var_1A0]
0x18000b9bd  xor     ebx, ebx
0x18000b9bf  jmp     short loc_18000BA03
0x18000b9c1  mov     rcx, rsi; this
0x18000b9c4  call    ??_GCComPlusTypelib@@QEAAPEAXI@Z; CComPlusTypelib::`scalar deleting destructor'(uint)
0x18000b9c9  nop
0x18000b9ca  lea     rcx, [rsp+1F8h+szFile]
0x18000b9d2  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18000b9d8  mov     esi, ebx
0x18000b9da  mov     r15d, 1
0x18000b9e0  add     r13d, r15d
0x18000b9e3  mov     [rsp+1F8h+var_1A8], r13d
0x18000b9e8  mov     eax, [rsp+1F8h+var_158]
0x18000b9ef  jmp     loc_18000B6BA
0x18000b9f4  movsxd  rcx, r15d
0x18000b9f7  add     rcx, rcx
0x18000b9fa  mov     rax, [rax+18h]
0x18000b9fe  mov     rsi, [rax+rcx*8+8]
0x18000ba03  mov     rax, [rdi]
0x18000ba06  mov     r8d, r15d
0x18000ba09  mov     edx, r13d
0x18000ba0c  mov     rcx, rdi
0x18000ba0f  mov     rax, [rax+70h]
0x18000ba13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba18  test    eax, eax
0x18000ba1a  js      short loc_18000BA86
0x18000ba1c  mov     [rsp+1F8h+var_188], ebx
0x18000ba20  xor     r8d, r8d; int
0x18000ba23  lea     rdx, [rsp+1F8h+var_188]; unsigned int *
0x18000ba28  mov     rcx, rsi; this
0x18000ba2b  call    ?GetChildCount@CComPlusTypelib@@QEAAJPEAKH@Z; CComPlusTypelib::GetChildCount(ulong *,int)
0x18000ba30  test    eax, eax
0x18000ba32  jnz     short loc_18000BA86
0x18000ba34  cmp     [rsp+1F8h+var_188], ebx
0x18000ba38  jbe     short loc_18000BA46
0x18000ba3a  mov     rax, [rdi+50h]
0x18000ba3e  mov     rcx, [rax+r14*8]
0x18000ba42  or      dword ptr [rcx+0Ch], 8
0x18000ba46  mov     eax, ebx
0x18000ba48  mov     [rsp+1F8h+var_160], eax
0x18000ba4f  cmp     eax, [rsp+1F8h+var_188]
0x18000ba53  jnb     loc_18000BF04
0x18000ba59  mov     [rsp+1F8h+var_198], 1
0x18000ba61  mov     [rsp+1F8h+var_190], rbx
0x18000ba66  xor     r9d, r9d; int
0x18000ba69  lea     r8, [rsp+1F8h+var_190]; struct CComPlusObject **
0x18000ba6e  mov     edx, eax; unsigned int
0x18000ba70  mov     rcx, rsi; this
0x18000ba73  call    ?GetChild@CComPlusTypelib@@QEAAJKPEAPEAVCComPlusObject@@H@Z; CComPlusTypelib::GetChild(ulong,CComPlusObject * *,int)
0x18000ba78  test    eax, eax
0x18000ba7a  jz      short loc_18000BAC0
0x18000ba7c  lea     rcx, [rsp+1F8h+var_198]
0x18000ba81  call    ??1?$CPtr@VCRegDBProvider@@@@QEAA@XZ; CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>(void)
0x18000ba86  mov     rax, [rdi+50h]
0x18000ba8a  mov     rcx, [rax+r14*8]
0x18000ba8e  bts     dword ptr [rcx+0Ch], 0Ah
0x18000ba93  mov     ebx, [rdi+78h]
0x18000ba96  sub     ebx, 1
0x18000ba99  js      loc_18000BF02
0x18000ba9f  mov     rax, [rdi+70h]
0x18000baa3  mov     rdx, [rax+rbx*8]
0x18000baa7  cmp     r13d, [rdx+18h]
0x18000baab  jnz     short loc_18000BA96
0x18000baad  cmp     r15d, [rdx+1Ch]
0x18000bab1  jnz     short loc_18000BA96
0x18000bab3  lea     rcx, [rdi+68h]
0x18000bab7  mov     edx, ebx
0x18000bab9  call    ?RemoveAt@?$CArray@PEAUCompInfo1@@AEBQEAU1@@@QEAAXHH@Z; CArray<CompInfo1 *,CompInfo1 * const &>::RemoveAt(int,int)
0x18000babe  jmp     short loc_18000BA96
0x18000bac0  xorps   xmm0, xmm0
0x18000bac3  movups  [rsp+1F8h+var_D8], xmm0
0x18000bacb  mov     r12, [rsp+1F8h+var_190]
0x18000bad0  mov     rax, [r12]
0x18000bad4  lea     rdx, [rsp+1F8h+var_D8]
0x18000badc  mov     rcx, r12
0x18000badf  mov     rax, [rax+30h]
0x18000bae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bae8  test    eax, eax
0x18000baea  jnz     short loc_18000BA7C
0x18000baec  mov     r8, [rsp+1F8h+var_F8]
0x18000baf4  test    r8, r8
0x18000baf7  jz      short loc_18000BB4C
0x18000baf9  movaps  xmm0, [rsp+1F8h+var_D8]
0x18000bb01  movdqa  [rsp+1F8h+var_148], xmm0
0x18000bb0a  mov     ecx, ebx
0x18000bb0c  cmp     ecx, [rsp+1F8h+arg_20]
0x18000bb13  jnb     loc_18000BC57
0x18000bb19  mov     eax, ecx
0x18000bb1b  lea     rdx, [rax+rax*4]
0x18000bb1f  mov     rax, [r8+rdx*4]
0x18000bb23  sub     rax, qword ptr [rsp+1F8h+var_148]
0x18000bb2b  jnz     short loc_18000BB3A
0x18000bb2d  mov     rax, [r8+rdx*4+8]
0x18000bb32  sub     rax, qword ptr [rsp+1F8h+var_148+8]
0x18000bb3a  test    rax, rax
0x18000bb3d  jz      short loc_18000BB43
0x18000bb3f  inc     ecx
0x18000bb41  jmp     short loc_18000BB0C
0x18000bb43  mov     dword ptr [r8+rdx*4+10h], 1
0x18000bb4c  mov     [rsp+1F8h+bstrString], rbx
0x18000bb54  mov     rax, [r12]
0x18000bb58  mov     qword ptr [rsp+1F8h+dwCreationDisposition], rbx
0x18000bb5d  xor     r9d, r9d
0x18000bb60  xor     r8d, r8d
0x18000bb63  lea     rdx, [rsp+1F8h+bstrString]
0x18000bb6b  mov     rcx, r12
0x18000bb6e  mov     rax, [rax+28h]
0x18000bb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb77  test    eax, eax
0x18000bb79  jnz     loc_18000BA7C
0x18000bb7f  mov     [rsp+1F8h+var_170], rbx
0x18000bb87  mov     rdx, [rdi]
0x18000bb8a  mov     rax, [rdi+50h]
0x18000bb8e  mov     rcx, [rax+r14*8]
0x18000bb92  mov     r9d, [rcx+0Ch]
0x18000bb96  and     r9d, 200000h
0x18000bb9d  bts     r9d, 0Dh
0x18000bba2  shr     r9d, 0Dh
0x18000bba6  mov     rax, [rdx+68h]
0x18000bbaa  lea     rcx, GUID_NULL
  ... truncated ...
```
