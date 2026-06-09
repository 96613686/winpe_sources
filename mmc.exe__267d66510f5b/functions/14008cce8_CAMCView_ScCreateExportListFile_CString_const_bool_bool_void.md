# CAMCView::ScCreateExportListFile(CString const &,bool,bool,void * &)

- ea: `0x14008cce8`
- end: `0x14008ced7`
- name: `?ScCreateExportListFile@CAMCView@@AEAA?AVSC@mmcerror@@AEBVCString@@_N1AEAPEAX@Z`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140094ec0`

## callees

- `0x1400871a4`
- `0x14008cce8`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14008cd18`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14008cd18`
- `mmcbase!?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z` at `0x14008cdbe`
- `mmcbase!?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z` at `0x14008ce53`
- `mmcbase!?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z` at `0x14008cdbe`
- `mmcbase!?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z` at `0x14008ce53`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x14008cdc7`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x14008ce5c`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x14008cea3`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x14008cdc7`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x14008ce5c`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x14008cea3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14008cd73`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14008cdd9`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14008ce6e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14008cd73`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14008cdd9`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14008ce6e`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14008cd30`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14008cd30`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14008ce34`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14008ce34`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14008cda5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14008cda5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008ce83`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008ce83`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14008cd48`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14008cd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008cdb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ce48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008cdb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ce48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008ce77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008ceb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008ce77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008ceb5`

## string_xrefs

- `0x14008cd26`: `CAMCView::ScCreateExportListFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
mmcerror::SC *__fastcall CAMCView::ScCreateExportListFile(
        __int64 a1,
        mmcerror::SC *a2,
        LPCWSTR *a3,
        char a4,
        char a5,
        HANDLE *NumberOfBytesWritten)
{
  HANDLE *v9; // rdi
  DWORD FileAttributesW; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  HANDLE FileW; // rax
  DWORD LastError; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  DWORD v18; // eax
  __int64 Buffer; // [rsp+70h] [rbp+8h] BYREF
  mmcerror::SC *v21; // [rsp+78h] [rbp+10h]

  v21 = a2;
  Buffer = a1;
  mmcerror::SC::SC(a2, 0);
  mmcerror::SC::SetFunctionName(a2, L"CAMCView::ScCreateExportListFile");
  v9 = NumberOfBytesWritten;
  *NumberOfBytesWritten = (HANDLE)-1LL;
  FileAttributesW = GetFileAttributesW(*a3);
  if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
  {
    if ( a5 )
      CAMCView::ListSaveErrorMes(v11, 0, v12, *a3);
    mmcerror::SC::operator=(a2, 2147942405LL);
    goto LABEL_19;
  }
  FileW = CreateFileW(*a3, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  *v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    mmcerror::SC::FromWin32(a2, LastError);
    if ( !mmcerror::SC::IsError(a2) )
      mmcerror::SC::operator=(a2, 2147549183LL);
    if ( a5 )
    {
      v17 = 1;
LABEL_18:
      CAMCView::ListSaveErrorMes(v15, v17, v16, *a3);
    }
  }
  else if ( a4 )
  {
    LOWORD(Buffer) = -257;
    LODWORD(NumberOfBytesWritten) = 0;
    if ( !WriteFile(FileW, &Buffer, 2u, (LPDWORD)&NumberOfBytesWritten, 0) || (_DWORD)NumberOfBytesWritten != 2 )
    {
      v18 = GetLastError();
      mmcerror::SC::FromWin32(a2, v18);
      if ( !mmcerror::SC::IsError(a2) )
        mmcerror::SC::operator=(a2, 2147549183LL);
      CloseHandle(*v9);
      *v9 = (HANDLE)-1LL;
      DeleteFileW(*a3);
      if ( a5 )
      {
        v17 = 2;
        goto LABEL_18;
      }
    }
  }
LABEL_19:
  if ( mmcerror::SC::IsError(a2) && *v9 != (HANDLE)-1LL )
  {
    CloseHandle(*v9);
    *v9 = (HANDLE)-1LL;
  }
  return a2;
}

```

## disassembly

```asm
0x14008cce8  mov     rax, rsp
0x14008cceb  mov     [rax+18h], rbx
0x14008ccef  mov     [rax+20h], rbp
0x14008ccf3  mov     [rax+10h], rdx
0x14008ccf7  mov     [rax+8], rcx
0x14008ccfb  push    rsi
0x14008ccfc  push    rdi
0x14008ccfd  push    r12
0x14008ccff  sub     rsp, 50h
0x14008cd03  mov     bpl, r9b
0x14008cd06  mov     rsi, r8
0x14008cd09  mov     rbx, rdx
0x14008cd0c  mov     dword ptr [rax-28h], 0
0x14008cd13  xor     edx, edx
0x14008cd15  mov     rcx, rbx
0x14008cd18  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14008cd1e  mov     [rsp+68h+var_28], 1
0x14008cd26  lea     rdx, aCamcviewSccrea_0; "CAMCView::ScCreateExportListFile"
0x14008cd2d  mov     rcx, rbx
0x14008cd30  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14008cd36  or      r12, 0FFFFFFFFFFFFFFFFh
0x14008cd3a  mov     rdi, [rsp+68h+NumberOfBytesWritten]
0x14008cd42  mov     [rdi], r12
0x14008cd45  mov     rcx, [rsi]; lpFileName
0x14008cd48  call    cs:__imp_GetFileAttributesW
0x14008cd4e  cmp     eax, 0FFFFFFFFh
0x14008cd51  jz      short loc_14008CD7E
0x14008cd53  test    al, 1
0x14008cd55  jz      short loc_14008CD7E
0x14008cd57  cmp     [rsp+68h+arg_20], 0
0x14008cd5f  jz      short loc_14008CD6B
0x14008cd61  mov     r9, [rsi]
0x14008cd64  xor     edx, edx
0x14008cd66  call    ?ListSaveErrorMes@CAMCView@@AEAAXW4EListSaveErrorType@1@PEAXPEBG@Z; CAMCView::ListSaveErrorMes(CAMCView::EListSaveErrorType,void *,ushort const *)
0x14008cd6b  mov     edx, 80070005h
0x14008cd70  mov     rcx, rbx
0x14008cd73  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14008cd79  jmp     loc_14008CEA0
0x14008cd7e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x14008cd87  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14008cd8f  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x14008cd97  xor     r9d, r9d; lpSecurityAttributes
0x14008cd9a  xor     r8d, r8d; dwShareMode
0x14008cd9d  mov     edx, 40000000h; dwDesiredAccess
0x14008cda2  mov     rcx, [rsi]; lpFileName
0x14008cda5  call    cs:__imp_CreateFileW
0x14008cdab  mov     [rdi], rax
0x14008cdae  cmp     rax, r12
0x14008cdb1  jnz     short loc_14008CDF7
0x14008cdb3  call    cs:__imp_GetLastError
0x14008cdb9  mov     edx, eax
0x14008cdbb  mov     rcx, rbx
0x14008cdbe  call    cs:__imp_?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z; mmcerror::SC::FromWin32(long)
0x14008cdc4  mov     rcx, rbx
0x14008cdc7  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x14008cdcd  test    al, al
0x14008cdcf  jnz     short loc_14008CDDF
0x14008cdd1  mov     edx, 8000FFFFh
0x14008cdd6  mov     rcx, rbx
0x14008cdd9  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14008cddf  cmp     [rsp+68h+arg_20], 0
0x14008cde7  jz      loc_14008CEA0
0x14008cded  mov     edx, 1
0x14008cdf2  jmp     loc_14008CE98
0x14008cdf7  test    bpl, bpl
0x14008cdfa  jz      loc_14008CEA0
0x14008ce00  mov     ecx, 0FEFFh
0x14008ce05  mov     word ptr [rsp+68h+Buffer], cx
0x14008ce0a  mov     dword ptr [rsp+68h+NumberOfBytesWritten], 0
0x14008ce15  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x14008ce1e  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14008ce26  mov     r8d, 2; nNumberOfBytesToWrite
0x14008ce2c  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x14008ce31  mov     rcx, rax; hFile
0x14008ce34  call    cs:__imp_WriteFile
0x14008ce3a  test    eax, eax
0x14008ce3c  jz      short loc_14008CE48
0x14008ce3e  cmp     dword ptr [rsp+68h+NumberOfBytesWritten], 2
0x14008ce46  jz      short loc_14008CEA0
0x14008ce48  call    cs:__imp_GetLastError
0x14008ce4e  mov     edx, eax
0x14008ce50  mov     rcx, rbx
0x14008ce53  call    cs:__imp_?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z; mmcerror::SC::FromWin32(long)
0x14008ce59  mov     rcx, rbx
0x14008ce5c  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x14008ce62  test    al, al
0x14008ce64  jnz     short loc_14008CE74
0x14008ce66  mov     edx, 8000FFFFh
0x14008ce6b  mov     rcx, rbx
0x14008ce6e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14008ce74  mov     rcx, [rdi]; hObject
0x14008ce77  call    cs:__imp_CloseHandle
0x14008ce7d  mov     [rdi], r12
0x14008ce80  mov     rcx, [rsi]; lpFileName
0x14008ce83  call    cs:__imp_DeleteFileW
0x14008ce89  cmp     [rsp+68h+arg_20], 0
0x14008ce91  jz      short loc_14008CEA0
0x14008ce93  mov     edx, 2
0x14008ce98  mov     r9, [rsi]
0x14008ce9b  call    ?ListSaveErrorMes@CAMCView@@AEAAXW4EListSaveErrorType@1@PEAXPEBG@Z; CAMCView::ListSaveErrorMes(CAMCView::EListSaveErrorType,void *,ushort const *)
0x14008cea0  mov     rcx, rbx
0x14008cea3  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x14008cea9  test    al, al
0x14008ceab  jz      short loc_14008CEBE
0x14008cead  cmp     [rdi], r12
0x14008ceb0  jz      short loc_14008CEBE
0x14008ceb2  mov     rcx, [rdi]; hObject
0x14008ceb5  call    cs:__imp_CloseHandle
0x14008cebb  mov     [rdi], r12
0x14008cebe  mov     rax, rbx
0x14008cec1  lea     r11, [rsp+68h+var_18]
0x14008cec6  mov     rbx, [r11+30h]
0x14008ceca  mov     rbp, [r11+38h]
0x14008cece  mov     rsp, r11
0x14008ced1  pop     r12
0x14008ced3  pop     rdi
0x14008ced4  pop     rsi
0x14008ced5  retn
```
