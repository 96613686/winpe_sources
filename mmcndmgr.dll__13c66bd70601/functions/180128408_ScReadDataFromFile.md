# ScReadDataFromFile

- ea: `0x180128408`
- end: `0x18012864a`
- name: `ScReadDataFromFile`
- size: `578`
- prototype: `mmcerror::SC *__fastcall(mmcerror::SC *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180127e68`

## callees

- `0x1800304c0`
- `0x18003fc1c`
- `0x1800445e4`
- `0x180046360`
- `0x180128408`

## import_xrefs

- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1801285f2`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1801285f2`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180128431`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180128431`
- `mmcbase!?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z` at `0x1801284cc`
- `mmcbase!?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z` at `0x1801284cc`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18012860a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180128624`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18012860a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180128624`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180128468`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180128520`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180128577`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1801285af`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180128468`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180128520`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180128577`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1801285af`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180128449`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180128449`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18012847c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180128534`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18012858b`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1801285c3`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18012847c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180128534`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18012858b`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1801285c3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180128473`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18012852b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180128582`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1801285ba`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180128473`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18012852b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180128582`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1801285ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801284c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801284c1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801284e6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801284e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801284b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801284b2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801285e5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801285e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012862d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012862d`

## string_xrefs

- `0x18012843f`: `ScReadDataFromFile`

## pseudocode

```c
mmcerror::SC *__fastcall ScReadDataFromFile(mmcerror::SC *a1, const WCHAR *a2, __int64 a3)
{
  __int64 v6; // rax
  HANDLE FileW; // rax
  void *v8; // rdi
  DWORD LastError; // eax
  signed int FileSize; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-40h] BYREF
  DWORD FileSizeHigh[2]; // [rsp+48h] [rbp-38h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v17[8]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v18; // [rsp+60h] [rbp-20h]
  _BYTE v19[24]; // [rsp+68h] [rbp-18h] BYREF

  mmcerror::SC::SC(a1, 0);
  mmcerror::SC::SetFunctionName(a1, L"ScReadDataFromFile");
  v6 = ScCheckPointers(v19, a3, 2147942487LL);
  mmcerror::SC::operator=(a1, v6);
  mmcerror::SC::~SC((mmcerror::SC *)v19);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(a1) )
  {
    FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v8 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      mmcerror::SC::FromWin32(a1, LastError);
    }
    else
    {
      FileSizeHigh[1] = 0;
      FileSize = GetFileSize(FileW, &FileSizeHigh[1]);
      FileSizeHigh[0] = FileSize;
      if ( FileSizeHigh[1] || FileSize < 0 )
      {
        mmcerror::SC::operator=(a1, 2147549183LL);
      }
      else if ( FileSize )
      {
        v11 = CXMLBinary::ScAlloc(a3, v19, (unsigned int)FileSize, 0);
        mmcerror::SC::operator=(a1, v11);
        mmcerror::SC::~SC((mmcerror::SC *)v19);
        if ( !(unsigned __int8)mmcerror::SC::operator bool(a1) )
        {
          NumberOfBytesRead = 0;
          v17[0] = 0;
          v18 = a3;
          lpBuffer = 0;
          CXMLBinaryLock::ScLockWorker(v17, v19, &lpBuffer);
          mmcerror::SC::operator=(a1, v19);
          mmcerror::SC::~SC((mmcerror::SC *)v19);
          if ( !(unsigned __int8)mmcerror::SC::operator bool(a1) )
          {
            v12 = ScCheckPointers(v19, lpBuffer, 2147942414LL);
            mmcerror::SC::operator=(a1, v12);
            mmcerror::SC::~SC((mmcerror::SC *)v19);
            if ( !(unsigned __int8)mmcerror::SC::operator bool(a1) )
            {
              if ( ReadFile(v8, lpBuffer, FileSizeHigh[0], &NumberOfBytesRead, 0) )
              {
                if ( NumberOfBytesRead != FileSizeHigh[0] )
                  mmcerror::SC::operator=(a1, 2147549183LL);
              }
              else
              {
                mmcerror::SC::FromLastError(a1);
              }
            }
          }
          CXMLBinaryLock::~CXMLBinaryLock((CXMLBinaryLock *)v17);
        }
      }
      CloseHandle(v8);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180128408  mov     [rsp-18h+arg_8], rbx
0x18012840d  mov     [rsp-18h+arg_0], rcx
0x180128412  push    rbp
0x180128413  push    rsi
0x180128414  push    rdi
0x180128415  mov     rbp, rsp
0x180128418  sub     rsp, 80h
0x18012841f  mov     rsi, r8
0x180128422  mov     rdi, rdx
0x180128425  mov     rbx, rcx
0x180128428  mov     [rbp+arg_18], 1
0x18012842f  xor     edx, edx
0x180128431  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180128437  nop
0x180128438  mov     [rbp+arg_18], 1
0x18012843f  lea     rdx, aScreaddatafrom; "ScReadDataFromFile"
0x180128446  mov     rcx, rbx
0x180128449  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18012844f  mov     r8d, 80070057h
0x180128455  mov     rdx, rsi
0x180128458  lea     rcx, [rbp+var_18]
0x18012845c  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x180128461  nop
0x180128462  mov     rdx, rax
0x180128465  mov     rcx, rbx
0x180128468  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18012846e  nop
0x18012846f  lea     rcx, [rbp+var_18]
0x180128473  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180128479  mov     rcx, rbx
0x18012847c  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180128482  test    al, al
0x180128484  jnz     loc_180128634
0x18012848a  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180128493  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18012849b  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1801284a3  xor     r9d, r9d; lpSecurityAttributes
0x1801284a6  mov     edx, 80000000h; dwDesiredAccess
0x1801284ab  lea     r8d, [r9+1]; dwShareMode
0x1801284af  mov     rcx, rdi; lpFileName
0x1801284b2  call    cs:__imp_CreateFileW
0x1801284b8  mov     rdi, rax
0x1801284bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801284bf  jnz     short loc_1801284D7
0x1801284c1  call    cs:__imp_GetLastError
0x1801284c7  mov     edx, eax
0x1801284c9  mov     rcx, rbx
0x1801284cc  call    cs:__imp_?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z; mmcerror::SC::FromWin32(long)
0x1801284d2  jmp     loc_180128634
0x1801284d7  mov     qword ptr [rbp+FileSizeHigh], 0
0x1801284df  lea     rdx, [rbp+FileSizeHigh+4]; lpFileSizeHigh
0x1801284e3  mov     rcx, rdi; hFile
0x1801284e6  call    cs:__imp_GetFileSize
0x1801284ec  mov     [rbp+FileSizeHigh], eax
0x1801284ef  cmp     [rbp+FileSizeHigh+4], 0
0x1801284f3  jnz     loc_18012861C
0x1801284f9  test    eax, eax
0x1801284fb  js      loc_18012861C
0x180128501  jz      loc_18012862A
0x180128507  mov     r8d, eax
0x18012850a  xor     r9d, r9d
0x18012850d  lea     rdx, [rbp+var_18]
0x180128511  mov     rcx, rsi
0x180128514  call    ?ScAlloc@CXMLBinary@@QEAA?AVSC@mmcerror@@_K_N@Z; CXMLBinary::ScAlloc(unsigned __int64,bool)
0x180128519  nop
0x18012851a  mov     rdx, rax
0x18012851d  mov     rcx, rbx
0x180128520  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180128526  nop
0x180128527  lea     rcx, [rbp+var_18]
0x18012852b  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180128531  mov     rcx, rbx
0x180128534  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18012853a  test    al, al
0x18012853c  jnz     loc_18012862A
0x180128542  mov     [rbp+NumberOfBytesRead], 0
0x180128549  mov     [rbp+var_28], al
0x18012854c  mov     [rbp+var_20], rsi
0x180128550  mov     [rbp+lpBuffer], 0
0x180128558  lea     r8, [rbp+lpBuffer]
0x18012855c  lea     rdx, [rbp+var_18]
0x180128560  lea     rcx, [rbp+var_28]
0x180128564  call    ?ScLockWorker@CXMLBinaryLock@@AEAA?AVSC@mmcerror@@PEAPEAX@Z; CXMLBinaryLock::ScLockWorker(void * *)
0x180128569  mov     [rbp+arg_18], 3
0x180128570  lea     rdx, [rbp+var_18]
0x180128574  mov     rcx, rbx
0x180128577  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18012857d  nop
0x18012857e  lea     rcx, [rbp+var_18]
0x180128582  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180128588  mov     rcx, rbx
0x18012858b  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180128591  test    al, al
0x180128593  jnz     short loc_180128611
0x180128595  mov     r8d, 8007000Eh
0x18012859b  mov     rdx, [rbp+lpBuffer]
0x18012859f  lea     rcx, [rbp+var_18]
0x1801285a3  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1801285a8  nop
0x1801285a9  mov     rdx, rax
0x1801285ac  mov     rcx, rbx
0x1801285af  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1801285b5  nop
0x1801285b6  lea     rcx, [rbp+var_18]
0x1801285ba  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1801285c0  mov     rcx, rbx
0x1801285c3  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1801285c9  test    al, al
0x1801285cb  jnz     short loc_180128611
0x1801285cd  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x1801285d6  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801285da  mov     r8d, [rbp+FileSizeHigh]; nNumberOfBytesToRead
0x1801285de  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x1801285e2  mov     rcx, rdi; hFile
0x1801285e5  call    cs:__imp_ReadFile
0x1801285eb  test    eax, eax
0x1801285ed  jnz     short loc_1801285FA
0x1801285ef  mov     rcx, rbx
0x1801285f2  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x1801285f8  jmp     short loc_180128611
0x1801285fa  mov     eax, [rbp+FileSizeHigh]
0x1801285fd  cmp     [rbp+NumberOfBytesRead], eax
0x180128600  jz      short loc_180128611
0x180128602  mov     edx, 8000FFFFh
0x180128607  mov     rcx, rbx
0x18012860a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180128610  nop
0x180128611  lea     rcx, [rbp+var_28]; this
0x180128615  call    ??1CXMLBinaryLock@@QEAA@XZ; CXMLBinaryLock::~CXMLBinaryLock(void)
0x18012861a  jmp     short loc_18012862A
0x18012861c  mov     edx, 8000FFFFh
0x180128621  mov     rcx, rbx
0x180128624  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18012862a  mov     rcx, rdi; hObject
0x18012862d  call    cs:__imp_CloseHandle
0x180128633  nop
0x180128634  mov     rax, rbx
0x180128637  mov     rbx, [rsp+80h+arg_8]
0x18012863f  add     rsp, 80h
0x180128646  pop     rdi
0x180128647  pop     rsi
0x180128648  pop     rbp
0x180128649  retn
```
