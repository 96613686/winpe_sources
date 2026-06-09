# CopyFileToTempDir(char const *,ushort * *)

- ea: `0x1400094a4`
- end: `0x1400096ae`
- name: `?CopyFileToTempDir@@YAJPEBDPEAPEAG@Z`
- size: `522`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14000747c`

## callees

- `0x140006070`
- `0x140008984`
- `0x1400094a4`
- `0x140009d84`
- `0x14000b248`
- `0x14001057c`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x14000950b`
- `KERNEL32!MultiByteToWideChar` at `0x14000950b`
- `KERNEL32!CopyFileW` at `0x140009630`
- `KERNEL32!CopyFileW` at `0x140009630`
- `KERNEL32!GetFileAttributesW` at `0x14000959d`
- `KERNEL32!GetFileAttributesW` at `0x14000959d`
- `KERNEL32!GetLastError` at `0x14000951e`
- `KERNEL32!GetLastError` at `0x140009530`
- `KERNEL32!GetLastError` at `0x140009547`
- `KERNEL32!GetLastError` at `0x140009640`
- `KERNEL32!GetLastError` at `0x140009652`
- `KERNEL32!GetLastError` at `0x140009663`
- `KERNEL32!GetLastError` at `0x14000951e`
- `KERNEL32!GetLastError` at `0x140009530`
- `KERNEL32!GetLastError` at `0x140009547`
- `KERNEL32!GetLastError` at `0x140009640`
- `KERNEL32!GetLastError` at `0x140009652`
- `KERNEL32!GetLastError` at `0x140009663`
- `OLEAUT32!__imp_SysAllocString` at `0x140009698`
- `OLEAUT32!__imp_SysAllocString` at `0x140009698`
- `OLEAUT32!__imp_SysFreeString` at `0x140009687`
- `OLEAUT32!__imp_SysFreeString` at `0x140009687`

## pseudocode

```c
DWORD __fastcall CopyFileToTempDir(LPCCH lpMultiByteStr, LPCWSTR *a2)
{
  unsigned __int16 *FileNameFromPath; // r14
  DWORD result; // eax
  DWORD LastError; // eax
  int v7; // ebx
  size_t v8; // rdx
  int Extension; // ebx
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  PCWSTR ppszExt; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+250h] [rbp+150h] BYREF

  FileNameFromPath = FindFileNameFromPath(*a2);
  if ( FileNameFromPath == *a2 )
    return -2147467259;
  if ( !MultiByteToWideChar(0, 8u, lpMultiByteStr, -1, WideCharStr, 260) )
  {
    if ( (GetLastError() & 0x80000000) != 0 )
    {
      result = GetLastError();
      goto LABEL_5;
    }
    LastError = GetLastError();
    goto LABEL_9;
  }
  v7 = 1;
  while ( 1 )
  {
    LODWORD(lpWideCharStr) = v7;
    if ( (int)StringCchPrintfW(FileName, 0x104u, L"%s\\[%d]%s", WideCharStr, lpWideCharStr, FileNameFromPath) < 0
      || GetFileAttributesW(FileName) == -1 )
    {
      break;
    }
    if ( ++v7 > 500 )
      return -2147467259;
  }
  ppszExt = 0;
  Extension = PathCchFindExtension(FileName, v8, &ppszExt);
  if ( Extension < 0 )
    return Extension;
  if ( *ppszExt )
    *ppszExt = 0;
  Extension = AxiPreScanPathW(FileName);
  if ( Extension < 0 )
    return Extension;
  if ( CopyFileW(*a2, FileName, 1) )
  {
    Extension = SetFileIntegrityLevelByNameW(FileName);
    if ( Extension >= 0 )
    {
      SysFreeString((BSTR)*a2);
      *a2 = SysAllocString(FileName);
    }
    return Extension;
  }
  if ( (GetLastError() & 0x80000000) != 0 )
  {
    result = GetLastError();
LABEL_5:
    if ( !result )
      return 1;
    return result;
  }
  LastError = GetLastError();
LABEL_9:
  if ( !LastError )
    LOWORD(LastError) = 1;
  return (unsigned __int16)LastError | 0x80070000;
}

```

## disassembly

```asm
0x1400094a4  mov     [rsp-8+arg_10], rbx
0x1400094a9  push    rbp
0x1400094aa  push    rsi
0x1400094ab  push    rdi
0x1400094ac  push    r14
0x1400094ae  push    r15
0x1400094b0  lea     rbp, [rsp-370h]
0x1400094b8  sub     rsp, 470h
0x1400094bf  mov     rax, cs:__security_cookie
0x1400094c6  xor     rax, rsp
0x1400094c9  mov     [rbp+390h+var_30], rax
0x1400094d0  mov     rbx, rcx
0x1400094d3  mov     rsi, rdx
0x1400094d6  mov     rcx, [rdx]; lpsz
0x1400094d9  call    ?FindFileNameFromPath@@YAPEAGPEBG@Z; FindFileNameFromPath(ushort const *)
0x1400094de  mov     r14, rax
0x1400094e1  cmp     rax, [rsi]
0x1400094e4  jz      loc_1400095B8
0x1400094ea  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1400094ee  mov     [rsp+490h+cchWideChar], 104h; cchWideChar
0x1400094f6  lea     rax, [rbp+390h+WideCharStr]
0x1400094fd  mov     r8, rbx; lpMultiByteStr
0x140009500  xor     ecx, ecx; CodePage
0x140009502  mov     [rsp+490h+lpWideCharStr], rax; lpWideCharStr
0x140009507  lea     edx, [r9+9]; dwFlags
0x14000950b  call    cs:__imp_MultiByteToWideChar
0x140009512  nop     dword ptr [rax+rax+00h]
0x140009517  xor     r15d, r15d
0x14000951a  test    eax, eax
0x14000951c  jnz     short loc_140009567
0x14000951e  call    cs:__imp_GetLastError
0x140009525  nop     dword ptr [rax+rax+00h]
0x14000952a  test    eax, eax
0x14000952c  jz      short loc_140009547
0x14000952e  jg      short loc_140009547
0x140009530  call    cs:__imp_GetLastError
0x140009537  nop     dword ptr [rax+rax+00h]
0x14000953c  lea     edi, [r15+1]
0x140009540  test    eax, eax
0x140009542  cmovz   eax, edi
0x140009545  jmp     short loc_1400095BD
0x140009547  call    cs:__imp_GetLastError
0x14000954e  nop     dword ptr [rax+rax+00h]
0x140009553  mov     edi, 1
0x140009558  test    eax, eax
0x14000955a  cmovz   eax, edi
0x14000955d  movzx   eax, ax
0x140009560  or      eax, 80070000h
0x140009565  jmp     short loc_1400095BD
0x140009567  mov     edi, 1
0x14000956c  mov     ebx, edi
0x14000956e  mov     qword ptr [rsp+490h+cchWideChar], r14
0x140009573  lea     r9, [rbp+390h+WideCharStr]
0x14000957a  lea     r8, aSDS; "%s\\[%d]%s"
0x140009581  mov     dword ptr [rsp+490h+lpWideCharStr], ebx
0x140009585  mov     edx, 104h; unsigned __int64
0x14000958a  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x14000958f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009594  test    eax, eax
0x140009596  js      short loc_1400095E4
0x140009598  lea     rcx, [rsp+490h+FileName]; lpFileName
0x14000959d  call    cs:__imp_GetFileAttributesW
0x1400095a4  nop     dword ptr [rax+rax+00h]
0x1400095a9  cmp     eax, 0FFFFFFFFh
0x1400095ac  jz      short loc_1400095E4
0x1400095ae  add     ebx, edi
0x1400095b0  cmp     ebx, 1F4h
0x1400095b6  jle     short loc_14000956E
0x1400095b8  mov     eax, 80004005h
0x1400095bd  mov     rcx, [rbp+390h+var_30]
0x1400095c4  xor     rcx, rsp; StackCookie
0x1400095c7  call    __security_check_cookie
0x1400095cc  mov     rbx, [rsp+490h+arg_10]
0x1400095d4  add     rsp, 470h
0x1400095db  pop     r15
0x1400095dd  pop     r14
0x1400095df  pop     rdi
0x1400095e0  pop     rsi
0x1400095e1  pop     rbp
0x1400095e2  retn
0x1400095e4  lea     r8, [rsp+490h+ppszExt]; ppszExt
0x1400095e9  mov     [rsp+490h+ppszExt], r15
0x1400095ee  lea     rcx, [rsp+490h+FileName]; pszPath
0x1400095f3  call    PathCchFindExtension
0x1400095f8  mov     ebx, eax
0x1400095fa  test    eax, eax
0x1400095fc  js      loc_1400096A7
0x140009602  mov     rcx, [rsp+490h+ppszExt]
0x140009607  cmp     [rcx], r15w
0x14000960b  jz      short loc_140009611
0x14000960d  mov     [rcx], r15w
0x140009611  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x140009616  call    ?AxiPreScanPathW@@YAJPEBG@Z; AxiPreScanPathW(ushort const *)
0x14000961b  mov     ebx, eax
0x14000961d  test    eax, eax
0x14000961f  js      loc_1400096A7
0x140009625  mov     rcx, [rsi]; lpExistingFileName
0x140009628  lea     rdx, [rsp+490h+FileName]; lpNewFileName
0x14000962d  mov     r8d, edi; bFailIfExists
0x140009630  call    cs:__imp_CopyFileW
0x140009637  nop     dword ptr [rax+rax+00h]
0x14000963c  test    eax, eax
0x14000963e  jnz     short loc_140009674
0x140009640  call    cs:__imp_GetLastError
0x140009647  nop     dword ptr [rax+rax+00h]
0x14000964c  test    eax, eax
0x14000964e  jz      short loc_140009663
0x140009650  jg      short loc_140009663
0x140009652  call    cs:__imp_GetLastError
0x140009659  nop     dword ptr [rax+rax+00h]
0x14000965e  jmp     loc_140009540
0x140009663  call    cs:__imp_GetLastError
0x14000966a  nop     dword ptr [rax+rax+00h]
0x14000966f  jmp     loc_140009558
0x140009674  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x140009679  call    ?SetFileIntegrityLevelByNameW@@YAJPEBGH@Z; SetFileIntegrityLevelByNameW(ushort const *,int)
0x14000967e  mov     ebx, eax
0x140009680  test    eax, eax
0x140009682  js      short loc_1400096A7
0x140009684  mov     rcx, [rsi]; bstrString
0x140009687  call    cs:__imp_SysFreeString
0x14000968e  nop     dword ptr [rax+rax+00h]
0x140009693  lea     rcx, [rsp+490h+FileName]; psz
0x140009698  call    cs:__imp_SysAllocString
0x14000969f  nop     dword ptr [rax+rax+00h]
0x1400096a4  mov     [rsi], rax
0x1400096a7  mov     eax, ebx
0x1400096a9  jmp     loc_1400095BD
```
