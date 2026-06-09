# UndetectedInstallerIsImageInProgramFiles(int *,ushort *)

- ea: `0x1800b679c`
- end: `0x1800b6932`
- name: `?UndetectedInstallerIsImageInProgramFiles@@YAKPEAHPEAG@Z`
- size: `406`
- prototype: `unsigned int(int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800b6cfc`

## callees

- `0x180012920`
- `0x1800b679c`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcslwr` at `0x1800b6834`
- `msvcrt!_wcslwr` at `0x1800b683d`
- `msvcrt!_wcslwr` at `0x1800b68e2`
- `msvcrt!_wcslwr` at `0x1800b68eb`
- `msvcrt!_wcslwr` at `0x1800b6834`
- `msvcrt!_wcslwr` at `0x1800b683d`
- `msvcrt!_wcslwr` at `0x1800b68e2`
- `msvcrt!_wcslwr` at `0x1800b68eb`
- `msvcrt!wcsstr` at `0x1800b6849`
- `msvcrt!wcsstr` at `0x1800b68f7`
- `msvcrt!wcsstr` at `0x1800b6849`
- `msvcrt!wcsstr` at `0x1800b68f7`
- `msvcrt!_wcsicmp` at `0x1800b6893`
- `msvcrt!_wcsicmp` at `0x1800b6893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b67f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b68c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b67f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b68c0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b67ea`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6868`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b68b6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b67ea`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6868`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b68b6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800b6828`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800b68d6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800b6828`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800b68d6`

## string_xrefs

- `0x1800b6807`: `UndetectedInstallerIsImageInProgramFiles`
- `0x1800b6800`: `Failed to get Program Files directory path [%d]`

## pseudocode

```c
__int64 __fastcall UndetectedInstallerIsImageInProgramFiles(int *a1, unsigned __int16 *a2)
{
  int v4; // edi
  DWORD LastError; // eax
  int v6; // r8d
  const char *v7; // r9
  DWORD v8; // ebx
  wchar_t *v9; // rbx
  wchar_t *v10; // rbx
  WCHAR String1[8]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Dst[264]; // [rsp+40h] [rbp-238h] BYREF

  *a1 = 0;
  Dst[0] = 0;
  String1[0] = 0;
  v4 = 0;
  if ( ExpandEnvironmentStringsW(L"%ProgramFiles%", Dst, 0x104u) )
  {
    v9 = PathSkipRootW(Dst);
    _wcslwr(a2);
    _wcslwr(v9);
    if ( wcsstr(a2, v9) )
      goto LABEL_12;
    if ( !ExpandEnvironmentStringsW(L"%PROCESSOR_ARCHITECTURE%", String1, 8u) )
    {
      LastError = GetLastError();
      v7 = "Failed to get processor architecture [%d]";
      v6 = 785;
      goto LABEL_4;
    }
    if ( _wcsicmp(String1, L"x86") )
    {
      Dst[0] = 0;
      if ( !ExpandEnvironmentStringsW(L"%ProgramFiles(x86)%", Dst, 0x104u) )
      {
        LastError = GetLastError();
        v6 = 810;
        goto LABEL_3;
      }
      v10 = PathSkipRootW(Dst);
      _wcslwr(a2);
      _wcslwr(v10);
      if ( wcsstr(a2, v10) )
LABEL_12:
        v4 = 1;
    }
    v8 = 0;
    goto LABEL_14;
  }
  LastError = GetLastError();
  v6 = 756;
LABEL_3:
  v7 = "Failed to get Program Files directory path [%d]";
LABEL_4:
  v8 = LastError;
  AslLogCallPrintf(1, (unsigned int)"UndetectedInstallerIsImageInProgramFiles", v6, (_DWORD)v7);
LABEL_14:
  *a1 = v4;
  return v8;
}

```

## disassembly

```asm
0x1800b679c  mov     [rsp+arg_10], rbx
0x1800b67a1  push    rsi
0x1800b67a2  push    rdi
0x1800b67a3  push    r14
0x1800b67a5  sub     rsp, 260h
0x1800b67ac  mov     rax, cs:__security_cookie
0x1800b67b3  xor     rax, rsp
0x1800b67b6  mov     [rsp+278h+var_28], rax
0x1800b67be  xor     eax, eax
0x1800b67c0  mov     dword ptr [rcx], 0
0x1800b67c6  mov     rsi, rdx
0x1800b67c9  mov     [rsp+278h+Dst], ax
0x1800b67ce  mov     r14, rcx
0x1800b67d1  mov     [rsp+278h+String1], ax
0x1800b67d6  lea     rdx, [rsp+278h+Dst]; lpDst
0x1800b67db  mov     r8d, 104h; nSize
0x1800b67e1  lea     rcx, aProgramfiles; "%ProgramFiles%"
0x1800b67e8  xor     edi, edi
0x1800b67ea  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b67f0  test    eax, eax
0x1800b67f2  jnz     short loc_1800B6823
0x1800b67f4  call    cs:__imp_GetLastError
0x1800b67fa  mov     r8d, 2F4h
0x1800b6800  lea     r9, aFailedToGetPro_6; "Failed to get Program Files directory p"...
0x1800b6807  lea     rdx, aUndetectedinst_1; "UndetectedInstallerIsImageInProgramFile"...
0x1800b680e  mov     [rsp+278h+var_258], eax
0x1800b6812  mov     ecx, 1
0x1800b6817  mov     ebx, eax
0x1800b6819  call    AslLogCallPrintf
0x1800b681e  jmp     loc_1800B6909
0x1800b6823  lea     rcx, [rsp+278h+Dst]; pszPath
0x1800b6828  call    cs:__imp_PathSkipRootW
0x1800b682e  mov     rcx, rsi; String
0x1800b6831  mov     rbx, rax
0x1800b6834  call    cs:__imp__wcslwr
0x1800b683a  mov     rcx, rbx; String
0x1800b683d  call    cs:__imp__wcslwr
0x1800b6843  mov     rdx, rbx; SubStr
0x1800b6846  mov     rcx, rsi; Str
0x1800b6849  call    cs:__imp_wcsstr
0x1800b684f  test    rax, rax
0x1800b6852  jnz     loc_1800B6902
0x1800b6858  lea     r8d, [rax+8]; nSize
0x1800b685c  lea     rdx, [rsp+278h+String1]; lpDst
0x1800b6861  lea     rcx, aProcessorArchi; "%PROCESSOR_ARCHITECTURE%"
0x1800b6868  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b686e  test    eax, eax
0x1800b6870  jnz     short loc_1800B6887
0x1800b6872  call    cs:__imp_GetLastError
0x1800b6878  lea     r9, aFailedToGetPro_9; "Failed to get processor architecture [%"...
0x1800b687f  mov     r8d, 311h
0x1800b6885  jmp     short loc_1800B6807
0x1800b6887  lea     rdx, aX86_0; "x86"
0x1800b688e  lea     rcx, [rsp+278h+String1]; String1
0x1800b6893  call    cs:__imp__wcsicmp
0x1800b6899  test    eax, eax
0x1800b689b  jz      short loc_1800B6907
0x1800b689d  xor     eax, eax
0x1800b689f  lea     rdx, [rsp+278h+Dst]; lpDst
0x1800b68a4  mov     r8d, 104h; nSize
0x1800b68aa  mov     [rsp+278h+Dst], ax
0x1800b68af  lea     rcx, aProgramfilesX8; "%ProgramFiles(x86)%"
0x1800b68b6  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b68bc  test    eax, eax
0x1800b68be  jnz     short loc_1800B68D1
0x1800b68c0  call    cs:__imp_GetLastError
0x1800b68c6  mov     r8d, 32Ah
0x1800b68cc  jmp     loc_1800B6800
0x1800b68d1  lea     rcx, [rsp+278h+Dst]; pszPath
0x1800b68d6  call    cs:__imp_PathSkipRootW
0x1800b68dc  mov     rcx, rsi; String
0x1800b68df  mov     rbx, rax
0x1800b68e2  call    cs:__imp__wcslwr
0x1800b68e8  mov     rcx, rbx; String
0x1800b68eb  call    cs:__imp__wcslwr
0x1800b68f1  mov     rdx, rbx; SubStr
0x1800b68f4  mov     rcx, rsi; Str
0x1800b68f7  call    cs:__imp_wcsstr
0x1800b68fd  test    rax, rax
0x1800b6900  jz      short loc_1800B6907
0x1800b6902  mov     edi, 1
0x1800b6907  xor     ebx, ebx
0x1800b6909  mov     [r14], edi
0x1800b690c  mov     eax, ebx
0x1800b690e  mov     rcx, [rsp+278h+var_28]
0x1800b6916  xor     rcx, rsp; StackCookie
0x1800b6919  call    __security_check_cookie
0x1800b691e  mov     rbx, [rsp+278h+arg_10]
0x1800b6926  add     rsp, 260h
0x1800b692d  pop     r14
0x1800b692f  pop     rdi
0x1800b6930  pop     rsi
0x1800b6931  retn
```
