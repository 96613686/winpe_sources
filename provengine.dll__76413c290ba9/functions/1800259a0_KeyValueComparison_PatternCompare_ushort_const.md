# KeyValueComparison::PatternCompare(ushort const *)

- ea: `0x1800259a0`
- end: `0x180025b7f`
- name: `?PatternCompare@KeyValueComparison@@AEBA_NPEBG@Z`
- size: `479`
- prototype: `bool __fastcall(KeyValueComparison *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800021b4`
- `0x180023900`
- `0x180024a20`
- `0x1800259a0`
- `0x180028f98`
- `0x180029078`
- `0x18002bdd0`
- `0x180047010`

## import_xrefs

- `msvcp110_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800259d2`
- `msvcp110_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800259d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025b1f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025b1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall KeyValueComparison::PatternCompare(KeyValueComparison *this, const unsigned __int16 *a2)
{
  char *v3; // rbx
  char *v4; // rcx
  __int64 v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v10; // rdi
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  _QWORD *v12; // rax
  __int64 v13; // rax
  char v14; // bl
  __int128 v16; // [rsp+30h] [rbp-79h] BYREF
  __int64 v17; // [rsp+40h] [rbp-69h]
  struct std::locale::_Locimp *v18; // [rsp+48h] [rbp-61h]
  unsigned __int16 *v19[4]; // [rsp+50h] [rbp-59h] BYREF
  __int128 v20; // [rsp+70h] [rbp-39h] BYREF
  __int64 v21; // [rsp+80h] [rbp-29h]
  __int64 v22; // [rsp+88h] [rbp-21h]
  _QWORD *v23; // [rsp+90h] [rbp-19h]
  _QWORD *v24; // [rsp+98h] [rbp-11h]
  int v25; // [rsp+A0h] [rbp-9h]
  char *v26; // [rsp+A8h] [rbp-1h]
  int v27; // [rsp+B0h] [rbp+7h]
  int v28; // [rsp+B4h] [rbp+Bh]
  char *v29; // [rsp+B8h] [rbp+Fh]
  int v30; // [rsp+C0h] [rbp+17h]
  int v31; // [rsp+D0h] [rbp+27h]
  _QWORD *v32; // [rsp+110h] [rbp+67h] BYREF

  v3 = (char *)this + 48;
  v16 = 0;
  v17 = 0;
  v18 = std::locale::_Init(1);
  if ( *((_QWORD *)v3 + 3) < 8u )
    v4 = v3;
  else
    v4 = *(char **)v3;
  v5 = *((_QWORD *)v3 + 2);
  if ( *((_QWORD *)v3 + 3) >= 8u )
    v3 = *(char **)v3;
  v19[0] = (unsigned __int16 *)v3;
  v19[1] = (unsigned __int16 *)v3;
  v19[2] = (unsigned __int16 *)&v4[2 * v5];
  v19[3] = 0;
  LODWORD(v32) = 0;
  v20 = 0;
  v21 = 0;
  std::vector<unsigned int>::_Construct_n(&v20, 0, &v32);
  if ( (__int64)(*((_QWORD *)&v20 + 1) - v20) >> 2 )
    *((_QWORD *)&v20 + 1) = v20;
  v22 = 0;
  v6 = operator new(0x30u);
  v32 = v6;
  if ( v6 )
  {
    v6[1] = 20;
    v6[2] = 0;
    v6[3] = 0;
    *v6 = &std::_Node_endif::`vftable';
    *(_QWORD *)((char *)v6 + 36) = 0;
    *((_DWORD *)v6 + 11) = 0;
  }
  else
  {
    v6 = 0;
  }
  v23 = v6;
  v24 = v6;
  v25 = 1;
  v26 = (char *)&v16 + 8;
  v27 = 256;
  v28 = 4;
  v29 = (char *)&v16 + 8;
  v30 = 1;
  v31 = 142040571;
  std::_Parser<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>>::_Trans(v19);
  v7 = std::_Parser<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>>::_Compile((__int64)v19);
  v8 = v7;
  if ( v7 )
    ++*(_DWORD *)(v7 + 44);
  if ( (_QWORD)v16 )
  {
    if ( (*(_DWORD *)(v16 + 44))-- == 1 )
    {
      v10 = v16;
      while ( v10 )
      {
        v11 = (void (__fastcall ***)(_QWORD, __int64))v10;
        v12 = (_QWORD *)(v10 + 16);
        v10 = *(_QWORD *)(v10 + 16);
        *v12 = 0;
        (**v11)(v11, 1);
      }
    }
  }
  *(_QWORD *)&v16 = v8;
  v22 = 0;
  if ( (_QWORD)v20 )
    operator delete((void *)v20);
  if ( *a2 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
  }
  else
  {
    LODWORD(v13) = 0;
  }
  v14 = std::_Regex_match<unsigned short const *,std::allocator<std::sub_match<unsigned short const *>>,unsigned short,std::regex_traits<unsigned short>,unsigned short const *>(
          (_DWORD)a2,
          (int)a2 + 2 * (int)v13,
          0,
          (unsigned int)&v16,
          16);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(&v16);
  return v14;
}

```

## disassembly

```asm
0x1800259a0  mov     [rsp-8+arg_8], rbx
0x1800259a5  mov     [rsp-8+arg_10], rsi
0x1800259aa  push    rbp
0x1800259ab  push    rdi
0x1800259ac  push    r14
0x1800259ae  lea     rbp, [rsp-47h]
0x1800259b3  sub     rsp, 0F0h
0x1800259ba  mov     rsi, rdx
0x1800259bd  lea     rbx, [rcx+30h]
0x1800259c1  xorps   xmm0, xmm0
0x1800259c4  movdqu  [rbp+57h+var_D0], xmm0
0x1800259c9  xor     r14d, r14d
0x1800259cc  mov     [rbp+57h+var_C0], r14
0x1800259d0  mov     cl, 1
0x1800259d2  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x1800259d8  mov     [rbp+57h+var_B8], rax
0x1800259dc  cmp     qword ptr [rbx+18h], 8
0x1800259e1  jb      short loc_1800259E8
0x1800259e3  mov     rcx, [rbx]
0x1800259e6  jmp     short loc_1800259EB
0x1800259e8  mov     rcx, rbx
0x1800259eb  mov     rax, [rbx+10h]
0x1800259ef  lea     rdx, [rcx+rax*2]
0x1800259f3  jb      short loc_1800259F8
0x1800259f5  mov     rbx, [rbx]
0x1800259f8  mov     [rbp+57h+var_B0], rbx
0x1800259fc  mov     [rbp+57h+var_A8], rbx
0x180025a00  mov     [rbp+57h+var_A0], rdx
0x180025a04  mov     [rbp+57h+var_98], r14
0x180025a08  mov     dword ptr [rbp+57h+arg_0], r14d
0x180025a0c  xorps   xmm0, xmm0
0x180025a0f  movdqa  [rbp+57h+var_90], xmm0
0x180025a14  mov     [rbp+57h+var_80], r14
0x180025a18  lea     r8, [rbp+57h+arg_0]
0x180025a1c  xor     edx, edx
0x180025a1e  lea     rcx, [rbp+57h+var_90]
0x180025a22  call    ?_Construct_n@?$vector@IV?$allocator@_N@std@@@std@@QEAAX_KPEBI@Z; std::vector<uint>::_Construct_n(unsigned __int64,uint const *)
0x180025a27  nop
0x180025a28  mov     rcx, qword ptr [rbp+57h+var_90]
0x180025a2c  mov     rax, qword ptr [rbp+57h+var_90+8]
0x180025a30  sub     rax, rcx
0x180025a33  sar     rax, 2
0x180025a37  test    rax, rax
0x180025a3a  jz      short loc_180025A40
0x180025a3c  mov     qword ptr [rbp+57h+var_90+8], rcx
0x180025a40  mov     [rbp+57h+var_78], r14
0x180025a44  mov     ecx, 30h ; '0'; Size
0x180025a49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025a4e  mov     [rbp+57h+arg_0], rax
0x180025a52  test    rax, rax
0x180025a55  jz      short loc_180025A7B
0x180025a57  mov     qword ptr [rax+8], 14h
0x180025a5f  mov     [rax+10h], r14
0x180025a63  mov     [rax+18h], r14
0x180025a67  lea     rcx, ??_7_Node_endif@std@@6B@; const std::_Node_endif::`vftable'
0x180025a6e  mov     [rax], rcx
0x180025a71  mov     [rax+24h], r14
0x180025a75  mov     [rax+2Ch], r14d
0x180025a79  jmp     short loc_180025A7E
0x180025a7b  mov     rax, r14
0x180025a7e  mov     [rbp+57h+var_70], rax
0x180025a82  mov     [rbp+57h+var_68], rax
0x180025a86  mov     [rbp+57h+var_60], 1
0x180025a8d  lea     rax, [rbp+57h+var_D0+8]
0x180025a91  mov     [rbp+57h+var_58], rax
0x180025a95  mov     [rbp+57h+var_50], 100h
0x180025a9c  mov     [rbp+57h+var_4C], 4
0x180025aa3  lea     rax, [rbp+57h+var_D0+8]
0x180025aa7  mov     [rbp+57h+var_48], rax
0x180025aab  mov     [rbp+57h+var_40], 1
0x180025ab2  mov     [rbp+57h+var_30], 8775DFBh
0x180025ab9  lea     rcx, [rbp+57h+var_B0]
0x180025abd  call    ?_Trans@?$_Parser@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@@std@@AEAAXXZ; std::_Parser<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>>::_Trans(void)
0x180025ac2  nop
0x180025ac3  lea     rcx, [rbp+57h+var_B0]
0x180025ac7  call    ?_Compile@?$_Parser@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@@std@@QEAAPEAV_Root_node@2@XZ; std::_Parser<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>>::_Compile(void)
0x180025acc  mov     rbx, rax
0x180025acf  test    rax, rax
0x180025ad2  jz      short loc_180025AD7
0x180025ad4  inc     dword ptr [rax+2Ch]
0x180025ad7  mov     rcx, qword ptr [rbp+57h+var_D0]
0x180025adb  test    rcx, rcx
0x180025ade  jz      short loc_180025B0E
0x180025ae0  add     dword ptr [rcx+2Ch], 0FFFFFFFFh
0x180025ae4  jnz     short loc_180025B0E
0x180025ae6  mov     rdi, qword ptr [rbp+57h+var_D0]
0x180025aea  jmp     short loc_180025B09
0x180025aec  mov     rcx, rdi
0x180025aef  lea     rax, [rdi+10h]
0x180025af3  mov     rdi, [rax]
0x180025af6  mov     [rax], r14
0x180025af9  mov     rax, [rcx]
0x180025afc  mov     edx, 1
0x180025b01  mov     rax, [rax]
0x180025b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b09  test    rdi, rdi
0x180025b0c  jnz     short loc_180025AEC
0x180025b0e  mov     qword ptr [rbp+57h+var_D0], rbx
0x180025b12  mov     [rbp+57h+var_78], r14
0x180025b16  mov     rcx, qword ptr [rbp+57h+var_90]
0x180025b1a  test    rcx, rcx
0x180025b1d  jz      short loc_180025B26
0x180025b1f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180025b25  nop
0x180025b26  cmp     [rsi], r14w
0x180025b2a  jnz     short loc_180025B31
0x180025b2c  mov     rax, r14
0x180025b2f  jmp     short loc_180025B3F
0x180025b31  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025b35  inc     rax
0x180025b38  cmp     [rsi+rax*2], r14w
0x180025b3d  jnz     short loc_180025B35
0x180025b3f  lea     rdx, [rsi+rax*2]
0x180025b43  mov     [rsp+100h+var_E0], 10h
0x180025b4b  lea     r9, [rbp+57h+var_D0]
0x180025b4f  xor     r8d, r8d
0x180025b52  mov     rcx, rsi
0x180025b55  call    ??$_Regex_match@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@GV?$regex_traits@G@2@PEBG@std@@YA_NPEBG0PEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@_N@Z; std::_Regex_match<ushort const *,std::allocator<std::sub_match<ushort const *>>,ushort,std::regex_traits<ushort>,ushort const *>(ushort const *,ushort const *,std::match_results<ushort const *> *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type,bool)
0x180025b5a  mov     bl, al
0x180025b5c  lea     rcx, [rbp+57h+var_D0]
0x180025b60  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180025b65  mov     al, bl
0x180025b67  lea     r11, [rsp+100h+var_10]
0x180025b6f  mov     rbx, [r11+28h]
0x180025b73  mov     rsi, [r11+30h]
0x180025b77  mov     rsp, r11
0x180025b7a  pop     r14
0x180025b7c  pop     rdi
0x180025b7d  pop     rbp
0x180025b7e  retn
```
