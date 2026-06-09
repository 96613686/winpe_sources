# CopyDBIDs(tagDBID *,tagDBID const *)

- ea: `0x18002b288`
- end: `0x18002b481`
- name: `?CopyDBIDs@@YAXPEAUtagDBID@@PEBU1@@Z`
- size: `505`
- prototype: `void __fastcall(struct tagDBID *, const struct tagDBID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002aee0`
- `0x18002bb50`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x1800028b8`
- `0x18000ca88`
- `0x18002b288`
- `0x18002dca4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CopyDBIDs(struct tagDBID *a1, const struct tagDBID *a2)
{
  DBKIND eKind; // ecx
  DBKIND v5; // ecx
  DBKIND v6; // ecx
  DBKIND v7; // ecx
  DBKIND v8; // ecx
  DBKIND v9; // ecx
  GUID *v10; // r15
  unsigned __int64 v11; // rbp
  unsigned __int128 v12; // rax
  unsigned __int8 *v13; // rbx
  int v14; // eax
  unsigned __int64 v15; // rdi
  unsigned __int128 v16; // rax
  OLECHAR *v17; // rax
  GUID *v18; // [rsp+50h] [rbp+8h]

  if ( !a1 || !a2 )
    ThrowHR(-2147467259);
  a1->eKind = a2->eKind;
  eKind = a2->eKind;
  if ( !eKind )
  {
    a1->uGuid = a2->uGuid;
    v15 = -1;
    do
      ++v15;
    while ( a2->uName.pwszName[v15] );
    goto LABEL_26;
  }
  v5 = eKind - 1;
  if ( !v5 )
  {
    a1->uGuid = a2->uGuid;
    goto LABEL_23;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a2->uName.pwszName[v15] );
LABEL_26:
    v16 = (v15 + 1) * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v15 + 1, 2u) )
      LODWORD(v16) = -1;
    v17 = (OLECHAR *)MMMAlloc(v16, DWORD2(v16));
    a1->uName.pwszName = v17;
    OnNullThrowOOM(v17);
    v14 = StringCchCopyNW(a1->uName.pwszName, v15 + 1, a2->uName.pwszName, v15);
    goto LABEL_29;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( !v8 )
    {
      v18 = (GUID *)MMMAlloc(0x10u, (unsigned int)a2);
      OnNullThrowOOM(v18);
      *a1->uGuid.pguid = *a2->uGuid.pguid;
      a1->uGuid.pguid = v18;
      goto LABEL_12;
    }
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 != 1 )
        ThrowHR(-2147467259);
      a1->uGuid = a2->uGuid;
      goto LABEL_12;
    }
LABEL_23:
    a1->uName.ulPropid = a2->uName.ulPropid;
    goto LABEL_12;
  }
  v10 = (GUID *)MMMAlloc(0x10u, (unsigned int)a2);
  OnNullThrowOOM(v10);
  *v10 = *a2->uGuid.pguid;
  v11 = -1;
  do
    ++v11;
  while ( a2->uName.pwszName[v11] );
  v12 = (v11 + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v11 + 1, 2u) )
    LODWORD(v12) = -1;
  v13 = MMMAlloc(v12, DWORD2(v12));
  OnNullThrowOOM(v13);
  v14 = StringCchCopyNW(a1->uName.pwszName, v11 + 1, a2->uName.pwszName, v11);
  a1->uGuid.pguid = v10;
  a1->uName.pwszName = (LPOLESTR)v13;
LABEL_29:
  if ( v14 < 0 )
    ThrowHR(v14);
LABEL_12:
  operator delete(0);
  operator delete(0);
}

```

## disassembly

```asm
0x18002b288  mov     r11, rsp
0x18002b28b  mov     [r11+10h], rbx
0x18002b28f  mov     [r11+20h], rbp
0x18002b293  push    rsi
0x18002b294  push    rdi
0x18002b295  push    r12
0x18002b297  push    r14
0x18002b299  push    r15
0x18002b29b  sub     rsp, 20h
0x18002b29f  mov     rsi, rdx
0x18002b2a2  mov     r14, rcx
0x18002b2a5  xor     r12d, r12d
0x18002b2a8  test    rcx, rcx
0x18002b2ab  jz      loc_18002B476
0x18002b2b1  test    rdx, rdx
0x18002b2b4  jz      loc_18002B476
0x18002b2ba  mov     eax, [rdx+10h]
0x18002b2bd  mov     [rcx+10h], eax
0x18002b2c0  mov     [r11+8], r12
0x18002b2c4  mov     [r11+18h], r12
0x18002b2c8  mov     ecx, [rdx+10h]
0x18002b2cb  test    ecx, ecx
0x18002b2cd  jz      loc_18002B413
0x18002b2d3  sub     ecx, 1
0x18002b2d6  jz      loc_18002B3FF
0x18002b2dc  sub     ecx, 1
0x18002b2df  jz      loc_18002B3E8
0x18002b2e5  sub     ecx, 1
0x18002b2e8  jz      short loc_18002B361
0x18002b2ea  sub     ecx, 1
0x18002b2ed  jz      short loc_18002B335
0x18002b2ef  sub     ecx, 1
0x18002b2f2  jz      loc_18002B407
0x18002b2f8  cmp     ecx, 1
0x18002b2fb  jz      short loc_18002B308
0x18002b2fd  mov     ecx, 80004005h; int
0x18002b302  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002b308  movups  xmm0, xmmword ptr [rdx]
0x18002b30b  movdqu  xmmword ptr [r14], xmm0
0x18002b310  xor     ecx, ecx; void *
0x18002b312  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b317  nop
0x18002b318  xor     ecx, ecx; void *
0x18002b31a  mov     rbx, [rsp+48h+arg_8]
0x18002b31f  mov     rbp, [rsp+48h+arg_18]
0x18002b324  add     rsp, 20h
0x18002b328  pop     r15
0x18002b32a  pop     r14
0x18002b32c  pop     r12
0x18002b32e  pop     rdi
0x18002b32f  pop     rsi
0x18002b330  jmp     ??3@YAXPEAX@Z; operator delete(void *)
0x18002b335  mov     ecx, 10h; unsigned int
0x18002b33a  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002b33f  mov     rbx, rax
0x18002b342  mov     [rsp+48h+arg_0], rax
0x18002b347  mov     rcx, rax; void *
0x18002b34a  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18002b34f  mov     rax, [rsi]
0x18002b352  mov     rcx, [r14]
0x18002b355  movups  xmm0, xmmword ptr [rax]
0x18002b358  movdqu  xmmword ptr [rcx], xmm0
0x18002b35c  mov     [r14], rbx
0x18002b35f  jmp     short loc_18002B310
0x18002b361  mov     ecx, 10h; unsigned int
0x18002b366  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002b36b  mov     r15, rax
0x18002b36e  mov     [rsp+48h+arg_0], rax
0x18002b373  mov     rcx, rax; void *
0x18002b376  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18002b37b  mov     rcx, [rsi]
0x18002b37e  movups  xmm0, xmmword ptr [rcx]
0x18002b381  movdqu  xmmword ptr [r15], xmm0
0x18002b386  mov     rax, [rsi+18h]
0x18002b38a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002b38e  mov     rbp, rcx
0x18002b391  inc     rbp
0x18002b394  cmp     [rax+rbp*2], r12w
0x18002b399  jnz     short loc_18002B391
0x18002b39b  lea     rdi, [rbp+1]
0x18002b39f  mov     eax, 2
0x18002b3a4  mul     rdi
0x18002b3a7  cmovb   rax, rcx
0x18002b3ab  mov     ecx, eax; unsigned int
0x18002b3ad  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002b3b2  mov     rbx, rax
0x18002b3b5  mov     [rsp+48h+arg_10], rax
0x18002b3ba  mov     rcx, rax; void *
0x18002b3bd  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18002b3c2  mov     r9, rbp; unsigned __int64
0x18002b3c5  mov     r8, [rsi+18h]; unsigned __int16 *
0x18002b3c9  mov     rdx, rdi; unsigned __int64
0x18002b3cc  mov     rcx, [r14+18h]; unsigned __int16 *
0x18002b3d0  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002b3d5  mov     [rsp+48h+arg_0], r12
0x18002b3da  mov     [r14], r15
0x18002b3dd  mov     [rsp+48h+arg_10], r12
0x18002b3e2  mov     [r14+18h], rbx
0x18002b3e6  jmp     short loc_18002B466
0x18002b3e8  mov     rax, [rdx+18h]
0x18002b3ec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002b3f0  mov     rdi, rcx
0x18002b3f3  inc     rdi
0x18002b3f6  cmp     [rax+rdi*2], r12w
0x18002b3fb  jnz     short loc_18002B3F3
0x18002b3fd  jmp     short loc_18002B430
0x18002b3ff  movups  xmm0, xmmword ptr [rdx]
0x18002b402  movdqu  xmmword ptr [r14], xmm0
0x18002b407  mov     eax, [rdx+18h]
0x18002b40a  mov     [r14+18h], eax
0x18002b40e  jmp     loc_18002B310
0x18002b413  movups  xmm0, xmmword ptr [rdx]
0x18002b416  movdqu  xmmword ptr [r14], xmm0
0x18002b41b  mov     rax, [rdx+18h]
0x18002b41f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002b423  mov     rdi, rcx
0x18002b426  inc     rdi
0x18002b429  cmp     [rax+rdi*2], r12w
0x18002b42e  jnz     short loc_18002B426
0x18002b430  mov     eax, 2
0x18002b435  lea     rbx, [rdi+1]
0x18002b439  mul     rbx
0x18002b43c  cmovb   rax, rcx
0x18002b440  mov     ecx, eax; unsigned int
0x18002b442  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002b447  mov     [r14+18h], rax
0x18002b44b  mov     rcx, rax; void *
0x18002b44e  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18002b453  mov     r9, rdi; unsigned __int64
0x18002b456  mov     r8, [rsi+18h]; unsigned __int16 *
0x18002b45a  mov     rdx, rbx; unsigned __int64
0x18002b45d  mov     rcx, [r14+18h]; unsigned __int16 *
0x18002b461  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002b466  test    eax, eax
0x18002b468  jns     loc_18002B310
0x18002b46e  mov     ecx, eax; int
0x18002b470  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002b476  mov     ecx, 80004005h; int
0x18002b47b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
