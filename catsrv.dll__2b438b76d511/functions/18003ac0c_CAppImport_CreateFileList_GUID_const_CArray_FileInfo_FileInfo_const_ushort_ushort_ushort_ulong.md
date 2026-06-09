# CAppImport::CreateFileList(_GUID const &,CArray<FileInfo *,FileInfo * const &> *,ushort *,ushort *,ushort *,ulong)

- ea: `0x18003ac0c`
- end: `0x18003b300`
- name: `?CreateFileList@CAppImport@@AEAAJAEBU_GUID@@PEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAG22K@Z`
- size: `1780`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const unsigned __int16 *, wchar_t *String1, unsigned __int16 *String2, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003caa0`

## callees

- `0x18000a01c`
- `0x18001a6c8`
- `0x18001ec1c`
- `0x18003a604`
- `0x18003a77c`
- `0x18003aa60`
- `0x18003ac0c`
- `0x18003c0f0`
- `0x18003c2c8`
- `0x18003d71c`
- `0x18003e5e4`
- `0x180042bb8`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18003b033`
- `msvcrt!wcsrchr` at `0x18003b033`
- `msvcrt!_wcsicmp` at `0x18003ac76`
- `msvcrt!_wcsicmp` at `0x18003ac76`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003ad0d`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003ad0d`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003ae6a`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003afc8`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003b159`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003b1d0`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003b293`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003b2ae`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003ae6a`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003afc8`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003b159`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003b1d0`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003b293`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003b2ae`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18003af0b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18003af5b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18003b04b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18003b197`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18003af0b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18003af5b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18003b04b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18003b197`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18003ae21`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18003afa3`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18003ae21`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18003afa3`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003b12d`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003b264`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003b12d`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003b264`
- `MfcSubs!??YCString@@QEAAAEBV0@PEBG@Z` at `0x18003af1d`
- `MfcSubs!??YCString@@QEAAAEBV0@PEBG@Z` at `0x18003af2d`
- `MfcSubs!??YCString@@QEAAAEBV0@PEBG@Z` at `0x18003af1d`
- `MfcSubs!??YCString@@QEAAAEBV0@PEBG@Z` at `0x18003af2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003b183`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003b183`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003af38`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003af38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b0be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b205`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b0be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b205`

## pseudocode

```c
__int64 __fastcall CAppImport::CreateFileList(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        wchar_t *String1,
        unsigned __int16 *String2,
        char a7)
{
  int SimpleTableDispenser; // edi
  int v12; // eax
  int v13; // r14d
  int v14; // eax
  unsigned int v15; // edx
  CAppImport *v16; // rcx
  unsigned int v17; // edx
  CAppImport *v18; // rcx
  CAppImport *v19; // rcx
  int v20; // r9d
  wchar_t *v21; // rax
  CAppImport *v22; // rcx
  CAppImport *v23; // rcx
  FileInfo *v24; // rax
  unsigned int v25; // edx
  FileInfo *v26; // rdi
  __int64 v27; // rsi
  unsigned int v28; // edx
  CAppImport *v29; // rcx
  unsigned int v30; // edx
  FileInfo *v31; // rax
  FileInfo *v32; // rdi
  __int64 v33; // rsi
  unsigned int v35; // edx
  LPCWSTR lpFileName; // [rsp+50h] [rbp-4F8h] BYREF
  DllInfo *v37; // [rsp+58h] [rbp-4F0h]
  _BYTE v38[8]; // [rsp+60h] [rbp-4E8h] BYREF
  unsigned __int16 *v39; // [rsp+68h] [rbp-4E0h] BYREF
  int v40; // [rsp+70h] [rbp-4D8h] BYREF
  FileInfo *v41; // [rsp+78h] [rbp-4D0h]
  __int64 v42; // [rsp+80h] [rbp-4C8h] BYREF
  int v43; // [rsp+88h] [rbp-4C0h] BYREF
  int v44; // [rsp+8Ch] [rbp-4BCh] BYREF
  _DWORD *v45; // [rsp+90h] [rbp-4B8h] BYREF
  int v46; // [rsp+98h] [rbp-4B0h] BYREF
  FileInfo *v47; // [rsp+A0h] [rbp-4A8h]
  unsigned __int16 *v48; // [rsp+A8h] [rbp-4A0h]
  const unsigned __int16 *v49; // [rsp+B0h] [rbp-498h] BYREF
  int v50; // [rsp+B8h] [rbp-490h]
  int v51; // [rsp+BCh] [rbp-48Ch]
  int v52; // [rsp+C0h] [rbp-488h]
  int v53; // [rsp+C4h] [rbp-484h]
  __int64 v54; // [rsp+C8h] [rbp-480h]
  __int64 v55; // [rsp+D0h] [rbp-478h]
  int v56; // [rsp+D8h] [rbp-470h]
  int v57; // [rsp+DCh] [rbp-46Ch]
  FileInfo *v58; // [rsp+E0h] [rbp-468h]
  FileInfo *v59; // [rsp+E8h] [rbp-460h]
  unsigned __int16 v60[264]; // [rsp+F0h] [rbp-458h] BYREF
  wchar_t Str[264]; // [rsp+300h] [rbp-248h] BYREF

  v48 = String2;
  LODWORD(v37) = 0;
  if ( (a7 & 1) != 0 )
    LODWORD(v37) = _wcsicmp(String1, String2) == 0;
  v49 = a4;
  v50 = 0;
  v51 = -268435455;
  v52 = 130;
  v53 = 2 * safe_lstrlenW(a4) + 2;
  v54 = a2;
  v55 = 0;
  v56 = 72;
  v57 = 16;
  v42 = 0;
  if ( !*(_QWORD *)(a1 + 72) )
  {
    v39 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v39);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_8;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), (signed __int64)v39, 0) )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v12 = memcmp_0(tidCOMSERVICES_DLLNAMES_EXPORT, &TID_APPLICATION, 0x10u);
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, const unsigned __int16 **, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 72) + 24LL))(
                           *(_QWORD *)(a1 + 72),
                           didCOMSERVICES,
                           tidCOMSERVICES_DLLNAMES_EXPORT,
                           &v49,
                           1,
                           1,
                           v12 != 0 ? 7 : 5,
                           &v42);
LABEL_8:
  if ( !SimpleTableDispenser )
  {
    if ( !v42 )
      return (unsigned int)-2147024882;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 24LL))(v42);
    if ( SimpleTableDispenser )
      goto LABEL_60;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 32LL))(v42);
    if ( SimpleTableDispenser )
      goto LABEL_60;
    v13 = (int)v37;
    while ( 1 )
    {
      v44 = 0;
      v43 = 0;
      v39 = 0;
      v45 = 0;
      CString::CString((CString *)&lpFileName);
      v40 = 1;
      v41 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 40LL))(v42);
      SimpleTableDispenser = v14;
      if ( v14 == -2146367487 )
      {
        SimpleTableDispenser = 0;
        goto LABEL_17;
      }
      if ( v14 )
        goto LABEL_17;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, unsigned __int16 **))(*(_QWORD *)v42 + 64LL))(
                               v42,
                               1,
                               &v44,
                               &v43,
                               &v39);
      if ( SimpleTableDispenser )
        goto LABEL_17;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, _DWORD **))(*(_QWORD *)v42 + 64LL))(
                               v42,
                               2,
                               &v44,
                               &v43,
                               &v45);
      if ( SimpleTableDispenser )
        goto LABEL_17;
      if ( CAppImport::IsComPlusFile(v16, v39) )
      {
        if ( (a7 & 1) != 0 )
        {
          CString::operator=(&lpFileName, String1);
          CString::operator+=(&lpFileName, L"\\");
          CString::operator+=(&lpFileName, v39);
          if ( !DeleteFileW(lpFileName) )
            GetLastError();
        }
      }
      else
      {
        CString::operator=(&lpFileName, v39);
        if ( (a7 & 1) != 0 )
        {
          Str[0] = 0;
          if ( (a7 & 0xC) == 8 )
          {
            if ( *v45 == 1 )
            {
              CString::CString((CString *)v38);
              SimpleTableDispenser = StringCchCopyW(v60, 0x104u, String1);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_30;
              SimpleTableDispenser = StringCchCatW(v60, 0x104u, L"\\");
              if ( SimpleTableDispenser < 0 )
                goto LABEL_30;
              SimpleTableDispenser = StringCchCatW(v60, 0x104u, v39);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_30;
              SimpleTableDispenser = CAppImport::GetSoapCacheName(v19, v60, Str, v20);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_30;
              v21 = wcsrchr(Str, 0x5Cu);
              if ( v21 )
              {
                CString::operator=(v38, v21 + 1);
                SimpleTableDispenser = StringCchCopyW(v60, 0x104u, Str);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_30;
                CAppImport::CheckOrCreateDirectory(v22, v60, 0);
                if ( !(unsigned int)CAppImport::GetNameAndCopy(v23, (struct CString *)v38, String1, v60, 1) )
                {
                  v46 = 1;
                  v47 = 0;
                  v24 = (FileInfo *)CoTaskMemAlloc(0x10u);
                  v58 = v24;
                  if ( v24 )
                    v26 = FileInfo::FileInfo(v24);
                  else
                    v26 = 0;
                  v37 = v26;
                  v47 = v26;
                  if ( !v26 )
                  {
                    SimpleTableDispenser = -2147024882;
                    CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v46, v25);
LABEL_30:
                    CString::~CString((CString *)v38);
LABEL_17:
                    CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v40, v15);
                    CString::~CString((CString *)&lpFileName);
                    break;
                  }
                  v27 = *(int *)(a3 + 16);
                  if ( (int)v27 >= 0 )
                  {
                    try
                    {
                      CArray<DllInfo *,DllInfo * const &>::SetSize(a3, (unsigned int)(v27 + 1));
                      *(_QWORD *)(*(_QWORD *)(a3 + 8) + 8 * v27) = v26;
                    }
                    catch ( ... )
                    {
                      DllInfo::`scalar deleting destructor'(v37);
                      LODWORD(v37) = -2147024882;
                      CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v46, v35);
                      CString::~CString((CString *)v38);
                      goto LABEL_59;
                    }
                  }
                  CString::operator=(v26, v38);
                  *((_QWORD *)v26 + 1) = 8;
                  v46 = 0;
                  CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v46, v28);
                }
              }
              CString::~CString((CString *)v38);
            }
            else if ( *v45 == 8 )
            {
              goto LABEL_58;
            }
          }
          if ( v13 )
          {
            if ( (unsigned int)CAppImport::VerifyFileExists(v18, (struct CString *)&lpFileName, String1) )
            {
              if ( !GetSystemDirectoryW(Str, 0x104u)
                || (CString::operator=(&lpFileName, v39),
                    (unsigned int)CAppImport::VerifyFileExists(v29, (struct CString *)&lpFileName, Str)) )
              {
                SimpleTableDispenser = -2146368476;
                goto LABEL_17;
              }
            }
          }
          else
          {
            SimpleTableDispenser = CAppImport::GetNameAndCopy(v18, (struct CString *)&lpFileName, String1, v48, a7 & 2);
            if ( SimpleTableDispenser )
              goto LABEL_17;
          }
        }
        v31 = (FileInfo *)CoTaskMemAlloc(0x10u);
        v59 = v31;
        if ( v31 )
          v32 = FileInfo::FileInfo(v31);
        else
          v32 = 0;
        v37 = v32;
        v41 = v32;
        if ( !v32 )
        {
          SimpleTableDispenser = -2147024882;
          goto LABEL_17;
        }
        v33 = *(int *)(a3 + 16);
        if ( (int)v33 >= 0 )
        {
          try
          {
            CArray<DllInfo *,DllInfo * const &>::SetSize(a3, (unsigned int)(v33 + 1));
            *(_QWORD *)(*(_QWORD *)(a3 + 8) + 8 * v33) = v32;
          }
          catch ( ... )
          {
            DllInfo::`scalar deleting destructor'(v37);
            LODWORD(v37) = -2147024882;
LABEL_59:
            CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v40, v30);
            CString::~CString((CString *)&lpFileName);
            SimpleTableDispenser = (int)v37;
            break;
          }
        }
        CString::operator=(v32, &lpFileName);
        *((_QWORD *)v32 + 1) = (unsigned int)*v45;
        v40 = 0;
      }
LABEL_58:
      CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v40, v17);
      CString::~CString((CString *)&lpFileName);
    }
  }
LABEL_60:
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18003ac0c  mov     [rsp+arg_8], rbx
0x18003ac11  mov     [rsp+arg_18], rsi
0x18003ac16  push    rdi
0x18003ac17  push    r12
0x18003ac19  push    r13
0x18003ac1b  push    r14
0x18003ac1d  push    r15
0x18003ac1f  sub     rsp, 520h
0x18003ac26  mov     rax, cs:__security_cookie
0x18003ac2d  xor     rax, rsp
0x18003ac30  mov     [rsp+548h+var_38], rax
0x18003ac38  mov     rdi, r9
0x18003ac3b  mov     r15, r8
0x18003ac3e  mov     r14, rdx
0x18003ac41  mov     rsi, rcx
0x18003ac44  mov     r12, [rsp+548h+String1]
0x18003ac4c  mov     rax, [rsp+548h+String2]
0x18003ac54  mov     [rsp+548h+var_4A0], rax
0x18003ac5c  xor     ebx, ebx
0x18003ac5e  mov     dword ptr [rsp+548h+var_4F0], ebx
0x18003ac62  mov     r13d, [rsp+548h+arg_30]
0x18003ac6a  and     r13d, 1
0x18003ac6e  jz      short loc_18003AC8A
0x18003ac70  mov     rdx, rax; String2
0x18003ac73  mov     rcx, r12; String1
0x18003ac76  call    cs:__imp__wcsicmp
0x18003ac7c  mov     r8d, ebx
0x18003ac7f  test    eax, eax
0x18003ac81  setz    r8b
0x18003ac85  mov     dword ptr [rsp+548h+var_4F0], r8d
0x18003ac8a  mov     [rsp+548h+var_498], rdi
0x18003ac92  mov     [rsp+548h+var_490], ebx
0x18003ac99  mov     [rsp+548h+var_48C], 0F0000001h
0x18003aca4  mov     [rsp+548h+var_488], 82h
0x18003acaf  mov     rcx, rdi; unsigned __int16 *
0x18003acb2  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003acb7  lea     eax, ds:2[rax*2]
0x18003acbe  mov     [rsp+548h+var_484], eax
0x18003acc5  mov     [rsp+548h+var_480], r14
0x18003accd  mov     [rsp+548h+var_478], rbx
0x18003acd5  mov     [rsp+548h+var_470], 48h ; 'H'
0x18003ace0  mov     r14d, 10h
0x18003ace6  mov     [rsp+548h+var_46C], r14d
0x18003acee  mov     [rsp+548h+var_4C8], rbx
0x18003acf6  cmp     [rsi+48h], rbx
0x18003acfa  jnz     short loc_18003AD3D
0x18003acfc  mov     [rsp+548h+var_4E0], rbx
0x18003ad01  lea     rdx, [rsp+548h+var_4E0]
0x18003ad06  lea     rcx, IID_ISimpleTableDispenser
0x18003ad0d  call    cs:__imp_GetSimpleTableDispenser
0x18003ad13  mov     edi, eax
0x18003ad15  test    eax, eax
0x18003ad17  js      loc_18003ADA4
0x18003ad1d  mov     rcx, [rsp+548h+var_4E0]
0x18003ad22  xor     eax, eax
0x18003ad24  lock cmpxchg [rsi+48h], rcx
0x18003ad2a  jz      short loc_18003AD3D
0x18003ad2c  mov     rcx, [rsp+548h+var_4E0]
0x18003ad31  mov     rax, [rcx]
0x18003ad34  mov     rax, [rax+10h]
0x18003ad38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad3d  mov     r8, r14; Size
0x18003ad40  lea     rdx, TID_APPLICATION; Buf2
0x18003ad47  lea     rcx, tidCOMSERVICES_DLLNAMES_EXPORT; Buf1
0x18003ad4e  call    memcmp_0
0x18003ad53  neg     eax
0x18003ad55  sbb     edx, edx
0x18003ad57  and     edx, 2
0x18003ad5a  add     edx, 5
0x18003ad5d  mov     rcx, [rsi+48h]
0x18003ad61  mov     rax, [rcx]
0x18003ad64  lea     r9, [rsp+548h+var_4C8]
0x18003ad6c  mov     [rsp+548h+var_510], r9
0x18003ad71  mov     [rsp+548h+var_518], edx
0x18003ad75  mov     edx, 1
0x18003ad7a  mov     [rsp+548h+var_520], edx
0x18003ad7e  mov     qword ptr [rsp+548h+var_528], rdx
0x18003ad83  lea     r9, [rsp+548h+var_498]
0x18003ad8b  lea     r8, tidCOMSERVICES_DLLNAMES_EXPORT
0x18003ad92  lea     rdx, didCOMSERVICES
0x18003ad99  mov     rax, [rax+18h]
0x18003ad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ada2  mov     edi, eax
0x18003ada4  test    edi, edi
0x18003ada6  jnz     loc_18003B2B8
0x18003adac  mov     rcx, [rsp+548h+var_4C8]
0x18003adb4  test    rcx, rcx
0x18003adb7  jnz     short loc_18003ADC3
0x18003adb9  mov     edi, 8007000Eh
0x18003adbe  jmp     loc_18003B2D1
0x18003adc3  mov     rax, [rcx]
0x18003adc6  mov     rax, [rax+18h]
0x18003adca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adcf  mov     edi, eax
0x18003add1  test    eax, eax
0x18003add3  jnz     loc_18003B2B8
0x18003add9  mov     rcx, [rsp+548h+var_4C8]
0x18003ade1  mov     rax, [rcx]
0x18003ade4  mov     rax, [rax+20h]
0x18003ade8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aded  mov     edi, eax
0x18003adef  test    eax, eax
0x18003adf1  jnz     loc_18003B2B8
0x18003adf7  mov     esi, 104h
0x18003adfc  mov     r14d, dword ptr [rsp+548h+var_4F0]
0x18003ae01  mov     [rsp+548h+var_4BC], ebx
0x18003ae08  mov     [rsp+548h+var_4C0], ebx
0x18003ae0f  mov     [rsp+548h+var_4E0], rbx
0x18003ae14  mov     [rsp+548h+var_4B8], rbx
0x18003ae1c  lea     rcx, [rsp+548h+lpFileName]
0x18003ae21  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x18003ae27  nop
0x18003ae28  mov     [rsp+548h+var_4D8], 1
0x18003ae30  mov     [rsp+548h+var_4D0], rbx
0x18003ae35  mov     rcx, [rsp+548h+var_4C8]
0x18003ae3d  mov     rax, [rcx]
0x18003ae40  mov     rax, [rax+28h]
0x18003ae44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae49  mov     edi, eax
0x18003ae4b  cmp     eax, 80110801h
0x18003ae50  jnz     short loc_18003AE56
0x18003ae52  mov     edi, ebx
0x18003ae54  jmp     short loc_18003AE5A
0x18003ae56  test    eax, eax
0x18003ae58  jz      short loc_18003AE75
0x18003ae5a  lea     rcx, [rsp+548h+var_4D8]
0x18003ae5f  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18003ae64  nop
0x18003ae65  lea     rcx, [rsp+548h+lpFileName]
0x18003ae6a  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003ae70  jmp     loc_18003B2B8
0x18003ae75  mov     rcx, [rsp+548h+var_4C8]
0x18003ae7d  mov     rax, [rcx]
0x18003ae80  lea     rdx, [rsp+548h+var_4E0]
0x18003ae85  mov     qword ptr [rsp+548h+var_528], rdx
0x18003ae8a  lea     r9, [rsp+548h+var_4C0]
0x18003ae92  lea     r8, [rsp+548h+var_4BC]
0x18003ae9a  mov     edx, 1
0x18003ae9f  mov     rax, [rax+40h]
0x18003aea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aea8  mov     edi, eax
0x18003aeaa  test    eax, eax
0x18003aeac  jnz     short loc_18003AE5A
0x18003aeae  mov     rcx, [rsp+548h+var_4C8]
0x18003aeb6  mov     rax, [rcx]
0x18003aeb9  lea     rdx, [rsp+548h+var_4B8]
0x18003aec1  mov     qword ptr [rsp+548h+var_528], rdx
0x18003aec6  lea     r9, [rsp+548h+var_4C0]
0x18003aece  lea     r8, [rsp+548h+var_4BC]
0x18003aed6  lea     edx, [rdi+2]
0x18003aed9  mov     rax, [rax+40h]
0x18003aedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aee2  mov     edi, eax
0x18003aee4  test    eax, eax
0x18003aee6  jnz     loc_18003AE5A
0x18003aeec  mov     rdx, [rsp+548h+var_4E0]; unsigned __int16 *
0x18003aef1  call    ?IsComPlusFile@CAppImport@@AEAAHPEBG@Z; CAppImport::IsComPlusFile(ushort const *)
0x18003aef6  test    eax, eax
0x18003aef8  jz      short loc_18003AF51
0x18003aefa  test    r13d, r13d
0x18003aefd  jz      loc_18003B283
0x18003af03  mov     rdx, r12
0x18003af06  lea     rcx, [rsp+548h+lpFileName]
0x18003af0b  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18003af11  lea     rdx, asc_18005D30C; "\\"
0x18003af18  lea     rcx, [rsp+548h+lpFileName]
0x18003af1d  call    cs:__imp_??YCString@@QEAAAEBV0@PEBG@Z; CString::operator+=(ushort const *)
0x18003af23  mov     rdx, [rsp+548h+var_4E0]
0x18003af28  lea     rcx, [rsp+548h+lpFileName]
0x18003af2d  call    cs:__imp_??YCString@@QEAAAEBV0@PEBG@Z; CString::operator+=(ushort const *)
0x18003af33  mov     rcx, [rsp+548h+lpFileName]; lpFileName
0x18003af38  call    cs:__imp_DeleteFileW
0x18003af3e  test    eax, eax
0x18003af40  jnz     loc_18003B283
0x18003af46  call    cs:__imp_GetLastError
0x18003af4c  jmp     loc_18003B283
0x18003af51  mov     rdx, [rsp+548h+var_4E0]
0x18003af56  lea     rcx, [rsp+548h+lpFileName]
0x18003af5b  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18003af61  test    r13d, r13d
0x18003af64  jz      loc_18003B200
0x18003af6a  mov     [rsp+548h+Str], bx
0x18003af72  mov     eax, [rsp+548h+arg_30]
0x18003af79  and     al, 0Ch
0x18003af7b  cmp     al, 8
0x18003af7d  jnz     loc_18003B15F
0x18003af83  mov     rax, [rsp+548h+var_4B8]
0x18003af8b  cmp     dword ptr [rax], 1
0x18003af8e  jz      short loc_18003AF9E
0x18003af90  cmp     dword ptr [rax], 8
0x18003af93  jnz     loc_18003B15F
0x18003af99  jmp     loc_18003B283
0x18003af9e  lea     rcx, [rsp+548h+var_4E8]
0x18003afa3  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x18003afa9  nop
0x18003afaa  mov     r8, r12; unsigned __int16 *
0x18003afad  mov     rdx, rsi; unsigned __int64
0x18003afb0  lea     rcx, [rsp+548h+var_458]; unsigned __int16 *
0x18003afb8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003afbd  mov     edi, eax
0x18003afbf  test    eax, eax
0x18003afc1  jns     short loc_18003AFD3
0x18003afc3  lea     rcx, [rsp+548h+var_4E8]
0x18003afc8  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003afce  jmp     loc_18003AE5A
0x18003afd3  lea     r8, asc_18005D30C; "\\"
0x18003afda  mov     rdx, rsi; unsigned __int64
0x18003afdd  lea     rcx, [rsp+548h+var_458]; unsigned __int16 *
0x18003afe5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003afea  mov     edi, eax
0x18003afec  test    eax, eax
0x18003afee  js      short loc_18003AFC3
0x18003aff0  mov     r8, [rsp+548h+var_4E0]; unsigned __int16 *
0x18003aff5  mov     rdx, rsi; unsigned __int64
0x18003aff8  lea     rcx, [rsp+548h+var_458]; unsigned __int16 *
0x18003b000  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b005  mov     edi, eax
0x18003b007  test    eax, eax
0x18003b009  js      short loc_18003AFC3
0x18003b00b  lea     r8, [rsp+548h+Str]; unsigned __int16 *
0x18003b013  lea     rdx, [rsp+548h+var_458]; unsigned __int16 *
0x18003b01b  call    ?GetSoapCacheName@CAppImport@@AEAAJPEAG0H@Z; CAppImport::GetSoapCacheName(ushort *,ushort *,int)
0x18003b020  mov     edi, eax
0x18003b022  test    eax, eax
0x18003b024  js      short loc_18003AFC3
0x18003b026  mov     edx, 5Ch ; '\'; Ch
0x18003b02b  lea     rcx, [rsp+548h+Str]; Str
0x18003b033  call    cs:__imp_wcsrchr
0x18003b039  test    rax, rax
0x18003b03c  jz      loc_18003B154
0x18003b042  lea     rdx, [rax+2]
0x18003b046  lea     rcx, [rsp+548h+var_4E8]
0x18003b04b  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18003b051  lea     r8, [rsp+548h+Str]; unsigned __int16 *
0x18003b059  mov     rdx, rsi; unsigned __int64
0x18003b05c  lea     rcx, [rsp+548h+var_458]; unsigned __int16 *
0x18003b064  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b069  mov     edi, eax
0x18003b06b  test    eax, eax
0x18003b06d  js      loc_18003AFC3
0x18003b073  xor     r8d, r8d; int
0x18003b076  lea     rdx, [rsp+548h+var_458]; unsigned __int16 *
0x18003b07e  call    ?CheckOrCreateDirectory@CAppImport@@AEAAJPEAGH@Z; CAppImport::CheckOrCreateDirectory(ushort *,int)
0x18003b083  mov     [rsp+548h+var_528], 1; int
0x18003b08b  lea     r9, [rsp+548h+var_458]; unsigned __int16 *
0x18003b093  mov     r8, r12; unsigned __int16 *
0x18003b096  lea     rdx, [rsp+548h+var_4E8]; struct CString *
0x18003b09b  call    ?GetNameAndCopy@CAppImport@@QEAAJAEAVCString@@PEAG1H@Z; CAppImport::GetNameAndCopy(CString &,ushort *,ushort *,int)
0x18003b0a0  test    eax, eax
0x18003b0a2  jnz     loc_18003B154
0x18003b0a8  mov     [rsp+548h+var_4B0], 1
0x18003b0b3  mov     [rsp+548h+var_4A8], rbx
0x18003b0bb  lea     ecx, [rax+10h]; cb
0x18003b0be  call    cs:__imp_CoTaskMemAlloc
0x18003b0c4  mov     [rsp+548h+var_468], rax
0x18003b0cc  test    rax, rax
0x18003b0cf  jz      short loc_18003B0DE
0x18003b0d1  mov     rcx, rax; this
0x18003b0d4  call    ??0FileInfo@@QEAA@XZ; FileInfo::FileInfo(void)
0x18003b0d9  mov     rdi, rax
0x18003b0dc  jmp     short loc_18003B0E1
0x18003b0de  mov     rdi, rbx
0x18003b0e1  mov     [rsp+548h+var_4F0], rdi
0x18003b0e6  mov     [rsp+548h+var_4A8], rdi
0x18003b0ee  test    rdi, rdi
0x18003b0f1  jnz     short loc_18003B10A
0x18003b0f3  mov     edi, 8007000Eh
0x18003b0f8  lea     rcx, [rsp+548h+var_4B0]
0x18003b100  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18003b105  jmp     loc_18003AFC3
0x18003b10a  movsxd  rsi, dword ptr [r15+10h]
0x18003b10e  test    esi, esi
0x18003b110  js      short loc_18003B125
0x18003b112  lea     edx, [rsi+1]
0x18003b115  mov     rcx, r15
0x18003b118  call    ?SetSize@?$CArray@PEAUDllInfo@@AEBQEAU1@@@QEAAXHH@Z; CArray<DllInfo *,DllInfo * const &>::SetSize(int,int)
0x18003b11d  mov     rax, [r15+8]
0x18003b121  mov     [rax+rsi*8], rdi
0x18003b125  lea     rdx, [rsp+548h+var_4E8]
0x18003b12a  mov     rcx, rdi
0x18003b12d  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18003b133  mov     qword ptr [rdi+8], 8
0x18003b13b  mov     [rsp+548h+var_4B0], ebx
0x18003b142  lea     rcx, [rsp+548h+var_4B0]
0x18003b14a  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18003b14f  mov     esi, 104h
0x18003b154  lea     rcx, [rsp+548h+var_4E8]
0x18003b159  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003b15f  mov     r8, r12; unsigned __int16 *
0x18003b162  lea     rdx, [rsp+548h+lpFileName]; struct CString *
0x18003b167  test    r14d, r14d
0x18003b16a  jz      short loc_18003B1DB
0x18003b16c  call    ?VerifyFileExists@CAppImport@@QEAAJAEAVCString@@PEAG@Z; CAppImport::VerifyFileExists(CString &,ushort *)
0x18003b171  test    eax, eax
0x18003b173  jz      loc_18003B200
0x18003b179  mov     edx, esi; uSize
0x18003b17b  lea     rcx, [rsp+548h+Str]; lpBuffer
0x18003b183  call    cs:__imp_GetSystemDirectoryW
0x18003b189  test    eax, eax
0x18003b18b  jz      short loc_18003B1B3
  ... truncated ...
```
