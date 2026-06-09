# CSecConLib::ListExtensionFiles(ushort const *,ushort * *,ulong *)

- ea: `0x18000f478`
- end: `0x18000f66d`
- name: `?ListExtensionFiles@CSecConLib@@QEAAJPEBGPEAPEAGPEAK@Z`
- size: `501`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180009700`

## callees

- `0x180001048`
- `0x180001054`
- `0x18000f02c`
- `0x18000f1c0`
- `0x18000f478`
- `0x1800111a2`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000f5b4`
- `msvcrt!wcscpy_s` at `0x18000f5b4`
- `msvcrt!wcschr` at `0x18000f52b`
- `msvcrt!wcschr` at `0x18000f52b`

## pseudocode

```c
__int64 __fastcall CSecConLib::ListExtensionFiles(
        CSecConLib *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  int inited; // ebx
  wchar_t *v7; // rsi
  _WORD *v8; // rdi
  unsigned int v9; // ebp
  char *v10; // r12
  const wchar_t *v11; // rax
  const wchar_t *v12; // r15
  wchar_t *v13; // rax
  wchar_t *v14; // r14
  __int64 v15; // rax
  int v16; // r13d
  _WORD *v17; // rax
  _WORD *v18; // r12
  const wchar_t *v19; // r14
  __int64 v20; // rax
  void *Block; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v23[16]; // [rsp+38h] [rbp-40h] BYREF

  Block = 0;
  v23[0] = 0;
  inited = CSecConLib::InternalInitIfNecessary(this);
  if ( inited < 0 )
    return (unsigned int)inited;
  inited = CSecConLib::GetMultiSZPropVal(this, a2, 0x878u, (unsigned __int16 **)&Block, v23);
  if ( inited < 0 )
    return (unsigned int)inited;
  v7 = (wchar_t *)Block;
  if ( !Block )
    return (unsigned int)-2147024882;
  if ( !*(_WORD *)Block )
    goto LABEL_20;
  v8 = 0;
  v9 = 1;
  LODWORD(Block) = 1;
  v10 = (char *)&v7[v23[0] - 1];
  v11 = v7;
  *(_QWORD *)v23 = v10;
  do
  {
    v12 = v11 + 2;
    v13 = wcschr(v11 + 2, 0x2Cu);
    v14 = v13;
    if ( v13 )
    {
      *v13 = 0;
      v15 = -1;
      do
        ++v15;
      while ( v12[v15] );
      v16 = v15 + v9;
      v9 += v15 + 1;
      v17 = operator new[](saturated_mul((unsigned int)(v16 + 1), 2u));
      v18 = v17;
      if ( !v17 )
        goto LABEL_21;
      v19 = v14 + 1;
      if ( v8 )
      {
        memcpy_0(v17, v8, 2LL * (unsigned int)Block);
        operator delete(v8);
      }
      wcscpy_s(&v18[(_DWORD)Block - 1], v9 - (unsigned int)Block + 1, v12);
      LODWORD(Block) = v16 + 1;
      v8 = v18;
      v18[v16 - 1] = 0;
      v18[v16] = 0;
      v10 = *(char **)v23;
    }
    else
    {
      v19 = v12;
    }
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    v11 = &v19[(unsigned int)v20 + 1];
  }
  while ( v11 <= (const wchar_t *)v10 && *v11 );
  if ( !v8 )
  {
LABEL_20:
    v8 = operator new[](4u);
    if ( !v8 )
    {
LABEL_21:
      inited = -2147024882;
      goto LABEL_24;
    }
    v9 = 2;
    *v8 = 0;
    v8[1] = 0;
  }
  *a3 = v8;
  *a4 = v9;
LABEL_24:
  if ( v7 )
    operator delete(v7);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000f478  mov     rax, rsp
0x18000f47b  mov     [rax+8], rbx
0x18000f47f  mov     [rax+20h], r9
0x18000f483  mov     [rax+18h], r8
0x18000f487  push    rbp
0x18000f488  push    rsi
0x18000f489  push    rdi
0x18000f48a  push    r12
0x18000f48c  push    r13
0x18000f48e  push    r14
0x18000f490  push    r15
0x18000f492  sub     rsp, 40h
0x18000f496  xor     r13d, r13d
0x18000f499  mov     rsi, rdx
0x18000f49c  mov     [rax-48h], r13
0x18000f4a0  mov     rdi, rcx
0x18000f4a3  mov     [rax-40h], r13d
0x18000f4a7  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000f4ac  mov     ebx, eax
0x18000f4ae  test    eax, eax
0x18000f4b0  js      loc_18000F653
0x18000f4b6  lea     rax, [rsp+78h+var_40]
0x18000f4bb  mov     r8d, 878h; unsigned int
0x18000f4c1  lea     r9, [rsp+78h+Block]; unsigned __int16 **
0x18000f4c6  mov     [rsp+78h+var_58], rax; unsigned int *
0x18000f4cb  mov     rdx, rsi; unsigned __int16 *
0x18000f4ce  mov     rcx, rdi; this
0x18000f4d1  call    ?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z; CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)
0x18000f4d6  mov     ebx, eax
0x18000f4d8  test    eax, eax
0x18000f4da  js      loc_18000F653
0x18000f4e0  mov     rsi, [rsp+78h+Block]
0x18000f4e5  test    rsi, rsi
0x18000f4e8  jnz     short loc_18000F4F4
0x18000f4ea  mov     ebx, 8007000Eh
0x18000f4ef  jmp     loc_18000F653
0x18000f4f4  cmp     [rsi], r13w
0x18000f4f8  jz      loc_18000F609
0x18000f4fe  mov     eax, 1
0x18000f503  mov     rdi, r13
0x18000f506  mov     ebp, eax
0x18000f508  mov     dword ptr [rsp+78h+Block], eax
0x18000f50c  mov     eax, [rsp+78h+var_40]
0x18000f510  dec     rax
0x18000f513  lea     r12, [rsi+rax*2]
0x18000f517  mov     rax, rsi
0x18000f51a  mov     qword ptr [rsp+78h+var_40], r12
0x18000f51f  lea     r15, [rax+4]
0x18000f523  mov     edx, 2Ch ; ','; Ch
0x18000f528  mov     rcx, r15; Str
0x18000f52b  call    cs:__imp_wcschr
0x18000f531  mov     r14, rax
0x18000f534  test    rax, rax
0x18000f537  jz      loc_18000F5DB
0x18000f53d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f541  mov     [rax], r13w
0x18000f545  mov     rax, r8
0x18000f548  inc     rax
0x18000f54b  cmp     [r15+rax*2], r13w
0x18000f550  jnz     short loc_18000F548
0x18000f552  lea     r13d, [rax+rbp]
0x18000f556  mov     eax, 2
0x18000f55b  lea     ebp, [r13+1]
0x18000f55f  mov     ecx, ebp
0x18000f561  mul     rcx
0x18000f564  cmovb   rax, r8
0x18000f568  mov     rcx, rax; unsigned __int64
0x18000f56b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f570  mov     r12, rax
0x18000f573  test    rax, rax
0x18000f576  jz      loc_18000F61B
0x18000f57c  add     r14, 2
0x18000f580  test    rdi, rdi
0x18000f583  jz      short loc_18000F5A0
0x18000f585  mov     r8d, dword ptr [rsp+78h+Block]
0x18000f58a  mov     rdx, rdi; Src
0x18000f58d  add     r8, r8; Size
0x18000f590  mov     rcx, rax; void *
0x18000f593  call    memcpy_0
0x18000f598  mov     rcx, rdi; Block
0x18000f59b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f5a0  mov     ecx, dword ptr [rsp+78h+Block]
0x18000f5a4  mov     edx, ebp
0x18000f5a6  sub     edx, ecx
0x18000f5a8  mov     r8, r15; Source
0x18000f5ab  inc     edx; SizeInWords
0x18000f5ad  lea     eax, [rcx-1]
0x18000f5b0  lea     rcx, [r12+rax*2]; Destination
0x18000f5b4  call    cs:__imp_wcscpy_s
0x18000f5ba  mov     ecx, r13d
0x18000f5bd  lea     eax, [rbp-2]
0x18000f5c0  xor     r13d, r13d
0x18000f5c3  mov     dword ptr [rsp+78h+Block], ebp
0x18000f5c7  mov     rdi, r12
0x18000f5ca  mov     [r12+rax*2], r13w
0x18000f5cf  mov     [r12+rcx*2], r13w
0x18000f5d4  mov     r12, qword ptr [rsp+78h+var_40]
0x18000f5d9  jmp     short loc_18000F5DE
0x18000f5db  mov     r14, r15
0x18000f5de  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f5e2  inc     rax
0x18000f5e5  cmp     [r14+rax*2], r13w
0x18000f5ea  jnz     short loc_18000F5E2
0x18000f5ec  mov     eax, eax
0x18000f5ee  inc     rax
0x18000f5f1  lea     rax, [r14+rax*2]
0x18000f5f5  cmp     rax, r12
0x18000f5f8  ja      short loc_18000F604
0x18000f5fa  cmp     [rax], r13w
0x18000f5fe  jnz     loc_18000F51F
0x18000f604  test    rdi, rdi
0x18000f607  jnz     short loc_18000F631
0x18000f609  mov     ecx, 4; unsigned __int64
0x18000f60e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f613  mov     rdi, rax
0x18000f616  test    rax, rax
0x18000f619  jnz     short loc_18000F622
0x18000f61b  mov     ebx, 8007000Eh
0x18000f620  jmp     short loc_18000F646
0x18000f622  mov     eax, r13d
0x18000f625  mov     ebp, 2
0x18000f62a  mov     [rdi], ax
0x18000f62d  mov     [rdi+2], ax
0x18000f631  mov     rax, [rsp+78h+arg_10]
0x18000f639  mov     [rax], rdi
0x18000f63c  mov     rax, [rsp+78h+arg_18]
0x18000f644  mov     [rax], ebp
0x18000f646  test    rsi, rsi
0x18000f649  jz      short loc_18000F653
0x18000f64b  mov     rcx, rsi; Block
0x18000f64e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f653  mov     eax, ebx
0x18000f655  mov     rbx, [rsp+78h+arg_0]
0x18000f65d  add     rsp, 40h
0x18000f661  pop     r15
0x18000f663  pop     r14
0x18000f665  pop     r13
0x18000f667  pop     r12
0x18000f669  pop     rdi
0x18000f66a  pop     rsi
0x18000f66b  pop     rbp
0x18000f66c  retn
```
