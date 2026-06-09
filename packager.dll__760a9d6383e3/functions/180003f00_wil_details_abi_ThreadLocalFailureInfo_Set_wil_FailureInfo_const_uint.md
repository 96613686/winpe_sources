# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180003f00`
- end: `0x18000411c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b70`

## callees

- `0x180003bb8`
- `0x180003f00`
- `0x18000cbbe`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000404c`
- `msvcrt!memcpy_s` at `0x18000409d`
- `msvcrt!memcpy_s` at `0x1800040e8`
- `msvcrt!memcpy_s` at `0x18000404c`
- `msvcrt!memcpy_s` at `0x18000409d`
- `msvcrt!memcpy_s` at `0x1800040e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ff6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ff6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fe8`

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
0x180003f00  push    rbx
0x180003f02  push    rbp
0x180003f03  push    rsi
0x180003f04  push    rdi
0x180003f05  push    r12
0x180003f07  push    r13
0x180003f09  push    r14
0x180003f0b  push    r15
0x180003f0d  sub     rsp, 28h
0x180003f11  mov     [rcx+4], r8d
0x180003f15  xor     r13d, r13d
0x180003f18  mov     eax, [rdx+8]
0x180003f1b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180003f1f  mov     [rcx+8], eax
0x180003f22  mov     rdi, rcx
0x180003f25  mov     [rcx+10h], r13
0x180003f29  mov     r12, rdx
0x180003f2c  movzx   eax, word ptr [rdx+40h]
0x180003f30  mov     [rcx+18h], ax
0x180003f34  mov     al, [rdx]
0x180003f36  mov     [rcx+1Ah], al
0x180003f39  mov     [rcx+20h], r13
0x180003f3d  mov     rax, [rdx+88h]
0x180003f44  mov     [rcx+28h], rax
0x180003f48  mov     rax, [rdx+90h]
0x180003f4f  mov     [rcx+30h], rax
0x180003f53  mov     [rcx+38h], r13
0x180003f57  mov     rcx, [rdx+38h]
0x180003f5b  lea     edx, [rbp+2]
0x180003f5e  test    rcx, rcx
0x180003f61  jnz     short loc_180003F68
0x180003f63  mov     r8d, edx
0x180003f66  jmp     short loc_180003F78
0x180003f68  mov     rax, rbp
0x180003f6b  inc     rax
0x180003f6e  cmp     [rcx+rax], r13b
0x180003f72  jnz     short loc_180003F6B
0x180003f74  lea     r8, [rax+1]; unsigned __int64
0x180003f78  mov     rcx, [r12+80h]
0x180003f80  test    rcx, rcx
0x180003f83  jz      short loc_180003F95
0x180003f85  mov     rax, rbp
0x180003f88  inc     rax
0x180003f8b  cmp     [rcx+rax], r13b
0x180003f8f  jnz     short loc_180003F88
0x180003f91  lea     rdx, [rax+1]
0x180003f95  mov     rcx, [r12+18h]
0x180003f9a  test    rcx, rcx
0x180003f9d  jnz     short loc_180003FA4
0x180003f9f  lea     eax, [rcx+2]
0x180003fa2  jmp     short loc_180003FB9
0x180003fa4  mov     rax, rbp
0x180003fa7  inc     rax
0x180003faa  cmp     [rcx+rax*2], r13w
0x180003faf  jnz     short loc_180003FA7
0x180003fb1  lea     rax, ds:2[rax*2]
0x180003fb9  lea     r14, [rdx+rax]
0x180003fbd  add     r14, r8
0x180003fc0  lea     rsi, [rdi+48h]
0x180003fc4  cmp     [rdi+40h], r13
0x180003fc8  jz      short loc_180003FCF
0x180003fca  cmp     [rsi], r14
0x180003fcd  jnb     short loc_180004003
0x180003fcf  mov     rdx, r14; dwBytes
0x180003fd2  mov     ecx, 8; dwFlags
0x180003fd7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003fdc  mov     r15, rax
0x180003fdf  test    rax, rax
0x180003fe2  jz      short loc_180004003
0x180003fe4  mov     rbx, [rdi+40h]
0x180003fe8  call    cs:__imp_GetProcessHeap
0x180003fee  mov     r8, rbx; lpMem
0x180003ff1  xor     edx, edx; dwFlags
0x180003ff3  mov     rcx, rax; hHeap
0x180003ff6  call    cs:__imp_HeapFree
0x180003ffc  mov     [rdi+40h], r15
0x180004000  mov     [rsi], r14
0x180004003  mov     rbx, [rdi+40h]
0x180004007  test    rbx, rbx
0x18000400a  jz      loc_18000410B
0x180004010  mov     rdx, [rsi]; DestinationSize
0x180004013  lea     rsi, [rdx+rbx]
0x180004017  cmp     rbx, rsi
0x18000401a  jz      short loc_18000405B
0x18000401c  mov     r8, [r12+38h]; Source
0x180004021  test    r8, r8
0x180004024  jz      short loc_18000405B
0x180004026  cmp     [r8], r13b
0x180004029  jz      short loc_18000405B
0x18000402b  mov     rax, rbp
0x18000402e  inc     rax
0x180004031  cmp     [r8+rax], r13b
0x180004035  jnz     short loc_18000402E
0x180004037  lea     r14, [rax+1]
0x18000403b  cmp     rdx, r14
0x18000403e  jnb     short loc_180004046
0x180004040  mov     [rdi+10h], r13
0x180004044  jmp     short loc_180004064
0x180004046  mov     r9, r14; SourceSize
0x180004049  mov     rcx, rbx; Destination
0x18000404c  call    cs:__imp_memcpy_s
0x180004052  mov     [rdi+10h], rbx
0x180004056  add     rbx, r14
0x180004059  jmp     short loc_18000405F
0x18000405b  mov     [rdi+10h], r13
0x18000405f  cmp     rbx, rsi
0x180004062  jz      short loc_1800040AC
0x180004064  mov     r8, [r12+80h]; Source
0x18000406c  test    r8, r8
0x18000406f  jz      short loc_1800040AC
0x180004071  cmp     [r8], r13b
0x180004074  jz      short loc_1800040AC
0x180004076  mov     rax, rbp
0x180004079  inc     rax
0x18000407c  cmp     [r8+rax], r13b
0x180004080  jnz     short loc_180004079
0x180004082  mov     rdx, rsi
0x180004085  lea     r14, [rax+1]
0x180004089  sub     rdx, rbx; DestinationSize
0x18000408c  cmp     rdx, r14
0x18000408f  jnb     short loc_180004097
0x180004091  mov     [rdi+20h], r13
0x180004095  jmp     short loc_1800040B5
0x180004097  mov     r9, r14; SourceSize
0x18000409a  mov     rcx, rbx; Destination
0x18000409d  call    cs:__imp_memcpy_s
0x1800040a3  mov     [rdi+20h], rbx
0x1800040a7  add     rbx, r14
0x1800040aa  jmp     short loc_1800040B0
0x1800040ac  mov     [rdi+20h], r13
0x1800040b0  cmp     rbx, rsi
0x1800040b3  jz      short loc_1800040F7
0x1800040b5  mov     r8, [r12+18h]; Source
0x1800040ba  test    r8, r8
0x1800040bd  jz      short loc_1800040F7
0x1800040bf  cmp     [r8], r13w
0x1800040c3  jz      short loc_1800040F7
0x1800040c5  inc     rbp
0x1800040c8  cmp     [r8+rbp*2], r13w
0x1800040cd  jnz     short loc_1800040C5
0x1800040cf  mov     rdx, rsi
0x1800040d2  lea     r14, ds:2[rbp*2]
0x1800040da  sub     rdx, rbx; DestinationSize
0x1800040dd  cmp     rdx, r14
0x1800040e0  jb      short loc_1800040F7
0x1800040e2  mov     r9, r14; SourceSize
0x1800040e5  mov     rcx, rbx; Destination
0x1800040e8  call    cs:__imp_memcpy_s
0x1800040ee  mov     [rdi+38h], rbx
0x1800040f2  add     rbx, r14
0x1800040f5  jmp     short loc_1800040FB
0x1800040f7  mov     [rdi+38h], r13
0x1800040fb  sub     rsi, rbx
0x1800040fe  xor     edx, edx; Val
0x180004100  mov     r8, rsi; Size
0x180004103  mov     rcx, rbx; void *
0x180004106  call    memset_0
0x18000410b  add     rsp, 28h
0x18000410f  pop     r15
0x180004111  pop     r14
0x180004113  pop     r13
0x180004115  pop     r12
0x180004117  pop     rdi
0x180004118  pop     rsi
0x180004119  pop     rbp
0x18000411a  pop     rbx
0x18000411b  retn
```
