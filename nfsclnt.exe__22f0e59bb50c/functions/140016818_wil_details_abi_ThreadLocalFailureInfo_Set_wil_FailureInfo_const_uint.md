# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140016818`
- end: `0x140016a34`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014320`

## callees

- `0x140015488`
- `0x140016818`
- `0x14001830e`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001690e`
- `KERNEL32!HeapFree` at `0x14001690e`
- `KERNEL32!GetProcessHeap` at `0x140016900`
- `KERNEL32!GetProcessHeap` at `0x140016900`
- `msvcrt!memcpy_s` at `0x140016964`
- `msvcrt!memcpy_s` at `0x1400169b5`
- `msvcrt!memcpy_s` at `0x140016a00`
- `msvcrt!memcpy_s` at `0x140016964`
- `msvcrt!memcpy_s` at `0x1400169b5`
- `msvcrt!memcpy_s` at `0x140016a00`

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
0x140016818  push    rbx
0x14001681a  push    rbp
0x14001681b  push    rsi
0x14001681c  push    rdi
0x14001681d  push    r12
0x14001681f  push    r13
0x140016821  push    r14
0x140016823  push    r15
0x140016825  sub     rsp, 28h
0x140016829  mov     [rcx+4], r8d
0x14001682d  xor     r13d, r13d
0x140016830  mov     eax, [rdx+8]
0x140016833  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140016837  mov     [rcx+8], eax
0x14001683a  mov     rdi, rcx
0x14001683d  mov     [rcx+10h], r13
0x140016841  mov     r12, rdx
0x140016844  movzx   eax, word ptr [rdx+40h]
0x140016848  mov     [rcx+18h], ax
0x14001684c  mov     al, [rdx]
0x14001684e  mov     [rcx+1Ah], al
0x140016851  mov     [rcx+20h], r13
0x140016855  mov     rax, [rdx+88h]
0x14001685c  mov     [rcx+28h], rax
0x140016860  mov     rax, [rdx+90h]
0x140016867  mov     [rcx+30h], rax
0x14001686b  mov     [rcx+38h], r13
0x14001686f  mov     rcx, [rdx+38h]
0x140016873  lea     edx, [rbp+2]
0x140016876  test    rcx, rcx
0x140016879  jnz     short loc_140016880
0x14001687b  mov     r8d, edx
0x14001687e  jmp     short loc_140016890
0x140016880  mov     rax, rbp
0x140016883  inc     rax
0x140016886  cmp     [rcx+rax], r13b
0x14001688a  jnz     short loc_140016883
0x14001688c  lea     r8, [rax+1]; unsigned __int64
0x140016890  mov     rcx, [r12+80h]
0x140016898  test    rcx, rcx
0x14001689b  jz      short loc_1400168AD
0x14001689d  mov     rax, rbp
0x1400168a0  inc     rax
0x1400168a3  cmp     [rcx+rax], r13b
0x1400168a7  jnz     short loc_1400168A0
0x1400168a9  lea     rdx, [rax+1]
0x1400168ad  mov     rcx, [r12+18h]
0x1400168b2  test    rcx, rcx
0x1400168b5  jnz     short loc_1400168BC
0x1400168b7  lea     eax, [rcx+2]
0x1400168ba  jmp     short loc_1400168D1
0x1400168bc  mov     rax, rbp
0x1400168bf  inc     rax
0x1400168c2  cmp     [rcx+rax*2], r13w
0x1400168c7  jnz     short loc_1400168BF
0x1400168c9  lea     rax, ds:2[rax*2]
0x1400168d1  lea     r14, [rdx+rax]
0x1400168d5  add     r14, r8
0x1400168d8  lea     rsi, [rdi+48h]
0x1400168dc  cmp     [rdi+40h], r13
0x1400168e0  jz      short loc_1400168E7
0x1400168e2  cmp     [rsi], r14
0x1400168e5  jnb     short loc_14001691B
0x1400168e7  mov     rdx, r14; dwBytes
0x1400168ea  mov     ecx, 8; dwFlags
0x1400168ef  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400168f4  mov     r15, rax
0x1400168f7  test    rax, rax
0x1400168fa  jz      short loc_14001691B
0x1400168fc  mov     rbx, [rdi+40h]
0x140016900  call    cs:__imp_GetProcessHeap
0x140016906  mov     r8, rbx; lpMem
0x140016909  xor     edx, edx; dwFlags
0x14001690b  mov     rcx, rax; hHeap
0x14001690e  call    cs:__imp_HeapFree
0x140016914  mov     [rdi+40h], r15
0x140016918  mov     [rsi], r14
0x14001691b  mov     rbx, [rdi+40h]
0x14001691f  test    rbx, rbx
0x140016922  jz      loc_140016A23
0x140016928  mov     rdx, [rsi]; DestinationSize
0x14001692b  lea     rsi, [rdx+rbx]
0x14001692f  cmp     rbx, rsi
0x140016932  jz      short loc_140016973
0x140016934  mov     r8, [r12+38h]; Source
0x140016939  test    r8, r8
0x14001693c  jz      short loc_140016973
0x14001693e  cmp     [r8], r13b
0x140016941  jz      short loc_140016973
0x140016943  mov     rax, rbp
0x140016946  inc     rax
0x140016949  cmp     [r8+rax], r13b
0x14001694d  jnz     short loc_140016946
0x14001694f  lea     r14, [rax+1]
0x140016953  cmp     rdx, r14
0x140016956  jnb     short loc_14001695E
0x140016958  mov     [rdi+10h], r13
0x14001695c  jmp     short loc_14001697C
0x14001695e  mov     r9, r14; SourceSize
0x140016961  mov     rcx, rbx; Destination
0x140016964  call    cs:__imp_memcpy_s
0x14001696a  mov     [rdi+10h], rbx
0x14001696e  add     rbx, r14
0x140016971  jmp     short loc_140016977
0x140016973  mov     [rdi+10h], r13
0x140016977  cmp     rbx, rsi
0x14001697a  jz      short loc_1400169C4
0x14001697c  mov     r8, [r12+80h]; Source
0x140016984  test    r8, r8
0x140016987  jz      short loc_1400169C4
0x140016989  cmp     [r8], r13b
0x14001698c  jz      short loc_1400169C4
0x14001698e  mov     rax, rbp
0x140016991  inc     rax
0x140016994  cmp     [r8+rax], r13b
0x140016998  jnz     short loc_140016991
0x14001699a  mov     rdx, rsi
0x14001699d  lea     r14, [rax+1]
0x1400169a1  sub     rdx, rbx; DestinationSize
0x1400169a4  cmp     rdx, r14
0x1400169a7  jnb     short loc_1400169AF
0x1400169a9  mov     [rdi+20h], r13
0x1400169ad  jmp     short loc_1400169CD
0x1400169af  mov     r9, r14; SourceSize
0x1400169b2  mov     rcx, rbx; Destination
0x1400169b5  call    cs:__imp_memcpy_s
0x1400169bb  mov     [rdi+20h], rbx
0x1400169bf  add     rbx, r14
0x1400169c2  jmp     short loc_1400169C8
0x1400169c4  mov     [rdi+20h], r13
0x1400169c8  cmp     rbx, rsi
0x1400169cb  jz      short loc_140016A0F
0x1400169cd  mov     r8, [r12+18h]; Source
0x1400169d2  test    r8, r8
0x1400169d5  jz      short loc_140016A0F
0x1400169d7  cmp     [r8], r13w
0x1400169db  jz      short loc_140016A0F
0x1400169dd  inc     rbp
0x1400169e0  cmp     [r8+rbp*2], r13w
0x1400169e5  jnz     short loc_1400169DD
0x1400169e7  mov     rdx, rsi
0x1400169ea  lea     r14, ds:2[rbp*2]
0x1400169f2  sub     rdx, rbx; DestinationSize
0x1400169f5  cmp     rdx, r14
0x1400169f8  jb      short loc_140016A0F
0x1400169fa  mov     r9, r14; SourceSize
0x1400169fd  mov     rcx, rbx; Destination
0x140016a00  call    cs:__imp_memcpy_s
0x140016a06  mov     [rdi+38h], rbx
0x140016a0a  add     rbx, r14
0x140016a0d  jmp     short loc_140016A13
0x140016a0f  mov     [rdi+38h], r13
0x140016a13  sub     rsi, rbx
0x140016a16  xor     edx, edx; Val
0x140016a18  mov     r8, rsi; Size
0x140016a1b  mov     rcx, rbx; void *
0x140016a1e  call    memset_0
0x140016a23  add     rsp, 28h
0x140016a27  pop     r15
0x140016a29  pop     r14
0x140016a2b  pop     r13
0x140016a2d  pop     r12
0x140016a2f  pop     rdi
0x140016a30  pop     rsi
0x140016a31  pop     rbp
0x140016a32  pop     rbx
0x140016a33  retn
```
