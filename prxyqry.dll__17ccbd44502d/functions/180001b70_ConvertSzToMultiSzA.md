# ConvertSzToMultiSzA

- ea: `0x180001b70`
- end: `0x180001d9e`
- name: `ConvertSzToMultiSzA`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001b70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001c2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001c2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001c10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001c10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001d8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001d8a`

## pseudocode

```c
__int64 __fastcall ConvertSzToMultiSzA(__int64 a1, unsigned int a2, void **a3, SIZE_T *a4)
{
  unsigned int v8; // ebx
  SIZE_T v9; // rdi
  unsigned int i; // r8d
  _BYTE *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int64 v14; // rax
  HANDLE ProcessHeap; // rax
  _BYTE *v16; // rax
  _BYTE *v17; // rdx
  unsigned __int64 v18; // r9
  unsigned int v19; // r11d
  _BYTE *v20; // rcx
  _BYTE *v21; // r15
  unsigned __int64 v22; // r10
  int v23; // r8d
  __int64 v24; // rax
  unsigned __int64 v25; // r8
  _BYTE *v26; // r10
  __int64 v27; // r15
  _BYTE *v28; // rax
  __int64 v29; // rcx
  void *v31; // rdi
  HANDLE v32; // rax

  *a3 = 0;
  *a4 = 0;
  v8 = 0;
  if ( !a1 || !a2 )
    return v8;
  v9 = 1;
  for ( i = 0; i < a2; ++i )
  {
    v11 = *(_BYTE **)(a1 + 8LL * i);
    if ( v11 )
    {
      v12 = 0x7FFFFFFF;
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v12;
      }
      while ( v12 );
      v13 = (0x7FFFFFFF - v12) & -(__int64)(v12 != 0);
      if ( !v12 )
        goto LABEL_39;
      v14 = v13 + v9;
      if ( v13 + v9 < v9 )
        goto LABEL_39;
      v9 = v14 + 1;
      if ( v14 + 1 < v14 )
        goto LABEL_39;
    }
  }
  ProcessHeap = GetProcessHeap();
  v16 = HeapAlloc(ProcessHeap, 8u, v9);
  *a3 = v16;
  v17 = v16;
  if ( !v16 )
  {
    v8 = 8;
    goto LABEL_40;
  }
  v18 = v9;
  v19 = 0;
  if ( !a2 )
  {
LABEL_35:
    *a4 = v9;
    return v8;
  }
  while ( 1 )
  {
    v20 = *(_BYTE **)(a1 + 8LL * v19);
    if ( !v20 )
      goto LABEL_34;
    if ( !v17 && v18 || v18 > 0x7FFFFFFF )
      break;
    if ( v18 )
    {
      v24 = 2147483646;
      v25 = v18;
      v26 = v17;
      v27 = 0;
      do
      {
        if ( !v24 )
          break;
        if ( !*v20 )
          break;
        *v26++ = *v20++;
        --v24;
        ++v27;
        --v25;
      }
      while ( v25 );
      v28 = v26 - 1;
      v29 = v27 - 1;
      if ( v25 )
      {
        v28 = v26;
        v29 = v27;
      }
      *v28 = 0;
      v23 = v25 == 0 ? 0x8007007A : 0;
      v21 = &v17[v29];
      v22 = v18 - v29;
LABEL_29:
      if ( (int)(v23 + 0x80000000) >= 0 && v23 != -2147024774 )
        goto LABEL_32;
      goto LABEL_31;
    }
    v21 = v17;
    v22 = 0;
    v23 = 0;
    if ( *v20 )
    {
      v23 = v17 != 0 ? -2147024774 : -2147024809;
      goto LABEL_29;
    }
LABEL_31:
    v17 = v21;
    v18 = v22;
LABEL_32:
    if ( v23 < 0 )
      goto LABEL_38;
    ++v17;
    --v18;
LABEL_34:
    if ( ++v19 >= a2 )
      goto LABEL_35;
  }
  *v17 = 0;
LABEL_38:
  *a4 = v9;
LABEL_39:
  v8 = 87;
LABEL_40:
  v31 = *a3;
  if ( *a3 )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v31);
    *a3 = 0;
    *a4 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180001b70  push    rbx
0x180001b72  push    rbp
0x180001b73  push    rsi
0x180001b74  push    rdi
0x180001b75  push    r12
0x180001b77  push    r13
0x180001b79  push    r14
0x180001b7b  push    r15
0x180001b7d  sub     rsp, 28h
0x180001b81  xor     r12d, r12d
0x180001b84  mov     rsi, r9
0x180001b87  mov     [r8], r12
0x180001b8a  mov     r14, r8
0x180001b8d  mov     [r9], r12
0x180001b90  mov     ebp, edx
0x180001b92  mov     r13, rcx
0x180001b95  mov     ebx, r12d
0x180001b98  test    rcx, rcx
0x180001b9b  jz      loc_180001D4F
0x180001ba1  test    edx, edx
0x180001ba3  jz      loc_180001D4F
0x180001ba9  lea     edi, [r12+1]
0x180001bae  mov     r8d, r12d
0x180001bb1  mov     eax, r8d
0x180001bb4  mov     rcx, [r13+rax*8+0]
0x180001bb9  test    rcx, rcx
0x180001bbc  jz      short loc_180001C08
0x180001bbe  mov     edx, 7FFFFFFFh
0x180001bc3  cmp     [rcx], r12b
0x180001bc6  jz      short loc_180001BD1
0x180001bc8  inc     rcx
0x180001bcb  sub     rdx, 1
0x180001bcf  jnz     short loc_180001BC3
0x180001bd1  mov     ecx, 7FFFFFFFh
0x180001bd6  mov     rax, rdx
0x180001bd9  sub     rcx, rdx
0x180001bdc  neg     rax
0x180001bdf  sbb     r9, r9
0x180001be2  and     r9, rcx
0x180001be5  test    rdx, rdx
0x180001be8  jz      loc_180001D69
0x180001bee  lea     rax, [r9+rdi]
0x180001bf2  cmp     rax, rdi
0x180001bf5  jb      loc_180001D69
0x180001bfb  lea     rdi, [rax+1]
0x180001bff  cmp     rdi, rax
0x180001c02  jb      loc_180001D69
0x180001c08  inc     r8d
0x180001c0b  cmp     r8d, ebp
0x180001c0e  jb      short loc_180001BB1
0x180001c10  call    cs:__imp_GetProcessHeap
0x180001c17  nop     dword ptr [rax+rax+00h]
0x180001c1c  mov     r15d, 8
0x180001c22  mov     r8, rdi; dwBytes
0x180001c25  mov     rcx, rax; hHeap
0x180001c28  mov     edx, r15d; dwFlags
0x180001c2b  call    cs:__imp_HeapAlloc
0x180001c32  nop     dword ptr [rax+rax+00h]
0x180001c37  mov     [r14], rax
0x180001c3a  mov     rdx, rax
0x180001c3d  test    rax, rax
0x180001c40  jnz     short loc_180001C4A
0x180001c42  mov     ebx, r15d
0x180001c45  jmp     loc_180001D6E
0x180001c4a  mov     r9, rdi
0x180001c4d  mov     r11d, r12d
0x180001c50  test    ebp, ebp
0x180001c52  jz      loc_180001D4C
0x180001c58  mov     eax, r11d
0x180001c5b  mov     rcx, [r13+rax*8+0]
0x180001c60  test    rcx, rcx
0x180001c63  jz      loc_180001D40
0x180001c69  test    rdx, rdx
0x180001c6c  jnz     short loc_180001C77
0x180001c6e  test    r9, r9
0x180001c71  jnz     loc_180001D63
0x180001c77  cmp     r9, 7FFFFFFFh
0x180001c7e  ja      loc_180001D63
0x180001c84  test    r9, r9
0x180001c87  jnz     short loc_180001CB1
0x180001c89  mov     r15, rdx
0x180001c8c  mov     r10, r9
0x180001c8f  mov     r8d, r12d
0x180001c92  cmp     [rcx], r12b
0x180001c95  jz      loc_180001D2F
0x180001c9b  mov     rax, rdx
0x180001c9e  neg     rax
0x180001ca1  sbb     r8d, r8d
0x180001ca4  and     r8d, 23h
0x180001ca8  add     r8d, 80070057h
0x180001caf  jmp     short loc_180001D19
0x180001cb1  mov     eax, 7FFFFFFEh
0x180001cb6  mov     r8, r9
0x180001cb9  mov     r10, rdx
0x180001cbc  mov     r15, r12
0x180001cbf  test    rax, rax
0x180001cc2  jz      short loc_180001CE9
0x180001cc4  mov     r12b, [rcx]
0x180001cc7  test    r12b, r12b
0x180001cca  jz      short loc_180001CE6
0x180001ccc  mov     [r10], r12b
0x180001ccf  inc     rcx
0x180001cd2  inc     r10
0x180001cd5  xor     r12d, r12d
0x180001cd8  dec     rax
0x180001cdb  inc     r15
0x180001cde  sub     r8, 1
0x180001ce2  jnz     short loc_180001CBF
0x180001ce4  jmp     short loc_180001CE9
0x180001ce6  xor     r12d, r12d
0x180001ce9  test    r8, r8
0x180001cec  lea     rax, [r10-1]
0x180001cf0  lea     rcx, [r15-1]
0x180001cf4  cmovnz  rax, r10
0x180001cf8  cmovnz  rcx, r15
0x180001cfc  neg     r8
0x180001cff  mov     r10, r9
0x180001d02  sbb     r8d, r8d
0x180001d05  not     r8d
0x180001d08  mov     [rax], r12b
0x180001d0b  and     r8d, 8007007Ah
0x180001d12  lea     r15, [rcx+rdx]
0x180001d16  sub     r10, rcx
0x180001d19  mov     ecx, 80000000h
0x180001d1e  lea     eax, [r8+rcx]
0x180001d22  test    ecx, eax
0x180001d24  jnz     short loc_180001D2F
0x180001d26  cmp     r8d, 8007007Ah
0x180001d2d  jnz     short loc_180001D35
0x180001d2f  mov     rdx, r15
0x180001d32  mov     r9, r10
0x180001d35  test    r8d, r8d
0x180001d38  js      short loc_180001D66
0x180001d3a  inc     rdx
0x180001d3d  dec     r9
0x180001d40  inc     r11d
0x180001d43  cmp     r11d, ebp
0x180001d46  jb      loc_180001C58
0x180001d4c  mov     [rsi], rdi
0x180001d4f  mov     eax, ebx
0x180001d51  add     rsp, 28h
0x180001d55  pop     r15
0x180001d57  pop     r14
0x180001d59  pop     r13
0x180001d5b  pop     r12
0x180001d5d  pop     rdi
0x180001d5e  pop     rsi
0x180001d5f  pop     rbp
0x180001d60  pop     rbx
0x180001d61  retn
0x180001d63  mov     [rdx], r12b
0x180001d66  mov     [rsi], rdi
0x180001d69  mov     ebx, 57h ; 'W'
0x180001d6e  mov     rdi, [r14]
0x180001d71  test    rdi, rdi
0x180001d74  jz      short loc_180001D4F
0x180001d76  call    cs:__imp_GetProcessHeap
0x180001d7d  nop     dword ptr [rax+rax+00h]
0x180001d82  mov     r8, rdi; lpMem
0x180001d85  xor     edx, edx; dwFlags
0x180001d87  mov     rcx, rax; hHeap
0x180001d8a  call    cs:__imp_HeapFree
0x180001d91  nop     dword ptr [rax+rax+00h]
0x180001d96  mov     [r14], r12
0x180001d99  mov     [rsi], r12
0x180001d9c  jmp     short loc_180001D4F
```
