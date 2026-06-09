# CATUtils::DeleteAppNameFromConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)

- ea: `0x14001c58c`
- end: `0x14001c6e1`
- name: `?DeleteAppNameFromConfig@CATUtils@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001cf70`

## callees

- `0x1400045c8`
- `0x140005c04`
- `0x140005ce8`
- `0x140009524`
- `0x140009cd8`
- `0x14000a414`
- `0x14001c508`
- `0x14001c58c`
- `0x14001cbac`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CATUtils::DeleteAppNameFromConfig(char **a1, __int64 a2)
{
  __int64 v3; // r8
  char *v4; // rdx
  char *v5; // rcx
  int *v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  char *v9; // [rsp+28h] [rbp-8h] BYREF
  int v10; // [rsp+68h] [rbp+38h] BYREF
  int v11; // [rsp+6Ch] [rbp+3Ch]
  int v12; // [rsp+70h] [rbp+40h] BYREF
  char *v13; // [rsp+78h] [rbp+48h] BYREF

  v11 = HIDWORD(a2);
  v12 = 0;
  v10 = 44;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v8,
    a1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
    &v8,
    &v13,
    (const wchar_t *)&v10,
    &v12);
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1, &qword_14002AAD0, 0);
  while ( *(_WORD *)v13 )
  {
    if ( *((_DWORD *)v13 - 4)
      && (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                         &v13,
                         L"osk") )
    {
      ATL::CSimpleStringT<unsigned short,0>::Append(a1, v13, *((unsigned int *)v13 - 4));
      v3 = -1;
      do
        ++v3;
      while ( *((_WORD *)&v10 + v3) );
      ATL::CSimpleStringT<unsigned short,0>::Append(a1, &v10, v3);
    }
    v4 = *ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
            &v8,
            &v9,
            (const wchar_t *)&v10,
            &v12);
    v5 = v4 - 24;
    v6 = (int *)(v13 - 24);
    if ( v4 - 24 != v13 - 24 )
    {
      if ( v6[4] >= 0 && *(_QWORD *)v5 == *(_QWORD *)v6 )
      {
        v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v5);
        ATL::CStringData::Release((ATL::CStringData *)v6);
        v13 = (char *)(v7 + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v13, v4, *((_DWORD *)v4 - 4));
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(a1, &v10);
  ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
}

```

## disassembly

```asm
0x14001c58c  mov     [rsp-28h+arg_8], rdx
0x14001c591  push    rbp
0x14001c592  push    rbx
0x14001c593  push    rsi
0x14001c594  push    rdi
0x14001c595  push    r14
0x14001c597  mov     rbp, rsp
0x14001c59a  sub     rsp, 30h
0x14001c59e  mov     rsi, rcx
0x14001c5a1  xor     r14d, r14d
0x14001c5a4  mov     [rbp+arg_10], r14d
0x14001c5a8  mov     dword ptr [rbp+arg_8], 2Ch ; ','
0x14001c5af  mov     rdx, rcx
0x14001c5b2  lea     rcx, [rbp+var_10]
0x14001c5b6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001c5bb  nop
0x14001c5bc  lea     r9, [rbp+arg_10]
0x14001c5c0  lea     r8, [rbp+arg_8]
0x14001c5c4  lea     rdx, [rbp+arg_18]
0x14001c5c8  lea     rcx, [rbp+var_10]
0x14001c5cc  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x14001c5d1  nop
0x14001c5d2  xor     r8d, r8d
0x14001c5d5  lea     rdx, qword_14002AAD0
0x14001c5dc  mov     rcx, rsi
0x14001c5df  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001c5e4  nop
0x14001c5e5  mov     rax, [rbp+arg_18]
0x14001c5e9  cmp     [rax], r14w
0x14001c5ed  jz      loc_14001C6AE
0x14001c5f3  cmp     [rax-10h], r14d
0x14001c5f7  jz      short loc_14001C63C
0x14001c5f9  lea     rdx, aOsk_2; "osk"
0x14001c600  lea     rcx, [rbp+arg_18]
0x14001c604  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x14001c609  nop
0x14001c60a  test    eax, eax
0x14001c60c  jz      short loc_14001C63C
0x14001c60e  mov     rdx, [rbp+arg_18]
0x14001c612  mov     r8d, [rdx-10h]
0x14001c616  mov     rcx, rsi
0x14001c619  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001c61e  lea     rax, [rbp+arg_8]
0x14001c622  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001c626  inc     r8
0x14001c629  cmp     [rax+r8*2], r14w
0x14001c62e  jnz     short loc_14001C626
0x14001c630  lea     rdx, [rbp+arg_8]
0x14001c634  mov     rcx, rsi
0x14001c637  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001c63c  lea     r9, [rbp+arg_10]
0x14001c640  lea     r8, [rbp+arg_8]
0x14001c644  lea     rdx, [rbp+var_8]
0x14001c648  lea     rcx, [rbp+var_10]
0x14001c64c  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x14001c651  nop
0x14001c652  mov     rdx, [rax]
0x14001c655  lea     rcx, [rdx-18h]
0x14001c659  mov     rdi, [rbp+arg_18]
0x14001c65d  add     rdi, 0FFFFFFFFFFFFFFE8h
0x14001c661  cmp     rcx, rdi
0x14001c664  jz      short loc_14001C69C
0x14001c666  cmp     [rdi+10h], r14d
0x14001c66a  jl      short loc_14001C68E
0x14001c66c  mov     rax, [rdi]
0x14001c66f  cmp     [rcx], rax
0x14001c672  jnz     short loc_14001C68E
0x14001c674  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001c679  mov     rbx, rax
0x14001c67c  mov     rcx, rdi; this
0x14001c67f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c684  lea     rax, [rbx+18h]
0x14001c688  mov     [rbp+arg_18], rax
0x14001c68c  jmp     short loc_14001C69C
0x14001c68e  mov     r8d, [rdx-10h]
0x14001c692  lea     rcx, [rbp+arg_18]
0x14001c696  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001c69b  nop
0x14001c69c  mov     rcx, [rbp+var_8]
0x14001c6a0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c6a4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c6a9  jmp     loc_14001C5E5
0x14001c6ae  lea     rdx, [rbp+arg_8]
0x14001c6b2  mov     rcx, rsi
0x14001c6b5  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(ushort const *)
0x14001c6ba  nop
0x14001c6bb  mov     rcx, [rbp+arg_18]
0x14001c6bf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c6c3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c6c8  nop
0x14001c6c9  mov     rcx, [rbp+var_10]
0x14001c6cd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c6d1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c6d6  add     rsp, 30h
0x14001c6da  pop     r14
0x14001c6dc  pop     rdi
0x14001c6dd  pop     rsi
0x14001c6de  pop     rbx
0x14001c6df  pop     rbp
0x14001c6e0  retn
```
