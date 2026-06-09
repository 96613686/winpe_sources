# DsrCmdStringHelper::GetDebugFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800adf04`
- end: `0x1800adffa`
- name: `?GetDebugFilePath@DsrCmdStringHelper@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18009b940`
- `0x1800a523c`

## callees

- `0x1800319ac`
- `0x180044300`
- `0x180044d30`
- `0x18005b3f4`
- `0x1800adf04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adfbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adfbe`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800adf8e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800adf8e`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800adf59`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800adf59`

## pseudocode

```c
__int64 __fastcall DsrCmdStringHelper::GetDebugFilePath(__int64 a1)
{
  UINT v2; // ebx
  unsigned int v3; // ebx
  __int64 v4; // r8
  signed int LastError; // eax
  WCHAR TempFileName[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR PathName[264]; // [rsp+230h] [rbp-228h] BYREF

  v2 = time(0);
  memset_0(PathName, 0, 0x208u);
  if ( (unsigned int)GetTempPath2W(260, PathName) - 1 <= 0x103
    && (memset_0(TempFileName, 0, 0x208u), GetTempFileNameW(PathName, L"DSR", v2, TempFileName)) )
  {
    v3 = 0;
    v4 = -1;
    do
      ++v4;
    while ( TempFileName[v4] );
    std::wstring::_Assign<unsigned short>(a1, TempFileName);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x1800adf04  mov     [rsp+arg_8], rbx
0x1800adf09  mov     [rsp+arg_10], rsi
0x1800adf0e  push    rdi
0x1800adf0f  sub     rsp, 450h
0x1800adf16  mov     rax, cs:__security_cookie
0x1800adf1d  xor     rax, rsp
0x1800adf20  mov     [rsp+458h+var_18], rax
0x1800adf28  mov     rsi, rcx
0x1800adf2b  xor     ecx, ecx; Time
0x1800adf2d  call    time
0x1800adf32  mov     edi, 208h
0x1800adf37  lea     rcx, [rsp+458h+PathName]; void *
0x1800adf3f  mov     r8d, edi; Size
0x1800adf42  xor     edx, edx; Val
0x1800adf44  mov     rbx, rax
0x1800adf47  call    memset_0
0x1800adf4c  lea     rdx, [rsp+458h+PathName]
0x1800adf54  mov     ecx, 104h
0x1800adf59  call    cs:__imp_GetTempPath2W
0x1800adf5f  dec     eax
0x1800adf61  cmp     eax, 103h
0x1800adf66  ja      short loc_1800ADFBE
0x1800adf68  mov     r8d, edi; Size
0x1800adf6b  lea     rcx, [rsp+458h+TempFileName]; void *
0x1800adf70  xor     edx, edx; Val
0x1800adf72  call    memset_0
0x1800adf77  mov     r8d, ebx; uUnique
0x1800adf7a  lea     r9, [rsp+458h+TempFileName]; lpTempFileName
0x1800adf7f  lea     rdx, PrefixString; "DSR"
0x1800adf86  lea     rcx, [rsp+458h+PathName]; lpPathName
0x1800adf8e  call    cs:__imp_GetTempFileNameW
0x1800adf94  xor     edi, edi
0x1800adf96  test    eax, eax
0x1800adf98  jz      short loc_1800ADFBE
0x1800adf9a  mov     ebx, edi
0x1800adf9c  lea     rax, [rsp+458h+TempFileName]
0x1800adfa1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800adfa5  inc     r8
0x1800adfa8  cmp     [rax+r8*2], di
0x1800adfad  jnz     short loc_1800ADFA5
0x1800adfaf  lea     rdx, [rsp+458h+TempFileName]
0x1800adfb4  mov     rcx, rsi
0x1800adfb7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800adfbc  jmp     short loc_1800ADFD3
0x1800adfbe  call    cs:__imp_GetLastError
0x1800adfc4  mov     ebx, eax
0x1800adfc6  test    eax, eax
0x1800adfc8  jle     short loc_1800ADFD3
0x1800adfca  movzx   ebx, ax
0x1800adfcd  or      ebx, 80070000h
0x1800adfd3  mov     eax, ebx
0x1800adfd5  mov     rcx, [rsp+458h+var_18]
0x1800adfdd  xor     rcx, rsp; StackCookie
0x1800adfe0  call    __security_check_cookie
0x1800adfe5  lea     r11, [rsp+458h+var_8]
0x1800adfed  mov     rbx, [r11+18h]
0x1800adff1  mov     rsi, [r11+20h]
0x1800adff5  mov     rsp, r11
0x1800adff8  pop     rdi
0x1800adff9  retn
```
