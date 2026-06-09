# AddFlushCacheEntry(_CRYPTNET_URL_CACHE_ENTRY const *,_CUCS_ENUM_URL_CACHE_ARG *)

- ea: `0x180004ac0`
- end: `0x180004c87`
- name: `?AddFlushCacheEntry@@YAXPEBU_CRYPTNET_URL_CACHE_ENTRY@@PEAU_CUCS_ENUM_URL_CACHE_ARG@@@Z`
- size: `455`
- prototype: `void __fastcall(const struct _CRYPTNET_URL_CACHE_ENTRY *, struct _CUCS_ENUM_URL_CACHE_ARG *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800028f0`
- `0x18000a500`

## callees

- `0x1800042e0`
- `0x180004ac0`
- `0x1800068b0`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004b6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004b8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004b6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004b8c`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180004bde`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180004bec`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180004bde`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180004bec`

## pseudocode

```c
void __fastcall AddFlushCacheEntry(const struct _CRYPTNET_URL_CACHE_ENTRY *a1, struct _CUCS_ENUM_URL_CACHE_ARG *a2)
{
  void *v3; // rsi
  unsigned int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  SIZE_T v10; // r14
  SIZE_T v11; // r15
  __int64 v12; // rax
  void *v13; // rcx
  unsigned int v14; // r12d
  void *v15; // rbp
  SIZE_T v16; // rbx
  HLOCAL v17; // rax
  void *v18; // rdi
  void *v19; // rcx
  HLOCAL v20; // rax
  void *v21; // rbx
  unsigned int v23; // [rsp+68h] [rbp+10h]

  v3 = 0;
  v5 = *((_DWORD *)a2 + 4);
  v23 = v5;
  if ( v5 > 0xFFFFFFF )
  {
    v18 = 0;
    v15 = 0;
    v21 = 0;
    SetLastError(0x216u);
LABEL_16:
    PkiFree(v3);
    PkiFree(v15);
    PkiFree(v18);
    PkiFree(v21);
    return;
  }
  v6 = *((_QWORD *)a1 + 5);
  v7 = -1;
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  v9 = *((_QWORD *)a1 + 6);
  if ( v9 )
  {
    do
      ++v7;
    while ( *(_WORD *)(v9 + 2 * v7) );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  v10 = (unsigned int)(2 * v8 + 2);
  v3 = (void *)PkiNonzeroAlloc(v10);
  v11 = (unsigned int)(2 * v7 + 2);
  v12 = PkiNonzeroAlloc(v11);
  v13 = (void *)*((_QWORD *)a2 + 3);
  v14 = v5 + 1;
  v15 = (void *)v12;
  v16 = 8LL * (v5 + 1);
  if ( v13 )
    v17 = LocalReAlloc(v13, v16, 2u);
  else
    v17 = LocalAlloc(0, v16);
  v18 = v17;
  if ( !v17 )
    SetLastError(0x8007000E);
  v19 = (void *)*((_QWORD *)a2 + 4);
  if ( v19 )
    v20 = LocalReAlloc(v19, v16, 2u);
  else
    v20 = LocalAlloc(0, v16);
  v21 = v20;
  if ( !v20 )
    SetLastError(0x8007000E);
  if ( !v3 || !v15 || !v18 || !v21 )
    goto LABEL_16;
  memcpy_0(v3, *((const void **)a1 + 5), v10);
  memcpy_0(v15, *((const void **)a1 + 6), v11);
  *((_QWORD *)v18 + v23) = v3;
  *((_QWORD *)v21 + v23) = v15;
  *((_QWORD *)a2 + 3) = v18;
  *((_QWORD *)a2 + 4) = v21;
  *((_DWORD *)a2 + 4) = v14;
}

```

## disassembly

```asm
0x180004ac0  mov     [rsp+arg_10], rbx
0x180004ac5  mov     [rsp+arg_0], rcx
0x180004aca  push    rbp
0x180004acb  push    rsi
0x180004acc  push    rdi
0x180004acd  push    r12
0x180004acf  push    r13
0x180004ad1  push    r14
0x180004ad3  push    r15
0x180004ad5  sub     rsp, 20h
0x180004ad9  mov     r13, rdx
0x180004adc  xor     esi, esi
0x180004ade  mov     rdx, rcx
0x180004ae1  mov     edi, [r13+10h]
0x180004ae5  mov     [rsp+58h+arg_8], edi
0x180004ae9  cmp     edi, 0FFFFFFFh
0x180004aef  ja      loc_180004C4E
0x180004af5  mov     rcx, [rcx+28h]
0x180004af9  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180004b00  test    rcx, rcx
0x180004b03  jz      loc_180004C40
0x180004b09  mov     rax, rbx
0x180004b0c  nop     dword ptr [rax+00h]
0x180004b10  inc     rax
0x180004b13  cmp     [rcx+rax*2], si
0x180004b17  jnz     short loc_180004B10
0x180004b19  mov     rcx, [rdx+30h]
0x180004b1d  test    rcx, rcx
0x180004b20  jz      loc_180004C47
0x180004b26  inc     rbx
0x180004b29  cmp     [rcx+rbx*2], si
0x180004b2d  jnz     short loc_180004B26
0x180004b2f  lea     eax, ds:2[rax*2]
0x180004b36  mov     ecx, eax; uBytes
0x180004b38  mov     r14d, eax
0x180004b3b  call    PkiNonzeroAlloc
0x180004b40  lea     ebx, ds:2[rbx*2]
0x180004b47  mov     rsi, rax
0x180004b4a  mov     ecx, ebx; uBytes
0x180004b4c  mov     r15d, ebx
0x180004b4f  call    PkiNonzeroAlloc
0x180004b54  mov     rcx, [r13+18h]; hMem
0x180004b58  lea     r12d, [rdi+1]
0x180004b5c  mov     ebx, r12d
0x180004b5f  mov     rbp, rax
0x180004b62  shl     rbx, 3
0x180004b66  mov     rdx, rbx; uBytes
0x180004b69  test    rcx, rcx
0x180004b6c  jnz     short loc_180004BD8
0x180004b6e  call    cs:__imp_LocalAlloc
0x180004b74  mov     rdi, rax
0x180004b77  test    rax, rax
0x180004b7a  jz      loc_180004C67
0x180004b80  mov     rcx, [r13+20h]; hMem
0x180004b84  mov     rdx, rbx; uBytes
0x180004b87  test    rcx, rcx
0x180004b8a  jnz     short loc_180004BE6
0x180004b8c  call    cs:__imp_LocalAlloc
0x180004b92  mov     rbx, rax
0x180004b95  test    rax, rax
0x180004b98  jz      loc_180004C77
0x180004b9e  test    rsi, rsi
0x180004ba1  jnz     short loc_180004BF4
0x180004ba3  mov     rcx, rsi; hMem
0x180004ba6  call    PkiFree
0x180004bab  mov     rcx, rbp; hMem
0x180004bae  call    PkiFree
0x180004bb3  mov     rcx, rdi; hMem
0x180004bb6  call    PkiFree
0x180004bbb  mov     rcx, rbx; hMem
0x180004bbe  call    PkiFree
0x180004bc3  mov     rbx, [rsp+58h+arg_10]
0x180004bc8  add     rsp, 20h
0x180004bcc  pop     r15
0x180004bce  pop     r14
0x180004bd0  pop     r13
0x180004bd2  pop     r12
0x180004bd4  pop     rdi
0x180004bd5  pop     rsi
0x180004bd6  pop     rbp
0x180004bd7  retn
0x180004bd8  mov     r8d, 2; uFlags
0x180004bde  call    cs:__imp_LocalReAlloc
0x180004be4  jmp     short loc_180004B74
0x180004be6  mov     r8d, 2; uFlags
0x180004bec  call    cs:__imp_LocalReAlloc
0x180004bf2  jmp     short loc_180004B92
0x180004bf4  test    rbp, rbp
0x180004bf7  jz      short loc_180004BA3
0x180004bf9  test    rdi, rdi
0x180004bfc  jz      short loc_180004BA3
0x180004bfe  test    rbx, rbx
0x180004c01  jz      short loc_180004BA3
0x180004c03  mov     r8, r14; Size
0x180004c06  mov     rcx, rsi; void *
0x180004c09  mov     r14, [rsp+58h+arg_0]
0x180004c0e  mov     rdx, [r14+28h]; Src
0x180004c12  call    memcpy_0
0x180004c17  mov     rdx, [r14+30h]; Src
0x180004c1b  mov     r8, r15; Size
0x180004c1e  mov     rcx, rbp; void *
0x180004c21  call    memcpy_0
0x180004c26  mov     eax, [rsp+58h+arg_8]
0x180004c2a  mov     [rdi+rax*8], rsi
0x180004c2e  mov     [rbx+rax*8], rbp
0x180004c32  mov     [r13+18h], rdi
0x180004c36  mov     [r13+20h], rbx
0x180004c3a  mov     [r13+10h], r12d
0x180004c3e  jmp     short loc_180004BC3
0x180004c40  mov     eax, esi
0x180004c42  jmp     loc_180004B19
0x180004c47  mov     ebx, esi
0x180004c49  jmp     loc_180004B2F
0x180004c4e  mov     rdi, rsi
0x180004c51  mov     rbp, rsi
0x180004c54  mov     rbx, rsi
0x180004c57  mov     ecx, 216h; dwErrCode
0x180004c5c  call    cs:__imp_SetLastError
0x180004c62  jmp     loc_180004BA3
0x180004c67  mov     ecx, 8007000Eh; dwErrCode
0x180004c6c  call    cs:__imp_SetLastError
0x180004c72  jmp     loc_180004B80
0x180004c77  mov     ecx, 8007000Eh; dwErrCode
0x180004c7c  call    cs:__imp_SetLastError
0x180004c82  jmp     loc_180004B9E
```
