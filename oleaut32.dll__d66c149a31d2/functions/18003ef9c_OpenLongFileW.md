# OpenLongFileW

- ea: `0x18003ef9c`
- end: `0x18003f106`
- name: `OpenLongFileW`
- size: `362`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18003ee5c`

## callees

- `0x18003ef9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003f05d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003f05d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003efb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003efed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f0e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003efb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003efed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0ed`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18003efde`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18003efde`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f042`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f0c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f042`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f0c9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003f00b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003f00b`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18003f097`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18003f097`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18003f0df`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18003f0df`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003f06b`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18003f06b`

## pseudocode

```c
__int64 __fastcall OpenLongFileW(LPCWSTR lpFileName, __int64 a2, WINBOOL a3)
{
  DWORD v5; // eax
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // edi
  PVOID OldValue; // [rsp+68h] [rbp+10h] BYREF
  WINBOOL Wow64Process; // [rsp+70h] [rbp+18h] BYREF

  Wow64Process = a3;
  SetLastError(0);
  v5 = SearchPathW(0, lpFileName, 0, 0x103u, (LPWSTR)(a2 + 4), 0);
  if ( v5 <= 0x103 && (v5 || GetFullPathNameW(lpFileName, 0x103u, (LPWSTR)(a2 + 4), 0) - 1 <= 0x102) )
  {
    FileW = CreateFileW((LPCWSTR)(a2 + 4), 0x80000000, 7u, 0, 3u, 0, 0);
    v6 = (unsigned int)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      Wow64Process = 0;
      CurrentProcess = GetCurrentProcess();
      if ( IsWow64Process(CurrentProcess, &Wow64Process) )
      {
        LastError = GetLastError();
        if ( LastError == 2 )
        {
          if ( Wow64Process )
          {
            OldValue = 0;
            if ( Wow64DisableWow64FsRedirection(&OldValue) )
            {
              v6 = (unsigned int)CreateFileW((LPCWSTR)(a2 + 4), 0x80000000, 7u, 0, 3u, 0, 0);
              LastError = GetLastError();
              Wow64RevertWow64FsRedirection(OldValue);
            }
            SetLastError(LastError);
          }
        }
      }
    }
  }
  else
  {
    SetLastError(0xDu);
    v6 = -1;
  }
  *(_DWORD *)a2 = GetLastError();
  return v6;
}

```

## disassembly

```asm
0x18003ef9c  mov     [rsp+arg_0], rbx
0x18003efa1  mov     [rsp+Wow64Process], r8d
0x18003efa6  push    rsi
0x18003efa7  push    rdi
0x18003efa8  push    r14
0x18003efaa  sub     rsp, 40h
0x18003efae  mov     rbx, rcx
0x18003efb1  mov     r14, rdx
0x18003efb4  xor     ecx, ecx; dwErrCode
0x18003efb6  call    cs:__imp_SetLastError
0x18003efbc  mov     edi, 103h
0x18003efc1  mov     [rsp+58h+lpFilePart], 0; lpFilePart
0x18003efca  lea     rsi, [r14+4]
0x18003efce  mov     r9d, edi; nBufferLength
0x18003efd1  xor     r8d, r8d; lpExtension
0x18003efd4  mov     [rsp+58h+lpBuffer], rsi; lpBuffer
0x18003efd9  mov     rdx, rbx; lpFileName
0x18003efdc  xor     ecx, ecx; lpPath
0x18003efde  call    cs:__imp_SearchPathW
0x18003efe4  cmp     eax, edi
0x18003efe6  jbe     short loc_18003EFFC
0x18003efe8  mov     ecx, 0Dh; dwErrCode
0x18003efed  call    cs:__imp_SetLastError
0x18003eff3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003eff7  jmp     loc_18003F0ED
0x18003effc  test    eax, eax
0x18003effe  jnz     short loc_18003F01A
0x18003f000  xor     r9d, r9d; lpFilePart
0x18003f003  mov     r8, rsi; lpBuffer
0x18003f006  mov     edx, edi; nBufferLength
0x18003f008  mov     rcx, rbx; lpFileName
0x18003f00b  call    cs:__imp_GetFullPathNameW
0x18003f011  dec     eax
0x18003f013  cmp     eax, 102h
0x18003f018  ja      short loc_18003EFE8
0x18003f01a  xor     r9d, r9d; lpSecurityAttributes
0x18003f01d  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18003f026  mov     dword ptr [rsp+58h+lpFilePart], 0; dwFlagsAndAttributes
0x18003f02e  mov     edx, 80000000h; dwDesiredAccess
0x18003f033  mov     rcx, rsi; lpFileName
0x18003f036  mov     dword ptr [rsp+58h+lpBuffer], 3; dwCreationDisposition
0x18003f03e  lea     r8d, [r9+7]; dwShareMode
0x18003f042  call    cs:__imp_CreateFileW
0x18003f048  mov     rbx, rax
0x18003f04b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f04f  jnz     loc_18003F0ED
0x18003f055  mov     [rsp+58h+Wow64Process], 0
0x18003f05d  call    cs:__imp_GetCurrentProcess
0x18003f063  mov     rcx, rax; hProcess
0x18003f066  lea     rdx, [rsp+58h+Wow64Process]; Wow64Process
0x18003f06b  call    cs:__imp_IsWow64Process
0x18003f071  test    eax, eax
0x18003f073  jz      short loc_18003F0ED
0x18003f075  call    cs:__imp_GetLastError
0x18003f07b  mov     edi, eax
0x18003f07d  cmp     eax, 2
0x18003f080  jnz     short loc_18003F0ED
0x18003f082  cmp     [rsp+58h+Wow64Process], 0
0x18003f087  jz      short loc_18003F0ED
0x18003f089  lea     rcx, [rsp+58h+OldValue]; OldValue
0x18003f08e  mov     [rsp+58h+OldValue], 0
0x18003f097  call    cs:__imp_Wow64DisableWow64FsRedirection
0x18003f09d  test    eax, eax
0x18003f09f  jz      short loc_18003F0E5
0x18003f0a1  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18003f0aa  lea     r8d, [rbx+8]; dwShareMode
0x18003f0ae  mov     dword ptr [rsp+58h+lpFilePart], 0; dwFlagsAndAttributes
0x18003f0b6  xor     r9d, r9d; lpSecurityAttributes
0x18003f0b9  mov     edx, 80000000h; dwDesiredAccess
0x18003f0be  mov     dword ptr [rsp+58h+lpBuffer], 3; dwCreationDisposition
0x18003f0c6  mov     rcx, rsi; lpFileName
0x18003f0c9  call    cs:__imp_CreateFileW
0x18003f0cf  mov     rbx, rax
0x18003f0d2  call    cs:__imp_GetLastError
0x18003f0d8  mov     rcx, [rsp+58h+OldValue]; OlValue
0x18003f0dd  mov     edi, eax
0x18003f0df  call    cs:__imp_Wow64RevertWow64FsRedirection
0x18003f0e5  mov     ecx, edi; dwErrCode
0x18003f0e7  call    cs:__imp_SetLastError
0x18003f0ed  call    cs:__imp_GetLastError
0x18003f0f3  mov     [r14], eax
0x18003f0f6  mov     eax, ebx
0x18003f0f8  mov     rbx, [rsp+58h+arg_0]
0x18003f0fd  add     rsp, 40h
0x18003f101  pop     r14
0x18003f103  pop     rdi
0x18003f104  pop     rsi
0x18003f105  retn
```
