# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x14000b288`
- end: `0x14000b50d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140006b00`

## callees

- `0x1400043f8`
- `0x14000a74c`
- `0x14000b288`
- `0x1400187b2`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000b4d7`
- `msvcrt!memcpy_s` at `0x14000b4d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b43a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b43a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b448`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b448`

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
0x14000b288  push    rbx
0x14000b28a  push    rbp
0x14000b28b  push    rsi
0x14000b28c  push    rdi
0x14000b28d  push    r12
0x14000b28f  push    r13
0x14000b291  push    r14
0x14000b293  push    r15
0x14000b295  sub     rsp, 28h
0x14000b299  mov     esi, [rcx+10h]
0x14000b29c  xor     r12d, r12d
0x14000b29f  mov     r15, rdx
0x14000b2a2  mov     rbx, rcx
0x14000b2a5  mov     ebp, 50h ; 'P'
0x14000b2aa  cmp     [rcx+18h], r12
0x14000b2ae  jnz     short loc_14000B2E5
0x14000b2b0  test    esi, esi
0x14000b2b2  jz      short loc_14000B2E5
0x14000b2b4  mov     edx, 190h; dwBytes
0x14000b2b9  lea     ecx, [rbp-48h]; dwFlags
0x14000b2bc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000b2c1  mov     [rbx+18h], rax
0x14000b2c5  test    rax, rax
0x14000b2c8  jz      short loc_14000B2E5
0x14000b2ca  mov     dword ptr [rbx+20h], 5
0x14000b2d1  lea     rcx, [rax+190h]
0x14000b2d8  jmp     short loc_14000B2E0
0x14000b2da  mov     [rax], bp
0x14000b2dd  add     rax, rbp
0x14000b2e0  cmp     rax, rcx
0x14000b2e3  jnz     short loc_14000B2DA
0x14000b2e5  mov     rdi, [rbx+18h]
0x14000b2e9  test    rdi, rdi
0x14000b2ec  jz      loc_14000B4FC
0x14000b2f2  test    esi, esi
0x14000b2f4  jz      short loc_14000B32C
0x14000b2f6  movzx   eax, word ptr [rbx+20h]
0x14000b2fa  mov     rcx, rdi
0x14000b2fd  lea     rdx, [rax+rax*4]
0x14000b301  shl     rdx, 4
0x14000b305  add     rdx, rdi
0x14000b308  cmp     rdi, rdx
0x14000b30b  jz      short loc_14000B32C
0x14000b30d  mov     r8d, [rbx+10h]
0x14000b311  cmp     [rcx+4], r8d
0x14000b315  jbe     short loc_14000B324
0x14000b317  mov     eax, [r15+8]
0x14000b31b  cmp     [rcx+8], eax
0x14000b31e  jz      loc_14000B4FC
0x14000b324  add     rcx, rbp
0x14000b327  cmp     rcx, rdx
0x14000b32a  jnz     short loc_14000B311
0x14000b32c  movzx   eax, word ptr [rbx+22h]
0x14000b330  mov     r8d, 1
0x14000b336  movzx   ecx, word ptr [rbx+20h]
0x14000b33a  add     eax, r8d
0x14000b33d  xor     edx, edx
0x14000b33f  div     ecx
0x14000b341  mov     ecx, r8d
0x14000b344  movzx   eax, dx
0x14000b347  mov     [rbx+22h], dx
0x14000b34b  lea     rsi, [rax+rax*4]
0x14000b34f  mov     rax, [rbx+8]
0x14000b353  shl     rsi, 4
0x14000b357  lock xadd [rax], ecx
0x14000b35b  add     ecx, r8d
0x14000b35e  lea     r13, [rsi+rdi]
0x14000b362  mov     [rsi+rdi+4], ecx
0x14000b366  lea     rbx, [rdi+20h]
0x14000b36a  mov     eax, [r15+8]
0x14000b36e  add     rbx, rsi
0x14000b371  mov     [rsi+rdi+8], eax
0x14000b375  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000b379  mov     [r13+10h], r12
0x14000b37d  movzx   eax, word ptr [r15+40h]
0x14000b382  mov     [rsi+rdi+18h], ax
0x14000b387  mov     al, [r15]
0x14000b38a  mov     [rsi+rdi+1Ah], al
0x14000b38e  mov     [rbx], r12
0x14000b391  mov     rax, [r15+88h]
0x14000b398  mov     [rsi+rdi+28h], rax
0x14000b39d  mov     rax, [r15+90h]
0x14000b3a4  mov     [rsi+rdi+30h], rax
0x14000b3a9  mov     [rsi+rdi+38h], r12
0x14000b3ae  mov     rcx, [r15+38h]
0x14000b3b2  test    rcx, rcx
0x14000b3b5  jnz     short loc_14000B3BC
0x14000b3b7  mov     edx, r8d
0x14000b3ba  jmp     short loc_14000B3CC
0x14000b3bc  mov     rax, r14
0x14000b3bf  inc     rax
0x14000b3c2  cmp     [rcx+rax], r12b
0x14000b3c6  jnz     short loc_14000B3BF
0x14000b3c8  lea     rdx, [rax+1]
0x14000b3cc  mov     rcx, [r15+80h]
0x14000b3d3  test    rcx, rcx
0x14000b3d6  jz      short loc_14000B3E8
0x14000b3d8  mov     rax, r14
0x14000b3db  inc     rax
0x14000b3de  cmp     [rcx+rax], r12b
0x14000b3e2  jnz     short loc_14000B3DB
0x14000b3e4  lea     r8, [rax+1]; unsigned __int64
0x14000b3e8  mov     rcx, [r15+18h]
0x14000b3ec  test    rcx, rcx
0x14000b3ef  jnz     short loc_14000B3F6
0x14000b3f1  lea     eax, [rcx+2]
0x14000b3f4  jmp     short loc_14000B40B
0x14000b3f6  mov     rax, r14
0x14000b3f9  inc     rax
0x14000b3fc  cmp     [rcx+rax*2], r12w
0x14000b401  jnz     short loc_14000B3F9
0x14000b403  lea     rax, ds:2[rax*2]
0x14000b40b  lea     rbp, [r8+rax]
0x14000b40f  add     rbp, rdx
0x14000b412  cmp     [rsi+rdi+40h], r12
0x14000b417  jz      short loc_14000B420
0x14000b419  cmp     [rsi+rdi+48h], rbp
0x14000b41e  jnb     short loc_14000B462
0x14000b420  mov     rdx, rbp; dwBytes
0x14000b423  mov     ecx, 8; dwFlags
0x14000b428  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000b42d  mov     r12, rax
0x14000b430  test    rax, rax
0x14000b433  jz      short loc_14000B45F
0x14000b435  mov     rbx, [rsi+rdi+40h]
0x14000b43a  call    cs:__imp_GetProcessHeap
0x14000b440  mov     r8, rbx; lpMem
0x14000b443  xor     edx, edx; dwFlags
0x14000b445  mov     rcx, rax; hHeap
0x14000b448  call    cs:__imp_HeapFree
0x14000b44e  lea     rbx, [rdi+20h]
0x14000b452  mov     [rsi+rdi+40h], r12
0x14000b457  add     rbx, rsi
0x14000b45a  mov     [rsi+rdi+48h], rbp
0x14000b45f  xor     r12d, r12d
0x14000b462  mov     rcx, [rsi+rdi+40h]
0x14000b467  test    rcx, rcx
0x14000b46a  jz      loc_14000B4FC
0x14000b470  mov     rbp, [rsi+rdi+48h]
0x14000b475  lea     r9, [r13+10h]
0x14000b479  mov     r8, [r15+38h]
0x14000b47d  add     rbp, rcx
0x14000b480  mov     rdx, rbp
0x14000b483  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000b488  mov     r8, [r15+80h]
0x14000b48f  mov     r9, rbx
0x14000b492  mov     rdx, rbp
0x14000b495  mov     rcx, rax
0x14000b498  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000b49d  mov     rbx, rax
0x14000b4a0  cmp     rax, rbp
0x14000b4a3  jz      short loc_14000B4E7
0x14000b4a5  mov     r8, [r15+18h]; Source
0x14000b4a9  test    r8, r8
0x14000b4ac  jz      short loc_14000B4E7
0x14000b4ae  cmp     [r8], r12w
0x14000b4b2  jz      short loc_14000B4E7
0x14000b4b4  inc     r14
0x14000b4b7  cmp     [r8+r14*2], r12w
0x14000b4bc  jnz     short loc_14000B4B4
0x14000b4be  mov     rdx, rbp
0x14000b4c1  lea     r14, ds:2[r14*2]
0x14000b4c9  sub     rdx, rbx; DestinationSize
0x14000b4cc  cmp     rdx, r14
0x14000b4cf  jb      short loc_14000B4E7
0x14000b4d1  mov     r9, r14; SourceSize
0x14000b4d4  mov     rcx, rbx; Destination
0x14000b4d7  call    cs:__imp_memcpy_s
0x14000b4dd  mov     [rsi+rdi+38h], rbx
0x14000b4e2  add     rbx, r14
0x14000b4e5  jmp     short loc_14000B4EC
0x14000b4e7  mov     [rsi+rdi+38h], r12
0x14000b4ec  sub     rbp, rbx
0x14000b4ef  xor     edx, edx; Val
0x14000b4f1  mov     r8, rbp; Size
0x14000b4f4  mov     rcx, rbx; void *
0x14000b4f7  call    memset_0
0x14000b4fc  add     rsp, 28h
0x14000b500  pop     r15
0x14000b502  pop     r14
0x14000b504  pop     r13
0x14000b506  pop     r12
0x14000b508  pop     rdi
0x14000b509  pop     rsi
0x14000b50a  pop     rbp
0x14000b50b  pop     rbx
0x14000b50c  retn
```
