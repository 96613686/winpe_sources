# NameTbl::CreateProtoRefVval(SYM *,VVAL * *,long *,int)

- ea: `0x18002ec50`
- end: `0x18002ef58`
- name: `?CreateProtoRefVval@NameTbl@@MEAAJPEAUSYM@@PEAPEAUVVAL@@PEAJH@Z`
- size: `776`
- prototype: `int(NameTbl *__hidden this, struct SYM *, struct VVAL **, int *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002eb80`

## callees

- `0x18002ec50`
- `0x18002f230`
- `0x18002f434`
- `0x180096692`
- `0x1800966aa`
- `0x180098010`

## import_xrefs

- `msvcrt!malloc` at `0x18002ecc2`
- `msvcrt!malloc` at `0x18002ee47`
- `msvcrt!malloc` at `0x18002eefe`
- `msvcrt!malloc` at `0x18002ecc2`
- `msvcrt!malloc` at `0x18002ee47`
- `msvcrt!malloc` at `0x18002eefe`

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
0x18002ec50  mov     [rsp+arg_18], r9
0x18002ec55  mov     [rsp+arg_10], r8
0x18002ec5a  push    rbx
0x18002ec5b  push    r14
0x18002ec5d  sub     rsp, 48h
0x18002ec61  cmp     qword ptr [rcx+10h], 0
0x18002ec66  mov     r14, rdx
0x18002ec69  mov     rbx, rcx
0x18002ec6c  jnz     short loc_18002EC85
0x18002ec6e  mov     rax, [rcx]
0x18002ec71  mov     rax, [rax+1A0h]
0x18002ec78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec7d  test    eax, eax
0x18002ec7f  js      loc_18002EE04
0x18002ec85  mov     rbx, [rbx+10h]
0x18002ec89  mov     [rsp+58h+arg_0], rbp
0x18002ec8e  mov     [rsp+58h+var_18], rsi
0x18002ec93  mov     [rsp+58h+var_20], rdi
0x18002ec98  cmp     qword ptr [rbx+38h], 0
0x18002ec9d  mov     [rsp+58h+var_28], r12
0x18002eca2  mov     [rsp+58h+var_30], r13
0x18002eca7  mov     [rsp+58h+var_38], r15
0x18002ecac  jnz     loc_18002EE6E
0x18002ecb2  mov     eax, [rbx+40h]
0x18002ecb5  lea     eax, ds:8[rax*8]
0x18002ecbc  movsxd  rdi, eax
0x18002ecbf  mov     rcx, rdi; Size
0x18002ecc2  call    cs:__imp_malloc
0x18002ecc9  nop     dword ptr [rax+rax+00h]
0x18002ecce  mov     [rbx+38h], rax
0x18002ecd2  test    rax, rax
0x18002ecd5  jz      loc_18002EE87
0x18002ecdb  mov     r8, rdi; Size
0x18002ecde  xor     edx, edx; Val
0x18002ece0  mov     rcx, rax; void *
0x18002ece3  call    memset_0
0x18002ece8  mov     ebp, [r14+0Ch]
0x18002ecec  mov     ecx, [rbx+40h]
0x18002ecef  mov     rax, [rbx+38h]
0x18002ecf3  and     rcx, rbp
0x18002ecf6  lea     r13, [rax+rcx*8]
0x18002ecfa  mov     rsi, r13
0x18002ecfd  mov     rdi, [rsi]
0x18002ed00  test    rdi, rdi
0x18002ed03  jnz     loc_18002EEAB
0x18002ed09  mov     eax, [r14+8]
0x18002ed0d  lea     edi, ds:42h[rax*2]
0x18002ed14  test    edi, edi
0x18002ed16  jle     loc_18002EE87
0x18002ed1c  mov     r15d, [rbx+1Ch]
0x18002ed20  xor     r12d, r12d
0x18002ed23  mov     ebp, [rbx+18h]
0x18002ed26  mov     eax, r15d
0x18002ed29  sub     eax, ebp
0x18002ed2b  cmp     edi, eax
0x18002ed2d  jg      loc_18002EE0D
0x18002ed33  lea     eax, [rdi+7]
0x18002ed36  and     eax, 0FFFFFFF8h
0x18002ed39  add     eax, ebp
0x18002ed3b  mov     [rbx+18h], eax
0x18002ed3e  movsxd  rax, ebp
0x18002ed41  add     rax, [rbx+10h]
0x18002ed45  lea     rdi, [rax+8]
0x18002ed49  test    rdi, rdi
0x18002ed4c  jz      loc_18002EE87
0x18002ed52  mov     rax, [rbx]
0x18002ed55  mov     rdx, rdi
0x18002ed58  mov     rcx, rbx
0x18002ed5b  mov     rax, [rax+30h]
0x18002ed5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed64  mov     [rdi+38h], eax
0x18002ed67  test    eax, eax
0x18002ed69  jz      loc_18002EE87
0x18002ed6f  mov     [rdi], r12w
0x18002ed73  lea     rcx, [rdi+40h]; void *
0x18002ed77  mov     [rdi+18h], r12d
0x18002ed7b  mov     eax, [r14+0Ch]
0x18002ed7f  mov     [rdi+20h], eax
0x18002ed82  mov     eax, [r14+8]
0x18002ed86  add     eax, eax
0x18002ed88  mov     [rdi+24h], eax
0x18002ed8b  mov     eax, [r14+8]
0x18002ed8f  mov     rdx, [r14]; Src
0x18002ed92  add     eax, eax
0x18002ed94  movsxd  r8, eax
0x18002ed97  add     r8, 2; Size
0x18002ed9b  call    memcpy_0
0x18002eda0  mov     rax, [r13+0]
0x18002eda4  lea     rcx, [rdi+28h]
0x18002eda8  mov     [rdi+30h], rax
0x18002edac  mov     [r13+0], rdi
0x18002edb0  inc     dword ptr [rbx+0Ch]
0x18002edb3  mov     rax, [rbx+28h]
0x18002edb7  test    rax, rax
0x18002edba  jnz     loc_18002EE91
0x18002edc0  mov     [rbx+28h], rdi
0x18002edc4  mov     [rbx+30h], rcx
0x18002edc8  mov     [rcx], r12
0x18002edcb  mov     rax, [rsp+58h+arg_10]
0x18002edd0  mov     rcx, [rsp+58h+arg_18]
0x18002edd5  mov     [rax], rdi
0x18002edd8  test    rcx, rcx
0x18002eddb  jnz     loc_18002EF4E
0x18002ede1  inc     dword ptr [rbx+8]
0x18002ede4  xor     eax, eax
0x18002ede6  mov     r13, [rsp+58h+var_30]
0x18002edeb  mov     r12, [rsp+58h+var_28]
0x18002edf0  mov     rdi, [rsp+58h+var_20]
0x18002edf5  mov     rsi, [rsp+58h+var_18]
0x18002edfa  mov     rbp, [rsp+58h+arg_0]
0x18002edff  mov     r15, [rsp+58h+var_38]
0x18002ee04  add     rsp, 48h
0x18002ee08  pop     r14
0x18002ee0a  pop     rbx
0x18002ee0b  retn
0x18002ee0d  mov     esi, [rbx+24h]
0x18002ee10  cmp     edi, esi
0x18002ee12  jge     loc_18002EEF0
0x18002ee18  mov     ecx, [rbx+20h]
0x18002ee1b  cmp     r15d, edi
0x18002ee1e  mov     eax, edi
0x18002ee20  cmovg   eax, r15d
0x18002ee24  add     eax, eax
0x18002ee26  cmp     ecx, eax
0x18002ee28  cmovle  ecx, eax
0x18002ee2b  cmp     ecx, esi
0x18002ee2d  jg      short loc_18002EE35
0x18002ee2f  cmp     edi, ecx
0x18002ee31  jg      short loc_18002EE87
0x18002ee33  mov     esi, ecx
0x18002ee35  lea     eax, [rsi+8]
0x18002ee38  cmp     eax, esi
0x18002ee3a  jl      short loc_18002EE87
0x18002ee3c  cmp     eax, edi
0x18002ee3e  jl      short loc_18002EE87
0x18002ee40  movsxd  rcx, esi
0x18002ee43  add     rcx, 8; Size
0x18002ee47  call    cs:__imp_malloc
0x18002ee4e  nop     dword ptr [rax+rax+00h]
0x18002ee53  test    rax, rax
0x18002ee56  jz      short loc_18002EE87
0x18002ee58  mov     rcx, [rbx+10h]
0x18002ee5c  mov     ebp, r12d
0x18002ee5f  mov     [rax], rcx
0x18002ee62  mov     [rbx+10h], rax
0x18002ee66  mov     [rbx+1Ch], esi
0x18002ee69  jmp     loc_18002ED33
0x18002ee6e  mov     eax, [rbx+44h]
0x18002ee71  cmp     [rbx+0Ch], eax
0x18002ee74  jl      loc_18002ECE8
0x18002ee7a  mov     rcx, rbx; this
0x18002ee7d  call    ?Rehash@NameList@@AEAAXXZ; NameList::Rehash(void)
0x18002ee82  jmp     loc_18002ECE8
0x18002ee87  mov     eax, 8007000Eh
0x18002ee8c  jmp     loc_18002EDE6
0x18002ee91  cmp     [rsp+58h+arg_20], r12d
0x18002ee99  jnz     loc_18002EF42
0x18002ee9f  mov     rax, [rbx+30h]
0x18002eea3  mov     [rax], rdi
0x18002eea6  jmp     loc_18002EDC4
0x18002eeab  cmp     [rdi+20h], ebp
0x18002eeae  jz      short loc_18002EEB9
0x18002eeb0  lea     rsi, [rdi+30h]
0x18002eeb4  jmp     loc_18002ECFD
0x18002eeb9  mov     rdx, r14; struct SYM *
0x18002eebc  mov     rcx, rdi; this
0x18002eebf  call    ?FEqualRgch@NME@NameList@@QEAAHPEAUSYM@@@Z; NameList::NME::FEqualRgch(SYM *)
0x18002eec4  test    eax, eax
0x18002eec6  jz      short loc_18002EF36
0x18002eec8  cmp     rsi, r13
0x18002eecb  jz      short loc_18002EEE0
0x18002eecd  mov     rax, [rdi+30h]
0x18002eed1  mov     [rsi], rax
0x18002eed4  mov     rax, [r13+0]
0x18002eed8  mov     [rdi+30h], rax
0x18002eedc  mov     [r13+0], rdi
0x18002eee0  xor     r12d, r12d
0x18002eee3  mov     [rdi], r12w
0x18002eee7  mov     [rdi+18h], r12d
0x18002eeeb  jmp     loc_18002EDCB
0x18002eef0  lea     eax, [rdi+8]
0x18002eef3  cmp     eax, edi
0x18002eef5  jl      short loc_18002EE87
0x18002eef7  movsxd  rcx, edi
0x18002eefa  add     rcx, 8; Size
0x18002eefe  call    cs:__imp_malloc
0x18002ef05  nop     dword ptr [rax+rax+00h]
0x18002ef0a  test    rax, rax
0x18002ef0d  jz      loc_18002EE87
0x18002ef13  mov     rdx, [rbx+10h]
0x18002ef17  cmp     ebp, r15d
0x18002ef1a  jge     short loc_18002EF2A
0x18002ef1c  mov     rcx, [rdx]
0x18002ef1f  mov     [rax], rcx
0x18002ef22  mov     [rdx], rax
0x18002ef25  jmp     loc_18002ED45
0x18002ef2a  mov     [rax], rdx
0x18002ef2d  mov     [rbx+10h], rax
0x18002ef31  jmp     loc_18002ED45
0x18002ef36  lea     rsi, [rdi+30h]
0x18002ef3a  mov     r13, rsi
0x18002ef3d  jmp     loc_18002ECFD
0x18002ef42  mov     [rcx], rax
0x18002ef45  mov     [rbx+28h], rdi
0x18002ef49  jmp     loc_18002EDCB
0x18002ef4e  mov     eax, [rdi+38h]
0x18002ef51  mov     [rcx], eax
0x18002ef53  jmp     loc_18002EDE1
```
