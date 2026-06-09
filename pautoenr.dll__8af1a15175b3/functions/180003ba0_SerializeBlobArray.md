# _SerializeBlobArray

- ea: `0x180003ba0`
- end: `0x180003d06`
- name: `_SerializeBlobArray`
- size: `358`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003ac0`

## callees

- `0x180003ba0`
- `0x180005200`
- `0x180007ce6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cfe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003bdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003bdd`

## pseudocode

```c
__int64 __fastcall SerializeBlobArray(__int64 a1, _QWORD *a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  unsigned int *v4; // rdi
  _QWORD *v5; // r13
  unsigned int v7; // esi
  unsigned int v8; // r12d
  _DWORD *v9; // rax
  _DWORD *v10; // r15
  unsigned int v11; // ebp
  __int64 v12; // r13
  _DWORD *v13; // rcx
  __int64 result; // rax
  unsigned int v15; // eax
  __int64 v16; // rdi
  unsigned int i; // r9d
  __int64 v18; // rax
  __int64 v19; // rcx
  _DWORD *v22; // [rsp+88h] [rbp+20h]

  v3 = 0;
  v4 = a3;
  v5 = a2;
  if ( a1 )
  {
    v7 = *(_DWORD *)a1;
    v10 = 0;
    if ( *(_DWORD *)a1 > 0xF4240u )
      goto LABEL_15;
    for ( i = 0; i < v7; ++i )
    {
      v18 = *(_QWORD *)(a1 + 8);
      v19 = 16LL * i;
      v3 += *(_DWORD *)(v19 + v18);
      if ( v3 < *(_DWORD *)(v19 + v18) || v3 > 0x5F5E100 )
        goto LABEL_15;
    }
  }
  else
  {
    v7 = 0;
  }
  v8 = v3 + 4 * (v7 + 2);
  v9 = LocalAlloc(0, v8);
  v10 = v9;
  if ( !v9 )
  {
    SetLastError(0x8007000E);
    goto LABEL_16;
  }
  v9[1] = v7;
  v11 = 1;
  *v9 = 1;
  if ( a1 )
  {
    v12 = 0;
    v13 = &v9[v7 + 2];
    v22 = v13;
    while ( 1 )
    {
      if ( (unsigned int)v12 >= v7 )
      {
        v4 = a3;
        v5 = a2;
        goto LABEL_8;
      }
      v15 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL * (unsigned int)v12);
      if ( v15 > v3 )
        break;
      v10[v12 + 2] = v15;
      if ( v15 )
      {
        v16 = v15;
        memcpy_0(v13, *(const void **)(*(_QWORD *)(a1 + 8) + 16LL * (unsigned int)v12 + 8), v15);
        v13 = (_DWORD *)((char *)v22 + v16);
        v22 = (_DWORD *)((char *)v22 + v16);
        v3 -= v16;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    v4 = a3;
    goto LABEL_15;
  }
LABEL_8:
  if ( v3 )
  {
LABEL_15:
    SetLastError(0x216u);
    v5 = a2;
LABEL_16:
    v11 = 0;
    PkiFree(v10);
    v10 = 0;
    v8 = 0;
  }
  *v5 = v10;
  result = v11;
  *v4 = v8;
  return result;
}

```

## disassembly

```asm
0x180003ba0  mov     [rsp+arg_10], r8
0x180003ba5  mov     [rsp+arg_8], rdx
0x180003baa  push    rbx
0x180003bab  push    rbp
0x180003bac  push    rsi
0x180003bad  push    rdi
0x180003bae  push    r12
0x180003bb0  push    r13
0x180003bb2  push    r14
0x180003bb4  push    r15
0x180003bb6  sub     rsp, 28h
0x180003bba  xor     ebx, ebx
0x180003bbc  mov     rdi, r8
0x180003bbf  mov     r13, rdx
0x180003bc2  mov     r14, rcx
0x180003bc5  test    rcx, rcx
0x180003bc8  jnz     loc_180003CB8
0x180003bce  xor     esi, esi
0x180003bd0  lea     r12d, [rsi+2]
0x180003bd4  xor     ecx, ecx; uFlags
0x180003bd6  lea     r12d, [rbx+r12*4]
0x180003bda  mov     edx, r12d; uBytes
0x180003bdd  call    cs:__imp_LocalAlloc
0x180003be3  mov     r15, rax
0x180003be6  test    rax, rax
0x180003be9  jz      loc_180003CF9
0x180003bef  mov     [rax+4], esi
0x180003bf2  mov     ebp, 1
0x180003bf7  mov     [rax], ebp
0x180003bf9  test    r14, r14
0x180003bfc  jz      short loc_180003C25
0x180003bfe  mov     ecx, esi
0x180003c00  add     rcx, 2
0x180003c04  xor     r13d, r13d
0x180003c07  lea     rcx, [rax+rcx*4]; void *
0x180003c0b  mov     [rsp+68h+arg_18], rcx
0x180003c13  cmp     r13d, esi
0x180003c16  jb      short loc_180003C43
0x180003c18  mov     rdi, [rsp+68h+arg_10]
0x180003c20  mov     r13, [rsp+68h+arg_8]
0x180003c25  test    ebx, ebx
0x180003c27  jnz     short loc_180003C93
0x180003c29  mov     [r13+0], r15
0x180003c2d  mov     eax, ebp
0x180003c2f  mov     [rdi], r12d
0x180003c32  add     rsp, 28h
0x180003c36  pop     r15
0x180003c38  pop     r14
0x180003c3a  pop     r13
0x180003c3c  pop     r12
0x180003c3e  pop     rdi
0x180003c3f  pop     rsi
0x180003c40  pop     rbp
0x180003c41  pop     rbx
0x180003c42  retn
0x180003c43  mov     rax, [r14+8]
0x180003c47  mov     r9d, r13d
0x180003c4a  add     r9, r9
0x180003c4d  mov     eax, [rax+r9*8]
0x180003c51  cmp     eax, ebx
0x180003c53  ja      short loc_180003C8B
0x180003c55  mov     [r15+r13*4+8], eax
0x180003c5a  test    eax, eax
0x180003c5c  jz      short loc_180003C86
0x180003c5e  mov     rdx, [r14+8]
0x180003c62  mov     r8d, eax; Size
0x180003c65  mov     edi, eax
0x180003c67  mov     rdx, [rdx+r9*8+8]; Src
0x180003c6c  call    memcpy_0
0x180003c71  mov     rcx, [rsp+68h+arg_18]
0x180003c79  add     rcx, rdi
0x180003c7c  mov     [rsp+68h+arg_18], rcx
0x180003c84  sub     ebx, edi
0x180003c86  inc     r13d
0x180003c89  jmp     short loc_180003C13
0x180003c8b  mov     rdi, [rsp+68h+arg_10]
0x180003c93  mov     ecx, 216h; dwErrCode
0x180003c98  call    cs:__imp_SetLastError
0x180003c9e  mov     r13, [rsp+68h+arg_8]
0x180003ca3  mov     rcx, r15; hMem
0x180003ca6  xor     ebp, ebp
0x180003ca8  call    PkiFree
0x180003cad  xor     r15d, r15d
0x180003cb0  xor     r12d, r12d
0x180003cb3  jmp     loc_180003C29
0x180003cb8  mov     esi, [rcx]
0x180003cba  xor     r15d, r15d
0x180003cbd  cmp     esi, 0F4240h
0x180003cc3  ja      short loc_180003C93
0x180003cc5  xor     r9d, r9d
0x180003cc8  nop     dword ptr [rax+rax+00000000h]
0x180003cd0  cmp     r9d, esi
0x180003cd3  jnb     loc_180003BD0
0x180003cd9  mov     rax, [r14+8]
0x180003cdd  mov     ecx, r9d
0x180003ce0  shl     rcx, 4
0x180003ce4  add     ebx, [rcx+rax]
0x180003ce7  cmp     ebx, [rcx+rax]
0x180003cea  jb      short loc_180003C93
0x180003cec  cmp     ebx, 5F5E100h
0x180003cf2  ja      short loc_180003C93
0x180003cf4  inc     r9d
0x180003cf7  jmp     short loc_180003CD0
0x180003cf9  mov     ecx, 8007000Eh; dwErrCode
0x180003cfe  call    cs:__imp_SetLastError
0x180003d04  jmp     short loc_180003CA3
```
