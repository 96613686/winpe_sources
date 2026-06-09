# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000b9ac`
- end: `0x18000bc3d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008220`

## callees

- `0x1800031a0`
- `0x180005d6c`
- `0x180009668`
- `0x18000b9ac`
- `0x180013bfc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb5e`

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
0x18000b9ac  push    rbx
0x18000b9ae  push    rbp
0x18000b9af  push    rsi
0x18000b9b0  push    rdi
0x18000b9b1  push    r12
0x18000b9b3  push    r13
0x18000b9b5  push    r14
0x18000b9b7  push    r15
0x18000b9b9  sub     rsp, 28h
0x18000b9bd  mov     esi, [rcx+10h]
0x18000b9c0  xor     r12d, r12d
0x18000b9c3  mov     r15, rdx
0x18000b9c6  mov     rbx, rcx
0x18000b9c9  mov     ebp, 50h ; 'P'
0x18000b9ce  cmp     [rcx+18h], r12
0x18000b9d2  jnz     short loc_18000BA09
0x18000b9d4  test    esi, esi
0x18000b9d6  jz      short loc_18000BA09
0x18000b9d8  mov     edx, 190h; dwBytes
0x18000b9dd  lea     ecx, [rbp-48h]; dwFlags
0x18000b9e0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b9e5  mov     [rbx+18h], rax
0x18000b9e9  test    rax, rax
0x18000b9ec  jz      short loc_18000BA09
0x18000b9ee  mov     dword ptr [rbx+20h], 5
0x18000b9f5  lea     rcx, [rax+190h]
0x18000b9fc  jmp     short loc_18000BA04
0x18000b9fe  mov     [rax], bp
0x18000ba01  add     rax, rbp
0x18000ba04  cmp     rax, rcx
0x18000ba07  jnz     short loc_18000B9FE
0x18000ba09  mov     rdi, [rbx+18h]
0x18000ba0d  test    rdi, rdi
0x18000ba10  jz      loc_18000BC2B
0x18000ba16  test    esi, esi
0x18000ba18  jz      short loc_18000BA50
0x18000ba1a  movzx   eax, word ptr [rbx+20h]
0x18000ba1e  mov     rcx, rdi
0x18000ba21  lea     rdx, [rax+rax*4]
0x18000ba25  shl     rdx, 4
0x18000ba29  add     rdx, rdi
0x18000ba2c  cmp     rdi, rdx
0x18000ba2f  jz      short loc_18000BA50
0x18000ba31  mov     r8d, [rbx+10h]
0x18000ba35  cmp     [rcx+4], r8d
0x18000ba39  jbe     short loc_18000BA48
0x18000ba3b  mov     eax, [r15+8]
0x18000ba3f  cmp     [rcx+8], eax
0x18000ba42  jz      loc_18000BC2B
0x18000ba48  add     rcx, rbp
0x18000ba4b  cmp     rcx, rdx
0x18000ba4e  jnz     short loc_18000BA35
0x18000ba50  movzx   eax, word ptr [rbx+22h]
0x18000ba54  mov     r8d, 1
0x18000ba5a  movzx   ecx, word ptr [rbx+20h]
0x18000ba5e  add     eax, r8d
0x18000ba61  xor     edx, edx
0x18000ba63  div     ecx
0x18000ba65  mov     ecx, r8d
0x18000ba68  movzx   eax, dx
0x18000ba6b  mov     [rbx+22h], dx
0x18000ba6f  lea     rsi, [rax+rax*4]
0x18000ba73  mov     rax, [rbx+8]
0x18000ba77  shl     rsi, 4
0x18000ba7b  lock xadd [rax], ecx
0x18000ba7f  add     ecx, r8d
0x18000ba82  lea     r13, [rsi+rdi]
0x18000ba86  mov     [rsi+rdi+4], ecx
0x18000ba8a  lea     rbx, [rdi+20h]
0x18000ba8e  mov     eax, [r15+8]
0x18000ba92  add     rbx, rsi
0x18000ba95  mov     [rsi+rdi+8], eax
0x18000ba99  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ba9d  mov     [r13+10h], r12
0x18000baa1  movzx   eax, word ptr [r15+40h]
0x18000baa6  mov     [rsi+rdi+18h], ax
0x18000baab  mov     al, [r15]
0x18000baae  mov     [rsi+rdi+1Ah], al
0x18000bab2  mov     [rbx], r12
0x18000bab5  mov     rax, [r15+88h]
0x18000babc  mov     [rsi+rdi+28h], rax
0x18000bac1  mov     rax, [r15+90h]
0x18000bac8  mov     [rsi+rdi+30h], rax
0x18000bacd  mov     [rsi+rdi+38h], r12
0x18000bad2  mov     rcx, [r15+38h]
0x18000bad6  test    rcx, rcx
0x18000bad9  jnz     short loc_18000BAE0
0x18000badb  mov     edx, r8d
0x18000bade  jmp     short loc_18000BAF0
0x18000bae0  mov     rax, r14
0x18000bae3  inc     rax
0x18000bae6  cmp     [rcx+rax], r12b
0x18000baea  jnz     short loc_18000BAE3
0x18000baec  lea     rdx, [rax+1]
0x18000baf0  mov     rcx, [r15+80h]
0x18000baf7  test    rcx, rcx
0x18000bafa  jz      short loc_18000BB0C
0x18000bafc  mov     rax, r14
0x18000baff  inc     rax
0x18000bb02  cmp     [rcx+rax], r12b
0x18000bb06  jnz     short loc_18000BAFF
0x18000bb08  lea     r8, [rax+1]; unsigned __int64
0x18000bb0c  mov     rcx, [r15+18h]
0x18000bb10  test    rcx, rcx
0x18000bb13  jnz     short loc_18000BB1A
0x18000bb15  lea     eax, [rcx+2]
0x18000bb18  jmp     short loc_18000BB2F
0x18000bb1a  mov     rax, r14
0x18000bb1d  inc     rax
0x18000bb20  cmp     [rcx+rax*2], r12w
0x18000bb25  jnz     short loc_18000BB1D
0x18000bb27  lea     rax, ds:2[rax*2]
0x18000bb2f  lea     rbp, [r8+rax]
0x18000bb33  add     rbp, rdx
0x18000bb36  cmp     [rsi+rdi+40h], r12
0x18000bb3b  jz      short loc_18000BB44
0x18000bb3d  cmp     [rsi+rdi+48h], rbp
0x18000bb42  jnb     short loc_18000BB92
0x18000bb44  mov     rdx, rbp; dwBytes
0x18000bb47  mov     ecx, 8; dwFlags
0x18000bb4c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bb51  mov     r12, rax
0x18000bb54  test    rax, rax
0x18000bb57  jz      short loc_18000BB8F
0x18000bb59  mov     rbx, [rsi+rdi+40h]
0x18000bb5e  call    cs:__imp_GetProcessHeap
0x18000bb65  nop     dword ptr [rax+rax+00h]
0x18000bb6a  mov     r8, rbx; lpMem
0x18000bb6d  xor     edx, edx; dwFlags
0x18000bb6f  mov     rcx, rax; hHeap
0x18000bb72  call    cs:__imp_HeapFree
0x18000bb79  nop     dword ptr [rax+rax+00h]
0x18000bb7e  lea     rbx, [rdi+20h]
0x18000bb82  mov     [rsi+rdi+40h], r12
0x18000bb87  add     rbx, rsi
0x18000bb8a  mov     [rsi+rdi+48h], rbp
0x18000bb8f  xor     r12d, r12d
0x18000bb92  mov     rcx, [rsi+rdi+40h]
0x18000bb97  test    rcx, rcx
0x18000bb9a  jz      loc_18000BC2B
0x18000bba0  mov     rbp, [rsi+rdi+48h]
0x18000bba5  lea     r9, [r13+10h]
0x18000bba9  mov     r8, [r15+38h]
0x18000bbad  add     rbp, rcx
0x18000bbb0  mov     rdx, rbp
0x18000bbb3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000bbb8  mov     r8, [r15+80h]
0x18000bbbf  mov     r9, rbx
0x18000bbc2  mov     rdx, rbp
0x18000bbc5  mov     rcx, rax
0x18000bbc8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000bbcd  mov     rbx, rax
0x18000bbd0  cmp     rax, rbp
0x18000bbd3  jz      short loc_18000BC16
0x18000bbd5  mov     r8, [r15+18h]; Source
0x18000bbd9  test    r8, r8
0x18000bbdc  jz      short loc_18000BC16
0x18000bbde  cmp     [r8], r12w
0x18000bbe2  jz      short loc_18000BC16
0x18000bbe4  inc     r14
0x18000bbe7  cmp     [r8+r14*2], r12w
0x18000bbec  jnz     short loc_18000BBE4
0x18000bbee  mov     rdx, rbp
0x18000bbf1  lea     r14, ds:2[r14*2]
0x18000bbf9  sub     rdx, rbx; DestinationSize
0x18000bbfc  cmp     rdx, r14
0x18000bbff  jb      short loc_18000BC16
0x18000bc01  mov     r9, r14; SourceSize
0x18000bc04  mov     rcx, rbx; Destination
0x18000bc07  call    memcpy_s
0x18000bc0c  mov     [rsi+rdi+38h], rbx
0x18000bc11  add     rbx, r14
0x18000bc14  jmp     short loc_18000BC1B
0x18000bc16  mov     [rsi+rdi+38h], r12
0x18000bc1b  sub     rbp, rbx
0x18000bc1e  xor     edx, edx; Val
0x18000bc20  mov     r8, rbp; Size
0x18000bc23  mov     rcx, rbx; void *
0x18000bc26  call    memset_0
0x18000bc2b  add     rsp, 28h
0x18000bc2f  pop     r15
0x18000bc31  pop     r14
0x18000bc33  pop     r13
0x18000bc35  pop     r12
0x18000bc37  pop     rdi
0x18000bc38  pop     rsi
0x18000bc39  pop     rbp
0x18000bc3a  pop     rbx
0x18000bc3b  retn
```
