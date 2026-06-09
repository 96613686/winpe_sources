# ConstructLogPaths

- ea: `0x1800a62b0`
- end: `0x1800a64fe`
- name: `ConstructLogPaths`
- size: `590`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1800a6a08`

## callees

- `0x180005886`
- `0x180005892`
- `0x18000596c`
- `0x180005978`
- `0x1800059a8`
- `0x1800a62b0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a645f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a645f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a62f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a62f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6447`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a62e1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a6349`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a62e1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a6349`

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
    if ( (unsigned int)o_wcsncpy_s_0(v12, v17 >> 1, Source) )
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
  if ( (unsigned int)o_wcsncpy_s_0(v3, v16, v12)
    || wcscat_s((wchar_t *)v3, v16, L".LOG1")
    || (unsigned int)o_wcsncpy_s_0(v4, v16, v12)
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
0x1800a62b0  mov     [rsp+arg_10], r8
0x1800a62b5  push    rbx
0x1800a62b6  push    rbp
0x1800a62b7  push    rsi
0x1800a62b8  push    rdi
0x1800a62b9  push    r12
0x1800a62bb  push    r13
0x1800a62bd  push    r14
0x1800a62bf  push    r15
0x1800a62c1  sub     rsp, 28h
0x1800a62c5  xor     esi, esi
0x1800a62c7  xor     edi, edi
0x1800a62c9  mov     r13, r8
0x1800a62cc  mov     rbx, rdx
0x1800a62cf  mov     r12, rcx
0x1800a62d2  test    rdx, rdx
0x1800a62d5  jnz     loc_1800A6457
0x1800a62db  xor     r9d, r9d; dwFlags
0x1800a62de  xor     r8d, r8d; cchFilePath
0x1800a62e1  call    cs:__imp_GetFinalPathNameByHandleW
0x1800a62e8  nop     dword ptr [rax+rax+00h]
0x1800a62ed  mov     ebx, eax
0x1800a62ef  test    eax, eax
0x1800a62f1  jnz     short loc_1800A6306
0x1800a62f3  call    cs:__imp_GetLastError
0x1800a62fa  nop     dword ptr [rax+rax+00h]
0x1800a62ff  mov     ebx, eax
0x1800a6301  jmp     loc_1800A64EA
0x1800a6306  lea     r13, [rbx+rbx]
0x1800a630a  mov     r15d, 10h
0x1800a6310  mov     edx, r15d; Alignment
0x1800a6313  mov     rcx, r13; Size
0x1800a6316  mov     r14, rbx
0x1800a6319  call    _o__aligned_malloc_0
0x1800a631e  mov     rbp, rax
0x1800a6321  test    rax, rax
0x1800a6324  jnz     short loc_1800A6330
0x1800a6326  mov     ebx, 8
0x1800a632b  jmp     loc_1800A64EA
0x1800a6330  mov     r8, r13; Size
0x1800a6333  xor     edx, edx; Val
0x1800a6335  mov     rcx, rbp; void *
0x1800a6338  call    memset_0
0x1800a633d  xor     r9d, r9d; dwFlags
0x1800a6340  mov     r8d, ebx; cchFilePath
0x1800a6343  mov     rdx, rbp; lpszFilePath
0x1800a6346  mov     rcx, r12; hFile
0x1800a6349  call    cs:__imp_GetFinalPathNameByHandleW
0x1800a6350  nop     dword ptr [rax+rax+00h]
0x1800a6355  test    eax, eax
0x1800a6357  jz      loc_1800A6447
0x1800a635d  inc     eax
0x1800a635f  cmp     eax, ebx
0x1800a6361  jnz     loc_1800A6447
0x1800a6367  mov     r13, [rsp+68h+arg_10]
0x1800a636f  dec     r14
0x1800a6372  test    r14, r14
0x1800a6375  jz      loc_1800A6447
0x1800a637b  lea     rbx, ds:0Ch[r14*2]
0x1800a6383  mov     rdx, r15; Alignment
0x1800a6386  mov     rcx, rbx; Size
0x1800a6389  call    _o__aligned_malloc_0
0x1800a638e  mov     rdx, r15; Alignment
0x1800a6391  mov     rcx, rbx; Size
0x1800a6394  mov     rsi, rax
0x1800a6397  call    _o__aligned_malloc_0
0x1800a639c  mov     rdi, rax
0x1800a639f  test    rsi, rsi
0x1800a63a2  jz      loc_1800A64C3
0x1800a63a8  test    rax, rax
0x1800a63ab  jz      loc_1800A64C3
0x1800a63b1  mov     r8, rbx; Size
0x1800a63b4  xor     edx, edx; Val
0x1800a63b6  mov     rcx, rsi; void *
0x1800a63b9  call    memset_0
0x1800a63be  mov     r8, rbx; Size
0x1800a63c1  xor     edx, edx; Val
0x1800a63c3  mov     rcx, rdi; void *
0x1800a63c6  call    memset_0
0x1800a63cb  shr     rbx, 1
0x1800a63ce  mov     r9, r14
0x1800a63d1  mov     rdx, rbx
0x1800a63d4  mov     r8, rbp
0x1800a63d7  mov     rcx, rsi
0x1800a63da  call    _o_wcsncpy_s_0
0x1800a63df  test    eax, eax
0x1800a63e1  jnz     loc_1800A64BC
0x1800a63e7  lea     r8, aLog1; ".LOG1"
0x1800a63ee  mov     rdx, rbx; SizeInWords
0x1800a63f1  mov     rcx, rsi; Destination
0x1800a63f4  call    wcscat_s
0x1800a63f9  test    eax, eax
0x1800a63fb  jnz     loc_1800A64BC
0x1800a6401  mov     r9, r14
0x1800a6404  mov     r8, rbp
0x1800a6407  mov     rdx, rbx
0x1800a640a  mov     rcx, rdi
0x1800a640d  call    _o_wcsncpy_s_0
0x1800a6412  test    eax, eax
0x1800a6414  jnz     loc_1800A64BC
0x1800a641a  lea     r8, aLog2; ".LOG2"
0x1800a6421  mov     rdx, rbx; SizeInWords
0x1800a6424  mov     rcx, rdi; Destination
0x1800a6427  call    wcscat_s
0x1800a642c  test    eax, eax
0x1800a642e  jnz     loc_1800A64BC
0x1800a6434  mov     [r13+0], rsi
0x1800a6438  xor     esi, esi
0x1800a643a  mov     [r13+8], rdi
0x1800a643e  xor     edi, edi
0x1800a6440  xor     ebx, ebx
0x1800a6442  jmp     loc_1800A64C8
0x1800a6447  call    cs:__imp_GetLastError
0x1800a644e  nop     dword ptr [rax+rax+00h]
0x1800a6453  mov     ebx, eax
0x1800a6455  jmp     short loc_1800A64C8
0x1800a6457  mov     edx, 100h; MaxCount
0x1800a645c  mov     rcx, rbx; Source
0x1800a645f  call    cs:__imp_wcsnlen
0x1800a6466  nop     dword ptr [rax+rax+00h]
0x1800a646b  mov     r15d, 10h
0x1800a6471  mov     r14, rax
0x1800a6474  mov     edx, r15d; Alignment
0x1800a6477  lea     r12, ds:2[rax*2]
0x1800a647f  mov     rcx, r12; Size
0x1800a6482  call    _o__aligned_malloc_0
0x1800a6487  mov     rbp, rax
0x1800a648a  test    rax, rax
0x1800a648d  jz      loc_1800A6326
0x1800a6493  mov     r8, r12; Size
0x1800a6496  xor     edx, edx; Val
0x1800a6498  mov     rcx, rax; void *
0x1800a649b  call    memset_0
0x1800a64a0  shr     r12, 1
0x1800a64a3  mov     r9, r14
0x1800a64a6  mov     rdx, r12
0x1800a64a9  mov     r8, rbx
0x1800a64ac  mov     rcx, rbp
0x1800a64af  call    _o_wcsncpy_s_0
0x1800a64b4  test    eax, eax
0x1800a64b6  jz      loc_1800A6372
0x1800a64bc  mov     ebx, 54Fh
0x1800a64c1  jmp     short loc_1800A64C8
0x1800a64c3  mov     ebx, 8
0x1800a64c8  mov     rcx, rbp; Block
0x1800a64cb  call    _aligned_free
0x1800a64d0  test    rsi, rsi
0x1800a64d3  jz      short loc_1800A64DD
0x1800a64d5  mov     rcx, rsi; Block
0x1800a64d8  call    _aligned_free
0x1800a64dd  test    rdi, rdi
0x1800a64e0  jz      short loc_1800A64EA
0x1800a64e2  mov     rcx, rdi; Block
0x1800a64e5  call    _aligned_free
0x1800a64ea  mov     eax, ebx
0x1800a64ec  add     rsp, 28h
0x1800a64f0  pop     r15
0x1800a64f2  pop     r14
0x1800a64f4  pop     r13
0x1800a64f6  pop     r12
0x1800a64f8  pop     rdi
0x1800a64f9  pop     rsi
0x1800a64fa  pop     rbp
0x1800a64fb  pop     rbx
0x1800a64fc  retn
```
