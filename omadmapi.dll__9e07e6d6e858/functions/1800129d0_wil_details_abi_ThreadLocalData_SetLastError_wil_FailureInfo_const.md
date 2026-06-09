# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800129d0`
- end: `0x180012c61`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ccd0`

## callees

- `0x180003db8`
- `0x180004e2c`
- `0x18000649c`
- `0x1800100a8`
- `0x1800129d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012b82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012b82`

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
0x1800129d0  push    rbx
0x1800129d2  push    rbp
0x1800129d3  push    rsi
0x1800129d4  push    rdi
0x1800129d5  push    r12
0x1800129d7  push    r13
0x1800129d9  push    r14
0x1800129db  push    r15
0x1800129dd  sub     rsp, 28h
0x1800129e1  mov     esi, [rcx+10h]
0x1800129e4  xor     r12d, r12d
0x1800129e7  mov     r15, rdx
0x1800129ea  mov     rbx, rcx
0x1800129ed  mov     ebp, 50h ; 'P'
0x1800129f2  cmp     [rcx+18h], r12
0x1800129f6  jnz     short loc_180012A2D
0x1800129f8  test    esi, esi
0x1800129fa  jz      short loc_180012A2D
0x1800129fc  mov     edx, 190h; dwBytes
0x180012a01  lea     ecx, [rbp-48h]; dwFlags
0x180012a04  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180012a09  mov     [rbx+18h], rax
0x180012a0d  test    rax, rax
0x180012a10  jz      short loc_180012A2D
0x180012a12  mov     dword ptr [rbx+20h], 5
0x180012a19  lea     rcx, [rax+190h]
0x180012a20  jmp     short loc_180012A28
0x180012a22  mov     [rax], bp
0x180012a25  add     rax, rbp
0x180012a28  cmp     rax, rcx
0x180012a2b  jnz     short loc_180012A22
0x180012a2d  mov     rdi, [rbx+18h]
0x180012a31  test    rdi, rdi
0x180012a34  jz      loc_180012C4F
0x180012a3a  test    esi, esi
0x180012a3c  jz      short loc_180012A74
0x180012a3e  movzx   eax, word ptr [rbx+20h]
0x180012a42  mov     rcx, rdi
0x180012a45  lea     rdx, [rax+rax*4]
0x180012a49  shl     rdx, 4
0x180012a4d  add     rdx, rdi
0x180012a50  cmp     rdi, rdx
0x180012a53  jz      short loc_180012A74
0x180012a55  mov     r8d, [rbx+10h]
0x180012a59  cmp     [rcx+4], r8d
0x180012a5d  jbe     short loc_180012A6C
0x180012a5f  mov     eax, [r15+8]
0x180012a63  cmp     [rcx+8], eax
0x180012a66  jz      loc_180012C4F
0x180012a6c  add     rcx, rbp
0x180012a6f  cmp     rcx, rdx
0x180012a72  jnz     short loc_180012A59
0x180012a74  movzx   eax, word ptr [rbx+22h]
0x180012a78  mov     r8d, 1
0x180012a7e  movzx   ecx, word ptr [rbx+20h]
0x180012a82  add     eax, r8d
0x180012a85  xor     edx, edx
0x180012a87  div     ecx
0x180012a89  mov     ecx, r8d
0x180012a8c  movzx   eax, dx
0x180012a8f  mov     [rbx+22h], dx
0x180012a93  lea     rsi, [rax+rax*4]
0x180012a97  mov     rax, [rbx+8]
0x180012a9b  shl     rsi, 4
0x180012a9f  lock xadd [rax], ecx
0x180012aa3  add     ecx, r8d
0x180012aa6  lea     r13, [rsi+rdi]
0x180012aaa  mov     [rsi+rdi+4], ecx
0x180012aae  lea     rbx, [rdi+20h]
0x180012ab2  mov     eax, [r15+8]
0x180012ab6  add     rbx, rsi
0x180012ab9  mov     [rsi+rdi+8], eax
0x180012abd  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012ac1  mov     [r13+10h], r12
0x180012ac5  movzx   eax, word ptr [r15+40h]
0x180012aca  mov     [rsi+rdi+18h], ax
0x180012acf  mov     al, [r15]
0x180012ad2  mov     [rsi+rdi+1Ah], al
0x180012ad6  mov     [rbx], r12
0x180012ad9  mov     rax, [r15+88h]
0x180012ae0  mov     [rsi+rdi+28h], rax
0x180012ae5  mov     rax, [r15+90h]
0x180012aec  mov     [rsi+rdi+30h], rax
0x180012af1  mov     [rsi+rdi+38h], r12
0x180012af6  mov     rcx, [r15+38h]
0x180012afa  test    rcx, rcx
0x180012afd  jnz     short loc_180012B04
0x180012aff  mov     edx, r8d
0x180012b02  jmp     short loc_180012B14
0x180012b04  mov     rax, r14
0x180012b07  inc     rax
0x180012b0a  cmp     [rcx+rax], r12b
0x180012b0e  jnz     short loc_180012B07
0x180012b10  lea     rdx, [rax+1]
0x180012b14  mov     rcx, [r15+80h]
0x180012b1b  test    rcx, rcx
0x180012b1e  jz      short loc_180012B30
0x180012b20  mov     rax, r14
0x180012b23  inc     rax
0x180012b26  cmp     [rcx+rax], r12b
0x180012b2a  jnz     short loc_180012B23
0x180012b2c  lea     r8, [rax+1]; unsigned __int64
0x180012b30  mov     rcx, [r15+18h]
0x180012b34  test    rcx, rcx
0x180012b37  jnz     short loc_180012B3E
0x180012b39  lea     eax, [rcx+2]
0x180012b3c  jmp     short loc_180012B53
0x180012b3e  mov     rax, r14
0x180012b41  inc     rax
0x180012b44  cmp     [rcx+rax*2], r12w
0x180012b49  jnz     short loc_180012B41
0x180012b4b  lea     rax, ds:2[rax*2]
0x180012b53  lea     rbp, [r8+rax]
0x180012b57  add     rbp, rdx
0x180012b5a  cmp     [rsi+rdi+40h], r12
0x180012b5f  jz      short loc_180012B68
0x180012b61  cmp     [rsi+rdi+48h], rbp
0x180012b66  jnb     short loc_180012BB6
0x180012b68  mov     rdx, rbp; dwBytes
0x180012b6b  mov     ecx, 8; dwFlags
0x180012b70  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180012b75  mov     r12, rax
0x180012b78  test    rax, rax
0x180012b7b  jz      short loc_180012BB3
0x180012b7d  mov     rbx, [rsi+rdi+40h]
0x180012b82  call    cs:__imp_GetProcessHeap
0x180012b89  nop     dword ptr [rax+rax+00h]
0x180012b8e  mov     r8, rbx; lpMem
0x180012b91  xor     edx, edx; dwFlags
0x180012b93  mov     rcx, rax; hHeap
0x180012b96  call    cs:__imp_HeapFree
0x180012b9d  nop     dword ptr [rax+rax+00h]
0x180012ba2  lea     rbx, [rdi+20h]
0x180012ba6  mov     [rsi+rdi+40h], r12
0x180012bab  add     rbx, rsi
0x180012bae  mov     [rsi+rdi+48h], rbp
0x180012bb3  xor     r12d, r12d
0x180012bb6  mov     rcx, [rsi+rdi+40h]
0x180012bbb  test    rcx, rcx
0x180012bbe  jz      loc_180012C4F
0x180012bc4  mov     rbp, [rsi+rdi+48h]
0x180012bc9  lea     r9, [r13+10h]
0x180012bcd  mov     r8, [r15+38h]
0x180012bd1  add     rbp, rcx
0x180012bd4  mov     rdx, rbp
0x180012bd7  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180012bdc  mov     r8, [r15+80h]
0x180012be3  mov     r9, rbx
0x180012be6  mov     rdx, rbp
0x180012be9  mov     rcx, rax
0x180012bec  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180012bf1  mov     rbx, rax
0x180012bf4  cmp     rax, rbp
0x180012bf7  jz      short loc_180012C3A
0x180012bf9  mov     r8, [r15+18h]; Source
0x180012bfd  test    r8, r8
0x180012c00  jz      short loc_180012C3A
0x180012c02  cmp     [r8], r12w
0x180012c06  jz      short loc_180012C3A
0x180012c08  inc     r14
0x180012c0b  cmp     [r8+r14*2], r12w
0x180012c10  jnz     short loc_180012C08
0x180012c12  mov     rdx, rbp
0x180012c15  lea     r14, ds:2[r14*2]
0x180012c1d  sub     rdx, rbx; DestinationSize
0x180012c20  cmp     rdx, r14
0x180012c23  jb      short loc_180012C3A
0x180012c25  mov     r9, r14; SourceSize
0x180012c28  mov     rcx, rbx; Destination
0x180012c2b  call    memcpy_s
0x180012c30  mov     [rsi+rdi+38h], rbx
0x180012c35  add     rbx, r14
0x180012c38  jmp     short loc_180012C3F
0x180012c3a  mov     [rsi+rdi+38h], r12
0x180012c3f  sub     rbp, rbx
0x180012c42  xor     edx, edx; Val
0x180012c44  mov     r8, rbp; Size
0x180012c47  mov     rcx, rbx; void *
0x180012c4a  call    memset_0
0x180012c4f  add     rsp, 28h
0x180012c53  pop     r15
0x180012c55  pop     r14
0x180012c57  pop     r13
0x180012c59  pop     r12
0x180012c5b  pop     rdi
0x180012c5c  pop     rsi
0x180012c5d  pop     rbp
0x180012c5e  pop     rbx
0x180012c5f  retn
```
