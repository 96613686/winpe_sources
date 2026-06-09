# CAppImport::GetAplFromMsi(ushort const *,ulong,ushort *,unsigned __int64)

- ea: `0x18004308c`
- end: `0x1800434e6`
- name: `?GetAplFromMsi@CAppImport@@AEAAJPEBGKPEAG_K@Z`
- size: `1114`
- prototype: `__int64 __fastcall(CAppImport *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003bbf0`
- `0x180043b4c`

## callees

- `0x180009ee0`
- `0x18002d540`
- `0x180042ce8`
- `0x180042d04`
- `0x180042d34`
- `0x18004308c`
- `0x180055550`
- `0x180055610`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043489`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004339c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004339c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043463`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180043392`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180043392`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800433cf`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800433cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180043431`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180043431`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800433fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800433fd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180043190`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180043190`
- `msi!__imp_MsiCreateRecord` at `0x18004325b`
- `msi!__imp_MsiCreateRecord` at `0x1800432f7`
- `msi!__imp_MsiCreateRecord` at `0x18004325b`
- `msi!__imp_MsiCreateRecord` at `0x1800432f7`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180043232`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180043347`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180043232`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180043347`
- `msi!__imp_MsiOpenDatabaseW` at `0x18004316b`
- `msi!__imp_MsiOpenDatabaseW` at `0x18004316b`
- `msi!__imp_MsiRecordGetStringW` at `0x1800432e6`
- `msi!__imp_MsiRecordGetStringW` at `0x1800432e6`
- `msi!__imp_MsiRecordReadStream` at `0x180043455`
- `msi!__imp_MsiRecordReadStream` at `0x180043455`
- `msi!__imp_MsiRecordSetStringW` at `0x180043321`
- `msi!__imp_MsiRecordSetStringW` at `0x180043321`
- `msi!__imp_MsiViewExecute` at `0x180043246`
- `msi!__imp_MsiViewExecute` at `0x18004335b`
- `msi!__imp_MsiViewExecute` at `0x180043246`
- `msi!__imp_MsiViewExecute` at `0x18004335b`
- `msi!__imp_MsiViewFetch` at `0x18004328f`
- `msi!__imp_MsiViewFetch` at `0x1800432b5`
- `msi!__imp_MsiViewFetch` at `0x18004337a`
- `msi!__imp_MsiViewFetch` at `0x18004328f`
- `msi!__imp_MsiViewFetch` at `0x1800432b5`
- `msi!__imp_MsiViewFetch` at `0x18004337a`

## string_xrefs

- `0x180043315`: `complus.cab`
- `0x180043227`: `SELECT `File` FROM `Complus`, `File` WHERE `Complus`.`Component_` = `File`.`Component_``

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAppImport::GetAplFromMsi(
        CAppImport *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  __int64 FileW; // rsi
  int v8; // r12d
  signed int v9; // edi
  __int64 v10; // rbx
  MSIHANDLE *v11; // rax
  MSIHANDLE *v13; // rax
  MSIHANDLE Record; // eax
  MSIHANDLE *v15; // rax
  unsigned int i; // ebx
  MSIHANDLE *v17; // rax
  MSIHANDLE v18; // eax
  MSIHANDLE v19; // ebx
  MSIHANDLE *v20; // rax
  MSIHANDLE *v21; // rax
  signed int LastError; // eax
  signed int v23; // eax
  bool v24; // cc
  MSIHANDLE hRecord; // [rsp+40h] [rbp-C0h] BYREF
  MSIHANDLE hView; // [rsp+44h] [rbp-BCh] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+48h] [rbp-B8h] BYREF
  MSIHANDLE v28; // [rsp+4Ch] [rbp-B4h] BYREF
  MSIHANDLE v29; // [rsp+50h] [rbp-B0h] BYREF
  MSIHANDLE hDatabase; // [rsp+54h] [rbp-ACh] BYREF
  MSIHANDLE v31; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcchValueBuf; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szValueBuf[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR Buffer[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  char szDataBuf[4096]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v34 = 0;
  hDatabase = 0;
  v29 = 0;
  v31 = 0;
  v28 = 0;
  hView = 0;
  hRecord = 0;
  FileW = -1;
  nNumberOfBytesToWrite = 4096;
  NumberOfBytesWritten = 0;
  pcchValueBuf = 0;
  v8 = 0;
  v35 = 0;
  v9 = ATL::CComObject<CMakeCab>::CreateInstance(&v35);
  if ( v9 < 0 )
    goto LABEL_5;
  v10 = v35;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v10)(v10, &IID_IMakeCab, &v34);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v9 < 0 )
    goto LABEL_5;
  v11 = PMSIHANDLE::operator&(&hDatabase);
  if ( MsiOpenDatabaseW(a2, 0, v11) )
    goto LABEL_4;
  v13 = PMSIHANDLE::operator&(&hView);
  if ( MsiDatabaseOpenViewW(
         hDatabase,
         L"SELECT `File` FROM `Complus`, `File` WHERE `Complus`.`Component_` = `File`.`Component_`",
         v13)
    || MsiViewExecute(hView, 0) )
  {
    goto LABEL_4;
  }
  Record = MsiCreateRecord(1u);
  PMSIHANDLE::operator=(&hRecord, Record);
  if ( !hRecord )
  {
LABEL_13:
    v9 = -2147024882;
    goto LABEL_5;
  }
  v15 = PMSIHANDLE::operator&(&hRecord);
  if ( MsiViewFetch(hView, v15) )
    goto LABEL_4;
  for ( i = 0; i < a3; ++i )
  {
    v17 = PMSIHANDLE::operator&(&hRecord);
    if ( MsiViewFetch(hView, v17) )
      goto LABEL_4;
  }
  pcchValueBuf = 260;
  if ( MsiRecordGetStringW(hRecord, 1u, szValueBuf, &pcchValueBuf) )
    goto LABEL_4;
  v18 = MsiCreateRecord(1u);
  PMSIHANDLE::operator=(&v31, v18);
  v19 = v31;
  if ( !v31 )
    goto LABEL_13;
  if ( MsiRecordSetStringW(v31, 1u, L"complus.cab")
    || (v20 = PMSIHANDLE::operator&(&v29),
        MsiDatabaseOpenViewW(hDatabase, L"SELECT * FROM `_Streams` WHERE `Name`=?", v20))
    || MsiViewExecute(v29, v19)
    || (v21 = PMSIHANDLE::operator&(&v28), MsiViewFetch(v29, v21)) )
  {
LABEL_4:
    v9 = -2146368504;
    goto LABEL_5;
  }
  if ( !GetTempPathW(0x104u, Buffer)
    || !GetTempFileNameW(Buffer, L"COM", 0, FileName)
    || (FileW = (__int64)CreateFileW(FileName, 0x40000000u, 0, 0, 3u, 0x80u, 0), FileW == -1) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_5;
  }
  while ( 1 )
  {
    v23 = MsiRecordReadStream(v28, 2u, szDataBuf, &nNumberOfBytesToWrite);
    v24 = v23 <= 0;
    v9 = v23;
    if ( v23 )
      break;
    if ( !nNumberOfBytesToWrite )
    {
      CloseHandle((HANDLE)FileW);
      if ( (*(unsigned int (__fastcall **)(__int64, WCHAR *, WCHAR *))(*(_QWORD *)v34 + 48LL))(
             v34,
             FileName,
             szValueBuf) )
      {
        v9 = -2146368504;
      }
      else
      {
        v9 = StringCchPrintfW(a4, 0x104u, L"%s%s", Buffer, szValueBuf);
      }
      goto LABEL_6;
    }
    if ( !WriteFile((HANDLE)FileW, szDataBuf, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      v23 = GetLastError();
      v9 = v23;
      v24 = v23 <= 0;
      break;
    }
    nNumberOfBytesToWrite = 4096;
  }
  if ( !v24 )
    v9 = (unsigned __int16)v23 | 0x80070000;
  v8 = 1;
  if ( FileW )
  {
LABEL_5:
    CloseHandle((HANDLE)FileW);
    if ( !v8 )
      goto LABEL_7;
  }
LABEL_6:
  DeleteFileW(FileName);
LABEL_7:
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  PMSIHANDLE::~PMSIHANDLE(&hRecord);
  PMSIHANDLE::~PMSIHANDLE(&hView);
  PMSIHANDLE::~PMSIHANDLE(&v28);
  PMSIHANDLE::~PMSIHANDLE(&v31);
  PMSIHANDLE::~PMSIHANDLE(&v29);
  PMSIHANDLE::~PMSIHANDLE(&hDatabase);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004308c  mov     [rsp-8+arg_0], rbx
0x180043091  push    rbp
0x180043092  push    rsi
0x180043093  push    rdi
0x180043094  push    r12
0x180043096  push    r13
0x180043098  push    r14
0x18004309a  push    r15
0x18004309c  lea     rbp, [rsp-15C0h]
0x1800430a4  mov     eax, 16C0h
0x1800430a9  call    _alloca_probe
0x1800430ae  sub     rsp, rax
0x1800430b1  mov     rax, cs:__security_cookie
0x1800430b8  xor     rax, rsp
0x1800430bb  mov     [rbp+15F0h+var_40], rax
0x1800430c2  mov     r13, r9
0x1800430c5  mov     r15d, r8d
0x1800430c8  mov     r14, rdx
0x1800430cb  xor     ebx, ebx
0x1800430cd  mov     [rsp+16F0h+var_1688], rbx
0x1800430d2  mov     [rsp+16F0h+hDatabase], ebx
0x1800430d6  mov     [rsp+16F0h+var_16A0], ebx
0x1800430da  mov     [rsp+16F0h+var_1698], ebx
0x1800430de  mov     [rsp+16F0h+var_16A4], ebx
0x1800430e2  mov     [rsp+16F0h+hView], ebx
0x1800430e6  mov     [rsp+16F0h+hRecord], ebx
0x1800430ea  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800430ee  mov     [rsp+16F0h+nNumberOfBytesToWrite], 1000h
0x1800430f6  mov     [rsp+16F0h+NumberOfBytesWritten], ebx
0x1800430fa  mov     [rsp+16F0h+pcchValueBuf], ebx
0x1800430fe  mov     r12d, ebx
0x180043101  mov     [rsp+16F0h+var_1680], rbx
0x180043106  lea     rcx, [rsp+16F0h+var_1680]
0x18004310b  call    ?CreateInstance@?$CComObject@VCMakeCab@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMakeCab>::CreateInstance(ATL::CComObject<CMakeCab> * *)
0x180043110  mov     edi, eax
0x180043112  test    eax, eax
0x180043114  js      short loc_18004317E
0x180043116  mov     rbx, [rsp+16F0h+var_1680]
0x18004311b  mov     rax, [rbx]
0x18004311e  mov     rcx, rbx
0x180043121  mov     rax, [rax+8]
0x180043125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004312a  mov     rax, [rbx]
0x18004312d  lea     r8, [rsp+16F0h+var_1688]
0x180043132  lea     rdx, IID_IMakeCab
0x180043139  mov     rcx, rbx
0x18004313c  mov     rax, [rax]
0x18004313f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043144  mov     edi, eax
0x180043146  mov     rax, [rbx]
0x180043149  mov     rcx, rbx
0x18004314c  mov     rax, [rax+10h]
0x180043150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043155  test    edi, edi
0x180043157  js      short loc_18004317E
0x180043159  lea     rcx, [rsp+16F0h+hDatabase]
0x18004315e  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043163  mov     r8, rax; phDatabase
0x180043166  xor     edx, edx; szPersist
0x180043168  mov     rcx, r14; szDatabasePath
0x18004316b  call    cs:__imp_MsiOpenDatabaseW
0x180043171  test    eax, eax
0x180043173  jz      loc_18004321A
0x180043179  mov     edi, 80110408h
0x18004317e  mov     rcx, rsi; hObject
0x180043181  call    cs:__imp_CloseHandle
0x180043187  test    r12d, r12d
0x18004318a  jz      short loc_180043196
0x18004318c  lea     rcx, [rbp+15F0h+FileName]; lpFileName
0x180043190  call    cs:__imp_DeleteFileW
0x180043196  mov     rcx, [rsp+16F0h+var_1688]
0x18004319b  test    rcx, rcx
0x18004319e  jz      short loc_1800431AD
0x1800431a0  mov     rax, [rcx]
0x1800431a3  mov     rax, [rax+10h]
0x1800431a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431ac  nop
0x1800431ad  lea     rcx, [rsp+16F0h+hRecord]; this
0x1800431b2  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x1800431b7  nop
0x1800431b8  lea     rcx, [rsp+16F0h+hView]; this
0x1800431bd  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x1800431c2  nop
0x1800431c3  lea     rcx, [rsp+16F0h+var_16A4]; this
0x1800431c8  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x1800431cd  nop
0x1800431ce  lea     rcx, [rsp+16F0h+var_1698]; this
0x1800431d3  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x1800431d8  nop
0x1800431d9  lea     rcx, [rsp+16F0h+var_16A0]; this
0x1800431de  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x1800431e3  nop
0x1800431e4  lea     rcx, [rsp+16F0h+hDatabase]; this
0x1800431e9  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x1800431ee  mov     eax, edi
0x1800431f0  mov     rcx, [rbp+15F0h+var_40]
0x1800431f7  xor     rcx, rsp; StackCookie
0x1800431fa  call    __security_check_cookie
0x1800431ff  mov     rbx, [rsp+16F0h+arg_0]
0x180043207  add     rsp, 16C0h
0x18004320e  pop     r15
0x180043210  pop     r14
0x180043212  pop     r13
0x180043214  pop     r12
0x180043216  pop     rdi
0x180043217  pop     rsi
0x180043218  pop     rbp
0x180043219  retn
0x18004321a  lea     rcx, [rsp+16F0h+hView]
0x18004321f  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043224  mov     r8, rax; phView
0x180043227  lea     rdx, aSelectFileFrom; "SELECT `File` FROM `Complus`, `File` WH"...
0x18004322e  mov     ecx, [rsp+16F0h+hDatabase]; hDatabase
0x180043232  call    cs:__imp_MsiDatabaseOpenViewW
0x180043238  test    eax, eax
0x18004323a  jnz     loc_180043179
0x180043240  xor     edx, edx; hRecord
0x180043242  mov     ecx, [rsp+16F0h+hView]; hView
0x180043246  call    cs:__imp_MsiViewExecute
0x18004324c  test    eax, eax
0x18004324e  jnz     loc_180043179
0x180043254  lea     r14d, [rax+1]
0x180043258  mov     ecx, r14d; cParams
0x18004325b  call    cs:__imp_MsiCreateRecord
0x180043261  mov     edx, eax
0x180043263  lea     rcx, [rsp+16F0h+hRecord]
0x180043268  call    ??4PMSIHANDLE@@QEAAXK@Z; PMSIHANDLE::operator=(ulong)
0x18004326d  cmp     [rsp+16F0h+hRecord], r12d
0x180043272  jnz     short loc_18004327E
0x180043274  mov     edi, 8007000Eh
0x180043279  jmp     loc_18004317E
0x18004327e  lea     rcx, [rsp+16F0h+hRecord]
0x180043283  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043288  mov     rdx, rax; phRecord
0x18004328b  mov     ecx, [rsp+16F0h+hView]; hView
0x18004328f  call    cs:__imp_MsiViewFetch
0x180043295  test    eax, eax
0x180043297  jnz     loc_180043179
0x18004329d  xor     ebx, ebx
0x18004329f  cmp     ebx, r15d
0x1800432a2  jnb     short loc_1800432C8
0x1800432a4  lea     rcx, [rsp+16F0h+hRecord]
0x1800432a9  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x1800432ae  mov     rdx, rax; phRecord
0x1800432b1  mov     ecx, [rsp+16F0h+hView]; hView
0x1800432b5  call    cs:__imp_MsiViewFetch
0x1800432bb  test    eax, eax
0x1800432bd  jnz     loc_180043179
0x1800432c3  add     ebx, r14d
0x1800432c6  jmp     short loc_18004329F
0x1800432c8  mov     r15d, 104h
0x1800432ce  mov     [rsp+16F0h+pcchValueBuf], r15d
0x1800432d3  lea     r9, [rsp+16F0h+pcchValueBuf]; pcchValueBuf
0x1800432d8  lea     r8, [rbp+15F0h+szValueBuf]; szValueBuf
0x1800432df  mov     edx, r14d; iField
0x1800432e2  mov     ecx, [rsp+16F0h+hRecord]; hRecord
0x1800432e6  call    cs:__imp_MsiRecordGetStringW
0x1800432ec  test    eax, eax
0x1800432ee  jnz     loc_180043179
0x1800432f4  mov     ecx, r14d; cParams
0x1800432f7  call    cs:__imp_MsiCreateRecord
0x1800432fd  mov     edx, eax
0x1800432ff  lea     rcx, [rsp+16F0h+var_1698]
0x180043304  call    ??4PMSIHANDLE@@QEAAXK@Z; PMSIHANDLE::operator=(ulong)
0x180043309  mov     ebx, [rsp+16F0h+var_1698]
0x18004330d  test    ebx, ebx
0x18004330f  jz      loc_180043274
0x180043315  lea     r8, szValue; "complus.cab"
0x18004331c  mov     edx, r14d; iField
0x18004331f  mov     ecx, ebx; hRecord
0x180043321  call    cs:__imp_MsiRecordSetStringW
0x180043327  test    eax, eax
0x180043329  jnz     loc_180043179
0x18004332f  lea     rcx, [rsp+16F0h+var_16A0]
0x180043334  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043339  mov     r8, rax; phView
0x18004333c  lea     rdx, aSelectFromStre_0; "SELECT * FROM `_Streams` WHERE `Name`=?"
0x180043343  mov     ecx, [rsp+16F0h+hDatabase]; hDatabase
0x180043347  call    cs:__imp_MsiDatabaseOpenViewW
0x18004334d  test    eax, eax
0x18004334f  jnz     loc_180043179
0x180043355  mov     edx, ebx; hRecord
0x180043357  mov     ecx, [rsp+16F0h+var_16A0]; hView
0x18004335b  call    cs:__imp_MsiViewExecute
0x180043361  test    eax, eax
0x180043363  jnz     loc_180043179
0x180043369  lea     rcx, [rsp+16F0h+var_16A4]
0x18004336e  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043373  mov     rdx, rax; phRecord
0x180043376  mov     ecx, [rsp+16F0h+var_16A0]; hView
0x18004337a  call    cs:__imp_MsiViewFetch
0x180043380  test    eax, eax
0x180043382  jnz     loc_180043179
0x180043388  lea     rdx, [rbp+15F0h+Buffer]; lpBuffer
0x18004338f  mov     ecx, r15d; nBufferLength
0x180043392  call    cs:__imp_GetTempPathW
0x180043398  test    eax, eax
0x18004339a  jnz     short loc_1800433BA
0x18004339c  call    cs:__imp_GetLastError
0x1800433a2  mov     edi, eax
0x1800433a4  test    eax, eax
0x1800433a6  jle     loc_18004317E
0x1800433ac  movzx   edi, ax
0x1800433af  or      edi, 80070000h
0x1800433b5  jmp     loc_18004317E
0x1800433ba  lea     r9, [rbp+15F0h+FileName]; lpTempFileName
0x1800433be  xor     r8d, r8d; uUnique
0x1800433c1  lea     rdx, aCom_1; "COM"
0x1800433c8  lea     rcx, [rbp+15F0h+Buffer]; lpPathName
0x1800433cf  call    cs:__imp_GetTempFileNameW
0x1800433d5  test    eax, eax
0x1800433d7  jz      short loc_18004339C
0x1800433d9  mov     [rsp+16F0h+hTemplateFile], r12; hTemplateFile
0x1800433de  mov     [rsp+16F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800433e6  mov     [rsp+16F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800433ee  xor     r9d, r9d; lpSecurityAttributes
0x1800433f1  xor     r8d, r8d; dwShareMode
0x1800433f4  mov     edx, 40000000h; dwDesiredAccess
0x1800433f9  lea     rcx, [rbp+15F0h+FileName]; lpFileName
0x1800433fd  call    cs:__imp_CreateFileW
0x180043403  mov     rsi, rax
0x180043406  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004340a  jz      short loc_18004339C
0x18004340c  mov     ebx, 2
0x180043411  jmp     short loc_180043443
0x180043413  mov     r8d, [rsp+16F0h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180043418  mov     rcx, rsi; hObject
0x18004341b  test    r8d, r8d
0x18004341e  jz      short loc_180043489
0x180043420  mov     qword ptr [rsp+16F0h+dwCreationDisposition], r12; lpOverlapped
0x180043425  lea     r9, [rsp+16F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004342a  lea     rdx, [rbp+15F0h+szDataBuf]; lpBuffer
0x180043431  call    cs:__imp_WriteFile
0x180043437  test    eax, eax
0x180043439  jz      short loc_180043463
0x18004343b  mov     [rsp+16F0h+nNumberOfBytesToWrite], 1000h
0x180043443  lea     r9, [rsp+16F0h+nNumberOfBytesToWrite]; pcbDataBuf
0x180043448  lea     r8, [rbp+15F0h+szDataBuf]; szDataBuf
0x18004344f  mov     edx, ebx; iField
0x180043451  mov     ecx, [rsp+16F0h+var_16A4]; hRecord
0x180043455  call    cs:__imp_MsiRecordReadStream
0x18004345b  test    eax, eax
0x18004345d  mov     edi, eax
0x18004345f  jz      short loc_180043413
0x180043461  jmp     short loc_18004346D
0x180043463  call    cs:__imp_GetLastError
0x180043469  mov     edi, eax
0x18004346b  test    eax, eax
0x18004346d  jle     short loc_180043478
0x18004346f  movzx   edi, ax
0x180043472  or      edi, 80070000h
0x180043478  mov     r12d, r14d
0x18004347b  test    rsi, rsi
0x18004347e  jz      loc_18004318C
0x180043484  jmp     loc_18004317E
0x180043489  call    cs:__imp_CloseHandle
0x18004348f  mov     rcx, [rsp+16F0h+var_1688]
0x180043494  mov     rax, [rcx]
0x180043497  lea     r8, [rbp+15F0h+szValueBuf]
0x18004349e  lea     rdx, [rbp+15F0h+FileName]
0x1800434a2  mov     rax, [rax+30h]
0x1800434a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434ab  test    eax, eax
0x1800434ad  jz      short loc_1800434B9
0x1800434af  mov     edi, 80110408h
0x1800434b4  jmp     loc_18004318C
0x1800434b9  lea     rax, [rbp+15F0h+szValueBuf]
0x1800434c0  mov     qword ptr [rsp+16F0h+dwCreationDisposition], rax
0x1800434c5  lea     r9, [rbp+15F0h+Buffer]
0x1800434cc  lea     r8, aSS_0; "%s%s"
0x1800434d3  mov     rdx, r15; unsigned __int64
0x1800434d6  mov     rcx, r13; unsigned __int16 *
0x1800434d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800434de  mov     edi, eax
0x1800434e0  jmp     loc_18004318C
```
