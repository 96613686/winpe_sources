# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140007df8`
- end: `0x14000807d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005070`

## callees

- `0x140001ebf`
- `0x140003130`
- `0x140007288`
- `0x140007df8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008047`
- `msvcrt!memcpy_s` at `0x140008047`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007fb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007fb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007faa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007faa`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // esi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rbp
  LPVOID v24; // r12
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v27; // rcx
  char *v28; // rbp
  __int64 v29; // rax
  char *v30; // rax
  char *v31; // rbx
  _WORD *v32; // r8
  rsize_t v33; // r14

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = 1;
      v11 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v11;
      v12 = 80LL * (unsigned __int16)v11;
      *(_DWORD *)(v12 + v7 + 4) = _InterlockedIncrement(*((volatile signed __int32 **)this + 1));
      v13 = (_QWORD *)(v12 + v7 + 32);
      *(_DWORD *)(v12 + v7 + 8) = *((_DWORD *)a2 + 2);
      v14 = -1;
      *(_QWORD *)(v12 + v7 + 16) = 0;
      *(_WORD *)(v12 + v7 + 24) = *((_WORD *)a2 + 32);
      *(_BYTE *)(v12 + v7 + 26) = *(_BYTE *)a2;
      *v13 = 0;
      *(_QWORD *)(v12 + v7 + 40) = *((_QWORD *)a2 + 17);
      *(_QWORD *)(v12 + v7 + 48) = *((_QWORD *)a2 + 18);
      *(_QWORD *)(v12 + v7 + 56) = 0;
      v15 = *((_QWORD *)a2 + 7);
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v15 + v17) );
        v16 = v17 + 1;
      }
      else
      {
        v16 = 1;
      }
      v18 = *((_QWORD *)a2 + 16);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_BYTE *)(v18 + v19) );
        v10 = v19 + 1;
      }
      v20 = *((_QWORD *)a2 + 3);
      if ( v20 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v20 + 2 * v22) );
        v21 = 2 * v22 + 2;
      }
      else
      {
        v21 = 2;
      }
      v23 = v16 + v10 + v21;
      if ( !*(_QWORD *)(v12 + v7 + 64) || *(_QWORD *)(v12 + v7 + 72) < v23 )
      {
        v24 = wil::details::ProcessHeapAlloc(8u, v16 + v10 + v21);
        if ( v24 )
        {
          v25 = *(void **)(v12 + v7 + 64);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          *(_QWORD *)(v12 + v7 + 64) = v24;
          v13 = (_QWORD *)(v12 + v7 + 32);
          *(_QWORD *)(v12 + v7 + 72) = v23;
        }
      }
      v27 = *(_QWORD *)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = (char *)(v27 + *(_QWORD *)(v12 + v7 + 72));
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_QWORD *)a2 + 7), v12 + v7 + 16);
        v30 = (char *)wil::details::WriteResultString<char const *>(v29, v28, *((_QWORD *)a2 + 16), v13);
        v31 = v30;
        if ( v30 == v28 )
          goto LABEL_38;
        v32 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( !v32 || !*v32 )
          goto LABEL_38;
        do
          ++v14;
        while ( v32[v14] );
        v33 = 2 * v14 + 2;
        if ( v28 - v30 >= v33 )
        {
          memcpy_s(v30, v28 - v30, v32, v33);
          *(_QWORD *)(v12 + v7 + 56) = v31;
          v31 += v33;
        }
        else
        {
LABEL_38:
          *(_QWORD *)(v12 + v7 + 56) = 0;
        }
        memset_0(v31, 0, v28 - v31);
      }
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x140007df8  push    rbx
0x140007dfa  push    rbp
0x140007dfb  push    rsi
0x140007dfc  push    rdi
0x140007dfd  push    r12
0x140007dff  push    r13
0x140007e01  push    r14
0x140007e03  push    r15
0x140007e05  sub     rsp, 28h
0x140007e09  mov     esi, [rcx+10h]
0x140007e0c  xor     r12d, r12d
0x140007e0f  mov     r15, rdx
0x140007e12  mov     rbx, rcx
0x140007e15  mov     ebp, 50h ; 'P'
0x140007e1a  cmp     [rcx+18h], r12
0x140007e1e  jnz     short loc_140007E55
0x140007e20  test    esi, esi
0x140007e22  jz      short loc_140007E55
0x140007e24  mov     edx, 190h; dwBytes
0x140007e29  lea     ecx, [rbp-48h]; dwFlags
0x140007e2c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140007e31  mov     [rbx+18h], rax
0x140007e35  test    rax, rax
0x140007e38  jz      short loc_140007E55
0x140007e3a  mov     dword ptr [rbx+20h], 5
0x140007e41  lea     rcx, [rax+190h]
0x140007e48  jmp     short loc_140007E50
0x140007e4a  mov     [rax], bp
0x140007e4d  add     rax, rbp
0x140007e50  cmp     rax, rcx
0x140007e53  jnz     short loc_140007E4A
0x140007e55  mov     rdi, [rbx+18h]
0x140007e59  test    rdi, rdi
0x140007e5c  jz      loc_14000806C
0x140007e62  test    esi, esi
0x140007e64  jz      short loc_140007E9C
0x140007e66  movzx   eax, word ptr [rbx+20h]
0x140007e6a  mov     rcx, rdi
0x140007e6d  lea     rdx, [rax+rax*4]
0x140007e71  shl     rdx, 4
0x140007e75  add     rdx, rdi
0x140007e78  cmp     rdi, rdx
0x140007e7b  jz      short loc_140007E9C
0x140007e7d  mov     r8d, [rbx+10h]
0x140007e81  cmp     [rcx+4], r8d
0x140007e85  jbe     short loc_140007E94
0x140007e87  mov     eax, [r15+8]
0x140007e8b  cmp     [rcx+8], eax
0x140007e8e  jz      loc_14000806C
0x140007e94  add     rcx, rbp
0x140007e97  cmp     rcx, rdx
0x140007e9a  jnz     short loc_140007E81
0x140007e9c  movzx   eax, word ptr [rbx+22h]
0x140007ea0  mov     r8d, 1
0x140007ea6  movzx   ecx, word ptr [rbx+20h]
0x140007eaa  add     eax, r8d
0x140007ead  xor     edx, edx
0x140007eaf  div     ecx
0x140007eb1  mov     ecx, r8d
0x140007eb4  movzx   eax, dx
0x140007eb7  mov     [rbx+22h], dx
0x140007ebb  lea     rsi, [rax+rax*4]
0x140007ebf  mov     rax, [rbx+8]
0x140007ec3  shl     rsi, 4
0x140007ec7  lock xadd [rax], ecx
0x140007ecb  add     ecx, r8d
0x140007ece  lea     r13, [rsi+rdi]
0x140007ed2  mov     [rsi+rdi+4], ecx
0x140007ed6  lea     rbx, [rdi+20h]
0x140007eda  mov     eax, [r15+8]
0x140007ede  add     rbx, rsi
0x140007ee1  mov     [rsi+rdi+8], eax
0x140007ee5  or      r14, 0FFFFFFFFFFFFFFFFh
0x140007ee9  mov     [r13+10h], r12
0x140007eed  movzx   eax, word ptr [r15+40h]
0x140007ef2  mov     [rsi+rdi+18h], ax
0x140007ef7  mov     al, [r15]
0x140007efa  mov     [rsi+rdi+1Ah], al
0x140007efe  mov     [rbx], r12
0x140007f01  mov     rax, [r15+88h]
0x140007f08  mov     [rsi+rdi+28h], rax
0x140007f0d  mov     rax, [r15+90h]
0x140007f14  mov     [rsi+rdi+30h], rax
0x140007f19  mov     [rsi+rdi+38h], r12
0x140007f1e  mov     rcx, [r15+38h]
0x140007f22  test    rcx, rcx
0x140007f25  jnz     short loc_140007F2C
0x140007f27  mov     edx, r8d
0x140007f2a  jmp     short loc_140007F3C
0x140007f2c  mov     rax, r14
0x140007f2f  inc     rax
0x140007f32  cmp     [rcx+rax], r12b
0x140007f36  jnz     short loc_140007F2F
0x140007f38  lea     rdx, [rax+1]
0x140007f3c  mov     rcx, [r15+80h]
0x140007f43  test    rcx, rcx
0x140007f46  jz      short loc_140007F58
0x140007f48  mov     rax, r14
0x140007f4b  inc     rax
0x140007f4e  cmp     [rcx+rax], r12b
0x140007f52  jnz     short loc_140007F4B
0x140007f54  lea     r8, [rax+1]; unsigned __int64
0x140007f58  mov     rcx, [r15+18h]
0x140007f5c  test    rcx, rcx
0x140007f5f  jnz     short loc_140007F66
0x140007f61  lea     eax, [rcx+2]
0x140007f64  jmp     short loc_140007F7B
0x140007f66  mov     rax, r14
0x140007f69  inc     rax
0x140007f6c  cmp     [rcx+rax*2], r12w
0x140007f71  jnz     short loc_140007F69
0x140007f73  lea     rax, ds:2[rax*2]
0x140007f7b  lea     rbp, [r8+rax]
0x140007f7f  add     rbp, rdx
0x140007f82  cmp     [rsi+rdi+40h], r12
0x140007f87  jz      short loc_140007F90
0x140007f89  cmp     [rsi+rdi+48h], rbp
0x140007f8e  jnb     short loc_140007FD2
0x140007f90  mov     rdx, rbp; dwBytes
0x140007f93  mov     ecx, 8; dwFlags
0x140007f98  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140007f9d  mov     r12, rax
0x140007fa0  test    rax, rax
0x140007fa3  jz      short loc_140007FCF
0x140007fa5  mov     rbx, [rsi+rdi+40h]
0x140007faa  call    cs:__imp_GetProcessHeap
0x140007fb0  mov     r8, rbx; lpMem
0x140007fb3  xor     edx, edx; dwFlags
0x140007fb5  mov     rcx, rax; hHeap
0x140007fb8  call    cs:__imp_HeapFree
0x140007fbe  lea     rbx, [rdi+20h]
0x140007fc2  mov     [rsi+rdi+40h], r12
0x140007fc7  add     rbx, rsi
0x140007fca  mov     [rsi+rdi+48h], rbp
0x140007fcf  xor     r12d, r12d
0x140007fd2  mov     rcx, [rsi+rdi+40h]
0x140007fd7  test    rcx, rcx
0x140007fda  jz      loc_14000806C
0x140007fe0  mov     rbp, [rsi+rdi+48h]
0x140007fe5  lea     r9, [r13+10h]
0x140007fe9  mov     r8, [r15+38h]
0x140007fed  add     rbp, rcx
0x140007ff0  mov     rdx, rbp
0x140007ff3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140007ff8  mov     r8, [r15+80h]
0x140007fff  mov     r9, rbx
0x140008002  mov     rdx, rbp
0x140008005  mov     rcx, rax
0x140008008  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000800d  mov     rbx, rax
0x140008010  cmp     rax, rbp
0x140008013  jz      short loc_140008057
0x140008015  mov     r8, [r15+18h]; Source
0x140008019  test    r8, r8
0x14000801c  jz      short loc_140008057
0x14000801e  cmp     [r8], r12w
0x140008022  jz      short loc_140008057
0x140008024  inc     r14
0x140008027  cmp     [r8+r14*2], r12w
0x14000802c  jnz     short loc_140008024
0x14000802e  mov     rdx, rbp
0x140008031  lea     r14, ds:2[r14*2]
0x140008039  sub     rdx, rbx; DestinationSize
0x14000803c  cmp     rdx, r14
0x14000803f  jb      short loc_140008057
0x140008041  mov     r9, r14; SourceSize
0x140008044  mov     rcx, rbx; Destination
0x140008047  call    cs:__imp_memcpy_s
0x14000804d  mov     [rsi+rdi+38h], rbx
0x140008052  add     rbx, r14
0x140008055  jmp     short loc_14000805C
0x140008057  mov     [rsi+rdi+38h], r12
0x14000805c  sub     rbp, rbx
0x14000805f  xor     edx, edx; Val
0x140008061  mov     r8, rbp; Size
0x140008064  mov     rcx, rbx; void *
0x140008067  call    memset_0
0x14000806c  add     rsp, 28h
0x140008070  pop     r15
0x140008072  pop     r14
0x140008074  pop     r13
0x140008076  pop     r12
0x140008078  pop     rdi
0x140008079  pop     rsi
0x14000807a  pop     rbp
0x14000807b  pop     rbx
0x14000807c  retn
```
