# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140004ed8`
- end: `0x140005169`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003440`

## callees

- `0x14000215c`
- `0x140002b60`
- `0x1400046a4`
- `0x140004ed8`
- `0x1400059dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000509e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000509e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000508a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000508a`

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
0x140004ed8  push    rbx
0x140004eda  push    rbp
0x140004edb  push    rsi
0x140004edc  push    rdi
0x140004edd  push    r12
0x140004edf  push    r13
0x140004ee1  push    r14
0x140004ee3  push    r15
0x140004ee5  sub     rsp, 28h
0x140004ee9  mov     esi, [rcx+10h]
0x140004eec  xor     r12d, r12d
0x140004eef  mov     r15, rdx
0x140004ef2  mov     rbx, rcx
0x140004ef5  mov     ebp, 50h ; 'P'
0x140004efa  cmp     [rcx+18h], r12
0x140004efe  jnz     short loc_140004F35
0x140004f00  test    esi, esi
0x140004f02  jz      short loc_140004F35
0x140004f04  mov     edx, 190h; dwBytes
0x140004f09  lea     ecx, [rbp-48h]; dwFlags
0x140004f0c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004f11  mov     [rbx+18h], rax
0x140004f15  test    rax, rax
0x140004f18  jz      short loc_140004F35
0x140004f1a  mov     dword ptr [rbx+20h], 5
0x140004f21  lea     rcx, [rax+190h]
0x140004f28  jmp     short loc_140004F30
0x140004f2a  mov     [rax], bp
0x140004f2d  add     rax, rbp
0x140004f30  cmp     rax, rcx
0x140004f33  jnz     short loc_140004F2A
0x140004f35  mov     rdi, [rbx+18h]
0x140004f39  test    rdi, rdi
0x140004f3c  jz      loc_140005157
0x140004f42  test    esi, esi
0x140004f44  jz      short loc_140004F7C
0x140004f46  movzx   eax, word ptr [rbx+20h]
0x140004f4a  mov     rcx, rdi
0x140004f4d  lea     rdx, [rax+rax*4]
0x140004f51  shl     rdx, 4
0x140004f55  add     rdx, rdi
0x140004f58  cmp     rdi, rdx
0x140004f5b  jz      short loc_140004F7C
0x140004f5d  mov     r8d, [rbx+10h]
0x140004f61  cmp     [rcx+4], r8d
0x140004f65  jbe     short loc_140004F74
0x140004f67  mov     eax, [r15+8]
0x140004f6b  cmp     [rcx+8], eax
0x140004f6e  jz      loc_140005157
0x140004f74  add     rcx, rbp
0x140004f77  cmp     rcx, rdx
0x140004f7a  jnz     short loc_140004F61
0x140004f7c  movzx   eax, word ptr [rbx+22h]
0x140004f80  mov     r8d, 1
0x140004f86  movzx   ecx, word ptr [rbx+20h]
0x140004f8a  add     eax, r8d
0x140004f8d  xor     edx, edx
0x140004f8f  div     ecx
0x140004f91  mov     ecx, r8d
0x140004f94  movzx   eax, dx
0x140004f97  mov     [rbx+22h], dx
0x140004f9b  lea     rsi, [rax+rax*4]
0x140004f9f  mov     rax, [rbx+8]
0x140004fa3  shl     rsi, 4
0x140004fa7  lock xadd [rax], ecx
0x140004fab  add     ecx, r8d
0x140004fae  lea     r13, [rsi+rdi]
0x140004fb2  mov     [rsi+rdi+4], ecx
0x140004fb6  lea     rbx, [rdi+20h]
0x140004fba  mov     eax, [r15+8]
0x140004fbe  add     rbx, rsi
0x140004fc1  mov     [rsi+rdi+8], eax
0x140004fc5  or      r14, 0FFFFFFFFFFFFFFFFh
0x140004fc9  mov     [r13+10h], r12
0x140004fcd  movzx   eax, word ptr [r15+40h]
0x140004fd2  mov     [rsi+rdi+18h], ax
0x140004fd7  mov     al, [r15]
0x140004fda  mov     [rsi+rdi+1Ah], al
0x140004fde  mov     [rbx], r12
0x140004fe1  mov     rax, [r15+88h]
0x140004fe8  mov     [rsi+rdi+28h], rax
0x140004fed  mov     rax, [r15+90h]
0x140004ff4  mov     [rsi+rdi+30h], rax
0x140004ff9  mov     [rsi+rdi+38h], r12
0x140004ffe  mov     rcx, [r15+38h]
0x140005002  test    rcx, rcx
0x140005005  jnz     short loc_14000500C
0x140005007  mov     edx, r8d
0x14000500a  jmp     short loc_14000501C
0x14000500c  mov     rax, r14
0x14000500f  inc     rax
0x140005012  cmp     [rcx+rax], r12b
0x140005016  jnz     short loc_14000500F
0x140005018  lea     rdx, [rax+1]
0x14000501c  mov     rcx, [r15+80h]
0x140005023  test    rcx, rcx
0x140005026  jz      short loc_140005038
0x140005028  mov     rax, r14
0x14000502b  inc     rax
0x14000502e  cmp     [rcx+rax], r12b
0x140005032  jnz     short loc_14000502B
0x140005034  lea     r8, [rax+1]; unsigned __int64
0x140005038  mov     rcx, [r15+18h]
0x14000503c  test    rcx, rcx
0x14000503f  jnz     short loc_140005046
0x140005041  lea     eax, [rcx+2]
0x140005044  jmp     short loc_14000505B
0x140005046  mov     rax, r14
0x140005049  inc     rax
0x14000504c  cmp     [rcx+rax*2], r12w
0x140005051  jnz     short loc_140005049
0x140005053  lea     rax, ds:2[rax*2]
0x14000505b  lea     rbp, [r8+rax]
0x14000505f  add     rbp, rdx
0x140005062  cmp     [rsi+rdi+40h], r12
0x140005067  jz      short loc_140005070
0x140005069  cmp     [rsi+rdi+48h], rbp
0x14000506e  jnb     short loc_1400050BE
0x140005070  mov     rdx, rbp; dwBytes
0x140005073  mov     ecx, 8; dwFlags
0x140005078  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000507d  mov     r12, rax
0x140005080  test    rax, rax
0x140005083  jz      short loc_1400050BB
0x140005085  mov     rbx, [rsi+rdi+40h]
0x14000508a  call    cs:__imp_GetProcessHeap
0x140005091  nop     dword ptr [rax+rax+00h]
0x140005096  mov     r8, rbx; lpMem
0x140005099  xor     edx, edx; dwFlags
0x14000509b  mov     rcx, rax; hHeap
0x14000509e  call    cs:__imp_HeapFree
0x1400050a5  nop     dword ptr [rax+rax+00h]
0x1400050aa  lea     rbx, [rdi+20h]
0x1400050ae  mov     [rsi+rdi+40h], r12
0x1400050b3  add     rbx, rsi
0x1400050b6  mov     [rsi+rdi+48h], rbp
0x1400050bb  xor     r12d, r12d
0x1400050be  mov     rcx, [rsi+rdi+40h]
0x1400050c3  test    rcx, rcx
0x1400050c6  jz      loc_140005157
0x1400050cc  mov     rbp, [rsi+rdi+48h]
0x1400050d1  lea     r9, [r13+10h]
0x1400050d5  mov     r8, [r15+38h]
0x1400050d9  add     rbp, rcx
0x1400050dc  mov     rdx, rbp
0x1400050df  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400050e4  mov     r8, [r15+80h]
0x1400050eb  mov     r9, rbx
0x1400050ee  mov     rdx, rbp
0x1400050f1  mov     rcx, rax
0x1400050f4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400050f9  mov     rbx, rax
0x1400050fc  cmp     rax, rbp
0x1400050ff  jz      short loc_140005142
0x140005101  mov     r8, [r15+18h]; Source
0x140005105  test    r8, r8
0x140005108  jz      short loc_140005142
0x14000510a  cmp     [r8], r12w
0x14000510e  jz      short loc_140005142
0x140005110  inc     r14
0x140005113  cmp     [r8+r14*2], r12w
0x140005118  jnz     short loc_140005110
0x14000511a  mov     rdx, rbp
0x14000511d  lea     r14, ds:2[r14*2]
0x140005125  sub     rdx, rbx; DestinationSize
0x140005128  cmp     rdx, r14
0x14000512b  jb      short loc_140005142
0x14000512d  mov     r9, r14; SourceSize
0x140005130  mov     rcx, rbx; Destination
0x140005133  call    memcpy_s
0x140005138  mov     [rsi+rdi+38h], rbx
0x14000513d  add     rbx, r14
0x140005140  jmp     short loc_140005147
0x140005142  mov     [rsi+rdi+38h], r12
0x140005147  sub     rbp, rbx
0x14000514a  xor     edx, edx; Val
0x14000514c  mov     r8, rbp; Size
0x14000514f  mov     rcx, rbx; void *
0x140005152  call    memset_0
0x140005157  add     rsp, 28h
0x14000515b  pop     r15
0x14000515d  pop     r14
0x14000515f  pop     r13
0x140005161  pop     r12
0x140005163  pop     rdi
0x140005164  pop     rsi
0x140005165  pop     rbp
0x140005166  pop     rbx
0x140005167  retn
```
