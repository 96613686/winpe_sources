# NameTbl::CreateVval(SYM *,VVAL * *,long *)

- ea: `0x180015db0`
- end: `0x180016072`
- name: `?CreateVval@NameTbl@@IEAAJPEAUSYM@@PEAPEAUVVAL@@PEAJ@Z`
- size: `706`
- prototype: `int(NameTbl *__hidden this, struct SYM *, struct VVAL **, int *)`
- caller_count: `41`
- callee_count: `7`
- tags: ``

## callers

- `0x180014f30`
- `0x180015d50`
- `0x180016380`
- `0x180016d10`
- `0x180017d00`
- `0x180017ee0`
- `0x180031730`
- `0x1800400f0`
- `0x1800424f0`
- `0x180044b50`
- `0x180044f30`
- `0x180046600`
- `0x180047020`
- `0x180048554`
- `0x18004a220`
- `0x18004a490`
- `0x18004b6c0`
- `0x18004b8a0`
- `0x18004b9c0`
- `0x18004bc30`
- `0x18004bd30`
- `0x18004f000`
- `0x18005d6d0`
- `0x18005fec0`
- `0x18005ff70`
- `0x180060070`
- `0x180060120`
- `0x1800603e0`
- `0x180060490`
- `0x180060540`
- `0x1800605f0`
- `0x180061f10`
- `0x18006225c`
- `0x1800676a0`
- `0x1800695d0`
- `0x180069680`
- `0x180069730`
- `0x180069a30`
- `0x18006e690`
- `0x18006ec40`
- `0x18006eda0`

## callees

- `0x180015db0`
- `0x180016078`
- `0x180030bd0`
- `0x180030dcc`
- `0x180094282`
- `0x18009429a`
- `0x180096010`

## import_xrefs

- `msvcrt!malloc` at `0x180015e01`
- `msvcrt!malloc` at `0x180015f73`
- `msvcrt!malloc` at `0x180016038`
- `msvcrt!malloc` at `0x180015e01`
- `msvcrt!malloc` at `0x180015f73`
- `msvcrt!malloc` at `0x180016038`

## pseudocode

```c
__int64 __fastcall NameTbl::CreateVval(NameTbl *this, struct SYM *a2, struct VVAL **a3, int *a4)
{
  int *v4; // r12
  __int64 v7; // rbx
  size_t v8; // rdi
  void *v9; // rax
  unsigned int v10; // ebp
  NameList::NME **v11; // r14
  NameList::NME **v12; // rsi
  NameList::NME *v13; // rdi
  int v14; // edi
  int v15; // r12d
  int v16; // ebp
  _QWORD *v17; // rax
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 result; // rax
  int v21; // esi
  int v22; // ecx
  int v23; // eax
  int v24; // eax
  _QWORD *v25; // rax
  _QWORD *v26; // rdx

  v4 = a4;
  if ( *((_QWORD *)this + 2)
    || (result = (*(__int64 (__fastcall **)(NameTbl *))(*(_QWORD *)this + 416LL))(this), (int)result >= 0) )
  {
    v7 = *((_QWORD *)this + 2);
    if ( *(_QWORD *)(v7 + 56) )
    {
      if ( *(_DWORD *)(v7 + 12) >= *(_DWORD *)(v7 + 68) )
        NameList::Rehash(*((NameList **)this + 2));
    }
    else
    {
      v8 = 8 * *(_DWORD *)(v7 + 64) + 8;
      v9 = malloc(v8);
      *(_QWORD *)(v7 + 56) = v9;
      if ( !v9 )
        return 2147942414LL;
      memset_0(v9, 0, v8);
    }
    v10 = *((_DWORD *)a2 + 3);
    v11 = (NameList::NME **)(*(_QWORD *)(v7 + 56) + 8LL * (v10 & *(_DWORD *)(v7 + 64)));
    v12 = v11;
    while ( 1 )
    {
      v13 = *v12;
      if ( !*v12 )
        break;
      if ( *((_DWORD *)v13 + 8) == v10 )
      {
        if ( (unsigned int)NameList::NME::FEqualRgch(*v12, a2) )
        {
          if ( v12 != v11 )
          {
            *v12 = (NameList::NME *)*((_QWORD *)v13 + 6);
            *((_QWORD *)v13 + 6) = *v11;
            *v11 = v13;
          }
          *(_WORD *)v13 = 0;
          *((_DWORD *)v13 + 6) = 0;
LABEL_15:
          *a3 = v13;
          if ( v4 )
            *v4 = *((_DWORD *)v13 + 14);
          ++*(_DWORD *)(v7 + 8);
          GcContext::RecordVValAlloc(*((GcContext **)this + 9));
          return 0;
        }
        v12 = (NameList::NME **)((char *)v13 + 48);
        v11 = (NameList::NME **)((char *)v13 + 48);
      }
      else
      {
        v12 = (NameList::NME **)((char *)v13 + 48);
      }
    }
    v14 = 2 * *((_DWORD *)a2 + 2) + 66;
    if ( v14 <= 0 )
      return 2147942414LL;
    v15 = *(_DWORD *)(v7 + 28);
    v16 = *(_DWORD *)(v7 + 24);
    if ( v14 <= v15 - v16 )
      goto LABEL_9;
    v21 = *(_DWORD *)(v7 + 36);
    if ( v14 >= v21 )
    {
      if ( 2 * *((_DWORD *)a2 + 2) + 74 <= 2 * *((_DWORD *)a2 + 2) + 66 )
        return 2147942414LL;
      v17 = malloc(v14 + 8LL);
      if ( !v17 )
        return 2147942414LL;
      v26 = *(_QWORD **)(v7 + 16);
      if ( v16 >= v15 )
      {
        *v17 = v26;
        *(_QWORD *)(v7 + 16) = v17;
      }
      else
      {
        *v17 = *v26;
        *v26 = v17;
      }
      goto LABEL_10;
    }
    v22 = *(_DWORD *)(v7 + 32);
    v23 = 2 * *((_DWORD *)a2 + 2) + 66;
    if ( v15 > v14 )
      v23 = *(_DWORD *)(v7 + 28);
    v24 = 2 * v23;
    if ( v22 <= v24 )
      v22 = v24;
    if ( v22 <= v21 )
    {
      if ( v14 > v22 )
        return 2147942414LL;
      v21 = v22;
    }
    if ( v21 + 8 > v21 && v21 + 8 >= v14 )
    {
      v25 = malloc(v21 + 8LL);
      if ( v25 )
      {
        v16 = 0;
        *v25 = *(_QWORD *)(v7 + 16);
        *(_QWORD *)(v7 + 16) = v25;
        *(_DWORD *)(v7 + 28) = v21;
LABEL_9:
        *(_DWORD *)(v7 + 24) = v16 + ((v14 + 7) & 0xFFFFFFF8);
        v17 = (_QWORD *)(*(_QWORD *)(v7 + 16) + v16);
LABEL_10:
        v13 = (NameList::NME *)(v17 + 1);
        if ( v17 == (_QWORD *)-8LL )
          return 2147942414LL;
        v18 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 48LL))(v7, v17 + 1);
        *((_DWORD *)v13 + 14) = v18;
        if ( !v18 )
          return 2147942414LL;
        *(_WORD *)v13 = 0;
        *((_DWORD *)v13 + 6) = 0;
        *((_DWORD *)v13 + 8) = *((_DWORD *)a2 + 3);
        *((_DWORD *)v13 + 9) = 2 * *((_DWORD *)a2 + 2);
        memcpy_0((char *)v13 + 64, *(const void **)a2, 2 * *((_DWORD *)a2 + 2) + 2LL);
        v19 = (_QWORD *)((char *)v13 + 40);
        *((_QWORD *)v13 + 6) = *v11;
        *v11 = v13;
        ++*(_DWORD *)(v7 + 12);
        if ( *(_QWORD *)(v7 + 40) )
          **(_QWORD **)(v7 + 48) = v13;
        else
          *(_QWORD *)(v7 + 40) = v13;
        *(_QWORD *)(v7 + 48) = v19;
        *v19 = 0;
        v4 = a4;
        goto LABEL_15;
      }
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180015db0  mov     [rsp+arg_0], rbx
0x180015db5  mov     [rsp+arg_18], r9
0x180015dba  mov     [rsp+arg_10], r8
0x180015dbf  push    rbp
0x180015dc0  push    rsi
0x180015dc1  push    rdi
0x180015dc2  push    r12
0x180015dc4  push    r13
0x180015dc6  push    r14
0x180015dc8  push    r15
0x180015dca  sub     rsp, 20h
0x180015dce  cmp     qword ptr [rcx+10h], 0
0x180015dd3  mov     r12, r9
0x180015dd6  mov     r13, rdx
0x180015dd9  mov     r15, rcx
0x180015ddc  jz      loc_180015FAC
0x180015de2  mov     rbx, [r15+10h]
0x180015de6  cmp     qword ptr [rbx+38h], 0
0x180015deb  jnz     loc_180015F93
0x180015df1  mov     eax, [rbx+40h]
0x180015df4  lea     eax, ds:8[rax*8]
0x180015dfb  movsxd  rdi, eax
0x180015dfe  mov     rcx, rdi; Size
0x180015e01  call    cs:__imp_malloc
0x180015e07  mov     [rbx+38h], rax
0x180015e0b  test    rax, rax
0x180015e0e  jz      loc_180015FC8
0x180015e14  mov     r8, rdi; Size
0x180015e17  xor     edx, edx; Val
0x180015e19  mov     rcx, rax; void *
0x180015e1c  call    memset_0
0x180015e21  mov     ebp, [r13+0Ch]
0x180015e25  mov     ecx, [rbx+40h]
0x180015e28  mov     rax, [rbx+38h]
0x180015e2c  and     rcx, rbp
0x180015e2f  lea     r14, [rax+rcx*8]
0x180015e33  mov     rsi, r14
0x180015e36  mov     rdi, [rsi]
0x180015e39  test    rdi, rdi
0x180015e3c  jnz     loc_180015FDE
0x180015e42  mov     eax, [r13+8]
0x180015e46  lea     edi, ds:42h[rax*2]
0x180015e4d  test    edi, edi
0x180015e4f  jle     loc_180015FC8
0x180015e55  mov     r12d, [rbx+1Ch]
0x180015e59  mov     eax, r12d
0x180015e5c  mov     ebp, [rbx+18h]
0x180015e5f  sub     eax, ebp
0x180015e61  cmp     edi, eax
0x180015e63  jg      loc_180015F39
0x180015e69  lea     eax, [rdi+7]
0x180015e6c  and     eax, 0FFFFFFF8h
0x180015e6f  add     eax, ebp
0x180015e71  mov     [rbx+18h], eax
0x180015e74  movsxd  rax, ebp
0x180015e77  add     rax, [rbx+10h]
0x180015e7b  lea     rdi, [rax+8]
0x180015e7f  test    rdi, rdi
0x180015e82  jz      loc_180015FC8
0x180015e88  mov     rax, [rbx]
0x180015e8b  mov     rdx, rdi
0x180015e8e  mov     rcx, rbx
0x180015e91  mov     rax, [rax+30h]
0x180015e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e9a  mov     [rdi+38h], eax
0x180015e9d  test    eax, eax
0x180015e9f  jz      loc_180015FC8
0x180015ea5  xor     eax, eax
0x180015ea7  lea     rcx, [rdi+40h]; void *
0x180015eab  mov     [rdi], ax
0x180015eae  mov     [rdi+18h], eax
0x180015eb1  mov     eax, [r13+0Ch]
0x180015eb5  mov     [rdi+20h], eax
0x180015eb8  mov     eax, [r13+8]
0x180015ebc  add     eax, eax
0x180015ebe  mov     [rdi+24h], eax
0x180015ec1  mov     eax, [r13+8]
0x180015ec5  mov     rdx, [r13+0]; Src
0x180015ec9  add     eax, eax
0x180015ecb  movsxd  r8, eax
0x180015ece  add     r8, 2; Size
0x180015ed2  call    memcpy_0
0x180015ed7  mov     rax, [r14]
0x180015eda  lea     rcx, [rdi+28h]
0x180015ede  mov     [rdi+30h], rax
0x180015ee2  mov     [r14], rdi
0x180015ee5  inc     dword ptr [rbx+0Ch]
0x180015ee8  cmp     qword ptr [rbx+28h], 0
0x180015eed  jnz     loc_180015FD2
0x180015ef3  mov     [rbx+28h], rdi
0x180015ef7  mov     [rbx+30h], rcx
0x180015efb  xor     eax, eax
0x180015efd  mov     [rcx], rax
0x180015f00  mov     r12, [rsp+58h+arg_18]
0x180015f05  mov     rax, [rsp+58h+arg_10]
0x180015f0a  mov     [rax], rdi
0x180015f0d  test    r12, r12
0x180015f10  jnz     loc_18001601E
0x180015f16  inc     dword ptr [rbx+8]
0x180015f19  mov     rcx, [r15+48h]; this
0x180015f1d  call    ?RecordVValAlloc@GcContext@@QEAAXXZ; GcContext::RecordVValAlloc(void)
0x180015f22  xor     eax, eax
0x180015f24  mov     rbx, [rsp+58h+arg_0]
0x180015f29  add     rsp, 20h
0x180015f2d  pop     r15
0x180015f2f  pop     r14
0x180015f31  pop     r13
0x180015f33  pop     r12
0x180015f35  pop     rdi
0x180015f36  pop     rsi
0x180015f37  pop     rbp
0x180015f38  retn
0x180015f39  mov     esi, [rbx+24h]
0x180015f3c  cmp     edi, esi
0x180015f3e  jge     loc_18001602A
0x180015f44  mov     ecx, [rbx+20h]
0x180015f47  cmp     r12d, edi
0x180015f4a  mov     eax, edi
0x180015f4c  cmovg   eax, r12d
0x180015f50  add     eax, eax
0x180015f52  cmp     ecx, eax
0x180015f54  cmovle  ecx, eax
0x180015f57  cmp     ecx, esi
0x180015f59  jg      short loc_180015F61
0x180015f5b  cmp     edi, ecx
0x180015f5d  jg      short loc_180015FC8
0x180015f5f  mov     esi, ecx
0x180015f61  lea     eax, [rsi+8]
0x180015f64  cmp     eax, esi
0x180015f66  jl      short loc_180015FC8
0x180015f68  cmp     eax, edi
0x180015f6a  jl      short loc_180015FC8
0x180015f6c  movsxd  rcx, esi
0x180015f6f  add     rcx, 8; Size
0x180015f73  call    cs:__imp_malloc
0x180015f79  test    rax, rax
0x180015f7c  jz      short loc_180015FC8
0x180015f7e  mov     rcx, [rbx+10h]
0x180015f82  xor     ebp, ebp
0x180015f84  mov     [rax], rcx
0x180015f87  mov     [rbx+10h], rax
0x180015f8b  mov     [rbx+1Ch], esi
0x180015f8e  jmp     loc_180015E69
0x180015f93  mov     eax, [rbx+44h]
0x180015f96  cmp     [rbx+0Ch], eax
0x180015f99  jl      loc_180015E21
0x180015f9f  mov     rcx, rbx; this
0x180015fa2  call    ?Rehash@NameList@@AEAAXXZ; NameList::Rehash(void)
0x180015fa7  jmp     loc_180015E21
0x180015fac  mov     rax, [rcx]
0x180015faf  mov     rax, [rax+1A0h]
0x180015fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fbb  test    eax, eax
0x180015fbd  jns     loc_180015DE2
0x180015fc3  jmp     loc_180015F24
0x180015fc8  mov     eax, 8007000Eh
0x180015fcd  jmp     loc_180015F24
0x180015fd2  mov     rax, [rbx+30h]
0x180015fd6  mov     [rax], rdi
0x180015fd9  jmp     loc_180015EF7
0x180015fde  cmp     [rdi+20h], ebp
0x180015fe1  jz      short loc_180015FEC
0x180015fe3  lea     rsi, [rdi+30h]
0x180015fe7  jmp     loc_180015E36
0x180015fec  mov     rdx, r13; struct SYM *
0x180015fef  mov     rcx, rdi; this
0x180015ff2  call    ?FEqualRgch@NME@NameList@@QEAAHPEAUSYM@@@Z; NameList::NME::FEqualRgch(SYM *)
0x180015ff7  test    eax, eax
0x180015ff9  jz      short loc_180016066
0x180015ffb  cmp     rsi, r14
0x180015ffe  jz      short loc_180016011
0x180016000  mov     rax, [rdi+30h]
0x180016004  mov     [rsi], rax
0x180016007  mov     rax, [r14]
0x18001600a  mov     [rdi+30h], rax
0x18001600e  mov     [r14], rdi
0x180016011  xor     eax, eax
0x180016013  mov     [rdi], ax
0x180016016  mov     [rdi+18h], eax
0x180016019  jmp     loc_180015F05
0x18001601e  mov     eax, [rdi+38h]
0x180016021  mov     [r12], eax
0x180016025  jmp     loc_180015F16
0x18001602a  lea     eax, [rdi+8]
0x18001602d  cmp     eax, edi
0x18001602f  jl      short loc_180015FC8
0x180016031  movsxd  rcx, edi
0x180016034  add     rcx, 8; Size
0x180016038  call    cs:__imp_malloc
0x18001603e  test    rax, rax
0x180016041  jz      short loc_180015FC8
0x180016043  mov     rdx, [rbx+10h]
0x180016047  cmp     ebp, r12d
0x18001604a  jge     short loc_18001605A
0x18001604c  mov     rcx, [rdx]
0x18001604f  mov     [rax], rcx
0x180016052  mov     [rdx], rax
0x180016055  jmp     loc_180015E7B
0x18001605a  mov     [rax], rdx
0x18001605d  mov     [rbx+10h], rax
0x180016061  jmp     loc_180015E7B
0x180016066  lea     rsi, [rdi+30h]
0x18001606a  mov     r14, rsi
0x18001606d  jmp     loc_180015E36
```
