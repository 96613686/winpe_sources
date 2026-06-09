# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000b648`
- end: `0x18000b883`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `571`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009e20`

## callees

- `0x18000af2c`
- `0x18000b648`
- `0x18000d192`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b7a0`
- `msvcrt!memcpy_s` at `0x18000b7f7`
- `msvcrt!memcpy_s` at `0x18000b848`
- `msvcrt!memcpy_s` at `0x18000b7a0`
- `msvcrt!memcpy_s` at `0x18000b7f7`
- `msvcrt!memcpy_s` at `0x18000b848`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b744`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b730`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b730`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x18000b648  push    rbx
0x18000b64a  push    rbp
0x18000b64b  push    rsi
0x18000b64c  push    rdi
0x18000b64d  push    r12
0x18000b64f  push    r13
0x18000b651  push    r14
0x18000b653  push    r15
0x18000b655  sub     rsp, 28h
0x18000b659  mov     [rcx+4], r8d
0x18000b65d  xor     r13d, r13d
0x18000b660  mov     eax, [rdx+8]
0x18000b663  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b667  mov     [rcx+8], eax
0x18000b66a  mov     rdi, rcx
0x18000b66d  mov     [rcx+10h], r13
0x18000b671  mov     r12, rdx
0x18000b674  movzx   eax, word ptr [rdx+40h]
0x18000b678  mov     [rcx+18h], ax
0x18000b67c  mov     al, [rdx]
0x18000b67e  mov     [rcx+1Ah], al
0x18000b681  mov     [rcx+20h], r13
0x18000b685  mov     rax, [rdx+88h]
0x18000b68c  mov     [rcx+28h], rax
0x18000b690  mov     rax, [rdx+90h]
0x18000b697  mov     [rcx+30h], rax
0x18000b69b  mov     [rcx+38h], r13
0x18000b69f  mov     rcx, [rdx+38h]
0x18000b6a3  lea     edx, [rbp+2]
0x18000b6a6  test    rcx, rcx
0x18000b6a9  jnz     short loc_18000B6B0
0x18000b6ab  mov     r8d, edx
0x18000b6ae  jmp     short loc_18000B6C0
0x18000b6b0  mov     rax, rbp
0x18000b6b3  inc     rax
0x18000b6b6  cmp     [rcx+rax], r13b
0x18000b6ba  jnz     short loc_18000B6B3
0x18000b6bc  lea     r8, [rax+1]; unsigned __int64
0x18000b6c0  mov     rcx, [r12+80h]
0x18000b6c8  test    rcx, rcx
0x18000b6cb  jz      short loc_18000B6DD
0x18000b6cd  mov     rax, rbp
0x18000b6d0  inc     rax
0x18000b6d3  cmp     [rcx+rax], r13b
0x18000b6d7  jnz     short loc_18000B6D0
0x18000b6d9  lea     rdx, [rax+1]
0x18000b6dd  mov     rcx, [r12+18h]
0x18000b6e2  test    rcx, rcx
0x18000b6e5  jnz     short loc_18000B6EC
0x18000b6e7  lea     eax, [rcx+2]
0x18000b6ea  jmp     short loc_18000B701
0x18000b6ec  mov     rax, rbp
0x18000b6ef  inc     rax
0x18000b6f2  cmp     [rcx+rax*2], r13w
0x18000b6f7  jnz     short loc_18000B6EF
0x18000b6f9  lea     rax, ds:2[rax*2]
0x18000b701  lea     r14, [rdx+rax]
0x18000b705  add     r14, r8
0x18000b708  lea     rsi, [rdi+48h]
0x18000b70c  cmp     [rdi+40h], r13
0x18000b710  jz      short loc_18000B717
0x18000b712  cmp     [rsi], r14
0x18000b715  jnb     short loc_18000B757
0x18000b717  mov     rdx, r14; dwBytes
0x18000b71a  mov     ecx, 8; dwFlags
0x18000b71f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b724  mov     r15, rax
0x18000b727  test    rax, rax
0x18000b72a  jz      short loc_18000B757
0x18000b72c  mov     rbx, [rdi+40h]
0x18000b730  call    cs:__imp_GetProcessHeap
0x18000b737  nop     dword ptr [rax+rax+00h]
0x18000b73c  mov     r8, rbx; lpMem
0x18000b73f  xor     edx, edx; dwFlags
0x18000b741  mov     rcx, rax; hHeap
0x18000b744  call    cs:__imp_HeapFree
0x18000b74b  nop     dword ptr [rax+rax+00h]
0x18000b750  mov     [rdi+40h], r15
0x18000b754  mov     [rsi], r14
0x18000b757  mov     rbx, [rdi+40h]
0x18000b75b  test    rbx, rbx
0x18000b75e  jz      loc_18000B871
0x18000b764  mov     rdx, [rsi]; DestinationSize
0x18000b767  lea     rsi, [rdx+rbx]
0x18000b76b  cmp     rbx, rsi
0x18000b76e  jz      short loc_18000B7B5
0x18000b770  mov     r8, [r12+38h]; Source
0x18000b775  test    r8, r8
0x18000b778  jz      short loc_18000B7B5
0x18000b77a  cmp     [r8], r13b
0x18000b77d  jz      short loc_18000B7B5
0x18000b77f  mov     rax, rbp
0x18000b782  inc     rax
0x18000b785  cmp     [r8+rax], r13b
0x18000b789  jnz     short loc_18000B782
0x18000b78b  lea     r14, [rax+1]
0x18000b78f  cmp     rdx, r14
0x18000b792  jnb     short loc_18000B79A
0x18000b794  mov     [rdi+10h], r13
0x18000b798  jmp     short loc_18000B7BE
0x18000b79a  mov     r9, r14; SourceSize
0x18000b79d  mov     rcx, rbx; Destination
0x18000b7a0  call    cs:__imp_memcpy_s
0x18000b7a7  nop     dword ptr [rax+rax+00h]
0x18000b7ac  mov     [rdi+10h], rbx
0x18000b7b0  add     rbx, r14
0x18000b7b3  jmp     short loc_18000B7B9
0x18000b7b5  mov     [rdi+10h], r13
0x18000b7b9  cmp     rbx, rsi
0x18000b7bc  jz      short loc_18000B80C
0x18000b7be  mov     r8, [r12+80h]; Source
0x18000b7c6  test    r8, r8
0x18000b7c9  jz      short loc_18000B80C
0x18000b7cb  cmp     [r8], r13b
0x18000b7ce  jz      short loc_18000B80C
0x18000b7d0  mov     rax, rbp
0x18000b7d3  inc     rax
0x18000b7d6  cmp     [r8+rax], r13b
0x18000b7da  jnz     short loc_18000B7D3
0x18000b7dc  mov     rdx, rsi
0x18000b7df  lea     r14, [rax+1]
0x18000b7e3  sub     rdx, rbx; DestinationSize
0x18000b7e6  cmp     rdx, r14
0x18000b7e9  jnb     short loc_18000B7F1
0x18000b7eb  mov     [rdi+20h], r13
0x18000b7ef  jmp     short loc_18000B815
0x18000b7f1  mov     r9, r14; SourceSize
0x18000b7f4  mov     rcx, rbx; Destination
0x18000b7f7  call    cs:__imp_memcpy_s
0x18000b7fe  nop     dword ptr [rax+rax+00h]
0x18000b803  mov     [rdi+20h], rbx
0x18000b807  add     rbx, r14
0x18000b80a  jmp     short loc_18000B810
0x18000b80c  mov     [rdi+20h], r13
0x18000b810  cmp     rbx, rsi
0x18000b813  jz      short loc_18000B85D
0x18000b815  mov     r8, [r12+18h]; Source
0x18000b81a  test    r8, r8
0x18000b81d  jz      short loc_18000B85D
0x18000b81f  cmp     [r8], r13w
0x18000b823  jz      short loc_18000B85D
0x18000b825  inc     rbp
0x18000b828  cmp     [r8+rbp*2], r13w
0x18000b82d  jnz     short loc_18000B825
0x18000b82f  mov     rdx, rsi
0x18000b832  lea     r14, ds:2[rbp*2]
0x18000b83a  sub     rdx, rbx; DestinationSize
0x18000b83d  cmp     rdx, r14
0x18000b840  jb      short loc_18000B85D
0x18000b842  mov     r9, r14; SourceSize
0x18000b845  mov     rcx, rbx; Destination
0x18000b848  call    cs:__imp_memcpy_s
0x18000b84f  nop     dword ptr [rax+rax+00h]
0x18000b854  mov     [rdi+38h], rbx
0x18000b858  add     rbx, r14
0x18000b85b  jmp     short loc_18000B861
0x18000b85d  mov     [rdi+38h], r13
0x18000b861  sub     rsi, rbx
0x18000b864  xor     edx, edx; Val
0x18000b866  mov     r8, rsi; Size
0x18000b869  mov     rcx, rbx; void *
0x18000b86c  call    memset_0
0x18000b871  add     rsp, 28h
0x18000b875  pop     r15
0x18000b877  pop     r14
0x18000b879  pop     r13
0x18000b87b  pop     r12
0x18000b87d  pop     rdi
0x18000b87e  pop     rsi
0x18000b87f  pop     rbp
0x18000b880  pop     rbx
0x18000b881  retn
```
