# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180011660`
- end: `0x18001186e`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `526`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011ecc`

## callees

- `0x180003374`
- `0x180005b78`
- `0x18000efd0`
- `0x180011660`
- `0x18001a6ac`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180011753`
- `KERNEL32!GetProcessHeap` at `0x180011753`
- `KERNEL32!HeapFree` at `0x180011767`
- `KERNEL32!HeapFree` at `0x180011767`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v4; // r14
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned __int64 v15; // rbp
  rsize_t *v16; // rdi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char **v22; // rdi
  _BYTE *v23; // r8
  char *v24; // r15
  __int64 v25; // rbp
  rsize_t v26; // rbp
  _BYTE *v27; // r8
  char **v28; // rdi
  rsize_t v29; // r14
  void *v30; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  v4 = -1;
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(v6 + v8) );
    v7 = v8 + 1;
  }
  else
  {
    v7 = 1;
  }
  v9 = *((_QWORD *)a2 + 16);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v10 = v11 + 1;
  }
  else
  {
    v10 = 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v7 + v13 + v10;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v7 + v13 + v10);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = (char **)((char *)this + 16);
    v23 = (_BYTE *)*((_QWORD *)a2 + 7);
    v24 = &v20[v21];
    if ( v20 == &v20[v21] )
      goto LABEL_30;
    if ( !v23 )
      goto LABEL_30;
    if ( !*v23 )
      goto LABEL_30;
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    v26 = v25 + 1;
    if ( v21 >= v26 )
    {
      memcpy_s(*((void *const *)this + 8), v21, v23, v26);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = v20;
      v20 += v26;
    }
    else
    {
LABEL_30:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = 0;
    }
    v27 = (_BYTE *)*((_QWORD *)a2 + 16);
    v28 = (char **)((char *)this + 32);
    if ( v20 == v24 || !v27 || !*v27 )
      goto LABEL_40;
    do
      ++v4;
    while ( v27[v4] );
    v29 = v4 + 1;
    if ( v24 - v20 >= v29 )
    {
      memcpy_s(v20, v24 - v20, v27, v29);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = v20;
      v20 += v29;
    }
    else
    {
LABEL_40:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = 0;
    }
    v30 = (void *)wil::details::WriteResultString<unsigned short const *>(
                    v20,
                    v24,
                    *((_QWORD *)a2 + 3),
                    (char *)this + 56);
    memset_0(v30, 0, v24 - (_BYTE *)v30);
  }
}

```

## disassembly

```asm
0x180011660  mov     [rsp+arg_0], rbx
0x180011665  mov     [rsp+arg_8], rbp
0x18001166a  mov     [rsp+arg_10], rsi
0x18001166f  push    rdi
0x180011670  push    r12
0x180011672  push    r13
0x180011674  push    r14
0x180011676  push    r15
0x180011678  sub     rsp, 20h
0x18001167c  mov     [rcx+4], r8d
0x180011680  xor     r13d, r13d
0x180011683  mov     eax, [rdx+8]
0x180011686  mov     rsi, rcx
0x180011689  mov     [rcx+8], eax
0x18001168c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011690  mov     [rcx+10h], r13
0x180011694  mov     r12, rdx
0x180011697  movzx   eax, word ptr [rdx+40h]
0x18001169b  mov     [rcx+18h], ax
0x18001169f  mov     al, [rdx]
0x1800116a1  mov     [rcx+1Ah], al
0x1800116a4  mov     [rcx+20h], r13
0x1800116a8  mov     rax, [rdx+88h]
0x1800116af  mov     [rcx+28h], rax
0x1800116b3  mov     rax, [rdx+90h]
0x1800116ba  mov     [rcx+30h], rax
0x1800116be  mov     [rcx+38h], r13
0x1800116c2  mov     rcx, [rdx+38h]
0x1800116c6  test    rcx, rcx
0x1800116c9  jnz     short loc_1800116D0
0x1800116cb  lea     eax, [rcx+1]
0x1800116ce  jmp     short loc_1800116DF
0x1800116d0  mov     rax, r14
0x1800116d3  inc     rax
0x1800116d6  cmp     [rcx+rax], r13b
0x1800116da  jnz     short loc_1800116D3
0x1800116dc  inc     rax
0x1800116df  mov     rdx, [rdx+80h]
0x1800116e6  test    rdx, rdx
0x1800116e9  jnz     short loc_1800116F0
0x1800116eb  lea     ecx, [rdx+1]
0x1800116ee  jmp     short loc_1800116FF
0x1800116f0  mov     rcx, r14
0x1800116f3  inc     rcx
0x1800116f6  cmp     [rdx+rcx], r13b
0x1800116fa  jnz     short loc_1800116F3
0x1800116fc  inc     rcx
0x1800116ff  mov     r8, [r12+18h]; unsigned __int64
0x180011704  test    r8, r8
0x180011707  jnz     short loc_18001170F
0x180011709  lea     edx, [r8+2]
0x18001170d  jmp     short loc_180011724
0x18001170f  mov     rdx, r14
0x180011712  inc     rdx
0x180011715  cmp     [r8+rdx*2], r13w
0x18001171a  jnz     short loc_180011712
0x18001171c  lea     rdx, ds:2[rdx*2]
0x180011724  lea     rbp, [rdx+rcx]
0x180011728  add     rbp, rax
0x18001172b  lea     rdi, [rsi+48h]
0x18001172f  cmp     [rsi+40h], r13
0x180011733  jz      short loc_18001173A
0x180011735  cmp     [rdi], rbp
0x180011738  jnb     short loc_18001177A
0x18001173a  mov     rdx, rbp; dwBytes
0x18001173d  mov     ecx, 8; dwFlags
0x180011742  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011747  mov     r15, rax
0x18001174a  test    rax, rax
0x18001174d  jz      short loc_18001177A
0x18001174f  mov     rbx, [rsi+40h]
0x180011753  call    cs:__imp_GetProcessHeap
0x18001175a  nop     dword ptr [rax+rax+00h]
0x18001175f  mov     r8, rbx; lpMem
0x180011762  xor     edx, edx; dwFlags
0x180011764  mov     rcx, rax; hHeap
0x180011767  call    cs:__imp_HeapFree
0x18001176e  nop     dword ptr [rax+rax+00h]
0x180011773  mov     [rsi+40h], r15
0x180011777  mov     [rdi], rbp
0x18001177a  mov     rbx, [rsi+40h]
0x18001177e  test    rbx, rbx
0x180011781  jz      loc_180011850
0x180011787  mov     rdx, [rdi]; DestinationSize
0x18001178a  lea     rdi, [rsi+10h]
0x18001178e  mov     r8, [r12+38h]; Source
0x180011793  lea     r15, [rdx+rbx]
0x180011797  cmp     rbx, r15
0x18001179a  jz      short loc_1800117D2
0x18001179c  test    r8, r8
0x18001179f  jz      short loc_1800117D2
0x1800117a1  cmp     [r8], r13b
0x1800117a4  jz      short loc_1800117D2
0x1800117a6  mov     rbp, r14
0x1800117a9  inc     rbp
0x1800117ac  cmp     [r8+rbp], r13b
0x1800117b0  jnz     short loc_1800117A9
0x1800117b2  inc     rbp
0x1800117b5  cmp     rdx, rbp
0x1800117b8  jb      short loc_1800117D2
0x1800117ba  mov     r9, rbp; SourceSize
0x1800117bd  mov     rcx, rbx; Destination
0x1800117c0  call    memcpy_s
0x1800117c5  test    rdi, rdi
0x1800117c8  jz      short loc_1800117CD
0x1800117ca  mov     [rdi], rbx
0x1800117cd  add     rbx, rbp
0x1800117d0  jmp     short loc_1800117DA
0x1800117d2  test    rdi, rdi
0x1800117d5  jz      short loc_1800117DA
0x1800117d7  mov     [rdi], r13
0x1800117da  mov     r8, [r12+80h]; Source
0x1800117e2  lea     rdi, [rsi+20h]
0x1800117e6  cmp     rbx, r15
0x1800117e9  jz      short loc_180011824
0x1800117eb  test    r8, r8
0x1800117ee  jz      short loc_180011824
0x1800117f0  cmp     [r8], r13b
0x1800117f3  jz      short loc_180011824
0x1800117f5  inc     r14
0x1800117f8  cmp     [r8+r14], r13b
0x1800117fc  jnz     short loc_1800117F5
0x1800117fe  mov     rdx, r15
0x180011801  inc     r14
0x180011804  sub     rdx, rbx; DestinationSize
0x180011807  cmp     rdx, r14
0x18001180a  jb      short loc_180011824
0x18001180c  mov     r9, r14; SourceSize
0x18001180f  mov     rcx, rbx; Destination
0x180011812  call    memcpy_s
0x180011817  test    rdi, rdi
0x18001181a  jz      short loc_18001181F
0x18001181c  mov     [rdi], rbx
0x18001181f  add     rbx, r14
0x180011822  jmp     short loc_18001182C
0x180011824  test    rdi, rdi
0x180011827  jz      short loc_18001182C
0x180011829  mov     [rdi], r13
0x18001182c  mov     r8, [r12+18h]
0x180011831  lea     r9, [rsi+38h]
0x180011835  mov     rdx, r15
0x180011838  mov     rcx, rbx
0x18001183b  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180011840  sub     r15, rax
0x180011843  xor     edx, edx; Val
0x180011845  mov     r8, r15; Size
0x180011848  mov     rcx, rax; void *
0x18001184b  call    memset_0
0x180011850  mov     rbx, [rsp+48h+arg_0]
0x180011855  mov     rbp, [rsp+48h+arg_8]
0x18001185a  mov     rsi, [rsp+48h+arg_10]
0x18001185f  add     rsp, 20h
0x180011863  pop     r15
0x180011865  pop     r14
0x180011867  pop     r13
0x180011869  pop     r12
0x18001186b  pop     rdi
0x18001186c  retn
```
