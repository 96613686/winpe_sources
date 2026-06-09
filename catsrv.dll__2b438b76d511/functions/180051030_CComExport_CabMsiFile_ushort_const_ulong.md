# CComExport::CabMsiFile(ushort const *,ulong)

- ea: `0x180051030`
- end: `0x1800513f0`
- name: `?CabMsiFile@CComExport@@IEAAJPEBGK@Z`
- size: `960`
- prototype: `__int64 __fastcall(CComExport *this, const unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180051a60`
- `0x180051f20`

## callees

- `0x180009ee0`
- `0x18002d540`
- `0x180051030`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800511ca`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800512d4`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800513b3`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800513bf`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800511ca`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800512d4`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800513b3`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800513bf`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180051181`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800512a2`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180051181`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800512a2`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x180051063`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18005106f`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x180051063`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18005106f`
- `MfcSubs!?Right@CString@@QEBA?AV1@H@Z` at `0x1800511af`
- `MfcSubs!?Right@CString@@QEBA?AV1@H@Z` at `0x1800511af`
- `MfcSubs!?ReverseFind@CString@@QEBAHG@Z` at `0x180051199`
- `MfcSubs!?ReverseFind@CString@@QEBAHG@Z` at `0x180051199`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x1800511be`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x1800512c8`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x1800511be`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x1800512c8`
- `MfcSubs!??H@YA?AVCString@@AEBV0@PEBG@Z` at `0x1800512b9`
- `MfcSubs!??H@YA?AVCString@@AEBV0@PEBG@Z` at `0x1800512b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005113d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005113d`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180051133`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180051133`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18005116f`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18005116f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800513a7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800513a7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800510b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800512df`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800510b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800512df`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180051213`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18005123b`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180051263`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18005128c`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180051213`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18005123b`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180051263`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18005128c`

## string_xrefs

- `0x180051351`: `msicab.inf`
- `0x1800511d5`: `msiexec.exe /i "%%EXTRACT_DIR%%\%s"`

## pseudocode

```c
__int64 __fastcall CComExport::CabMsiFile(CComExport *this, const unsigned __int16 *a2, char a3)
{
  signed int v5; // edi
  __int64 v6; // rbx
  signed int LastError; // eax
  UINT TempFileNameW; // eax
  int v9; // ebx
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v15; // [rsp+30h] [rbp-668h] BYREF
  __int64 v16; // [rsp+38h] [rbp-660h] BYREF
  __int64 v17; // [rsp+40h] [rbp-658h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-650h] BYREF
  WCHAR Buffer; // [rsp+50h] [rbp-648h] BYREF
  _BYTE v20[526]; // [rsp+52h] [rbp-646h] BYREF
  WCHAR String; // [rsp+260h] [rbp-438h] BYREF
  _BYTE v22[1038]; // [rsp+262h] [rbp-436h] BYREF

  CString::CString((CString *)&v16);
  CString::CString((CString *)&lpFileName);
  Buffer = 0;
  memset_0(v20, 0, 0x206u);
  String = 0;
  memset_0(v22, 0, sizeof(v22));
  v17 = 0;
  v15 = 0;
  if ( GetFileAttributesW(a2) == -1 )
  {
    v5 = -2147418113;
    goto LABEL_22;
  }
  v5 = ATL::CComObject<CMakeCab>::CreateInstance(&v15);
  if ( v5 >= 0 )
  {
    v6 = v15;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &IID_IMakeCab, &v17);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 >= 0 )
    {
      if ( !GetTempPathW(0x104u, &Buffer) || (TempFileNameW = GetTempFileNameW(&Buffer, L"INF", 0, &Buffer)) == 0 )
      {
LABEL_6:
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_22;
      }
      try
      {
        CString::operator=(&v16, a2);
        v9 = *(_DWORD *)(v16 - 8);
        v10 = CString::ReverseFind((CString *)&v16, 0x5Cu);
        v11 = CString::Right(&v16, &v15, (unsigned int)(v9 - v10 - 1));
        CString::operator=(&v16, v11);
        CString::~CString((CString *)&v15);
        v12 = StringCchPrintfW(&String, 0x208u, L"msiexec.exe /i \"%%EXTRACT_DIR%%\\%s\"", v16);
      }
      catch ( ... )
      {
        LODWORD(v15) = -2147024882;
        v5 = -2147024882;
        goto LABEL_22;
      }
      v5 = v12;
      if ( v12 >= 0 )
      {
        if ( WritePrivateProfileStringW(L"version", L"signature", L"\"$CHICAGO$\"", &Buffer)
          && WritePrivateProfileStringW(L"version", L"AdvancedINF", L"2.0", &Buffer)
          && WritePrivateProfileStringW(L"Setup Hooks", L"hook1", L"hook1", &Buffer)
          && WritePrivateProfileStringW(L"hook1", L"run", &String, &Buffer) )
        {
          CString::operator=(&lpFileName, a2);
          v13 = operator+(&v15, &lpFileName, L".cab");
          CString::operator=(&lpFileName, v13);
          CString::~CString((CString *)&v15);
          if ( GetFileAttributesW(lpFileName) == -1 || (a3 & 1) != 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, LPCWSTR, __int64))(*(_QWORD *)v17 + 24LL))(v17, lpFileName, 1);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v17 + 32LL))(
                     v17,
                     a2,
                     v16);
              if ( v5 >= 0 )
              {
                v5 = (*(__int64 (__fastcall **)(__int64, WCHAR *, const wchar_t *))(*(_QWORD *)v17 + 32LL))(
                       v17,
                       &Buffer,
                       L"msicab.inf");
                if ( v5 >= 0 )
                  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
              }
            }
          }
          else
          {
            v5 = -2146368499;
          }
          goto LABEL_22;
        }
        goto LABEL_6;
      }
    }
  }
LABEL_22:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  DeleteFileW(&Buffer);
  CString::~CString((CString *)&lpFileName);
  CString::~CString((CString *)&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180051030  mov     [rsp+arg_0], rbx
0x180051035  mov     [rsp+arg_10], rsi
0x18005103a  push    rdi
0x18005103b  push    r14
0x18005103d  push    r15
0x18005103f  sub     rsp, 680h
0x180051046  mov     rax, cs:__security_cookie
0x18005104d  xor     rax, rsp
0x180051050  mov     [rsp+698h+var_28], rax
0x180051058  mov     r14d, r8d
0x18005105b  mov     r15, rdx
0x18005105e  lea     rcx, [rsp+698h+var_660]
0x180051063  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x180051069  nop
0x18005106a  lea     rcx, [rsp+698h+lpFileName]
0x18005106f  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x180051075  nop
0x180051076  xor     esi, esi
0x180051078  mov     [rsp+698h+Buffer], si
0x18005107d  xor     edx, edx; Val
0x18005107f  mov     r8d, 206h; Size
0x180051085  lea     rcx, [rsp+698h+var_646]; void *
0x18005108a  call    memset_0
0x18005108f  mov     [rsp+698h+String], si
0x180051097  xor     edx, edx; Val
0x180051099  mov     r8d, 40Eh; Size
0x18005109f  lea     rcx, [rsp+698h+var_436]; void *
0x1800510a7  call    memset_0
0x1800510ac  mov     [rsp+698h+var_658], rsi
0x1800510b1  mov     [rsp+698h+var_668], rsi
0x1800510b6  mov     rcx, r15; lpFileName
0x1800510b9  call    cs:__imp_GetFileAttributesW
0x1800510bf  cmp     eax, 0FFFFFFFFh
0x1800510c2  jnz     short loc_1800510CE
0x1800510c4  mov     edi, 8000FFFFh
0x1800510c9  jmp     loc_180051387
0x1800510ce  lea     rcx, [rsp+698h+var_668]
0x1800510d3  call    ?CreateInstance@?$CComObject@VCMakeCab@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMakeCab>::CreateInstance(ATL::CComObject<CMakeCab> * *)
0x1800510d8  mov     edi, eax
0x1800510da  test    eax, eax
0x1800510dc  js      loc_180051387
0x1800510e2  mov     rbx, [rsp+698h+var_668]
0x1800510e7  mov     rax, [rbx]
0x1800510ea  mov     rcx, rbx
0x1800510ed  mov     rax, [rax+8]
0x1800510f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510f6  mov     rax, [rbx]
0x1800510f9  lea     r8, [rsp+698h+var_658]
0x1800510fe  lea     rdx, IID_IMakeCab
0x180051105  mov     rcx, rbx
0x180051108  mov     rax, [rax]
0x18005110b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051110  mov     edi, eax
0x180051112  mov     rax, [rbx]
0x180051115  mov     rcx, rbx
0x180051118  mov     rax, [rax+10h]
0x18005111c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051121  test    edi, edi
0x180051123  js      loc_180051387
0x180051129  lea     rdx, [rsp+698h+Buffer]; lpBuffer
0x18005112e  mov     ecx, 104h; nBufferLength
0x180051133  call    cs:__imp_GetTempPathW
0x180051139  test    eax, eax
0x18005113b  jnz     short loc_18005115B
0x18005113d  call    cs:__imp_GetLastError
0x180051143  mov     edi, eax
0x180051145  test    eax, eax
0x180051147  jle     loc_180051387
0x18005114d  movzx   edi, ax
0x180051150  or      edi, 80070000h
0x180051156  jmp     loc_180051387
0x18005115b  lea     r9, [rsp+698h+Buffer]; lpTempFileName
0x180051160  xor     r8d, r8d; uUnique
0x180051163  lea     rdx, aInf; "INF"
0x18005116a  lea     rcx, [rsp+698h+Buffer]; lpPathName
0x18005116f  call    cs:__imp_GetTempFileNameW
0x180051175  test    eax, eax
0x180051177  jz      short loc_18005113D
0x180051179  mov     rdx, r15
0x18005117c  lea     rcx, [rsp+698h+var_660]
0x180051181  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180051187  mov     rax, [rsp+698h+var_660]
0x18005118c  mov     ebx, [rax-8]
0x18005118f  mov     edx, 5Ch ; '\'
0x180051194  lea     rcx, [rsp+698h+var_660]
0x180051199  call    cs:__imp_?ReverseFind@CString@@QEBAHG@Z; CString::ReverseFind(ushort)
0x18005119f  sub     ebx, eax
0x1800511a1  lea     r8d, [rbx-1]
0x1800511a5  lea     rdx, [rsp+698h+var_668]
0x1800511aa  lea     rcx, [rsp+698h+var_660]
0x1800511af  call    cs:__imp_?Right@CString@@QEBA?AV1@H@Z; CString::Right(int)
0x1800511b5  nop
0x1800511b6  mov     rdx, rax
0x1800511b9  lea     rcx, [rsp+698h+var_660]
0x1800511be  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800511c4  nop
0x1800511c5  lea     rcx, [rsp+698h+var_668]
0x1800511ca  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800511d0  mov     r9, [rsp+698h+var_660]
0x1800511d5  lea     r8, aMsiexecExeIExt; "msiexec.exe /i \"%%EXTRACT_DIR%%\\%s\""
0x1800511dc  mov     edx, 208h; unsigned __int64
0x1800511e1  lea     rcx, [rsp+698h+String]; unsigned __int16 *
0x1800511e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800511ee  mov     edi, eax
0x1800511f0  test    eax, eax
0x1800511f2  jns     short loc_1800511F9
0x1800511f4  jmp     loc_180051387
0x1800511f9  lea     r9, [rsp+698h+Buffer]; lpFileName
0x1800511fe  lea     r8, String; "\"$CHICAGO$\""
0x180051205  lea     rdx, KeyName; "signature"
0x18005120c  lea     rcx, AppName; "version"
0x180051213  call    cs:__imp_WritePrivateProfileStringW
0x180051219  test    eax, eax
0x18005121b  jz      loc_18005113D
0x180051221  lea     r9, [rsp+698h+Buffer]; lpFileName
0x180051226  lea     r8, a20; "2.0"
0x18005122d  lea     rdx, aAdvancedinf; "AdvancedINF"
0x180051234  lea     rcx, AppName; "version"
0x18005123b  call    cs:__imp_WritePrivateProfileStringW
0x180051241  test    eax, eax
0x180051243  jz      loc_18005113D
0x180051249  lea     r9, [rsp+698h+Buffer]; lpFileName
0x18005124e  lea     r8, aHook1; "hook1"
0x180051255  lea     rdx, aHook1_0; "hook1"
0x18005125c  lea     rcx, aSetupHooks; "Setup Hooks"
0x180051263  call    cs:__imp_WritePrivateProfileStringW
0x180051269  test    eax, eax
0x18005126b  jz      loc_18005113D
0x180051271  lea     r9, [rsp+698h+Buffer]; lpFileName
0x180051276  lea     r8, [rsp+698h+String]; lpString
0x18005127e  lea     rdx, aRun; "run"
0x180051285  lea     rcx, aHook1_1; "hook1"
0x18005128c  call    cs:__imp_WritePrivateProfileStringW
0x180051292  test    eax, eax
0x180051294  jz      loc_18005113D
0x18005129a  mov     rdx, r15
0x18005129d  lea     rcx, [rsp+698h+lpFileName]
0x1800512a2  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800512a8  lea     r8, aCab; ".cab"
0x1800512af  lea     rdx, [rsp+698h+lpFileName]
0x1800512b4  lea     rcx, [rsp+698h+var_668]
0x1800512b9  call    cs:__imp_??H@YA?AVCString@@AEBV0@PEBG@Z; operator+(CString const &,ushort const *)
0x1800512bf  nop
0x1800512c0  mov     rdx, rax
0x1800512c3  lea     rcx, [rsp+698h+lpFileName]
0x1800512c8  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800512ce  nop
0x1800512cf  lea     rcx, [rsp+698h+var_668]
0x1800512d4  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800512da  mov     rcx, [rsp+698h+lpFileName]; lpFileName
0x1800512df  call    cs:__imp_GetFileAttributesW
0x1800512e5  cmp     eax, 0FFFFFFFFh
0x1800512e8  jz      short loc_1800512FA
0x1800512ea  test    r14b, 1
0x1800512ee  jnz     short loc_1800512FA
0x1800512f0  mov     edi, 8011040Dh
0x1800512f5  jmp     loc_180051387
0x1800512fa  mov     rcx, [rsp+698h+var_658]
0x1800512ff  mov     rax, [rcx]
0x180051302  shr     r14d, 7
0x180051306  and     r14d, 1
0x18005130a  mov     [rsp+698h+var_678], r14d
0x18005130f  xor     r9d, r9d
0x180051312  lea     r8d, [r9+1]
0x180051316  mov     rdx, [rsp+698h+lpFileName]
0x18005131b  mov     rax, [rax+18h]
0x18005131f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051324  mov     edi, eax
0x180051326  test    eax, eax
0x180051328  js      short loc_180051387
0x18005132a  mov     rcx, [rsp+698h+var_658]
0x18005132f  mov     rax, [rcx]
0x180051332  mov     r8, [rsp+698h+var_660]
0x180051337  mov     rdx, r15
0x18005133a  mov     rax, [rax+20h]
0x18005133e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051343  mov     edi, eax
0x180051345  test    eax, eax
0x180051347  js      short loc_180051387
0x180051349  mov     rcx, [rsp+698h+var_658]
0x18005134e  mov     rax, [rcx]
0x180051351  lea     r8, aMsicabInf; "msicab.inf"
0x180051358  lea     rdx, [rsp+698h+Buffer]
0x18005135d  mov     rax, [rax+20h]
0x180051361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051366  mov     edi, eax
0x180051368  test    eax, eax
0x18005136a  js      short loc_180051387
0x18005136c  mov     rcx, [rsp+698h+var_658]
0x180051371  mov     rax, [rcx]
0x180051374  mov     rax, [rax+28h]
0x180051378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005137d  mov     edi, eax
0x18005137f  jmp     short loc_180051387
0x180051381  xor     esi, esi
0x180051383  mov     edi, dword ptr [rsp+698h+var_668]
0x180051387  mov     rcx, [rsp+698h+var_658]
0x18005138c  test    rcx, rcx
0x18005138f  jz      short loc_1800513A2
0x180051391  mov     rax, [rcx]
0x180051394  mov     rax, [rax+10h]
0x180051398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005139d  mov     [rsp+698h+var_658], rsi
0x1800513a2  lea     rcx, [rsp+698h+Buffer]; lpFileName
0x1800513a7  call    cs:__imp_DeleteFileW
0x1800513ad  nop
0x1800513ae  lea     rcx, [rsp+698h+lpFileName]
0x1800513b3  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800513b9  nop
0x1800513ba  lea     rcx, [rsp+698h+var_660]
0x1800513bf  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800513c5  mov     eax, edi
0x1800513c7  mov     rcx, [rsp+698h+var_28]
0x1800513cf  xor     rcx, rsp; StackCookie
0x1800513d2  call    __security_check_cookie
0x1800513d7  lea     r11, [rsp+698h+var_18]
0x1800513df  mov     rbx, [r11+20h]
0x1800513e3  mov     rsi, [r11+30h]
0x1800513e7  mov     rsp, r11
0x1800513ea  pop     r15
0x1800513ec  pop     r14
0x1800513ee  pop     rdi
0x1800513ef  retn
```
