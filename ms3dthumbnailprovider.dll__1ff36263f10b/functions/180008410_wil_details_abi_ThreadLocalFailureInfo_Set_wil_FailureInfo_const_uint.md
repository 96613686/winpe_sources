# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008410`
- end: `0x180008629`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800063a0`

## callees

- `0x180002954`
- `0x180007b60`
- `0x180008410`
- `0x180009c08`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008506`
- `KERNEL32!HeapFree` at `0x180008506`
- `KERNEL32!GetProcessHeap` at `0x1800084f8`
- `KERNEL32!GetProcessHeap` at `0x1800084f8`

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
0x180008410  push    rbx
0x180008412  push    rbp
0x180008413  push    rsi
0x180008414  push    rdi
0x180008415  push    r12
0x180008417  push    r13
0x180008419  push    r14
0x18000841b  push    r15
0x18000841d  sub     rsp, 28h
0x180008421  mov     [rcx+4], r8d
0x180008425  xor     r13d, r13d
0x180008428  mov     eax, [rdx+8]
0x18000842b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000842f  mov     [rcx+8], eax
0x180008432  mov     rdi, rcx
0x180008435  mov     [rcx+10h], r13
0x180008439  mov     r12, rdx
0x18000843c  movzx   eax, word ptr [rdx+40h]
0x180008440  mov     [rcx+18h], ax
0x180008444  mov     al, [rdx]
0x180008446  mov     [rcx+1Ah], al
0x180008449  mov     [rcx+20h], r13
0x18000844d  mov     rax, [rdx+88h]
0x180008454  mov     [rcx+28h], rax
0x180008458  mov     rax, [rdx+90h]
0x18000845f  mov     [rcx+30h], rax
0x180008463  mov     [rcx+38h], r13
0x180008467  mov     rcx, [rdx+38h]
0x18000846b  lea     edx, [rbp+2]
0x18000846e  test    rcx, rcx
0x180008471  jnz     short loc_180008478
0x180008473  mov     r8d, edx
0x180008476  jmp     short loc_180008488
0x180008478  mov     rax, rbp
0x18000847b  inc     rax
0x18000847e  cmp     [rcx+rax], r13b
0x180008482  jnz     short loc_18000847B
0x180008484  lea     r8, [rax+1]; unsigned __int64
0x180008488  mov     rcx, [r12+80h]
0x180008490  test    rcx, rcx
0x180008493  jz      short loc_1800084A5
0x180008495  mov     rax, rbp
0x180008498  inc     rax
0x18000849b  cmp     [rcx+rax], r13b
0x18000849f  jnz     short loc_180008498
0x1800084a1  lea     rdx, [rax+1]
0x1800084a5  mov     rcx, [r12+18h]
0x1800084aa  test    rcx, rcx
0x1800084ad  jnz     short loc_1800084B4
0x1800084af  lea     eax, [rcx+2]
0x1800084b2  jmp     short loc_1800084C9
0x1800084b4  mov     rax, rbp
0x1800084b7  inc     rax
0x1800084ba  cmp     [rcx+rax*2], r13w
0x1800084bf  jnz     short loc_1800084B7
0x1800084c1  lea     rax, ds:2[rax*2]
0x1800084c9  lea     r14, [rdx+rax]
0x1800084cd  add     r14, r8
0x1800084d0  lea     rsi, [rdi+48h]
0x1800084d4  cmp     [rdi+40h], r13
0x1800084d8  jz      short loc_1800084DF
0x1800084da  cmp     [rsi], r14
0x1800084dd  jnb     short loc_180008513
0x1800084df  mov     rdx, r14; dwBytes
0x1800084e2  mov     ecx, 8; dwFlags
0x1800084e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800084ec  mov     r15, rax
0x1800084ef  test    rax, rax
0x1800084f2  jz      short loc_180008513
0x1800084f4  mov     rbx, [rdi+40h]
0x1800084f8  call    cs:__imp_GetProcessHeap
0x1800084fe  mov     r8, rbx; lpMem
0x180008501  xor     edx, edx; dwFlags
0x180008503  mov     rcx, rax; hHeap
0x180008506  call    cs:__imp_HeapFree
0x18000850c  mov     [rdi+40h], r15
0x180008510  mov     [rsi], r14
0x180008513  mov     rbx, [rdi+40h]
0x180008517  test    rbx, rbx
0x18000851a  jz      loc_180008618
0x180008520  mov     rdx, [rsi]; DestinationSize
0x180008523  lea     rsi, [rdx+rbx]
0x180008527  cmp     rbx, rsi
0x18000852a  jz      short loc_18000856A
0x18000852c  mov     r8, [r12+38h]; Source
0x180008531  test    r8, r8
0x180008534  jz      short loc_18000856A
0x180008536  cmp     [r8], r13b
0x180008539  jz      short loc_18000856A
0x18000853b  mov     rax, rbp
0x18000853e  inc     rax
0x180008541  cmp     [r8+rax], r13b
0x180008545  jnz     short loc_18000853E
0x180008547  lea     r14, [rax+1]
0x18000854b  cmp     rdx, r14
0x18000854e  jnb     short loc_180008556
0x180008550  mov     [rdi+10h], r13
0x180008554  jmp     short loc_180008573
0x180008556  mov     r9, r14; SourceSize
0x180008559  mov     rcx, rbx; Destination
0x18000855c  call    memcpy_s
0x180008561  mov     [rdi+10h], rbx
0x180008565  add     rbx, r14
0x180008568  jmp     short loc_18000856E
0x18000856a  mov     [rdi+10h], r13
0x18000856e  cmp     rbx, rsi
0x180008571  jz      short loc_1800085BA
0x180008573  mov     r8, [r12+80h]; Source
0x18000857b  test    r8, r8
0x18000857e  jz      short loc_1800085BA
0x180008580  cmp     [r8], r13b
0x180008583  jz      short loc_1800085BA
0x180008585  mov     rax, rbp
0x180008588  inc     rax
0x18000858b  cmp     [r8+rax], r13b
0x18000858f  jnz     short loc_180008588
0x180008591  mov     rdx, rsi
0x180008594  lea     r14, [rax+1]
0x180008598  sub     rdx, rbx; DestinationSize
0x18000859b  cmp     rdx, r14
0x18000859e  jnb     short loc_1800085A6
0x1800085a0  mov     [rdi+20h], r13
0x1800085a4  jmp     short loc_1800085C3
0x1800085a6  mov     r9, r14; SourceSize
0x1800085a9  mov     rcx, rbx; Destination
0x1800085ac  call    memcpy_s
0x1800085b1  mov     [rdi+20h], rbx
0x1800085b5  add     rbx, r14
0x1800085b8  jmp     short loc_1800085BE
0x1800085ba  mov     [rdi+20h], r13
0x1800085be  cmp     rbx, rsi
0x1800085c1  jz      short loc_180008604
0x1800085c3  mov     r8, [r12+18h]; Source
0x1800085c8  test    r8, r8
0x1800085cb  jz      short loc_180008604
0x1800085cd  cmp     [r8], r13w
0x1800085d1  jz      short loc_180008604
0x1800085d3  inc     rbp
0x1800085d6  cmp     [r8+rbp*2], r13w
0x1800085db  jnz     short loc_1800085D3
0x1800085dd  mov     rdx, rsi
0x1800085e0  lea     r14, ds:2[rbp*2]
0x1800085e8  sub     rdx, rbx; DestinationSize
0x1800085eb  cmp     rdx, r14
0x1800085ee  jb      short loc_180008604
0x1800085f0  mov     r9, r14; SourceSize
0x1800085f3  mov     rcx, rbx; Destination
0x1800085f6  call    memcpy_s
0x1800085fb  mov     [rdi+38h], rbx
0x1800085ff  add     rbx, r14
0x180008602  jmp     short loc_180008608
0x180008604  mov     [rdi+38h], r13
0x180008608  sub     rsi, rbx
0x18000860b  xor     edx, edx; Val
0x18000860d  mov     r8, rsi; Size
0x180008610  mov     rcx, rbx; void *
0x180008613  call    memset_0
0x180008618  add     rsp, 28h
0x18000861c  pop     r15
0x18000861e  pop     r14
0x180008620  pop     r13
0x180008622  pop     r12
0x180008624  pop     rdi
0x180008625  pop     rsi
0x180008626  pop     rbp
0x180008627  pop     rbx
0x180008628  retn
```
