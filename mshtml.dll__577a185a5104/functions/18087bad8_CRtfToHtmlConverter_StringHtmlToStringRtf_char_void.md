# CRtfToHtmlConverter::StringHtmlToStringRtf(char *,void * *)

- ea: `0x18087bad8`
- end: `0x18087bd36`
- name: `?StringHtmlToStringRtf@CRtfToHtmlConverter@@IEAAJPEADPEAPEAX@Z`
- size: `606`
- prototype: `__int64 __fastcall(CDoc **this, _BYTE *lpBuffer, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180e10cd0`

## callees

- `0x18087b610`
- `0x18087bad8`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18087bc8b`
- `KERNEL32!GlobalLock` at `0x18087bc8b`
- `KERNEL32!GlobalUnlock` at `0x18087bcef`
- `KERNEL32!GlobalUnlock` at `0x18087bcef`
- `KERNEL32!WriteFile` at `0x18087bbd8`
- `KERNEL32!WriteFile` at `0x18087bbd8`
- `KERNEL32!ReadFile` at `0x18087bcb6`
- `KERNEL32!ReadFile` at `0x18087bcb6`
- `KERNEL32!GlobalAlloc` at `0x18087bc79`
- `KERNEL32!GlobalAlloc` at `0x18087bc79`
- `KERNEL32!GetTempPath2W` at `0x18087bb2b`
- `KERNEL32!GetTempPath2W` at `0x18087bb2b`
- `KERNEL32!GetTempFileNameW` at `0x18087bb4d`
- `KERNEL32!GetTempFileNameW` at `0x18087bb71`
- `KERNEL32!GetTempFileNameW` at `0x18087bb4d`
- `KERNEL32!GetTempFileNameW` at `0x18087bb71`
- `KERNEL32!CreateFileW` at `0x18087bba2`
- `KERNEL32!CreateFileW` at `0x18087bc43`
- `KERNEL32!CreateFileW` at `0x18087bba2`
- `KERNEL32!CreateFileW` at `0x18087bc43`
- `KERNEL32!GetFileSize` at `0x18087bc61`
- `KERNEL32!GetFileSize` at `0x18087bc61`
- `KERNEL32!DeleteFileW` at `0x18087bd00`
- `KERNEL32!DeleteFileW` at `0x18087bd00`
- `KERNEL32!CloseHandle` at `0x18087bbe9`
- `KERNEL32!CloseHandle` at `0x18087bcc7`
- `KERNEL32!CloseHandle` at `0x18087bbe9`
- `KERNEL32!CloseHandle` at `0x18087bcc7`

## pseudocode

```c
__int64 __fastcall CRtfToHtmlConverter::StringHtmlToStringRtf(CDoc **this, _BYTE *lpBuffer, void **a3)
{
  _BYTE *v6; // rdi
  HANDLE FileW; // rax
  void *v8; // rsi
  __int64 v9; // r8
  BOOL v10; // ebx
  unsigned int v11; // r14d
  HANDLE v12; // rax
  void *v13; // rsi
  DWORD FileSize; // eax
  DWORD v15; // ebx
  HGLOBAL v16; // rax
  _BYTE *v17; // rax
  BOOL v18; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR TempFileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR PathName[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+470h] [rbp+370h] BYREF

  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  v6 = 0;
  GetTempPath2W(260, PathName);
  GetTempFileNameW(PathName, L"h2r", 0, TempFileName);
  GetTempFileNameW(PathName, L"h2r", 0, FileName);
  FileW = CreateFileW(TempFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpBuffer[v9] );
    v10 = WriteFile(FileW, lpBuffer, v9, &NumberOfBytesWritten, 0);
    CloseHandle(v8);
    if ( v10 )
    {
      v11 = CRtfToHtmlConverter::InternalHtmlToExternalRtf(this, FileName, TempFileName);
      if ( !v11 )
      {
        v12 = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x4000000u, 0);
        v13 = v12;
        if ( v12 != (HANDLE)-1LL )
        {
          FileSize = GetFileSize(v12, 0);
          v15 = FileSize;
          if ( FileSize != -1 )
          {
            v16 = GlobalAlloc(0, FileSize + 1);
            *a3 = v16;
            v17 = GlobalLock(v16);
            v6 = v17;
            if ( v17 )
            {
              v18 = ReadFile(v13, v17, v15, &NumberOfBytesRead, 0);
              CloseHandle(v13);
              if ( v18 )
              {
                v6[NumberOfBytesRead] = 0;
LABEL_12:
                GlobalUnlock(*a3);
                goto LABEL_13;
              }
            }
          }
        }
      }
    }
  }
  v11 = -2147467259;
  if ( v6 )
    goto LABEL_12;
LABEL_13:
  DeleteFileW(TempFileName);
  return v11;
}

```

## disassembly

```asm
0x18087bad8  mov     [rsp-8+arg_18], rbx
0x18087badd  push    rbp
0x18087bade  push    rsi
0x18087badf  push    rdi
0x18087bae0  push    r14
0x18087bae2  push    r15
0x18087bae4  lea     rbp, [rsp-590h]
0x18087baec  sub     rsp, 690h
0x18087baf3  mov     rax, cs:__security_cookie
0x18087bafa  xor     rax, rsp
0x18087bafd  mov     [rbp+5B0h+var_30], rax
0x18087bb04  mov     rbx, rdx
0x18087bb07  mov     [rsp+6B0h+NumberOfBytesRead], 0
0x18087bb0f  mov     r14, rcx
0x18087bb12  mov     [rsp+6B0h+NumberOfBytesWritten], 0
0x18087bb1a  lea     rdx, [rbp+5B0h+PathName]
0x18087bb21  mov     ecx, 104h
0x18087bb26  mov     r15, r8
0x18087bb29  xor     edi, edi
0x18087bb2b  call    cs:__imp_GetTempPath2W
0x18087bb32  nop     dword ptr [rax+rax+00h]
0x18087bb37  lea     r9, [rsp+6B0h+TempFileName]; lpTempFileName
0x18087bb3c  xor     r8d, r8d; uUnique
0x18087bb3f  lea     rdx, aH2r; "h2r"
0x18087bb46  lea     rcx, [rbp+5B0h+PathName]; lpPathName
0x18087bb4d  call    cs:__imp_GetTempFileNameW
0x18087bb54  nop     dword ptr [rax+rax+00h]
0x18087bb59  lea     r9, [rbp+5B0h+FileName]; lpTempFileName
0x18087bb60  xor     r8d, r8d; uUnique
0x18087bb63  lea     rdx, aH2r; "h2r"
0x18087bb6a  lea     rcx, [rbp+5B0h+PathName]; lpPathName
0x18087bb71  call    cs:__imp_GetTempFileNameW
0x18087bb78  nop     dword ptr [rax+rax+00h]
0x18087bb7d  mov     [rsp+6B0h+hTemplateFile], rdi; hTemplateFile
0x18087bb82  lea     rcx, [rsp+6B0h+TempFileName]; lpFileName
0x18087bb87  mov     [rsp+6B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18087bb8f  xor     r9d, r9d; lpSecurityAttributes
0x18087bb92  xor     r8d, r8d; dwShareMode
0x18087bb95  mov     [rsp+6B0h+dwCreationDisposition], 2; dwCreationDisposition
0x18087bb9d  mov     edx, 40000000h; dwDesiredAccess
0x18087bba2  call    cs:__imp_CreateFileW
0x18087bba9  nop     dword ptr [rax+rax+00h]
0x18087bbae  mov     rsi, rax
0x18087bbb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18087bbb5  jz      loc_18087BCE1
0x18087bbbb  or      r8, 0FFFFFFFFFFFFFFFFh
0x18087bbbf  inc     r8; nNumberOfBytesToWrite
0x18087bbc2  cmp     [rbx+r8], dil
0x18087bbc6  jnz     short loc_18087BBBF
0x18087bbc8  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18087bbcd  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOverlapped
0x18087bbd2  mov     rdx, rbx; lpBuffer
0x18087bbd5  mov     rcx, rsi; hFile
0x18087bbd8  call    cs:__imp_WriteFile
0x18087bbdf  nop     dword ptr [rax+rax+00h]
0x18087bbe4  mov     rcx, rsi; hObject
0x18087bbe7  mov     ebx, eax
0x18087bbe9  call    cs:__imp_CloseHandle
0x18087bbf0  nop     dword ptr [rax+rax+00h]
0x18087bbf5  test    ebx, ebx
0x18087bbf7  jz      loc_18087BCE1
0x18087bbfd  lea     r8, [rsp+6B0h+TempFileName]; unsigned __int16 *
0x18087bc02  mov     rcx, r14; this
0x18087bc05  lea     rdx, [rbp+5B0h+FileName]; unsigned __int16 *
0x18087bc0c  call    ?InternalHtmlToExternalRtf@CRtfToHtmlConverter@@IEAAJPEBG0@Z; CRtfToHtmlConverter::InternalHtmlToExternalRtf(ushort const *,ushort const *)
0x18087bc11  mov     r14d, eax
0x18087bc14  test    eax, eax
0x18087bc16  jnz     loc_18087BCE1
0x18087bc1c  mov     [rsp+6B0h+hTemplateFile], rdi; hTemplateFile
0x18087bc21  lea     rcx, [rbp+5B0h+FileName]; lpFileName
0x18087bc28  mov     [rsp+6B0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x18087bc30  xor     r9d, r9d; lpSecurityAttributes
0x18087bc33  xor     r8d, r8d; dwShareMode
0x18087bc36  mov     [rsp+6B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18087bc3e  mov     edx, 80000000h; dwDesiredAccess
0x18087bc43  call    cs:__imp_CreateFileW
0x18087bc4a  nop     dword ptr [rax+rax+00h]
0x18087bc4f  mov     rsi, rax
0x18087bc52  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18087bc56  jz      loc_18087BCE1
0x18087bc5c  xor     edx, edx; lpFileSizeHigh
0x18087bc5e  mov     rcx, rax; hFile
0x18087bc61  call    cs:__imp_GetFileSize
0x18087bc68  nop     dword ptr [rax+rax+00h]
0x18087bc6d  mov     ebx, eax
0x18087bc6f  cmp     eax, 0FFFFFFFFh
0x18087bc72  jz      short loc_18087BCE1
0x18087bc74  lea     edx, [rax+1]; dwBytes
0x18087bc77  xor     ecx, ecx; uFlags
0x18087bc79  call    cs:__imp_GlobalAlloc
0x18087bc80  nop     dword ptr [rax+rax+00h]
0x18087bc85  mov     rcx, rax; hMem
0x18087bc88  mov     [r15], rax
0x18087bc8b  call    cs:__imp_GlobalLock
0x18087bc92  nop     dword ptr [rax+rax+00h]
0x18087bc97  mov     rdi, rax
0x18087bc9a  test    rax, rax
0x18087bc9d  jz      short loc_18087BCE1
0x18087bc9f  lea     r9, [rsp+6B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18087bca4  mov     qword ptr [rsp+6B0h+dwCreationDisposition], 0; lpOverlapped
0x18087bcad  mov     r8d, ebx; nNumberOfBytesToRead
0x18087bcb0  mov     rdx, rax; lpBuffer
0x18087bcb3  mov     rcx, rsi; hFile
0x18087bcb6  call    cs:__imp_ReadFile
0x18087bcbd  nop     dword ptr [rax+rax+00h]
0x18087bcc2  mov     rcx, rsi; hObject
0x18087bcc5  mov     ebx, eax
0x18087bcc7  call    cs:__imp_CloseHandle
0x18087bcce  nop     dword ptr [rax+rax+00h]
0x18087bcd3  test    ebx, ebx
0x18087bcd5  jz      short loc_18087BCE1
0x18087bcd7  mov     eax, [rsp+6B0h+NumberOfBytesRead]
0x18087bcdb  mov     [rax+rdi], r14b
0x18087bcdf  jmp     short loc_18087BCEC
0x18087bce1  mov     r14d, 80004005h
0x18087bce7  test    rdi, rdi
0x18087bcea  jz      short loc_18087BCFB
0x18087bcec  mov     rcx, [r15]; hMem
0x18087bcef  call    cs:__imp_GlobalUnlock
0x18087bcf6  nop     dword ptr [rax+rax+00h]
0x18087bcfb  lea     rcx, [rsp+6B0h+TempFileName]; lpFileName
0x18087bd00  call    cs:__imp_DeleteFileW
0x18087bd07  nop     dword ptr [rax+rax+00h]
0x18087bd0c  mov     eax, r14d
0x18087bd0f  mov     rcx, [rbp+5B0h+var_30]
0x18087bd16  xor     rcx, rsp; StackCookie
0x18087bd19  call    __security_check_cookie
0x18087bd1e  mov     rbx, [rsp+6B0h+arg_18]
0x18087bd26  add     rsp, 690h
0x18087bd2d  pop     r15
0x18087bd2f  pop     r14
0x18087bd31  pop     rdi
0x18087bd32  pop     rsi
0x18087bd33  pop     rbp
0x18087bd34  retn
```
