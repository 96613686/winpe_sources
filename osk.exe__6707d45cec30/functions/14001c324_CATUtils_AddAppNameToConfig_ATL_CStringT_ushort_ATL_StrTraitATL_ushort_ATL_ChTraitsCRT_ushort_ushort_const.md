# CATUtils::AddAppNameToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)

- ea: `0x14001c324`
- end: `0x14001c440`
- name: `?AddAppNameToConfig@CATUtils@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001cf70`

## callees

- `0x140005c04`
- `0x140005ce8`
- `0x140009524`
- `0x140009cd8`
- `0x14000a414`
- `0x14001c324`
- `0x14001c4e0`
- `0x14001c508`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CATUtils::AddAppNameToConfig(__int64 *a1, __int64 a2)
{
  char *v3; // rdx
  char *v4; // rcx
  int *v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // r8
  char *v8; // [rsp+20h] [rbp-10h] BYREF
  int v9; // [rsp+68h] [rbp+38h] BYREF
  int v10; // [rsp+6Ch] [rbp+3Ch]
  int v11; // [rsp+70h] [rbp+40h] BYREF
  char *v12; // [rsp+78h] [rbp+48h] BYREF

  v10 = HIDWORD(a2);
  v11 = 0;
  v9 = 44;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
    a1,
    &v12,
    (const wchar_t *)&v9,
    &v11);
  while ( *(_WORD *)v12 )
  {
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                          &v12,
                          L"osk") )
      goto LABEL_15;
    v3 = *ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
            a1,
            &v8,
            (const wchar_t *)&v9,
            &v11);
    v4 = v3 - 24;
    v5 = (int *)(v12 - 24);
    if ( v3 - 24 != v12 - 24 )
    {
      if ( v5[4] >= 0 && *(_QWORD *)v4 == *(_QWORD *)v5 )
      {
        v6 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v4);
        ATL::CStringData::Release((ATL::CStringData *)v5);
        v12 = (char *)(v6 + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v12, v3, *((_DWORD *)v3 - 4));
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
  }
  if ( *(_DWORD *)(*a1 - 16) )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)&v9 + v7) );
    ATL::CSimpleStringT<unsigned short,0>::Append(a1, &v9, v7);
  }
  ATL::CSimpleStringT<unsigned short,0>::Append(a1, L"osk");
LABEL_15:
  ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
}

```

## disassembly

```asm
0x14001c324  mov     [rsp-28h+arg_8], rdx
0x14001c329  push    rbp
0x14001c32a  push    rbx
0x14001c32b  push    rsi
0x14001c32c  push    rdi
0x14001c32d  push    r14
0x14001c32f  mov     rbp, rsp
0x14001c332  sub     rsp, 30h
0x14001c336  mov     rdi, rcx
0x14001c339  xor     r14d, r14d
0x14001c33c  mov     [rbp+arg_10], r14d
0x14001c340  mov     dword ptr [rbp+arg_8], 2Ch ; ','
0x14001c347  lea     r9, [rbp+arg_10]
0x14001c34b  lea     r8, [rbp+arg_8]
0x14001c34f  lea     rdx, [rbp+arg_18]
0x14001c353  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x14001c358  nop
0x14001c359  mov     rax, [rbp+arg_18]
0x14001c35d  cmp     [rax], r14w
0x14001c361  jz      loc_14001C3F1
0x14001c367  lea     rdx, aOsk_2; "osk"
0x14001c36e  lea     rcx, [rbp+arg_18]
0x14001c372  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x14001c377  nop
0x14001c378  test    eax, eax
0x14001c37a  jz      loc_14001C428
0x14001c380  lea     r9, [rbp+arg_10]
0x14001c384  lea     r8, [rbp+arg_8]
0x14001c388  lea     rdx, [rbp+var_10]
0x14001c38c  mov     rcx, rdi
0x14001c38f  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x14001c394  nop
0x14001c395  mov     rdx, [rax]
0x14001c398  lea     rcx, [rdx-18h]
0x14001c39c  mov     rsi, [rbp+arg_18]
0x14001c3a0  add     rsi, 0FFFFFFFFFFFFFFE8h
0x14001c3a4  cmp     rcx, rsi
0x14001c3a7  jz      short loc_14001C3DF
0x14001c3a9  cmp     [rsi+10h], r14d
0x14001c3ad  jl      short loc_14001C3D1
0x14001c3af  mov     rax, [rsi]
0x14001c3b2  cmp     [rcx], rax
0x14001c3b5  jnz     short loc_14001C3D1
0x14001c3b7  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001c3bc  mov     rbx, rax
0x14001c3bf  mov     rcx, rsi; this
0x14001c3c2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c3c7  lea     rax, [rbx+18h]
0x14001c3cb  mov     [rbp+arg_18], rax
0x14001c3cf  jmp     short loc_14001C3DF
0x14001c3d1  mov     r8d, [rdx-10h]
0x14001c3d5  lea     rcx, [rbp+arg_18]
0x14001c3d9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001c3de  nop
0x14001c3df  mov     rcx, [rbp+var_10]
0x14001c3e3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c3e7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c3ec  jmp     loc_14001C359
0x14001c3f1  mov     rax, [rdi]
0x14001c3f4  cmp     [rax-10h], r14d
0x14001c3f8  jz      short loc_14001C418
0x14001c3fa  lea     rax, [rbp+arg_8]
0x14001c3fe  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001c402  inc     r8
0x14001c405  cmp     [rax+r8*2], r14w
0x14001c40a  jnz     short loc_14001C402
0x14001c40c  lea     rdx, [rbp+arg_8]
0x14001c410  mov     rcx, rdi
0x14001c413  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001c418  lea     rdx, aOsk_2; "osk"
0x14001c41f  mov     rcx, rdi
0x14001c422  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14001c427  nop
0x14001c428  mov     rcx, [rbp+arg_18]
0x14001c42c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c430  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c435  add     rsp, 30h
0x14001c439  pop     r14
0x14001c43b  pop     rdi
0x14001c43c  pop     rsi
0x14001c43d  pop     rbx
0x14001c43e  pop     rbp
0x14001c43f  retn
```
