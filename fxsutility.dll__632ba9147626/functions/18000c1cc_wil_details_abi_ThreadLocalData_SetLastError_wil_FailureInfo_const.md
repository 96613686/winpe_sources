# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000c1cc`
- end: `0x18000c451`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009850`

## callees

- `0x180007dbc`
- `0x18000a908`
- `0x18000c1cc`
- `0x180015cbe`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c41b`
- `msvcrt!memcpy_s` at `0x18000c41b`
- `KERNEL32!HeapFree` at `0x18000c38c`
- `KERNEL32!HeapFree` at `0x18000c38c`
- `KERNEL32!GetProcessHeap` at `0x18000c37e`
- `KERNEL32!GetProcessHeap` at `0x18000c37e`

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
0x18000c1cc  push    rbx
0x18000c1ce  push    rbp
0x18000c1cf  push    rsi
0x18000c1d0  push    rdi
0x18000c1d1  push    r12
0x18000c1d3  push    r13
0x18000c1d5  push    r14
0x18000c1d7  push    r15
0x18000c1d9  sub     rsp, 28h
0x18000c1dd  mov     esi, [rcx+10h]
0x18000c1e0  xor     r12d, r12d
0x18000c1e3  mov     r15, rdx
0x18000c1e6  mov     rbx, rcx
0x18000c1e9  mov     ebp, 50h ; 'P'
0x18000c1ee  cmp     [rcx+18h], r12
0x18000c1f2  jnz     short loc_18000C229
0x18000c1f4  test    esi, esi
0x18000c1f6  jz      short loc_18000C229
0x18000c1f8  mov     edx, 190h; dwBytes
0x18000c1fd  lea     ecx, [rbp-48h]; dwFlags
0x18000c200  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c205  mov     [rbx+18h], rax
0x18000c209  test    rax, rax
0x18000c20c  jz      short loc_18000C229
0x18000c20e  mov     dword ptr [rbx+20h], 5
0x18000c215  lea     rcx, [rax+190h]
0x18000c21c  jmp     short loc_18000C224
0x18000c21e  mov     [rax], bp
0x18000c221  add     rax, rbp
0x18000c224  cmp     rax, rcx
0x18000c227  jnz     short loc_18000C21E
0x18000c229  mov     rdi, [rbx+18h]
0x18000c22d  test    rdi, rdi
0x18000c230  jz      loc_18000C440
0x18000c236  test    esi, esi
0x18000c238  jz      short loc_18000C270
0x18000c23a  movzx   eax, word ptr [rbx+20h]
0x18000c23e  mov     rcx, rdi
0x18000c241  lea     rdx, [rax+rax*4]
0x18000c245  shl     rdx, 4
0x18000c249  add     rdx, rdi
0x18000c24c  cmp     rdi, rdx
0x18000c24f  jz      short loc_18000C270
0x18000c251  mov     r8d, [rbx+10h]
0x18000c255  cmp     [rcx+4], r8d
0x18000c259  jbe     short loc_18000C268
0x18000c25b  mov     eax, [r15+8]
0x18000c25f  cmp     [rcx+8], eax
0x18000c262  jz      loc_18000C440
0x18000c268  add     rcx, rbp
0x18000c26b  cmp     rcx, rdx
0x18000c26e  jnz     short loc_18000C255
0x18000c270  movzx   eax, word ptr [rbx+22h]
0x18000c274  mov     r8d, 1
0x18000c27a  movzx   ecx, word ptr [rbx+20h]
0x18000c27e  add     eax, r8d
0x18000c281  xor     edx, edx
0x18000c283  div     ecx
0x18000c285  mov     ecx, r8d
0x18000c288  movzx   eax, dx
0x18000c28b  mov     [rbx+22h], dx
0x18000c28f  lea     rsi, [rax+rax*4]
0x18000c293  mov     rax, [rbx+8]
0x18000c297  shl     rsi, 4
0x18000c29b  lock xadd [rax], ecx
0x18000c29f  add     ecx, r8d
0x18000c2a2  lea     r13, [rsi+rdi]
0x18000c2a6  mov     [rsi+rdi+4], ecx
0x18000c2aa  lea     rbx, [rdi+20h]
0x18000c2ae  mov     eax, [r15+8]
0x18000c2b2  add     rbx, rsi
0x18000c2b5  mov     [rsi+rdi+8], eax
0x18000c2b9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000c2bd  mov     [r13+10h], r12
0x18000c2c1  movzx   eax, word ptr [r15+40h]
0x18000c2c6  mov     [rsi+rdi+18h], ax
0x18000c2cb  mov     al, [r15]
0x18000c2ce  mov     [rsi+rdi+1Ah], al
0x18000c2d2  mov     [rbx], r12
0x18000c2d5  mov     rax, [r15+88h]
0x18000c2dc  mov     [rsi+rdi+28h], rax
0x18000c2e1  mov     rax, [r15+90h]
0x18000c2e8  mov     [rsi+rdi+30h], rax
0x18000c2ed  mov     [rsi+rdi+38h], r12
0x18000c2f2  mov     rcx, [r15+38h]
0x18000c2f6  test    rcx, rcx
0x18000c2f9  jnz     short loc_18000C300
0x18000c2fb  mov     edx, r8d
0x18000c2fe  jmp     short loc_18000C310
0x18000c300  mov     rax, r14
0x18000c303  inc     rax
0x18000c306  cmp     [rcx+rax], r12b
0x18000c30a  jnz     short loc_18000C303
0x18000c30c  lea     rdx, [rax+1]
0x18000c310  mov     rcx, [r15+80h]
0x18000c317  test    rcx, rcx
0x18000c31a  jz      short loc_18000C32C
0x18000c31c  mov     rax, r14
0x18000c31f  inc     rax
0x18000c322  cmp     [rcx+rax], r12b
0x18000c326  jnz     short loc_18000C31F
0x18000c328  lea     r8, [rax+1]; unsigned __int64
0x18000c32c  mov     rcx, [r15+18h]
0x18000c330  test    rcx, rcx
0x18000c333  jnz     short loc_18000C33A
0x18000c335  lea     eax, [rcx+2]
0x18000c338  jmp     short loc_18000C34F
0x18000c33a  mov     rax, r14
0x18000c33d  inc     rax
0x18000c340  cmp     [rcx+rax*2], r12w
0x18000c345  jnz     short loc_18000C33D
0x18000c347  lea     rax, ds:2[rax*2]
0x18000c34f  lea     rbp, [r8+rax]
0x18000c353  add     rbp, rdx
0x18000c356  cmp     [rsi+rdi+40h], r12
0x18000c35b  jz      short loc_18000C364
0x18000c35d  cmp     [rsi+rdi+48h], rbp
0x18000c362  jnb     short loc_18000C3A6
0x18000c364  mov     rdx, rbp; dwBytes
0x18000c367  mov     ecx, 8; dwFlags
0x18000c36c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c371  mov     r12, rax
0x18000c374  test    rax, rax
0x18000c377  jz      short loc_18000C3A3
0x18000c379  mov     rbx, [rsi+rdi+40h]
0x18000c37e  call    cs:__imp_GetProcessHeap
0x18000c384  mov     r8, rbx; lpMem
0x18000c387  xor     edx, edx; dwFlags
0x18000c389  mov     rcx, rax; hHeap
0x18000c38c  call    cs:__imp_HeapFree
0x18000c392  lea     rbx, [rdi+20h]
0x18000c396  mov     [rsi+rdi+40h], r12
0x18000c39b  add     rbx, rsi
0x18000c39e  mov     [rsi+rdi+48h], rbp
0x18000c3a3  xor     r12d, r12d
0x18000c3a6  mov     rcx, [rsi+rdi+40h]
0x18000c3ab  test    rcx, rcx
0x18000c3ae  jz      loc_18000C440
0x18000c3b4  mov     rbp, [rsi+rdi+48h]
0x18000c3b9  lea     r9, [r13+10h]
0x18000c3bd  mov     r8, [r15+38h]
0x18000c3c1  add     rbp, rcx
0x18000c3c4  mov     rdx, rbp
0x18000c3c7  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c3cc  mov     r8, [r15+80h]
0x18000c3d3  mov     r9, rbx
0x18000c3d6  mov     rdx, rbp
0x18000c3d9  mov     rcx, rax
0x18000c3dc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c3e1  mov     rbx, rax
0x18000c3e4  cmp     rax, rbp
0x18000c3e7  jz      short loc_18000C42B
0x18000c3e9  mov     r8, [r15+18h]; Source
0x18000c3ed  test    r8, r8
0x18000c3f0  jz      short loc_18000C42B
0x18000c3f2  cmp     [r8], r12w
0x18000c3f6  jz      short loc_18000C42B
0x18000c3f8  inc     r14
0x18000c3fb  cmp     [r8+r14*2], r12w
0x18000c400  jnz     short loc_18000C3F8
0x18000c402  mov     rdx, rbp
0x18000c405  lea     r14, ds:2[r14*2]
0x18000c40d  sub     rdx, rbx; DestinationSize
0x18000c410  cmp     rdx, r14
0x18000c413  jb      short loc_18000C42B
0x18000c415  mov     r9, r14; SourceSize
0x18000c418  mov     rcx, rbx; Destination
0x18000c41b  call    cs:__imp_memcpy_s
0x18000c421  mov     [rsi+rdi+38h], rbx
0x18000c426  add     rbx, r14
0x18000c429  jmp     short loc_18000C430
0x18000c42b  mov     [rsi+rdi+38h], r12
0x18000c430  sub     rbp, rbx
0x18000c433  xor     edx, edx; Val
0x18000c435  mov     r8, rbp; Size
0x18000c438  mov     rcx, rbx; void *
0x18000c43b  call    memset_0
0x18000c440  add     rsp, 28h
0x18000c444  pop     r15
0x18000c446  pop     r14
0x18000c448  pop     r13
0x18000c44a  pop     r12
0x18000c44c  pop     rdi
0x18000c44d  pop     rsi
0x18000c44e  pop     rbp
0x18000c44f  pop     rbx
0x18000c450  retn
```
