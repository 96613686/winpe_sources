# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005320`
- end: `0x180005539`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003de0`

## callees

- `0x180002722`
- `0x180004e28`
- `0x180005320`
- `0x1800062b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005408`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005416`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005416`

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
0x180005320  push    rbx
0x180005322  push    rbp
0x180005323  push    rsi
0x180005324  push    rdi
0x180005325  push    r12
0x180005327  push    r13
0x180005329  push    r14
0x18000532b  push    r15
0x18000532d  sub     rsp, 28h
0x180005331  mov     [rcx+4], r8d
0x180005335  xor     r13d, r13d
0x180005338  mov     eax, [rdx+8]
0x18000533b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000533f  mov     [rcx+8], eax
0x180005342  mov     rdi, rcx
0x180005345  mov     [rcx+10h], r13
0x180005349  mov     r12, rdx
0x18000534c  movzx   eax, word ptr [rdx+40h]
0x180005350  mov     [rcx+18h], ax
0x180005354  mov     al, [rdx]
0x180005356  mov     [rcx+1Ah], al
0x180005359  mov     [rcx+20h], r13
0x18000535d  mov     rax, [rdx+88h]
0x180005364  mov     [rcx+28h], rax
0x180005368  mov     rax, [rdx+90h]
0x18000536f  mov     [rcx+30h], rax
0x180005373  mov     [rcx+38h], r13
0x180005377  mov     rcx, [rdx+38h]
0x18000537b  lea     edx, [rbp+2]
0x18000537e  test    rcx, rcx
0x180005381  jnz     short loc_180005388
0x180005383  mov     r8d, edx
0x180005386  jmp     short loc_180005398
0x180005388  mov     rax, rbp
0x18000538b  inc     rax
0x18000538e  cmp     [rcx+rax], r13b
0x180005392  jnz     short loc_18000538B
0x180005394  lea     r8, [rax+1]; unsigned __int64
0x180005398  mov     rcx, [r12+80h]
0x1800053a0  test    rcx, rcx
0x1800053a3  jz      short loc_1800053B5
0x1800053a5  mov     rax, rbp
0x1800053a8  inc     rax
0x1800053ab  cmp     [rcx+rax], r13b
0x1800053af  jnz     short loc_1800053A8
0x1800053b1  lea     rdx, [rax+1]
0x1800053b5  mov     rcx, [r12+18h]
0x1800053ba  test    rcx, rcx
0x1800053bd  jnz     short loc_1800053C4
0x1800053bf  lea     eax, [rcx+2]
0x1800053c2  jmp     short loc_1800053D9
0x1800053c4  mov     rax, rbp
0x1800053c7  inc     rax
0x1800053ca  cmp     [rcx+rax*2], r13w
0x1800053cf  jnz     short loc_1800053C7
0x1800053d1  lea     rax, ds:2[rax*2]
0x1800053d9  lea     r14, [rdx+rax]
0x1800053dd  add     r14, r8
0x1800053e0  lea     rsi, [rdi+48h]
0x1800053e4  cmp     [rdi+40h], r13
0x1800053e8  jz      short loc_1800053EF
0x1800053ea  cmp     [rsi], r14
0x1800053ed  jnb     short loc_180005423
0x1800053ef  mov     rdx, r14; dwBytes
0x1800053f2  mov     ecx, 8; dwFlags
0x1800053f7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800053fc  mov     r15, rax
0x1800053ff  test    rax, rax
0x180005402  jz      short loc_180005423
0x180005404  mov     rbx, [rdi+40h]
0x180005408  call    cs:__imp_GetProcessHeap
0x18000540e  mov     r8, rbx; lpMem
0x180005411  xor     edx, edx; dwFlags
0x180005413  mov     rcx, rax; hHeap
0x180005416  call    cs:__imp_HeapFree
0x18000541c  mov     [rdi+40h], r15
0x180005420  mov     [rsi], r14
0x180005423  mov     rbx, [rdi+40h]
0x180005427  test    rbx, rbx
0x18000542a  jz      loc_180005528
0x180005430  mov     rdx, [rsi]; DestinationSize
0x180005433  lea     rsi, [rdx+rbx]
0x180005437  cmp     rbx, rsi
0x18000543a  jz      short loc_18000547A
0x18000543c  mov     r8, [r12+38h]; Source
0x180005441  test    r8, r8
0x180005444  jz      short loc_18000547A
0x180005446  cmp     [r8], r13b
0x180005449  jz      short loc_18000547A
0x18000544b  mov     rax, rbp
0x18000544e  inc     rax
0x180005451  cmp     [r8+rax], r13b
0x180005455  jnz     short loc_18000544E
0x180005457  lea     r14, [rax+1]
0x18000545b  cmp     rdx, r14
0x18000545e  jnb     short loc_180005466
0x180005460  mov     [rdi+10h], r13
0x180005464  jmp     short loc_180005483
0x180005466  mov     r9, r14; SourceSize
0x180005469  mov     rcx, rbx; Destination
0x18000546c  call    memcpy_s
0x180005471  mov     [rdi+10h], rbx
0x180005475  add     rbx, r14
0x180005478  jmp     short loc_18000547E
0x18000547a  mov     [rdi+10h], r13
0x18000547e  cmp     rbx, rsi
0x180005481  jz      short loc_1800054CA
0x180005483  mov     r8, [r12+80h]; Source
0x18000548b  test    r8, r8
0x18000548e  jz      short loc_1800054CA
0x180005490  cmp     [r8], r13b
0x180005493  jz      short loc_1800054CA
0x180005495  mov     rax, rbp
0x180005498  inc     rax
0x18000549b  cmp     [r8+rax], r13b
0x18000549f  jnz     short loc_180005498
0x1800054a1  mov     rdx, rsi
0x1800054a4  lea     r14, [rax+1]
0x1800054a8  sub     rdx, rbx; DestinationSize
0x1800054ab  cmp     rdx, r14
0x1800054ae  jnb     short loc_1800054B6
0x1800054b0  mov     [rdi+20h], r13
0x1800054b4  jmp     short loc_1800054D3
0x1800054b6  mov     r9, r14; SourceSize
0x1800054b9  mov     rcx, rbx; Destination
0x1800054bc  call    memcpy_s
0x1800054c1  mov     [rdi+20h], rbx
0x1800054c5  add     rbx, r14
0x1800054c8  jmp     short loc_1800054CE
0x1800054ca  mov     [rdi+20h], r13
0x1800054ce  cmp     rbx, rsi
0x1800054d1  jz      short loc_180005514
0x1800054d3  mov     r8, [r12+18h]; Source
0x1800054d8  test    r8, r8
0x1800054db  jz      short loc_180005514
0x1800054dd  cmp     [r8], r13w
0x1800054e1  jz      short loc_180005514
0x1800054e3  inc     rbp
0x1800054e6  cmp     [r8+rbp*2], r13w
0x1800054eb  jnz     short loc_1800054E3
0x1800054ed  mov     rdx, rsi
0x1800054f0  lea     r14, ds:2[rbp*2]
0x1800054f8  sub     rdx, rbx; DestinationSize
0x1800054fb  cmp     rdx, r14
0x1800054fe  jb      short loc_180005514
0x180005500  mov     r9, r14; SourceSize
0x180005503  mov     rcx, rbx; Destination
0x180005506  call    memcpy_s
0x18000550b  mov     [rdi+38h], rbx
0x18000550f  add     rbx, r14
0x180005512  jmp     short loc_180005518
0x180005514  mov     [rdi+38h], r13
0x180005518  sub     rsi, rbx
0x18000551b  xor     edx, edx; Val
0x18000551d  mov     r8, rsi; Size
0x180005520  mov     rcx, rbx; void *
0x180005523  call    memset_0
0x180005528  add     rsp, 28h
0x18000552c  pop     r15
0x18000552e  pop     r14
0x180005530  pop     r13
0x180005532  pop     r12
0x180005534  pop     rdi
0x180005535  pop     rsi
0x180005536  pop     rbp
0x180005537  pop     rbx
0x180005538  retn
```
