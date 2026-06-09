# IsBinaryPresent

- ea: `0x1800149e8`
- end: `0x180014b11`
- name: `IsBinaryPresent`
- size: `297`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180021420`

## callees

- `0x180005670`
- `0x1800149e8`
- `0x18001cef0`
- `0x18001d826`
- `0x18002e8d0`
- `0x18004d1a0`
- `0x18004d200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a52`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014a48`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014a48`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014abc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014abc`

## pseudocode

```c
__int64 __fastcall IsBinaryPresent(STRSAFE_LPCWSTR pszSrc)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax
  HRESULT v4; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_S(1028, 10, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids, pszSrc);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_4;
  v4 = StringCchCatW(Buffer, 0x104u, L"\\");
  if ( v4 < 0 || (v4 = StringCchCatW(Buffer, 0x104u, pszSrc), v4 < 0) )
  {
    LastError = WX_WIN32_FROM_HR((unsigned int)v4);
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_S(1028, 11, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids, Buffer);
    if ( GetFileAttributesW(Buffer) == -1 )
    {
LABEL_4:
      LastError = GetLastError();
      goto LABEL_12;
    }
    LastError = 0;
    v2 = 1;
  }
LABEL_12:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 12, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids, LastError);
  return v2;
}

```

## disassembly

```asm
0x1800149e8  mov     [rsp+arg_8], rbx
0x1800149ed  push    rdi
0x1800149ee  sub     rsp, 240h
0x1800149f5  mov     rax, cs:__security_cookie
0x1800149fc  xor     rax, rsp
0x1800149ff  mov     [rsp+248h+var_18], rax
0x180014a07  mov     rdi, rcx
0x180014a0a  xor     ebx, ebx
0x180014a0c  lea     rcx, [rsp+248h+Buffer]; void *
0x180014a11  xor     edx, edx; Val
0x180014a13  mov     r8d, 208h; Size
0x180014a19  call    memset_0
0x180014a1e  test    byte ptr cs:xmmword_1800616A0, 10h
0x180014a25  jz      short loc_180014A3E
0x180014a27  lea     edx, [rbx+0Ah]
0x180014a2a  mov     ecx, 404h
0x180014a2f  mov     r9, rdi
0x180014a32  lea     r8, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids
0x180014a39  call    WPP_SF_S
0x180014a3e  mov     edx, 104h; uSize
0x180014a43  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180014a48  call    cs:__imp_GetSystemDirectoryW
0x180014a4e  test    eax, eax
0x180014a50  jnz     short loc_180014A5A
0x180014a52  call    cs:__imp_GetLastError
0x180014a58  jmp     short loc_180014ACC
0x180014a5a  lea     r8, asc_180055030; "\\"
0x180014a61  mov     edx, 104h; cchDest
0x180014a66  lea     rcx, [rsp+248h+Buffer]; pszDest
0x180014a6b  call    StringCchCatW
0x180014a70  test    eax, eax
0x180014a72  jns     short loc_180014A7D
0x180014a74  mov     ecx, eax
0x180014a76  call    WX_WIN32_FROM_HR
0x180014a7b  jmp     short loc_180014ACC
0x180014a7d  mov     r8, rdi; pszSrc
0x180014a80  lea     rcx, [rsp+248h+Buffer]; pszDest
0x180014a85  mov     edx, 104h; cchDest
0x180014a8a  call    StringCchCatW
0x180014a8f  test    eax, eax
0x180014a91  js      short loc_180014A74
0x180014a93  test    byte ptr cs:xmmword_1800616A0, 10h
0x180014a9a  jz      short loc_180014AB7
0x180014a9c  mov     edx, 0Bh
0x180014aa1  lea     r9, [rsp+248h+Buffer]
0x180014aa6  mov     ecx, 404h
0x180014aab  lea     r8, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids
0x180014ab2  call    WPP_SF_S
0x180014ab7  lea     rcx, [rsp+248h+Buffer]; lpFileName
0x180014abc  call    cs:__imp_GetFileAttributesW
0x180014ac2  cmp     eax, 0FFFFFFFFh
0x180014ac5  jz      short loc_180014A52
0x180014ac7  xor     eax, eax
0x180014ac9  lea     ebx, [rax+1]
0x180014acc  test    byte ptr cs:xmmword_1800616A0, 10h
0x180014ad3  jz      short loc_180014AEE
0x180014ad5  mov     edx, 0Ch
0x180014ada  lea     r8, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids
0x180014ae1  mov     ecx, 404h
0x180014ae6  mov     r9d, eax
0x180014ae9  call    WPP_SF_D
0x180014aee  mov     eax, ebx
0x180014af0  mov     rcx, [rsp+248h+var_18]
0x180014af8  xor     rcx, rsp; StackCookie
0x180014afb  call    __security_check_cookie
0x180014b00  mov     rbx, [rsp+248h+arg_8]
0x180014b08  add     rsp, 240h
0x180014b0f  pop     rdi
0x180014b10  retn
```
