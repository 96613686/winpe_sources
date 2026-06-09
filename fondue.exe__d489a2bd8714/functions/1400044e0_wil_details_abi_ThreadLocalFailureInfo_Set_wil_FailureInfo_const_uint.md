# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400044e0`
- end: `0x1400046fc`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003150`

## callees

- `0x1400017bf`
- `0x140004198`
- `0x1400044e0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000462c`
- `msvcrt!memcpy_s` at `0x14000467d`
- `msvcrt!memcpy_s` at `0x1400046c8`
- `msvcrt!memcpy_s` at `0x14000462c`
- `msvcrt!memcpy_s` at `0x14000467d`
- `msvcrt!memcpy_s` at `0x1400046c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400045d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400045d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400045c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400045c8`

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
0x1400044e0  push    rbx
0x1400044e2  push    rbp
0x1400044e3  push    rsi
0x1400044e4  push    rdi
0x1400044e5  push    r12
0x1400044e7  push    r13
0x1400044e9  push    r14
0x1400044eb  push    r15
0x1400044ed  sub     rsp, 28h
0x1400044f1  mov     [rcx+4], r8d
0x1400044f5  xor     r13d, r13d
0x1400044f8  mov     eax, [rdx+8]
0x1400044fb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400044ff  mov     [rcx+8], eax
0x140004502  mov     rdi, rcx
0x140004505  mov     [rcx+10h], r13
0x140004509  mov     r12, rdx
0x14000450c  movzx   eax, word ptr [rdx+40h]
0x140004510  mov     [rcx+18h], ax
0x140004514  mov     al, [rdx]
0x140004516  mov     [rcx+1Ah], al
0x140004519  mov     [rcx+20h], r13
0x14000451d  mov     rax, [rdx+88h]
0x140004524  mov     [rcx+28h], rax
0x140004528  mov     rax, [rdx+90h]
0x14000452f  mov     [rcx+30h], rax
0x140004533  mov     [rcx+38h], r13
0x140004537  mov     rcx, [rdx+38h]
0x14000453b  lea     edx, [rbp+2]
0x14000453e  test    rcx, rcx
0x140004541  jnz     short loc_140004548
0x140004543  mov     r8d, edx
0x140004546  jmp     short loc_140004558
0x140004548  mov     rax, rbp
0x14000454b  inc     rax
0x14000454e  cmp     [rcx+rax], r13b
0x140004552  jnz     short loc_14000454B
0x140004554  lea     r8, [rax+1]; unsigned __int64
0x140004558  mov     rcx, [r12+80h]
0x140004560  test    rcx, rcx
0x140004563  jz      short loc_140004575
0x140004565  mov     rax, rbp
0x140004568  inc     rax
0x14000456b  cmp     [rcx+rax], r13b
0x14000456f  jnz     short loc_140004568
0x140004571  lea     rdx, [rax+1]
0x140004575  mov     rcx, [r12+18h]
0x14000457a  test    rcx, rcx
0x14000457d  jnz     short loc_140004584
0x14000457f  lea     eax, [rcx+2]
0x140004582  jmp     short loc_140004599
0x140004584  mov     rax, rbp
0x140004587  inc     rax
0x14000458a  cmp     [rcx+rax*2], r13w
0x14000458f  jnz     short loc_140004587
0x140004591  lea     rax, ds:2[rax*2]
0x140004599  lea     r14, [rdx+rax]
0x14000459d  add     r14, r8
0x1400045a0  lea     rsi, [rdi+48h]
0x1400045a4  cmp     [rdi+40h], r13
0x1400045a8  jz      short loc_1400045AF
0x1400045aa  cmp     [rsi], r14
0x1400045ad  jnb     short loc_1400045E3
0x1400045af  mov     rdx, r14; dwBytes
0x1400045b2  mov     ecx, 8; dwFlags
0x1400045b7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400045bc  mov     r15, rax
0x1400045bf  test    rax, rax
0x1400045c2  jz      short loc_1400045E3
0x1400045c4  mov     rbx, [rdi+40h]
0x1400045c8  call    cs:__imp_GetProcessHeap
0x1400045ce  mov     r8, rbx; lpMem
0x1400045d1  xor     edx, edx; dwFlags
0x1400045d3  mov     rcx, rax; hHeap
0x1400045d6  call    cs:__imp_HeapFree
0x1400045dc  mov     [rdi+40h], r15
0x1400045e0  mov     [rsi], r14
0x1400045e3  mov     rbx, [rdi+40h]
0x1400045e7  test    rbx, rbx
0x1400045ea  jz      loc_1400046EB
0x1400045f0  mov     rdx, [rsi]; DestinationSize
0x1400045f3  lea     rsi, [rdx+rbx]
0x1400045f7  cmp     rbx, rsi
0x1400045fa  jz      short loc_14000463B
0x1400045fc  mov     r8, [r12+38h]; Source
0x140004601  test    r8, r8
0x140004604  jz      short loc_14000463B
0x140004606  cmp     [r8], r13b
0x140004609  jz      short loc_14000463B
0x14000460b  mov     rax, rbp
0x14000460e  inc     rax
0x140004611  cmp     [r8+rax], r13b
0x140004615  jnz     short loc_14000460E
0x140004617  lea     r14, [rax+1]
0x14000461b  cmp     rdx, r14
0x14000461e  jnb     short loc_140004626
0x140004620  mov     [rdi+10h], r13
0x140004624  jmp     short loc_140004644
0x140004626  mov     r9, r14; SourceSize
0x140004629  mov     rcx, rbx; Destination
0x14000462c  call    cs:__imp_memcpy_s
0x140004632  mov     [rdi+10h], rbx
0x140004636  add     rbx, r14
0x140004639  jmp     short loc_14000463F
0x14000463b  mov     [rdi+10h], r13
0x14000463f  cmp     rbx, rsi
0x140004642  jz      short loc_14000468C
0x140004644  mov     r8, [r12+80h]; Source
0x14000464c  test    r8, r8
0x14000464f  jz      short loc_14000468C
0x140004651  cmp     [r8], r13b
0x140004654  jz      short loc_14000468C
0x140004656  mov     rax, rbp
0x140004659  inc     rax
0x14000465c  cmp     [r8+rax], r13b
0x140004660  jnz     short loc_140004659
0x140004662  mov     rdx, rsi
0x140004665  lea     r14, [rax+1]
0x140004669  sub     rdx, rbx; DestinationSize
0x14000466c  cmp     rdx, r14
0x14000466f  jnb     short loc_140004677
0x140004671  mov     [rdi+20h], r13
0x140004675  jmp     short loc_140004695
0x140004677  mov     r9, r14; SourceSize
0x14000467a  mov     rcx, rbx; Destination
0x14000467d  call    cs:__imp_memcpy_s
0x140004683  mov     [rdi+20h], rbx
0x140004687  add     rbx, r14
0x14000468a  jmp     short loc_140004690
0x14000468c  mov     [rdi+20h], r13
0x140004690  cmp     rbx, rsi
0x140004693  jz      short loc_1400046D7
0x140004695  mov     r8, [r12+18h]; Source
0x14000469a  test    r8, r8
0x14000469d  jz      short loc_1400046D7
0x14000469f  cmp     [r8], r13w
0x1400046a3  jz      short loc_1400046D7
0x1400046a5  inc     rbp
0x1400046a8  cmp     [r8+rbp*2], r13w
0x1400046ad  jnz     short loc_1400046A5
0x1400046af  mov     rdx, rsi
0x1400046b2  lea     r14, ds:2[rbp*2]
0x1400046ba  sub     rdx, rbx; DestinationSize
0x1400046bd  cmp     rdx, r14
0x1400046c0  jb      short loc_1400046D7
0x1400046c2  mov     r9, r14; SourceSize
0x1400046c5  mov     rcx, rbx; Destination
0x1400046c8  call    cs:__imp_memcpy_s
0x1400046ce  mov     [rdi+38h], rbx
0x1400046d2  add     rbx, r14
0x1400046d5  jmp     short loc_1400046DB
0x1400046d7  mov     [rdi+38h], r13
0x1400046db  sub     rsi, rbx
0x1400046de  xor     edx, edx; Val
0x1400046e0  mov     r8, rsi; Size
0x1400046e3  mov     rcx, rbx; void *
0x1400046e6  call    memset_0
0x1400046eb  add     rsp, 28h
0x1400046ef  pop     r15
0x1400046f1  pop     r14
0x1400046f3  pop     r13
0x1400046f5  pop     r12
0x1400046f7  pop     rdi
0x1400046f8  pop     rsi
0x1400046f9  pop     rbp
0x1400046fa  pop     rbx
0x1400046fb  retn
```
