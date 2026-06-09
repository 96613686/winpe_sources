# GetDefaultDir

- ea: `0x1800bc604`
- end: `0x1800bc6cf`
- name: `GetDefaultDir`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800bcad0`

## callees

- `0x1800203dc`
- `0x18002c3a4`
- `0x18008d814`
- `0x1800bc604`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bc690`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bc690`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800bc634`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800bc634`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800bc66f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800bc66f`

## pseudocode

```c
__int64 GetDefaultDir()
{
  DWORD FileAttributesW; // eax
  size_t v1; // rbx
  wchar_t *v2; // rax
  __int64 v3; // r11
  size_t pcchLength[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  pcchLength[0] = 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return 0;
  if ( StringCchCatW(Buffer, 0x104u, L"\\Tracing") < 0 )
    return 0;
  if ( StringCchLengthW(Buffer, 0x104u, pcchLength) < 0 )
    return 0;
  FileAttributesW = GetFileAttributesW(Buffer);
  if ( FileAttributesW == -1 )
    return 0;
  if ( (FileAttributesW & 0x10) == 0 )
    return 0;
  v1 = pcchLength[0];
  v2 = (wchar_t *)LocalAlloc(0x40u, 2 * pcchLength[0] + 2);
  if ( !v2 )
    return 0;
  StringCchCopyW(v2, v1 + 1, Buffer);
  return v3;
}

```

## disassembly

```asm
0x1800bc604  push    rbx
0x1800bc606  sub     rsp, 250h
0x1800bc60d  mov     rax, cs:__security_cookie
0x1800bc614  xor     rax, rsp
0x1800bc617  mov     [rsp+258h+var_18], rax
0x1800bc61f  mov     ebx, 104h
0x1800bc624  mov     [rsp+258h+pcchLength], 0
0x1800bc62d  mov     edx, ebx; uSize
0x1800bc62f  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800bc634  call    cs:__imp_GetWindowsDirectoryW
0x1800bc63a  test    eax, eax
0x1800bc63c  jz      short loc_1800BC6B4
0x1800bc63e  lea     r8, aTracing; "\\Tracing"
0x1800bc645  mov     edx, ebx; cchDest
0x1800bc647  lea     rcx, [rsp+258h+Buffer]; pszDest
0x1800bc64c  call    StringCchCatW
0x1800bc651  test    eax, eax
0x1800bc653  js      short loc_1800BC6B4
0x1800bc655  lea     r8, [rsp+258h+pcchLength]; pcchLength
0x1800bc65a  mov     edx, ebx; cchMax
0x1800bc65c  lea     rcx, [rsp+258h+Buffer]; psz
0x1800bc661  call    StringCchLengthW
0x1800bc666  test    eax, eax
0x1800bc668  js      short loc_1800BC6B4
0x1800bc66a  lea     rcx, [rsp+258h+Buffer]; lpFileName
0x1800bc66f  call    cs:__imp_GetFileAttributesW
0x1800bc675  cmp     eax, 0FFFFFFFFh
0x1800bc678  jz      short loc_1800BC6B4
0x1800bc67a  test    al, 10h
0x1800bc67c  jz      short loc_1800BC6B4
0x1800bc67e  mov     rbx, [rsp+258h+pcchLength]
0x1800bc683  mov     ecx, 40h ; '@'; uFlags
0x1800bc688  lea     rdx, ds:2[rbx*2]; uBytes
0x1800bc690  call    cs:__imp_LocalAlloc
0x1800bc696  mov     r11, rax
0x1800bc699  test    rax, rax
0x1800bc69c  jz      short loc_1800BC6B4
0x1800bc69e  lea     rdx, [rbx+1]; cchDest
0x1800bc6a2  mov     rcx, rax; pszDest
0x1800bc6a5  lea     r8, [rsp+258h+Buffer]; pszSrc
0x1800bc6aa  call    StringCchCopyW
0x1800bc6af  mov     rax, r11
0x1800bc6b2  jmp     short loc_1800BC6B6
0x1800bc6b4  xor     eax, eax
0x1800bc6b6  mov     rcx, [rsp+258h+var_18]
0x1800bc6be  xor     rcx, rsp; StackCookie
0x1800bc6c1  call    __security_check_cookie
0x1800bc6c6  add     rsp, 250h
0x1800bc6cd  pop     rbx
0x1800bc6ce  retn
```
