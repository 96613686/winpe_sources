# ConstructLogPaths

- ea: `0x1400273a4`
- end: `0x1400275f2`
- name: `ConstructLogPaths`
- size: `590`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140027b04`

## callees

- `0x1400029c6`
- `0x1400029d2`
- `0x140002af0`
- `0x140002afc`
- `0x140002b2c`
- `0x1400273a4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140027553`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140027553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400273e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002753b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400273e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002753b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1400273d5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14002743d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1400273d5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14002743d`

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
0x1400273a4  mov     [rsp+arg_10], r8
0x1400273a9  push    rbx
0x1400273aa  push    rbp
0x1400273ab  push    rsi
0x1400273ac  push    rdi
0x1400273ad  push    r12
0x1400273af  push    r13
0x1400273b1  push    r14
0x1400273b3  push    r15
0x1400273b5  sub     rsp, 28h
0x1400273b9  xor     esi, esi
0x1400273bb  xor     edi, edi
0x1400273bd  mov     r13, r8
0x1400273c0  mov     rbx, rdx
0x1400273c3  mov     r12, rcx
0x1400273c6  test    rdx, rdx
0x1400273c9  jnz     loc_14002754B
0x1400273cf  xor     r9d, r9d; dwFlags
0x1400273d2  xor     r8d, r8d; cchFilePath
0x1400273d5  call    cs:__imp_GetFinalPathNameByHandleW
0x1400273dc  nop     dword ptr [rax+rax+00h]
0x1400273e1  mov     ebx, eax
0x1400273e3  test    eax, eax
0x1400273e5  jnz     short loc_1400273FA
0x1400273e7  call    cs:__imp_GetLastError
0x1400273ee  nop     dword ptr [rax+rax+00h]
0x1400273f3  mov     ebx, eax
0x1400273f5  jmp     loc_1400275DE
0x1400273fa  lea     r13, [rbx+rbx]
0x1400273fe  mov     r15d, 10h
0x140027404  mov     edx, r15d; Alignment
0x140027407  mov     rcx, r13; Size
0x14002740a  mov     r14, rbx
0x14002740d  call    _o__aligned_malloc_0
0x140027412  mov     rbp, rax
0x140027415  test    rax, rax
0x140027418  jnz     short loc_140027424
0x14002741a  mov     ebx, 8
0x14002741f  jmp     loc_1400275DE
0x140027424  mov     r8, r13; Size
0x140027427  xor     edx, edx; Val
0x140027429  mov     rcx, rbp; void *
0x14002742c  call    memset_0
0x140027431  xor     r9d, r9d; dwFlags
0x140027434  mov     r8d, ebx; cchFilePath
0x140027437  mov     rdx, rbp; lpszFilePath
0x14002743a  mov     rcx, r12; hFile
0x14002743d  call    cs:__imp_GetFinalPathNameByHandleW
0x140027444  nop     dword ptr [rax+rax+00h]
0x140027449  test    eax, eax
0x14002744b  jz      loc_14002753B
0x140027451  inc     eax
0x140027453  cmp     eax, ebx
0x140027455  jnz     loc_14002753B
0x14002745b  mov     r13, [rsp+68h+arg_10]
0x140027463  dec     r14
0x140027466  test    r14, r14
0x140027469  jz      loc_14002753B
0x14002746f  lea     rbx, ds:0Ch[r14*2]
0x140027477  mov     rdx, r15; Alignment
0x14002747a  mov     rcx, rbx; Size
0x14002747d  call    _o__aligned_malloc_0
0x140027482  mov     rdx, r15; Alignment
0x140027485  mov     rcx, rbx; Size
0x140027488  mov     rsi, rax
0x14002748b  call    _o__aligned_malloc_0
0x140027490  mov     rdi, rax
0x140027493  test    rsi, rsi
0x140027496  jz      loc_1400275B7
0x14002749c  test    rax, rax
0x14002749f  jz      loc_1400275B7
0x1400274a5  mov     r8, rbx; Size
0x1400274a8  xor     edx, edx; Val
0x1400274aa  mov     rcx, rsi; void *
0x1400274ad  call    memset_0
0x1400274b2  mov     r8, rbx; Size
0x1400274b5  xor     edx, edx; Val
0x1400274b7  mov     rcx, rdi; void *
0x1400274ba  call    memset_0
0x1400274bf  shr     rbx, 1
0x1400274c2  mov     r9, r14
0x1400274c5  mov     rdx, rbx
0x1400274c8  mov     r8, rbp
0x1400274cb  mov     rcx, rsi
0x1400274ce  call    _o_wcsncpy_s_0
0x1400274d3  test    eax, eax
0x1400274d5  jnz     loc_1400275B0
0x1400274db  lea     r8, aLog1; ".LOG1"
0x1400274e2  mov     rdx, rbx; SizeInWords
0x1400274e5  mov     rcx, rsi; Destination
0x1400274e8  call    wcscat_s
0x1400274ed  test    eax, eax
0x1400274ef  jnz     loc_1400275B0
0x1400274f5  mov     r9, r14
0x1400274f8  mov     r8, rbp
0x1400274fb  mov     rdx, rbx
0x1400274fe  mov     rcx, rdi
0x140027501  call    _o_wcsncpy_s_0
0x140027506  test    eax, eax
0x140027508  jnz     loc_1400275B0
0x14002750e  lea     r8, aLog2; ".LOG2"
0x140027515  mov     rdx, rbx; SizeInWords
0x140027518  mov     rcx, rdi; Destination
0x14002751b  call    wcscat_s
0x140027520  test    eax, eax
0x140027522  jnz     loc_1400275B0
0x140027528  mov     [r13+0], rsi
0x14002752c  xor     esi, esi
0x14002752e  mov     [r13+8], rdi
0x140027532  xor     edi, edi
0x140027534  xor     ebx, ebx
0x140027536  jmp     loc_1400275BC
0x14002753b  call    cs:__imp_GetLastError
0x140027542  nop     dword ptr [rax+rax+00h]
0x140027547  mov     ebx, eax
0x140027549  jmp     short loc_1400275BC
0x14002754b  mov     edx, 100h; MaxCount
0x140027550  mov     rcx, rbx; Source
0x140027553  call    cs:__imp_wcsnlen
0x14002755a  nop     dword ptr [rax+rax+00h]
0x14002755f  mov     r15d, 10h
0x140027565  mov     r14, rax
0x140027568  mov     edx, r15d; Alignment
0x14002756b  lea     r12, ds:2[rax*2]
0x140027573  mov     rcx, r12; Size
0x140027576  call    _o__aligned_malloc_0
0x14002757b  mov     rbp, rax
0x14002757e  test    rax, rax
0x140027581  jz      loc_14002741A
0x140027587  mov     r8, r12; Size
0x14002758a  xor     edx, edx; Val
0x14002758c  mov     rcx, rax; void *
0x14002758f  call    memset_0
0x140027594  shr     r12, 1
0x140027597  mov     r9, r14
0x14002759a  mov     rdx, r12
0x14002759d  mov     r8, rbx
0x1400275a0  mov     rcx, rbp
0x1400275a3  call    _o_wcsncpy_s_0
0x1400275a8  test    eax, eax
0x1400275aa  jz      loc_140027466
0x1400275b0  mov     ebx, 54Fh
0x1400275b5  jmp     short loc_1400275BC
0x1400275b7  mov     ebx, 8
0x1400275bc  mov     rcx, rbp; Block
0x1400275bf  call    _aligned_free
0x1400275c4  test    rsi, rsi
0x1400275c7  jz      short loc_1400275D1
0x1400275c9  mov     rcx, rsi; Block
0x1400275cc  call    _aligned_free
0x1400275d1  test    rdi, rdi
0x1400275d4  jz      short loc_1400275DE
0x1400275d6  mov     rcx, rdi; Block
0x1400275d9  call    _aligned_free
0x1400275de  mov     eax, ebx
0x1400275e0  add     rsp, 28h
0x1400275e4  pop     r15
0x1400275e6  pop     r14
0x1400275e8  pop     r13
0x1400275ea  pop     r12
0x1400275ec  pop     rdi
0x1400275ed  pop     rsi
0x1400275ee  pop     rbp
0x1400275ef  pop     rbx
0x1400275f0  retn
```
