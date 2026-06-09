# FDeleteFolder(ushort const *)

- ea: `0x1801d5540`
- end: `0x1801d58aa`
- name: `?FDeleteFolder@@YA_NPEBG@Z`
- size: `874`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1801b7b84`
- `0x1801d5540`
- `0x180209120`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x180014160`
- `0x1800141e0`
- `0x180014288`
- `0x18004a014`
- `0x1800798e4`
- `0x1801d5540`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1801d57be`
- `KERNEL32!DeleteFileW` at `0x1801d57f7`
- `KERNEL32!DeleteFileW` at `0x1801d57be`
- `KERNEL32!DeleteFileW` at `0x1801d57f7`
- `KERNEL32!GetLastError` at `0x1801d5616`
- `KERNEL32!GetLastError` at `0x1801d5627`
- `KERNEL32!GetLastError` at `0x1801d5616`
- `KERNEL32!GetLastError` at `0x1801d5627`
- `KERNEL32!FindFirstFileW` at `0x1801d5601`
- `KERNEL32!FindFirstFileW` at `0x1801d5601`
- `KERNEL32!SetFileAttributesW` at `0x1801d57e6`
- `KERNEL32!SetFileAttributesW` at `0x1801d585e`
- `KERNEL32!SetFileAttributesW` at `0x1801d57e6`
- `KERNEL32!SetFileAttributesW` at `0x1801d585e`
- `KERNEL32!FindNextFileW` at `0x1801d5814`
- `KERNEL32!FindNextFileW` at `0x1801d5814`
- `KERNEL32!FindClose` at `0x1801d582b`
- `KERNEL32!FindClose` at `0x1801d582b`
- `KERNEL32!RemoveDirectoryW` at `0x1801d583a`
- `KERNEL32!RemoveDirectoryW` at `0x1801d586d`
- `KERNEL32!RemoveDirectoryW` at `0x1801d583a`
- `KERNEL32!RemoveDirectoryW` at `0x1801d586d`

## string_xrefs

- `0x1801d5726`: `FDeleteFolder: Deleting folder '%s'`
- `0x1801d577e`: `FDeleteFolder: Deleting file '%s'`

## pseudocode

```c
char __fastcall FDeleteFolder(const unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  char v3; // bl
  __int64 v5; // r8
  HANDLE FirstFileW; // rsi
  int v8; // edx
  int v9; // edx
  struct IMsiRecord *v10; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpPathName; // [rsp+68h] [rbp-98h] BYREF
  int v12; // [rsp+70h] [rbp-90h]
  char v13; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h] BYREF
  int v15; // [rsp+88h] [rbp-78h]
  char v16; // [rsp+90h] [rbp-70h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v3 = 1;
  lpFileName = (LPCWSTR)&v16;
  v15 = 1;
  lpPathName = (LPCWSTR)&v13;
  LOBYTE(a3) = 1;
  v12 = 1;
  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpFileName, 780, a3) )
    goto LABEL_8;
  LOBYTE(v5) = 1;
  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpPathName, 780, v5)
    || (int)StringCchCopyW((unsigned __int16 *)lpFileName, v15, a1) < 0
    || (int)StringCchCatW((unsigned __int16 *)lpFileName, v15, L"\\*.*") < 0 )
  {
    goto LABEL_8;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( GetLastError() == 5 || GetLastError() != 2 )
    {
LABEL_8:
      CAPITempBuffer<unsigned short,1>::Destroy(&lpPathName);
      CAPITempBuffer<unsigned short,1>::Destroy(&lpFileName);
      return 0;
    }
  }
  else
  {
    do
    {
      v8 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v8 = FindFileData.cFileName[1];
      if ( v8 )
      {
        v9 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v9 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v9 = FindFileData.cFileName[2];
        }
        if ( v9
          && (int)StringCchCopyW((unsigned __int16 *)lpPathName, v12, a1) >= 0
          && (int)StringCchCatW((unsigned __int16 *)lpPathName, v12, L"\\") >= 0
          && (int)StringCchCatW((unsigned __int16 *)lpPathName, v12, FindFileData.cFileName) >= 0 )
        {
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                10,
                0,
                0,
                L"FDeleteFolder: Deleting folder '%s'",
                lpPathName,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            FDeleteFolder(lpPathName);
          }
          else
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                10,
                0,
                0,
                L"FDeleteFolder: Deleting file '%s'",
                lpPathName,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            if ( !DeleteFileW(lpPathName) )
            {
              v10 = LockdownPath(lpPathName, 0);
              SetFileAttributesW(lpPathName, 0);
              DeleteFileW(lpPathName);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v10);
            }
          }
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    FindClose(FirstFileW);
    if ( !RemoveDirectoryW(a1) )
    {
      v10 = LockdownPath(a1, 0);
      SetFileAttributesW(a1, 0);
      if ( RemoveDirectoryW(a1) )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v10);
      }
      else
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v10);
        v3 = 0;
      }
    }
  }
  CAPITempBuffer<unsigned short,1>::Destroy(&lpPathName);
  CAPITempBuffer<unsigned short,1>::Destroy(&lpFileName);
  return v3;
}

```

## disassembly

```asm
0x1801d5540  push    rbp
0x1801d5542  push    rbx
0x1801d5543  push    rsi
0x1801d5544  push    rdi
0x1801d5545  push    r12
0x1801d5547  push    r15
0x1801d5549  lea     rbp, [rsp-208h]
0x1801d5551  sub     rsp, 308h
0x1801d5558  mov     rax, cs:__security_cookie
0x1801d555f  xor     rax, rsp
0x1801d5562  mov     [rbp+230h+var_40], rax
0x1801d5569  mov     ebx, 1
0x1801d556e  lea     rax, [rbp+230h+var_2A0]
0x1801d5572  mov     [rbp+230h+lpFileName], rax
0x1801d5576  mov     rdi, rcx
0x1801d5579  lea     rax, [rsp+330h+var_2B8]
0x1801d557e  mov     [rbp+230h+var_2A8], ebx
0x1801d5581  mov     esi, 30Ch
0x1801d5586  mov     [rsp+330h+lpPathName], rax
0x1801d558b  mov     r8b, bl
0x1801d558e  mov     [rsp+330h+var_2C0], ebx
0x1801d5592  mov     edx, esi
0x1801d5594  lea     rcx, [rbp+230h+lpFileName]
0x1801d5598  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x1801d559d  test    al, al
0x1801d559f  jz      loc_1801D563C
0x1801d55a5  mov     r8b, bl
0x1801d55a8  lea     rcx, [rsp+330h+lpPathName]
0x1801d55ad  mov     edx, esi
0x1801d55af  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x1801d55b4  test    al, al
0x1801d55b6  jz      loc_1801D563C
0x1801d55bc  movsxd  rdx, [rbp+230h+var_2A8]; unsigned __int64
0x1801d55c0  mov     r8, rdi; unsigned __int16 *
0x1801d55c3  mov     rcx, [rbp+230h+lpFileName]; unsigned __int16 *
0x1801d55c7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801d55cc  test    eax, eax
0x1801d55ce  js      short loc_1801D563C
0x1801d55d0  movsxd  rdx, [rbp+230h+var_2A8]; unsigned __int64
0x1801d55d4  lea     r8, asc_1802BF3C0; "\\*.*"
0x1801d55db  mov     rcx, [rbp+230h+lpFileName]; unsigned __int16 *
0x1801d55df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801d55e4  test    eax, eax
0x1801d55e6  js      short loc_1801D563C
0x1801d55e8  xor     edx, edx; Val
0x1801d55ea  lea     rcx, [rbp+230h+FindFileData]; void *
0x1801d55ee  mov     r8d, 250h; Size
0x1801d55f4  call    memset_0
0x1801d55f9  mov     rcx, [rbp+230h+lpFileName]; lpFileName
0x1801d55fd  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x1801d5601  call    cs:__imp_FindFirstFileW
0x1801d5608  nop     dword ptr [rax+rax+00h]
0x1801d560d  mov     rsi, rax
0x1801d5610  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801d5614  jnz     short loc_1801D5671
0x1801d5616  call    cs:__imp_GetLastError
0x1801d561d  nop     dword ptr [rax+rax+00h]
0x1801d5622  cmp     eax, 5
0x1801d5625  jz      short loc_1801D563C
0x1801d5627  call    cs:__imp_GetLastError
0x1801d562e  nop     dword ptr [rax+rax+00h]
0x1801d5633  cmp     eax, 2
0x1801d5636  jz      loc_1801D5889
0x1801d563c  lea     rcx, [rsp+330h+lpPathName]
0x1801d5641  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801d5646  lea     rcx, [rbp+230h+lpFileName]
0x1801d564a  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801d564f  xor     al, al
0x1801d5651  mov     rcx, [rbp+230h+var_40]
0x1801d5658  xor     rcx, rsp; StackCookie
0x1801d565b  call    __security_check_cookie
0x1801d5660  add     rsp, 308h
0x1801d5667  pop     r15
0x1801d5669  pop     r12
0x1801d566b  pop     rdi
0x1801d566c  pop     rsi
0x1801d566d  pop     rbx
0x1801d566e  pop     rbp
0x1801d566f  retn
0x1801d5671  mov     r12d, 2Eh ; '.'
0x1801d5677  lea     r15, aNull; "(NULL)"
0x1801d567e  movzx   edx, [rbp+230h+FindFileData.cFileName]
0x1801d5682  sub     edx, r12d
0x1801d5685  jnz     short loc_1801D5692
0x1801d5687  movzx   edx, [rbp+230h+FindFileData.cFileName+2]
0x1801d568b  xor     eax, eax
0x1801d568d  movzx   ecx, ax
0x1801d5690  sub     edx, ecx
0x1801d5692  test    edx, edx
0x1801d5694  jz      loc_1801D580D
0x1801d569a  movzx   edx, [rbp+230h+FindFileData.cFileName]
0x1801d569e  sub     edx, r12d
0x1801d56a1  jnz     short loc_1801D56B7
0x1801d56a3  movzx   edx, [rbp+230h+FindFileData.cFileName+2]
0x1801d56a7  sub     edx, r12d
0x1801d56aa  jnz     short loc_1801D56B7
0x1801d56ac  movzx   edx, [rbp+230h+FindFileData.cFileName+4]
0x1801d56b0  xor     eax, eax
0x1801d56b2  movzx   ecx, ax
0x1801d56b5  sub     edx, ecx
0x1801d56b7  test    edx, edx
0x1801d56b9  jz      loc_1801D580D
0x1801d56bf  movsxd  rdx, [rsp+330h+var_2C0]; unsigned __int64
0x1801d56c4  mov     r8, rdi; unsigned __int16 *
0x1801d56c7  mov     rcx, [rsp+330h+lpPathName]; unsigned __int16 *
0x1801d56cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801d56d1  test    eax, eax
0x1801d56d3  js      loc_1801D580D
0x1801d56d9  movsxd  rdx, [rsp+330h+var_2C0]; unsigned __int64
0x1801d56de  lea     r8, asc_18027979C; "\\"
0x1801d56e5  mov     rcx, [rsp+330h+lpPathName]; unsigned __int16 *
0x1801d56ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801d56ef  test    eax, eax
0x1801d56f1  js      loc_1801D580D
0x1801d56f7  movsxd  rdx, [rsp+330h+var_2C0]; unsigned __int64
0x1801d56fc  lea     r8, [rbp+230h+FindFileData.cFileName]; unsigned __int16 *
0x1801d5700  mov     rcx, [rsp+330h+lpPathName]; unsigned __int16 *
0x1801d5705  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801d570a  test    eax, eax
0x1801d570c  js      loc_1801D580D
0x1801d5712  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x1801d5716  jz      short loc_1801D5770
0x1801d5718  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801d571f  jz      short loc_1801D5761
0x1801d5721  mov     rax, [rsp+330h+lpPathName]
0x1801d5726  lea     r9, aFdeletefolderD; "FDeleteFolder: Deleting folder '%s'"
0x1801d572d  xor     edx, edx; unsigned __int16
0x1801d572f  xor     r8d, r8d; int
0x1801d5732  mov     [rsp+330h+var_2D8], rdx; void *
0x1801d5737  mov     [rsp+330h+var_2E0], edx; unsigned int
0x1801d573b  mov     [rsp+330h+var_2E8], r15; unsigned __int16 *
0x1801d5740  mov     [rsp+330h+var_2F0], r15; unsigned __int16 *
0x1801d5745  lea     ecx, [rdx+0Ah]; int
0x1801d5748  mov     [rsp+330h+var_2F8], r15; unsigned __int16 *
0x1801d574d  mov     [rsp+330h+var_300], r15; unsigned __int16 *
0x1801d5752  mov     [rsp+330h+var_308], r15; unsigned __int16 *
0x1801d5757  mov     [rsp+330h+var_310], rax; unsigned __int16 *
0x1801d575c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801d5761  mov     rcx, [rsp+330h+lpPathName]; unsigned __int16 *
0x1801d5766  call    ?FDeleteFolder@@YA_NPEBG@Z; FDeleteFolder(ushort const *)
0x1801d576b  jmp     loc_1801D580D
0x1801d5770  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801d5777  jz      short loc_1801D57B9
0x1801d5779  mov     rax, [rsp+330h+lpPathName]
0x1801d577e  lea     r9, aFdeletefolderD_0; "FDeleteFolder: Deleting file '%s'"
0x1801d5785  xor     edx, edx; unsigned __int16
0x1801d5787  xor     r8d, r8d; int
0x1801d578a  mov     [rsp+330h+var_2D8], rdx; void *
0x1801d578f  mov     [rsp+330h+var_2E0], edx; unsigned int
0x1801d5793  mov     [rsp+330h+var_2E8], r15; unsigned __int16 *
0x1801d5798  mov     [rsp+330h+var_2F0], r15; unsigned __int16 *
0x1801d579d  lea     ecx, [rdx+0Ah]; int
0x1801d57a0  mov     [rsp+330h+var_2F8], r15; unsigned __int16 *
0x1801d57a5  mov     [rsp+330h+var_300], r15; unsigned __int16 *
0x1801d57aa  mov     [rsp+330h+var_308], r15; unsigned __int16 *
0x1801d57af  mov     [rsp+330h+var_310], rax; unsigned __int16 *
0x1801d57b4  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801d57b9  mov     rcx, [rsp+330h+lpPathName]; lpFileName
0x1801d57be  call    cs:__imp_DeleteFileW
0x1801d57c5  nop     dword ptr [rax+rax+00h]
0x1801d57ca  test    eax, eax
0x1801d57cc  jnz     short loc_1801D580D
0x1801d57ce  mov     rcx, [rsp+330h+lpPathName]; lpFileName
0x1801d57d3  xor     edx, edx; bool
0x1801d57d5  call    ?LockdownPath@@YAPEAVIMsiRecord@@PEBG_N@Z; LockdownPath(ushort const *,bool)
0x1801d57da  mov     rcx, [rsp+330h+lpPathName]; lpFileName
0x1801d57df  xor     edx, edx; dwFileAttributes
0x1801d57e1  mov     [rsp+330h+var_2D0], rax
0x1801d57e6  call    cs:__imp_SetFileAttributesW
0x1801d57ed  nop     dword ptr [rax+rax+00h]
0x1801d57f2  mov     rcx, [rsp+330h+lpPathName]; lpFileName
0x1801d57f7  call    cs:__imp_DeleteFileW
0x1801d57fe  nop     dword ptr [rax+rax+00h]
0x1801d5803  lea     rcx, [rsp+330h+var_2D0]
0x1801d5808  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801d580d  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x1801d5811  mov     rcx, rsi; hFindFile
0x1801d5814  call    cs:__imp_FindNextFileW
0x1801d581b  nop     dword ptr [rax+rax+00h]
0x1801d5820  cmp     eax, ebx
0x1801d5822  jz      loc_1801D567E
0x1801d5828  mov     rcx, rsi; hFindFile
0x1801d582b  call    cs:__imp_FindClose
0x1801d5832  nop     dword ptr [rax+rax+00h]
0x1801d5837  mov     rcx, rdi; lpPathName
0x1801d583a  call    cs:__imp_RemoveDirectoryW
0x1801d5841  nop     dword ptr [rax+rax+00h]
0x1801d5846  test    eax, eax
0x1801d5848  jnz     short loc_1801D5889
0x1801d584a  xor     edx, edx; bool
0x1801d584c  mov     rcx, rdi; lpFileName
0x1801d584f  call    ?LockdownPath@@YAPEAVIMsiRecord@@PEBG_N@Z; LockdownPath(ushort const *,bool)
0x1801d5854  xor     edx, edx; dwFileAttributes
0x1801d5856  mov     [rsp+330h+var_2D0], rax
0x1801d585b  mov     rcx, rdi; lpFileName
0x1801d585e  call    cs:__imp_SetFileAttributesW
0x1801d5865  nop     dword ptr [rax+rax+00h]
0x1801d586a  mov     rcx, rdi; lpPathName
0x1801d586d  call    cs:__imp_RemoveDirectoryW
0x1801d5874  nop     dword ptr [rax+rax+00h]
0x1801d5879  lea     rcx, [rsp+330h+var_2D0]
0x1801d587e  test    eax, eax
0x1801d5880  jnz     short loc_1801D58A3
0x1801d5882  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801d5887  xor     bl, bl
0x1801d5889  lea     rcx, [rsp+330h+lpPathName]
0x1801d588e  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801d5893  lea     rcx, [rbp+230h+lpFileName]
0x1801d5897  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801d589c  mov     al, bl
0x1801d589e  jmp     loc_1801D5651
0x1801d58a3  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801d58a8  jmp     short loc_1801D5889
```
