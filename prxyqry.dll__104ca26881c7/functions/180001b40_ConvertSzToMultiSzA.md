# ConvertSzToMultiSzA

- ea: `0x180001b40`
- end: `0x180001d55`
- name: `ConvertSzToMultiSzA`
- size: `533`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001b40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001bf5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001bf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001be0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001be0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001d47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001d47`

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
0x180001b40  push    rbx
0x180001b42  push    rbp
0x180001b43  push    rsi
0x180001b44  push    rdi
0x180001b45  push    r12
0x180001b47  push    r13
0x180001b49  push    r14
0x180001b4b  push    r15
0x180001b4d  sub     rsp, 28h
0x180001b51  xor     r12d, r12d
0x180001b54  mov     rsi, r9
0x180001b57  mov     [r8], r12
0x180001b5a  mov     r14, r8
0x180001b5d  mov     [r9], r12
0x180001b60  mov     ebp, edx
0x180001b62  mov     r13, rcx
0x180001b65  mov     ebx, r12d
0x180001b68  test    rcx, rcx
0x180001b6b  jz      loc_180001D13
0x180001b71  test    edx, edx
0x180001b73  jz      loc_180001D13
0x180001b79  lea     edi, [r12+1]
0x180001b7e  mov     r8d, r12d
0x180001b81  mov     eax, r8d
0x180001b84  mov     rcx, [r13+rax*8+0]
0x180001b89  test    rcx, rcx
0x180001b8c  jz      short loc_180001BD8
0x180001b8e  mov     edx, 7FFFFFFFh
0x180001b93  cmp     [rcx], r12b
0x180001b96  jz      short loc_180001BA1
0x180001b98  inc     rcx
0x180001b9b  sub     rdx, 1
0x180001b9f  jnz     short loc_180001B93
0x180001ba1  mov     ecx, 7FFFFFFFh
0x180001ba6  mov     rax, rdx
0x180001ba9  sub     rcx, rdx
0x180001bac  neg     rax
0x180001baf  sbb     r9, r9
0x180001bb2  and     r9, rcx
0x180001bb5  test    rdx, rdx
0x180001bb8  jz      loc_180001D2C
0x180001bbe  lea     rax, [r9+rdi]
0x180001bc2  cmp     rax, rdi
0x180001bc5  jb      loc_180001D2C
0x180001bcb  lea     rdi, [rax+1]
0x180001bcf  cmp     rdi, rax
0x180001bd2  jb      loc_180001D2C
0x180001bd8  inc     r8d
0x180001bdb  cmp     r8d, ebp
0x180001bde  jb      short loc_180001B81
0x180001be0  call    cs:__imp_GetProcessHeap
0x180001be6  mov     r15d, 8
0x180001bec  mov     r8, rdi; dwBytes
0x180001bef  mov     rcx, rax; hHeap
0x180001bf2  mov     edx, r15d; dwFlags
0x180001bf5  call    cs:__imp_HeapAlloc
0x180001bfb  mov     [r14], rax
0x180001bfe  mov     rdx, rax
0x180001c01  test    rax, rax
0x180001c04  jnz     short loc_180001C0E
0x180001c06  mov     ebx, r15d
0x180001c09  jmp     loc_180001D31
0x180001c0e  mov     r9, rdi
0x180001c11  mov     r11d, r12d
0x180001c14  test    ebp, ebp
0x180001c16  jz      loc_180001D10
0x180001c1c  mov     eax, r11d
0x180001c1f  mov     rcx, [r13+rax*8+0]
0x180001c24  test    rcx, rcx
0x180001c27  jz      loc_180001D04
0x180001c2d  test    rdx, rdx
0x180001c30  jnz     short loc_180001C3B
0x180001c32  test    r9, r9
0x180001c35  jnz     loc_180001D26
0x180001c3b  cmp     r9, 7FFFFFFFh
0x180001c42  ja      loc_180001D26
0x180001c48  test    r9, r9
0x180001c4b  jnz     short loc_180001C75
0x180001c4d  mov     r15, rdx
0x180001c50  mov     r10, r9
0x180001c53  mov     r8d, r12d
0x180001c56  cmp     [rcx], r12b
0x180001c59  jz      loc_180001CF3
0x180001c5f  mov     rax, rdx
0x180001c62  neg     rax
0x180001c65  sbb     r8d, r8d
0x180001c68  and     r8d, 23h
0x180001c6c  add     r8d, 80070057h
0x180001c73  jmp     short loc_180001CDD
0x180001c75  mov     eax, 7FFFFFFEh
0x180001c7a  mov     r8, r9
0x180001c7d  mov     r10, rdx
0x180001c80  mov     r15, r12
0x180001c83  test    rax, rax
0x180001c86  jz      short loc_180001CAD
0x180001c88  mov     r12b, [rcx]
0x180001c8b  test    r12b, r12b
0x180001c8e  jz      short loc_180001CAA
0x180001c90  mov     [r10], r12b
0x180001c93  inc     rcx
0x180001c96  inc     r10
0x180001c99  xor     r12d, r12d
0x180001c9c  dec     rax
0x180001c9f  inc     r15
0x180001ca2  sub     r8, 1
0x180001ca6  jnz     short loc_180001C83
0x180001ca8  jmp     short loc_180001CAD
0x180001caa  xor     r12d, r12d
0x180001cad  test    r8, r8
0x180001cb0  lea     rax, [r10-1]
0x180001cb4  lea     rcx, [r15-1]
0x180001cb8  cmovnz  rax, r10
0x180001cbc  cmovnz  rcx, r15
0x180001cc0  neg     r8
0x180001cc3  mov     r10, r9
0x180001cc6  sbb     r8d, r8d
0x180001cc9  not     r8d
0x180001ccc  mov     [rax], r12b
0x180001ccf  and     r8d, 8007007Ah
0x180001cd6  lea     r15, [rcx+rdx]
0x180001cda  sub     r10, rcx
0x180001cdd  mov     ecx, 80000000h
0x180001ce2  lea     eax, [r8+rcx]
0x180001ce6  test    ecx, eax
0x180001ce8  jnz     short loc_180001CF3
0x180001cea  cmp     r8d, 8007007Ah
0x180001cf1  jnz     short loc_180001CF9
0x180001cf3  mov     rdx, r15
0x180001cf6  mov     r9, r10
0x180001cf9  test    r8d, r8d
0x180001cfc  js      short loc_180001D29
0x180001cfe  inc     rdx
0x180001d01  dec     r9
0x180001d04  inc     r11d
0x180001d07  cmp     r11d, ebp
0x180001d0a  jb      loc_180001C1C
0x180001d10  mov     [rsi], rdi
0x180001d13  mov     eax, ebx
0x180001d15  add     rsp, 28h
0x180001d19  pop     r15
0x180001d1b  pop     r14
0x180001d1d  pop     r13
0x180001d1f  pop     r12
0x180001d21  pop     rdi
0x180001d22  pop     rsi
0x180001d23  pop     rbp
0x180001d24  pop     rbx
0x180001d25  retn
0x180001d26  mov     [rdx], r12b
0x180001d29  mov     [rsi], rdi
0x180001d2c  mov     ebx, 57h ; 'W'
0x180001d31  mov     rdi, [r14]
0x180001d34  test    rdi, rdi
0x180001d37  jz      short loc_180001D13
0x180001d39  call    cs:__imp_GetProcessHeap
0x180001d3f  mov     r8, rdi; lpMem
0x180001d42  xor     edx, edx; dwFlags
0x180001d44  mov     rcx, rax; hHeap
0x180001d47  call    cs:__imp_HeapFree
0x180001d4d  mov     [r14], r12
0x180001d50  mov     [rsi], r12
0x180001d53  jmp     short loc_180001D13
```
