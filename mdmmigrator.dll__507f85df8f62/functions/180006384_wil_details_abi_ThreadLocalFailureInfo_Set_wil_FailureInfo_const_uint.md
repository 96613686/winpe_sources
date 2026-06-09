# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006384`
- end: `0x18000659d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004e50`

## callees

- `0x180002cbc`
- `0x180005ea8`
- `0x180006384`
- `0x1800075ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000646c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000646c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000647a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000647a`

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
0x180006384  push    rbx
0x180006386  push    rbp
0x180006387  push    rsi
0x180006388  push    rdi
0x180006389  push    r12
0x18000638b  push    r13
0x18000638d  push    r14
0x18000638f  push    r15
0x180006391  sub     rsp, 28h
0x180006395  mov     [rcx+4], r8d
0x180006399  xor     r13d, r13d
0x18000639c  mov     eax, [rdx+8]
0x18000639f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800063a3  mov     [rcx+8], eax
0x1800063a6  mov     rdi, rcx
0x1800063a9  mov     [rcx+10h], r13
0x1800063ad  mov     r12, rdx
0x1800063b0  movzx   eax, word ptr [rdx+40h]
0x1800063b4  mov     [rcx+18h], ax
0x1800063b8  mov     al, [rdx]
0x1800063ba  mov     [rcx+1Ah], al
0x1800063bd  mov     [rcx+20h], r13
0x1800063c1  mov     rax, [rdx+88h]
0x1800063c8  mov     [rcx+28h], rax
0x1800063cc  mov     rax, [rdx+90h]
0x1800063d3  mov     [rcx+30h], rax
0x1800063d7  mov     [rcx+38h], r13
0x1800063db  mov     rcx, [rdx+38h]
0x1800063df  lea     edx, [rbp+2]
0x1800063e2  test    rcx, rcx
0x1800063e5  jnz     short loc_1800063EC
0x1800063e7  mov     r8d, edx
0x1800063ea  jmp     short loc_1800063FC
0x1800063ec  mov     rax, rbp
0x1800063ef  inc     rax
0x1800063f2  cmp     [rcx+rax], r13b
0x1800063f6  jnz     short loc_1800063EF
0x1800063f8  lea     r8, [rax+1]; unsigned __int64
0x1800063fc  mov     rcx, [r12+80h]
0x180006404  test    rcx, rcx
0x180006407  jz      short loc_180006419
0x180006409  mov     rax, rbp
0x18000640c  inc     rax
0x18000640f  cmp     [rcx+rax], r13b
0x180006413  jnz     short loc_18000640C
0x180006415  lea     rdx, [rax+1]
0x180006419  mov     rcx, [r12+18h]
0x18000641e  test    rcx, rcx
0x180006421  jnz     short loc_180006428
0x180006423  lea     eax, [rcx+2]
0x180006426  jmp     short loc_18000643D
0x180006428  mov     rax, rbp
0x18000642b  inc     rax
0x18000642e  cmp     [rcx+rax*2], r13w
0x180006433  jnz     short loc_18000642B
0x180006435  lea     rax, ds:2[rax*2]
0x18000643d  lea     r14, [rdx+rax]
0x180006441  add     r14, r8
0x180006444  lea     rsi, [rdi+48h]
0x180006448  cmp     [rdi+40h], r13
0x18000644c  jz      short loc_180006453
0x18000644e  cmp     [rsi], r14
0x180006451  jnb     short loc_180006487
0x180006453  mov     rdx, r14; dwBytes
0x180006456  mov     ecx, 8; dwFlags
0x18000645b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006460  mov     r15, rax
0x180006463  test    rax, rax
0x180006466  jz      short loc_180006487
0x180006468  mov     rbx, [rdi+40h]
0x18000646c  call    cs:__imp_GetProcessHeap
0x180006472  mov     r8, rbx; lpMem
0x180006475  xor     edx, edx; dwFlags
0x180006477  mov     rcx, rax; hHeap
0x18000647a  call    cs:__imp_HeapFree
0x180006480  mov     [rdi+40h], r15
0x180006484  mov     [rsi], r14
0x180006487  mov     rbx, [rdi+40h]
0x18000648b  test    rbx, rbx
0x18000648e  jz      loc_18000658C
0x180006494  mov     rdx, [rsi]; DestinationSize
0x180006497  lea     rsi, [rdx+rbx]
0x18000649b  cmp     rbx, rsi
0x18000649e  jz      short loc_1800064DE
0x1800064a0  mov     r8, [r12+38h]; Source
0x1800064a5  test    r8, r8
0x1800064a8  jz      short loc_1800064DE
0x1800064aa  cmp     [r8], r13b
0x1800064ad  jz      short loc_1800064DE
0x1800064af  mov     rax, rbp
0x1800064b2  inc     rax
0x1800064b5  cmp     [r8+rax], r13b
0x1800064b9  jnz     short loc_1800064B2
0x1800064bb  lea     r14, [rax+1]
0x1800064bf  cmp     rdx, r14
0x1800064c2  jnb     short loc_1800064CA
0x1800064c4  mov     [rdi+10h], r13
0x1800064c8  jmp     short loc_1800064E7
0x1800064ca  mov     r9, r14; SourceSize
0x1800064cd  mov     rcx, rbx; Destination
0x1800064d0  call    memcpy_s
0x1800064d5  mov     [rdi+10h], rbx
0x1800064d9  add     rbx, r14
0x1800064dc  jmp     short loc_1800064E2
0x1800064de  mov     [rdi+10h], r13
0x1800064e2  cmp     rbx, rsi
0x1800064e5  jz      short loc_18000652E
0x1800064e7  mov     r8, [r12+80h]; Source
0x1800064ef  test    r8, r8
0x1800064f2  jz      short loc_18000652E
0x1800064f4  cmp     [r8], r13b
0x1800064f7  jz      short loc_18000652E
0x1800064f9  mov     rax, rbp
0x1800064fc  inc     rax
0x1800064ff  cmp     [r8+rax], r13b
0x180006503  jnz     short loc_1800064FC
0x180006505  mov     rdx, rsi
0x180006508  lea     r14, [rax+1]
0x18000650c  sub     rdx, rbx; DestinationSize
0x18000650f  cmp     rdx, r14
0x180006512  jnb     short loc_18000651A
0x180006514  mov     [rdi+20h], r13
0x180006518  jmp     short loc_180006537
0x18000651a  mov     r9, r14; SourceSize
0x18000651d  mov     rcx, rbx; Destination
0x180006520  call    memcpy_s
0x180006525  mov     [rdi+20h], rbx
0x180006529  add     rbx, r14
0x18000652c  jmp     short loc_180006532
0x18000652e  mov     [rdi+20h], r13
0x180006532  cmp     rbx, rsi
0x180006535  jz      short loc_180006578
0x180006537  mov     r8, [r12+18h]; Source
0x18000653c  test    r8, r8
0x18000653f  jz      short loc_180006578
0x180006541  cmp     [r8], r13w
0x180006545  jz      short loc_180006578
0x180006547  inc     rbp
0x18000654a  cmp     [r8+rbp*2], r13w
0x18000654f  jnz     short loc_180006547
0x180006551  mov     rdx, rsi
0x180006554  lea     r14, ds:2[rbp*2]
0x18000655c  sub     rdx, rbx; DestinationSize
0x18000655f  cmp     rdx, r14
0x180006562  jb      short loc_180006578
0x180006564  mov     r9, r14; SourceSize
0x180006567  mov     rcx, rbx; Destination
0x18000656a  call    memcpy_s
0x18000656f  mov     [rdi+38h], rbx
0x180006573  add     rbx, r14
0x180006576  jmp     short loc_18000657C
0x180006578  mov     [rdi+38h], r13
0x18000657c  sub     rsi, rbx
0x18000657f  xor     edx, edx; Val
0x180006581  mov     r8, rsi; Size
0x180006584  mov     rcx, rbx; void *
0x180006587  call    memset_0
0x18000658c  add     rsp, 28h
0x180006590  pop     r15
0x180006592  pop     r14
0x180006594  pop     r13
0x180006596  pop     r12
0x180006598  pop     rdi
0x180006599  pop     rsi
0x18000659a  pop     rbp
0x18000659b  pop     rbx
0x18000659c  retn
```
