# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009648`
- end: `0x180009864`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800061f0`

## callees

- `0x180008038`
- `0x180009648`
- `0x18000ccde`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009794`
- `msvcrt!memcpy_s` at `0x1800097e5`
- `msvcrt!memcpy_s` at `0x180009830`
- `msvcrt!memcpy_s` at `0x180009794`
- `msvcrt!memcpy_s` at `0x1800097e5`
- `msvcrt!memcpy_s` at `0x180009830`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009730`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009730`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000973e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000973e`

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
0x180009648  push    rbx
0x18000964a  push    rbp
0x18000964b  push    rsi
0x18000964c  push    rdi
0x18000964d  push    r12
0x18000964f  push    r13
0x180009651  push    r14
0x180009653  push    r15
0x180009655  sub     rsp, 28h
0x180009659  mov     [rcx+4], r8d
0x18000965d  xor     r13d, r13d
0x180009660  mov     eax, [rdx+8]
0x180009663  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009667  mov     [rcx+8], eax
0x18000966a  mov     rdi, rcx
0x18000966d  mov     [rcx+10h], r13
0x180009671  mov     r12, rdx
0x180009674  movzx   eax, word ptr [rdx+40h]
0x180009678  mov     [rcx+18h], ax
0x18000967c  mov     al, [rdx]
0x18000967e  mov     [rcx+1Ah], al
0x180009681  mov     [rcx+20h], r13
0x180009685  mov     rax, [rdx+88h]
0x18000968c  mov     [rcx+28h], rax
0x180009690  mov     rax, [rdx+90h]
0x180009697  mov     [rcx+30h], rax
0x18000969b  mov     [rcx+38h], r13
0x18000969f  mov     rcx, [rdx+38h]
0x1800096a3  lea     edx, [rbp+2]
0x1800096a6  test    rcx, rcx
0x1800096a9  jnz     short loc_1800096B0
0x1800096ab  mov     r8d, edx
0x1800096ae  jmp     short loc_1800096C0
0x1800096b0  mov     rax, rbp
0x1800096b3  inc     rax
0x1800096b6  cmp     [rcx+rax], r13b
0x1800096ba  jnz     short loc_1800096B3
0x1800096bc  lea     r8, [rax+1]; unsigned __int64
0x1800096c0  mov     rcx, [r12+80h]
0x1800096c8  test    rcx, rcx
0x1800096cb  jz      short loc_1800096DD
0x1800096cd  mov     rax, rbp
0x1800096d0  inc     rax
0x1800096d3  cmp     [rcx+rax], r13b
0x1800096d7  jnz     short loc_1800096D0
0x1800096d9  lea     rdx, [rax+1]
0x1800096dd  mov     rcx, [r12+18h]
0x1800096e2  test    rcx, rcx
0x1800096e5  jnz     short loc_1800096EC
0x1800096e7  lea     eax, [rcx+2]
0x1800096ea  jmp     short loc_180009701
0x1800096ec  mov     rax, rbp
0x1800096ef  inc     rax
0x1800096f2  cmp     [rcx+rax*2], r13w
0x1800096f7  jnz     short loc_1800096EF
0x1800096f9  lea     rax, ds:2[rax*2]
0x180009701  lea     r14, [rdx+rax]
0x180009705  add     r14, r8
0x180009708  lea     rsi, [rdi+48h]
0x18000970c  cmp     [rdi+40h], r13
0x180009710  jz      short loc_180009717
0x180009712  cmp     [rsi], r14
0x180009715  jnb     short loc_18000974B
0x180009717  mov     rdx, r14; dwBytes
0x18000971a  mov     ecx, 8; dwFlags
0x18000971f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009724  mov     r15, rax
0x180009727  test    rax, rax
0x18000972a  jz      short loc_18000974B
0x18000972c  mov     rbx, [rdi+40h]
0x180009730  call    cs:__imp_GetProcessHeap
0x180009736  mov     r8, rbx; lpMem
0x180009739  xor     edx, edx; dwFlags
0x18000973b  mov     rcx, rax; hHeap
0x18000973e  call    cs:__imp_HeapFree
0x180009744  mov     [rdi+40h], r15
0x180009748  mov     [rsi], r14
0x18000974b  mov     rbx, [rdi+40h]
0x18000974f  test    rbx, rbx
0x180009752  jz      loc_180009853
0x180009758  mov     rdx, [rsi]; DestinationSize
0x18000975b  lea     rsi, [rdx+rbx]
0x18000975f  cmp     rbx, rsi
0x180009762  jz      short loc_1800097A3
0x180009764  mov     r8, [r12+38h]; Source
0x180009769  test    r8, r8
0x18000976c  jz      short loc_1800097A3
0x18000976e  cmp     [r8], r13b
0x180009771  jz      short loc_1800097A3
0x180009773  mov     rax, rbp
0x180009776  inc     rax
0x180009779  cmp     [r8+rax], r13b
0x18000977d  jnz     short loc_180009776
0x18000977f  lea     r14, [rax+1]
0x180009783  cmp     rdx, r14
0x180009786  jnb     short loc_18000978E
0x180009788  mov     [rdi+10h], r13
0x18000978c  jmp     short loc_1800097AC
0x18000978e  mov     r9, r14; SourceSize
0x180009791  mov     rcx, rbx; Destination
0x180009794  call    cs:__imp_memcpy_s
0x18000979a  mov     [rdi+10h], rbx
0x18000979e  add     rbx, r14
0x1800097a1  jmp     short loc_1800097A7
0x1800097a3  mov     [rdi+10h], r13
0x1800097a7  cmp     rbx, rsi
0x1800097aa  jz      short loc_1800097F4
0x1800097ac  mov     r8, [r12+80h]; Source
0x1800097b4  test    r8, r8
0x1800097b7  jz      short loc_1800097F4
0x1800097b9  cmp     [r8], r13b
0x1800097bc  jz      short loc_1800097F4
0x1800097be  mov     rax, rbp
0x1800097c1  inc     rax
0x1800097c4  cmp     [r8+rax], r13b
0x1800097c8  jnz     short loc_1800097C1
0x1800097ca  mov     rdx, rsi
0x1800097cd  lea     r14, [rax+1]
0x1800097d1  sub     rdx, rbx; DestinationSize
0x1800097d4  cmp     rdx, r14
0x1800097d7  jnb     short loc_1800097DF
0x1800097d9  mov     [rdi+20h], r13
0x1800097dd  jmp     short loc_1800097FD
0x1800097df  mov     r9, r14; SourceSize
0x1800097e2  mov     rcx, rbx; Destination
0x1800097e5  call    cs:__imp_memcpy_s
0x1800097eb  mov     [rdi+20h], rbx
0x1800097ef  add     rbx, r14
0x1800097f2  jmp     short loc_1800097F8
0x1800097f4  mov     [rdi+20h], r13
0x1800097f8  cmp     rbx, rsi
0x1800097fb  jz      short loc_18000983F
0x1800097fd  mov     r8, [r12+18h]; Source
0x180009802  test    r8, r8
0x180009805  jz      short loc_18000983F
0x180009807  cmp     [r8], r13w
0x18000980b  jz      short loc_18000983F
0x18000980d  inc     rbp
0x180009810  cmp     [r8+rbp*2], r13w
0x180009815  jnz     short loc_18000980D
0x180009817  mov     rdx, rsi
0x18000981a  lea     r14, ds:2[rbp*2]
0x180009822  sub     rdx, rbx; DestinationSize
0x180009825  cmp     rdx, r14
0x180009828  jb      short loc_18000983F
0x18000982a  mov     r9, r14; SourceSize
0x18000982d  mov     rcx, rbx; Destination
0x180009830  call    cs:__imp_memcpy_s
0x180009836  mov     [rdi+38h], rbx
0x18000983a  add     rbx, r14
0x18000983d  jmp     short loc_180009843
0x18000983f  mov     [rdi+38h], r13
0x180009843  sub     rsi, rbx
0x180009846  xor     edx, edx; Val
0x180009848  mov     r8, rsi; Size
0x18000984b  mov     rcx, rbx; void *
0x18000984e  call    memset_0
0x180009853  add     rsp, 28h
0x180009857  pop     r15
0x180009859  pop     r14
0x18000985b  pop     r13
0x18000985d  pop     r12
0x18000985f  pop     rdi
0x180009860  pop     rsi
0x180009861  pop     rbp
0x180009862  pop     rbx
0x180009863  retn
```
