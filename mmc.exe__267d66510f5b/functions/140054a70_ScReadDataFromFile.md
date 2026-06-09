# ScReadDataFromFile

- ea: `0x140054a70`
- end: `0x140054cbb`
- name: `ScReadDataFromFile`
- size: `587`
- prototype: `mmcerror::SC *__fastcall(mmcerror::SC *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x14001c1c8`

## callees

- `0x14000c1d0`
- `0x14001cad4`
- `0x1400391d4`
- `0x140054a70`
- `0x1400570e4`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140054ae7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140054b9c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140054bf3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140054c2b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140054ae7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140054b9c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140054bf3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140054c2b`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140054af0`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140054ba5`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140054bfc`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140054c34`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140054af0`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140054ba5`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140054bfc`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140054c34`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140054a99`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140054ac8`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140054a99`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140054ac8`
- `mmcbase!?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z` at `0x140054b40`
- `mmcbase!?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z` at `0x140054b40`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140054c63`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140054c63`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054c7b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054c95`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054c7b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054c95`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140054adc`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140054b91`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140054be8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140054c20`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140054adc`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140054b91`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140054be8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140054c20`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140054ab1`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140054ab1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140054b26`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140054b26`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140054c56`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140054c56`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x140054b5a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x140054b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054b35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140054c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140054c9e`

## string_xrefs

- `0x140054aa7`: `ScReadDataFromFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
mmcerror::SC *__fastcall ScReadDataFromFile(mmcerror::SC *a1, const WCHAR *a2, __int64 a3)
{
  int v6; // edx
  HANDLE FileW; // rax
  void *v8; // rdi
  DWORD LastError; // eax
  signed int FileSize; // eax
  mmcerror::SC *v11; // rax
  __int64 v12; // rax
  DWORD FileSizeHigh[2]; // [rsp+40h] [rbp-40h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v16[8]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-28h]
  _BYTE v18[24]; // [rsp+68h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B8h] [rbp+38h] BYREF

  mmcerror::SC::SC(a1, 0);
  mmcerror::SC::SetFunctionName(a1, L"ScReadDataFromFile");
  v6 = -2147024809;
  if ( a3 )
    v6 = 0;
  mmcerror::SC::SC((mmcerror::SC *)v16, v6);
  mmcerror::SC::operator=(a1, v16);
  mmcerror::SC::~SC((mmcerror::SC *)v16);
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
        v11 = CXMLBinary::ScAlloc(a3, (mmcerror::SC *)v18, (unsigned int)FileSize);
        mmcerror::SC::operator=(a1, v11);
        mmcerror::SC::~SC((mmcerror::SC *)v18);
        if ( !(unsigned __int8)mmcerror::SC::operator bool(a1) )
        {
          NumberOfBytesRead = 0;
          v16[0] = 0;
          v17 = a3;
          lpBuffer = 0;
          CXMLBinaryLock::ScLockWorker(v16, v18, &lpBuffer);
          mmcerror::SC::operator=(a1, v18);
          mmcerror::SC::~SC((mmcerror::SC *)v18);
          if ( !(unsigned __int8)mmcerror::SC::operator bool(a1) )
          {
            v12 = ScCheckPointers(v18, lpBuffer, 2147942414LL);
            mmcerror::SC::operator=(a1, v12);
            mmcerror::SC::~SC((mmcerror::SC *)v18);
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
          CXMLBinaryLock::~CXMLBinaryLock((CXMLBinaryLock *)v16);
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
0x140054a70  mov     [rsp-18h+arg_8], rbx
0x140054a75  mov     [rsp-18h+arg_0], rcx
0x140054a7a  push    rbp
0x140054a7b  push    rsi
0x140054a7c  push    rdi
0x140054a7d  mov     rbp, rsp
0x140054a80  sub     rsp, 80h
0x140054a87  mov     rsi, r8
0x140054a8a  mov     rdi, rdx
0x140054a8d  mov     rbx, rcx
0x140054a90  mov     [rbp+arg_10], 1
0x140054a97  xor     edx, edx
0x140054a99  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140054a9f  nop
0x140054aa0  mov     [rbp+arg_10], 1
0x140054aa7  lea     rdx, aScreaddatafrom; "ScReadDataFromFile"
0x140054aae  mov     rcx, rbx
0x140054ab1  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x140054ab7  mov     edx, 80070057h
0x140054abc  xor     eax, eax
0x140054abe  test    rsi, rsi
0x140054ac1  cmovnz  edx, eax
0x140054ac4  lea     rcx, [rbp+var_30]
0x140054ac8  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140054ace  mov     [rbp+arg_10], 3
0x140054ad5  lea     rdx, [rbp+var_30]
0x140054ad9  mov     rcx, rbx
0x140054adc  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140054ae2  nop
0x140054ae3  lea     rcx, [rbp+var_30]
0x140054ae7  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140054aed  mov     rcx, rbx
0x140054af0  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140054af6  test    al, al
0x140054af8  jnz     loc_140054CA5
0x140054afe  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x140054b07  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140054b0f  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x140054b17  xor     r9d, r9d; lpSecurityAttributes
0x140054b1a  mov     edx, 80000000h; dwDesiredAccess
0x140054b1f  lea     r8d, [r9+1]; dwShareMode
0x140054b23  mov     rcx, rdi; lpFileName
0x140054b26  call    cs:__imp_CreateFileW
0x140054b2c  mov     rdi, rax
0x140054b2f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140054b33  jnz     short loc_140054B4B
0x140054b35  call    cs:__imp_GetLastError
0x140054b3b  mov     edx, eax
0x140054b3d  mov     rcx, rbx
0x140054b40  call    cs:__imp_?FromWin32@SC@mmcerror@@QEAAAEAV12@J@Z; mmcerror::SC::FromWin32(long)
0x140054b46  jmp     loc_140054CA5
0x140054b4b  mov     qword ptr [rbp+FileSizeHigh], 0
0x140054b53  lea     rdx, [rbp+FileSizeHigh+4]; lpFileSizeHigh
0x140054b57  mov     rcx, rdi; hFile
0x140054b5a  call    cs:__imp_GetFileSize
0x140054b60  mov     [rbp+FileSizeHigh], eax
0x140054b63  cmp     [rbp+FileSizeHigh+4], 0
0x140054b67  jnz     loc_140054C8D
0x140054b6d  test    eax, eax
0x140054b6f  js      loc_140054C8D
0x140054b75  jz      loc_140054C9B
0x140054b7b  mov     r8d, eax
0x140054b7e  lea     rdx, [rbp+var_18]
0x140054b82  mov     rcx, rsi
0x140054b85  call    ?ScAlloc@CXMLBinary@@QEAA?AVSC@mmcerror@@_K_N@Z; CXMLBinary::ScAlloc(unsigned __int64,bool)
0x140054b8a  nop
0x140054b8b  mov     rdx, rax
0x140054b8e  mov     rcx, rbx
0x140054b91  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140054b97  nop
0x140054b98  lea     rcx, [rbp+var_18]
0x140054b9c  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140054ba2  mov     rcx, rbx
0x140054ba5  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140054bab  test    al, al
0x140054bad  jnz     loc_140054C9B
0x140054bb3  mov     [rbp+NumberOfBytesRead], 0
0x140054bba  mov     [rbp+var_30], al
0x140054bbd  mov     [rbp+var_28], rsi
0x140054bc1  mov     [rbp+lpBuffer], 0
0x140054bc9  lea     r8, [rbp+lpBuffer]
0x140054bcd  lea     rdx, [rbp+var_18]
0x140054bd1  lea     rcx, [rbp+var_30]
0x140054bd5  call    ?ScLockWorker@CXMLBinaryLock@@AEAA?AVSC@mmcerror@@PEAPEAX@Z; CXMLBinaryLock::ScLockWorker(void * *)
0x140054bda  mov     [rbp+arg_10], 7
0x140054be1  lea     rdx, [rbp+var_18]
0x140054be5  mov     rcx, rbx
0x140054be8  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140054bee  nop
0x140054bef  lea     rcx, [rbp+var_18]
0x140054bf3  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140054bf9  mov     rcx, rbx
0x140054bfc  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140054c02  test    al, al
0x140054c04  jnz     short loc_140054C82
0x140054c06  mov     r8d, 8007000Eh
0x140054c0c  mov     rdx, [rbp+lpBuffer]
0x140054c10  lea     rcx, [rbp+var_18]
0x140054c14  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x140054c19  nop
0x140054c1a  mov     rdx, rax
0x140054c1d  mov     rcx, rbx
0x140054c20  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140054c26  nop
0x140054c27  lea     rcx, [rbp+var_18]
0x140054c2b  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140054c31  mov     rcx, rbx
0x140054c34  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140054c3a  test    al, al
0x140054c3c  jnz     short loc_140054C82
0x140054c3e  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x140054c47  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140054c4b  mov     r8d, [rbp+FileSizeHigh]; nNumberOfBytesToRead
0x140054c4f  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x140054c53  mov     rcx, rdi; hFile
0x140054c56  call    cs:__imp_ReadFile
0x140054c5c  test    eax, eax
0x140054c5e  jnz     short loc_140054C6B
0x140054c60  mov     rcx, rbx
0x140054c63  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x140054c69  jmp     short loc_140054C82
0x140054c6b  mov     eax, [rbp+FileSizeHigh]
0x140054c6e  cmp     [rbp+NumberOfBytesRead], eax
0x140054c71  jz      short loc_140054C82
0x140054c73  mov     edx, 8000FFFFh
0x140054c78  mov     rcx, rbx
0x140054c7b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140054c81  nop
0x140054c82  lea     rcx, [rbp+var_30]; this
0x140054c86  call    ??1CXMLBinaryLock@@QEAA@XZ; CXMLBinaryLock::~CXMLBinaryLock(void)
0x140054c8b  jmp     short loc_140054C9B
0x140054c8d  mov     edx, 8000FFFFh
0x140054c92  mov     rcx, rbx
0x140054c95  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140054c9b  mov     rcx, rdi; hObject
0x140054c9e  call    cs:__imp_CloseHandle
0x140054ca4  nop
0x140054ca5  mov     rax, rbx
0x140054ca8  mov     rbx, [rsp+80h+arg_8]
0x140054cb0  add     rsp, 80h
0x140054cb7  pop     rdi
0x140054cb8  pop     rsi
0x140054cb9  pop     rbp
0x140054cba  retn
```
