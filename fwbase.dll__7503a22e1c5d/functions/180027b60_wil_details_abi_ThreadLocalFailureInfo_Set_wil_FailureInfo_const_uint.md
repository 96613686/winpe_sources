# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180027b60`
- end: `0x180027d44`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `484`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800242b0`

## callees

- `0x18001eb54`
- `0x1800221b0`
- `0x180025d20`
- `0x180027b60`
- `0x180029fd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027c78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027c78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027c6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027c6a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char *v3; // rbx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  bool v11; // zf
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rbp
  unsigned __int64 *v18; // r14
  LPVOID v19; // r12
  void *v20; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v22; // rcx
  char *v23; // rbp
  __int64 v24; // rax
  char *v25; // rax
  char *v26; // rbx
  _WORD *v27; // r8
  rsize_t v28; // rdi

  *((_DWORD *)this + 1) = a3;
  v3 = (char *)this + 32;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  v6 = -1;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = *((_QWORD *)a2 + 7);
  v8 = 1;
  if ( v7 )
  {
    v10 = -1;
    do
      v11 = *(_BYTE *)(v7 + v10++ + 1) == 0;
    while ( !v11 );
    v9 = v10 + 1;
  }
  else
  {
    v9 = 1;
  }
  v12 = *((_QWORD *)a2 + 16);
  if ( v12 )
  {
    v13 = -1;
    do
      v11 = *(_BYTE *)(v12 + v13++ + 1) == 0;
    while ( !v11 );
    v8 = v13 + 1;
  }
  v14 = *((_QWORD *)a2 + 3);
  if ( v14 )
  {
    v16 = -1;
    do
      v11 = *(_WORD *)(v14 + 2 * v16++ + 2) == 0;
    while ( !v11 );
    v15 = 2 * v16 + 2;
  }
  else
  {
    v15 = 2;
  }
  v17 = v9 + v8 + v15;
  v18 = (unsigned __int64 *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v18 < v17 )
  {
    v19 = wil::details::ProcessHeapAlloc(8u, v9 + v8 + v15);
    if ( v19 )
    {
      v20 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v20);
      *((_QWORD *)this + 8) = v19;
      v3 = (char *)this + 32;
      *v18 = v17;
    }
  }
  v22 = *((_QWORD *)this + 8);
  if ( v22 )
  {
    v23 = (char *)(v22 + *v18);
    v24 = wil::details::WriteResultString<char const *>(v22, v23, *((_QWORD *)a2 + 7), (char *)this + 16);
    v25 = (char *)wil::details::WriteResultString<char const *>(v24, v23, *((_QWORD *)a2 + 16), v3);
    v26 = v25;
    if ( v25 == v23 )
      goto LABEL_26;
    v27 = (_WORD *)*((_QWORD *)a2 + 3);
    if ( !v27 || !*v27 )
      goto LABEL_26;
    do
      v11 = v27[++v6] == 0;
    while ( !v11 );
    v28 = 2 * v6 + 2;
    if ( v23 - v25 >= v28 )
    {
      memcpy_s(v25, v23 - v25, v27, v28);
      *((_QWORD *)this + 7) = v26;
      v26 += v28;
    }
    else
    {
LABEL_26:
      *((_QWORD *)this + 7) = 0;
    }
    memset_0(v26, 0, v23 - v26);
  }
}

```

## disassembly

```asm
0x180027b60  mov     [rsp+arg_8], rbx
0x180027b65  mov     [rsp+arg_10], rbp
0x180027b6a  push    rsi
0x180027b6b  push    rdi
0x180027b6c  push    r12
0x180027b6e  push    r13
0x180027b70  push    r15
0x180027b72  sub     rsp, 20h
0x180027b76  mov     [rcx+4], r8d
0x180027b7a  lea     rbx, [rcx+20h]
0x180027b7e  mov     eax, [rdx+8]
0x180027b81  xor     r12d, r12d
0x180027b84  mov     [rcx+8], eax
0x180027b87  mov     rsi, rcx
0x180027b8a  mov     [rcx+10h], r12
0x180027b8e  mov     r15, rdx
0x180027b91  movzx   eax, word ptr [rdx+40h]
0x180027b95  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180027b9c  mov     [rcx+18h], ax
0x180027ba0  movzx   eax, byte ptr [rdx]
0x180027ba3  mov     [rcx+1Ah], al
0x180027ba6  mov     [rbx], r12
0x180027ba9  mov     rax, [rdx+88h]
0x180027bb0  mov     [rcx+28h], rax
0x180027bb4  mov     rax, [rdx+90h]
0x180027bbb  mov     [rcx+30h], rax
0x180027bbf  mov     [rcx+38h], r12
0x180027bc3  mov     rcx, [rdx+38h]
0x180027bc7  mov     edx, 1
0x180027bcc  test    rcx, rcx
0x180027bcf  jnz     short loc_180027BD6
0x180027bd1  mov     r8d, edx
0x180027bd4  jmp     short loc_180027BEF
0x180027bd6  mov     rax, rdi
0x180027bd9  nop     dword ptr [rax+00000000h]
0x180027be0  cmp     [rcx+rax+1], r12b
0x180027be5  lea     rax, [rax+1]
0x180027be9  jnz     short loc_180027BE0
0x180027beb  lea     r8, [rax+1]; unsigned __int64
0x180027bef  mov     rcx, [r15+80h]
0x180027bf6  test    rcx, rcx
0x180027bf9  jz      short loc_180027C0F
0x180027bfb  mov     rax, rdi
0x180027bfe  xchg    ax, ax
0x180027c00  cmp     [rcx+rax+1], r12b
0x180027c05  lea     rax, [rax+1]
0x180027c09  jnz     short loc_180027C00
0x180027c0b  lea     rdx, [rax+1]
0x180027c0f  mov     rcx, [r15+18h]
0x180027c13  test    rcx, rcx
0x180027c16  jnz     short loc_180027C1F
0x180027c18  mov     eax, 2
0x180027c1d  jmp     short loc_180027C36
0x180027c1f  mov     rax, rdi
0x180027c22  cmp     [rcx+rax*2+2], r12w
0x180027c28  lea     rax, [rax+1]
0x180027c2c  jnz     short loc_180027C22
0x180027c2e  lea     rax, ds:2[rax*2]
0x180027c36  lea     rbp, [rdx+rax]
0x180027c3a  mov     [rsp+48h+arg_0], r14
0x180027c3f  add     rbp, r8
0x180027c42  lea     r14, [rsi+48h]
0x180027c46  cmp     [rsi+40h], r12
0x180027c4a  jz      short loc_180027C51
0x180027c4c  cmp     [r14], rbp
0x180027c4f  jnb     short loc_180027C8C
0x180027c51  mov     rdx, rbp; dwBytes
0x180027c54  mov     ecx, 8; dwFlags
0x180027c59  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180027c5e  mov     r12, rax
0x180027c61  test    rax, rax
0x180027c64  jz      short loc_180027C89
0x180027c66  mov     rbx, [rsi+40h]
0x180027c6a  call    cs:__imp_GetProcessHeap
0x180027c70  mov     r8, rbx; lpMem
0x180027c73  xor     edx, edx; dwFlags
0x180027c75  mov     rcx, rax; hHeap
0x180027c78  call    cs:__imp_HeapFree
0x180027c7e  mov     [rsi+40h], r12
0x180027c82  lea     rbx, [rsi+20h]
0x180027c86  mov     [r14], rbp
0x180027c89  xor     r12d, r12d
0x180027c8c  mov     rcx, [rsi+40h]
0x180027c90  test    rcx, rcx
0x180027c93  jz      loc_180027D28
0x180027c99  mov     rbp, [r14]
0x180027c9c  lea     r9, [rsi+10h]
0x180027ca0  mov     r8, [r15+38h]
0x180027ca4  add     rbp, rcx
0x180027ca7  mov     rdx, rbp
0x180027caa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027caf  mov     r8, [r15+80h]
0x180027cb6  mov     r9, rbx
0x180027cb9  mov     rdx, rbp
0x180027cbc  mov     rcx, rax
0x180027cbf  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027cc4  mov     rbx, rax
0x180027cc7  cmp     rax, rbp
0x180027cca  jz      short loc_180027D14
0x180027ccc  mov     r8, [r15+18h]; Source
0x180027cd0  test    r8, r8
0x180027cd3  jz      short loc_180027D14
0x180027cd5  cmp     word ptr [r8], 0
0x180027cda  jz      short loc_180027D14
0x180027cdc  nop     dword ptr [rax+00h]
0x180027ce0  cmp     word ptr [r8+rdi*2+2], 0
0x180027ce7  lea     rdi, [rdi+1]
0x180027ceb  jnz     short loc_180027CE0
0x180027ced  mov     rdx, rbp
0x180027cf0  lea     rdi, ds:2[rdi*2]
0x180027cf8  sub     rdx, rbx; DestinationSize
0x180027cfb  cmp     rdx, rdi
0x180027cfe  jb      short loc_180027D14
0x180027d00  mov     r9, rdi; SourceSize
0x180027d03  mov     rcx, rbx; Destination
0x180027d06  call    memcpy_s
0x180027d0b  mov     [rsi+38h], rbx
0x180027d0f  add     rbx, rdi
0x180027d12  jmp     short loc_180027D18
0x180027d14  mov     [rsi+38h], r12
0x180027d18  sub     rbp, rbx
0x180027d1b  xor     edx, edx; Val
0x180027d1d  mov     r8, rbp; Size
0x180027d20  mov     rcx, rbx; void *
0x180027d23  call    memset_0
0x180027d28  mov     r14, [rsp+48h+arg_0]
0x180027d2d  mov     rbx, [rsp+48h+arg_8]
0x180027d32  mov     rbp, [rsp+48h+arg_10]
0x180027d37  add     rsp, 20h
0x180027d3b  pop     r15
0x180027d3d  pop     r13
0x180027d3f  pop     r12
0x180027d41  pop     rdi
0x180027d42  pop     rsi
0x180027d43  retn
```
