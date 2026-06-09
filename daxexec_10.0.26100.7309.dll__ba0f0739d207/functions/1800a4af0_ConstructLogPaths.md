# ConstructLogPaths

- ea: `0x1800a4af0`
- end: `0x1800a4d48`
- name: `ConstructLogPaths`
- size: `600`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1800a5284`

## callees

- `0x180006036`
- `0x180006042`
- `0x18000611c`
- `0x180006128`
- `0x180006158`
- `0x1800a4af0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a4c9d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800a4c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4c85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4c85`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a4b28`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a4b8d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a4b28`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a4b8d`

## pseudocode

```c
__int64 __fastcall ConstructLogPaths(HANDLE hFile, wchar_t *Source, _QWORD *a3)
{
  void *v3; // rsi
  void *v4; // rdi
  DWORD FinalPathNameByHandleW; // eax
  __int64 v9; // rbx
  DWORD LastError; // ebx
  WCHAR *v11; // rax
  WCHAR *v12; // r14
  DWORD v13; // eax
  size_t v14; // rbx
  void *v15; // rax
  rsize_t v16; // rbp
  size_t v17; // r12
  WCHAR *v18; // rax

  v3 = 0;
  v4 = 0;
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
    if ( !v13 || v13 + 1 != v9 )
      goto LABEL_17;
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
  *a3 = v3;
  v3 = 0;
  a3[1] = v4;
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
0x1800a4af0  mov     [rsp+arg_0], rbx
0x1800a4af5  mov     [rsp+arg_8], rbp
0x1800a4afa  mov     [rsp+arg_10], rsi
0x1800a4aff  push    rdi
0x1800a4b00  push    r12
0x1800a4b02  push    r13
0x1800a4b04  push    r14
0x1800a4b06  push    r15
0x1800a4b08  sub     rsp, 20h
0x1800a4b0c  xor     esi, esi
0x1800a4b0e  xor     edi, edi
0x1800a4b10  mov     r13, r8
0x1800a4b13  mov     rbp, rdx
0x1800a4b16  mov     r12, rcx
0x1800a4b19  test    rdx, rdx
0x1800a4b1c  jnz     loc_1800A4C95
0x1800a4b22  xor     r9d, r9d; dwFlags
0x1800a4b25  xor     r8d, r8d; cchFilePath
0x1800a4b28  call    cs:__imp_GetFinalPathNameByHandleW
0x1800a4b2f  nop     dword ptr [rax+rax+00h]
0x1800a4b34  mov     ebx, eax
0x1800a4b36  test    eax, eax
0x1800a4b38  jnz     short loc_1800A4B4D
0x1800a4b3a  call    cs:__imp_GetLastError
0x1800a4b41  nop     dword ptr [rax+rax+00h]
0x1800a4b46  mov     ebx, eax
0x1800a4b48  jmp     loc_1800A4D28
0x1800a4b4d  lea     rbp, [rbx+rbx]
0x1800a4b51  mov     r15d, 10h
0x1800a4b57  mov     edx, r15d; Alignment
0x1800a4b5a  mov     rcx, rbp; Size
0x1800a4b5d  call    _o__aligned_malloc_0
0x1800a4b62  mov     r14, rax
0x1800a4b65  test    rax, rax
0x1800a4b68  jnz     short loc_1800A4B74
0x1800a4b6a  mov     ebx, 8
0x1800a4b6f  jmp     loc_1800A4D28
0x1800a4b74  mov     r8, rbp; Size
0x1800a4b77  xor     edx, edx; Val
0x1800a4b79  mov     rcx, r14; void *
0x1800a4b7c  call    memset_0
0x1800a4b81  xor     r9d, r9d; dwFlags
0x1800a4b84  mov     r8d, ebx; cchFilePath
0x1800a4b87  mov     rdx, r14; lpszFilePath
0x1800a4b8a  mov     rcx, r12; hFile
0x1800a4b8d  call    cs:__imp_GetFinalPathNameByHandleW
0x1800a4b94  nop     dword ptr [rax+rax+00h]
0x1800a4b99  test    eax, eax
0x1800a4b9b  jz      loc_1800A4C85
0x1800a4ba1  lea     ecx, [rax+1]
0x1800a4ba4  cmp     rcx, rbx
0x1800a4ba7  jnz     loc_1800A4C85
0x1800a4bad  dec     rbx
0x1800a4bb0  test    rbx, rbx
0x1800a4bb3  jz      loc_1800A4C85
0x1800a4bb9  lea     rbp, ds:0Ch[rbx*2]
0x1800a4bc1  mov     rdx, r15; Alignment
0x1800a4bc4  mov     rcx, rbp; Size
0x1800a4bc7  call    _o__aligned_malloc_0
0x1800a4bcc  mov     rdx, r15; Alignment
0x1800a4bcf  mov     rcx, rbp; Size
0x1800a4bd2  mov     rsi, rax
0x1800a4bd5  call    _o__aligned_malloc_0
0x1800a4bda  mov     rdi, rax
0x1800a4bdd  test    rsi, rsi
0x1800a4be0  jz      loc_1800A4D01
0x1800a4be6  test    rax, rax
0x1800a4be9  jz      loc_1800A4D01
0x1800a4bef  mov     r8, rbp; Size
0x1800a4bf2  xor     edx, edx; Val
0x1800a4bf4  mov     rcx, rsi; void *
0x1800a4bf7  call    memset_0
0x1800a4bfc  mov     r8, rbp; Size
0x1800a4bff  xor     edx, edx; Val
0x1800a4c01  mov     rcx, rdi; void *
0x1800a4c04  call    memset_0
0x1800a4c09  shr     rbp, 1
0x1800a4c0c  mov     r9, rbx
0x1800a4c0f  mov     rdx, rbp
0x1800a4c12  mov     r8, r14
0x1800a4c15  mov     rcx, rsi
0x1800a4c18  call    _o_wcsncpy_s_0
0x1800a4c1d  test    eax, eax
0x1800a4c1f  jnz     loc_1800A4CFA
0x1800a4c25  lea     r8, aLog1
0x1800a4c2c  mov     rdx, rbp; SizeInWords
0x1800a4c2f  mov     rcx, rsi; Destination
0x1800a4c32  call    wcscat_s
0x1800a4c37  test    eax, eax
0x1800a4c39  jnz     loc_1800A4CFA
0x1800a4c3f  mov     r9, rbx
0x1800a4c42  mov     r8, r14
0x1800a4c45  mov     rdx, rbp
0x1800a4c48  mov     rcx, rdi
0x1800a4c4b  call    _o_wcsncpy_s_0
0x1800a4c50  test    eax, eax
0x1800a4c52  jnz     loc_1800A4CFA
0x1800a4c58  lea     r8, aLog2
0x1800a4c5f  mov     rdx, rbp; SizeInWords
0x1800a4c62  mov     rcx, rdi; Destination
0x1800a4c65  call    wcscat_s
0x1800a4c6a  test    eax, eax
0x1800a4c6c  jnz     loc_1800A4CFA
0x1800a4c72  mov     [r13+0], rsi
0x1800a4c76  xor     esi, esi
0x1800a4c78  mov     [r13+8], rdi
0x1800a4c7c  xor     edi, edi
0x1800a4c7e  xor     ebx, ebx
0x1800a4c80  jmp     loc_1800A4D06
0x1800a4c85  call    cs:__imp_GetLastError
0x1800a4c8c  nop     dword ptr [rax+rax+00h]
0x1800a4c91  mov     ebx, eax
0x1800a4c93  jmp     short loc_1800A4D06
0x1800a4c95  mov     edx, 100h; MaxCount
0x1800a4c9a  mov     rcx, rbp; Source
0x1800a4c9d  call    cs:__imp_wcsnlen
0x1800a4ca4  nop     dword ptr [rax+rax+00h]
0x1800a4ca9  mov     r15d, 10h
0x1800a4caf  mov     rbx, rax
0x1800a4cb2  mov     edx, r15d; Alignment
0x1800a4cb5  lea     r12, ds:2[rax*2]
0x1800a4cbd  mov     rcx, r12; Size
0x1800a4cc0  call    _o__aligned_malloc_0
0x1800a4cc5  mov     r14, rax
0x1800a4cc8  test    rax, rax
0x1800a4ccb  jz      loc_1800A4B6A
0x1800a4cd1  mov     r8, r12; Size
0x1800a4cd4  xor     edx, edx; Val
0x1800a4cd6  mov     rcx, rax; void *
0x1800a4cd9  call    memset_0
0x1800a4cde  shr     r12, 1
0x1800a4ce1  mov     r9, rbx
0x1800a4ce4  mov     rdx, r12
0x1800a4ce7  mov     r8, rbp
0x1800a4cea  mov     rcx, r14
0x1800a4ced  call    _o_wcsncpy_s_0
0x1800a4cf2  test    eax, eax
0x1800a4cf4  jz      loc_1800A4BB0
0x1800a4cfa  mov     ebx, 54Fh
0x1800a4cff  jmp     short loc_1800A4D06
0x1800a4d01  mov     ebx, 8
0x1800a4d06  mov     rcx, r14; Block
0x1800a4d09  call    _aligned_free
0x1800a4d0e  test    rsi, rsi
0x1800a4d11  jz      short loc_1800A4D1B
0x1800a4d13  mov     rcx, rsi; Block
0x1800a4d16  call    _aligned_free
0x1800a4d1b  test    rdi, rdi
0x1800a4d1e  jz      short loc_1800A4D28
0x1800a4d20  mov     rcx, rdi; Block
0x1800a4d23  call    _aligned_free
0x1800a4d28  mov     rbp, [rsp+48h+arg_8]
0x1800a4d2d  mov     eax, ebx
0x1800a4d2f  mov     rbx, [rsp+48h+arg_0]
0x1800a4d34  mov     rsi, [rsp+48h+arg_10]
0x1800a4d39  add     rsp, 20h
0x1800a4d3d  pop     r15
0x1800a4d3f  pop     r14
0x1800a4d41  pop     r13
0x1800a4d43  pop     r12
0x1800a4d45  pop     rdi
0x1800a4d46  retn
```
