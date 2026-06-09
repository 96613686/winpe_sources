# GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)

- ea: `0x140029978`
- end: `0x140029e58`
- name: `?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z`
- size: `1248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000fcb4`
- `0x140014574`
- `0x14001c458`
- `0x14001f624`
- `0x140021e00`
- `0x140027098`
- `0x140027ce0`
- `0x14002b4a0`

## callees

- `0x140002463`
- `0x140029978`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `ADVAPI32!GetUserNameW` at `0x140029d6f`
- `ADVAPI32!GetUserNameW` at `0x140029d6f`
- `KERNEL32!GetComputerNameW` at `0x140029cad`
- `KERNEL32!GetComputerNameW` at `0x140029cad`
- `KERNEL32!CreateFileW` at `0x140029a84`
- `KERNEL32!CreateFileW` at `0x140029a84`
- `KERNEL32!GetFileSizeEx` at `0x140029ad7`
- `KERNEL32!GetFileSizeEx` at `0x140029ad7`
- `KERNEL32!HeapFree` at `0x140029e01`
- `KERNEL32!HeapFree` at `0x140029e26`
- `KERNEL32!HeapFree` at `0x140029e01`
- `KERNEL32!HeapFree` at `0x140029e26`
- `KERNEL32!ReadFile` at `0x140029b8a`
- `KERNEL32!ReadFile` at `0x140029b8a`
- `KERNEL32!GetProcessHeap` at `0x140029b52`
- `KERNEL32!GetProcessHeap` at `0x140029bde`
- `KERNEL32!GetProcessHeap` at `0x140029c64`
- `KERNEL32!GetProcessHeap` at `0x140029cfe`
- `KERNEL32!GetProcessHeap` at `0x140029ded`
- `KERNEL32!GetProcessHeap` at `0x140029e12`
- `KERNEL32!GetProcessHeap` at `0x140029b52`
- `KERNEL32!GetProcessHeap` at `0x140029bde`
- `KERNEL32!GetProcessHeap` at `0x140029c64`
- `KERNEL32!GetProcessHeap` at `0x140029cfe`
- `KERNEL32!GetProcessHeap` at `0x140029ded`
- `KERNEL32!GetProcessHeap` at `0x140029e12`
- `KERNEL32!HeapAlloc` at `0x140029b66`
- `KERNEL32!HeapAlloc` at `0x140029bf2`
- `KERNEL32!HeapAlloc` at `0x140029c79`
- `KERNEL32!HeapAlloc` at `0x140029d15`
- `KERNEL32!HeapAlloc` at `0x140029b66`
- `KERNEL32!HeapAlloc` at `0x140029bf2`
- `KERNEL32!HeapAlloc` at `0x140029c79`
- `KERNEL32!HeapAlloc` at `0x140029d15`
- `KERNEL32!CloseHandle` at `0x140029ddc`
- `KERNEL32!CloseHandle` at `0x140029ddc`
- `KERNEL32!GetLastError` at `0x140029aa0`
- `KERNEL32!GetLastError` at `0x140029ab0`
- `KERNEL32!GetLastError` at `0x140029aa0`
- `KERNEL32!GetLastError` at `0x140029ab0`
- `OLEAUT32!__imp_SysAllocString` at `0x140029d8d`
- `OLEAUT32!__imp_SysAllocString` at `0x140029d8d`
- `SHELL32!__imp_SHGetUserPicturePath` at `0x140029a44`
- `SHELL32!__imp_SHGetUserPicturePath` at `0x140029a44`
- `CRYPT32!CryptBinaryToStringW` at `0x140029bbd`
- `CRYPT32!CryptBinaryToStringW` at `0x140029c2b`
- `CRYPT32!CryptBinaryToStringW` at `0x140029bbd`
- `CRYPT32!CryptBinaryToStringW` at `0x140029c2b`
- `SspiCli!GetUserNameExW` at `0x140029d4c`
- `SspiCli!GetUserNameExW` at `0x140029d4c`

## string_xrefs

- `0x1400299ed`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140029af9`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140029cd3`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140029dbc`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall GetUserInfoAsBSTR(int a1, BSTR *a2)
{
  CEventLogger *v4; // rcx
  unsigned int v5; // edi
  WCHAR *v6; // rsi
  HANDLE FileW; // r14
  void *v8; // r15
  int v9; // ebx
  int v10; // ebx
  signed int v11; // eax
  CEventLogger *v12; // rcx
  CEventLogger *v13; // rcx
  signed int LastError; // eax
  CEventLogger *v15; // rcx
  unsigned int v16; // r9d
  DWORD LowPart; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v19; // rbx
  HANDLE v20; // rax
  CEventLogger *v21; // rcx
  unsigned int v22; // r9d
  HANDLE v23; // rax
  WCHAR *v24; // rax
  CEventLogger *v25; // rcx
  CEventLogger *v26; // rcx
  unsigned int v27; // r9d
  HANDLE v28; // rax
  WCHAR *v29; // rax
  CEventLogger *v30; // rcx
  BSTR v31; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchString; // [rsp+44h] [rbp-BCh] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF

  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  memset_0(FileName, 0, 0x20Au);
  pcchString = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    CEventLogger::LogError(
      v4,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0xDEu,
      L"GetUserInfoAsBSTR",
      0x80004003);
    return v5;
  }
  *a2 = 0;
  v5 = 0;
  v6 = 0;
  FileW = 0;
  v8 = 0;
  v9 = a1 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 != 1 )
        goto LABEL_42;
      v11 = SHGetUserPicturePath(0, 0, FileName, 261);
      v5 = v11;
      if ( v11 < 0 )
      {
        CEventLogger::LogError(
          v12,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x115u,
          L"GetUserInfoAsBSTR",
          v11);
        return v5;
      }
      FileW = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0, 0);
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        if ( GetLastError() )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          if ( (v5 & 0x80000000) == 0 )
            goto LABEL_14;
        }
        else
        {
          v5 = -2147467259;
        }
        CEventLogger::LogError(
          v13,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x120u,
          L"GetUserInfoAsBSTR",
          v5);
        goto LABEL_45;
      }
LABEL_14:
      if ( !GetFileSizeEx(FileW, &FileSize) )
      {
        v16 = 289;
LABEL_16:
        CEventLogger::LogError(
          v15,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          v16,
          L"GetUserInfoAsBSTR",
          0);
        v5 = -2147467259;
        goto LABEL_45;
      }
      if ( FileSize.HighPart )
      {
        v5 = -2147024809;
        CEventLogger::LogError(
          v15,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x126u,
          L"GetUserInfoAsBSTR",
          0x80070057);
        goto LABEL_45;
      }
      LowPart = FileSize.LowPart;
      ProcessHeap = GetProcessHeap();
      v8 = HeapAlloc(ProcessHeap, 0, LowPart);
      if ( !ReadFile(FileW, v8, FileSize.LowPart, &NumberOfBytesRead, 0) )
      {
        v16 = 309;
        goto LABEL_16;
      }
      if ( !CryptBinaryToStringW((const BYTE *)v8, NumberOfBytesRead, 1u, 0, &pcchString) || !pcchString )
      {
        v16 = 326;
        goto LABEL_16;
      }
      v19 = 2LL * pcchString;
      v20 = GetProcessHeap();
      v6 = (WCHAR *)HeapAlloc(v20, 0, v19);
      if ( !v6 )
      {
        v22 = 333;
        goto LABEL_44;
      }
      if ( !CryptBinaryToStringW((const BYTE *)v8, NumberOfBytesRead, 1u, v6, &pcchString) || !pcchString )
      {
        v16 = 345;
        goto LABEL_16;
      }
LABEL_42:
      v31 = SysAllocString(v6);
      *a2 = v31;
      if ( v31 )
        goto LABEL_45;
      v22 = 358;
LABEL_44:
      v5 = -2147024882;
      CEventLogger::LogError(
        v21,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        v22,
        L"GetUserInfoAsBSTR",
        0x8007000E);
LABEL_45:
      if ( FileW )
        CloseHandle(FileW);
      if ( !v6 )
        goto LABEL_49;
      goto LABEL_48;
    }
    NumberOfBytesRead = 16;
    v23 = GetProcessHeap();
    v24 = (WCHAR *)HeapAlloc(v23, 0, 0x20u);
    v6 = v24;
    if ( !v24 )
    {
      v5 = -2147024882;
      CEventLogger::LogError(
        v25,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x102u,
        L"GetUserInfoAsBSTR",
        0x8007000E);
      return v5;
    }
    if ( GetComputerNameW(v24, &NumberOfBytesRead) )
      goto LABEL_42;
    v27 = 262;
  }
  else
  {
    NumberOfBytesRead = 257;
    v28 = GetProcessHeap();
    v29 = (WCHAR *)HeapAlloc(v28, 0, 0x202u);
    v6 = v29;
    if ( !v29 )
    {
      v5 = -2147024882;
      CEventLogger::LogError(
        v30,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0xE9u,
        L"GetUserInfoAsBSTR",
        0x8007000E);
      return v5;
    }
    if ( GetUserNameExW(NameDisplay, v29, &NumberOfBytesRead) && NumberOfBytesRead )
      goto LABEL_42;
    NumberOfBytesRead = 257;
    if ( GetUserNameW(v6, &NumberOfBytesRead) )
      goto LABEL_42;
    v27 = 243;
  }
  CEventLogger::LogError(
    v26,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    v27,
    L"GetUserInfoAsBSTR",
    0);
  v5 = -2147467259;
LABEL_48:
  v32 = GetProcessHeap();
  HeapFree(v32, 0, v6);
LABEL_49:
  if ( v8 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x140029978  push    rbp
0x14002997a  push    rbx
0x14002997b  push    rsi
0x14002997c  push    rdi
0x14002997d  push    r12
0x14002997f  push    r13
0x140029981  push    r14
0x140029983  push    r15
0x140029985  lea     rbp, [rsp-178h]
0x14002998d  sub     rsp, 278h
0x140029994  mov     rax, cs:__security_cookie
0x14002999b  xor     rax, rsp
0x14002999e  mov     [rbp+1B0h+var_50], rax
0x1400299a5  mov     r12, rdx
0x1400299a8  mov     ebx, ecx
0x1400299aa  xor     r13d, r13d
0x1400299ad  lea     rcx, [rsp+2B0h+FileName]; void *
0x1400299b2  xor     edx, edx; Val
0x1400299b4  mov     qword ptr [rsp+2B0h+FileSize], r13
0x1400299b9  mov     r8d, 20Ah; Size
0x1400299bf  mov     [rsp+2B0h+NumberOfBytesRead], r13d
0x1400299c4  call    memset_0
0x1400299c9  mov     [rsp+2B0h+pcchString], r13d
0x1400299ce  test    r12, r12
0x1400299d1  jnz     short loc_140029A0A
0x1400299d3  mov     edi, 80004003h
0x1400299d8  mov     [rsp+2B0h+dwFlagsAndAttributes], 80004003h; unsigned int
0x1400299e0  mov     r9d, 0DEh; unsigned int
0x1400299e6  lea     rax, aGetuserinfoasb; "GetUserInfoAsBSTR"
0x1400299ed  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400299f4  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; unsigned __int16 *
0x1400299f9  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140029a00  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140029a05  jmp     loc_140029E32
0x140029a0a  mov     [r12], r13
0x140029a0e  mov     edi, r13d
0x140029a11  mov     rsi, r13
0x140029a14  mov     r14, r13
0x140029a17  mov     r15, r13
0x140029a1a  sub     ebx, 1
0x140029a1d  jz      loc_140029CF5
0x140029a23  sub     ebx, 1
0x140029a26  jz      loc_140029C5C
0x140029a2c  cmp     ebx, 1
0x140029a2f  jnz     loc_140029D8A
0x140029a35  mov     r9d, 105h
0x140029a3b  lea     r8, [rsp+2B0h+FileName]
0x140029a40  xor     edx, edx
0x140029a42  xor     ecx, ecx
0x140029a44  call    cs:__imp_SHGetUserPicturePath
0x140029a4b  nop     dword ptr [rax+rax+00h]
0x140029a50  mov     edi, eax
0x140029a52  test    eax, eax
0x140029a54  jns     short loc_140029A62
0x140029a56  mov     [rsp+2B0h+dwFlagsAndAttributes], eax
0x140029a5a  mov     r9d, 115h
0x140029a60  jmp     short loc_1400299E6
0x140029a62  mov     [rsp+2B0h+hTemplateFile], r13; hTemplateFile
0x140029a67  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x140029a6c  mov     [rsp+2B0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x140029a71  xor     r9d, r9d; lpSecurityAttributes
0x140029a74  xor     r8d, r8d; dwShareMode
0x140029a77  mov     [rsp+2B0h+dwCreationDisposition], 3; dwCreationDisposition
0x140029a7f  mov     edx, 80000000h; dwDesiredAccess
0x140029a84  call    cs:__imp_CreateFileW
0x140029a8b  nop     dword ptr [rax+rax+00h]
0x140029a90  mov     r14, rax
0x140029a93  lea     rcx, [rax+1]
0x140029a97  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140029a9e  jnz     short loc_140029ACF
0x140029aa0  call    cs:__imp_GetLastError
0x140029aa7  nop     dword ptr [rax+rax+00h]
0x140029aac  test    eax, eax
0x140029aae  jz      short loc_140029B1B
0x140029ab0  call    cs:__imp_GetLastError
0x140029ab7  nop     dword ptr [rax+rax+00h]
0x140029abc  mov     edi, eax
0x140029abe  test    eax, eax
0x140029ac0  jle     short loc_140029ACB
0x140029ac2  movzx   edi, ax
0x140029ac5  or      edi, 80070000h
0x140029acb  test    edi, edi
0x140029acd  js      short loc_140029B20
0x140029acf  lea     rdx, [rsp+2B0h+FileSize]; lpFileSize
0x140029ad4  mov     rcx, r14; hFile
0x140029ad7  call    cs:__imp_GetFileSizeEx
0x140029ade  nop     dword ptr [rax+rax+00h]
0x140029ae3  test    eax, eax
0x140029ae5  jnz     short loc_140029B2F
0x140029ae7  mov     r9d, 121h; unsigned int
0x140029aed  lea     rax, aGetuserinfoasb; "GetUserInfoAsBSTR"
0x140029af4  mov     [rsp+2B0h+dwFlagsAndAttributes], r13d; unsigned int
0x140029af9  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140029b00  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; unsigned __int16 *
0x140029b05  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140029b0c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140029b11  mov     edi, 80004005h
0x140029b16  jmp     loc_140029DD4
0x140029b1b  mov     edi, 80004005h
0x140029b20  mov     [rsp+2B0h+dwFlagsAndAttributes], edi
0x140029b24  mov     r9d, 120h
0x140029b2a  jmp     loc_140029DB5
0x140029b2f  cmp     dword ptr [rsp+2B0h+FileSize+4], r13d
0x140029b34  jz      short loc_140029B4E
0x140029b36  mov     edi, 80070057h
0x140029b3b  mov     [rsp+2B0h+dwFlagsAndAttributes], 80070057h
0x140029b43  mov     r9d, 126h
0x140029b49  jmp     loc_140029DB5
0x140029b4e  mov     ebx, dword ptr [rsp+2B0h+FileSize]
0x140029b52  call    cs:__imp_GetProcessHeap
0x140029b59  nop     dword ptr [rax+rax+00h]
0x140029b5e  mov     r8d, ebx; dwBytes
0x140029b61  xor     edx, edx; dwFlags
0x140029b63  mov     rcx, rax; hHeap
0x140029b66  call    cs:__imp_HeapAlloc
0x140029b6d  nop     dword ptr [rax+rax+00h]
0x140029b72  mov     r8d, dword ptr [rsp+2B0h+FileSize]; nNumberOfBytesToRead
0x140029b77  lea     r9, [rsp+2B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140029b7c  mov     rdx, rax; lpBuffer
0x140029b7f  mov     qword ptr [rsp+2B0h+dwCreationDisposition], r13; lpOverlapped
0x140029b84  mov     rcx, r14; hFile
0x140029b87  mov     r15, rax
0x140029b8a  call    cs:__imp_ReadFile
0x140029b91  nop     dword ptr [rax+rax+00h]
0x140029b96  test    eax, eax
0x140029b98  jnz     short loc_140029BA5
0x140029b9a  mov     r9d, 135h
0x140029ba0  jmp     loc_140029AED
0x140029ba5  mov     edx, [rsp+2B0h+NumberOfBytesRead]; cbBinary
0x140029ba9  lea     rax, [rsp+2B0h+pcchString]
0x140029bae  xor     r9d, r9d; pszString
0x140029bb1  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; pcchString
0x140029bb6  mov     rcx, r15; pbBinary
0x140029bb9  lea     r8d, [r9+1]; dwFlags
0x140029bbd  call    cs:__imp_CryptBinaryToStringW
0x140029bc4  nop     dword ptr [rax+rax+00h]
0x140029bc9  test    eax, eax
0x140029bcb  jz      loc_140029C51
0x140029bd1  mov     eax, [rsp+2B0h+pcchString]
0x140029bd5  test    eax, eax
0x140029bd7  jz      short loc_140029C51
0x140029bd9  mov     ebx, eax
0x140029bdb  add     rbx, rbx
0x140029bde  call    cs:__imp_GetProcessHeap
0x140029be5  nop     dword ptr [rax+rax+00h]
0x140029bea  mov     r8, rbx; dwBytes
0x140029bed  xor     edx, edx; dwFlags
0x140029bef  mov     rcx, rax; hHeap
0x140029bf2  call    cs:__imp_HeapAlloc
0x140029bf9  nop     dword ptr [rax+rax+00h]
0x140029bfe  mov     rsi, rax
0x140029c01  test    rax, rax
0x140029c04  jnz     short loc_140029C11
0x140029c06  mov     r9d, 14Dh
0x140029c0c  jmp     loc_140029DA8
0x140029c11  mov     edx, [rsp+2B0h+NumberOfBytesRead]; cbBinary
0x140029c15  lea     rax, [rsp+2B0h+pcchString]
0x140029c1a  mov     r9, rsi; pszString
0x140029c1d  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; pcchString
0x140029c22  mov     r8d, 1; dwFlags
0x140029c28  mov     rcx, r15; pbBinary
0x140029c2b  call    cs:__imp_CryptBinaryToStringW
0x140029c32  nop     dword ptr [rax+rax+00h]
0x140029c37  test    eax, eax
0x140029c39  jz      short loc_140029C46
0x140029c3b  cmp     [rsp+2B0h+pcchString], r13d
0x140029c40  jnz     loc_140029D8A
0x140029c46  mov     r9d, 159h
0x140029c4c  jmp     loc_140029AED
0x140029c51  mov     r9d, 146h
0x140029c57  jmp     loc_140029AED
0x140029c5c  mov     [rsp+2B0h+NumberOfBytesRead], 10h
0x140029c64  call    cs:__imp_GetProcessHeap
0x140029c6b  nop     dword ptr [rax+rax+00h]
0x140029c70  xor     edx, edx; dwFlags
0x140029c72  mov     rcx, rax; hHeap
0x140029c75  lea     r8d, [rdx+20h]; dwBytes
0x140029c79  call    cs:__imp_HeapAlloc
0x140029c80  nop     dword ptr [rax+rax+00h]
0x140029c85  mov     rsi, rax
0x140029c88  test    rax, rax
0x140029c8b  jnz     short loc_140029CA5
0x140029c8d  mov     edi, 8007000Eh
0x140029c92  mov     [rsp+2B0h+dwFlagsAndAttributes], 8007000Eh
0x140029c9a  mov     r9d, 102h
0x140029ca0  jmp     loc_1400299E6
0x140029ca5  lea     rdx, [rsp+2B0h+NumberOfBytesRead]; nSize
0x140029caa  mov     rcx, rax; lpBuffer
0x140029cad  call    cs:__imp_GetComputerNameW
0x140029cb4  nop     dword ptr [rax+rax+00h]
0x140029cb9  test    eax, eax
0x140029cbb  jnz     loc_140029D8A
0x140029cc1  mov     r9d, 106h; unsigned int
0x140029cc7  lea     rax, aGetuserinfoasb; "GetUserInfoAsBSTR"
0x140029cce  mov     [rsp+2B0h+dwFlagsAndAttributes], r13d; unsigned int
0x140029cd3  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140029cda  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; unsigned __int16 *
0x140029cdf  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140029ce6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140029ceb  mov     edi, 80004005h
0x140029cf0  jmp     loc_140029DED
0x140029cf5  mov     ebx, 101h
0x140029cfa  mov     [rsp+2B0h+NumberOfBytesRead], ebx
0x140029cfe  call    cs:__imp_GetProcessHeap
0x140029d05  nop     dword ptr [rax+rax+00h]
0x140029d0a  xor     edx, edx; dwFlags
0x140029d0c  mov     r8d, 202h; dwBytes
0x140029d12  mov     rcx, rax; hHeap
0x140029d15  call    cs:__imp_HeapAlloc
0x140029d1c  nop     dword ptr [rax+rax+00h]
0x140029d21  mov     rsi, rax
0x140029d24  test    rax, rax
0x140029d27  jnz     short loc_140029D3F
0x140029d29  mov     edi, 8007000Eh
0x140029d2e  mov     [rsp+2B0h+dwFlagsAndAttributes], 8007000Eh
0x140029d36  lea     r9d, [rbx-18h]
0x140029d3a  jmp     loc_1400299E6
0x140029d3f  lea     r8, [rsp+2B0h+NumberOfBytesRead]; nSize
0x140029d44  mov     rdx, rsi; lpNameBuffer
0x140029d47  mov     ecx, 3; NameFormat
0x140029d4c  call    cs:__imp_GetUserNameExW
0x140029d53  nop     dword ptr [rax+rax+00h]
0x140029d58  test    al, al
0x140029d5a  jz      short loc_140029D63
0x140029d5c  cmp     [rsp+2B0h+NumberOfBytesRead], r13d
0x140029d61  jnz     short loc_140029D8A
0x140029d63  lea     rdx, [rsp+2B0h+NumberOfBytesRead]; pcbBuffer
0x140029d68  mov     [rsp+2B0h+NumberOfBytesRead], ebx
0x140029d6c  mov     rcx, rsi; lpBuffer
0x140029d6f  call    cs:__imp_GetUserNameW
0x140029d76  nop     dword ptr [rax+rax+00h]
0x140029d7b  test    eax, eax
0x140029d7d  jnz     short loc_140029D8A
0x140029d7f  mov     r9d, 0F3h
0x140029d85  jmp     loc_140029CC7
0x140029d8a  mov     rcx, rsi; psz
0x140029d8d  call    cs:__imp_SysAllocString
0x140029d94  nop     dword ptr [rax+rax+00h]
0x140029d99  mov     [r12], rax
0x140029d9d  test    rax, rax
0x140029da0  jnz     short loc_140029DD4
0x140029da2  mov     r9d, 166h; unsigned int
0x140029da8  mov     [rsp+2B0h+dwFlagsAndAttributes], 8007000Eh; unsigned int
0x140029db0  mov     edi, 8007000Eh
0x140029db5  lea     rax, aGetuserinfoasb; "GetUserInfoAsBSTR"
0x140029dbc  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140029dc3  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; unsigned __int16 *
0x140029dc8  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140029dcf  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140029dd4  test    r14, r14
0x140029dd7  jz      short loc_140029DE8
0x140029dd9  mov     rcx, r14; hObject
0x140029ddc  call    cs:__imp_CloseHandle
0x140029de3  nop     dword ptr [rax+rax+00h]
0x140029de8  test    rsi, rsi
0x140029deb  jz      short loc_140029E0D
0x140029ded  call    cs:__imp_GetProcessHeap
0x140029df4  nop     dword ptr [rax+rax+00h]
0x140029df9  mov     r8, rsi; lpMem
0x140029dfc  xor     edx, edx; dwFlags
0x140029dfe  mov     rcx, rax; hHeap
0x140029e01  call    cs:__imp_HeapFree
0x140029e08  nop     dword ptr [rax+rax+00h]
0x140029e0d  test    r15, r15
0x140029e10  jz      short loc_140029E32
0x140029e12  call    cs:__imp_GetProcessHeap
0x140029e19  nop     dword ptr [rax+rax+00h]
0x140029e1e  mov     r8, r15; lpMem
0x140029e21  xor     edx, edx; dwFlags
0x140029e23  mov     rcx, rax; hHeap
0x140029e26  call    cs:__imp_HeapFree
0x140029e2d  nop     dword ptr [rax+rax+00h]
0x140029e32  mov     eax, edi
0x140029e34  mov     rcx, [rbp+1B0h+var_50]
0x140029e3b  xor     rcx, rsp; StackCookie
0x140029e3e  call    __security_check_cookie
0x140029e43  add     rsp, 278h
0x140029e4a  pop     r15
0x140029e4c  pop     r14
0x140029e4e  pop     r13
0x140029e50  pop     r12
0x140029e52  pop     rdi
0x140029e53  pop     rsi
0x140029e54  pop     rbx
0x140029e55  pop     rbp
0x140029e56  retn
```
