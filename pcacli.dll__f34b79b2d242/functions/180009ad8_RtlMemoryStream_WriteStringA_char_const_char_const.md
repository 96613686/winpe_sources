# RtlMemoryStream::WriteStringA(char const *,char const *)

- ea: `0x180009ad8`
- end: `0x180009ce7`
- name: `?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z`
- size: `527`
- prototype: `int(RtlMemoryStream *__hidden this, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003560`

## callees

- `0x180009ad8`
- `0x18000bfe6`
- `0x18000bffe`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c47`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009b9b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009c78`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009b9b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009c78`

## pseudocode

```c
__int64 __fastcall RtlMemoryStream::WriteStringA(RtlMemoryStream *this, const char *a2, const char *a3)
{
  size_t v6; // rdi
  size_t v7; // rsi
  size_t *v8; // r15
  size_t v9; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // r14
  unsigned __int64 v12; // rax
  void *v13; // r8
  void *v14; // rcx
  SIZE_T v15; // r14
  void *v16; // rax
  LPVOID v17; // rbp
  size_t *v19; // rax
  size_t v20; // rcx
  size_t v21; // rax
  size_t *v22; // r14
  size_t v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // rsi
  unsigned __int64 v26; // rax
  void *v27; // r8
  void *v28; // rcx
  SIZE_T v29; // rsi
  void *v30; // rax
  LPVOID v31; // rbp
  _QWORD *v32; // rax
  size_t v33; // rcx
  size_t v34; // rax

  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    if ( !v6 )
      v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 )
    {
      v8 = (size_t *)((char *)this + 32);
      v9 = *((_QWORD *)this + 4);
      v10 = v9 + v7;
      if ( v9 + v7 < v9 )
        return 160;
      if ( v10 <= *((_QWORD *)this + 2) )
      {
        v19 = v8;
      }
      else
      {
        v11 = *((_QWORD *)this + 3) - 1LL;
        v12 = v11 + v10;
        if ( v11 + v10 < v10 )
          return 534;
        v13 = (void *)*((_QWORD *)this + 5);
        v14 = *(void **)this;
        v15 = v12 & ~v11;
        if ( v13 )
        {
          v17 = HeapReAlloc(v14, 0, v13, v15);
        }
        else
        {
          v16 = HeapAlloc(v14, 0, v15);
          v17 = v16;
          if ( v16 )
            memset_0(v16, 0, v15);
        }
        if ( !v17 )
          return 14;
        *((_QWORD *)this + 5) = v17;
        v19 = (size_t *)((char *)this + 32);
        *((_QWORD *)this + 2) = v15;
      }
      memcpy_0((void *)(*v19 + *((_QWORD *)this + 5)), a2, v7);
      v20 = *v8 + v7;
      if ( v20 < *v8 )
      {
        *v8 = -1;
        return 534;
      }
      *v8 = v20;
      v21 = *((_QWORD *)this + 1);
      if ( v21 <= v20 )
        v21 = v20;
      *((_QWORD *)this + 1) = v21;
    }
  }
  if ( a3 && v6 )
  {
    v22 = (size_t *)((char *)this + 32);
    v23 = *((_QWORD *)this + 4);
    v24 = v23 + v6;
    if ( v23 + v6 >= v23 )
    {
      if ( v24 <= *((_QWORD *)this + 2) )
      {
        v32 = (_QWORD *)((char *)this + 32);
      }
      else
      {
        v25 = *((_QWORD *)this + 3) - 1LL;
        v26 = v24 + v25;
        if ( v24 + v25 < v24 )
          return 534;
        v27 = (void *)*((_QWORD *)this + 5);
        v28 = *(void **)this;
        v29 = v26 & ~v25;
        if ( v27 )
        {
          v31 = HeapReAlloc(v28, 0, v27, v29);
        }
        else
        {
          v30 = HeapAlloc(v28, 0, v29);
          v31 = v30;
          if ( v30 )
            memset_0(v30, 0, v29);
        }
        if ( !v31 )
          return 14;
        *((_QWORD *)this + 5) = v31;
        v32 = (_QWORD *)((char *)this + 32);
        *((_QWORD *)this + 2) = v29;
      }
      memcpy_0((void *)(*v32 + *((_QWORD *)this + 5)), a3, v6);
      v33 = *v22 + v6;
      if ( v33 >= *v22 )
      {
        *v22 = v33;
        v34 = *((_QWORD *)this + 1);
        if ( v34 <= v33 )
          v34 = v33;
        *((_QWORD *)this + 1) = v34;
        return 0;
      }
      *v22 = -1;
      return 534;
    }
    return 160;
  }
  return 0;
}

```

## disassembly

```asm
0x180009ad8  push    rbx
0x180009ada  push    rbp
0x180009adb  push    rsi
0x180009adc  push    rdi
0x180009add  push    r12
0x180009adf  push    r13
0x180009ae1  push    r14
0x180009ae3  push    r15
0x180009ae5  sub     rsp, 28h
0x180009ae9  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009aed  mov     r13, r8
0x180009af0  mov     r12, rdx
0x180009af3  mov     rbx, rcx
0x180009af6  test    r8, r8
0x180009af9  jz      short loc_180009B16
0x180009afb  mov     rdi, rbp
0x180009afe  inc     rdi
0x180009b01  cmp     byte ptr [rdi+r8], 0
0x180009b06  jnz     short loc_180009AFE
0x180009b08  mov     eax, 1
0x180009b0d  cmp     rdi, rax
0x180009b10  cmovb   rdi, rax
0x180009b14  jmp     short loc_180009B18
0x180009b16  xor     edi, edi
0x180009b18  test    r12, r12
0x180009b1b  jz      loc_180009BF8
0x180009b21  mov     rsi, rbp
0x180009b24  inc     rsi
0x180009b27  cmp     byte ptr [rdx+rsi], 0
0x180009b2b  jnz     short loc_180009B24
0x180009b2d  test    rsi, rsi
0x180009b30  jz      loc_180009BF8
0x180009b36  lea     r15, [rcx+20h]
0x180009b3a  mov     rax, [r15]
0x180009b3d  lea     rcx, [rax+rsi]
0x180009b41  cmp     rcx, rax
0x180009b44  jb      loc_180009C6E
0x180009b4a  cmp     rcx, [rbx+10h]
0x180009b4e  jbe     short loc_180009BC5
0x180009b50  mov     r14, [rbx+18h]
0x180009b54  dec     r14
0x180009b57  lea     rax, [r14+rcx]
0x180009b5b  cmp     rax, rcx
0x180009b5e  jb      loc_180009C67
0x180009b64  mov     r8, [rbx+28h]; lpMem
0x180009b68  not     r14
0x180009b6b  mov     rcx, [rbx]; hHeap
0x180009b6e  and     r14, rax
0x180009b71  xor     edx, edx; dwFlags
0x180009b73  test    r8, r8
0x180009b76  jnz     short loc_180009B98
0x180009b78  mov     r8, r14; dwBytes
0x180009b7b  call    cs:__imp_HeapAlloc
0x180009b81  mov     rbp, rax
0x180009b84  test    rax, rax
0x180009b87  jz      short loc_180009BA4
0x180009b89  mov     r8, r14; Size
0x180009b8c  xor     edx, edx; Val
0x180009b8e  mov     rcx, rax; void *
0x180009b91  call    memset_0
0x180009b96  jmp     short loc_180009BA4
0x180009b98  mov     r9, r14; dwBytes
0x180009b9b  call    cs:__imp_HeapReAlloc
0x180009ba1  mov     rbp, rax
0x180009ba4  test    rbp, rbp
0x180009ba7  jnz     short loc_180009BB3
0x180009ba9  mov     eax, 0Eh
0x180009bae  jmp     loc_180009CCD
0x180009bb3  mov     [rbx+28h], rbp
0x180009bb7  lea     rax, [rbx+20h]
0x180009bbb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009bbf  mov     [rbx+10h], r14
0x180009bc3  jmp     short loc_180009BC8
0x180009bc5  mov     rax, r15
0x180009bc8  mov     rcx, [rbx+28h]
0x180009bcc  mov     r8, rsi; Size
0x180009bcf  add     rcx, [rax]; void *
0x180009bd2  mov     rdx, r12; Src
0x180009bd5  call    memcpy_0
0x180009bda  mov     rax, [r15]
0x180009bdd  lea     rcx, [rax+rsi]
0x180009be1  cmp     rcx, rax
0x180009be4  jb      short loc_180009C64
0x180009be6  mov     [r15], rcx
0x180009be9  mov     rax, [rbx+8]
0x180009bed  cmp     rax, rcx
0x180009bf0  cmovbe  rax, rcx
0x180009bf4  mov     [rbx+8], rax
0x180009bf8  test    r13, r13
0x180009bfb  jz      loc_180009CCB
0x180009c01  test    rdi, rdi
0x180009c04  jz      loc_180009CCB
0x180009c0a  lea     r14, [rbx+20h]
0x180009c0e  mov     rax, [r14]
0x180009c11  lea     rcx, [rax+rdi]
0x180009c15  cmp     rcx, rax
0x180009c18  jb      short loc_180009C6E
0x180009c1a  cmp     rcx, [rbx+10h]
0x180009c1e  jbe     short loc_180009C98
0x180009c20  mov     rsi, [rbx+18h]
0x180009c24  dec     rsi
0x180009c27  lea     rax, [rcx+rsi]
0x180009c2b  cmp     rax, rcx
0x180009c2e  jb      short loc_180009C67
0x180009c30  mov     r8, [rbx+28h]; lpMem
0x180009c34  not     rsi
0x180009c37  mov     rcx, [rbx]; hHeap
0x180009c3a  and     rsi, rax
0x180009c3d  xor     edx, edx; dwFlags
0x180009c3f  test    r8, r8
0x180009c42  jnz     short loc_180009C75
0x180009c44  mov     r8, rsi; dwBytes
0x180009c47  call    cs:__imp_HeapAlloc
0x180009c4d  mov     rbp, rax
0x180009c50  test    rax, rax
0x180009c53  jz      short loc_180009C81
0x180009c55  mov     r8, rsi; Size
0x180009c58  xor     edx, edx; Val
0x180009c5a  mov     rcx, rax; void *
0x180009c5d  call    memset_0
0x180009c62  jmp     short loc_180009C81
0x180009c64  mov     [r15], rbp
0x180009c67  mov     eax, 216h
0x180009c6c  jmp     short loc_180009CCD
0x180009c6e  mov     eax, 0A0h
0x180009c73  jmp     short loc_180009CCD
0x180009c75  mov     r9, rsi; dwBytes
0x180009c78  call    cs:__imp_HeapReAlloc
0x180009c7e  mov     rbp, rax
0x180009c81  test    rbp, rbp
0x180009c84  jz      loc_180009BA9
0x180009c8a  mov     [rbx+28h], rbp
0x180009c8e  lea     rax, [rbx+20h]
0x180009c92  mov     [rbx+10h], rsi
0x180009c96  jmp     short loc_180009C9B
0x180009c98  mov     rax, r14
0x180009c9b  mov     rcx, [rbx+28h]
0x180009c9f  mov     r8, rdi; Size
0x180009ca2  add     rcx, [rax]; void *
0x180009ca5  mov     rdx, r13; Src
0x180009ca8  call    memcpy_0
0x180009cad  mov     rax, [r14]
0x180009cb0  lea     rcx, [rax+rdi]
0x180009cb4  cmp     rcx, rax
0x180009cb7  jb      short loc_180009CDE
0x180009cb9  mov     [r14], rcx
0x180009cbc  mov     rax, [rbx+8]
0x180009cc0  cmp     rax, rcx
0x180009cc3  cmovbe  rax, rcx
0x180009cc7  mov     [rbx+8], rax
0x180009ccb  xor     eax, eax
0x180009ccd  add     rsp, 28h
0x180009cd1  pop     r15
0x180009cd3  pop     r14
0x180009cd5  pop     r13
0x180009cd7  pop     r12
0x180009cd9  pop     rdi
0x180009cda  pop     rsi
0x180009cdb  pop     rbp
0x180009cdc  pop     rbx
0x180009cdd  retn
0x180009cde  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180009ce5  jmp     short loc_180009C67
```
