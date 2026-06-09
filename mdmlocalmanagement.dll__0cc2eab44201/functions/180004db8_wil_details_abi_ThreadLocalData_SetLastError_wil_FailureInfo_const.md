# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180004db8`
- end: `0x180005049`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003310`

## callees

- `0x180001fea`
- `0x1800029fc`
- `0x180004584`
- `0x180004db8`
- `0x180005df8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f7e`

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
0x180004db8  push    rbx
0x180004dba  push    rbp
0x180004dbb  push    rsi
0x180004dbc  push    rdi
0x180004dbd  push    r12
0x180004dbf  push    r13
0x180004dc1  push    r14
0x180004dc3  push    r15
0x180004dc5  sub     rsp, 28h
0x180004dc9  mov     esi, [rcx+10h]
0x180004dcc  xor     r12d, r12d
0x180004dcf  mov     r15, rdx
0x180004dd2  mov     rbx, rcx
0x180004dd5  mov     ebp, 50h ; 'P'
0x180004dda  cmp     [rcx+18h], r12
0x180004dde  jnz     short loc_180004E15
0x180004de0  test    esi, esi
0x180004de2  jz      short loc_180004E15
0x180004de4  mov     edx, 190h; dwBytes
0x180004de9  lea     ecx, [rbp-48h]; dwFlags
0x180004dec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004df1  mov     [rbx+18h], rax
0x180004df5  test    rax, rax
0x180004df8  jz      short loc_180004E15
0x180004dfa  mov     dword ptr [rbx+20h], 5
0x180004e01  lea     rcx, [rax+190h]
0x180004e08  jmp     short loc_180004E10
0x180004e0a  mov     [rax], bp
0x180004e0d  add     rax, rbp
0x180004e10  cmp     rax, rcx
0x180004e13  jnz     short loc_180004E0A
0x180004e15  mov     rdi, [rbx+18h]
0x180004e19  test    rdi, rdi
0x180004e1c  jz      loc_180005037
0x180004e22  test    esi, esi
0x180004e24  jz      short loc_180004E5C
0x180004e26  movzx   eax, word ptr [rbx+20h]
0x180004e2a  mov     rcx, rdi
0x180004e2d  lea     rdx, [rax+rax*4]
0x180004e31  shl     rdx, 4
0x180004e35  add     rdx, rdi
0x180004e38  cmp     rdi, rdx
0x180004e3b  jz      short loc_180004E5C
0x180004e3d  mov     r8d, [rbx+10h]
0x180004e41  cmp     [rcx+4], r8d
0x180004e45  jbe     short loc_180004E54
0x180004e47  mov     eax, [r15+8]
0x180004e4b  cmp     [rcx+8], eax
0x180004e4e  jz      loc_180005037
0x180004e54  add     rcx, rbp
0x180004e57  cmp     rcx, rdx
0x180004e5a  jnz     short loc_180004E41
0x180004e5c  movzx   eax, word ptr [rbx+22h]
0x180004e60  mov     r8d, 1
0x180004e66  movzx   ecx, word ptr [rbx+20h]
0x180004e6a  add     eax, r8d
0x180004e6d  xor     edx, edx
0x180004e6f  div     ecx
0x180004e71  mov     ecx, r8d
0x180004e74  movzx   eax, dx
0x180004e77  mov     [rbx+22h], dx
0x180004e7b  lea     rsi, [rax+rax*4]
0x180004e7f  mov     rax, [rbx+8]
0x180004e83  shl     rsi, 4
0x180004e87  lock xadd [rax], ecx
0x180004e8b  add     ecx, r8d
0x180004e8e  lea     r13, [rsi+rdi]
0x180004e92  mov     [rsi+rdi+4], ecx
0x180004e96  lea     rbx, [rdi+20h]
0x180004e9a  mov     eax, [r15+8]
0x180004e9e  add     rbx, rsi
0x180004ea1  mov     [rsi+rdi+8], eax
0x180004ea5  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004ea9  mov     [r13+10h], r12
0x180004ead  movzx   eax, word ptr [r15+40h]
0x180004eb2  mov     [rsi+rdi+18h], ax
0x180004eb7  mov     al, [r15]
0x180004eba  mov     [rsi+rdi+1Ah], al
0x180004ebe  mov     [rbx], r12
0x180004ec1  mov     rax, [r15+88h]
0x180004ec8  mov     [rsi+rdi+28h], rax
0x180004ecd  mov     rax, [r15+90h]
0x180004ed4  mov     [rsi+rdi+30h], rax
0x180004ed9  mov     [rsi+rdi+38h], r12
0x180004ede  mov     rcx, [r15+38h]
0x180004ee2  test    rcx, rcx
0x180004ee5  jnz     short loc_180004EEC
0x180004ee7  mov     edx, r8d
0x180004eea  jmp     short loc_180004EFC
0x180004eec  mov     rax, r14
0x180004eef  inc     rax
0x180004ef2  cmp     [rcx+rax], r12b
0x180004ef6  jnz     short loc_180004EEF
0x180004ef8  lea     rdx, [rax+1]
0x180004efc  mov     rcx, [r15+80h]
0x180004f03  test    rcx, rcx
0x180004f06  jz      short loc_180004F18
0x180004f08  mov     rax, r14
0x180004f0b  inc     rax
0x180004f0e  cmp     [rcx+rax], r12b
0x180004f12  jnz     short loc_180004F0B
0x180004f14  lea     r8, [rax+1]; unsigned __int64
0x180004f18  mov     rcx, [r15+18h]
0x180004f1c  test    rcx, rcx
0x180004f1f  jnz     short loc_180004F26
0x180004f21  lea     eax, [rcx+2]
0x180004f24  jmp     short loc_180004F3B
0x180004f26  mov     rax, r14
0x180004f29  inc     rax
0x180004f2c  cmp     [rcx+rax*2], r12w
0x180004f31  jnz     short loc_180004F29
0x180004f33  lea     rax, ds:2[rax*2]
0x180004f3b  lea     rbp, [r8+rax]
0x180004f3f  add     rbp, rdx
0x180004f42  cmp     [rsi+rdi+40h], r12
0x180004f47  jz      short loc_180004F50
0x180004f49  cmp     [rsi+rdi+48h], rbp
0x180004f4e  jnb     short loc_180004F9E
0x180004f50  mov     rdx, rbp; dwBytes
0x180004f53  mov     ecx, 8; dwFlags
0x180004f58  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f5d  mov     r12, rax
0x180004f60  test    rax, rax
0x180004f63  jz      short loc_180004F9B
0x180004f65  mov     rbx, [rsi+rdi+40h]
0x180004f6a  call    cs:__imp_GetProcessHeap
0x180004f71  nop     dword ptr [rax+rax+00h]
0x180004f76  mov     r8, rbx; lpMem
0x180004f79  xor     edx, edx; dwFlags
0x180004f7b  mov     rcx, rax; hHeap
0x180004f7e  call    cs:__imp_HeapFree
0x180004f85  nop     dword ptr [rax+rax+00h]
0x180004f8a  lea     rbx, [rdi+20h]
0x180004f8e  mov     [rsi+rdi+40h], r12
0x180004f93  add     rbx, rsi
0x180004f96  mov     [rsi+rdi+48h], rbp
0x180004f9b  xor     r12d, r12d
0x180004f9e  mov     rcx, [rsi+rdi+40h]
0x180004fa3  test    rcx, rcx
0x180004fa6  jz      loc_180005037
0x180004fac  mov     rbp, [rsi+rdi+48h]
0x180004fb1  lea     r9, [r13+10h]
0x180004fb5  mov     r8, [r15+38h]
0x180004fb9  add     rbp, rcx
0x180004fbc  mov     rdx, rbp
0x180004fbf  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004fc4  mov     r8, [r15+80h]
0x180004fcb  mov     r9, rbx
0x180004fce  mov     rdx, rbp
0x180004fd1  mov     rcx, rax
0x180004fd4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004fd9  mov     rbx, rax
0x180004fdc  cmp     rax, rbp
0x180004fdf  jz      short loc_180005022
0x180004fe1  mov     r8, [r15+18h]; Source
0x180004fe5  test    r8, r8
0x180004fe8  jz      short loc_180005022
0x180004fea  cmp     [r8], r12w
0x180004fee  jz      short loc_180005022
0x180004ff0  inc     r14
0x180004ff3  cmp     [r8+r14*2], r12w
0x180004ff8  jnz     short loc_180004FF0
0x180004ffa  mov     rdx, rbp
0x180004ffd  lea     r14, ds:2[r14*2]
0x180005005  sub     rdx, rbx; DestinationSize
0x180005008  cmp     rdx, r14
0x18000500b  jb      short loc_180005022
0x18000500d  mov     r9, r14; SourceSize
0x180005010  mov     rcx, rbx; Destination
0x180005013  call    memcpy_s
0x180005018  mov     [rsi+rdi+38h], rbx
0x18000501d  add     rbx, r14
0x180005020  jmp     short loc_180005027
0x180005022  mov     [rsi+rdi+38h], r12
0x180005027  sub     rbp, rbx
0x18000502a  xor     edx, edx; Val
0x18000502c  mov     r8, rbp; Size
0x18000502f  mov     rcx, rbx; void *
0x180005032  call    memset_0
0x180005037  add     rsp, 28h
0x18000503b  pop     r15
0x18000503d  pop     r14
0x18000503f  pop     r13
0x180005041  pop     r12
0x180005043  pop     rdi
0x180005044  pop     rsi
0x180005045  pop     rbp
0x180005046  pop     rbx
0x180005047  retn
```
