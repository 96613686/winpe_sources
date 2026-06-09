# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000d010`
- end: `0x18000d229`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bc80`

## callees

- `0x1800025fe`
- `0x180002616`
- `0x18000ccc8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d106`

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
0x18000d010  push    rbx
0x18000d012  push    rbp
0x18000d013  push    rsi
0x18000d014  push    rdi
0x18000d015  push    r12
0x18000d017  push    r13
0x18000d019  push    r14
0x18000d01b  push    r15
0x18000d01d  sub     rsp, 28h
0x18000d021  mov     [rcx+4], r8d
0x18000d025  xor     r13d, r13d
0x18000d028  mov     eax, [rdx+8]
0x18000d02b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000d02f  mov     [rcx+8], eax
0x18000d032  mov     rdi, rcx
0x18000d035  mov     [rcx+10h], r13
0x18000d039  mov     r12, rdx
0x18000d03c  movzx   eax, word ptr [rdx+40h]
0x18000d040  mov     [rcx+18h], ax
0x18000d044  mov     al, [rdx]
0x18000d046  mov     [rcx+1Ah], al
0x18000d049  mov     [rcx+20h], r13
0x18000d04d  mov     rax, [rdx+88h]
0x18000d054  mov     [rcx+28h], rax
0x18000d058  mov     rax, [rdx+90h]
0x18000d05f  mov     [rcx+30h], rax
0x18000d063  mov     [rcx+38h], r13
0x18000d067  mov     rcx, [rdx+38h]
0x18000d06b  lea     edx, [rbp+2]
0x18000d06e  test    rcx, rcx
0x18000d071  jnz     short loc_18000D078
0x18000d073  mov     r8d, edx
0x18000d076  jmp     short loc_18000D088
0x18000d078  mov     rax, rbp
0x18000d07b  inc     rax
0x18000d07e  cmp     [rcx+rax], r13b
0x18000d082  jnz     short loc_18000D07B
0x18000d084  lea     r8, [rax+1]; unsigned __int64
0x18000d088  mov     rcx, [r12+80h]
0x18000d090  test    rcx, rcx
0x18000d093  jz      short loc_18000D0A5
0x18000d095  mov     rax, rbp
0x18000d098  inc     rax
0x18000d09b  cmp     [rcx+rax], r13b
0x18000d09f  jnz     short loc_18000D098
0x18000d0a1  lea     rdx, [rax+1]
0x18000d0a5  mov     rcx, [r12+18h]
0x18000d0aa  test    rcx, rcx
0x18000d0ad  jnz     short loc_18000D0B4
0x18000d0af  lea     eax, [rcx+2]
0x18000d0b2  jmp     short loc_18000D0C9
0x18000d0b4  mov     rax, rbp
0x18000d0b7  inc     rax
0x18000d0ba  cmp     [rcx+rax*2], r13w
0x18000d0bf  jnz     short loc_18000D0B7
0x18000d0c1  lea     rax, ds:2[rax*2]
0x18000d0c9  lea     r14, [rdx+rax]
0x18000d0cd  add     r14, r8
0x18000d0d0  lea     rsi, [rdi+48h]
0x18000d0d4  cmp     [rdi+40h], r13
0x18000d0d8  jz      short loc_18000D0DF
0x18000d0da  cmp     [rsi], r14
0x18000d0dd  jnb     short loc_18000D113
0x18000d0df  mov     rdx, r14; dwBytes
0x18000d0e2  mov     ecx, 8; dwFlags
0x18000d0e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d0ec  mov     r15, rax
0x18000d0ef  test    rax, rax
0x18000d0f2  jz      short loc_18000D113
0x18000d0f4  mov     rbx, [rdi+40h]
0x18000d0f8  call    cs:__imp_GetProcessHeap
0x18000d0fe  mov     r8, rbx; lpMem
0x18000d101  xor     edx, edx; dwFlags
0x18000d103  mov     rcx, rax; hHeap
0x18000d106  call    cs:__imp_HeapFree
0x18000d10c  mov     [rdi+40h], r15
0x18000d110  mov     [rsi], r14
0x18000d113  mov     rbx, [rdi+40h]
0x18000d117  test    rbx, rbx
0x18000d11a  jz      loc_18000D218
0x18000d120  mov     rdx, [rsi]; DestinationSize
0x18000d123  lea     rsi, [rdx+rbx]
0x18000d127  cmp     rbx, rsi
0x18000d12a  jz      short loc_18000D16A
0x18000d12c  mov     r8, [r12+38h]; Source
0x18000d131  test    r8, r8
0x18000d134  jz      short loc_18000D16A
0x18000d136  cmp     [r8], r13b
0x18000d139  jz      short loc_18000D16A
0x18000d13b  mov     rax, rbp
0x18000d13e  inc     rax
0x18000d141  cmp     [r8+rax], r13b
0x18000d145  jnz     short loc_18000D13E
0x18000d147  lea     r14, [rax+1]
0x18000d14b  cmp     rdx, r14
0x18000d14e  jnb     short loc_18000D156
0x18000d150  mov     [rdi+10h], r13
0x18000d154  jmp     short loc_18000D173
0x18000d156  mov     r9, r14; SourceSize
0x18000d159  mov     rcx, rbx; Destination
0x18000d15c  call    memcpy_s
0x18000d161  mov     [rdi+10h], rbx
0x18000d165  add     rbx, r14
0x18000d168  jmp     short loc_18000D16E
0x18000d16a  mov     [rdi+10h], r13
0x18000d16e  cmp     rbx, rsi
0x18000d171  jz      short loc_18000D1BA
0x18000d173  mov     r8, [r12+80h]; Source
0x18000d17b  test    r8, r8
0x18000d17e  jz      short loc_18000D1BA
0x18000d180  cmp     [r8], r13b
0x18000d183  jz      short loc_18000D1BA
0x18000d185  mov     rax, rbp
0x18000d188  inc     rax
0x18000d18b  cmp     [r8+rax], r13b
0x18000d18f  jnz     short loc_18000D188
0x18000d191  mov     rdx, rsi
0x18000d194  lea     r14, [rax+1]
0x18000d198  sub     rdx, rbx; DestinationSize
0x18000d19b  cmp     rdx, r14
0x18000d19e  jnb     short loc_18000D1A6
0x18000d1a0  mov     [rdi+20h], r13
0x18000d1a4  jmp     short loc_18000D1C3
0x18000d1a6  mov     r9, r14; SourceSize
0x18000d1a9  mov     rcx, rbx; Destination
0x18000d1ac  call    memcpy_s
0x18000d1b1  mov     [rdi+20h], rbx
0x18000d1b5  add     rbx, r14
0x18000d1b8  jmp     short loc_18000D1BE
0x18000d1ba  mov     [rdi+20h], r13
0x18000d1be  cmp     rbx, rsi
0x18000d1c1  jz      short loc_18000D204
0x18000d1c3  mov     r8, [r12+18h]; Source
0x18000d1c8  test    r8, r8
0x18000d1cb  jz      short loc_18000D204
0x18000d1cd  cmp     [r8], r13w
0x18000d1d1  jz      short loc_18000D204
0x18000d1d3  inc     rbp
0x18000d1d6  cmp     [r8+rbp*2], r13w
0x18000d1db  jnz     short loc_18000D1D3
0x18000d1dd  mov     rdx, rsi
0x18000d1e0  lea     r14, ds:2[rbp*2]
0x18000d1e8  sub     rdx, rbx; DestinationSize
0x18000d1eb  cmp     rdx, r14
0x18000d1ee  jb      short loc_18000D204
0x18000d1f0  mov     r9, r14; SourceSize
0x18000d1f3  mov     rcx, rbx; Destination
0x18000d1f6  call    memcpy_s
0x18000d1fb  mov     [rdi+38h], rbx
0x18000d1ff  add     rbx, r14
0x18000d202  jmp     short loc_18000D208
0x18000d204  mov     [rdi+38h], r13
0x18000d208  sub     rsi, rbx
0x18000d20b  xor     edx, edx; Val
0x18000d20d  mov     r8, rsi; Size
0x18000d210  mov     rcx, rbx; void *
0x18000d213  call    memset_0
0x18000d218  add     rsp, 28h
0x18000d21c  pop     r15
0x18000d21e  pop     r14
0x18000d220  pop     r13
0x18000d222  pop     r12
0x18000d224  pop     rdi
0x18000d225  pop     rsi
0x18000d226  pop     rbp
0x18000d227  pop     rbx
0x18000d228  retn
```
