# NameList::FCreateVval(SYM *,VVAL * *,long *,int)

- ea: `0x180030920`
- end: `0x180030bca`
- name: `?FCreateVval@NameList@@QEAAHPEAUSYM@@PEAPEAUVVAL@@PEAJH@Z`
- size: `682`
- prototype: `int(NameList *__hidden this, struct SYM *, struct VVAL **, int *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800210b0`
- `0x18004ee0c`
- `0x180077820`

## callees

- `0x180030920`
- `0x180030bd0`
- `0x180030dcc`
- `0x180094282`
- `0x18009429a`
- `0x180096010`

## import_xrefs

- `msvcrt!malloc` at `0x18003095f`
- `msvcrt!malloc` at `0x180030acd`
- `msvcrt!malloc` at `0x180030b81`
- `msvcrt!malloc` at `0x18003095f`
- `msvcrt!malloc` at `0x180030acd`
- `msvcrt!malloc` at `0x180030b81`

## pseudocode

```c
__int64 __fastcall NameList::FCreateVval(NameList *this, struct SYM *a2, struct VVAL **a3, int *a4, int a5)
{
  size_t v7; // rdi
  void *v8; // rax
  unsigned int v9; // ebp
  NameList::NME **v10; // r15
  NameList::NME **v11; // rsi
  NameList::NME *v12; // rdi
  int v13; // edi
  int v14; // ebp
  int v15; // esi
  _QWORD *v16; // rax
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rax
  int v21; // r13d
  int v22; // eax
  int v23; // ebp
  _QWORD *v24; // rax
  _QWORD *v25; // rdx

  if ( *((_QWORD *)this + 7) )
  {
    if ( *((_DWORD *)this + 3) >= *((_DWORD *)this + 17) )
      NameList::Rehash(this);
  }
  else
  {
    v7 = 8 * *((_DWORD *)this + 16) + 8;
    v8 = malloc(v7);
    *((_QWORD *)this + 7) = v8;
    if ( !v8 )
      return 0;
    memset_0(v8, 0, v7);
  }
  v9 = *((_DWORD *)a2 + 3);
  v10 = (NameList::NME **)(*((_QWORD *)this + 7) + 8LL * (v9 & *((_DWORD *)this + 16)));
  v11 = v10;
  while ( 1 )
  {
    v12 = *v11;
    if ( !*v11 )
      break;
    if ( *((_DWORD *)v12 + 8) == v9 )
    {
      if ( (unsigned int)NameList::NME::FEqualRgch(*v11, a2) )
      {
        if ( v11 != v10 )
        {
          *v11 = (NameList::NME *)*((_QWORD *)v12 + 6);
          *((_QWORD *)v12 + 6) = *v10;
          *v10 = v12;
        }
        *(_WORD *)v12 = 0;
        *((_DWORD *)v12 + 6) = 0;
        goto LABEL_14;
      }
      v11 = (NameList::NME **)((char *)v12 + 48);
      v10 = (NameList::NME **)((char *)v12 + 48);
    }
    else
    {
      v11 = (NameList::NME **)((char *)v12 + 48);
    }
  }
  v13 = 2 * *((_DWORD *)a2 + 2) + 66;
  if ( v13 <= 0 )
    return 0;
  v14 = *((_DWORD *)this + 7);
  v15 = *((_DWORD *)this + 6);
  if ( v13 <= v14 - v15 )
    goto LABEL_8;
  v21 = *((_DWORD *)this + 9);
  if ( v13 >= v21 )
  {
    if ( 2 * *((_DWORD *)a2 + 2) + 74 <= 2 * *((_DWORD *)a2 + 2) + 66 )
      return 0;
    v16 = malloc(v13 + 8LL);
    if ( !v16 )
      return 0;
    v25 = (_QWORD *)*((_QWORD *)this + 2);
    if ( v15 >= v14 )
    {
      *v16 = v25;
      *((_QWORD *)this + 2) = v16;
    }
    else
    {
      *v16 = *v25;
      *v25 = v16;
    }
LABEL_9:
    v12 = (NameList::NME *)(v16 + 1);
    if ( v16 == (_QWORD *)-8LL )
      return 0;
    v17 = (*(__int64 (__fastcall **)(NameList *, _QWORD *))(*(_QWORD *)this + 48LL))(this, v16 + 1);
    *((_DWORD *)v12 + 14) = v17;
    if ( !v17 )
      return 0;
    *(_WORD *)v12 = 0;
    *((_DWORD *)v12 + 6) = 0;
    *((_DWORD *)v12 + 8) = *((_DWORD *)a2 + 3);
    *((_DWORD *)v12 + 9) = 2 * *((_DWORD *)a2 + 2);
    memcpy_0((char *)v12 + 64, *(const void **)a2, 2 * *((_DWORD *)a2 + 2) + 2LL);
    v18 = (_QWORD *)((char *)v12 + 40);
    *((_QWORD *)v12 + 6) = *v10;
    *v10 = v12;
    ++*((_DWORD *)this + 3);
    v19 = *((_QWORD *)this + 5);
    if ( v19 )
    {
      if ( a5 )
      {
        *v18 = v19;
        *((_QWORD *)this + 5) = v12;
        goto LABEL_14;
      }
      **((_QWORD **)this + 6) = v12;
    }
    else
    {
      *((_QWORD *)this + 5) = v12;
    }
    *((_QWORD *)this + 6) = v18;
    *v18 = 0;
LABEL_14:
    *a3 = v12;
    if ( a4 )
      *a4 = *((_DWORD *)v12 + 14);
    ++*((_DWORD *)this + 2);
    return 1;
  }
  v22 = *((_DWORD *)this + 8);
  if ( v14 <= v13 )
    v14 = 2 * *((_DWORD *)a2 + 2) + 66;
  v23 = 2 * v14;
  if ( v22 <= v23 )
    v22 = v23;
  if ( v22 <= v21 )
    v21 = v22;
  if ( v13 <= v21 && v21 + 8 > v21 && v21 + 8 >= v13 )
  {
    v24 = malloc(v21 + 8LL);
    if ( v24 )
    {
      v15 = 0;
      *v24 = *((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = v24;
      *((_DWORD *)this + 7) = v21;
LABEL_8:
      *((_DWORD *)this + 6) = v15 + ((v13 + 7) & 0xFFFFFFF8);
      v16 = (_QWORD *)(*((_QWORD *)this + 2) + v15);
      goto LABEL_9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180030920  mov     [rsp+arg_0], rbx
0x180030925  mov     [rsp+arg_18], r9
0x18003092a  mov     [rsp+arg_10], r8
0x18003092f  push    rbp
0x180030930  push    rsi
0x180030931  push    rdi
0x180030932  push    r12
0x180030934  push    r13
0x180030936  push    r14
0x180030938  push    r15
0x18003093a  sub     rsp, 20h
0x18003093e  cmp     qword ptr [rcx+38h], 0
0x180030943  mov     r14, rdx
0x180030946  mov     rbx, rcx
0x180030949  jnz     loc_180030AEF
0x18003094f  mov     eax, [rcx+40h]
0x180030952  lea     eax, ds:8[rax*8]
0x180030959  movsxd  rdi, eax
0x18003095c  mov     rcx, rdi; Size
0x18003095f  call    cs:__imp_malloc
0x180030965  mov     [rbx+38h], rax
0x180030969  test    rax, rax
0x18003096c  jz      loc_180030B05
0x180030972  mov     r8, rdi; Size
0x180030975  xor     edx, edx; Val
0x180030977  mov     rcx, rax; void *
0x18003097a  call    memset_0
0x18003097f  mov     ebp, [r14+0Ch]
0x180030983  mov     ecx, [rbx+40h]
0x180030986  mov     rax, [rbx+38h]
0x18003098a  and     rcx, rbp
0x18003098d  lea     r15, [rax+rcx*8]
0x180030991  mov     rsi, r15
0x180030994  mov     rdi, [rsi]
0x180030997  test    rdi, rdi
0x18003099a  jnz     loc_180030B26
0x1800309a0  mov     eax, [r14+8]
0x1800309a4  lea     edi, ds:42h[rax*2]
0x1800309ab  test    edi, edi
0x1800309ad  jle     loc_180030B05
0x1800309b3  mov     ebp, [rbx+1Ch]
0x1800309b6  xor     r12d, r12d
0x1800309b9  mov     esi, [rbx+18h]
0x1800309bc  mov     eax, ebp
0x1800309be  sub     eax, esi
0x1800309c0  cmp     edi, eax
0x1800309c2  jg      loc_180030A91
0x1800309c8  lea     eax, [rdi+7]
0x1800309cb  and     eax, 0FFFFFFF8h
0x1800309ce  add     eax, esi
0x1800309d0  mov     [rbx+18h], eax
0x1800309d3  movsxd  rax, esi
0x1800309d6  add     rax, [rbx+10h]
0x1800309da  lea     rdi, [rax+8]
0x1800309de  test    rdi, rdi
0x1800309e1  jz      loc_180030B05
0x1800309e7  mov     rax, [rbx]
0x1800309ea  mov     rdx, rdi
0x1800309ed  mov     rcx, rbx
0x1800309f0  mov     rax, [rax+30h]
0x1800309f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309f9  mov     [rdi+38h], eax
0x1800309fc  test    eax, eax
0x1800309fe  jz      loc_180030B05
0x180030a04  mov     [rdi], r12w
0x180030a08  lea     rcx, [rdi+40h]; void *
0x180030a0c  mov     [rdi+18h], r12d
0x180030a10  mov     eax, [r14+0Ch]
0x180030a14  mov     [rdi+20h], eax
0x180030a17  mov     eax, [r14+8]
0x180030a1b  add     eax, eax
0x180030a1d  mov     [rdi+24h], eax
0x180030a20  mov     eax, [r14+8]
0x180030a24  mov     rdx, [r14]; Src
0x180030a27  add     eax, eax
0x180030a29  movsxd  r8, eax
0x180030a2c  add     r8, 2; Size
0x180030a30  call    memcpy_0
0x180030a35  mov     rax, [r15]
0x180030a38  lea     rcx, [rdi+28h]
0x180030a3c  mov     [rdi+30h], rax
0x180030a40  mov     [r15], rdi
0x180030a43  inc     dword ptr [rbx+0Ch]
0x180030a46  mov     rax, [rbx+28h]
0x180030a4a  test    rax, rax
0x180030a4d  jnz     loc_180030B0C
0x180030a53  mov     [rbx+28h], rdi
0x180030a57  mov     [rbx+30h], rcx
0x180030a5b  mov     [rcx], r12
0x180030a5e  mov     rax, [rsp+58h+arg_10]
0x180030a63  mov     rcx, [rsp+58h+arg_18]
0x180030a68  mov     [rax], rdi
0x180030a6b  test    rcx, rcx
0x180030a6e  jnz     loc_180030B69
0x180030a74  inc     dword ptr [rbx+8]
0x180030a77  mov     eax, 1
0x180030a7c  mov     rbx, [rsp+58h+arg_0]
0x180030a81  add     rsp, 20h
0x180030a85  pop     r15
0x180030a87  pop     r14
0x180030a89  pop     r13
0x180030a8b  pop     r12
0x180030a8d  pop     rdi
0x180030a8e  pop     rsi
0x180030a8f  pop     rbp
0x180030a90  retn
0x180030a91  mov     r13d, [rbx+24h]
0x180030a95  cmp     edi, r13d
0x180030a98  jge     loc_180030B73
0x180030a9e  mov     eax, [rbx+20h]
0x180030aa1  cmp     ebp, edi
0x180030aa3  cmovle  ebp, edi
0x180030aa6  add     ebp, ebp
0x180030aa8  cmp     eax, ebp
0x180030aaa  cmovle  eax, ebp
0x180030aad  cmp     eax, r13d
0x180030ab0  cmovle  r13d, eax
0x180030ab4  cmp     edi, r13d
0x180030ab7  jg      short loc_180030B05
0x180030ab9  lea     eax, [r13+8]
0x180030abd  cmp     eax, r13d
0x180030ac0  jl      short loc_180030B05
0x180030ac2  cmp     eax, edi
0x180030ac4  jl      short loc_180030B05
0x180030ac6  movsxd  rcx, r13d
0x180030ac9  add     rcx, 8; Size
0x180030acd  call    cs:__imp_malloc
0x180030ad3  test    rax, rax
0x180030ad6  jz      short loc_180030B05
0x180030ad8  mov     rcx, [rbx+10h]; this
0x180030adc  mov     esi, r12d
0x180030adf  mov     [rax], rcx
0x180030ae2  mov     [rbx+10h], rax
0x180030ae6  mov     [rbx+1Ch], r13d
0x180030aea  jmp     loc_1800309C8
0x180030aef  mov     eax, [rcx+44h]
0x180030af2  cmp     [rcx+0Ch], eax
0x180030af5  jl      loc_18003097F
0x180030afb  call    ?Rehash@NameList@@AEAAXXZ; NameList::Rehash(void)
0x180030b00  jmp     loc_18003097F
0x180030b05  xor     eax, eax
0x180030b07  jmp     loc_180030A7C
0x180030b0c  cmp     [rsp+58h+arg_20], r12d
0x180030b14  jnz     loc_180030BBE
0x180030b1a  mov     rax, [rbx+30h]
0x180030b1e  mov     [rax], rdi
0x180030b21  jmp     loc_180030A57
0x180030b26  cmp     [rdi+20h], ebp
0x180030b29  jz      short loc_180030B34
0x180030b2b  lea     rsi, [rdi+30h]
0x180030b2f  jmp     loc_180030994
0x180030b34  mov     rdx, r14; struct SYM *
0x180030b37  mov     rcx, rdi; this
0x180030b3a  call    ?FEqualRgch@NME@NameList@@QEAAHPEAUSYM@@@Z; NameList::NME::FEqualRgch(SYM *)
0x180030b3f  test    eax, eax
0x180030b41  jz      short loc_180030BB2
0x180030b43  cmp     rsi, r15
0x180030b46  jz      short loc_180030B59
0x180030b48  mov     rax, [rdi+30h]
0x180030b4c  mov     [rsi], rax
0x180030b4f  mov     rax, [r15]
0x180030b52  mov     [rdi+30h], rax
0x180030b56  mov     [r15], rdi
0x180030b59  xor     r12d, r12d
0x180030b5c  mov     [rdi], r12w
0x180030b60  mov     [rdi+18h], r12d
0x180030b64  jmp     loc_180030A5E
0x180030b69  mov     eax, [rdi+38h]
0x180030b6c  mov     [rcx], eax
0x180030b6e  jmp     loc_180030A74
0x180030b73  lea     eax, [rdi+8]
0x180030b76  cmp     eax, edi
0x180030b78  jl      short loc_180030B05
0x180030b7a  movsxd  rcx, edi
0x180030b7d  add     rcx, 8; Size
0x180030b81  call    cs:__imp_malloc
0x180030b87  test    rax, rax
0x180030b8a  jz      loc_180030B05
0x180030b90  mov     rdx, [rbx+10h]
0x180030b94  cmp     esi, ebp
0x180030b96  jge     short loc_180030BA6
0x180030b98  mov     rcx, [rdx]
0x180030b9b  mov     [rax], rcx
0x180030b9e  mov     [rdx], rax
0x180030ba1  jmp     loc_1800309DA
0x180030ba6  mov     [rax], rdx
0x180030ba9  mov     [rbx+10h], rax
0x180030bad  jmp     loc_1800309DA
0x180030bb2  lea     rsi, [rdi+30h]
0x180030bb6  mov     r15, rsi
0x180030bb9  jmp     loc_180030994
0x180030bbe  mov     [rcx], rax
0x180030bc1  mov     [rbx+28h], rdi
0x180030bc5  jmp     loc_180030A5E
```
