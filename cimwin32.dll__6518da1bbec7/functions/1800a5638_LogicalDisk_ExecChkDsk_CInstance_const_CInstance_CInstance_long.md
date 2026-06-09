# LogicalDisk::ExecChkDsk(CInstance const &,CInstance *,CInstance *,long)

- ea: `0x1800a5638`
- end: `0x1800a5a78`
- name: `?ExecChkDsk@LogicalDisk@@AEAAJAEBVCInstance@@PEAV2@1J@Z`
- size: `1088`
- prototype: `__int64 __fastcall(LogicalDisk *this, const struct CInstance *, struct CInstance *, struct CInstance *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a5b50`

## callees

- `0x180088000`
- `0x1800a5488`
- `0x1800a5638`
- `0x180110010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5660`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5660`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a5a04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a5a04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a571d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a589f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a571d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a589f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a56fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a56fc`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800a56d8`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800a56d8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a56a0`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a5734`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a56a0`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a5734`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800a56b6`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800a56b6`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800a57a0`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800a57b6`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800a57cc`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800a57a0`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800a57b6`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800a57cc`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a56cf`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a56cf`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800a5754`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800a5764`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800a5978`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800a5988`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800a5754`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800a5764`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800a5978`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800a5988`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x1800a59bc`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x1800a59bc`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800a59c7`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800a59c7`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a5820`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a5835`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a584a`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a585f`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a5877`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a588f`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a5820`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a5835`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a584a`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a585f`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a5877`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x1800a588f`
- `framedynos!?SetWORD@CInstance@@QEAA_NPEBGG@Z` at `0x1800a5a3f`
- `framedynos!?SetWORD@CInstance@@QEAA_NPEBGG@Z` at `0x1800a5a3f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a59fa`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a5a16`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a59fa`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a5a16`

## string_xrefs

- `0x1800a56f5`: `fmifs.dll`
- `0x1800a5855`: `ForceDismount`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall LogicalDisk::ExecChkDsk(
        LogicalDisk *this,
        const struct CInstance *a2,
        struct CInstance *a3,
        struct CInstance *a4,
        char a5)
{
  int v8; // edi
  const WCHAR *v9; // rax
  LogicalDisk *v10; // rcx
  HMODULE Library; // rax
  HMODULE v12; // rsi
  FARPROC ProcAddress; // r15
  unsigned __int16 *Buffer; // rbx
  unsigned __int16 *v15; // rax
  FARPROC v16; // r13
  void *v17; // r15
  char v18; // r14
  unsigned __int16 *v19; // rbx
  unsigned __int16 *v20; // rax
  __int64 v21; // r8
  unsigned __int16 *v22; // rax
  bool v24; // [rsp+30h] [rbp-98h] BYREF
  bool v25; // [rsp+31h] [rbp-97h] BYREF
  bool v26; // [rsp+32h] [rbp-96h] BYREF
  char v27; // [rsp+33h] [rbp-95h] BYREF
  _BYTE v28[4]; // [rsp+34h] [rbp-94h] BYREF
  DWORD CurrentThreadId; // [rsp+38h] [rbp-90h]
  _BYTE v30[8]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v31[8]; // [rsp+48h] [rbp-80h] BYREF
  _DWORD v32[2]; // [rsp+50h] [rbp-78h] BYREF
  HMODULE v33; // [rsp+58h] [rbp-70h]
  _OWORD v34[3]; // [rsp+60h] [rbp-68h] BYREF
  __int64 v35; // [rsp+90h] [rbp-38h]
  LogicalDisk *v36; // [rsp+D0h] [rbp+8h] BYREF
  bool v37; // [rsp+E0h] [rbp+18h] BYREF

  v36 = this;
  CurrentThreadId = GetCurrentThreadId();
  if ( !a3 || (v8 = 0, !a4) )
    v8 = -2147217400;
  *(_DWORD *)std::map<unsigned long,unsigned long>::operator[]((int)&mReturnVal) = 0;
  if ( v8 >= 0 )
  {
    CHString::CHString((CHString *)v31);
    if ( !CInstance::GetCHString(a2, L"DeviceID", (struct CHString *)v31) )
    {
      v8 = -2147217404;
      goto LABEL_30;
    }
    v9 = (const WCHAR *)CHString::operator unsigned short const *(v31);
    GetDriveTypeW(v9);
    v8 = LogicalDisk::CheckParameters(v10, a3);
    if ( v8 >= 0 )
    {
      Library = LoadLibraryExW(L"fmifs.dll", 0, 0);
      v12 = Library;
      v33 = Library;
      if ( Library )
      {
        try
        {
          ProcAddress = GetProcAddress(Library, "QueryFileSystemName");
          if ( !ProcAddress )
            goto LABEL_35;
          CHString::CHString((CHString *)v30);
          v28[0] = 0;
          v27 = 0;
          v32[0] = 0;
          Buffer = CHString::GetBuffer((CHString *)v30, 261);
          v15 = CHString::GetBuffer((CHString *)v31, 0);
          if ( ((unsigned __int8 (__fastcall *)(unsigned __int16 *, unsigned __int16 *, _BYTE *, char *, _DWORD *))ProcAddress)(
                 v15,
                 Buffer,
                 v28,
                 &v27,
                 v32) )
          {
            if ( !CHString::CompareNoCase((CHString *)v30, L"FAT")
              || !CHString::CompareNoCase((CHString *)v30, L"FAT32")
              || !CHString::CompareNoCase((CHString *)v30, L"NTFS") )
            {
              a5 = 0;
              v25 = 0;
              v26 = 0;
              v24 = 0;
              v37 = 0;
              LOBYTE(v36) = 0;
              CInstance::Getbool(a3, L"FixErrors", (bool *)&a5);
              CInstance::Getbool(a3, L"VigorousIndexCheck", &v25);
              CInstance::Getbool(a3, L"SkipFolderCycle", &v26);
              CInstance::Getbool(a3, L"ForceDismount", &v24);
              CInstance::Getbool(a3, L"RecoverBadSectors", &v37);
              CInstance::Getbool(a3, L"OkToRunAtBootup", (bool *)&v36);
              v16 = GetProcAddress(v12, "ChkdskEx");
              if ( v16 )
              {
                v17 = &DontScheduleAutoChkIfLocked;
                if ( (_BYTE)v36 )
                  v17 = &ScheduleAutoChkIfLocked;
                memset(v34, 0, sizeof(v34));
                v35 = 0;
                v18 = 1;
                LOWORD(v34[0]) = 1;
                DWORD1(v34[0]) = (v26 ? 0x400 : 0) | (v25 ? 0x200 : 0) | (v37 ? 6 : 0) | (v24 ? 0x100 : 0);
                if ( v37 || v24 )
                  a5 = 1;
                else
                  v18 = a5;
                v19 = CHString::GetBuffer((CHString *)v30, 0);
                v20 = CHString::GetBuffer((CHString *)v31, 0);
                LOBYTE(v21) = v18;
                ((void (__fastcall *)(unsigned __int16 *, unsigned __int16 *, __int64, _OWORD *, void *))v16)(
                  v20,
                  v19,
                  v21,
                  v34,
                  v17);
              }
              else
              {
                v8 = -2147217407;
                v32[1] = -2147217407;
              }
              goto LABEL_27;
            }
          }
          else
          {
            CHString::ReleaseBuffer((CHString *)v30, -1);
            if ( CHString::IsEmpty((CHString *)v30) )
            {
              *(_DWORD *)std::map<unsigned long,unsigned long>::operator[]((int)&mReturnVal) = 2;
              goto LABEL_27;
            }
          }
          *(_DWORD *)std::map<unsigned long,unsigned long>::operator[]((int)&mReturnVal) = 4;
LABEL_27:
          CHString::~CHString((CHString *)v30);
        }
        catch ( ... )
        {
          FreeLibrary(v33);
          throw;
        }
LABEL_35:
        FreeLibrary(v12);
        goto LABEL_30;
      }
      v8 = -2147217407;
    }
LABEL_30:
    CHString::~CHString((CHString *)v31);
    if ( v8 >= 0 )
    {
      v22 = (unsigned __int16 *)std::map<unsigned long,unsigned long>::operator[]((int)&mReturnVal);
      CInstance::SetWORD(a4, L"ReturnValue", *v22);
      *(_DWORD *)std::map<unsigned long,unsigned long>::operator[]((int)&mReturnVal) = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a5638  mov     [rsp+arg_8], rbx
0x1800a563d  mov     [rsp+arg_18], rsi
0x1800a5642  mov     [rsp+arg_0], rcx
0x1800a5647  push    rdi
0x1800a5648  push    r12
0x1800a564a  push    r13
0x1800a564c  push    r14
0x1800a564e  push    r15
0x1800a5650  sub     rsp, 0A0h
0x1800a5657  mov     r12, r9
0x1800a565a  mov     r14, r8
0x1800a565d  mov     rbx, rdx
0x1800a5660  call    cs:__imp_GetCurrentThreadId
0x1800a5666  mov     [rsp+0C8h+var_90], eax
0x1800a566a  xor     r13d, r13d
0x1800a566d  test    r14, r14
0x1800a5670  jz      short loc_1800A567A
0x1800a5672  mov     edi, r13d
0x1800a5675  test    r12, r12
0x1800a5678  jnz     short loc_1800A567F
0x1800a567a  mov     edi, 80041008h
0x1800a567f  lea     rdx, [rsp+0C8h+var_90]
0x1800a5684  lea     rcx, ?mReturnVal@@3V?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@A; int
0x1800a568b  call    ??A?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@QEAAAEAKAEBK@Z; std::map<ulong,ulong>::operator[](ulong const &)
0x1800a5690  mov     [rax], r13d
0x1800a5693  test    edi, edi
0x1800a5695  js      loc_1800A5A59
0x1800a569b  lea     rcx, [rsp+0C8h+var_80]
0x1800a56a0  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800a56a6  nop
0x1800a56a7  lea     r8, [rsp+0C8h+var_80]
0x1800a56ac  lea     rdx, aDeviceid; "DeviceID"
0x1800a56b3  mov     rcx, rbx
0x1800a56b6  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800a56bc  test    al, al
0x1800a56be  jnz     short loc_1800A56CA
0x1800a56c0  mov     edi, 80041004h
0x1800a56c5  jmp     loc_1800A5A11
0x1800a56ca  lea     rcx, [rsp+0C8h+var_80]
0x1800a56cf  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800a56d5  mov     rcx, rax; lpRootPathName
0x1800a56d8  call    cs:__imp_GetDriveTypeW
0x1800a56de  mov     rdx, r14; struct CInstance *
0x1800a56e1  call    ?CheckParameters@LogicalDisk@@AEAAJPEAVCInstance@@@Z; LogicalDisk::CheckParameters(CInstance *)
0x1800a56e6  mov     edi, eax
0x1800a56e8  test    eax, eax
0x1800a56ea  js      loc_1800A5A11
0x1800a56f0  xor     r8d, r8d; dwFlags
0x1800a56f3  xor     edx, edx; hFile
0x1800a56f5  lea     rcx, aFmifsDll; "fmifs.dll"
0x1800a56fc  call    cs:__imp_LoadLibraryExW
0x1800a5702  mov     rsi, rax
0x1800a5705  mov     [rsp+0C8h+var_70], rax
0x1800a570a  test    rax, rax
0x1800a570d  jz      loc_1800A5A0C
0x1800a5713  lea     rdx, aQueryfilesyste; "QueryFileSystemName"
0x1800a571a  mov     rcx, rax; hModule
0x1800a571d  call    cs:__imp_GetProcAddress
0x1800a5723  mov     r15, rax
0x1800a5726  test    rax, rax
0x1800a5729  jz      loc_1800A5A01
0x1800a572f  lea     rcx, [rsp+0C8h+var_88]
0x1800a5734  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800a573a  nop
0x1800a573b  mov     [rsp+0C8h+var_94], r13b
0x1800a5740  mov     [rsp+0C8h+var_95], r13b
0x1800a5745  mov     [rsp+0C8h+var_78], r13d
0x1800a574a  mov     edx, 105h
0x1800a574f  lea     rcx, [rsp+0C8h+var_88]
0x1800a5754  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x1800a575a  mov     rbx, rax
0x1800a575d  xor     edx, edx
0x1800a575f  lea     rcx, [rsp+0C8h+var_80]
0x1800a5764  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x1800a576a  lea     rcx, [rsp+0C8h+var_78]
0x1800a576f  mov     [rsp+0C8h+var_A8], rcx
0x1800a5774  lea     r9, [rsp+0C8h+var_95]
0x1800a5779  lea     r8, [rsp+0C8h+var_94]
0x1800a577e  mov     rdx, rbx
0x1800a5781  mov     rcx, rax
0x1800a5784  mov     rax, r15
0x1800a5787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a578c  lea     rcx, [rsp+0C8h+var_88]
0x1800a5791  test    al, al
0x1800a5793  jz      loc_1800A59B9
0x1800a5799  lea     rdx, aFat; "FAT"
0x1800a57a0  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800a57a6  test    eax, eax
0x1800a57a8  jz      short loc_1800A57E7
0x1800a57aa  lea     rdx, aFat32; "FAT32"
0x1800a57b1  lea     rcx, [rsp+0C8h+var_88]
0x1800a57b6  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800a57bc  test    eax, eax
0x1800a57be  jz      short loc_1800A57E7
0x1800a57c0  lea     rdx, aNtfs; "NTFS"
0x1800a57c7  lea     rcx, [rsp+0C8h+var_88]
0x1800a57cc  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800a57d2  test    eax, eax
0x1800a57d4  jz      short loc_1800A57E7
0x1800a57d6  lea     rdx, [rsp+0C8h+var_90]
0x1800a57db  lea     rcx, ?mReturnVal@@3V?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@A; std::map<ulong,ulong> mReturnVal
0x1800a57e2  jmp     loc_1800A59DD
0x1800a57e7  mov     byte ptr [rsp+0C8h+arg_20], r13b
0x1800a57ef  mov     [rsp+0C8h+var_97], r13b
0x1800a57f4  mov     [rsp+0C8h+var_96], r13b
0x1800a57f9  mov     [rsp+0C8h+var_98], r13b
0x1800a57fe  mov     [rsp+0C8h+arg_10], r13b
0x1800a5806  mov     byte ptr [rsp+0C8h+arg_0], r13b
0x1800a580e  lea     r8, [rsp+0C8h+arg_20]
0x1800a5816  lea     rdx, aFixerrors; "FixErrors"
0x1800a581d  mov     rcx, r14
0x1800a5820  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x1800a5826  lea     r8, [rsp+0C8h+var_97]
0x1800a582b  lea     rdx, aVigorousindexc; "VigorousIndexCheck"
0x1800a5832  mov     rcx, r14
0x1800a5835  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x1800a583b  lea     r8, [rsp+0C8h+var_96]
0x1800a5840  lea     rdx, aSkipfoldercycl; "SkipFolderCycle"
0x1800a5847  mov     rcx, r14
0x1800a584a  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x1800a5850  lea     r8, [rsp+0C8h+var_98]
0x1800a5855  lea     rdx, aForcedismount; "ForceDismount"
0x1800a585c  mov     rcx, r14
0x1800a585f  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x1800a5865  lea     r8, [rsp+0C8h+arg_10]
0x1800a586d  lea     rdx, aRecoverbadsect; "RecoverBadSectors"
0x1800a5874  mov     rcx, r14
0x1800a5877  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x1800a587d  lea     r8, [rsp+0C8h+arg_0]
0x1800a5885  lea     rdx, aOktorunatbootu; "OkToRunAtBootup"
0x1800a588c  mov     rcx, r14
0x1800a588f  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x1800a5895  lea     rdx, aChkdskex; "ChkdskEx"
0x1800a589c  mov     rcx, rsi; hModule
0x1800a589f  call    cs:__imp_GetProcAddress
0x1800a58a5  mov     r13, rax
0x1800a58a8  xor     r10d, r10d
0x1800a58ab  test    rax, rax
0x1800a58ae  jz      loc_1800A59AB
0x1800a58b4  lea     r15, ?DontScheduleAutoChkIfLocked@@YAEW4_FMIFS_PACKET_TYPE@@KPEAX@Z; DontScheduleAutoChkIfLocked(_FMIFS_PACKET_TYPE,ulong,void *)
0x1800a58bb  lea     rax, ?ScheduleAutoChkIfLocked@@YAEW4_FMIFS_PACKET_TYPE@@KPEAX@Z; ScheduleAutoChkIfLocked(_FMIFS_PACKET_TYPE,ulong,void *)
0x1800a58c2  cmp     byte ptr [rsp+0C8h+arg_0], r10b
0x1800a58ca  cmovnz  r15, rax
0x1800a58ce  xorps   xmm0, xmm0
0x1800a58d1  xor     eax, eax
0x1800a58d3  movups  [rsp+0C8h+var_68], xmm0
0x1800a58d8  movups  [rsp+0C8h+var_58], xmm0
0x1800a58dd  movups  [rsp+0C8h+var_48], xmm0
0x1800a58e5  mov     [rsp+0C8h+var_38], rax
0x1800a58ed  mov     r14b, 1
0x1800a58f0  mov     byte ptr [rsp+0C8h+var_68], r14b
0x1800a58f5  mov     byte ptr [rsp+0C8h+var_68+1], r10b
0x1800a58fa  mov     dword ptr [rsp+0C8h+var_68+4], r10d
0x1800a58ff  mov     r8b, [rsp+0C8h+arg_10]
0x1800a5907  mov     al, r8b
0x1800a590a  neg     al
0x1800a590c  sbb     ecx, ecx
0x1800a590e  and     ecx, 6
0x1800a5911  mov     dword ptr [rsp+0C8h+var_68+4], ecx
0x1800a5915  mov     r9b, [rsp+0C8h+var_98]
0x1800a591a  mov     al, r9b
0x1800a591d  neg     al
0x1800a591f  sbb     edx, edx
0x1800a5921  and     edx, 100h
0x1800a5927  or      edx, ecx
0x1800a5929  mov     dword ptr [rsp+0C8h+var_68+4], edx
0x1800a592d  mov     al, [rsp+0C8h+var_97]
0x1800a5931  neg     al
0x1800a5933  sbb     ecx, ecx
0x1800a5935  and     ecx, 200h
0x1800a593b  or      edx, ecx
0x1800a593d  mov     dword ptr [rsp+0C8h+var_68+4], edx
0x1800a5941  mov     al, [rsp+0C8h+var_96]
0x1800a5945  neg     al
0x1800a5947  sbb     ecx, ecx
0x1800a5949  and     ecx, 400h
0x1800a594f  or      edx, ecx
0x1800a5951  mov     dword ptr [rsp+0C8h+var_68+4], edx
0x1800a5955  test    r8b, r8b
0x1800a5958  jnz     short loc_1800A5969
0x1800a595a  test    r9b, r9b
0x1800a595d  jnz     short loc_1800A5969
0x1800a595f  mov     r14b, byte ptr [rsp+0C8h+arg_20]
0x1800a5967  jmp     short loc_1800A5971
0x1800a5969  mov     byte ptr [rsp+0C8h+arg_20], r14b
0x1800a5971  xor     edx, edx
0x1800a5973  lea     rcx, [rsp+0C8h+var_88]
0x1800a5978  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x1800a597e  mov     rbx, rax
0x1800a5981  xor     edx, edx
0x1800a5983  lea     rcx, [rsp+0C8h+var_80]
0x1800a5988  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x1800a598e  mov     [rsp+0C8h+var_A8], r15
0x1800a5993  lea     r9, [rsp+0C8h+var_68]
0x1800a5998  mov     r8b, r14b
0x1800a599b  mov     rdx, rbx
0x1800a599e  mov     rcx, rax
0x1800a59a1  mov     rax, r13
0x1800a59a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a59a9  jmp     short loc_1800A59B4
0x1800a59ab  mov     edi, 80041001h
0x1800a59b0  mov     [rsp+0C8h+var_74], edi
0x1800a59b4  xor     r13d, r13d
0x1800a59b7  jmp     short loc_1800A59F5
0x1800a59b9  or      edx, 0FFFFFFFFh
0x1800a59bc  call    cs:__imp_?ReleaseBuffer@CHString@@QEAAXH@Z; CHString::ReleaseBuffer(int)
0x1800a59c2  lea     rcx, [rsp+0C8h+var_88]
0x1800a59c7  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800a59cd  lea     rdx, [rsp+0C8h+var_90]
0x1800a59d2  lea     rcx, ?mReturnVal@@3V?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@A; int
0x1800a59d9  test    eax, eax
0x1800a59db  jnz     short loc_1800A59EA
0x1800a59dd  call    ??A?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@QEAAAEAKAEBK@Z; std::map<ulong,ulong>::operator[](ulong const &)
0x1800a59e2  mov     dword ptr [rax], 4
0x1800a59e8  jmp     short loc_1800A59F5
0x1800a59ea  call    ??A?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@QEAAAEAKAEBK@Z; std::map<ulong,ulong>::operator[](ulong const &)
0x1800a59ef  mov     dword ptr [rax], 2
0x1800a59f5  lea     rcx, [rsp+0C8h+var_88]
0x1800a59fa  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a5a00  nop
0x1800a5a01  mov     rcx, rsi; hLibModule
0x1800a5a04  call    cs:__imp_FreeLibrary
0x1800a5a0a  jmp     short loc_1800A5A11
0x1800a5a0c  mov     edi, 80041001h
0x1800a5a11  lea     rcx, [rsp+0C8h+var_80]
0x1800a5a16  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a5a1c  test    edi, edi
0x1800a5a1e  js      short loc_1800A5A59
0x1800a5a20  lea     rdx, [rsp+0C8h+var_90]
0x1800a5a25  lea     rcx, ?mReturnVal@@3V?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@A; int
0x1800a5a2c  call    ??A?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@QEAAAEAKAEBK@Z; std::map<ulong,ulong>::operator[](ulong const &)
0x1800a5a31  movzx   r8d, word ptr [rax]
0x1800a5a35  lea     rdx, aReturnvalue; "ReturnValue"
0x1800a5a3c  mov     rcx, r12
0x1800a5a3f  call    cs:__imp_?SetWORD@CInstance@@QEAA_NPEBGG@Z; CInstance::SetWORD(ushort const *,ushort)
0x1800a5a45  lea     rdx, [rsp+0C8h+var_90]
0x1800a5a4a  lea     rcx, ?mReturnVal@@3V?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@A; int
0x1800a5a51  call    ??A?$map@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@@std@@QEAAAEAKAEBK@Z; std::map<ulong,ulong>::operator[](ulong const &)
0x1800a5a56  mov     [rax], r13d
0x1800a5a59  mov     eax, edi
0x1800a5a5b  lea     r11, [rsp+0C8h+var_28]
0x1800a5a63  mov     rbx, [r11+38h]
0x1800a5a67  mov     rsi, [r11+48h]
0x1800a5a6b  mov     rsp, r11
0x1800a5a6e  pop     r15
0x1800a5a70  pop     r14
0x1800a5a72  pop     r13
0x1800a5a74  pop     r12
0x1800a5a76  pop     rdi
0x1800a5a77  retn
```
