# NameTbl::CreateProtoRefVval(SYM *,VVAL * *,long *,int)

- ea: `0x180030620`
- end: `0x180030915`
- name: `?CreateProtoRefVval@NameTbl@@MEAAJPEAUSYM@@PEAPEAUVVAL@@PEAJH@Z`
- size: `757`
- prototype: `int(NameTbl *__hidden this, struct SYM *, struct VVAL **, int *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180030550`

## callees

- `0x180030620`
- `0x180030bd0`
- `0x180030dcc`
- `0x180094282`
- `0x18009429a`
- `0x180096010`

## import_xrefs

- `msvcrt!malloc` at `0x180030692`
- `msvcrt!malloc` at `0x180030810`
- `msvcrt!malloc` at `0x1800308c1`
- `msvcrt!malloc` at `0x180030692`
- `msvcrt!malloc` at `0x180030810`
- `msvcrt!malloc` at `0x1800308c1`

## pseudocode

```c
__int64 __fastcall NameTbl::CreateProtoRefVval(NameTbl *this, struct SYM *a2, struct VVAL **a3, int *a4, int a5)
{
  __int64 result; // rax
  __int64 v8; // rbx
  size_t v9; // rdi
  void *v10; // rax
  unsigned int v11; // ebp
  NameList::NME **v12; // r13
  NameList::NME **v13; // rsi
  NameList::NME *v14; // rdi
  int v15; // edi
  int v16; // r15d
  int v17; // ebp
  _QWORD *v18; // rax
  int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rax
  int v22; // esi
  int v23; // ecx
  int v24; // eax
  int v25; // eax
  _QWORD *v26; // rax
  _QWORD *v27; // rdx

  if ( *((_QWORD *)this + 2)
    || (result = (*(__int64 (__fastcall **)(NameTbl *))(*(_QWORD *)this + 416LL))(this), (int)result >= 0) )
  {
    v8 = *((_QWORD *)this + 2);
    if ( *(_QWORD *)(v8 + 56) )
    {
      if ( *(_DWORD *)(v8 + 12) >= *(_DWORD *)(v8 + 68) )
        NameList::Rehash((NameList *)v8);
    }
    else
    {
      v9 = 8 * *(_DWORD *)(v8 + 64) + 8;
      v10 = malloc(v9);
      *(_QWORD *)(v8 + 56) = v10;
      if ( !v10 )
        return 2147942414LL;
      memset_0(v10, 0, v9);
    }
    v11 = *((_DWORD *)a2 + 3);
    v12 = (NameList::NME **)(*(_QWORD *)(v8 + 56) + 8LL * (v11 & *(_DWORD *)(v8 + 64)));
    v13 = v12;
    while ( 1 )
    {
      v14 = *v13;
      if ( !*v13 )
        break;
      if ( *((_DWORD *)v14 + 8) == v11 )
      {
        if ( (unsigned int)NameList::NME::FEqualRgch(*v13, a2) )
        {
          if ( v13 != v12 )
          {
            *v13 = (NameList::NME *)*((_QWORD *)v14 + 6);
            *((_QWORD *)v14 + 6) = *v12;
            *v12 = v14;
          }
          *(_WORD *)v14 = 0;
          *((_DWORD *)v14 + 6) = 0;
          goto LABEL_16;
        }
        v13 = (NameList::NME **)((char *)v14 + 48);
        v12 = (NameList::NME **)((char *)v14 + 48);
      }
      else
      {
        v13 = (NameList::NME **)((char *)v14 + 48);
      }
    }
    v15 = 2 * *((_DWORD *)a2 + 2) + 66;
    if ( v15 <= 0 )
      return 2147942414LL;
    v16 = *(_DWORD *)(v8 + 28);
    v17 = *(_DWORD *)(v8 + 24);
    if ( v15 <= v16 - v17 )
      goto LABEL_10;
    v22 = *(_DWORD *)(v8 + 36);
    if ( v15 >= v22 )
    {
      if ( 2 * *((_DWORD *)a2 + 2) + 74 <= 2 * *((_DWORD *)a2 + 2) + 66 )
        return 2147942414LL;
      v18 = malloc(v15 + 8LL);
      if ( !v18 )
        return 2147942414LL;
      v27 = *(_QWORD **)(v8 + 16);
      if ( v17 >= v16 )
      {
        *v18 = v27;
        *(_QWORD *)(v8 + 16) = v18;
      }
      else
      {
        *v18 = *v27;
        *v27 = v18;
      }
LABEL_11:
      v14 = (NameList::NME *)(v18 + 1);
      if ( v18 == (_QWORD *)-8LL )
        return 2147942414LL;
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 48LL))(v8, v18 + 1);
      *((_DWORD *)v14 + 14) = v19;
      if ( !v19 )
        return 2147942414LL;
      *(_WORD *)v14 = 0;
      *((_DWORD *)v14 + 6) = 0;
      *((_DWORD *)v14 + 8) = *((_DWORD *)a2 + 3);
      *((_DWORD *)v14 + 9) = 2 * *((_DWORD *)a2 + 2);
      memcpy_0((char *)v14 + 64, *(const void **)a2, 2 * *((_DWORD *)a2 + 2) + 2LL);
      v20 = (_QWORD *)((char *)v14 + 40);
      *((_QWORD *)v14 + 6) = *v12;
      *v12 = v14;
      ++*(_DWORD *)(v8 + 12);
      v21 = *(_QWORD *)(v8 + 40);
      if ( v21 )
      {
        if ( a5 )
        {
          *v20 = v21;
          *(_QWORD *)(v8 + 40) = v14;
          goto LABEL_16;
        }
        **(_QWORD **)(v8 + 48) = v14;
      }
      else
      {
        *(_QWORD *)(v8 + 40) = v14;
      }
      *(_QWORD *)(v8 + 48) = v20;
      *v20 = 0;
LABEL_16:
      *a3 = v14;
      if ( a4 )
        *a4 = *((_DWORD *)v14 + 14);
      ++*(_DWORD *)(v8 + 8);
      return 0;
    }
    v23 = *(_DWORD *)(v8 + 32);
    v24 = 2 * *((_DWORD *)a2 + 2) + 66;
    if ( v16 > v15 )
      v24 = *(_DWORD *)(v8 + 28);
    v25 = 2 * v24;
    if ( v23 <= v25 )
      v23 = v25;
    if ( v23 <= v22 )
    {
      if ( v15 > v23 )
        return 2147942414LL;
      v22 = v23;
    }
    if ( v22 + 8 > v22 && v22 + 8 >= v15 )
    {
      v26 = malloc(v22 + 8LL);
      if ( v26 )
      {
        v17 = 0;
        *v26 = *(_QWORD *)(v8 + 16);
        *(_QWORD *)(v8 + 16) = v26;
        *(_DWORD *)(v8 + 28) = v22;
LABEL_10:
        *(_DWORD *)(v8 + 24) = v17 + ((v15 + 7) & 0xFFFFFFF8);
        v18 = (_QWORD *)(*(_QWORD *)(v8 + 16) + v17);
        goto LABEL_11;
      }
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180030620  mov     [rsp+arg_18], r9
0x180030625  mov     [rsp+arg_10], r8
0x18003062a  push    rbx
0x18003062b  push    r14
0x18003062d  sub     rsp, 48h
0x180030631  cmp     qword ptr [rcx+10h], 0
0x180030636  mov     r14, rdx
0x180030639  mov     rbx, rcx
0x18003063c  jnz     short loc_180030655
0x18003063e  mov     rax, [rcx]
0x180030641  mov     rax, [rax+1A0h]
0x180030648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003064d  test    eax, eax
0x18003064f  js      loc_1800307CE
0x180030655  mov     rbx, [rbx+10h]
0x180030659  mov     [rsp+58h+arg_0], rbp
0x18003065e  mov     [rsp+58h+var_18], rsi
0x180030663  mov     [rsp+58h+var_20], rdi
0x180030668  cmp     qword ptr [rbx+38h], 0
0x18003066d  mov     [rsp+58h+var_28], r12
0x180030672  mov     [rsp+58h+var_30], r13
0x180030677  mov     [rsp+58h+var_38], r15
0x18003067c  jnz     loc_180030831
0x180030682  mov     eax, [rbx+40h]
0x180030685  lea     eax, ds:8[rax*8]
0x18003068c  movsxd  rdi, eax
0x18003068f  mov     rcx, rdi; Size
0x180030692  call    cs:__imp_malloc
0x180030698  mov     [rbx+38h], rax
0x18003069c  test    rax, rax
0x18003069f  jz      loc_18003084A
0x1800306a5  mov     r8, rdi; Size
0x1800306a8  xor     edx, edx; Val
0x1800306aa  mov     rcx, rax; void *
0x1800306ad  call    memset_0
0x1800306b2  mov     ebp, [r14+0Ch]
0x1800306b6  mov     ecx, [rbx+40h]
0x1800306b9  mov     rax, [rbx+38h]
0x1800306bd  and     rcx, rbp
0x1800306c0  lea     r13, [rax+rcx*8]
0x1800306c4  mov     rsi, r13
0x1800306c7  mov     rdi, [rsi]
0x1800306ca  test    rdi, rdi
0x1800306cd  jnz     loc_18003086E
0x1800306d3  mov     eax, [r14+8]
0x1800306d7  lea     edi, ds:42h[rax*2]
0x1800306de  test    edi, edi
0x1800306e0  jle     loc_18003084A
0x1800306e6  mov     r15d, [rbx+1Ch]
0x1800306ea  xor     r12d, r12d
0x1800306ed  mov     ebp, [rbx+18h]
0x1800306f0  mov     eax, r15d
0x1800306f3  sub     eax, ebp
0x1800306f5  cmp     edi, eax
0x1800306f7  jg      loc_1800307D6
0x1800306fd  lea     eax, [rdi+7]
0x180030700  and     eax, 0FFFFFFF8h
0x180030703  add     eax, ebp
0x180030705  mov     [rbx+18h], eax
0x180030708  movsxd  rax, ebp
0x18003070b  add     rax, [rbx+10h]
0x18003070f  lea     rdi, [rax+8]
0x180030713  test    rdi, rdi
0x180030716  jz      loc_18003084A
0x18003071c  mov     rax, [rbx]
0x18003071f  mov     rdx, rdi
0x180030722  mov     rcx, rbx
0x180030725  mov     rax, [rax+30h]
0x180030729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003072e  mov     [rdi+38h], eax
0x180030731  test    eax, eax
0x180030733  jz      loc_18003084A
0x180030739  mov     [rdi], r12w
0x18003073d  lea     rcx, [rdi+40h]; void *
0x180030741  mov     [rdi+18h], r12d
0x180030745  mov     eax, [r14+0Ch]
0x180030749  mov     [rdi+20h], eax
0x18003074c  mov     eax, [r14+8]
0x180030750  add     eax, eax
0x180030752  mov     [rdi+24h], eax
0x180030755  mov     eax, [r14+8]
0x180030759  mov     rdx, [r14]; Src
0x18003075c  add     eax, eax
0x18003075e  movsxd  r8, eax
0x180030761  add     r8, 2; Size
0x180030765  call    memcpy_0
0x18003076a  mov     rax, [r13+0]
0x18003076e  lea     rcx, [rdi+28h]
0x180030772  mov     [rdi+30h], rax
0x180030776  mov     [r13+0], rdi
0x18003077a  inc     dword ptr [rbx+0Ch]
0x18003077d  mov     rax, [rbx+28h]
0x180030781  test    rax, rax
0x180030784  jnz     loc_180030854
0x18003078a  mov     [rbx+28h], rdi
0x18003078e  mov     [rbx+30h], rcx
0x180030792  mov     [rcx], r12
0x180030795  mov     rax, [rsp+58h+arg_10]
0x18003079a  mov     rcx, [rsp+58h+arg_18]
0x18003079f  mov     [rax], rdi
0x1800307a2  test    rcx, rcx
0x1800307a5  jnz     loc_18003090B
0x1800307ab  inc     dword ptr [rbx+8]
0x1800307ae  xor     eax, eax
0x1800307b0  mov     r13, [rsp+58h+var_30]
0x1800307b5  mov     r12, [rsp+58h+var_28]
0x1800307ba  mov     rdi, [rsp+58h+var_20]
0x1800307bf  mov     rsi, [rsp+58h+var_18]
0x1800307c4  mov     rbp, [rsp+58h+arg_0]
0x1800307c9  mov     r15, [rsp+58h+var_38]
0x1800307ce  add     rsp, 48h
0x1800307d2  pop     r14
0x1800307d4  pop     rbx
0x1800307d5  retn
0x1800307d6  mov     esi, [rbx+24h]
0x1800307d9  cmp     edi, esi
0x1800307db  jge     loc_1800308B3
0x1800307e1  mov     ecx, [rbx+20h]
0x1800307e4  cmp     r15d, edi
0x1800307e7  mov     eax, edi
0x1800307e9  cmovg   eax, r15d
0x1800307ed  add     eax, eax
0x1800307ef  cmp     ecx, eax
0x1800307f1  cmovle  ecx, eax
0x1800307f4  cmp     ecx, esi
0x1800307f6  jg      short loc_1800307FE
0x1800307f8  cmp     edi, ecx
0x1800307fa  jg      short loc_18003084A
0x1800307fc  mov     esi, ecx
0x1800307fe  lea     eax, [rsi+8]
0x180030801  cmp     eax, esi
0x180030803  jl      short loc_18003084A
0x180030805  cmp     eax, edi
0x180030807  jl      short loc_18003084A
0x180030809  movsxd  rcx, esi
0x18003080c  add     rcx, 8; Size
0x180030810  call    cs:__imp_malloc
0x180030816  test    rax, rax
0x180030819  jz      short loc_18003084A
0x18003081b  mov     rcx, [rbx+10h]
0x18003081f  mov     ebp, r12d
0x180030822  mov     [rax], rcx
0x180030825  mov     [rbx+10h], rax
0x180030829  mov     [rbx+1Ch], esi
0x18003082c  jmp     loc_1800306FD
0x180030831  mov     eax, [rbx+44h]
0x180030834  cmp     [rbx+0Ch], eax
0x180030837  jl      loc_1800306B2
0x18003083d  mov     rcx, rbx; this
0x180030840  call    ?Rehash@NameList@@AEAAXXZ; NameList::Rehash(void)
0x180030845  jmp     loc_1800306B2
0x18003084a  mov     eax, 8007000Eh
0x18003084f  jmp     loc_1800307B0
0x180030854  cmp     [rsp+58h+arg_20], r12d
0x18003085c  jnz     loc_1800308FF
0x180030862  mov     rax, [rbx+30h]
0x180030866  mov     [rax], rdi
0x180030869  jmp     loc_18003078E
0x18003086e  cmp     [rdi+20h], ebp
0x180030871  jz      short loc_18003087C
0x180030873  lea     rsi, [rdi+30h]
0x180030877  jmp     loc_1800306C7
0x18003087c  mov     rdx, r14; struct SYM *
0x18003087f  mov     rcx, rdi; this
0x180030882  call    ?FEqualRgch@NME@NameList@@QEAAHPEAUSYM@@@Z; NameList::NME::FEqualRgch(SYM *)
0x180030887  test    eax, eax
0x180030889  jz      short loc_1800308F3
0x18003088b  cmp     rsi, r13
0x18003088e  jz      short loc_1800308A3
0x180030890  mov     rax, [rdi+30h]
0x180030894  mov     [rsi], rax
0x180030897  mov     rax, [r13+0]
0x18003089b  mov     [rdi+30h], rax
0x18003089f  mov     [r13+0], rdi
0x1800308a3  xor     r12d, r12d
0x1800308a6  mov     [rdi], r12w
0x1800308aa  mov     [rdi+18h], r12d
0x1800308ae  jmp     loc_180030795
0x1800308b3  lea     eax, [rdi+8]
0x1800308b6  cmp     eax, edi
0x1800308b8  jl      short loc_18003084A
0x1800308ba  movsxd  rcx, edi
0x1800308bd  add     rcx, 8; Size
0x1800308c1  call    cs:__imp_malloc
0x1800308c7  test    rax, rax
0x1800308ca  jz      loc_18003084A
0x1800308d0  mov     rdx, [rbx+10h]
0x1800308d4  cmp     ebp, r15d
0x1800308d7  jge     short loc_1800308E7
0x1800308d9  mov     rcx, [rdx]
0x1800308dc  mov     [rax], rcx
0x1800308df  mov     [rdx], rax
0x1800308e2  jmp     loc_18003070F
0x1800308e7  mov     [rax], rdx
0x1800308ea  mov     [rbx+10h], rax
0x1800308ee  jmp     loc_18003070F
0x1800308f3  lea     rsi, [rdi+30h]
0x1800308f7  mov     r13, rsi
0x1800308fa  jmp     loc_1800306C7
0x1800308ff  mov     [rcx], rax
0x180030902  mov     [rbx+28h], rdi
0x180030906  jmp     loc_180030795
0x18003090b  mov     eax, [rdi+38h]
0x18003090e  mov     [rcx], eax
0x180030910  jmp     loc_1800307AB
```
