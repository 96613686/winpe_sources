# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180013eb0`
- end: `0x1800140a5`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `501`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e640`

## callees

- `0x1800021a8`
- `0x18000a000`
- `0x180012bf0`
- `0x180013eb0`
- `0x180018dd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013fce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013fce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013fba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013fba`

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
0x180013eb0  mov     [rsp+arg_8], rbx
0x180013eb5  mov     [rsp+arg_10], rbp
0x180013eba  push    rsi
0x180013ebb  push    rdi
0x180013ebc  push    r12
0x180013ebe  push    r13
0x180013ec0  push    r15
0x180013ec2  sub     rsp, 20h
0x180013ec6  mov     [rcx+4], r8d
0x180013eca  lea     rbx, [rcx+20h]
0x180013ece  mov     eax, [rdx+8]
0x180013ed1  xor     r12d, r12d
0x180013ed4  mov     [rcx+8], eax
0x180013ed7  mov     rsi, rcx
0x180013eda  mov     [rcx+10h], r12
0x180013ede  mov     r15, rdx
0x180013ee1  movzx   eax, word ptr [rdx+40h]
0x180013ee5  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180013eec  mov     [rcx+18h], ax
0x180013ef0  movzx   eax, byte ptr [rdx]
0x180013ef3  mov     [rcx+1Ah], al
0x180013ef6  mov     [rbx], r12
0x180013ef9  mov     rax, [rdx+88h]
0x180013f00  mov     [rcx+28h], rax
0x180013f04  mov     rax, [rdx+90h]
0x180013f0b  mov     [rcx+30h], rax
0x180013f0f  mov     [rcx+38h], r12
0x180013f13  mov     rcx, [rdx+38h]
0x180013f17  mov     edx, 1
0x180013f1c  test    rcx, rcx
0x180013f1f  jnz     short loc_180013F26
0x180013f21  mov     r8d, edx
0x180013f24  jmp     short loc_180013F3F
0x180013f26  mov     rax, rdi
0x180013f29  nop     dword ptr [rax+00000000h]
0x180013f30  cmp     [rcx+rax+1], r12b
0x180013f35  lea     rax, [rax+1]
0x180013f39  jnz     short loc_180013F30
0x180013f3b  lea     r8, [rax+1]; unsigned __int64
0x180013f3f  mov     rcx, [r15+80h]
0x180013f46  test    rcx, rcx
0x180013f49  jz      short loc_180013F5F
0x180013f4b  mov     rax, rdi
0x180013f4e  xchg    ax, ax
0x180013f50  cmp     [rcx+rax+1], r12b
0x180013f55  lea     rax, [rax+1]
0x180013f59  jnz     short loc_180013F50
0x180013f5b  lea     rdx, [rax+1]
0x180013f5f  mov     rcx, [r15+18h]
0x180013f63  test    rcx, rcx
0x180013f66  jnz     short loc_180013F6F
0x180013f68  mov     eax, 2
0x180013f6d  jmp     short loc_180013F86
0x180013f6f  mov     rax, rdi
0x180013f72  cmp     [rcx+rax*2+2], r12w
0x180013f78  lea     rax, [rax+1]
0x180013f7c  jnz     short loc_180013F72
0x180013f7e  lea     rax, ds:2[rax*2]
0x180013f86  lea     rbp, [rdx+rax]
0x180013f8a  mov     [rsp+48h+arg_0], r14
0x180013f8f  add     rbp, r8
0x180013f92  lea     r14, [rsi+48h]
0x180013f96  cmp     [rsi+40h], r12
0x180013f9a  jz      short loc_180013FA1
0x180013f9c  cmp     [r14], rbp
0x180013f9f  jnb     short loc_180013FE8
0x180013fa1  mov     rdx, rbp; dwBytes
0x180013fa4  mov     ecx, 8; dwFlags
0x180013fa9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013fae  mov     r12, rax
0x180013fb1  test    rax, rax
0x180013fb4  jz      short loc_180013FE5
0x180013fb6  mov     rbx, [rsi+40h]
0x180013fba  call    cs:__imp_GetProcessHeap
0x180013fc1  nop     dword ptr [rax+rax+00h]
0x180013fc6  mov     r8, rbx; lpMem
0x180013fc9  xor     edx, edx; dwFlags
0x180013fcb  mov     rcx, rax; hHeap
0x180013fce  call    cs:__imp_HeapFree
0x180013fd5  nop     dword ptr [rax+rax+00h]
0x180013fda  mov     [rsi+40h], r12
0x180013fde  lea     rbx, [rsi+20h]
0x180013fe2  mov     [r14], rbp
0x180013fe5  xor     r12d, r12d
0x180013fe8  mov     rcx, [rsi+40h]
0x180013fec  test    rcx, rcx
0x180013fef  jz      loc_180014088
0x180013ff5  mov     rbp, [r14]
0x180013ff8  lea     r9, [rsi+10h]
0x180013ffc  mov     r8, [r15+38h]
0x180014000  add     rbp, rcx
0x180014003  mov     rdx, rbp
0x180014006  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001400b  mov     r8, [r15+80h]
0x180014012  mov     r9, rbx
0x180014015  mov     rdx, rbp
0x180014018  mov     rcx, rax
0x18001401b  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180014020  mov     rbx, rax
0x180014023  cmp     rax, rbp
0x180014026  jz      short loc_180014074
0x180014028  mov     r8, [r15+18h]; Source
0x18001402c  test    r8, r8
0x18001402f  jz      short loc_180014074
0x180014031  cmp     word ptr [r8], 0
0x180014036  jz      short loc_180014074
0x180014038  nop     dword ptr [rax+rax+00000000h]
0x180014040  cmp     word ptr [r8+rdi*2+2], 0
0x180014047  lea     rdi, [rdi+1]
0x18001404b  jnz     short loc_180014040
0x18001404d  mov     rdx, rbp
0x180014050  lea     rdi, ds:2[rdi*2]
0x180014058  sub     rdx, rbx; DestinationSize
0x18001405b  cmp     rdx, rdi
0x18001405e  jb      short loc_180014074
0x180014060  mov     r9, rdi; SourceSize
0x180014063  mov     rcx, rbx; Destination
0x180014066  call    memcpy_s
0x18001406b  mov     [rsi+38h], rbx
0x18001406f  add     rbx, rdi
0x180014072  jmp     short loc_180014078
0x180014074  mov     [rsi+38h], r12
0x180014078  sub     rbp, rbx
0x18001407b  xor     edx, edx; Val
0x18001407d  mov     r8, rbp; Size
0x180014080  mov     rcx, rbx; void *
0x180014083  call    memset_0
0x180014088  mov     r14, [rsp+48h+arg_0]
0x18001408d  mov     rbx, [rsp+48h+arg_8]
0x180014092  mov     rbp, [rsp+48h+arg_10]
0x180014097  add     rsp, 20h
0x18001409b  pop     r15
0x18001409d  pop     r13
0x18001409f  pop     r12
0x1800140a1  pop     rdi
0x1800140a2  pop     rsi
0x1800140a3  retn
```
