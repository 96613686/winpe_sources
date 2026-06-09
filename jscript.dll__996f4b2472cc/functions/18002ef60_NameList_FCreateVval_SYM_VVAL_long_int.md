# NameList::FCreateVval(SYM *,VVAL * *,long *,int)

- ea: `0x18002ef60`
- end: `0x18002f21d`
- name: `?FCreateVval@NameList@@QEAAHPEAUSYM@@PEAPEAUVVAL@@PEAJH@Z`
- size: `701`
- prototype: `int(NameList *__hidden this, struct SYM *, struct VVAL **, int *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e114`
- `0x18004fe50`
- `0x180078e20`

## callees

- `0x18002ef60`
- `0x18002f230`
- `0x18002f434`
- `0x180096692`
- `0x1800966aa`
- `0x180098010`

## import_xrefs

- `msvcrt!malloc` at `0x18002ef9f`
- `msvcrt!malloc` at `0x18002f114`
- `msvcrt!malloc` at `0x18002f1ce`
- `msvcrt!malloc` at `0x18002ef9f`
- `msvcrt!malloc` at `0x18002f114`
- `msvcrt!malloc` at `0x18002f1ce`

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
0x18002ef60  mov     [rsp+arg_0], rbx
0x18002ef65  mov     [rsp+arg_18], r9
0x18002ef6a  mov     [rsp+arg_10], r8
0x18002ef6f  push    rbp
0x18002ef70  push    rsi
0x18002ef71  push    rdi
0x18002ef72  push    r12
0x18002ef74  push    r13
0x18002ef76  push    r14
0x18002ef78  push    r15
0x18002ef7a  sub     rsp, 20h
0x18002ef7e  cmp     qword ptr [rcx+38h], 0
0x18002ef83  mov     r14, rdx
0x18002ef86  mov     rbx, rcx
0x18002ef89  jnz     loc_18002F13C
0x18002ef8f  mov     eax, [rcx+40h]
0x18002ef92  lea     eax, ds:8[rax*8]
0x18002ef99  movsxd  rdi, eax
0x18002ef9c  mov     rcx, rdi; Size
0x18002ef9f  call    cs:__imp_malloc
0x18002efa6  nop     dword ptr [rax+rax+00h]
0x18002efab  mov     [rbx+38h], rax
0x18002efaf  test    rax, rax
0x18002efb2  jz      loc_18002F152
0x18002efb8  mov     r8, rdi; Size
0x18002efbb  xor     edx, edx; Val
0x18002efbd  mov     rcx, rax; void *
0x18002efc0  call    memset_0
0x18002efc5  mov     ebp, [r14+0Ch]
0x18002efc9  mov     ecx, [rbx+40h]
0x18002efcc  mov     rax, [rbx+38h]
0x18002efd0  and     rcx, rbp
0x18002efd3  lea     r15, [rax+rcx*8]
0x18002efd7  mov     rsi, r15
0x18002efda  mov     rdi, [rsi]
0x18002efdd  test    rdi, rdi
0x18002efe0  jnz     loc_18002F173
0x18002efe6  mov     eax, [r14+8]
0x18002efea  lea     edi, ds:42h[rax*2]
0x18002eff1  test    edi, edi
0x18002eff3  jle     loc_18002F152
0x18002eff9  mov     ebp, [rbx+1Ch]
0x18002effc  xor     r12d, r12d
0x18002efff  mov     esi, [rbx+18h]
0x18002f002  mov     eax, ebp
0x18002f004  sub     eax, esi
0x18002f006  cmp     edi, eax
0x18002f008  jg      loc_18002F0D8
0x18002f00e  lea     eax, [rdi+7]
0x18002f011  and     eax, 0FFFFFFF8h
0x18002f014  add     eax, esi
0x18002f016  mov     [rbx+18h], eax
0x18002f019  movsxd  rax, esi
0x18002f01c  add     rax, [rbx+10h]
0x18002f020  lea     rdi, [rax+8]
0x18002f024  test    rdi, rdi
0x18002f027  jz      loc_18002F152
0x18002f02d  mov     rax, [rbx]
0x18002f030  mov     rdx, rdi
0x18002f033  mov     rcx, rbx
0x18002f036  mov     rax, [rax+30h]
0x18002f03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f03f  mov     [rdi+38h], eax
0x18002f042  test    eax, eax
0x18002f044  jz      loc_18002F152
0x18002f04a  mov     [rdi], r12w
0x18002f04e  lea     rcx, [rdi+40h]; void *
0x18002f052  mov     [rdi+18h], r12d
0x18002f056  mov     eax, [r14+0Ch]
0x18002f05a  mov     [rdi+20h], eax
0x18002f05d  mov     eax, [r14+8]
0x18002f061  add     eax, eax
0x18002f063  mov     [rdi+24h], eax
0x18002f066  mov     eax, [r14+8]
0x18002f06a  mov     rdx, [r14]; Src
0x18002f06d  add     eax, eax
0x18002f06f  movsxd  r8, eax
0x18002f072  add     r8, 2; Size
0x18002f076  call    memcpy_0
0x18002f07b  mov     rax, [r15]
0x18002f07e  lea     rcx, [rdi+28h]
0x18002f082  mov     [rdi+30h], rax
0x18002f086  mov     [r15], rdi
0x18002f089  inc     dword ptr [rbx+0Ch]
0x18002f08c  mov     rax, [rbx+28h]
0x18002f090  test    rax, rax
0x18002f093  jnz     loc_18002F159
0x18002f099  mov     [rbx+28h], rdi
0x18002f09d  mov     [rbx+30h], rcx
0x18002f0a1  mov     [rcx], r12
0x18002f0a4  mov     rax, [rsp+58h+arg_10]
0x18002f0a9  mov     rcx, [rsp+58h+arg_18]
0x18002f0ae  mov     [rax], rdi
0x18002f0b1  test    rcx, rcx
0x18002f0b4  jnz     loc_18002F1B6
0x18002f0ba  inc     dword ptr [rbx+8]
0x18002f0bd  mov     eax, 1
0x18002f0c2  mov     rbx, [rsp+58h+arg_0]
0x18002f0c7  add     rsp, 20h
0x18002f0cb  pop     r15
0x18002f0cd  pop     r14
0x18002f0cf  pop     r13
0x18002f0d1  pop     r12
0x18002f0d3  pop     rdi
0x18002f0d4  pop     rsi
0x18002f0d5  pop     rbp
0x18002f0d6  retn
0x18002f0d8  mov     r13d, [rbx+24h]
0x18002f0dc  cmp     edi, r13d
0x18002f0df  jge     loc_18002F1C0
0x18002f0e5  mov     eax, [rbx+20h]
0x18002f0e8  cmp     ebp, edi
0x18002f0ea  cmovle  ebp, edi
0x18002f0ed  add     ebp, ebp
0x18002f0ef  cmp     eax, ebp
0x18002f0f1  cmovle  eax, ebp
0x18002f0f4  cmp     eax, r13d
0x18002f0f7  cmovle  r13d, eax
0x18002f0fb  cmp     edi, r13d
0x18002f0fe  jg      short loc_18002F152
0x18002f100  lea     eax, [r13+8]
0x18002f104  cmp     eax, r13d
0x18002f107  jl      short loc_18002F152
0x18002f109  cmp     eax, edi
0x18002f10b  jl      short loc_18002F152
0x18002f10d  movsxd  rcx, r13d
0x18002f110  add     rcx, 8; Size
0x18002f114  call    cs:__imp_malloc
0x18002f11b  nop     dword ptr [rax+rax+00h]
0x18002f120  test    rax, rax
0x18002f123  jz      short loc_18002F152
0x18002f125  mov     rcx, [rbx+10h]; this
0x18002f129  mov     esi, r12d
0x18002f12c  mov     [rax], rcx
0x18002f12f  mov     [rbx+10h], rax
0x18002f133  mov     [rbx+1Ch], r13d
0x18002f137  jmp     loc_18002F00E
0x18002f13c  mov     eax, [rcx+44h]
0x18002f13f  cmp     [rcx+0Ch], eax
0x18002f142  jl      loc_18002EFC5
0x18002f148  call    ?Rehash@NameList@@AEAAXXZ; NameList::Rehash(void)
0x18002f14d  jmp     loc_18002EFC5
0x18002f152  xor     eax, eax
0x18002f154  jmp     loc_18002F0C2
0x18002f159  cmp     [rsp+58h+arg_20], r12d
0x18002f161  jnz     loc_18002F211
0x18002f167  mov     rax, [rbx+30h]
0x18002f16b  mov     [rax], rdi
0x18002f16e  jmp     loc_18002F09D
0x18002f173  cmp     [rdi+20h], ebp
0x18002f176  jz      short loc_18002F181
0x18002f178  lea     rsi, [rdi+30h]
0x18002f17c  jmp     loc_18002EFDA
0x18002f181  mov     rdx, r14; struct SYM *
0x18002f184  mov     rcx, rdi; this
0x18002f187  call    ?FEqualRgch@NME@NameList@@QEAAHPEAUSYM@@@Z; NameList::NME::FEqualRgch(SYM *)
0x18002f18c  test    eax, eax
0x18002f18e  jz      short loc_18002F205
0x18002f190  cmp     rsi, r15
0x18002f193  jz      short loc_18002F1A6
0x18002f195  mov     rax, [rdi+30h]
0x18002f199  mov     [rsi], rax
0x18002f19c  mov     rax, [r15]
0x18002f19f  mov     [rdi+30h], rax
0x18002f1a3  mov     [r15], rdi
0x18002f1a6  xor     r12d, r12d
0x18002f1a9  mov     [rdi], r12w
0x18002f1ad  mov     [rdi+18h], r12d
0x18002f1b1  jmp     loc_18002F0A4
0x18002f1b6  mov     eax, [rdi+38h]
0x18002f1b9  mov     [rcx], eax
0x18002f1bb  jmp     loc_18002F0BA
0x18002f1c0  lea     eax, [rdi+8]
0x18002f1c3  cmp     eax, edi
0x18002f1c5  jl      short loc_18002F152
0x18002f1c7  movsxd  rcx, edi
0x18002f1ca  add     rcx, 8; Size
0x18002f1ce  call    cs:__imp_malloc
0x18002f1d5  nop     dword ptr [rax+rax+00h]
0x18002f1da  test    rax, rax
0x18002f1dd  jz      loc_18002F152
0x18002f1e3  mov     rdx, [rbx+10h]
0x18002f1e7  cmp     esi, ebp
0x18002f1e9  jge     short loc_18002F1F9
0x18002f1eb  mov     rcx, [rdx]
0x18002f1ee  mov     [rax], rcx
0x18002f1f1  mov     [rdx], rax
0x18002f1f4  jmp     loc_18002F020
0x18002f1f9  mov     [rax], rdx
0x18002f1fc  mov     [rbx+10h], rax
0x18002f200  jmp     loc_18002F020
0x18002f205  lea     rsi, [rdi+30h]
0x18002f209  mov     r15, rsi
0x18002f20c  jmp     loc_18002EFDA
0x18002f211  mov     [rcx], rax
0x18002f214  mov     [rbx+28h], rdi
0x18002f218  jmp     loc_18002F0A4
```
