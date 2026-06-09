# ConstructLogPaths

- ea: `0x18003d01c`
- end: `0x18003d26a`
- name: `ConstructLogPaths`
- size: `590`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18003d768`

## callees

- `0x180003166`
- `0x180003172`
- `0x180003270`
- `0x180003288`
- `0x1800032b8`
- `0x18003d01c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003d1cb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003d1cb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003d04d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003d0b5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003d04d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003d0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d05f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d05f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1b3`

## pseudocode

```c
__int64 __fastcall ConstructLogPaths(HANDLE hFile, wchar_t *Source, _QWORD *a3)
{
  void *v3; // rsi
  void *v4; // rdi
  _QWORD *v5; // r13
  DWORD FinalPathNameByHandleW; // eax
  __int64 v9; // rbx
  DWORD LastError; // ebx
  WCHAR *v11; // rax
  WCHAR *v12; // rbp
  DWORD v13; // eax
  size_t v14; // r14
  void *v15; // rax
  rsize_t v16; // rbx
  size_t v17; // r12
  WCHAR *v18; // rax

  v3 = 0;
  v4 = 0;
  v5 = a3;
  if ( Source )
  {
    v14 = wcsnlen(Source, 0x100u);
    v17 = 2 * v14 + 2;
    v18 = (WCHAR *)o__aligned_malloc_0(v17, 0x10u);
    v12 = v18;
    if ( !v18 )
      return 8;
    memset_0(v18, 0, v17);
    if ( (unsigned int)o_wcsncpy_s_0(v12, v17 >> 1, Source, v14) )
    {
LABEL_20:
      LastError = 1359;
      goto LABEL_22;
    }
  }
  else
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
    v9 = FinalPathNameByHandleW;
    if ( !FinalPathNameByHandleW )
      return GetLastError();
    v11 = (WCHAR *)o__aligned_malloc_0(2LL * FinalPathNameByHandleW, 0x10u);
    v12 = v11;
    if ( !v11 )
      return 8;
    memset_0(v11, 0, 2 * v9);
    v13 = GetFinalPathNameByHandleW(hFile, v12, v9, 0);
    if ( !v13 || v13 + 1 != (_DWORD)v9 )
      goto LABEL_17;
    v5 = a3;
    v14 = v9 - 1;
  }
  if ( !v14 )
  {
LABEL_17:
    LastError = GetLastError();
    goto LABEL_22;
  }
  v3 = o__aligned_malloc_0(2 * v14 + 12, 0x10u);
  v15 = o__aligned_malloc_0(2 * v14 + 12, 0x10u);
  v4 = v15;
  if ( !v3 || !v15 )
  {
    LastError = 8;
    goto LABEL_22;
  }
  memset_0(v3, 0, 2 * v14 + 12);
  memset_0(v4, 0, 2 * v14 + 12);
  v16 = (2 * v14 + 12) >> 1;
  if ( (unsigned int)o_wcsncpy_s_0(v3, v16, v12, v14)
    || wcscat_s((wchar_t *)v3, v16, L".LOG1")
    || (unsigned int)o_wcsncpy_s_0(v4, v16, v12, v14)
    || wcscat_s((wchar_t *)v4, v16, L".LOG2") )
  {
    goto LABEL_20;
  }
  *v5 = v3;
  v3 = 0;
  v5[1] = v4;
  v4 = 0;
  LastError = 0;
LABEL_22:
  aligned_free(v12);
  if ( v3 )
    aligned_free(v3);
  if ( v4 )
    aligned_free(v4);
  return LastError;
}

```

## disassembly

```asm
0x18003d01c  mov     [rsp+arg_10], r8
0x18003d021  push    rbx
0x18003d022  push    rbp
0x18003d023  push    rsi
0x18003d024  push    rdi
0x18003d025  push    r12
0x18003d027  push    r13
0x18003d029  push    r14
0x18003d02b  push    r15
0x18003d02d  sub     rsp, 28h
0x18003d031  xor     esi, esi
0x18003d033  xor     edi, edi
0x18003d035  mov     r13, r8
0x18003d038  mov     rbx, rdx
0x18003d03b  mov     r12, rcx
0x18003d03e  test    rdx, rdx
0x18003d041  jnz     loc_18003D1C3
0x18003d047  xor     r9d, r9d; dwFlags
0x18003d04a  xor     r8d, r8d; cchFilePath
0x18003d04d  call    cs:__imp_GetFinalPathNameByHandleW
0x18003d054  nop     dword ptr [rax+rax+00h]
0x18003d059  mov     ebx, eax
0x18003d05b  test    eax, eax
0x18003d05d  jnz     short loc_18003D072
0x18003d05f  call    cs:__imp_GetLastError
0x18003d066  nop     dword ptr [rax+rax+00h]
0x18003d06b  mov     ebx, eax
0x18003d06d  jmp     loc_18003D256
0x18003d072  lea     r13, [rbx+rbx]
0x18003d076  mov     r15d, 10h
0x18003d07c  mov     edx, r15d; Alignment
0x18003d07f  mov     rcx, r13; Size
0x18003d082  mov     r14, rbx
0x18003d085  call    _o__aligned_malloc_0
0x18003d08a  mov     rbp, rax
0x18003d08d  test    rax, rax
0x18003d090  jnz     short loc_18003D09C
0x18003d092  mov     ebx, 8
0x18003d097  jmp     loc_18003D256
0x18003d09c  mov     r8, r13; Size
0x18003d09f  xor     edx, edx; Val
0x18003d0a1  mov     rcx, rbp; void *
0x18003d0a4  call    memset_0
0x18003d0a9  xor     r9d, r9d; dwFlags
0x18003d0ac  mov     r8d, ebx; cchFilePath
0x18003d0af  mov     rdx, rbp; lpszFilePath
0x18003d0b2  mov     rcx, r12; hFile
0x18003d0b5  call    cs:__imp_GetFinalPathNameByHandleW
0x18003d0bc  nop     dword ptr [rax+rax+00h]
0x18003d0c1  test    eax, eax
0x18003d0c3  jz      loc_18003D1B3
0x18003d0c9  inc     eax
0x18003d0cb  cmp     eax, ebx
0x18003d0cd  jnz     loc_18003D1B3
0x18003d0d3  mov     r13, [rsp+68h+arg_10]
0x18003d0db  dec     r14
0x18003d0de  test    r14, r14
0x18003d0e1  jz      loc_18003D1B3
0x18003d0e7  lea     rbx, ds:0Ch[r14*2]
0x18003d0ef  mov     rdx, r15; Alignment
0x18003d0f2  mov     rcx, rbx; Size
0x18003d0f5  call    _o__aligned_malloc_0
0x18003d0fa  mov     rdx, r15; Alignment
0x18003d0fd  mov     rcx, rbx; Size
0x18003d100  mov     rsi, rax
0x18003d103  call    _o__aligned_malloc_0
0x18003d108  mov     rdi, rax
0x18003d10b  test    rsi, rsi
0x18003d10e  jz      loc_18003D22F
0x18003d114  test    rax, rax
0x18003d117  jz      loc_18003D22F
0x18003d11d  mov     r8, rbx; Size
0x18003d120  xor     edx, edx; Val
0x18003d122  mov     rcx, rsi; void *
0x18003d125  call    memset_0
0x18003d12a  mov     r8, rbx; Size
0x18003d12d  xor     edx, edx; Val
0x18003d12f  mov     rcx, rdi; void *
0x18003d132  call    memset_0
0x18003d137  shr     rbx, 1
0x18003d13a  mov     r9, r14
0x18003d13d  mov     rdx, rbx
0x18003d140  mov     r8, rbp
0x18003d143  mov     rcx, rsi
0x18003d146  call    _o_wcsncpy_s_0
0x18003d14b  test    eax, eax
0x18003d14d  jnz     loc_18003D228
0x18003d153  lea     r8, aLog1; ".LOG1"
0x18003d15a  mov     rdx, rbx; SizeInWords
0x18003d15d  mov     rcx, rsi; Destination
0x18003d160  call    wcscat_s
0x18003d165  test    eax, eax
0x18003d167  jnz     loc_18003D228
0x18003d16d  mov     r9, r14
0x18003d170  mov     r8, rbp
0x18003d173  mov     rdx, rbx
0x18003d176  mov     rcx, rdi
0x18003d179  call    _o_wcsncpy_s_0
0x18003d17e  test    eax, eax
0x18003d180  jnz     loc_18003D228
0x18003d186  lea     r8, aLog2; ".LOG2"
0x18003d18d  mov     rdx, rbx; SizeInWords
0x18003d190  mov     rcx, rdi; Destination
0x18003d193  call    wcscat_s
0x18003d198  test    eax, eax
0x18003d19a  jnz     loc_18003D228
0x18003d1a0  mov     [r13+0], rsi
0x18003d1a4  xor     esi, esi
0x18003d1a6  mov     [r13+8], rdi
0x18003d1aa  xor     edi, edi
0x18003d1ac  xor     ebx, ebx
0x18003d1ae  jmp     loc_18003D234
0x18003d1b3  call    cs:__imp_GetLastError
0x18003d1ba  nop     dword ptr [rax+rax+00h]
0x18003d1bf  mov     ebx, eax
0x18003d1c1  jmp     short loc_18003D234
0x18003d1c3  mov     edx, 100h; MaxCount
0x18003d1c8  mov     rcx, rbx; Source
0x18003d1cb  call    cs:__imp_wcsnlen
0x18003d1d2  nop     dword ptr [rax+rax+00h]
0x18003d1d7  mov     r15d, 10h
0x18003d1dd  mov     r14, rax
0x18003d1e0  mov     edx, r15d; Alignment
0x18003d1e3  lea     r12, ds:2[rax*2]
0x18003d1eb  mov     rcx, r12; Size
0x18003d1ee  call    _o__aligned_malloc_0
0x18003d1f3  mov     rbp, rax
0x18003d1f6  test    rax, rax
0x18003d1f9  jz      loc_18003D092
0x18003d1ff  mov     r8, r12; Size
0x18003d202  xor     edx, edx; Val
0x18003d204  mov     rcx, rax; void *
0x18003d207  call    memset_0
0x18003d20c  shr     r12, 1
0x18003d20f  mov     r9, r14
0x18003d212  mov     rdx, r12
0x18003d215  mov     r8, rbx
0x18003d218  mov     rcx, rbp
0x18003d21b  call    _o_wcsncpy_s_0
0x18003d220  test    eax, eax
0x18003d222  jz      loc_18003D0DE
0x18003d228  mov     ebx, 54Fh
0x18003d22d  jmp     short loc_18003D234
0x18003d22f  mov     ebx, 8
0x18003d234  mov     rcx, rbp; Block
0x18003d237  call    _aligned_free
0x18003d23c  test    rsi, rsi
0x18003d23f  jz      short loc_18003D249
0x18003d241  mov     rcx, rsi; Block
0x18003d244  call    _aligned_free
0x18003d249  test    rdi, rdi
0x18003d24c  jz      short loc_18003D256
0x18003d24e  mov     rcx, rdi; Block
0x18003d251  call    _aligned_free
0x18003d256  mov     eax, ebx
0x18003d258  add     rsp, 28h
0x18003d25c  pop     r15
0x18003d25e  pop     r14
0x18003d260  pop     r13
0x18003d262  pop     r12
0x18003d264  pop     rdi
0x18003d265  pop     rsi
0x18003d266  pop     rbp
0x18003d267  pop     rbx
0x18003d268  retn
```
