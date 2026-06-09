# PkgDefIO::CPkgDefFileWriter::WriteCharBuffer(ushort const *,int)

- ea: `0x1400611cc`
- end: `0x140061340`
- name: `?WriteCharBuffer@CPkgDefFileWriter@PkgDefIO@@IEAAJPEBGH@Z`
- size: `372`
- prototype: `int(PkgDefIO::CPkgDefFileWriter *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140061340`
- `0x1400617ac`

## callees

- `0x140001020`
- `0x140002190`
- `0x14000fea0`
- `0x1400344fc`
- `0x1400611cc`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140061254`
- `KERNEL32!WideCharToMultiByte` at `0x1400612a3`
- `KERNEL32!WideCharToMultiByte` at `0x1400612df`
- `KERNEL32!WideCharToMultiByte` at `0x140061254`
- `KERNEL32!WideCharToMultiByte` at `0x1400612a3`
- `KERNEL32!WideCharToMultiByte` at `0x1400612df`
- `KERNEL32!WriteFile` at `0x1400612ff`
- `KERNEL32!WriteFile` at `0x1400612ff`
- `KERNEL32!GetLastError` at `0x140061264`
- `KERNEL32!GetLastError` at `0x140061264`

## pseudocode

```c
__int64 __fastcall PkgDefIO::CPkgDefFileWriter::WriteCharBuffer(HANDLE *this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rsi
  int cbMultiByte; // edi
  CHAR *lpMultiByteStr; // rbx
  DWORD Error; // edi
  signed int LastError; // eax
  const struct std::nothrow_t *v11; // rdx
  unsigned __int64 v12; // rdi
  const struct std::nothrow_t *v13; // rdx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-38h] BYREF

  LODWORD(v3) = a3;
  if ( a3 < 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
  }
  if ( !(_DWORD)v3 )
    return 0;
  cbMultiByte = (int)((double)(int)v3 * 1.5);
  lpMultiByteStr = (CHAR *)operator new[](cbMultiByte);
  Error = WideCharToMultiByte(0xFDE9u, 0, a2, v3, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( Error )
    goto LABEL_18;
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    Error = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      Error = LastError;
    goto LABEL_15;
  }
  v12 = WideCharToMultiByte(0xFDE9u, 0, a2, v3, 0, 0, 0, 0);
  operator delete(lpMultiByteStr, v13);
  lpMultiByteStr = (CHAR *)operator new[](v12);
  Error = WideCharToMultiByte(0xFDE9u, 0, a2, v3, lpMultiByteStr, v12, 0, 0);
  if ( Error )
  {
LABEL_18:
    if ( WriteFile(this[1], lpMultiByteStr, Error, &NumberOfBytesWritten, 0) )
      Error = 0;
    else
      Error = ATL::AtlHresultFromLastError();
  }
LABEL_15:
  operator delete(lpMultiByteStr, v11);
  return Error;
}

```

## disassembly

```asm
0x1400611cc  mov     [rsp+arg_18], rbx
0x1400611d1  push    rbp
0x1400611d2  push    rsi
0x1400611d3  push    rdi
0x1400611d4  push    r14
0x1400611d6  push    r15
0x1400611d8  sub     rsp, 50h
0x1400611dc  mov     rax, cs:__security_cookie
0x1400611e3  xor     rax, rsp
0x1400611e6  mov     [rsp+78h+var_30], rax
0x1400611eb  xor     r15d, r15d
0x1400611ee  mov     esi, r8d
0x1400611f1  mov     rbp, rdx
0x1400611f4  mov     r14, rcx
0x1400611f7  test    r8d, r8d
0x1400611fa  jns     short loc_14006120A
0x1400611fc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140061200  inc     rsi
0x140061203  cmp     [rdx+rsi*2], r15w
0x140061208  jnz     short loc_140061200
0x14006120a  test    esi, esi
0x14006120c  jnz     short loc_140061215
0x14006120e  xor     eax, eax
0x140061210  jmp     loc_14006131F
0x140061215  movd    xmm0, esi
0x140061219  cvtdq2pd xmm0, xmm0
0x14006121d  mulsd   xmm0, cs:__real@3ff8000000000000
0x140061225  cvttsd2si edi, xmm0
0x140061229  movsxd  rcx, edi; unsigned __int64
0x14006122c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140061231  mov     [rsp+78h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x140061236  mov     r9d, esi; cchWideChar
0x140061239  mov     [rsp+78h+lpDefaultChar], r15; lpDefaultChar
0x14006123e  mov     r8, rbp; lpWideCharStr
0x140061241  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x140061245  xor     edx, edx; dwFlags
0x140061247  mov     ecx, 0FDE9h; CodePage
0x14006124c  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x140061251  mov     rbx, rax
0x140061254  call    cs:__imp_WideCharToMultiByte
0x14006125a  mov     edi, eax
0x14006125c  test    eax, eax
0x14006125e  jnz     loc_1400612EB
0x140061264  call    cs:__imp_GetLastError
0x14006126a  cmp     eax, 7Ah ; 'z'
0x14006126d  jz      short loc_140061282
0x14006126f  movzx   edi, ax
0x140061272  or      edi, 80070000h
0x140061278  test    eax, eax
0x14006127a  cmovle  edi, eax
0x14006127d  jmp     loc_140061315
0x140061282  mov     [rsp+78h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x140061287  mov     r9d, esi; cchWideChar
0x14006128a  mov     [rsp+78h+lpDefaultChar], r15; lpDefaultChar
0x14006128f  mov     r8, rbp; lpWideCharStr
0x140061292  mov     [rsp+78h+cbMultiByte], r15d; cbMultiByte
0x140061297  xor     edx, edx; dwFlags
0x140061299  mov     ecx, 0FDE9h; CodePage
0x14006129e  mov     [rsp+78h+lpMultiByteStr], r15; lpMultiByteStr
0x1400612a3  call    cs:__imp_WideCharToMultiByte
0x1400612a9  mov     rcx, rbx; void *
0x1400612ac  movsxd  rdi, eax
0x1400612af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400612b4  mov     rcx, rdi; unsigned __int64
0x1400612b7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400612bc  mov     [rsp+78h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1400612c1  mov     r9d, esi; cchWideChar
0x1400612c4  mov     [rsp+78h+lpDefaultChar], r15; lpDefaultChar
0x1400612c9  mov     r8, rbp; lpWideCharStr
0x1400612cc  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x1400612d0  xor     edx, edx; dwFlags
0x1400612d2  mov     ecx, 0FDE9h; CodePage
0x1400612d7  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x1400612dc  mov     rbx, rax
0x1400612df  call    cs:__imp_WideCharToMultiByte
0x1400612e5  mov     edi, eax
0x1400612e7  test    eax, eax
0x1400612e9  jz      short loc_140061315
0x1400612eb  mov     rcx, [r14+8]; hFile
0x1400612ef  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400612f4  mov     r8d, edi; nNumberOfBytesToWrite
0x1400612f7  mov     [rsp+78h+lpMultiByteStr], r15; lpOverlapped
0x1400612fc  mov     rdx, rbx; lpBuffer
0x1400612ff  call    cs:__imp_WriteFile
0x140061305  test    eax, eax
0x140061307  jnz     short loc_140061312
0x140061309  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14006130e  mov     edi, eax
0x140061310  jmp     short loc_140061315
0x140061312  mov     edi, r15d
0x140061315  mov     rcx, rbx; void *
0x140061318  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006131d  mov     eax, edi
0x14006131f  mov     rcx, [rsp+78h+var_30]
0x140061324  xor     rcx, rsp; StackCookie
0x140061327  call    __security_check_cookie
0x14006132c  mov     rbx, [rsp+78h+arg_18]
0x140061334  add     rsp, 50h
0x140061338  pop     r15
0x14006133a  pop     r14
0x14006133c  pop     rdi
0x14006133d  pop     rsi
0x14006133e  pop     rbp
0x14006133f  retn
```
