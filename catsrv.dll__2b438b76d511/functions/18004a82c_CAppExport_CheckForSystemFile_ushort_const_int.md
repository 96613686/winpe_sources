# CAppExport::CheckForSystemFile(ushort const *,int *)

- ea: `0x18004a82c`
- end: `0x18004a97f`
- name: `?CheckForSystemFile@CAppExport@@AEAAJPEBGPEAH@Z`
- size: `339`
- prototype: `int __fastcall(CAppExport *this, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fe08`
- `0x18004aa88`
- `0x18004f2a4`

## callees

- `0x18000be28`
- `0x1800136d8`
- `0x18004a82c`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004a93f`
- `msvcrt!_wcsicmp` at `0x18004a93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004a8e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004a8e9`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18004a8a7`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18004a90b`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18004a8a7`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18004a90b`

## pseudocode

```c
int __fastcall CAppExport::CheckForSystemFile(CAppExport *this, const unsigned __int16 *a2, int *a3)
{
  int result; // eax
  DWORD LongPathNameW; // edi
  DWORD v7; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-438h] BYREF
  wchar_t szLongPath[264]; // [rsp+230h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( !a2 || !a3 )
    return -2147467261;
  *a3 = 0;
  result = IsLocalPath(a2, 0);
  if ( result == 1 )
    return 0;
  if ( result < 0 )
    return result;
  LongPathNameW = GetLongPathNameW(a2, szLongPath, 0x104u);
  if ( !LongPathNameW )
  {
    result = GetLastError();
    if ( result != 2 )
      goto LABEL_7;
    return 0;
  }
  if ( LongPathNameW >= 0x104 )
    return 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    v7 = GetLongPathNameW(Buffer, Buffer, 0x104u);
    if ( v7 )
    {
      if ( v7 <= LongPathNameW )
      {
        if ( 2 * (unsigned __int64)v7 >= 0x20A )
          _report_rangecheckfailure();
        szLongPath[v7] = 0;
        if ( !_wcsicmp(szLongPath, Buffer) )
          *a3 = 1;
      }
      return 0;
    }
  }
  result = GetLastError();
LABEL_7:
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18004a82c  mov     [rsp+arg_0], rbx
0x18004a831  push    rdi
0x18004a832  sub     rsp, 450h
0x18004a839  mov     rax, cs:__security_cookie
0x18004a840  xor     rax, rsp
0x18004a843  mov     [rsp+458h+var_18], rax
0x18004a84b  mov     rbx, r8
0x18004a84e  lea     rcx, [rsp+458h+Buffer]; void *
0x18004a853  mov     rdi, rdx
0x18004a856  mov     r8d, 20Ah; Size
0x18004a85c  xor     edx, edx; Val
0x18004a85e  call    memset_0
0x18004a863  test    rdi, rdi
0x18004a866  jz      loc_18004A959
0x18004a86c  test    rbx, rbx
0x18004a86f  jz      loc_18004A959
0x18004a875  xor     edx, edx; unsigned __int16 **
0x18004a877  mov     dword ptr [rbx], 0
0x18004a87d  mov     rcx, rdi; unsigned __int16 *
0x18004a880  call    ?IsLocalPath@@YAJPEBGPEAPEAG@Z; IsLocalPath(ushort const *,ushort * *)
0x18004a885  cmp     eax, 1
0x18004a888  jz      loc_18004A94F
0x18004a88e  test    eax, eax
0x18004a890  js      loc_18004A95E
0x18004a896  mov     r8d, 104h; cchBuffer
0x18004a89c  lea     rdx, [rsp+458h+szLongPath]; lpszLongPath
0x18004a8a4  mov     rcx, rdi; lpszShortPath
0x18004a8a7  call    cs:__imp_GetLongPathNameW
0x18004a8ad  mov     edi, eax
0x18004a8af  test    eax, eax
0x18004a8b1  jnz     short loc_18004A8D7
0x18004a8b3  call    cs:__imp_GetLastError
0x18004a8b9  cmp     eax, 2
0x18004a8bc  jz      loc_18004A94F
0x18004a8c2  test    eax, eax
0x18004a8c4  jle     loc_18004A95E
0x18004a8ca  movzx   eax, ax
0x18004a8cd  or      eax, 80070000h
0x18004a8d2  jmp     loc_18004A95E
0x18004a8d7  cmp     edi, 104h
0x18004a8dd  jnb     short loc_18004A94F
0x18004a8df  mov     edx, 104h; uSize
0x18004a8e4  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x18004a8e9  call    cs:__imp_GetSystemDirectoryW
0x18004a8ef  test    eax, eax
0x18004a8f1  jnz     short loc_18004A8FB
0x18004a8f3  call    cs:__imp_GetLastError
0x18004a8f9  jmp     short loc_18004A8C2
0x18004a8fb  mov     r8d, 104h; cchBuffer
0x18004a901  lea     rdx, [rsp+458h+Buffer]; lpszLongPath
0x18004a906  lea     rcx, [rsp+458h+Buffer]; lpszShortPath
0x18004a90b  call    cs:__imp_GetLongPathNameW
0x18004a911  test    eax, eax
0x18004a913  jz      short loc_18004A8F3
0x18004a915  cmp     eax, edi
0x18004a917  ja      short loc_18004A94F
0x18004a919  mov     eax, eax
0x18004a91b  lea     rcx, [rax+rax]
0x18004a91f  cmp     rcx, 20Ah
0x18004a926  jnb     short loc_18004A953
0x18004a928  xor     eax, eax
0x18004a92a  lea     rdx, [rsp+458h+Buffer]; String2
0x18004a92f  mov     [rsp+rcx+458h+szLongPath], ax
0x18004a937  lea     rcx, [rsp+458h+szLongPath]; String1
0x18004a93f  call    cs:__imp__wcsicmp
0x18004a945  test    eax, eax
0x18004a947  jnz     short loc_18004A94F
0x18004a949  mov     dword ptr [rbx], 1
0x18004a94f  xor     eax, eax
0x18004a951  jmp     short loc_18004A95E
0x18004a953  call    __report_rangecheckfailure
0x18004a959  mov     eax, 80004003h
0x18004a95e  mov     rcx, [rsp+458h+var_18]
0x18004a966  xor     rcx, rsp; StackCookie
0x18004a969  call    __security_check_cookie
0x18004a96e  mov     rbx, [rsp+458h+arg_0]
0x18004a976  add     rsp, 450h
0x18004a97d  pop     rdi
0x18004a97e  retn
```
