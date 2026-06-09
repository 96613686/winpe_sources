# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x14000c44c`
- end: `0x14000c5a7`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `347`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000c5f0`
- `0x14000e20c`
- `0x14000e534`

## callees

- `0x140001c48`
- `0x140001c54`
- `0x14000c44c`
- `0x14000eb64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x14000c523`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x14000c540`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x14000c523`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x14000c540`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  void *v7; // r12
  ATL::Checked *v8; // rdi
  __int64 v9; // rcx
  void *v10; // r15
  ATL::Checked *v11; // rax
  ATL::Checked *v12; // rbx
  unsigned int v13; // ebp
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  ATL::Checked **v18; // rcx
  ATL::Checked **v19; // rcx
  unsigned __int64 v21; // [rsp+20h] [rbp-48h]
  unsigned __int64 v22; // [rsp+20h] [rbp-48h]

  if ( !a2 || !a3 )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = (void *)(2 * v6 + 2);
  v8 = (ATL::Checked *)operator new[](saturated_mul((unsigned __int64)v7, 2u));
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = (void *)(2LL * ((int)v9 + 1));
  v11 = (ATL::Checked *)operator new[](saturated_mul((unsigned __int64)v10, 2u));
  v12 = v11;
  if ( v8
    && v11
    && (ATL::Checked::memcpy_s(v8, v7, (unsigned __int64)a2, v7, v21),
        ATL::Checked::memcpy_s(v12, v10, (unsigned __int64)a3, v10, v22),
        v13 = 1,
        (v14 = _o__recalloc(*(_QWORD *)this, *((_DWORD *)this + 4) + 1, 8)) != 0)
    && (v15 = *((_QWORD *)this + 1), *(_QWORD *)this = v14, (v16 = _o__recalloc(v15, *((_DWORD *)this + 4) + 1, 8)) != 0) )
  {
    v17 = *((int *)this + 4);
    *((_QWORD *)this + 1) = v16;
    v18 = (ATL::Checked **)(*(_QWORD *)this + 8 * v17);
    if ( v18 )
      *v18 = v8;
    v19 = (ATL::Checked **)(*((_QWORD *)this + 1) + 8 * v17);
    if ( v19 )
      *v19 = v12;
    ++*((_DWORD *)this + 4);
    v8 = 0;
    v12 = 0;
  }
  else
  {
    v13 = 0;
  }
  operator delete(v12);
  operator delete(v8);
  return v13;
}

```

## disassembly

```asm
0x14000c44c  push    rbx
0x14000c44e  push    rbp
0x14000c44f  push    rsi
0x14000c450  push    rdi
0x14000c451  push    r12
0x14000c453  push    r13
0x14000c455  push    r14
0x14000c457  push    r15
0x14000c459  sub     rsp, 28h
0x14000c45d  xor     r13d, r13d
0x14000c460  mov     rbp, r8
0x14000c463  mov     r14, rdx
0x14000c466  mov     rsi, rcx
0x14000c469  test    rdx, rdx
0x14000c46c  jz      loc_14000C594
0x14000c472  test    r8, r8
0x14000c475  jz      loc_14000C594
0x14000c47b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000c47f  mov     rax, rbx
0x14000c482  inc     rax
0x14000c485  cmp     [rdx+rax*2], r13w
0x14000c48a  jnz     short loc_14000C482
0x14000c48c  lea     r12, ds:2[rax*2]
0x14000c494  mov     eax, 2
0x14000c499  mul     r12
0x14000c49c  cmovb   rax, rbx
0x14000c4a0  mov     rcx, rax; unsigned __int64
0x14000c4a3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000c4a8  mov     rdi, rax
0x14000c4ab  mov     rcx, rbx
0x14000c4ae  inc     rcx
0x14000c4b1  cmp     [rbp+rcx*2+0], r13w
0x14000c4b7  jnz     short loc_14000C4AE
0x14000c4b9  inc     ecx
0x14000c4bb  mov     eax, 2
0x14000c4c0  movsxd  r15, ecx
0x14000c4c3  add     r15, r15
0x14000c4c6  mul     r15
0x14000c4c9  cmovb   rax, rbx
0x14000c4cd  mov     rcx, rax; unsigned __int64
0x14000c4d0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000c4d5  mov     rbx, rax
0x14000c4d8  test    rdi, rdi
0x14000c4db  jz      loc_14000C57D
0x14000c4e1  test    rax, rax
0x14000c4e4  jz      loc_14000C57D
0x14000c4ea  mov     r9, r12; void *
0x14000c4ed  mov     r8, r14; unsigned __int64
0x14000c4f0  mov     rdx, r12; void *
0x14000c4f3  mov     rcx, rdi; this
0x14000c4f6  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x14000c4fb  mov     r9, r15; void *
0x14000c4fe  mov     r8, rbp; unsigned __int64
0x14000c501  mov     rdx, r15; void *
0x14000c504  mov     rcx, rbx; this
0x14000c507  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x14000c50c  mov     eax, [rsi+10h]
0x14000c50f  mov     ebp, 1
0x14000c514  mov     rcx, [rsi]
0x14000c517  add     eax, ebp
0x14000c519  movsxd  rdx, eax
0x14000c51c  lea     r14d, [rbp+7]
0x14000c520  mov     r8d, r14d
0x14000c523  call    cs:__imp__o__recalloc
0x14000c529  test    rax, rax
0x14000c52c  jz      short loc_14000C57D
0x14000c52e  mov     rcx, [rsi+8]
0x14000c532  mov     r8d, r14d
0x14000c535  mov     [rsi], rax
0x14000c538  mov     eax, [rsi+10h]
0x14000c53b  add     eax, ebp
0x14000c53d  movsxd  rdx, eax
0x14000c540  call    cs:__imp__o__recalloc
0x14000c546  test    rax, rax
0x14000c549  jz      short loc_14000C57D
0x14000c54b  movsxd  rdx, dword ptr [rsi+10h]
0x14000c54f  mov     [rsi+8], rax
0x14000c553  mov     rax, [rsi]
0x14000c556  lea     rcx, [rax+rdx*8]
0x14000c55a  test    rcx, rcx
0x14000c55d  jz      short loc_14000C562
0x14000c55f  mov     [rcx], rdi
0x14000c562  mov     rax, [rsi+8]
0x14000c566  lea     rcx, [rax+rdx*8]
0x14000c56a  test    rcx, rcx
0x14000c56d  jz      short loc_14000C572
0x14000c56f  mov     [rcx], rbx
0x14000c572  add     [rsi+10h], ebp
0x14000c575  mov     rdi, r13
0x14000c578  mov     rbx, r13
0x14000c57b  jmp     short loc_14000C580
0x14000c57d  mov     ebp, r13d
0x14000c580  mov     rcx, rbx; Block
0x14000c583  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c588  mov     rcx, rdi; Block
0x14000c58b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c590  mov     eax, ebp
0x14000c592  jmp     short loc_14000C596
0x14000c594  xor     eax, eax
0x14000c596  add     rsp, 28h
0x14000c59a  pop     r15
0x14000c59c  pop     r14
0x14000c59e  pop     r13
0x14000c5a0  pop     r12
0x14000c5a2  pop     rdi
0x14000c5a3  pop     rsi
0x14000c5a4  pop     rbp
0x14000c5a5  pop     rbx
0x14000c5a6  retn
```
