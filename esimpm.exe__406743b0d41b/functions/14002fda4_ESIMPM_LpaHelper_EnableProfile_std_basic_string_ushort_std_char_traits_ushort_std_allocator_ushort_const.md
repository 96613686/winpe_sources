# ESIMPM::LpaHelper::EnableProfile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14002fda4`
- end: `0x140030025`
- name: `?EnableProfile@LpaHelper@ESIMPM@@QEAAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x140027e3c`
- `0x14002a188`
- `0x14003002c`
- `0x1400311ec`

## callees

- `0x140002f60`
- `0x140003b28`
- `0x140014f64`
- `0x140020620`
- `0x1400240fc`
- `0x14002fda4`
- `0x1400336c8`

## import_xrefs

- `luiapi!LuiEnableProfile` at `0x14002ff6c`
- `luiapi!LuiEnableProfile` at `0x14002ff6c`

## string_xrefs

- `0x14002fe81`: `LuiEnableProfile eid %s, profileid %s, already active`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ESIMPM::LpaHelper::EnableProfile(__int64 a1, __int64 *a2)
{
  __int64 *v4; // rbx
  _QWORD *v5; // rdi
  __int64 v6; // rcx
  __int64 **v7; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  bool v11; // cc
  __int64 v12; // rdx
  _WORD *v13; // rax
  _WORD *v14; // rcx
  _WORD *v15; // rdx
  unsigned __int64 v16; // rcx
  __int64 v17; // r8
  _WORD *v18; // rax
  _WORD *v19; // rcx
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // [rsp+40h] [rbp-69h] BYREF
  _OWORD v23[3]; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v24[80]; // [rsp+80h] [rbp-29h] BYREF

  v4 = **(__int64 ***)(a1 + 24);
  while ( 1 )
  {
    if ( *((_BYTE *)v4 + 25) )
      return 1168;
    v5 = v4 + 4;
    v6 = v4[8];
    if ( *(_DWORD *)(*(_QWORD *)v6 + 112LL) )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>,0>>::find(
        v6 + 8,
        &v22,
        a2);
      if ( *(_QWORD *)(v4[8] + 8) != v22 )
        break;
    }
    v7 = (__int64 **)v4[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  if ( *(_DWORD *)(**(_QWORD **)(v22 + 64) + 56LL) != 1 )
  {
    memset_0(v24, 0, 0x42u);
    v11 = (unsigned __int64)v4[7] <= 7;
    LODWORD(v22) = 0;
    memset(v23, 0, 42);
    if ( !v11 )
      v5 = (_QWORD *)*v5;
    v12 = 33;
    v13 = v24;
    do
    {
      if ( !*(_WORD *)v5 )
        break;
      *v13 = *(_WORD *)v5;
      v5 = (_QWORD *)((char *)v5 + 2);
      ++v13;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    if ( v12 )
      v14 = v13;
    v11 = (unsigned __int64)a2[3] <= 7;
    *v14 = 0;
    if ( v11 )
      v15 = a2;
    else
      v15 = (_WORD *)*a2;
    v16 = a2[2];
    if ( v16 <= 0x7FFFFFFE )
    {
      v17 = 21;
      v18 = v23;
      do
      {
        if ( !v16 )
          break;
        if ( !*v15 )
          break;
        *v18++ = *v15++;
        --v16;
        --v17;
      }
      while ( v17 );
      v19 = v18 - 1;
      if ( v17 )
        v19 = v18;
      *v19 = 0;
    }
    v20 = LuiEnableProfile(*(_QWORD *)a1, 0, v24, v23, &v22);
    v21 = v20;
    if ( v20 < 0 )
    {
      if ( (v20 & 0x1FFF0000) == 0x70000 )
        v21 = (unsigned __int16)v20;
      if ( v21 )
        goto LABEL_44;
    }
    else
    {
      v21 = 0;
    }
    std::wstring::operator=(a1 + 104, a2);
    *(_DWORD *)(a1 + 232) = v22;
    std::wstring::operator=(a1 + 200, a1 + 168);
    std::wstring::operator=(a1 + 136, a2);
LABEL_44:
    ESIMPM::Log::Info(
      "ESIMPM::LpaHelper::EnableProfile",
      0,
      L"LuiEnableProfile eid %s, profileid %s, TxId %d, result %x",
      v24,
      v23,
      *(_DWORD *)(a1 + 232),
      v21);
    return v21;
  }
  if ( (unsigned __int64)a2[3] > 7 )
    a2 = (__int64 *)*a2;
  if ( (unsigned __int64)v4[7] > 7 )
    v5 = (_QWORD *)*v5;
  ESIMPM::Log::Error(
    "ESIMPM::LpaHelper::EnableProfile",
    0,
    L"LuiEnableProfile eid %s, profileid %s, already active",
    v5,
    a2);
  return 5023;
}

```

## disassembly

```asm
0x14002fda4  mov     [rsp-8+arg_10], rbx
0x14002fda9  push    rbp
0x14002fdaa  push    rsi
0x14002fdab  push    rdi
0x14002fdac  push    r14
0x14002fdae  push    r15
0x14002fdb0  lea     rbp, [rsp-37h]
0x14002fdb5  sub     rsp, 0E0h
0x14002fdbc  mov     rax, cs:__security_cookie
0x14002fdc3  xor     rax, rsp
0x14002fdc6  mov     [rbp+57h+var_30], rax
0x14002fdca  mov     rbx, [rcx+18h]
0x14002fdce  mov     rsi, rdx
0x14002fdd1  mov     r14, rcx
0x14002fdd4  xor     r15d, r15d
0x14002fdd7  mov     rbx, [rbx]
0x14002fdda  cmp     [rbx+19h], r15b
0x14002fdde  jnz     loc_14002FFFD
0x14002fde4  lea     rdi, [rbx+20h]
0x14002fde8  mov     rcx, [rdi+20h]
0x14002fdec  mov     rax, [rcx]
0x14002fdef  cmp     [rax+70h], r15d
0x14002fdf3  jz      short loc_14002FE13
0x14002fdf5  add     rcx, 8
0x14002fdf9  lea     rdx, [rbp+57h+var_C0]
0x14002fdfd  mov     r8, rsi
0x14002fe00  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>,0>>::find(std::wstring const &)
0x14002fe05  mov     rcx, [rdi+20h]
0x14002fe09  mov     rax, [rbp+57h+var_C0]
0x14002fe0d  cmp     [rcx+8], rax
0x14002fe11  jnz     short loc_14002FE58
0x14002fe13  mov     rcx, [rbx+10h]
0x14002fe17  cmp     [rcx+19h], r15b
0x14002fe1b  jz      short loc_14002FE3B
0x14002fe1d  mov     rax, [rbx+8]
0x14002fe21  jmp     short loc_14002FE30
0x14002fe23  cmp     rbx, [rax+10h]
0x14002fe27  jnz     short loc_14002FE36
0x14002fe29  mov     rbx, rax
0x14002fe2c  mov     rax, [rax+8]
0x14002fe30  cmp     [rax+19h], r15b
0x14002fe34  jz      short loc_14002FE23
0x14002fe36  mov     rbx, rax
0x14002fe39  jmp     short loc_14002FDDA
0x14002fe3b  mov     rbx, rcx
0x14002fe3e  mov     rcx, [rcx]
0x14002fe41  cmp     [rcx+19h], r15b
0x14002fe45  jnz     short loc_14002FDDA
0x14002fe47  mov     rax, [rcx]
0x14002fe4a  mov     rbx, rcx
0x14002fe4d  mov     rcx, rax
0x14002fe50  cmp     [rax+19h], r15b
0x14002fe54  jz      short loc_14002FE47
0x14002fe56  jmp     short loc_14002FDDA
0x14002fe58  mov     rcx, [rax+40h]
0x14002fe5c  mov     rax, [rcx]
0x14002fe5f  cmp     dword ptr [rax+38h], 1
0x14002fe63  jnz     short loc_14002FEA0
0x14002fe65  cmp     qword ptr [rsi+18h], 7
0x14002fe6a  jbe     short loc_14002FE6F
0x14002fe6c  mov     rsi, [rsi]
0x14002fe6f  cmp     qword ptr [rdi+18h], 7
0x14002fe74  jbe     short loc_14002FE79
0x14002fe76  mov     rdi, [rdi]
0x14002fe79  mov     r9, rdi
0x14002fe7c  mov     [rsp+100h+var_E0], rsi
0x14002fe81  lea     r8, aLuienableprofi_0; "LuiEnableProfile eid %s, profileid %s, "...
0x14002fe88  xor     edx, edx; struct _GUID *
0x14002fe8a  lea     rcx, aEsimpmLpahelpe_1; "ESIMPM::LpaHelper::EnableProfile"
0x14002fe91  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002fe96  mov     eax, 139Fh
0x14002fe9b  jmp     loc_140030002
0x14002fea0  xor     edx, edx; Val
0x14002fea2  lea     rcx, [rbp+57h+var_80]; void *
0x14002fea6  lea     r8d, [rdx+42h]; Size
0x14002feaa  call    memset_0
0x14002feaf  cmp     qword ptr [rdi+18h], 7
0x14002feb4  xorps   xmm0, xmm0
0x14002feb7  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x14002febb  mov     dword ptr [rbp+57h+var_C0], r15d
0x14002febf  movups  xmmword ptr [rbp+57h+var_A8+0Ah], xmm0
0x14002fec3  movups  [rbp+57h+var_B8], xmm0
0x14002fec7  jbe     short loc_14002FECC
0x14002fec9  mov     rdi, [rdi]
0x14002fecc  mov     edx, 21h ; '!'
0x14002fed1  lea     rax, [rbp+57h+var_80]
0x14002fed5  movzx   ecx, word ptr [rdi]
0x14002fed8  test    cx, cx
0x14002fedb  jz      short loc_14002FEEE
0x14002fedd  mov     [rax], cx
0x14002fee0  add     rdi, 2
0x14002fee4  add     rax, 2
0x14002fee8  sub     rdx, 1
0x14002feec  jnz     short loc_14002FED5
0x14002feee  test    rdx, rdx
0x14002fef1  lea     rcx, [rax-2]
0x14002fef5  cmovnz  rcx, rax
0x14002fef9  cmp     qword ptr [rsi+18h], 7
0x14002fefe  mov     [rcx], r15w
0x14002ff02  jbe     short loc_14002FF09
0x14002ff04  mov     rdx, [rsi]
0x14002ff07  jmp     short loc_14002FF0C
0x14002ff09  mov     rdx, rsi
0x14002ff0c  mov     rcx, [rsi+10h]
0x14002ff10  cmp     rcx, 7FFFFFFEh
0x14002ff17  ja      short loc_14002FF56
0x14002ff19  mov     r8d, 15h
0x14002ff1f  lea     rax, [rbp+57h+var_B8]
0x14002ff23  test    rcx, rcx
0x14002ff26  jz      short loc_14002FF47
0x14002ff28  movzx   r9d, word ptr [rdx]
0x14002ff2c  test    r9w, r9w
0x14002ff30  jz      short loc_14002FF47
0x14002ff32  mov     [rax], r9w
0x14002ff36  add     rdx, 2
0x14002ff3a  add     rax, 2
0x14002ff3e  dec     rcx
0x14002ff41  sub     r8, 1
0x14002ff45  jnz     short loc_14002FF23
0x14002ff47  test    r8, r8
0x14002ff4a  lea     rcx, [rax-2]
0x14002ff4e  cmovnz  rcx, rax
0x14002ff52  mov     [rcx], r15w
0x14002ff56  mov     rcx, [r14]
0x14002ff59  lea     rax, [rbp+57h+var_C0]
0x14002ff5d  lea     r9, [rbp+57h+var_B8]
0x14002ff61  mov     [rsp+100h+var_E0], rax
0x14002ff66  lea     r8, [rbp+57h+var_80]
0x14002ff6a  xor     edx, edx
0x14002ff6c  call    cs:__imp_LuiEnableProfile
0x14002ff72  mov     ebx, eax
0x14002ff74  test    eax, eax
0x14002ff76  js      short loc_14002FF7D
0x14002ff78  mov     ebx, r15d
0x14002ff7b  jmp     short loc_14002FF90
0x14002ff7d  and     eax, 1FFF0000h
0x14002ff82  cmp     eax, 70000h
0x14002ff87  jnz     short loc_14002FF8C
0x14002ff89  movzx   ebx, bx
0x14002ff8c  test    ebx, ebx
0x14002ff8e  jnz     short loc_14002FFC8
0x14002ff90  lea     rcx, [r14+68h]
0x14002ff94  mov     rdx, rsi
0x14002ff97  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14002ff9c  mov     eax, dword ptr [rbp+57h+var_C0]
0x14002ff9f  lea     rdx, [r14+0A8h]
0x14002ffa6  lea     rcx, [r14+0C8h]
0x14002ffad  mov     [r14+0E8h], eax
0x14002ffb4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14002ffb9  lea     rcx, [r14+88h]
0x14002ffc0  mov     rdx, rsi
0x14002ffc3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14002ffc8  mov     ecx, [r14+0E8h]
0x14002ffcf  lea     rax, [rbp+57h+var_B8]
0x14002ffd3  mov     [rsp+100h+var_D0], ebx
0x14002ffd7  lea     r9, [rbp+57h+var_80]
0x14002ffdb  mov     [rsp+100h+var_D8], ecx
0x14002ffdf  lea     r8, aLuienableprofi; "LuiEnableProfile eid %s, profileid %s, "...
0x14002ffe6  lea     rcx, aEsimpmLpahelpe_1; "ESIMPM::LpaHelper::EnableProfile"
0x14002ffed  mov     [rsp+100h+var_E0], rax
0x14002fff2  xor     edx, edx; struct _GUID *
0x14002fff4  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002fff9  mov     eax, ebx
0x14002fffb  jmp     short loc_140030002
0x14002fffd  mov     eax, 490h
0x140030002  mov     rcx, [rbp+57h+var_30]
0x140030006  xor     rcx, rsp; StackCookie
0x140030009  call    __security_check_cookie
0x14003000e  mov     rbx, [rsp+100h+arg_10]
0x140030016  add     rsp, 0E0h
0x14003001d  pop     r15
0x14003001f  pop     r14
0x140030021  pop     rdi
0x140030022  pop     rsi
0x140030023  pop     rbp
0x140030024  retn
```
