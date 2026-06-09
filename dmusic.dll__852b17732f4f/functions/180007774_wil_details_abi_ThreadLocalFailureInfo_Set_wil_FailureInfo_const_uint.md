# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007774`
- end: `0x18000798d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004b90`

## callees

- `0x1800021a8`
- `0x18000603c`
- `0x180007774`
- `0x180009458`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000786a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000786a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000785c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000785c`

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
0x180007774  push    rbx
0x180007776  push    rbp
0x180007777  push    rsi
0x180007778  push    rdi
0x180007779  push    r12
0x18000777b  push    r13
0x18000777d  push    r14
0x18000777f  push    r15
0x180007781  sub     rsp, 28h
0x180007785  mov     [rcx+4], r8d
0x180007789  xor     r13d, r13d
0x18000778c  mov     eax, [rdx+8]
0x18000778f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007793  mov     [rcx+8], eax
0x180007796  mov     rdi, rcx
0x180007799  mov     [rcx+10h], r13
0x18000779d  mov     r12, rdx
0x1800077a0  movzx   eax, word ptr [rdx+40h]
0x1800077a4  mov     [rcx+18h], ax
0x1800077a8  mov     al, [rdx]
0x1800077aa  mov     [rcx+1Ah], al
0x1800077ad  mov     [rcx+20h], r13
0x1800077b1  mov     rax, [rdx+88h]
0x1800077b8  mov     [rcx+28h], rax
0x1800077bc  mov     rax, [rdx+90h]
0x1800077c3  mov     [rcx+30h], rax
0x1800077c7  mov     [rcx+38h], r13
0x1800077cb  mov     rcx, [rdx+38h]
0x1800077cf  lea     edx, [rbp+2]
0x1800077d2  test    rcx, rcx
0x1800077d5  jnz     short loc_1800077DC
0x1800077d7  mov     r8d, edx
0x1800077da  jmp     short loc_1800077EC
0x1800077dc  mov     rax, rbp
0x1800077df  inc     rax
0x1800077e2  cmp     [rcx+rax], r13b
0x1800077e6  jnz     short loc_1800077DF
0x1800077e8  lea     r8, [rax+1]; unsigned __int64
0x1800077ec  mov     rcx, [r12+80h]
0x1800077f4  test    rcx, rcx
0x1800077f7  jz      short loc_180007809
0x1800077f9  mov     rax, rbp
0x1800077fc  inc     rax
0x1800077ff  cmp     [rcx+rax], r13b
0x180007803  jnz     short loc_1800077FC
0x180007805  lea     rdx, [rax+1]
0x180007809  mov     rcx, [r12+18h]
0x18000780e  test    rcx, rcx
0x180007811  jnz     short loc_180007818
0x180007813  lea     eax, [rcx+2]
0x180007816  jmp     short loc_18000782D
0x180007818  mov     rax, rbp
0x18000781b  inc     rax
0x18000781e  cmp     [rcx+rax*2], r13w
0x180007823  jnz     short loc_18000781B
0x180007825  lea     rax, ds:2[rax*2]
0x18000782d  lea     r14, [rdx+rax]
0x180007831  add     r14, r8
0x180007834  lea     rsi, [rdi+48h]
0x180007838  cmp     [rdi+40h], r13
0x18000783c  jz      short loc_180007843
0x18000783e  cmp     [rsi], r14
0x180007841  jnb     short loc_180007877
0x180007843  mov     rdx, r14; dwBytes
0x180007846  mov     ecx, 8; dwFlags
0x18000784b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007850  mov     r15, rax
0x180007853  test    rax, rax
0x180007856  jz      short loc_180007877
0x180007858  mov     rbx, [rdi+40h]
0x18000785c  call    cs:__imp_GetProcessHeap
0x180007862  mov     r8, rbx; lpMem
0x180007865  xor     edx, edx; dwFlags
0x180007867  mov     rcx, rax; hHeap
0x18000786a  call    cs:__imp_HeapFree
0x180007870  mov     [rdi+40h], r15
0x180007874  mov     [rsi], r14
0x180007877  mov     rbx, [rdi+40h]
0x18000787b  test    rbx, rbx
0x18000787e  jz      loc_18000797C
0x180007884  mov     rdx, [rsi]; DestinationSize
0x180007887  lea     rsi, [rdx+rbx]
0x18000788b  cmp     rbx, rsi
0x18000788e  jz      short loc_1800078CE
0x180007890  mov     r8, [r12+38h]; Source
0x180007895  test    r8, r8
0x180007898  jz      short loc_1800078CE
0x18000789a  cmp     [r8], r13b
0x18000789d  jz      short loc_1800078CE
0x18000789f  mov     rax, rbp
0x1800078a2  inc     rax
0x1800078a5  cmp     [r8+rax], r13b
0x1800078a9  jnz     short loc_1800078A2
0x1800078ab  lea     r14, [rax+1]
0x1800078af  cmp     rdx, r14
0x1800078b2  jnb     short loc_1800078BA
0x1800078b4  mov     [rdi+10h], r13
0x1800078b8  jmp     short loc_1800078D7
0x1800078ba  mov     r9, r14; SourceSize
0x1800078bd  mov     rcx, rbx; Destination
0x1800078c0  call    memcpy_s
0x1800078c5  mov     [rdi+10h], rbx
0x1800078c9  add     rbx, r14
0x1800078cc  jmp     short loc_1800078D2
0x1800078ce  mov     [rdi+10h], r13
0x1800078d2  cmp     rbx, rsi
0x1800078d5  jz      short loc_18000791E
0x1800078d7  mov     r8, [r12+80h]; Source
0x1800078df  test    r8, r8
0x1800078e2  jz      short loc_18000791E
0x1800078e4  cmp     [r8], r13b
0x1800078e7  jz      short loc_18000791E
0x1800078e9  mov     rax, rbp
0x1800078ec  inc     rax
0x1800078ef  cmp     [r8+rax], r13b
0x1800078f3  jnz     short loc_1800078EC
0x1800078f5  mov     rdx, rsi
0x1800078f8  lea     r14, [rax+1]
0x1800078fc  sub     rdx, rbx; DestinationSize
0x1800078ff  cmp     rdx, r14
0x180007902  jnb     short loc_18000790A
0x180007904  mov     [rdi+20h], r13
0x180007908  jmp     short loc_180007927
0x18000790a  mov     r9, r14; SourceSize
0x18000790d  mov     rcx, rbx; Destination
0x180007910  call    memcpy_s
0x180007915  mov     [rdi+20h], rbx
0x180007919  add     rbx, r14
0x18000791c  jmp     short loc_180007922
0x18000791e  mov     [rdi+20h], r13
0x180007922  cmp     rbx, rsi
0x180007925  jz      short loc_180007968
0x180007927  mov     r8, [r12+18h]; Source
0x18000792c  test    r8, r8
0x18000792f  jz      short loc_180007968
0x180007931  cmp     [r8], r13w
0x180007935  jz      short loc_180007968
0x180007937  inc     rbp
0x18000793a  cmp     [r8+rbp*2], r13w
0x18000793f  jnz     short loc_180007937
0x180007941  mov     rdx, rsi
0x180007944  lea     r14, ds:2[rbp*2]
0x18000794c  sub     rdx, rbx; DestinationSize
0x18000794f  cmp     rdx, r14
0x180007952  jb      short loc_180007968
0x180007954  mov     r9, r14; SourceSize
0x180007957  mov     rcx, rbx; Destination
0x18000795a  call    memcpy_s
0x18000795f  mov     [rdi+38h], rbx
0x180007963  add     rbx, r14
0x180007966  jmp     short loc_18000796C
0x180007968  mov     [rdi+38h], r13
0x18000796c  sub     rsi, rbx
0x18000796f  xor     edx, edx; Val
0x180007971  mov     r8, rsi; Size
0x180007974  mov     rcx, rbx; void *
0x180007977  call    memset_0
0x18000797c  add     rsp, 28h
0x180007980  pop     r15
0x180007982  pop     r14
0x180007984  pop     r13
0x180007986  pop     r12
0x180007988  pop     rdi
0x180007989  pop     rsi
0x18000798a  pop     rbp
0x18000798b  pop     rbx
0x18000798c  retn
```
