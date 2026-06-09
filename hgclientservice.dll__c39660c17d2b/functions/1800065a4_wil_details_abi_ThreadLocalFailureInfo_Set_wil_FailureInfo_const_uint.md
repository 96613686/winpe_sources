# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800065a4`
- end: `0x1800067bd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004e00`

## callees

- `0x1800021f0`
- `0x180005ec8`
- `0x1800065a4`
- `0x180007ba0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000669a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000669a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000668c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000668c`

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
0x1800065a4  push    rbx
0x1800065a6  push    rbp
0x1800065a7  push    rsi
0x1800065a8  push    rdi
0x1800065a9  push    r12
0x1800065ab  push    r13
0x1800065ad  push    r14
0x1800065af  push    r15
0x1800065b1  sub     rsp, 28h
0x1800065b5  mov     [rcx+4], r8d
0x1800065b9  xor     r13d, r13d
0x1800065bc  mov     eax, [rdx+8]
0x1800065bf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800065c3  mov     [rcx+8], eax
0x1800065c6  mov     rdi, rcx
0x1800065c9  mov     [rcx+10h], r13
0x1800065cd  mov     r12, rdx
0x1800065d0  movzx   eax, word ptr [rdx+40h]
0x1800065d4  mov     [rcx+18h], ax
0x1800065d8  mov     al, [rdx]
0x1800065da  mov     [rcx+1Ah], al
0x1800065dd  mov     [rcx+20h], r13
0x1800065e1  mov     rax, [rdx+88h]
0x1800065e8  mov     [rcx+28h], rax
0x1800065ec  mov     rax, [rdx+90h]
0x1800065f3  mov     [rcx+30h], rax
0x1800065f7  mov     [rcx+38h], r13
0x1800065fb  mov     rcx, [rdx+38h]
0x1800065ff  lea     edx, [rbp+2]
0x180006602  test    rcx, rcx
0x180006605  jnz     short loc_18000660C
0x180006607  mov     r8d, edx
0x18000660a  jmp     short loc_18000661C
0x18000660c  mov     rax, rbp
0x18000660f  inc     rax
0x180006612  cmp     [rcx+rax], r13b
0x180006616  jnz     short loc_18000660F
0x180006618  lea     r8, [rax+1]; unsigned __int64
0x18000661c  mov     rcx, [r12+80h]
0x180006624  test    rcx, rcx
0x180006627  jz      short loc_180006639
0x180006629  mov     rax, rbp
0x18000662c  inc     rax
0x18000662f  cmp     [rcx+rax], r13b
0x180006633  jnz     short loc_18000662C
0x180006635  lea     rdx, [rax+1]
0x180006639  mov     rcx, [r12+18h]
0x18000663e  test    rcx, rcx
0x180006641  jnz     short loc_180006648
0x180006643  lea     eax, [rcx+2]
0x180006646  jmp     short loc_18000665D
0x180006648  mov     rax, rbp
0x18000664b  inc     rax
0x18000664e  cmp     [rcx+rax*2], r13w
0x180006653  jnz     short loc_18000664B
0x180006655  lea     rax, ds:2[rax*2]
0x18000665d  lea     r14, [rdx+rax]
0x180006661  add     r14, r8
0x180006664  lea     rsi, [rdi+48h]
0x180006668  cmp     [rdi+40h], r13
0x18000666c  jz      short loc_180006673
0x18000666e  cmp     [rsi], r14
0x180006671  jnb     short loc_1800066A7
0x180006673  mov     rdx, r14; dwBytes
0x180006676  mov     ecx, 8; dwFlags
0x18000667b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006680  mov     r15, rax
0x180006683  test    rax, rax
0x180006686  jz      short loc_1800066A7
0x180006688  mov     rbx, [rdi+40h]
0x18000668c  call    cs:__imp_GetProcessHeap
0x180006692  mov     r8, rbx; lpMem
0x180006695  xor     edx, edx; dwFlags
0x180006697  mov     rcx, rax; hHeap
0x18000669a  call    cs:__imp_HeapFree
0x1800066a0  mov     [rdi+40h], r15
0x1800066a4  mov     [rsi], r14
0x1800066a7  mov     rbx, [rdi+40h]
0x1800066ab  test    rbx, rbx
0x1800066ae  jz      loc_1800067AC
0x1800066b4  mov     rdx, [rsi]; DestinationSize
0x1800066b7  lea     rsi, [rdx+rbx]
0x1800066bb  cmp     rbx, rsi
0x1800066be  jz      short loc_1800066FE
0x1800066c0  mov     r8, [r12+38h]; Source
0x1800066c5  test    r8, r8
0x1800066c8  jz      short loc_1800066FE
0x1800066ca  cmp     [r8], r13b
0x1800066cd  jz      short loc_1800066FE
0x1800066cf  mov     rax, rbp
0x1800066d2  inc     rax
0x1800066d5  cmp     [r8+rax], r13b
0x1800066d9  jnz     short loc_1800066D2
0x1800066db  lea     r14, [rax+1]
0x1800066df  cmp     rdx, r14
0x1800066e2  jnb     short loc_1800066EA
0x1800066e4  mov     [rdi+10h], r13
0x1800066e8  jmp     short loc_180006707
0x1800066ea  mov     r9, r14; SourceSize
0x1800066ed  mov     rcx, rbx; Destination
0x1800066f0  call    memcpy_s
0x1800066f5  mov     [rdi+10h], rbx
0x1800066f9  add     rbx, r14
0x1800066fc  jmp     short loc_180006702
0x1800066fe  mov     [rdi+10h], r13
0x180006702  cmp     rbx, rsi
0x180006705  jz      short loc_18000674E
0x180006707  mov     r8, [r12+80h]; Source
0x18000670f  test    r8, r8
0x180006712  jz      short loc_18000674E
0x180006714  cmp     [r8], r13b
0x180006717  jz      short loc_18000674E
0x180006719  mov     rax, rbp
0x18000671c  inc     rax
0x18000671f  cmp     [r8+rax], r13b
0x180006723  jnz     short loc_18000671C
0x180006725  mov     rdx, rsi
0x180006728  lea     r14, [rax+1]
0x18000672c  sub     rdx, rbx; DestinationSize
0x18000672f  cmp     rdx, r14
0x180006732  jnb     short loc_18000673A
0x180006734  mov     [rdi+20h], r13
0x180006738  jmp     short loc_180006757
0x18000673a  mov     r9, r14; SourceSize
0x18000673d  mov     rcx, rbx; Destination
0x180006740  call    memcpy_s
0x180006745  mov     [rdi+20h], rbx
0x180006749  add     rbx, r14
0x18000674c  jmp     short loc_180006752
0x18000674e  mov     [rdi+20h], r13
0x180006752  cmp     rbx, rsi
0x180006755  jz      short loc_180006798
0x180006757  mov     r8, [r12+18h]; Source
0x18000675c  test    r8, r8
0x18000675f  jz      short loc_180006798
0x180006761  cmp     [r8], r13w
0x180006765  jz      short loc_180006798
0x180006767  inc     rbp
0x18000676a  cmp     [r8+rbp*2], r13w
0x18000676f  jnz     short loc_180006767
0x180006771  mov     rdx, rsi
0x180006774  lea     r14, ds:2[rbp*2]
0x18000677c  sub     rdx, rbx; DestinationSize
0x18000677f  cmp     rdx, r14
0x180006782  jb      short loc_180006798
0x180006784  mov     r9, r14; SourceSize
0x180006787  mov     rcx, rbx; Destination
0x18000678a  call    memcpy_s
0x18000678f  mov     [rdi+38h], rbx
0x180006793  add     rbx, r14
0x180006796  jmp     short loc_18000679C
0x180006798  mov     [rdi+38h], r13
0x18000679c  sub     rsi, rbx
0x18000679f  xor     edx, edx; Val
0x1800067a1  mov     r8, rsi; Size
0x1800067a4  mov     rcx, rbx; void *
0x1800067a7  call    memset_0
0x1800067ac  add     rsp, 28h
0x1800067b0  pop     r15
0x1800067b2  pop     r14
0x1800067b4  pop     r13
0x1800067b6  pop     r12
0x1800067b8  pop     rdi
0x1800067b9  pop     rsi
0x1800067ba  pop     rbp
0x1800067bb  pop     rbx
0x1800067bc  retn
```
