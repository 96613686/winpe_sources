# CopyFileToRandomDir(char const *,ushort *,ushort * *)

- ea: `0x140009240`
- end: `0x14000949c`
- name: `?CopyFileToRandomDir@@YAJPEBDPEAGPEAPEAG@Z`
- size: `604`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, LPCWSTR lpsz, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000747c`

## callees

- `0x140006070`
- `0x140008984`
- `0x140009240`
- `0x140009d84`
- `0x14000b248`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140009390`
- `KERNEL32!CloseHandle` at `0x140009390`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1400093ed`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1400093ed`
- `KERNEL32!MultiByteToWideChar` at `0x140009311`
- `KERNEL32!MultiByteToWideChar` at `0x140009311`
- `KERNEL32!CopyFileW` at `0x140009424`
- `KERNEL32!CopyFileW` at `0x140009424`
- `KERNEL32!CreateFileW` at `0x1400092ab`
- `KERNEL32!CreateFileW` at `0x1400092ab`
- `KERNEL32!GetLastError` at `0x140009321`
- `KERNEL32!GetLastError` at `0x140009333`
- `KERNEL32!GetLastError` at `0x140009349`
- `KERNEL32!GetLastError` at `0x140009321`
- `KERNEL32!GetLastError` at `0x140009333`
- `KERNEL32!GetLastError` at `0x140009349`
- `ole32!CoImpersonateClient` at `0x14000926d`
- `ole32!CoImpersonateClient` at `0x14000926d`
- `ole32!CoRevertToSelf` at `0x1400092ba`
- `ole32!CoRevertToSelf` at `0x1400092ba`
- `OLEAUT32!__imp_SysAllocString` at `0x140009460`
- `OLEAUT32!__imp_SysAllocString` at `0x140009460`
- `OLEAUT32!__imp_SysFreeString` at `0x14000944f`
- `OLEAUT32!__imp_SysFreeString` at `0x14000944f`

## pseudocode

```c
__int64 __fastcall CopyFileToRandomDir(LPCCH lpMultiByteStr, LPCWSTR lpsz, unsigned __int16 **a3)
{
  char *FileW; // rbx
  const WCHAR *FileNameFromPath; // rsi
  signed int v8; // edi
  DWORD LastError; // eax
  WCHAR v11; // ax
  WCHAR *v12; // rcx
  DWORD FinalPathNameByHandleW; // eax
  int v14; // edx
  WCHAR NewFileName[264]; // [rsp+40h] [rbp-688h] BYREF
  WCHAR WideCharStr[264]; // [rsp+250h] [rbp-478h] BYREF
  WCHAR szFilePath[272]; // [rsp+460h] [rbp-268h] BYREF

  if ( CoImpersonateClient() >= 0 )
  {
    FileW = (char *)CreateFileW(lpsz, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    CoRevertToSelf();
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      FileNameFromPath = FindFileNameFromPath(lpsz);
      if ( FileNameFromPath == lpsz )
        goto LABEL_4;
      if ( MultiByteToWideChar(0, 8u, lpMultiByteStr, -1, WideCharStr, 260) )
      {
        v8 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s.dat", WideCharStr, FileNameFromPath);
        if ( v8 < 0 )
          goto LABEL_14;
        v8 = AxiPreScanPathW(NewFileName);
        if ( v8 < 0 )
          goto LABEL_14;
        v11 = NewFileName[0];
        if ( NewFileName[0] )
        {
          v12 = NewFileName;
          do
          {
            if ( v11 == 47 )
              *v12 = 92;
            v11 = *++v12;
          }
          while ( *v12 );
        }
        FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, szFilePath, 0x10Cu, 0);
        if ( FinalPathNameByHandleW == 3 || FinalPathNameByHandleW == 8 || FinalPathNameByHandleW == 87 )
        {
LABEL_4:
          v8 = -2147467259;
LABEL_14:
          CloseHandle(FileW);
          return (unsigned int)v8;
        }
        if ( CopyFileW(szFilePath, NewFileName, 1) )
        {
          v8 = SetFileIntegrityLevelByNameW(NewFileName, v14);
          if ( v8 >= 0 )
          {
            SysFreeString(*a3);
            *a3 = SysAllocString(NewFileName);
          }
          goto LABEL_14;
        }
      }
      if ( (GetLastError() & 0x80000000) == 0 )
      {
        LastError = GetLastError();
        if ( !LastError )
          LOWORD(LastError) = 1;
        v8 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v8 = GetLastError();
        if ( !v8 )
          v8 = 1;
      }
      goto LABEL_14;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x140009240  push    rbx
0x140009242  push    rbp
0x140009243  push    rsi
0x140009244  push    rdi
0x140009245  push    r12
0x140009247  push    r14
0x140009249  push    r15
0x14000924b  sub     rsp, 690h
0x140009252  mov     rax, cs:__security_cookie
0x140009259  xor     rax, rsp
0x14000925c  mov     [rsp+6C8h+var_48], rax
0x140009264  mov     r14, r8
0x140009267  mov     rdi, rdx
0x14000926a  mov     rbp, rcx
0x14000926d  call    cs:__imp_CoImpersonateClient
0x140009274  nop     dword ptr [rax+rax+00h]
0x140009279  xor     r15d, r15d
0x14000927c  test    eax, eax
0x14000927e  js      loc_140009474
0x140009284  mov     [rsp+6C8h+hTemplateFile], r15; hTemplateFile
0x140009289  lea     r12d, [r15+1]
0x14000928d  mov     r8d, r12d; dwShareMode
0x140009290  mov     [rsp+6C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140009298  xor     r9d, r9d; lpSecurityAttributes
0x14000929b  mov     [rsp+6C8h+dwCreationDisposition], 3; dwCreationDisposition
0x1400092a3  mov     edx, 80000000h; dwDesiredAccess
0x1400092a8  mov     rcx, rdi; lpFileName
0x1400092ab  call    cs:__imp_CreateFileW
0x1400092b2  nop     dword ptr [rax+rax+00h]
0x1400092b7  mov     rbx, rax
0x1400092ba  call    cs:__imp_CoRevertToSelf
0x1400092c1  nop     dword ptr [rax+rax+00h]
0x1400092c6  lea     rax, [rbx-1]
0x1400092ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400092ce  ja      loc_140009474
0x1400092d4  mov     rcx, rdi; lpsz
0x1400092d7  call    ?FindFileNameFromPath@@YAPEAGPEBG@Z; FindFileNameFromPath(ushort const *)
0x1400092dc  mov     rsi, rax
0x1400092df  cmp     rax, rdi
0x1400092e2  jnz     short loc_1400092EE
0x1400092e4  mov     edi, 80004005h
0x1400092e9  jmp     loc_14000938D
0x1400092ee  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1400092f2  lea     rax, [rsp+6C8h+WideCharStr]
0x1400092fa  mov     edi, 104h
0x1400092ff  mov     r8, rbp; lpMultiByteStr
0x140009302  mov     [rsp+6C8h+dwFlagsAndAttributes], edi; cchWideChar
0x140009306  xor     ecx, ecx; CodePage
0x140009308  mov     qword ptr [rsp+6C8h+dwCreationDisposition], rax; lpWideCharStr
0x14000930d  lea     edx, [r9+9]; dwFlags
0x140009311  call    cs:__imp_MultiByteToWideChar
0x140009318  nop     dword ptr [rax+rax+00h]
0x14000931d  test    eax, eax
0x14000931f  jnz     short loc_140009366
0x140009321  call    cs:__imp_GetLastError
0x140009328  nop     dword ptr [rax+rax+00h]
0x14000932d  test    eax, eax
0x14000932f  jz      short loc_140009349
0x140009331  jg      short loc_140009349
0x140009333  call    cs:__imp_GetLastError
0x14000933a  nop     dword ptr [rax+rax+00h]
0x14000933f  test    eax, eax
0x140009341  mov     edi, eax
0x140009343  cmovz   edi, r12d
0x140009347  jmp     short loc_14000938D
0x140009349  call    cs:__imp_GetLastError
0x140009350  nop     dword ptr [rax+rax+00h]
0x140009355  test    eax, eax
0x140009357  cmovz   eax, r12d
0x14000935b  movzx   edi, ax
0x14000935e  or      edi, 80070000h
0x140009364  jmp     short loc_14000938D
0x140009366  lea     r9, [rsp+6C8h+WideCharStr]
0x14000936e  mov     qword ptr [rsp+6C8h+dwCreationDisposition], rsi
0x140009373  lea     r8, aSSDat; "%s\\%s.dat"
0x14000937a  mov     rdx, rdi; unsigned __int64
0x14000937d  lea     rcx, [rsp+6C8h+NewFileName]; unsigned __int16 *
0x140009382  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009387  mov     edi, eax
0x140009389  test    eax, eax
0x14000938b  jns     short loc_1400093A3
0x14000938d  mov     rcx, rbx; hObject
0x140009390  call    cs:__imp_CloseHandle
0x140009397  nop     dword ptr [rax+rax+00h]
0x14000939c  mov     eax, edi
0x14000939e  jmp     loc_140009479
0x1400093a3  lea     rcx, [rsp+6C8h+NewFileName]; unsigned __int16 *
0x1400093a8  call    ?AxiPreScanPathW@@YAJPEBG@Z; AxiPreScanPathW(ushort const *)
0x1400093ad  mov     edi, eax
0x1400093af  test    eax, eax
0x1400093b1  js      short loc_14000938D
0x1400093b3  movzx   eax, [rsp+6C8h+NewFileName]
0x1400093b8  test    ax, ax
0x1400093bb  jz      short loc_1400093D9
0x1400093bd  lea     rcx, [rsp+6C8h+NewFileName]
0x1400093c2  cmp     ax, 2Fh ; '/'
0x1400093c6  jnz     short loc_1400093CD
0x1400093c8  mov     word ptr [rcx], 5Ch ; '\'
0x1400093cd  add     rcx, 2
0x1400093d1  movzx   eax, word ptr [rcx]
0x1400093d4  test    ax, ax
0x1400093d7  jnz     short loc_1400093C2
0x1400093d9  xor     r9d, r9d; dwFlags
0x1400093dc  lea     rdx, [rsp+6C8h+szFilePath]; lpszFilePath
0x1400093e4  mov     r8d, 10Ch; cchFilePath
0x1400093ea  mov     rcx, rbx; hFile
0x1400093ed  call    cs:__imp_GetFinalPathNameByHandleW
0x1400093f4  nop     dword ptr [rax+rax+00h]
0x1400093f9  cmp     eax, 3
0x1400093fc  jz      loc_1400092E4
0x140009402  cmp     eax, 8
0x140009405  jz      loc_1400092E4
0x14000940b  cmp     eax, 57h ; 'W'
0x14000940e  jz      loc_1400092E4
0x140009414  mov     r8d, r12d; bFailIfExists
0x140009417  lea     rdx, [rsp+6C8h+NewFileName]; lpNewFileName
0x14000941c  lea     rcx, [rsp+6C8h+szFilePath]; lpExistingFileName
0x140009424  call    cs:__imp_CopyFileW
0x14000942b  nop     dword ptr [rax+rax+00h]
0x140009430  test    eax, eax
0x140009432  jz      loc_140009321
0x140009438  lea     rcx, [rsp+6C8h+NewFileName]; unsigned __int16 *
0x14000943d  call    ?SetFileIntegrityLevelByNameW@@YAJPEBGH@Z; SetFileIntegrityLevelByNameW(ushort const *,int)
0x140009442  mov     edi, eax
0x140009444  test    eax, eax
0x140009446  js      loc_14000938D
0x14000944c  mov     rcx, [r14]; bstrString
0x14000944f  call    cs:__imp_SysFreeString
0x140009456  nop     dword ptr [rax+rax+00h]
0x14000945b  lea     rcx, [rsp+6C8h+NewFileName]; psz
0x140009460  call    cs:__imp_SysAllocString
0x140009467  nop     dword ptr [rax+rax+00h]
0x14000946c  mov     [r14], rax
0x14000946f  jmp     loc_14000938D
0x140009474  mov     eax, 80004005h
0x140009479  mov     rcx, [rsp+6C8h+var_48]
0x140009481  xor     rcx, rsp; StackCookie
0x140009484  call    __security_check_cookie
0x140009489  add     rsp, 690h
0x140009490  pop     r15
0x140009492  pop     r14
0x140009494  pop     r12
0x140009496  pop     rdi
0x140009497  pop     rsi
0x140009498  pop     rbp
0x140009499  pop     rbx
0x14000949a  retn
```
