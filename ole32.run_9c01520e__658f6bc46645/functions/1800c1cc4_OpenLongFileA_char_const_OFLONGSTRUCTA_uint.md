# OpenLongFileA(char const *,_OFLONGSTRUCTA *,uint)

- ea: `0x1800c1cc4`
- end: `0x1800c1f73`
- name: `?OpenLongFileA@@YAHPEBDPEAU_OFLONGSTRUCTA@@I@Z`
- size: `687`
- prototype: `int __fastcall(const char *lpFileName, _OFLONGSTRUCTA *lpReOpenBuff, unsigned int uStyle)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800c1ae0`

## callees

- `0x1800c1cc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c1ce3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c1d1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c1f39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c1ce3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c1d1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c1f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1f45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1f45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c1e75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c1e75`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800c1d07`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800c1e0b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800c1d07`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800c1e0b`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c1e55`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c1f06`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c1e55`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800c1f06`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x1800c1dcf`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x1800c1dcf`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1800c1f2b`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1800c1f2b`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x1800c1ed4`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x1800c1ed4`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800c1e8c`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800c1e8c`

## pseudocode

```c
__int64 __fastcall OpenLongFileA(const char *lpFileName, _OFLONGSTRUCTA *lpReOpenBuff, unsigned int uStyle)
{
  DWORD v6; // ecx
  unsigned int v7; // edi
  DWORD v8; // r15d
  unsigned int v9; // eax
  DWORD v10; // r14d
  DWORD v11; // ecx
  DWORD v12; // ebp
  HANDLE FileA; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // esi
  unsigned int v16; // ecx
  __int64 result; // rax
  int dwCreationDisposition; // [rsp+88h] [rbp+10h]
  int isWow64Process; // [rsp+90h] [rbp+18h] BYREF
  void *pFsRedirection; // [rsp+98h] [rbp+20h] BYREF

  SetLastError(0);
  if ( (uStyle & 0x100) != 0 )
  {
    if ( GetFullPathNameA(lpFileName, 0x103u, lpReOpenBuff->szPathName, 0) <= 0x103 )
    {
      lpReOpenBuff->nErrCode = 0;
      v7 = 0;
      goto $finally_exit;
    }
    goto LABEL_3;
  }
  v7 = 1;
  v8 = (((uStyle & 1) == 0) + 1) << 30;
  if ( (uStyle & 2) != 0 )
    v8 = -1073741824;
  v9 = uStyle & 0x70;
  if ( (uStyle & 0x70) != 0 )
  {
    switch ( v9 )
    {
      case 0x10u:
        v10 = 0;
        goto LABEL_16;
      case 0x20u:
        v10 = 5;
        goto LABEL_16;
      case 0x30u:
        v10 = 6;
        goto LABEL_16;
    }
  }
  v10 = 7;
LABEL_16:
  if ( (uStyle & 0x1000) != 0 )
    v8 = -1073741824;
  dwCreationDisposition = 3 - ((uStyle & 0x1000) != 0);
  if ( (uStyle & 0x8000) == 0 )
  {
    v11 = SearchPathA(0, lpFileName, 0, 0x103u, lpReOpenBuff->szPathName, 0);
    if ( v11 > 0x103 )
      goto LABEL_3;
    if ( v11 )
    {
      if ( (uStyle & 0x4000) != 0 )
        goto $finally_exit;
    }
    else
    {
      if ( (uStyle & 0x4000) != 0 )
      {
        v6 = 2;
        goto LABEL_4;
      }
      if ( GetFullPathNameA(lpFileName, 0x103u, lpReOpenBuff->szPathName, 0) - 1 > 0x102 )
      {
LABEL_3:
        v6 = 13;
LABEL_4:
        SetLastError(v6);
        v7 = -1;
        goto $finally_exit;
      }
    }
  }
  v12 = uStyle & 0xFFFF0000;
  FileA = CreateFileA(lpReOpenBuff->szPathName, v8, v10, 0, dwCreationDisposition, v12, 0);
  v7 = (unsigned int)FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    isWow64Process = 0;
    CurrentProcess = GetCurrentProcess();
    if ( IsWow64Process(CurrentProcess, &isWow64Process) )
    {
      LastError = GetLastError();
      if ( LastError == 2 )
      {
        if ( isWow64Process )
        {
          pFsRedirection = 0;
          if ( Wow64DisableWow64FsRedirection(&pFsRedirection) )
          {
            v7 = (unsigned int)CreateFileA(lpReOpenBuff->szPathName, v8, v10, 0, dwCreationDisposition, v12, 0);
            LastError = GetLastError();
            Wow64RevertWow64FsRedirection(pFsRedirection);
          }
          SetLastError(LastError);
        }
      }
    }
  }
$finally_exit:
  v16 = (unsigned __int16)GetLastError();
  result = v7;
  lpReOpenBuff->nErrCode = v16;
  return result;
}

```

## disassembly

```asm
0x1800c1cc4  mov     [rsp+arg_0], rbx
0x1800c1cc9  push    rbp
0x1800c1cca  push    rsi
0x1800c1ccb  push    rdi
0x1800c1ccc  push    r12
0x1800c1cce  push    r13
0x1800c1cd0  push    r14
0x1800c1cd2  push    r15
0x1800c1cd4  sub     rsp, 40h
0x1800c1cd8  mov     r13, lpFileName
0x1800c1cdb  mov     ebp, uStyle
0x1800c1cde  xor     ecx, ecx; dwErrCode
0x1800c1ce0  mov     r12, lpReOpenBuff
0x1800c1ce3  call    cs:__imp_SetLastError
0x1800c1cea  nop     dword ptr [rax+rax+00h]
0x1800c1cef  bt      ebp, 8
0x1800c1cf3  jnb     short loc_1800C1D3E
0x1800c1cf5  mov     esi, 103h
0x1800c1cfa  lea     r8, [r12+4]; lpBuffer
0x1800c1cff  mov     edx, esi; nBufferLength
0x1800c1d01  xor     r9d, r9d; lpFilePart
0x1800c1d04  mov     lpFileName, r13; lpFileName
0x1800c1d07  call    cs:__imp_GetFullPathNameA
0x1800c1d0e  nop     dword ptr [rax+rax+00h]
0x1800c1d13  cmp     eax, esi
0x1800c1d15  jbe     short loc_1800C1D31
0x1800c1d17  mov     ecx, 0Dh; dwErrCode
0x1800c1d1c  call    cs:__imp_SetLastError
0x1800c1d23  nop     dword ptr [rax+rax+00h]
0x1800c1d28  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c1d2c  jmp     $finally_exit
0x1800c1d31  xor     ebx, ebx
0x1800c1d33  mov     [r12], ebx
0x1800c1d37  mov     edi, ebx
0x1800c1d39  jmp     $finally_exit
0x1800c1d3e  mov     edi, 1
0x1800c1d43  mov     r15d, ebp
0x1800c1d46  not     r15d
0x1800c1d49  mov     ecx, 0C0000000h
0x1800c1d4e  and     r15d, edi
0x1800c1d51  mov     eax, ebp
0x1800c1d53  add     r15d, edi
0x1800c1d56  shl     r15d, 1Eh
0x1800c1d5a  test    bpl, 2
0x1800c1d5e  cmovnz  r15d, ecx
0x1800c1d62  xor     ebx, ebx
0x1800c1d64  and     eax, 70h
0x1800c1d67  jz      short loc_1800C1D8B
0x1800c1d69  cmp     eax, 10h
0x1800c1d6c  jz      short loc_1800C1D86
0x1800c1d6e  cmp     eax, 20h ; ' '
0x1800c1d71  jz      short loc_1800C1D7E
0x1800c1d73  cmp     eax, 30h ; '0'
0x1800c1d76  jnz     short loc_1800C1D8B
0x1800c1d78  lea     r14d, [rdi+5]
0x1800c1d7c  jmp     short loc_1800C1D91
0x1800c1d7e  mov     r14d, 5
0x1800c1d84  jmp     short loc_1800C1D91
0x1800c1d86  mov     r14d, ebx
0x1800c1d89  jmp     short loc_1800C1D91
0x1800c1d8b  mov     r14d, 7
0x1800c1d91  mov     eax, ebp
0x1800c1d93  and     eax, 1000h
0x1800c1d98  cmovnz  r15d, ecx
0x1800c1d9c  neg     eax
0x1800c1d9e  sbb     edx, edx
0x1800c1da0  add     edx, 3
0x1800c1da3  mov     [rsp+78h+dwCreationDisposition], edx
0x1800c1daa  lea     lpReOpenBuff, [r12+4]
0x1800c1daf  bt      ebp, 0Fh
0x1800c1db3  jb      short loc_1800C1E2D
0x1800c1db5  mov     [rsp+78h+lpFilePart], rbx; lpFilePart
0x1800c1dba  mov     esi, 103h
0x1800c1dbf  mov     [rsp+78h+lpBuffer], lpReOpenBuff; lpBuffer
0x1800c1dc4  mov     r9d, esi; nBufferLength
0x1800c1dc7  mov     lpReOpenBuff, r13; lpFileName
0x1800c1dca  xor     uStyle, uStyle; lpExtension
0x1800c1dcd  xor     ecx, ecx; lpPath
0x1800c1dcf  call    cs:__imp_SearchPathA
0x1800c1dd6  nop     dword ptr [rax+rax+00h]
0x1800c1ddb  mov     ecx, eax
0x1800c1ddd  cmp     eax, esi
0x1800c1ddf  ja      loc_1800C1D17
0x1800c1de5  mov     eax, ebp
0x1800c1de7  and     eax, 4000h
0x1800c1dec  test    ecx, ecx
0x1800c1dee  jnz     short loc_1800C1E25
0x1800c1df0  test    eax, eax
0x1800c1df2  jz      short loc_1800C1DFE
0x1800c1df4  mov     ecx, 2
0x1800c1df9  jmp     loc_1800C1D1C
0x1800c1dfe  xor     r9d, r9d; lpFilePart
0x1800c1e01  lea     r8, [r12+4]; lpBuffer
0x1800c1e06  mov     edx, esi; nBufferLength
0x1800c1e08  mov     lpFileName, r13; lpFileName
0x1800c1e0b  call    cs:__imp_GetFullPathNameA
0x1800c1e12  nop     dword ptr [rax+rax+00h]
0x1800c1e17  dec     eax
0x1800c1e19  cmp     eax, 102h
0x1800c1e1e  jbe     short loc_1800C1E2D
0x1800c1e20  jmp     loc_1800C1D17
0x1800c1e25  test    eax, eax
0x1800c1e27  jnz     $finally_exit
0x1800c1e2d  mov     eax, [rsp+78h+dwCreationDisposition]
0x1800c1e34  lea     lpFileName, [r12+4]; lpFileName
0x1800c1e39  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x1800c1e3e  and     ebp, 0FFFF0000h
0x1800c1e44  mov     dword ptr [rsp+78h+lpFilePart], ebp; dwFlagsAndAttributes
0x1800c1e48  xor     r9d, r9d; lpSecurityAttributes
0x1800c1e4b  mov     uStyle, r14d; dwShareMode
0x1800c1e4e  mov     dword ptr [rsp+78h+lpBuffer], eax; dwCreationDisposition
0x1800c1e52  mov     edx, r15d; dwDesiredAccess
0x1800c1e55  call    cs:__imp_CreateFileA
0x1800c1e5c  nop     dword ptr [rax+rax+00h]
0x1800c1e61  mov     rdi, rax
0x1800c1e64  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c1e68  jnz     $finally_exit
0x1800c1e6e  mov     [rsp+78h+isWow64Process], ebx
0x1800c1e75  call    cs:__imp_GetCurrentProcess
0x1800c1e7c  nop     dword ptr [rax+rax+00h]
0x1800c1e81  mov     lpFileName, rax; hProcess
0x1800c1e84  lea     lpReOpenBuff, [rsp+78h+isWow64Process]; Wow64Process
0x1800c1e8c  call    cs:__imp_IsWow64Process
0x1800c1e93  nop     dword ptr [rax+rax+00h]
0x1800c1e98  test    eax, eax
0x1800c1e9a  jz      $finally_exit
0x1800c1ea0  call    cs:__imp_GetLastError
0x1800c1ea7  nop     dword ptr [rax+rax+00h]
0x1800c1eac  mov     esi, eax
0x1800c1eae  cmp     eax, 2
0x1800c1eb1  jnz     $finally_exit
0x1800c1eb7  cmp     [rsp+78h+isWow64Process], ebx
0x1800c1ebe  jz      $finally_exit
0x1800c1ec4  lea     lpFileName, [rsp+78h+pFsRedirection]; OldValue
0x1800c1ecc  mov     [rsp+78h+pFsRedirection], rbx
0x1800c1ed4  call    cs:__imp_Wow64DisableWow64FsRedirection
0x1800c1edb  nop     dword ptr [rax+rax+00h]
0x1800c1ee0  test    eax, eax
0x1800c1ee2  jz      short loc_1800C1F37
0x1800c1ee4  mov     eax, [rsp+78h+dwCreationDisposition]
0x1800c1eeb  lea     lpFileName, [r12+4]; lpFileName
0x1800c1ef0  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x1800c1ef5  xor     r9d, r9d; lpSecurityAttributes
0x1800c1ef8  mov     dword ptr [rsp+78h+lpFilePart], ebp; dwFlagsAndAttributes
0x1800c1efc  mov     uStyle, r14d; dwShareMode
0x1800c1eff  mov     edx, r15d; dwDesiredAccess
0x1800c1f02  mov     dword ptr [rsp+78h+lpBuffer], eax; dwCreationDisposition
0x1800c1f06  call    cs:__imp_CreateFileA
0x1800c1f0d  nop     dword ptr [rax+rax+00h]
0x1800c1f12  mov     rdi, rax
0x1800c1f15  call    cs:__imp_GetLastError
0x1800c1f1c  nop     dword ptr [rax+rax+00h]
0x1800c1f21  mov     lpFileName, [rsp+78h+pFsRedirection]; OlValue
0x1800c1f29  mov     esi, eax
0x1800c1f2b  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1800c1f32  nop     dword ptr [rax+rax+00h]
0x1800c1f37  mov     ecx, esi; dwErrCode
0x1800c1f39  call    cs:__imp_SetLastError
0x1800c1f40  nop     dword ptr [rax+rax+00h]
0x1800c1f45  call    cs:__imp_GetLastError
0x1800c1f4c  nop     dword ptr [rax+rax+00h]
0x1800c1f51  mov     rbx, [rsp+78h+arg_0]
0x1800c1f59  movzx   ecx, ax
0x1800c1f5c  mov     eax, edi
0x1800c1f5e  mov     [r12], ecx
0x1800c1f62  add     rsp, 40h
0x1800c1f66  pop     r15
0x1800c1f68  pop     r14
0x1800c1f6a  pop     r13
0x1800c1f6c  pop     r12
0x1800c1f6e  pop     rdi
0x1800c1f6f  pop     rsi
0x1800c1f70  pop     rbp
0x1800c1f71  retn
```
