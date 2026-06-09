# VerifySameInf

- ea: `0x180023a98`
- end: `0x180023ca5`
- name: `VerifySameInf`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002354c`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180012b28`
- `0x18001e8b0`
- `0x180020998`
- `0x180023a98`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180023bf9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180023bf9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180023b46`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180023b46`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180023c6c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180023c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c4e`

## pseudocode

```c
__int64 __fastcall VerifySameInf(
        unsigned int a1,
        WCHAR *a2,
        int a3,
        __int64 a4,
        FILETIME FileTime1,
        __int64 a6,
        __int64 a7,
        int *a8)
{
  int *v8; // r12
  __int64 v13; // rsi
  int IsPackageAware; // ebx
  int v15; // edi
  HANDLE FirstFileW; // r15
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  v8 = a8;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !(unsigned int)ValidPlatform(a1) || !a2 || !a3 || !a4 || (v13 = a7) == 0 || !v8 )
    return (unsigned int)-2147024809;
  IsPackageAware = 0;
  *v8 = 0;
  v15 = 0;
  FirstFileW = FindFirstFileW(a2, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL
    && *(_DWORD *)(v13 + 28) == FindFileData.nFileSizeHigh
    && *(_DWORD *)(v13 + 32) == FindFileData.nFileSizeLow )
  {
    IsPackageAware = InfFileIsPackageAware(a2);
    if ( IsPackageAware < 0 )
    {
LABEL_13:
      FindClose(FirstFileW);
      return (unsigned int)IsPackageAware;
    }
    v15 = 1;
  }
  *v8 = v15;
  if ( FirstFileW != (HANDLE)-1LL )
    goto LABEL_13;
  return (unsigned int)IsPackageAware;
}

```

## disassembly

```asm
0x180023a98  mov     [rsp-8+arg_10], rbx
0x180023a9d  push    rbp
0x180023a9e  push    rsi
0x180023a9f  push    rdi
0x180023aa0  push    r12
0x180023aa2  push    r13
0x180023aa4  push    r14
0x180023aa6  push    r15
0x180023aa8  lea     rbp, [rsp-1C0h]
0x180023ab0  sub     rsp, 2C0h
0x180023ab7  mov     rax, cs:__security_cookie
0x180023abe  xor     rax, rsp
0x180023ac1  mov     [rbp+1F0h+var_40], rax
0x180023ac8  mov     r12, [rbp+1F0h+arg_38]
0x180023acf  mov     ebx, r8d
0x180023ad2  mov     r14, rdx
0x180023ad5  mov     [rsp+2F0h+var_2C0], ecx
0x180023ad9  mov     edi, ecx
0x180023adb  mov     [rsp+2F0h+var_2B8], ebx
0x180023adf  xor     edx, edx; Val
0x180023ae1  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x180023ae6  mov     r8d, 250h; Size
0x180023aec  mov     r13, r9
0x180023aef  call    memset_0
0x180023af4  mov     ecx, edi
0x180023af6  call    ValidPlatform
0x180023afb  test    eax, eax
0x180023afd  jz      loc_180023C74
0x180023b03  test    r14, r14
0x180023b06  jz      loc_180023C74
0x180023b0c  test    ebx, ebx
0x180023b0e  jz      loc_180023C74
0x180023b14  test    r13, r13
0x180023b17  jz      loc_180023C74
0x180023b1d  mov     rsi, [rbp+1F0h+arg_30]
0x180023b24  test    rsi, rsi
0x180023b27  jz      loc_180023C74
0x180023b2d  test    r12, r12
0x180023b30  jz      loc_180023C74
0x180023b36  xor     ebx, ebx
0x180023b38  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180023b3d  mov     rcx, r14; lpFileName
0x180023b40  mov     [r12], ebx
0x180023b44  xor     edi, edi
0x180023b46  call    cs:__imp_FindFirstFileW
0x180023b4c  mov     r15, rax
0x180023b4f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023b53  jz      loc_180023C5F
0x180023b59  mov     ecx, [rsp+2F0h+FindFileData.nFileSizeHigh]
0x180023b5d  cmp     [rsi+1Ch], ecx
0x180023b60  jnz     loc_180023C5F
0x180023b66  mov     ecx, [rbp+1F0h+FindFileData.nFileSizeLow]
0x180023b69  cmp     [rsi+20h], ecx
0x180023b6c  jnz     loc_180023C5F
0x180023b72  mov     esi, [rsp+2F0h+var_2C0]
0x180023b76  lea     r8, [rsp+2F0h+var_2BC]
0x180023b7b  mov     edx, esi
0x180023b7d  mov     [rsp+2F0h+var_2BC], ebx
0x180023b81  mov     rcx, r14; unsigned __int16 *
0x180023b84  call    InfFileIsPackageAware
0x180023b89  mov     ebx, eax
0x180023b8b  xor     eax, eax
0x180023b8d  test    ebx, ebx
0x180023b8f  js      loc_180023C69
0x180023b95  cmp     [rsp+2F0h+var_2BC], eax
0x180023b99  jz      loc_180023C5A
0x180023b9f  mov     qword ptr [rsp+2F0h+FileTime2.dwLowDateTime], rax
0x180023ba4  lea     r9, [rsp+2F0h+hMem]
0x180023ba9  mov     [rsp+2F0h+var_2A0], rax
0x180023bae  lea     r8, [rsp+2F0h+var_2C0]
0x180023bb3  mov     [rsp+2F0h+var_2C0], eax
0x180023bb7  mov     edx, esi
0x180023bb9  mov     [rsp+2F0h+hMem], rax
0x180023bbe  mov     rcx, r14; unsigned __int16 *
0x180023bc1  lea     rax, [rsp+2F0h+var_2A0]
0x180023bc6  mov     [rsp+2F0h+var_2C8], rax; unsigned __int64 *
0x180023bcb  lea     rax, [rsp+2F0h+FileTime2]
0x180023bd0  mov     [rsp+2F0h+var_2D0], rax; struct _FILETIME *
0x180023bd5  call    ObtainPackageInfInfo
0x180023bda  mov     r14d, [rsp+2F0h+var_2B8]
0x180023bdf  mov     ebx, eax
0x180023be1  mov     rsi, [rsp+2F0h+hMem]
0x180023be6  cmp     r14d, [rsp+2F0h+var_2C0]
0x180023beb  jnz     short loc_180023C46
0x180023bed  lea     rdx, [rsp+2F0h+FileTime2]; lpFileTime2
0x180023bf2  lea     rcx, [rbp+1F0h+FileTime1]; lpFileTime1
0x180023bf9  call    cs:__imp_CompareFileTime
0x180023bff  test    eax, eax
0x180023c01  jnz     short loc_180023C46
0x180023c03  mov     rax, [rsp+2F0h+var_2A0]
0x180023c08  cmp     [rbp+1F0h+arg_28], rax
0x180023c0f  jnz     short loc_180023C46
0x180023c11  mov     edi, 1
0x180023c16  xor     edx, edx
0x180023c18  cmp     edx, r14d
0x180023c1b  jnb     short loc_180023C46
0x180023c1d  mov     ecx, edx
0x180023c1f  shl     rcx, 4
0x180023c23  mov     rax, [rcx+r13]
0x180023c27  sub     rax, [rcx+rsi]
0x180023c2b  jnz     short loc_180023C37
0x180023c2d  mov     rax, [rcx+r13+8]
0x180023c32  sub     rax, [rcx+rsi+8]
0x180023c37  xor     edi, edi
0x180023c39  test    rax, rax
0x180023c3c  setz    dil
0x180023c40  inc     edx
0x180023c42  test    edi, edi
0x180023c44  jnz     short loc_180023C18
0x180023c46  test    rsi, rsi
0x180023c49  jz      short loc_180023C54
0x180023c4b  mov     rcx, rsi; hMem
0x180023c4e  call    cs:__imp_LocalFree
0x180023c54  test    ebx, ebx
0x180023c56  js      short loc_180023C69
0x180023c58  jmp     short loc_180023C5F
0x180023c5a  mov     edi, 1
0x180023c5f  mov     [r12], edi
0x180023c63  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180023c67  jz      short loc_180023C79
0x180023c69  mov     rcx, r15; hFindFile
0x180023c6c  call    cs:__imp_FindClose
0x180023c72  jmp     short loc_180023C79
0x180023c74  mov     ebx, 80070057h
0x180023c79  mov     eax, ebx
0x180023c7b  mov     rcx, [rbp+1F0h+var_40]
0x180023c82  xor     rcx, rsp; StackCookie
0x180023c85  call    __security_check_cookie
0x180023c8a  mov     rbx, [rsp+2F0h+arg_10]
0x180023c92  add     rsp, 2C0h
0x180023c99  pop     r15
0x180023c9b  pop     r14
0x180023c9d  pop     r13
0x180023c9f  pop     r12
0x180023ca1  pop     rdi
0x180023ca2  pop     rsi
0x180023ca3  pop     rbp
0x180023ca4  retn
```
