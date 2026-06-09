# CAepStoreAccess::Create(ushort const *,ushort const *,CAepStoreAccess * *)

- ea: `0x1400191ec`
- end: `0x140019329`
- name: `?Create@CAepStoreAccess@@SAJPEBG0PEAPEAV1@@Z`
- size: `317`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, const unsigned __int16 *, struct CAepStoreAccess **)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140016b40`
- `0x140017640`
- `0x140018150`
- `0x1400189e0`
- `0x140018e20`

## callees

- `0x1400018d4`
- `0x14000190c`
- `0x140009060`
- `0x14001917c`
- `0x1400191ec`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14001923f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14001923f`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::Create(
        const unsigned __int16 *Src,
        const unsigned __int16 *a2,
        struct CAepStoreAccess **a3)
{
  char *v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rcx
  void *v9; // rax
  unsigned int v10; // edi
  __int64 v11; // r8
  __int64 v12; // rcx
  void *v13; // rax
  _QWORD *v14; // rsi

  v6 = (char *)operator new(0x58u);
  *(_QWORD *)v6 = &CAepStoreAccess::`vftable';
  *((_DWORD *)v6 + 2) = 1;
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *((_DWORD *)v6 + 8) = 1;
  *((_QWORD *)v6 + 5) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
  *a3 = (struct CAepStoreAccess *)v6;
  v7 = -1;
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    if ( v8 )
    {
      v9 = (void *)DAF_user_alloc(2 * v8 + 2);
      *((_QWORD *)*a3 + 2) = v9;
      if ( !v9 )
        goto LABEL_6;
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      memcpy_0(v9, a2, 2 * v11 + 2);
    }
  }
  v12 = -1;
  do
    ++v12;
  while ( Src[v12] );
  v13 = (void *)DAF_user_alloc(2 * v12 + 2);
  *((_QWORD *)*a3 + 3) = v13;
  if ( v13 )
  {
    v10 = 0;
    do
      ++v7;
    while ( Src[v7] );
    memcpy_0(v13, Src, 2 * v7 + 2);
    return v10;
  }
LABEL_6:
  v10 = -2147024882;
  v14 = *a3;
  if ( *a3 )
  {
    CAepStoreAccess::~CAepStoreAccess(*a3);
    operator delete(v14);
    *a3 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x1400191ec  mov     [rsp+arg_0], rbx
0x1400191f1  mov     [rsp+arg_10], r8
0x1400191f6  push    rsi
0x1400191f7  push    rdi
0x1400191f8  push    r12
0x1400191fa  push    r14
0x1400191fc  push    r15
0x1400191fe  sub     rsp, 20h
0x140019202  mov     r14, r8
0x140019205  mov     r15, rdx
0x140019208  mov     r12, rcx
0x14001920b  mov     ecx, 58h ; 'X'; Size
0x140019210  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140019215  mov     rdi, rax
0x140019218  lea     rax, ??_7CAepStoreAccess@@6B@; const CAepStoreAccess::`vftable'
0x14001921f  mov     [rdi], rax
0x140019222  mov     eax, 1
0x140019227  mov     [rdi+8], eax
0x14001922a  xor     ebx, ebx
0x14001922c  mov     [rdi+10h], rbx
0x140019230  mov     [rdi+18h], rbx
0x140019234  mov     [rdi+20h], eax
0x140019237  mov     [rdi+28h], rbx
0x14001923b  lea     rcx, [rdi+30h]; lpCriticalSection
0x14001923f  call    cs:__imp_InitializeCriticalSection
0x140019245  mov     [r14], rdi
0x140019248  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001924c  test    r15, r15
0x14001924f  jz      short loc_1400192A3
0x140019251  mov     rcx, rsi
0x140019254  inc     rcx
0x140019257  cmp     [r15+rcx*2], bx
0x14001925c  jnz     short loc_140019254
0x14001925e  test    rcx, rcx
0x140019261  jz      short loc_1400192A3
0x140019263  lea     rcx, ds:2[rcx*2]
0x14001926b  call    DAF_user_alloc
0x140019270  mov     rcx, [r14]
0x140019273  mov     [rcx+10h], rax
0x140019277  test    rax, rax
0x14001927a  jnz     short loc_140019283
0x14001927c  mov     edi, 8007000Eh
0x140019281  jmp     short loc_1400192F5
0x140019283  mov     r8, rsi
0x140019286  inc     r8
0x140019289  cmp     [r15+r8*2], bx
0x14001928e  jnz     short loc_140019286
0x140019290  lea     r8, ds:2[r8*2]; Size
0x140019298  mov     rdx, r15; Src
0x14001929b  mov     rcx, rax; void *
0x14001929e  call    memcpy_0
0x1400192a3  mov     rcx, rsi
0x1400192a6  inc     rcx
0x1400192a9  cmp     [r12+rcx*2], bx
0x1400192ae  jnz     short loc_1400192A6
0x1400192b0  lea     rcx, ds:2[rcx*2]
0x1400192b8  call    DAF_user_alloc
0x1400192bd  mov     rcx, [r14]
0x1400192c0  mov     [rcx+18h], rax
0x1400192c4  test    rax, rax
0x1400192c7  jz      short loc_14001927C
0x1400192c9  mov     edi, ebx
0x1400192cb  inc     rsi
0x1400192ce  cmp     [r12+rsi*2], bx
0x1400192d3  jnz     short loc_1400192CB
0x1400192d5  lea     r8, ds:2[rsi*2]; Size
0x1400192dd  mov     rdx, r12; Src
0x1400192e0  mov     rcx, rax; void *
0x1400192e3  call    memcpy_0
0x1400192e8  jmp     short loc_140019315
0x1400192ea  xor     ebx, ebx
0x1400192ec  mov     r14, [rsp+48h+arg_10]
0x1400192f1  mov     edi, [rsp+48h+arg_18]
0x1400192f5  mov     rsi, [r14]
0x1400192f8  test    rsi, rsi
0x1400192fb  jz      short loc_140019315
0x1400192fd  mov     rcx, rsi; this
0x140019300  call    ??1CAepStoreAccess@@IEAA@XZ; CAepStoreAccess::~CAepStoreAccess(void)
0x140019305  mov     edx, 58h ; 'X'; unsigned __int64
0x14001930a  mov     rcx, rsi; void *
0x14001930d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140019312  mov     [r14], rbx
0x140019315  mov     eax, edi
0x140019317  mov     rbx, [rsp+48h+arg_0]
0x14001931c  add     rsp, 20h
0x140019320  pop     r15
0x140019322  pop     r14
0x140019324  pop     r12
0x140019326  pop     rdi
0x140019327  pop     rsi
0x140019328  retn
```
