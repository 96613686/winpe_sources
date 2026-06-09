# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008364`
- end: `0x18000857d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005560`

## callees

- `0x1800028dc`
- `0x180006840`
- `0x180008364`
- `0x180009fe8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000845a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000845a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000844c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000844c`

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
0x180008364  push    rbx
0x180008366  push    rbp
0x180008367  push    rsi
0x180008368  push    rdi
0x180008369  push    r12
0x18000836b  push    r13
0x18000836d  push    r14
0x18000836f  push    r15
0x180008371  sub     rsp, 28h
0x180008375  mov     [rcx+4], r8d
0x180008379  xor     r13d, r13d
0x18000837c  mov     eax, [rdx+8]
0x18000837f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180008383  mov     [rcx+8], eax
0x180008386  mov     rdi, rcx
0x180008389  mov     [rcx+10h], r13
0x18000838d  mov     r12, rdx
0x180008390  movzx   eax, word ptr [rdx+40h]
0x180008394  mov     [rcx+18h], ax
0x180008398  mov     al, [rdx]
0x18000839a  mov     [rcx+1Ah], al
0x18000839d  mov     [rcx+20h], r13
0x1800083a1  mov     rax, [rdx+88h]
0x1800083a8  mov     [rcx+28h], rax
0x1800083ac  mov     rax, [rdx+90h]
0x1800083b3  mov     [rcx+30h], rax
0x1800083b7  mov     [rcx+38h], r13
0x1800083bb  mov     rcx, [rdx+38h]
0x1800083bf  lea     edx, [rbp+2]
0x1800083c2  test    rcx, rcx
0x1800083c5  jnz     short loc_1800083CC
0x1800083c7  mov     r8d, edx
0x1800083ca  jmp     short loc_1800083DC
0x1800083cc  mov     rax, rbp
0x1800083cf  inc     rax
0x1800083d2  cmp     [rcx+rax], r13b
0x1800083d6  jnz     short loc_1800083CF
0x1800083d8  lea     r8, [rax+1]; unsigned __int64
0x1800083dc  mov     rcx, [r12+80h]
0x1800083e4  test    rcx, rcx
0x1800083e7  jz      short loc_1800083F9
0x1800083e9  mov     rax, rbp
0x1800083ec  inc     rax
0x1800083ef  cmp     [rcx+rax], r13b
0x1800083f3  jnz     short loc_1800083EC
0x1800083f5  lea     rdx, [rax+1]
0x1800083f9  mov     rcx, [r12+18h]
0x1800083fe  test    rcx, rcx
0x180008401  jnz     short loc_180008408
0x180008403  lea     eax, [rcx+2]
0x180008406  jmp     short loc_18000841D
0x180008408  mov     rax, rbp
0x18000840b  inc     rax
0x18000840e  cmp     [rcx+rax*2], r13w
0x180008413  jnz     short loc_18000840B
0x180008415  lea     rax, ds:2[rax*2]
0x18000841d  lea     r14, [rdx+rax]
0x180008421  add     r14, r8
0x180008424  lea     rsi, [rdi+48h]
0x180008428  cmp     [rdi+40h], r13
0x18000842c  jz      short loc_180008433
0x18000842e  cmp     [rsi], r14
0x180008431  jnb     short loc_180008467
0x180008433  mov     rdx, r14; dwBytes
0x180008436  mov     ecx, 8; dwFlags
0x18000843b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008440  mov     r15, rax
0x180008443  test    rax, rax
0x180008446  jz      short loc_180008467
0x180008448  mov     rbx, [rdi+40h]
0x18000844c  call    cs:__imp_GetProcessHeap
0x180008452  mov     r8, rbx; lpMem
0x180008455  xor     edx, edx; dwFlags
0x180008457  mov     rcx, rax; hHeap
0x18000845a  call    cs:__imp_HeapFree
0x180008460  mov     [rdi+40h], r15
0x180008464  mov     [rsi], r14
0x180008467  mov     rbx, [rdi+40h]
0x18000846b  test    rbx, rbx
0x18000846e  jz      loc_18000856C
0x180008474  mov     rdx, [rsi]; DestinationSize
0x180008477  lea     rsi, [rdx+rbx]
0x18000847b  cmp     rbx, rsi
0x18000847e  jz      short loc_1800084BE
0x180008480  mov     r8, [r12+38h]; Source
0x180008485  test    r8, r8
0x180008488  jz      short loc_1800084BE
0x18000848a  cmp     [r8], r13b
0x18000848d  jz      short loc_1800084BE
0x18000848f  mov     rax, rbp
0x180008492  inc     rax
0x180008495  cmp     [r8+rax], r13b
0x180008499  jnz     short loc_180008492
0x18000849b  lea     r14, [rax+1]
0x18000849f  cmp     rdx, r14
0x1800084a2  jnb     short loc_1800084AA
0x1800084a4  mov     [rdi+10h], r13
0x1800084a8  jmp     short loc_1800084C7
0x1800084aa  mov     r9, r14; SourceSize
0x1800084ad  mov     rcx, rbx; Destination
0x1800084b0  call    memcpy_s
0x1800084b5  mov     [rdi+10h], rbx
0x1800084b9  add     rbx, r14
0x1800084bc  jmp     short loc_1800084C2
0x1800084be  mov     [rdi+10h], r13
0x1800084c2  cmp     rbx, rsi
0x1800084c5  jz      short loc_18000850E
0x1800084c7  mov     r8, [r12+80h]; Source
0x1800084cf  test    r8, r8
0x1800084d2  jz      short loc_18000850E
0x1800084d4  cmp     [r8], r13b
0x1800084d7  jz      short loc_18000850E
0x1800084d9  mov     rax, rbp
0x1800084dc  inc     rax
0x1800084df  cmp     [r8+rax], r13b
0x1800084e3  jnz     short loc_1800084DC
0x1800084e5  mov     rdx, rsi
0x1800084e8  lea     r14, [rax+1]
0x1800084ec  sub     rdx, rbx; DestinationSize
0x1800084ef  cmp     rdx, r14
0x1800084f2  jnb     short loc_1800084FA
0x1800084f4  mov     [rdi+20h], r13
0x1800084f8  jmp     short loc_180008517
0x1800084fa  mov     r9, r14; SourceSize
0x1800084fd  mov     rcx, rbx; Destination
0x180008500  call    memcpy_s
0x180008505  mov     [rdi+20h], rbx
0x180008509  add     rbx, r14
0x18000850c  jmp     short loc_180008512
0x18000850e  mov     [rdi+20h], r13
0x180008512  cmp     rbx, rsi
0x180008515  jz      short loc_180008558
0x180008517  mov     r8, [r12+18h]; Source
0x18000851c  test    r8, r8
0x18000851f  jz      short loc_180008558
0x180008521  cmp     [r8], r13w
0x180008525  jz      short loc_180008558
0x180008527  inc     rbp
0x18000852a  cmp     [r8+rbp*2], r13w
0x18000852f  jnz     short loc_180008527
0x180008531  mov     rdx, rsi
0x180008534  lea     r14, ds:2[rbp*2]
0x18000853c  sub     rdx, rbx; DestinationSize
0x18000853f  cmp     rdx, r14
0x180008542  jb      short loc_180008558
0x180008544  mov     r9, r14; SourceSize
0x180008547  mov     rcx, rbx; Destination
0x18000854a  call    memcpy_s
0x18000854f  mov     [rdi+38h], rbx
0x180008553  add     rbx, r14
0x180008556  jmp     short loc_18000855C
0x180008558  mov     [rdi+38h], r13
0x18000855c  sub     rsi, rbx
0x18000855f  xor     edx, edx; Val
0x180008561  mov     r8, rsi; Size
0x180008564  mov     rcx, rbx; void *
0x180008567  call    memset_0
0x18000856c  add     rsp, 28h
0x180008570  pop     r15
0x180008572  pop     r14
0x180008574  pop     r13
0x180008576  pop     r12
0x180008578  pop     rdi
0x180008579  pop     rsi
0x18000857a  pop     rbp
0x18000857b  pop     rbx
0x18000857c  retn
```
