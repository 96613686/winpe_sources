# StgIsStorageFileHandle

- ea: `0x180033ec0`
- end: `0x180033fe2`
- name: `StgIsStorageFileHandle`
- size: `290`
- prototype: `__int64 __fastcall(HANDLE hFile, LPOVERLAPPED lpOverlapped)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180027350`
- `0x1800338dc`
- `0x18004fdec`

## callees

- `0x180033ec0`
- `0x180042800`
- `0x180061410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fc9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033f29`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033f29`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180033fbb`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180033fbb`

## pseudocode

```c
signed int __fastcall StgIsStorageFileHandle(HANDLE hFile, LPOVERLAPPED lpOverlapped)
{
  __m128i si128; // xmm1
  struct _OVERLAPPED *v3; // rax
  signed int result; // eax
  bool v7; // sf
  DWORD NumberOfBytesTransferred; // [rsp+30h] [rbp-58h] BYREF
  _OWORD v9[2]; // [rsp+38h] [rbp-50h] BYREF
  __m128i Buf1; // [rsp+58h] [rbp-30h] BYREF
  __int64 v11; // [rsp+68h] [rbp-20h]

  si128 = _mm_load_si128((const __m128i *)&_xmm_dededededededededededededededede);
  v3 = (struct _OVERLAPPED *)v9;
  NumberOfBytesTransferred = 0;
  v11 = si128.m128i_i64[0];
  if ( lpOverlapped )
    v3 = lpOverlapped;
  memset(v9, 0, sizeof(v9));
  Buf1 = si128;
  if ( ReadFile(hFile, &Buf1, 0x18u, &NumberOfBytesTransferred, v3) )
    goto LABEL_4;
  if ( !lpOverlapped )
    return 1;
  result = GetLastError();
  if ( result == 997 )
  {
    if ( GetOverlappedResult(hFile, lpOverlapped, &NumberOfBytesTransferred, 1) )
    {
LABEL_4:
      result = memcmp_0(&Buf1, &qword_180066818, 8u) != 0 ? 0x800300FB : 0;
      goto LABEL_5;
    }
    result = GetLastError();
  }
  if ( !result || result == 38 )
    goto LABEL_4;
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
    goto LABEL_4;
LABEL_5:
  if ( result == -2147286780 || result == -2147286789 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180033ec0  mov     r11, rsp
0x180033ec3  mov     [r11+18h], rbx
0x180033ec7  push    rdi
0x180033ec8  sub     rsp, 80h
0x180033ecf  mov     rax, cs:__security_cookie
0x180033ed6  xor     rax, rsp
0x180033ed9  mov     [rsp+88h+var_18], rax
0x180033ede  movdqa  xmm1, cs:__xmm@dededededededededededededededede
0x180033ee6  lea     rax, [r11-50h]
0x180033eea  test    rdx, rdx
0x180033eed  mov     [rsp+88h+NumberOfBytesTransferred], 0
0x180033ef5  xorps   xmm0, xmm0
0x180033ef8  movq    [rsp+88h+var_20], xmm1
0x180033efe  cmovnz  rax, rdx
0x180033f02  lea     r9, [r11-58h]; lpNumberOfBytesRead
0x180033f06  mov     rbx, rdx
0x180033f09  mov     [r11-68h], rax
0x180033f0d  lea     rdx, [r11-30h]; lpBuffer
0x180033f11  mov     r8d, 18h; nNumberOfBytesToRead
0x180033f17  mov     rdi, rcx
0x180033f1a  movups  [rsp+88h+var_50], xmm0
0x180033f1f  movups  [rsp+88h+var_40], xmm0
0x180033f24  movups  [rsp+88h+Buf1], xmm1
0x180033f29  call    cs:__imp_ReadFile
0x180033f2f  test    eax, eax
0x180033f31  jz      short loc_180033F98
0x180033f33  mov     r8d, 8; Size
0x180033f39  lea     rdx, qword_180066818; Buf2
0x180033f40  lea     rcx, [rsp+88h+Buf1]; Buf1
0x180033f45  call    memcmp_0
0x180033f4a  neg     eax
0x180033f4c  sbb     eax, eax
0x180033f4e  and     eax, 800300FBh
0x180033f53  cmp     eax, 80030104h
0x180033f58  jz      short loc_180033F7F
0x180033f5a  cmp     eax, 800300FBh
0x180033f5f  jz      short loc_180033F7F
0x180033f61  mov     rcx, [rsp+88h+var_18]
0x180033f66  xor     rcx, rsp; StackCookie
0x180033f69  call    __security_check_cookie
0x180033f6e  mov     rbx, [rsp+88h+arg_10]
0x180033f76  add     rsp, 80h
0x180033f7d  pop     rdi
0x180033f7e  retn
0x180033f7f  mov     eax, 1
0x180033f84  jmp     short loc_180033F61
0x180033f86  test    eax, eax
0x180033f88  jle     short loc_180033F94
0x180033f8a  movzx   eax, ax
0x180033f8d  or      eax, 80070000h
0x180033f92  test    eax, eax
0x180033f94  js      short loc_180033F53
0x180033f96  jmp     short loc_180033F33
0x180033f98  test    rbx, rbx
0x180033f9b  jz      short loc_180033F7F
0x180033f9d  call    cs:__imp_GetLastError
0x180033fa3  cmp     eax, 3E5h
0x180033fa8  jnz     short loc_180033FCF
0x180033faa  mov     r9d, 1; bWait
0x180033fb0  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180033fb5  mov     rdx, rbx; lpOverlapped
0x180033fb8  mov     rcx, rdi; hFile
0x180033fbb  call    cs:__imp_GetOverlappedResult
0x180033fc1  test    eax, eax
0x180033fc3  jnz     loc_180033F33
0x180033fc9  call    cs:__imp_GetLastError
0x180033fcf  test    eax, eax
0x180033fd1  jz      loc_180033F33
0x180033fd7  cmp     eax, 26h ; '&'
0x180033fda  jz      loc_180033F33
0x180033fe0  jmp     short loc_180033F86
```
