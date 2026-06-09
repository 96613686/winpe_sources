# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180007b68`
- end: `0x180007ded`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005e10`

## callees

- `0x180004cec`
- `0x180006eac`
- `0x180007b68`
- `0x180033e9a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007db7`
- `msvcrt!memcpy_s` at `0x180007db7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d1a`

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
  char *v27; // rcx
  char *v28; // rbp
  char *v29; // rax
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
      v27 = *(char **)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = &v27[*(_QWORD *)(v12 + v7 + 72)];
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_BYTE **)a2 + 7), (_QWORD *)(v12 + v7 + 16));
        v30 = wil::details::WriteResultString<char const *>(v29, v28, *((_BYTE **)a2 + 16), v13);
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
0x180007b68  push    rbx
0x180007b6a  push    rbp
0x180007b6b  push    rsi
0x180007b6c  push    rdi
0x180007b6d  push    r12
0x180007b6f  push    r13
0x180007b71  push    r14
0x180007b73  push    r15
0x180007b75  sub     rsp, 28h
0x180007b79  mov     esi, [rcx+10h]
0x180007b7c  xor     r12d, r12d
0x180007b7f  mov     r15, rdx
0x180007b82  mov     rbx, rcx
0x180007b85  mov     ebp, 50h ; 'P'
0x180007b8a  cmp     [rcx+18h], r12
0x180007b8e  jnz     short loc_180007BC5
0x180007b90  test    esi, esi
0x180007b92  jz      short loc_180007BC5
0x180007b94  mov     edx, 190h; dwBytes
0x180007b99  lea     ecx, [rbp-48h]; dwFlags
0x180007b9c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007ba1  mov     [rbx+18h], rax
0x180007ba5  test    rax, rax
0x180007ba8  jz      short loc_180007BC5
0x180007baa  mov     dword ptr [rbx+20h], 5
0x180007bb1  lea     rcx, [rax+190h]
0x180007bb8  jmp     short loc_180007BC0
0x180007bba  mov     [rax], bp
0x180007bbd  add     rax, rbp
0x180007bc0  cmp     rax, rcx
0x180007bc3  jnz     short loc_180007BBA
0x180007bc5  mov     rdi, [rbx+18h]
0x180007bc9  test    rdi, rdi
0x180007bcc  jz      loc_180007DDC
0x180007bd2  test    esi, esi
0x180007bd4  jz      short loc_180007C0C
0x180007bd6  movzx   eax, word ptr [rbx+20h]
0x180007bda  mov     rcx, rdi
0x180007bdd  lea     rdx, [rax+rax*4]
0x180007be1  shl     rdx, 4
0x180007be5  add     rdx, rdi
0x180007be8  cmp     rdi, rdx
0x180007beb  jz      short loc_180007C0C
0x180007bed  mov     r8d, [rbx+10h]
0x180007bf1  cmp     [rcx+4], r8d
0x180007bf5  jbe     short loc_180007C04
0x180007bf7  mov     eax, [r15+8]
0x180007bfb  cmp     [rcx+8], eax
0x180007bfe  jz      loc_180007DDC
0x180007c04  add     rcx, rbp
0x180007c07  cmp     rcx, rdx
0x180007c0a  jnz     short loc_180007BF1
0x180007c0c  movzx   eax, word ptr [rbx+22h]
0x180007c10  mov     r8d, 1
0x180007c16  movzx   ecx, word ptr [rbx+20h]
0x180007c1a  add     eax, r8d
0x180007c1d  xor     edx, edx
0x180007c1f  div     ecx
0x180007c21  mov     ecx, r8d
0x180007c24  movzx   eax, dx
0x180007c27  mov     [rbx+22h], dx
0x180007c2b  lea     rsi, [rax+rax*4]
0x180007c2f  mov     rax, [rbx+8]
0x180007c33  shl     rsi, 4
0x180007c37  lock xadd [rax], ecx
0x180007c3b  add     ecx, r8d
0x180007c3e  lea     r13, [rsi+rdi]
0x180007c42  mov     [rsi+rdi+4], ecx
0x180007c46  lea     rbx, [rdi+20h]
0x180007c4a  mov     eax, [r15+8]
0x180007c4e  add     rbx, rsi
0x180007c51  mov     [rsi+rdi+8], eax
0x180007c55  or      r14, 0FFFFFFFFFFFFFFFFh
0x180007c59  mov     [r13+10h], r12
0x180007c5d  movzx   eax, word ptr [r15+40h]
0x180007c62  mov     [rsi+rdi+18h], ax
0x180007c67  mov     al, [r15]
0x180007c6a  mov     [rsi+rdi+1Ah], al
0x180007c6e  mov     [rbx], r12
0x180007c71  mov     rax, [r15+88h]
0x180007c78  mov     [rsi+rdi+28h], rax
0x180007c7d  mov     rax, [r15+90h]
0x180007c84  mov     [rsi+rdi+30h], rax
0x180007c89  mov     [rsi+rdi+38h], r12
0x180007c8e  mov     rcx, [r15+38h]
0x180007c92  test    rcx, rcx
0x180007c95  jnz     short loc_180007C9C
0x180007c97  mov     edx, r8d
0x180007c9a  jmp     short loc_180007CAC
0x180007c9c  mov     rax, r14
0x180007c9f  inc     rax
0x180007ca2  cmp     [rcx+rax], r12b
0x180007ca6  jnz     short loc_180007C9F
0x180007ca8  lea     rdx, [rax+1]
0x180007cac  mov     rcx, [r15+80h]
0x180007cb3  test    rcx, rcx
0x180007cb6  jz      short loc_180007CC8
0x180007cb8  mov     rax, r14
0x180007cbb  inc     rax
0x180007cbe  cmp     [rcx+rax], r12b
0x180007cc2  jnz     short loc_180007CBB
0x180007cc4  lea     r8, [rax+1]; unsigned __int64
0x180007cc8  mov     rcx, [r15+18h]
0x180007ccc  test    rcx, rcx
0x180007ccf  jnz     short loc_180007CD6
0x180007cd1  lea     eax, [rcx+2]
0x180007cd4  jmp     short loc_180007CEB
0x180007cd6  mov     rax, r14
0x180007cd9  inc     rax
0x180007cdc  cmp     [rcx+rax*2], r12w
0x180007ce1  jnz     short loc_180007CD9
0x180007ce3  lea     rax, ds:2[rax*2]
0x180007ceb  lea     rbp, [r8+rax]
0x180007cef  add     rbp, rdx
0x180007cf2  cmp     [rsi+rdi+40h], r12
0x180007cf7  jz      short loc_180007D00
0x180007cf9  cmp     [rsi+rdi+48h], rbp
0x180007cfe  jnb     short loc_180007D42
0x180007d00  mov     rdx, rbp; dwBytes
0x180007d03  mov     ecx, 8; dwFlags
0x180007d08  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007d0d  mov     r12, rax
0x180007d10  test    rax, rax
0x180007d13  jz      short loc_180007D3F
0x180007d15  mov     rbx, [rsi+rdi+40h]
0x180007d1a  call    cs:__imp_GetProcessHeap
0x180007d20  mov     r8, rbx; lpMem
0x180007d23  xor     edx, edx; dwFlags
0x180007d25  mov     rcx, rax; hHeap
0x180007d28  call    cs:__imp_HeapFree
0x180007d2e  lea     rbx, [rdi+20h]
0x180007d32  mov     [rsi+rdi+40h], r12
0x180007d37  add     rbx, rsi
0x180007d3a  mov     [rsi+rdi+48h], rbp
0x180007d3f  xor     r12d, r12d
0x180007d42  mov     rcx, [rsi+rdi+40h]
0x180007d47  test    rcx, rcx
0x180007d4a  jz      loc_180007DDC
0x180007d50  mov     rbp, [rsi+rdi+48h]
0x180007d55  lea     r9, [r13+10h]
0x180007d59  mov     r8, [r15+38h]
0x180007d5d  add     rbp, rcx
0x180007d60  mov     rdx, rbp
0x180007d63  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007d68  mov     r8, [r15+80h]
0x180007d6f  mov     r9, rbx
0x180007d72  mov     rdx, rbp
0x180007d75  mov     rcx, rax
0x180007d78  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007d7d  mov     rbx, rax
0x180007d80  cmp     rax, rbp
0x180007d83  jz      short loc_180007DC7
0x180007d85  mov     r8, [r15+18h]; Source
0x180007d89  test    r8, r8
0x180007d8c  jz      short loc_180007DC7
0x180007d8e  cmp     [r8], r12w
0x180007d92  jz      short loc_180007DC7
0x180007d94  inc     r14
0x180007d97  cmp     [r8+r14*2], r12w
0x180007d9c  jnz     short loc_180007D94
0x180007d9e  mov     rdx, rbp
0x180007da1  lea     r14, ds:2[r14*2]
0x180007da9  sub     rdx, rbx; DestinationSize
0x180007dac  cmp     rdx, r14
0x180007daf  jb      short loc_180007DC7
0x180007db1  mov     r9, r14; SourceSize
0x180007db4  mov     rcx, rbx; Destination
0x180007db7  call    cs:__imp_memcpy_s
0x180007dbd  mov     [rsi+rdi+38h], rbx
0x180007dc2  add     rbx, r14
0x180007dc5  jmp     short loc_180007DCC
0x180007dc7  mov     [rsi+rdi+38h], r12
0x180007dcc  sub     rbp, rbx
0x180007dcf  xor     edx, edx; Val
0x180007dd1  mov     r8, rbp; Size
0x180007dd4  mov     rcx, rbx; void *
0x180007dd7  call    memset_0
0x180007ddc  add     rsp, 28h
0x180007de0  pop     r15
0x180007de2  pop     r14
0x180007de4  pop     r13
0x180007de6  pop     r12
0x180007de8  pop     rdi
0x180007de9  pop     rsi
0x180007dea  pop     rbp
0x180007deb  pop     rbx
0x180007dec  retn
```
