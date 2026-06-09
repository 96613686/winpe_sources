# ReplaceFileA

- ea: `0x180072d50`
- end: `0x180072e71`
- name: `ReplaceFileA`
- size: `289`
- prototype: `BOOL __stdcall(LPCSTR lpReplacedFileName, LPCSTR lpReplacementFileName, LPCSTR lpBackupFileName, DWORD dwReplaceFlags, LPVOID lpExclude, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180028f60`
- `0x180072d50`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180072e22`
- `ntdll!RtlFreeUnicodeString` at `0x180072e32`
- `ntdll!RtlFreeUnicodeString` at `0x180072e42`
- `ntdll!RtlFreeUnicodeString` at `0x180072e22`
- `ntdll!RtlFreeUnicodeString` at `0x180072e32`
- `ntdll!RtlFreeUnicodeString` at `0x180072e42`
- `ntdll!RtlSetLastWin32Error` at `0x180072e57`
- `ntdll!RtlSetLastWin32Error` at `0x180072e57`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x180072e0b`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x180072e0b`

## pseudocode

```c
BOOL __stdcall ReplaceFileA(
        LPCSTR lpReplacedFileName,
        LPCSTR lpReplacementFileName,
        LPCSTR lpBackupFileName,
        DWORD dwReplaceFlags,
        LPVOID lpExclude,
        LPVOID lpReserved)
{
  BOOL v9; // ebx
  const WCHAR *Buffer; // r8
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpReplacementFileNamea[2]; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpReplacedFileNamea[2]; // [rsp+50h] [rbp-10h] BYREF

  *(_OWORD *)lpReplacedFileNamea = 0;
  *(_OWORD *)lpReplacementFileNamea = 0;
  UnicodeString = 0;
  if ( !lpReplacedFileName || !lpReplacementFileName || lpExclude || lpReserved || (dwReplaceFlags & 0xFFFFFFF8) != 0 )
  {
    RtlSetLastWin32Error(0x57u);
  }
  else if ( (unsigned int)Basep8BitStringToDynamicUnicodeString(lpReplacedFileNamea, lpReplacedFileName) )
  {
    v9 = 0;
    if ( !(unsigned int)Basep8BitStringToDynamicUnicodeString(lpReplacementFileNamea, lpReplacementFileName) )
    {
LABEL_15:
      RtlFreeUnicodeString((PUNICODE_STRING)lpReplacedFileNamea);
      return v9;
    }
    if ( lpBackupFileName )
    {
      if ( !(unsigned int)Basep8BitStringToDynamicUnicodeString(&UnicodeString, lpBackupFileName) )
      {
LABEL_14:
        RtlFreeUnicodeString((PUNICODE_STRING)lpReplacementFileNamea);
        goto LABEL_15;
      }
      Buffer = UnicodeString.Buffer;
    }
    else
    {
      Buffer = 0;
      UnicodeString.Buffer = 0;
    }
    v9 = ReplaceFileW(lpReplacedFileNamea[1], lpReplacementFileNamea[1], Buffer, dwReplaceFlags, 0, 0);
    if ( lpBackupFileName )
      RtlFreeUnicodeString(&UnicodeString);
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x180072d50  push    rbp
0x180072d52  push    rbx
0x180072d53  push    rsi
0x180072d54  push    rdi
0x180072d55  push    r14
0x180072d57  mov     rbp, rsp
0x180072d5a  sub     rsp, 60h
0x180072d5e  xorps   xmm0, xmm0
0x180072d61  xorps   xmm1, xmm1
0x180072d64  mov     r14d, r9d
0x180072d67  mov     rdi, r8
0x180072d6a  mov     rsi, rdx
0x180072d6d  movups  xmmword ptr [rbp+lpReplacedFileName], xmm0
0x180072d71  movups  xmmword ptr [rbp+lpReplacementFileName], xmm1
0x180072d75  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180072d79  test    rcx, rcx
0x180072d7c  jz      loc_180072E52
0x180072d82  test    rdx, rdx
0x180072d85  jz      loc_180072E52
0x180072d8b  cmp     [rbp+lpExclude], 0
0x180072d90  jnz     loc_180072E52
0x180072d96  cmp     [rbp+lpReserved], 0
0x180072d9b  jnz     loc_180072E52
0x180072da1  test    r9d, 0FFFFFFF8h
0x180072da8  jnz     loc_180072E52
0x180072dae  mov     rdx, rcx
0x180072db1  lea     rcx, [rbp+lpReplacedFileName]
0x180072db5  call    Basep8BitStringToDynamicUnicodeString
0x180072dba  test    eax, eax
0x180072dbc  jz      loc_180072E63
0x180072dc2  mov     rdx, rsi
0x180072dc5  lea     rcx, [rbp+lpReplacementFileName]
0x180072dc9  xor     ebx, ebx
0x180072dcb  call    Basep8BitStringToDynamicUnicodeString
0x180072dd0  test    eax, eax
0x180072dd2  jz      short loc_180072E3E
0x180072dd4  test    rdi, rdi
0x180072dd7  jz      short loc_180072DEF
0x180072dd9  mov     rdx, rdi
0x180072ddc  lea     rcx, [rbp+UnicodeString]
0x180072de0  call    Basep8BitStringToDynamicUnicodeString
0x180072de5  test    eax, eax
0x180072de7  jz      short loc_180072E2E
0x180072de9  mov     r8, [rbp+UnicodeString.Buffer]
0x180072ded  jmp     short loc_180072DF6
0x180072def  xor     r8d, r8d; lpBackupFileName
0x180072df2  mov     [rbp+UnicodeString.Buffer], r8
0x180072df6  mov     rdx, [rbp+lpReplacementFileName+8]; lpReplacementFileName
0x180072dfa  mov     r9d, r14d; dwReplaceFlags
0x180072dfd  mov     rcx, [rbp+lpReplacedFileName+8]; lpReplacedFileName
0x180072e01  mov     [rsp+60h+var_38], rbx; lpReserved
0x180072e06  mov     [rsp+60h+var_40], rbx; lpExclude
0x180072e0b  call    cs:__imp_ReplaceFileW
0x180072e12  nop     dword ptr [rax+rax+00h]
0x180072e17  mov     ebx, eax
0x180072e19  test    rdi, rdi
0x180072e1c  jz      short loc_180072E2E
0x180072e1e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180072e22  call    cs:__imp_RtlFreeUnicodeString
0x180072e29  nop     dword ptr [rax+rax+00h]
0x180072e2e  lea     rcx, [rbp+lpReplacementFileName]; UnicodeString
0x180072e32  call    cs:__imp_RtlFreeUnicodeString
0x180072e39  nop     dword ptr [rax+rax+00h]
0x180072e3e  lea     rcx, [rbp+lpReplacedFileName]; UnicodeString
0x180072e42  call    cs:__imp_RtlFreeUnicodeString
0x180072e49  nop     dword ptr [rax+rax+00h]
0x180072e4e  mov     eax, ebx
0x180072e50  jmp     short loc_180072E65
0x180072e52  mov     ecx, 57h ; 'W'; LastError
0x180072e57  call    cs:__imp_RtlSetLastWin32Error
0x180072e5e  nop     dword ptr [rax+rax+00h]
0x180072e63  xor     eax, eax
0x180072e65  add     rsp, 60h
0x180072e69  pop     r14
0x180072e6b  pop     rdi
0x180072e6c  pop     rsi
0x180072e6d  pop     rbx
0x180072e6e  pop     rbp
0x180072e6f  retn
```
