# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000a94c`
- end: `0x18000abdd`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006f50`

## callees

- `0x18000362c`
- `0x180004a00`
- `0x18000889c`
- `0x18000a94c`
- `0x18000c498`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aafe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aafe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab12`

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
0x18000a94c  push    rbx
0x18000a94e  push    rbp
0x18000a94f  push    rsi
0x18000a950  push    rdi
0x18000a951  push    r12
0x18000a953  push    r13
0x18000a955  push    r14
0x18000a957  push    r15
0x18000a959  sub     rsp, 28h
0x18000a95d  mov     esi, [rcx+10h]
0x18000a960  xor     r12d, r12d
0x18000a963  mov     r15, rdx
0x18000a966  mov     rbx, rcx
0x18000a969  mov     ebp, 50h ; 'P'
0x18000a96e  cmp     [rcx+18h], r12
0x18000a972  jnz     short loc_18000A9A9
0x18000a974  test    esi, esi
0x18000a976  jz      short loc_18000A9A9
0x18000a978  mov     edx, 190h; dwBytes
0x18000a97d  lea     ecx, [rbp-48h]; dwFlags
0x18000a980  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a985  mov     [rbx+18h], rax
0x18000a989  test    rax, rax
0x18000a98c  jz      short loc_18000A9A9
0x18000a98e  mov     dword ptr [rbx+20h], 5
0x18000a995  lea     rcx, [rax+190h]
0x18000a99c  jmp     short loc_18000A9A4
0x18000a99e  mov     [rax], bp
0x18000a9a1  add     rax, rbp
0x18000a9a4  cmp     rax, rcx
0x18000a9a7  jnz     short loc_18000A99E
0x18000a9a9  mov     rdi, [rbx+18h]
0x18000a9ad  test    rdi, rdi
0x18000a9b0  jz      loc_18000ABCB
0x18000a9b6  test    esi, esi
0x18000a9b8  jz      short loc_18000A9F0
0x18000a9ba  movzx   eax, word ptr [rbx+20h]
0x18000a9be  mov     rcx, rdi
0x18000a9c1  lea     rdx, [rax+rax*4]
0x18000a9c5  shl     rdx, 4
0x18000a9c9  add     rdx, rdi
0x18000a9cc  cmp     rdi, rdx
0x18000a9cf  jz      short loc_18000A9F0
0x18000a9d1  mov     r8d, [rbx+10h]
0x18000a9d5  cmp     [rcx+4], r8d
0x18000a9d9  jbe     short loc_18000A9E8
0x18000a9db  mov     eax, [r15+8]
0x18000a9df  cmp     [rcx+8], eax
0x18000a9e2  jz      loc_18000ABCB
0x18000a9e8  add     rcx, rbp
0x18000a9eb  cmp     rcx, rdx
0x18000a9ee  jnz     short loc_18000A9D5
0x18000a9f0  movzx   eax, word ptr [rbx+22h]
0x18000a9f4  mov     r8d, 1
0x18000a9fa  movzx   ecx, word ptr [rbx+20h]
0x18000a9fe  add     eax, r8d
0x18000aa01  xor     edx, edx
0x18000aa03  div     ecx
0x18000aa05  mov     ecx, r8d
0x18000aa08  movzx   eax, dx
0x18000aa0b  mov     [rbx+22h], dx
0x18000aa0f  lea     rsi, [rax+rax*4]
0x18000aa13  mov     rax, [rbx+8]
0x18000aa17  shl     rsi, 4
0x18000aa1b  lock xadd [rax], ecx
0x18000aa1f  add     ecx, r8d
0x18000aa22  lea     r13, [rsi+rdi]
0x18000aa26  mov     [rsi+rdi+4], ecx
0x18000aa2a  lea     rbx, [rdi+20h]
0x18000aa2e  mov     eax, [r15+8]
0x18000aa32  add     rbx, rsi
0x18000aa35  mov     [rsi+rdi+8], eax
0x18000aa39  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000aa3d  mov     [r13+10h], r12
0x18000aa41  movzx   eax, word ptr [r15+40h]
0x18000aa46  mov     [rsi+rdi+18h], ax
0x18000aa4b  mov     al, [r15]
0x18000aa4e  mov     [rsi+rdi+1Ah], al
0x18000aa52  mov     [rbx], r12
0x18000aa55  mov     rax, [r15+88h]
0x18000aa5c  mov     [rsi+rdi+28h], rax
0x18000aa61  mov     rax, [r15+90h]
0x18000aa68  mov     [rsi+rdi+30h], rax
0x18000aa6d  mov     [rsi+rdi+38h], r12
0x18000aa72  mov     rcx, [r15+38h]
0x18000aa76  test    rcx, rcx
0x18000aa79  jnz     short loc_18000AA80
0x18000aa7b  mov     edx, r8d
0x18000aa7e  jmp     short loc_18000AA90
0x18000aa80  mov     rax, r14
0x18000aa83  inc     rax
0x18000aa86  cmp     [rcx+rax], r12b
0x18000aa8a  jnz     short loc_18000AA83
0x18000aa8c  lea     rdx, [rax+1]
0x18000aa90  mov     rcx, [r15+80h]
0x18000aa97  test    rcx, rcx
0x18000aa9a  jz      short loc_18000AAAC
0x18000aa9c  mov     rax, r14
0x18000aa9f  inc     rax
0x18000aaa2  cmp     [rcx+rax], r12b
0x18000aaa6  jnz     short loc_18000AA9F
0x18000aaa8  lea     r8, [rax+1]; unsigned __int64
0x18000aaac  mov     rcx, [r15+18h]
0x18000aab0  test    rcx, rcx
0x18000aab3  jnz     short loc_18000AABA
0x18000aab5  lea     eax, [rcx+2]
0x18000aab8  jmp     short loc_18000AACF
0x18000aaba  mov     rax, r14
0x18000aabd  inc     rax
0x18000aac0  cmp     [rcx+rax*2], r12w
0x18000aac5  jnz     short loc_18000AABD
0x18000aac7  lea     rax, ds:2[rax*2]
0x18000aacf  lea     rbp, [r8+rax]
0x18000aad3  add     rbp, rdx
0x18000aad6  cmp     [rsi+rdi+40h], r12
0x18000aadb  jz      short loc_18000AAE4
0x18000aadd  cmp     [rsi+rdi+48h], rbp
0x18000aae2  jnb     short loc_18000AB32
0x18000aae4  mov     rdx, rbp; dwBytes
0x18000aae7  mov     ecx, 8; dwFlags
0x18000aaec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aaf1  mov     r12, rax
0x18000aaf4  test    rax, rax
0x18000aaf7  jz      short loc_18000AB2F
0x18000aaf9  mov     rbx, [rsi+rdi+40h]
0x18000aafe  call    cs:__imp_GetProcessHeap
0x18000ab05  nop     dword ptr [rax+rax+00h]
0x18000ab0a  mov     r8, rbx; lpMem
0x18000ab0d  xor     edx, edx; dwFlags
0x18000ab0f  mov     rcx, rax; hHeap
0x18000ab12  call    cs:__imp_HeapFree
0x18000ab19  nop     dword ptr [rax+rax+00h]
0x18000ab1e  lea     rbx, [rdi+20h]
0x18000ab22  mov     [rsi+rdi+40h], r12
0x18000ab27  add     rbx, rsi
0x18000ab2a  mov     [rsi+rdi+48h], rbp
0x18000ab2f  xor     r12d, r12d
0x18000ab32  mov     rcx, [rsi+rdi+40h]
0x18000ab37  test    rcx, rcx
0x18000ab3a  jz      loc_18000ABCB
0x18000ab40  mov     rbp, [rsi+rdi+48h]
0x18000ab45  lea     r9, [r13+10h]
0x18000ab49  mov     r8, [r15+38h]
0x18000ab4d  add     rbp, rcx
0x18000ab50  mov     rdx, rbp
0x18000ab53  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ab58  mov     r8, [r15+80h]
0x18000ab5f  mov     r9, rbx
0x18000ab62  mov     rdx, rbp
0x18000ab65  mov     rcx, rax
0x18000ab68  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ab6d  mov     rbx, rax
0x18000ab70  cmp     rax, rbp
0x18000ab73  jz      short loc_18000ABB6
0x18000ab75  mov     r8, [r15+18h]; Source
0x18000ab79  test    r8, r8
0x18000ab7c  jz      short loc_18000ABB6
0x18000ab7e  cmp     [r8], r12w
0x18000ab82  jz      short loc_18000ABB6
0x18000ab84  inc     r14
0x18000ab87  cmp     [r8+r14*2], r12w
0x18000ab8c  jnz     short loc_18000AB84
0x18000ab8e  mov     rdx, rbp
0x18000ab91  lea     r14, ds:2[r14*2]
0x18000ab99  sub     rdx, rbx; DestinationSize
0x18000ab9c  cmp     rdx, r14
0x18000ab9f  jb      short loc_18000ABB6
0x18000aba1  mov     r9, r14; SourceSize
0x18000aba4  mov     rcx, rbx; Destination
0x18000aba7  call    memcpy_s
0x18000abac  mov     [rsi+rdi+38h], rbx
0x18000abb1  add     rbx, r14
0x18000abb4  jmp     short loc_18000ABBB
0x18000abb6  mov     [rsi+rdi+38h], r12
0x18000abbb  sub     rbp, rbx
0x18000abbe  xor     edx, edx; Val
0x18000abc0  mov     r8, rbp; Size
0x18000abc3  mov     rcx, rbx; void *
0x18000abc6  call    memset_0
0x18000abcb  add     rsp, 28h
0x18000abcf  pop     r15
0x18000abd1  pop     r14
0x18000abd3  pop     r13
0x18000abd5  pop     r12
0x18000abd7  pop     rdi
0x18000abd8  pop     rsi
0x18000abd9  pop     rbp
0x18000abda  pop     rbx
0x18000abdb  retn
```
