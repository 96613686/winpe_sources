# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008e7c`
- end: `0x180009095`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008600`

## callees

- `0x180001fe2`
- `0x180006ed8`
- `0x180008c0c`
- `0x180008e7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f72`

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
0x180008e7c  push    rbx
0x180008e7e  push    rbp
0x180008e7f  push    rsi
0x180008e80  push    rdi
0x180008e81  push    r12
0x180008e83  push    r13
0x180008e85  push    r14
0x180008e87  push    r15
0x180008e89  sub     rsp, 28h
0x180008e8d  mov     [rcx+4], r8d
0x180008e91  xor     r13d, r13d
0x180008e94  mov     eax, [rdx+8]
0x180008e97  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180008e9b  mov     [rcx+8], eax
0x180008e9e  mov     rdi, rcx
0x180008ea1  mov     [rcx+10h], r13
0x180008ea5  mov     r12, rdx
0x180008ea8  movzx   eax, word ptr [rdx+40h]
0x180008eac  mov     [rcx+18h], ax
0x180008eb0  mov     al, [rdx]
0x180008eb2  mov     [rcx+1Ah], al
0x180008eb5  mov     [rcx+20h], r13
0x180008eb9  mov     rax, [rdx+88h]
0x180008ec0  mov     [rcx+28h], rax
0x180008ec4  mov     rax, [rdx+90h]
0x180008ecb  mov     [rcx+30h], rax
0x180008ecf  mov     [rcx+38h], r13
0x180008ed3  mov     rcx, [rdx+38h]
0x180008ed7  lea     edx, [rbp+2]
0x180008eda  test    rcx, rcx
0x180008edd  jnz     short loc_180008EE4
0x180008edf  mov     r8d, edx
0x180008ee2  jmp     short loc_180008EF4
0x180008ee4  mov     rax, rbp
0x180008ee7  inc     rax
0x180008eea  cmp     [rcx+rax], r13b
0x180008eee  jnz     short loc_180008EE7
0x180008ef0  lea     r8, [rax+1]; unsigned __int64
0x180008ef4  mov     rcx, [r12+80h]
0x180008efc  test    rcx, rcx
0x180008eff  jz      short loc_180008F11
0x180008f01  mov     rax, rbp
0x180008f04  inc     rax
0x180008f07  cmp     [rcx+rax], r13b
0x180008f0b  jnz     short loc_180008F04
0x180008f0d  lea     rdx, [rax+1]
0x180008f11  mov     rcx, [r12+18h]
0x180008f16  test    rcx, rcx
0x180008f19  jnz     short loc_180008F20
0x180008f1b  lea     eax, [rcx+2]
0x180008f1e  jmp     short loc_180008F35
0x180008f20  mov     rax, rbp
0x180008f23  inc     rax
0x180008f26  cmp     [rcx+rax*2], r13w
0x180008f2b  jnz     short loc_180008F23
0x180008f2d  lea     rax, ds:2[rax*2]
0x180008f35  lea     r14, [rdx+rax]
0x180008f39  add     r14, r8
0x180008f3c  lea     rsi, [rdi+48h]
0x180008f40  cmp     [rdi+40h], r13
0x180008f44  jz      short loc_180008F4B
0x180008f46  cmp     [rsi], r14
0x180008f49  jnb     short loc_180008F7F
0x180008f4b  mov     rdx, r14; dwBytes
0x180008f4e  mov     ecx, 8; dwFlags
0x180008f53  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008f58  mov     r15, rax
0x180008f5b  test    rax, rax
0x180008f5e  jz      short loc_180008F7F
0x180008f60  mov     rbx, [rdi+40h]
0x180008f64  call    cs:__imp_GetProcessHeap
0x180008f6a  mov     r8, rbx; lpMem
0x180008f6d  xor     edx, edx; dwFlags
0x180008f6f  mov     rcx, rax; hHeap
0x180008f72  call    cs:__imp_HeapFree
0x180008f78  mov     [rdi+40h], r15
0x180008f7c  mov     [rsi], r14
0x180008f7f  mov     rbx, [rdi+40h]
0x180008f83  test    rbx, rbx
0x180008f86  jz      loc_180009084
0x180008f8c  mov     rdx, [rsi]; DestinationSize
0x180008f8f  lea     rsi, [rdx+rbx]
0x180008f93  cmp     rbx, rsi
0x180008f96  jz      short loc_180008FD6
0x180008f98  mov     r8, [r12+38h]; Source
0x180008f9d  test    r8, r8
0x180008fa0  jz      short loc_180008FD6
0x180008fa2  cmp     [r8], r13b
0x180008fa5  jz      short loc_180008FD6
0x180008fa7  mov     rax, rbp
0x180008faa  inc     rax
0x180008fad  cmp     [r8+rax], r13b
0x180008fb1  jnz     short loc_180008FAA
0x180008fb3  lea     r14, [rax+1]
0x180008fb7  cmp     rdx, r14
0x180008fba  jnb     short loc_180008FC2
0x180008fbc  mov     [rdi+10h], r13
0x180008fc0  jmp     short loc_180008FDF
0x180008fc2  mov     r9, r14; SourceSize
0x180008fc5  mov     rcx, rbx; Destination
0x180008fc8  call    memcpy_s
0x180008fcd  mov     [rdi+10h], rbx
0x180008fd1  add     rbx, r14
0x180008fd4  jmp     short loc_180008FDA
0x180008fd6  mov     [rdi+10h], r13
0x180008fda  cmp     rbx, rsi
0x180008fdd  jz      short loc_180009026
0x180008fdf  mov     r8, [r12+80h]; Source
0x180008fe7  test    r8, r8
0x180008fea  jz      short loc_180009026
0x180008fec  cmp     [r8], r13b
0x180008fef  jz      short loc_180009026
0x180008ff1  mov     rax, rbp
0x180008ff4  inc     rax
0x180008ff7  cmp     [r8+rax], r13b
0x180008ffb  jnz     short loc_180008FF4
0x180008ffd  mov     rdx, rsi
0x180009000  lea     r14, [rax+1]
0x180009004  sub     rdx, rbx; DestinationSize
0x180009007  cmp     rdx, r14
0x18000900a  jnb     short loc_180009012
0x18000900c  mov     [rdi+20h], r13
0x180009010  jmp     short loc_18000902F
0x180009012  mov     r9, r14; SourceSize
0x180009015  mov     rcx, rbx; Destination
0x180009018  call    memcpy_s
0x18000901d  mov     [rdi+20h], rbx
0x180009021  add     rbx, r14
0x180009024  jmp     short loc_18000902A
0x180009026  mov     [rdi+20h], r13
0x18000902a  cmp     rbx, rsi
0x18000902d  jz      short loc_180009070
0x18000902f  mov     r8, [r12+18h]; Source
0x180009034  test    r8, r8
0x180009037  jz      short loc_180009070
0x180009039  cmp     [r8], r13w
0x18000903d  jz      short loc_180009070
0x18000903f  inc     rbp
0x180009042  cmp     [r8+rbp*2], r13w
0x180009047  jnz     short loc_18000903F
0x180009049  mov     rdx, rsi
0x18000904c  lea     r14, ds:2[rbp*2]
0x180009054  sub     rdx, rbx; DestinationSize
0x180009057  cmp     rdx, r14
0x18000905a  jb      short loc_180009070
0x18000905c  mov     r9, r14; SourceSize
0x18000905f  mov     rcx, rbx; Destination
0x180009062  call    memcpy_s
0x180009067  mov     [rdi+38h], rbx
0x18000906b  add     rbx, r14
0x18000906e  jmp     short loc_180009074
0x180009070  mov     [rdi+38h], r13
0x180009074  sub     rsi, rbx
0x180009077  xor     edx, edx; Val
0x180009079  mov     r8, rsi; Size
0x18000907c  mov     rcx, rbx; void *
0x18000907f  call    memset_0
0x180009084  add     rsp, 28h
0x180009088  pop     r15
0x18000908a  pop     r14
0x18000908c  pop     r13
0x18000908e  pop     r12
0x180009090  pop     rdi
0x180009091  pop     rsi
0x180009092  pop     rbp
0x180009093  pop     rbx
0x180009094  retn
```
