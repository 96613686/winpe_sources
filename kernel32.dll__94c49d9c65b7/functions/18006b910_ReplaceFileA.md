# ReplaceFileA

- ea: `0x18006b910`
- end: `0x18006ba12`
- name: `ReplaceFileA`
- size: `258`
- prototype: `BOOL __stdcall(LPCSTR lpReplacedFileName, LPCSTR lpReplacementFileName, LPCSTR lpBackupFileName, DWORD dwReplaceFlags, LPVOID lpExclude, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000d6c0`
- `0x18006b910`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006b9dc`
- `ntdll!RtlFreeUnicodeString` at `0x18006b9e6`
- `ntdll!RtlFreeUnicodeString` at `0x18006b9f0`
- `ntdll!RtlFreeUnicodeString` at `0x18006b9dc`
- `ntdll!RtlFreeUnicodeString` at `0x18006b9e6`
- `ntdll!RtlFreeUnicodeString` at `0x18006b9f0`
- `ntdll!RtlSetLastWin32Error` at `0x18006b9ff`
- `ntdll!RtlSetLastWin32Error` at `0x18006b9ff`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x18006b9cb`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x18006b9cb`

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
0x18006b910  push    rbp
0x18006b912  push    rbx
0x18006b913  push    rsi
0x18006b914  push    rdi
0x18006b915  push    r14
0x18006b917  mov     rbp, rsp
0x18006b91a  sub     rsp, 60h
0x18006b91e  xorps   xmm0, xmm0
0x18006b921  xorps   xmm1, xmm1
0x18006b924  mov     r14d, r9d
0x18006b927  mov     rdi, r8
0x18006b92a  mov     rsi, rdx
0x18006b92d  movups  xmmword ptr [rbp+lpReplacedFileName], xmm0
0x18006b931  movups  xmmword ptr [rbp+lpReplacementFileName], xmm1
0x18006b935  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18006b939  test    rcx, rcx
0x18006b93c  jz      loc_18006B9FA
0x18006b942  test    rdx, rdx
0x18006b945  jz      loc_18006B9FA
0x18006b94b  cmp     [rbp+lpExclude], 0
0x18006b950  jnz     loc_18006B9FA
0x18006b956  cmp     [rbp+lpReserved], 0
0x18006b95b  jnz     loc_18006B9FA
0x18006b961  test    r9d, 0FFFFFFF8h
0x18006b968  jnz     loc_18006B9FA
0x18006b96e  mov     rdx, rcx
0x18006b971  lea     rcx, [rbp+lpReplacedFileName]
0x18006b975  call    Basep8BitStringToDynamicUnicodeString
0x18006b97a  test    eax, eax
0x18006b97c  jz      loc_18006BA05
0x18006b982  mov     rdx, rsi
0x18006b985  lea     rcx, [rbp+lpReplacementFileName]
0x18006b989  xor     ebx, ebx
0x18006b98b  call    Basep8BitStringToDynamicUnicodeString
0x18006b990  test    eax, eax
0x18006b992  jz      short loc_18006B9EC
0x18006b994  test    rdi, rdi
0x18006b997  jz      short loc_18006B9AF
0x18006b999  mov     rdx, rdi
0x18006b99c  lea     rcx, [rbp+UnicodeString]
0x18006b9a0  call    Basep8BitStringToDynamicUnicodeString
0x18006b9a5  test    eax, eax
0x18006b9a7  jz      short loc_18006B9E2
0x18006b9a9  mov     r8, [rbp+UnicodeString.Buffer]
0x18006b9ad  jmp     short loc_18006B9B6
0x18006b9af  xor     r8d, r8d; lpBackupFileName
0x18006b9b2  mov     [rbp+UnicodeString.Buffer], r8
0x18006b9b6  mov     rdx, [rbp+lpReplacementFileName+8]; lpReplacementFileName
0x18006b9ba  mov     r9d, r14d; dwReplaceFlags
0x18006b9bd  mov     rcx, [rbp+lpReplacedFileName+8]; lpReplacedFileName
0x18006b9c1  mov     [rsp+60h+var_38], rbx; lpReserved
0x18006b9c6  mov     [rsp+60h+var_40], rbx; lpExclude
0x18006b9cb  call    cs:__imp_ReplaceFileW
0x18006b9d1  mov     ebx, eax
0x18006b9d3  test    rdi, rdi
0x18006b9d6  jz      short loc_18006B9E2
0x18006b9d8  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18006b9dc  call    cs:__imp_RtlFreeUnicodeString
0x18006b9e2  lea     rcx, [rbp+lpReplacementFileName]; UnicodeString
0x18006b9e6  call    cs:__imp_RtlFreeUnicodeString
0x18006b9ec  lea     rcx, [rbp+lpReplacedFileName]; UnicodeString
0x18006b9f0  call    cs:__imp_RtlFreeUnicodeString
0x18006b9f6  mov     eax, ebx
0x18006b9f8  jmp     short loc_18006BA07
0x18006b9fa  mov     ecx, 57h ; 'W'; LastError
0x18006b9ff  call    cs:__imp_RtlSetLastWin32Error
0x18006ba05  xor     eax, eax
0x18006ba07  add     rsp, 60h
0x18006ba0b  pop     r14
0x18006ba0d  pop     rdi
0x18006ba0e  pop     rsi
0x18006ba0f  pop     rbx
0x18006ba10  pop     rbp
0x18006ba11  retn
```
