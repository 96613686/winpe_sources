# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140008b50`
- end: `0x140008de8`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `664`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005460`

## callees

- `0x14000271f`
- `0x1400036dc`
- `0x1400067f8`
- `0x140008b50`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008dab`
- `msvcrt!memcpy_s` at `0x140008dab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008d02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008d02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008d16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008d16`

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
0x140008b50  push    rbx
0x140008b52  push    rbp
0x140008b53  push    rsi
0x140008b54  push    rdi
0x140008b55  push    r12
0x140008b57  push    r13
0x140008b59  push    r14
0x140008b5b  push    r15
0x140008b5d  sub     rsp, 28h
0x140008b61  mov     esi, [rcx+10h]
0x140008b64  xor     r12d, r12d
0x140008b67  mov     r15, rdx
0x140008b6a  mov     rbx, rcx
0x140008b6d  mov     ebp, 50h ; 'P'
0x140008b72  cmp     [rcx+18h], r12
0x140008b76  jnz     short loc_140008BAD
0x140008b78  test    esi, esi
0x140008b7a  jz      short loc_140008BAD
0x140008b7c  mov     edx, 190h; dwBytes
0x140008b81  lea     ecx, [rbp-48h]; dwFlags
0x140008b84  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008b89  mov     [rbx+18h], rax
0x140008b8d  test    rax, rax
0x140008b90  jz      short loc_140008BAD
0x140008b92  mov     dword ptr [rbx+20h], 5
0x140008b99  lea     rcx, [rax+190h]
0x140008ba0  jmp     short loc_140008BA8
0x140008ba2  mov     [rax], bp
0x140008ba5  add     rax, rbp
0x140008ba8  cmp     rax, rcx
0x140008bab  jnz     short loc_140008BA2
0x140008bad  mov     rdi, [rbx+18h]
0x140008bb1  test    rdi, rdi
0x140008bb4  jz      loc_140008DD6
0x140008bba  test    esi, esi
0x140008bbc  jz      short loc_140008BF4
0x140008bbe  movzx   eax, word ptr [rbx+20h]
0x140008bc2  mov     rcx, rdi
0x140008bc5  lea     rdx, [rax+rax*4]
0x140008bc9  shl     rdx, 4
0x140008bcd  add     rdx, rdi
0x140008bd0  cmp     rdi, rdx
0x140008bd3  jz      short loc_140008BF4
0x140008bd5  mov     r8d, [rbx+10h]
0x140008bd9  cmp     [rcx+4], r8d
0x140008bdd  jbe     short loc_140008BEC
0x140008bdf  mov     eax, [r15+8]
0x140008be3  cmp     [rcx+8], eax
0x140008be6  jz      loc_140008DD6
0x140008bec  add     rcx, rbp
0x140008bef  cmp     rcx, rdx
0x140008bf2  jnz     short loc_140008BD9
0x140008bf4  movzx   eax, word ptr [rbx+22h]
0x140008bf8  mov     r8d, 1
0x140008bfe  movzx   ecx, word ptr [rbx+20h]
0x140008c02  add     eax, r8d
0x140008c05  xor     edx, edx
0x140008c07  div     ecx
0x140008c09  mov     ecx, r8d
0x140008c0c  movzx   eax, dx
0x140008c0f  mov     [rbx+22h], dx
0x140008c13  lea     rsi, [rax+rax*4]
0x140008c17  mov     rax, [rbx+8]
0x140008c1b  shl     rsi, 4
0x140008c1f  lock xadd [rax], ecx
0x140008c23  add     ecx, r8d
0x140008c26  lea     r13, [rsi+rdi]
0x140008c2a  mov     [rsi+rdi+4], ecx
0x140008c2e  lea     rbx, [rdi+20h]
0x140008c32  mov     eax, [r15+8]
0x140008c36  add     rbx, rsi
0x140008c39  mov     [rsi+rdi+8], eax
0x140008c3d  or      r14, 0FFFFFFFFFFFFFFFFh
0x140008c41  mov     [r13+10h], r12
0x140008c45  movzx   eax, word ptr [r15+40h]
0x140008c4a  mov     [rsi+rdi+18h], ax
0x140008c4f  mov     al, [r15]
0x140008c52  mov     [rsi+rdi+1Ah], al
0x140008c56  mov     [rbx], r12
0x140008c59  mov     rax, [r15+88h]
0x140008c60  mov     [rsi+rdi+28h], rax
0x140008c65  mov     rax, [r15+90h]
0x140008c6c  mov     [rsi+rdi+30h], rax
0x140008c71  mov     [rsi+rdi+38h], r12
0x140008c76  mov     rcx, [r15+38h]
0x140008c7a  test    rcx, rcx
0x140008c7d  jnz     short loc_140008C84
0x140008c7f  mov     edx, r8d
0x140008c82  jmp     short loc_140008C94
0x140008c84  mov     rax, r14
0x140008c87  inc     rax
0x140008c8a  cmp     [rcx+rax], r12b
0x140008c8e  jnz     short loc_140008C87
0x140008c90  lea     rdx, [rax+1]
0x140008c94  mov     rcx, [r15+80h]
0x140008c9b  test    rcx, rcx
0x140008c9e  jz      short loc_140008CB0
0x140008ca0  mov     rax, r14
0x140008ca3  inc     rax
0x140008ca6  cmp     [rcx+rax], r12b
0x140008caa  jnz     short loc_140008CA3
0x140008cac  lea     r8, [rax+1]; unsigned __int64
0x140008cb0  mov     rcx, [r15+18h]
0x140008cb4  test    rcx, rcx
0x140008cb7  jnz     short loc_140008CBE
0x140008cb9  lea     eax, [rcx+2]
0x140008cbc  jmp     short loc_140008CD3
0x140008cbe  mov     rax, r14
0x140008cc1  inc     rax
0x140008cc4  cmp     [rcx+rax*2], r12w
0x140008cc9  jnz     short loc_140008CC1
0x140008ccb  lea     rax, ds:2[rax*2]
0x140008cd3  lea     rbp, [r8+rax]
0x140008cd7  add     rbp, rdx
0x140008cda  cmp     [rsi+rdi+40h], r12
0x140008cdf  jz      short loc_140008CE8
0x140008ce1  cmp     [rsi+rdi+48h], rbp
0x140008ce6  jnb     short loc_140008D36
0x140008ce8  mov     rdx, rbp; dwBytes
0x140008ceb  mov     ecx, 8; dwFlags
0x140008cf0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008cf5  mov     r12, rax
0x140008cf8  test    rax, rax
0x140008cfb  jz      short loc_140008D33
0x140008cfd  mov     rbx, [rsi+rdi+40h]
0x140008d02  call    cs:__imp_GetProcessHeap
0x140008d09  nop     dword ptr [rax+rax+00h]
0x140008d0e  mov     r8, rbx; lpMem
0x140008d11  xor     edx, edx; dwFlags
0x140008d13  mov     rcx, rax; hHeap
0x140008d16  call    cs:__imp_HeapFree
0x140008d1d  nop     dword ptr [rax+rax+00h]
0x140008d22  lea     rbx, [rdi+20h]
0x140008d26  mov     [rsi+rdi+40h], r12
0x140008d2b  add     rbx, rsi
0x140008d2e  mov     [rsi+rdi+48h], rbp
0x140008d33  xor     r12d, r12d
0x140008d36  mov     rcx, [rsi+rdi+40h]
0x140008d3b  test    rcx, rcx
0x140008d3e  jz      loc_140008DD6
0x140008d44  mov     rbp, [rsi+rdi+48h]
0x140008d49  lea     r9, [r13+10h]
0x140008d4d  mov     r8, [r15+38h]
0x140008d51  add     rbp, rcx
0x140008d54  mov     rdx, rbp
0x140008d57  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140008d5c  mov     r8, [r15+80h]
0x140008d63  mov     r9, rbx
0x140008d66  mov     rdx, rbp
0x140008d69  mov     rcx, rax
0x140008d6c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140008d71  mov     rbx, rax
0x140008d74  cmp     rax, rbp
0x140008d77  jz      short loc_140008DC1
0x140008d79  mov     r8, [r15+18h]; Source
0x140008d7d  test    r8, r8
0x140008d80  jz      short loc_140008DC1
0x140008d82  cmp     [r8], r12w
0x140008d86  jz      short loc_140008DC1
0x140008d88  inc     r14
0x140008d8b  cmp     [r8+r14*2], r12w
0x140008d90  jnz     short loc_140008D88
0x140008d92  mov     rdx, rbp
0x140008d95  lea     r14, ds:2[r14*2]
0x140008d9d  sub     rdx, rbx; DestinationSize
0x140008da0  cmp     rdx, r14
0x140008da3  jb      short loc_140008DC1
0x140008da5  mov     r9, r14; SourceSize
0x140008da8  mov     rcx, rbx; Destination
0x140008dab  call    cs:__imp_memcpy_s
0x140008db2  nop     dword ptr [rax+rax+00h]
0x140008db7  mov     [rsi+rdi+38h], rbx
0x140008dbc  add     rbx, r14
0x140008dbf  jmp     short loc_140008DC6
0x140008dc1  mov     [rsi+rdi+38h], r12
0x140008dc6  sub     rbp, rbx
0x140008dc9  xor     edx, edx; Val
0x140008dcb  mov     r8, rbp; Size
0x140008dce  mov     rcx, rbx; void *
0x140008dd1  call    memset_0
0x140008dd6  add     rsp, 28h
0x140008dda  pop     r15
0x140008ddc  pop     r14
0x140008dde  pop     r13
0x140008de0  pop     r12
0x140008de2  pop     rdi
0x140008de3  pop     rsi
0x140008de4  pop     rbp
0x140008de5  pop     rbx
0x140008de6  retn
```
