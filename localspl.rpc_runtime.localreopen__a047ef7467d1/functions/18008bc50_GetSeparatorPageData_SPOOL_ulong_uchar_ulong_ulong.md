# GetSeparatorPageData(_SPOOL *,ulong *,uchar *,ulong,ulong *)

- ea: `0x18008bc50`
- end: `0x18008be13`
- name: `?GetSeparatorPageData@@YAKPEAU_SPOOL@@PEAKPEAEK1@Z`
- size: `451`
- prototype: `unsigned int(struct _SPOOL *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x18008964c`

## callees

- `0x180046650`
- `0x18008bc50`
- `0x180096e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bdc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008bddb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008bddb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008bd2c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008bd2c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008bd9e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008bd9e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008bcfa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008bcfa`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008bd5b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008bd5b`
- `SPOOLSS!RevertToPrinterSelf` at `0x18008bcbb`
- `SPOOLSS!RevertToPrinterSelf` at `0x18008bcbb`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18008bd06`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18008bd06`

## pseudocode

```c
__int64 __fastcall GetSeparatorPageData(
        struct _SPOOL *a1,
        unsigned int *a2,
        unsigned __int8 *a3,
        DWORD a4,
        unsigned int *a5)
{
  _WORD *v9; // rcx
  HANDLE v10; // rbx
  HANDLE FileW; // rdi
  DWORD LowPart; // r8d
  DWORD LastError; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-268h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-260h] BYREF
  WCHAR szFilePath[264]; // [rsp+50h] [rbp-258h] BYREF

  if ( a3 && a5 )
  {
    v9 = *(_WORD **)(*((_QWORD *)a1 + 8) + 128LL);
    if ( !v9 )
      return 2;
    if ( !*v9 )
      return 2;
    v10 = RevertToPrinterSelf();
    if ( !v10 )
      return 2;
    FileW = CreateFileW(*(LPCWSTR *)(*((_QWORD *)a1 + 8) + 128LL), 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
    ImpersonatePrinterClient(v10);
    if ( FileW == (HANDLE)-1LL )
      return 2;
    FileSize.QuadPart = 0;
    if ( GetFinalPathNameByHandleW(FileW, szFilePath, 0x105u, 0) - 1 > 0x103
      || !(unsigned int)IsSepFilePathAllowed(szFilePath, 0) )
    {
      LastError = 2;
      goto LABEL_22;
    }
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      LowPart = FileSize.LowPart;
      *a5 = FileSize.LowPart;
      if ( LowPart > a4 )
      {
        LastError = 234;
LABEL_22:
        CloseHandle(FileW);
        return LastError;
      }
      if ( LowPart > 0x10000 || FileSize.HighPart > 0 )
      {
        LastError = 13;
        goto LABEL_22;
      }
      NumberOfBytesRead = 0;
      if ( !ReadFile(FileW, a3, LowPart, &NumberOfBytesRead, 0) || FileSize.LowPart != NumberOfBytesRead )
      {
        LastError = GetLastError();
        goto LABEL_22;
      }
      if ( a2 )
        *a2 = 3;
    }
    LastError = 0;
    goto LABEL_22;
  }
  return 87;
}

```

## disassembly

```asm
0x18008bc50  push    rbx
0x18008bc52  push    rbp
0x18008bc53  push    rsi
0x18008bc54  push    rdi
0x18008bc55  push    r12
0x18008bc57  push    r14
0x18008bc59  push    r15
0x18008bc5b  sub     rsp, 270h
0x18008bc62  mov     rax, cs:__security_cookie
0x18008bc69  xor     rax, rsp
0x18008bc6c  mov     [rsp+2A8h+var_48], rax
0x18008bc74  mov     r14, [rsp+2A8h+arg_20]
0x18008bc7c  xor     r12d, r12d
0x18008bc7f  mov     r15d, r9d
0x18008bc82  mov     rbp, r8
0x18008bc85  mov     rsi, rdx
0x18008bc88  mov     rdi, rcx
0x18008bc8b  test    r8, r8
0x18008bc8e  jz      loc_18008BDEC
0x18008bc94  test    r14, r14
0x18008bc97  jz      loc_18008BDEC
0x18008bc9d  mov     rax, [rcx+40h]
0x18008bca1  mov     rcx, [rax+80h]
0x18008bca8  test    rcx, rcx
0x18008bcab  jz      loc_18008BDE3
0x18008bcb1  cmp     [rcx], r12w
0x18008bcb5  jz      loc_18008BDE3
0x18008bcbb  call    cs:__imp_RevertToPrinterSelf
0x18008bcc1  mov     rbx, rax
0x18008bcc4  test    rax, rax
0x18008bcc7  jz      loc_18008BDE3
0x18008bccd  mov     rcx, [rdi+40h]
0x18008bcd1  lea     r8d, [r12+1]; dwShareMode
0x18008bcd6  mov     [rsp+2A8h+hTemplateFile], r12; hTemplateFile
0x18008bcdb  xor     r9d, r9d; lpSecurityAttributes
0x18008bcde  mov     [rsp+2A8h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18008bce6  mov     edx, 80000000h; dwDesiredAccess
0x18008bceb  mov     [rsp+2A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18008bcf3  mov     rcx, [rcx+80h]; lpFileName
0x18008bcfa  call    cs:__imp_CreateFileW
0x18008bd00  mov     rcx, rbx; hToken
0x18008bd03  mov     rdi, rax
0x18008bd06  call    cs:__imp_ImpersonatePrinterClient
0x18008bd0c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008bd10  jz      loc_18008BDE3
0x18008bd16  xor     r9d, r9d; dwFlags
0x18008bd19  mov     qword ptr [rsp+2A8h+FileSize], r12
0x18008bd1e  mov     r8d, 105h; cchFilePath
0x18008bd24  lea     rdx, [rsp+2A8h+szFilePath]; lpszFilePath
0x18008bd29  mov     rcx, rdi; hFile
0x18008bd2c  call    cs:__imp_GetFinalPathNameByHandleW
0x18008bd32  dec     eax
0x18008bd34  cmp     eax, 103h
0x18008bd39  ja      loc_18008BDD3
0x18008bd3f  xor     edx, edx; wchar_t *
0x18008bd41  lea     rcx, [rsp+2A8h+szFilePath]; String1
0x18008bd46  call    ?IsSepFilePathAllowed@@YAHPEBG0@Z; IsSepFilePathAllowed(ushort const *,ushort const *)
0x18008bd4b  test    eax, eax
0x18008bd4d  jz      loc_18008BDD3
0x18008bd53  lea     rdx, [rsp+2A8h+FileSize]; lpFileSize
0x18008bd58  mov     rcx, rdi; hFile
0x18008bd5b  call    cs:__imp_GetFileSizeEx
0x18008bd61  test    eax, eax
0x18008bd63  jz      short loc_18008BDBD
0x18008bd65  mov     r8d, dword ptr [rsp+2A8h+FileSize]; nNumberOfBytesToRead
0x18008bd6a  mov     [r14], r8d
0x18008bd6d  cmp     r8d, r15d
0x18008bd70  jbe     short loc_18008BD79
0x18008bd72  mov     ebx, 0EAh
0x18008bd77  jmp     short loc_18008BDD8
0x18008bd79  cmp     r8d, 10000h
0x18008bd80  ja      short loc_18008BDCC
0x18008bd82  cmp     dword ptr [rsp+2A8h+FileSize+4], r12d
0x18008bd87  jg      short loc_18008BDCC
0x18008bd89  lea     r9, [rsp+2A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008bd8e  mov     [rsp+2A8h+NumberOfBytesRead], r12d
0x18008bd93  mov     rdx, rbp; lpBuffer
0x18008bd96  mov     qword ptr [rsp+2A8h+dwCreationDisposition], r12; lpOverlapped
0x18008bd9b  mov     rcx, rdi; hFile
0x18008bd9e  call    cs:__imp_ReadFile
0x18008bda4  test    eax, eax
0x18008bda6  jz      short loc_18008BDC2
0x18008bda8  mov     eax, [rsp+2A8h+NumberOfBytesRead]
0x18008bdac  cmp     dword ptr [rsp+2A8h+FileSize], eax
0x18008bdb0  jnz     short loc_18008BDC2
0x18008bdb2  test    rsi, rsi
0x18008bdb5  jz      short loc_18008BDBD
0x18008bdb7  mov     dword ptr [rsi], 3
0x18008bdbd  mov     ebx, r12d
0x18008bdc0  jmp     short loc_18008BDD8
0x18008bdc2  call    cs:__imp_GetLastError
0x18008bdc8  mov     ebx, eax
0x18008bdca  jmp     short loc_18008BDD8
0x18008bdcc  mov     ebx, 0Dh
0x18008bdd1  jmp     short loc_18008BDD8
0x18008bdd3  mov     ebx, 2
0x18008bdd8  mov     rcx, rdi; hObject
0x18008bddb  call    cs:__imp_CloseHandle
0x18008bde1  jmp     short loc_18008BDE8
0x18008bde3  mov     ebx, 2
0x18008bde8  mov     eax, ebx
0x18008bdea  jmp     short loc_18008BDF1
0x18008bdec  mov     eax, 57h ; 'W'
0x18008bdf1  mov     rcx, [rsp+2A8h+var_48]
0x18008bdf9  xor     rcx, rsp; StackCookie
0x18008bdfc  call    __security_check_cookie
0x18008be01  add     rsp, 270h
0x18008be08  pop     r15
0x18008be0a  pop     r14
0x18008be0c  pop     r12
0x18008be0e  pop     rdi
0x18008be0f  pop     rsi
0x18008be10  pop     rbp
0x18008be11  pop     rbx
0x18008be12  retn
```
