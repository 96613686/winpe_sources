# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000fe74`
- end: `0x1400100af`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `571`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e910`

## callees

- `0x140001af3`
- `0x14000fafc`
- `0x14000fe74`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000ff5c`
- `KERNEL32!GetProcessHeap` at `0x14000ff5c`
- `KERNEL32!HeapFree` at `0x14000ff70`
- `KERNEL32!HeapFree` at `0x14000ff70`
- `msvcrt!memcpy_s` at `0x14000ffcc`
- `msvcrt!memcpy_s` at `0x140010023`
- `msvcrt!memcpy_s` at `0x140010074`
- `msvcrt!memcpy_s` at `0x14000ffcc`
- `msvcrt!memcpy_s` at `0x140010023`
- `msvcrt!memcpy_s` at `0x140010074`

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
0x14000fe74  push    rbx
0x14000fe76  push    rbp
0x14000fe77  push    rsi
0x14000fe78  push    rdi
0x14000fe79  push    r12
0x14000fe7b  push    r13
0x14000fe7d  push    r14
0x14000fe7f  push    r15
0x14000fe81  sub     rsp, 28h
0x14000fe85  mov     [rcx+4], r8d
0x14000fe89  xor     r13d, r13d
0x14000fe8c  mov     eax, [rdx+8]
0x14000fe8f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000fe93  mov     [rcx+8], eax
0x14000fe96  mov     rdi, rcx
0x14000fe99  mov     [rcx+10h], r13
0x14000fe9d  mov     r12, rdx
0x14000fea0  movzx   eax, word ptr [rdx+40h]
0x14000fea4  mov     [rcx+18h], ax
0x14000fea8  mov     al, [rdx]
0x14000feaa  mov     [rcx+1Ah], al
0x14000fead  mov     [rcx+20h], r13
0x14000feb1  mov     rax, [rdx+88h]
0x14000feb8  mov     [rcx+28h], rax
0x14000febc  mov     rax, [rdx+90h]
0x14000fec3  mov     [rcx+30h], rax
0x14000fec7  mov     [rcx+38h], r13
0x14000fecb  mov     rcx, [rdx+38h]
0x14000fecf  lea     edx, [rbp+2]
0x14000fed2  test    rcx, rcx
0x14000fed5  jnz     short loc_14000FEDC
0x14000fed7  mov     r8d, edx
0x14000feda  jmp     short loc_14000FEEC
0x14000fedc  mov     rax, rbp
0x14000fedf  inc     rax
0x14000fee2  cmp     [rcx+rax], r13b
0x14000fee6  jnz     short loc_14000FEDF
0x14000fee8  lea     r8, [rax+1]; unsigned __int64
0x14000feec  mov     rcx, [r12+80h]
0x14000fef4  test    rcx, rcx
0x14000fef7  jz      short loc_14000FF09
0x14000fef9  mov     rax, rbp
0x14000fefc  inc     rax
0x14000feff  cmp     [rcx+rax], r13b
0x14000ff03  jnz     short loc_14000FEFC
0x14000ff05  lea     rdx, [rax+1]
0x14000ff09  mov     rcx, [r12+18h]
0x14000ff0e  test    rcx, rcx
0x14000ff11  jnz     short loc_14000FF18
0x14000ff13  lea     eax, [rcx+2]
0x14000ff16  jmp     short loc_14000FF2D
0x14000ff18  mov     rax, rbp
0x14000ff1b  inc     rax
0x14000ff1e  cmp     [rcx+rax*2], r13w
0x14000ff23  jnz     short loc_14000FF1B
0x14000ff25  lea     rax, ds:2[rax*2]
0x14000ff2d  lea     r14, [rdx+rax]
0x14000ff31  add     r14, r8
0x14000ff34  lea     rsi, [rdi+48h]
0x14000ff38  cmp     [rdi+40h], r13
0x14000ff3c  jz      short loc_14000FF43
0x14000ff3e  cmp     [rsi], r14
0x14000ff41  jnb     short loc_14000FF83
0x14000ff43  mov     rdx, r14; dwBytes
0x14000ff46  mov     ecx, 8; dwFlags
0x14000ff4b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000ff50  mov     r15, rax
0x14000ff53  test    rax, rax
0x14000ff56  jz      short loc_14000FF83
0x14000ff58  mov     rbx, [rdi+40h]
0x14000ff5c  call    cs:__imp_GetProcessHeap
0x14000ff63  nop     dword ptr [rax+rax+00h]
0x14000ff68  mov     r8, rbx; lpMem
0x14000ff6b  xor     edx, edx; dwFlags
0x14000ff6d  mov     rcx, rax; hHeap
0x14000ff70  call    cs:__imp_HeapFree
0x14000ff77  nop     dword ptr [rax+rax+00h]
0x14000ff7c  mov     [rdi+40h], r15
0x14000ff80  mov     [rsi], r14
0x14000ff83  mov     rbx, [rdi+40h]
0x14000ff87  test    rbx, rbx
0x14000ff8a  jz      loc_14001009D
0x14000ff90  mov     rdx, [rsi]; DestinationSize
0x14000ff93  lea     rsi, [rdx+rbx]
0x14000ff97  cmp     rbx, rsi
0x14000ff9a  jz      short loc_14000FFE1
0x14000ff9c  mov     r8, [r12+38h]; Source
0x14000ffa1  test    r8, r8
0x14000ffa4  jz      short loc_14000FFE1
0x14000ffa6  cmp     [r8], r13b
0x14000ffa9  jz      short loc_14000FFE1
0x14000ffab  mov     rax, rbp
0x14000ffae  inc     rax
0x14000ffb1  cmp     [r8+rax], r13b
0x14000ffb5  jnz     short loc_14000FFAE
0x14000ffb7  lea     r14, [rax+1]
0x14000ffbb  cmp     rdx, r14
0x14000ffbe  jnb     short loc_14000FFC6
0x14000ffc0  mov     [rdi+10h], r13
0x14000ffc4  jmp     short loc_14000FFEA
0x14000ffc6  mov     r9, r14; SourceSize
0x14000ffc9  mov     rcx, rbx; Destination
0x14000ffcc  call    cs:__imp_memcpy_s
0x14000ffd3  nop     dword ptr [rax+rax+00h]
0x14000ffd8  mov     [rdi+10h], rbx
0x14000ffdc  add     rbx, r14
0x14000ffdf  jmp     short loc_14000FFE5
0x14000ffe1  mov     [rdi+10h], r13
0x14000ffe5  cmp     rbx, rsi
0x14000ffe8  jz      short loc_140010038
0x14000ffea  mov     r8, [r12+80h]; Source
0x14000fff2  test    r8, r8
0x14000fff5  jz      short loc_140010038
0x14000fff7  cmp     [r8], r13b
0x14000fffa  jz      short loc_140010038
0x14000fffc  mov     rax, rbp
0x14000ffff  inc     rax
0x140010002  cmp     [r8+rax], r13b
0x140010006  jnz     short loc_14000FFFF
0x140010008  mov     rdx, rsi
0x14001000b  lea     r14, [rax+1]
0x14001000f  sub     rdx, rbx; DestinationSize
0x140010012  cmp     rdx, r14
0x140010015  jnb     short loc_14001001D
0x140010017  mov     [rdi+20h], r13
0x14001001b  jmp     short loc_140010041
0x14001001d  mov     r9, r14; SourceSize
0x140010020  mov     rcx, rbx; Destination
0x140010023  call    cs:__imp_memcpy_s
0x14001002a  nop     dword ptr [rax+rax+00h]
0x14001002f  mov     [rdi+20h], rbx
0x140010033  add     rbx, r14
0x140010036  jmp     short loc_14001003C
0x140010038  mov     [rdi+20h], r13
0x14001003c  cmp     rbx, rsi
0x14001003f  jz      short loc_140010089
0x140010041  mov     r8, [r12+18h]; Source
0x140010046  test    r8, r8
0x140010049  jz      short loc_140010089
0x14001004b  cmp     [r8], r13w
0x14001004f  jz      short loc_140010089
0x140010051  inc     rbp
0x140010054  cmp     [r8+rbp*2], r13w
0x140010059  jnz     short loc_140010051
0x14001005b  mov     rdx, rsi
0x14001005e  lea     r14, ds:2[rbp*2]
0x140010066  sub     rdx, rbx; DestinationSize
0x140010069  cmp     rdx, r14
0x14001006c  jb      short loc_140010089
0x14001006e  mov     r9, r14; SourceSize
0x140010071  mov     rcx, rbx; Destination
0x140010074  call    cs:__imp_memcpy_s
0x14001007b  nop     dword ptr [rax+rax+00h]
0x140010080  mov     [rdi+38h], rbx
0x140010084  add     rbx, r14
0x140010087  jmp     short loc_14001008D
0x140010089  mov     [rdi+38h], r13
0x14001008d  sub     rsi, rbx
0x140010090  xor     edx, edx; Val
0x140010092  mov     r8, rsi; Size
0x140010095  mov     rcx, rbx; void *
0x140010098  call    memset_0
0x14001009d  add     rsp, 28h
0x1400100a1  pop     r15
0x1400100a3  pop     r14
0x1400100a5  pop     r13
0x1400100a7  pop     r12
0x1400100a9  pop     rdi
0x1400100aa  pop     rsi
0x1400100ab  pop     rbp
0x1400100ac  pop     rbx
0x1400100ad  retn
```
