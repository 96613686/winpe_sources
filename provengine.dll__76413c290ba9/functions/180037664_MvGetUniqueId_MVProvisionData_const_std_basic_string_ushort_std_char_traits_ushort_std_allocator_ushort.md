# MvGetUniqueId(_MVProvisionData const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180037664`
- end: `0x180037954`
- name: `?MvGetUniqueId@@YAJAEBU_MVProvisionData@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `752`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180034380`

## callees

- `0x1800098dc`
- `0x18000af20`
- `0x18000b030`
- `0x180010ad8`
- `0x180021c5c`
- `0x180021e40`
- `0x180021f40`
- `0x1800228e4`
- `0x180036c74`
- `0x180037664`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!towupper` at `0x1800377aa`
- `msvcrt!_wcsicmp` at `0x180037756`
- `msvcrt!_wcsicmp` at `0x180037756`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037859`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037859`

## string_xrefs

- `0x18003789e`: `onecoreuap\admin\prov\multivariant\common\src\provxmlhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MvGetUniqueId(__int64 a1, const void **a2)
{
  const void **v2; // rdi
  const void **v4; // r12
  unsigned int v5; // eax
  const void **v6; // rbx
  const void **v7; // rsi
  __int64 v8; // r15
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rcx
  unsigned __int64 v13; // r8
  const void **v14; // rdi
  const void **v15; // rcx
  const void **v16; // r13
  const void **v17; // r15
  signed __int64 v18; // rdi
  void **v19; // rdx
  char *v20; // rdx
  unsigned __int64 v21; // r8
  __int64 v22; // rdx
  unsigned int i; // ebx
  int v25; // [rsp+20h] [rbp-60h]
  void *v26[2]; // [rsp+28h] [rbp-58h] BYREF
  const void **v27; // [rsp+38h] [rbp-48h]
  wchar_t *String1; // [rsp+40h] [rbp-40h] BYREF
  void *v29; // [rsp+48h] [rbp-38h] BYREF
  const void **v30; // [rsp+50h] [rbp-30h]
  const void *Src[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v32; // [rsp+68h] [rbp-18h]
  unsigned __int64 v33; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v2 = a2;
  v30 = a2;
  *(_OWORD *)v26 = 0;
  v4 = 0;
  v27 = 0;
  v5 = 0;
  v25 = 0;
  v6 = 0;
  v7 = 0;
  if ( *(_DWORD *)(a1 + 32) )
  {
    while ( 1 )
    {
      String1 = 0;
      v29 = 0;
      v8 = v5;
      v9 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL * v5);
      v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v9 + 40LL))(v9, &String1);
      v11 = v10;
      if ( v10 < 0 )
        break;
      v12 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8 * v8);
      v10 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v12 + 48LL))(v12, &v29);
      v11 = v10;
      if ( v10 < 0 )
      {
        v22 = 161;
        goto LABEL_34;
      }
      v33 = 7;
      v32 = 0;
      LOWORD(Src[0]) = 0;
      if ( *String1 )
      {
        v13 = -1;
        do
          ++v13;
        while ( String1[v13] );
      }
      else
      {
        v13 = 0;
      }
      std::wstring::assign(Src, (char *)String1, v13);
      if ( _wcsicmp(String1, L"roaming") )
      {
        std::wstring::push_back(Src);
        std::wstring::append(Src, (char *)v29);
      }
      v14 = Src;
      if ( v33 >= 8 )
        v14 = (const void **)Src[0];
      v15 = Src;
      if ( v33 >= 8 )
        v15 = (const void **)Src[0];
      v16 = (const void **)((char *)v15 + 2 * v32);
      v17 = Src;
      if ( v33 >= 8 )
        v17 = (const void **)Src[0];
      while ( v17 != v16 )
      {
        *(_WORD *)v14 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v17);
        v14 = (const void **)((char *)v14 + 2);
        v17 = (const void **)((char *)v17 + 2);
      }
      if ( Src >= v6 || v7 > Src )
      {
        if ( v6 == v4 )
        {
          std::vector<std::wstring>::_Reserve(v26);
          v4 = v27;
          v6 = (const void **)v26[1];
          v7 = (const void **)v26[0];
        }
        v19 = (void **)Src;
      }
      else
      {
        v18 = (char *)Src - (char *)v7;
        if ( v6 == v4 )
        {
          std::vector<std::wstring>::_Reserve(v26);
          v4 = v27;
          v6 = (const void **)v26[1];
          v7 = (const void **)v26[0];
        }
        v19 = (void **)((char *)v7 + (v18 & 0xFFFFFFFFFFFFFFE0uLL));
      }
      v6[3] = (const void *)7;
      v6[2] = 0;
      *(_WORD *)v6 = 0;
      std::wstring::assign((void **)v6, v19, 0, 0xFFFFFFFFFFFFFFFFuLL);
      v6 += 4;
      v26[1] = v6;
      if ( v33 >= 8 )
        operator delete((void *)Src[0]);
      v5 = v25 + 1;
      v25 = v5;
      if ( v5 >= *(_DWORD *)(a1 + 32) )
      {
        v2 = v30;
        goto LABEL_31;
      }
    }
    v22 = 160;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\provxmlhelper.cpp",
      (const char *)(unsigned int)v10,
      v25);
  }
  else
  {
LABEL_31:
    std::_Sort<std::wstring *,__int64>(v7, v6, ((char *)v6 - (char *)v7) >> 5);
    v20 = *(char **)(a1 + 40);
    if ( *(_WORD *)v20 )
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)&v20[2 * v21] );
    }
    else
    {
      v21 = 0;
    }
    std::wstring::assign(v2, v20, v21);
    std::wstring::append(v2, (char *)L"--");
    for ( i = 0; i < *(_DWORD *)(a1 + 32); ++i )
    {
      std::wstring::append(v2, &v7[4 * i], 0, 0xFFFFFFFFFFFFFFFFuLL);
      if ( i != *(_DWORD *)(a1 + 32) - 1 )
        std::wstring::append(v2, (char *)L"--");
    }
    v11 = 0;
  }
  std::vector<std::wstring>::_Tidy((__int64)v26);
  return v11;
}

```

## disassembly

```asm
0x180037664  mov     [rsp-38h+arg_10], rbx
0x180037669  push    rbp
0x18003766a  push    rsi
0x18003766b  push    rdi
0x18003766c  push    r12
0x18003766e  push    r13
0x180037670  push    r14
0x180037672  push    r15
0x180037674  mov     rbp, rsp
0x180037677  sub     rsp, 80h
0x18003767e  mov     rax, cs:__security_cookie
0x180037685  xor     rax, rsp
0x180037688  mov     [rbp+var_8], rax
0x18003768c  mov     rdi, rdx
0x18003768f  mov     [rbp+var_30], rdx
0x180037693  mov     r14, rcx
0x180037696  xorps   xmm0, xmm0
0x180037699  movdqu  xmmword ptr [rbp+var_58], xmm0
0x18003769e  xor     r13d, r13d
0x1800376a1  mov     r12d, r13d
0x1800376a4  mov     [rbp+var_48], r13
0x1800376a8  mov     eax, r13d
0x1800376ab  mov     [rbp+var_60], eax
0x1800376ae  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800376b2  mov     rbx, [rbp+var_58+8]
0x1800376b6  mov     rsi, [rbp+var_58]
0x1800376ba  cmp     [rcx+20h], r13d
0x1800376be  jbe     loc_180037875
0x1800376c4  mov     [rbp+String1], r13
0x1800376c8  mov     [rbp+var_38], r13
0x1800376cc  mov     r15d, eax
0x1800376cf  mov     rax, [r14+18h]
0x1800376d3  mov     rcx, [rax+r15*8]
0x1800376d7  mov     rax, [rcx]
0x1800376da  lea     rdx, [rbp+String1]
0x1800376de  mov     rax, [rax+28h]
0x1800376e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376e7  mov     edi, eax
0x1800376e9  test    eax, eax
0x1800376eb  js      loc_1800378B3
0x1800376f1  mov     rax, [r14+18h]
0x1800376f5  mov     rcx, [rax+r15*8]
0x1800376f9  mov     rax, [rcx]
0x1800376fc  lea     rdx, [rbp+var_38]
0x180037700  mov     rax, [rax+30h]
0x180037704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037709  mov     edi, eax
0x18003770b  test    eax, eax
0x18003770d  js      loc_180037899
0x180037713  mov     rdx, [rbp+String1]; Src
0x180037717  mov     [rbp+var_10], 7
0x18003771f  mov     [rbp+var_18], r13
0x180037723  mov     word ptr [rbp+Src], r13w
0x180037728  cmp     [rdx], r13w
0x18003772c  jnz     short loc_180037733
0x18003772e  mov     r8, r13
0x180037731  jmp     short loc_180037741
0x180037733  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037737  inc     r8
0x18003773a  cmp     [rdx+r8*2], r13w
0x18003773f  jnz     short loc_180037737
0x180037741  lea     rcx, [rbp+Src]; void *
0x180037745  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003774a  nop
0x18003774b  lea     rdx, ?gc_wszRoaming@@3QBGB; "roaming"
0x180037752  mov     rcx, [rbp+String1]; String1
0x180037756  call    cs:__imp__wcsicmp
0x18003775c  test    eax, eax
0x18003775e  jz      short loc_18003777B
0x180037760  mov     edx, 2Dh ; '-'
0x180037765  lea     rcx, [rbp+Src]; Src
0x180037769  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18003776e  mov     rdx, [rbp+var_38]; void *
0x180037772  lea     rcx, [rbp+Src]; Src
0x180037776  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18003777b  lea     rdi, [rbp+Src]
0x18003777f  mov     r8, [rbp+Src]
0x180037783  cmp     [rbp+var_10], 8
0x180037788  cmovnb  rdi, r8
0x18003778c  lea     rcx, [rbp+Src]
0x180037790  cmovnb  rcx, r8
0x180037794  mov     rax, [rbp+var_18]
0x180037798  lea     r13, [rcx+rax*2]
0x18003779c  lea     r15, [rbp+Src]
0x1800377a0  cmovnb  r15, r8
0x1800377a4  jmp     short loc_1800377C1
0x1800377a6  movzx   ecx, word ptr [r15]
0x1800377aa  mov     rax, cs:__imp_towupper
0x1800377b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377b6  mov     [rdi], ax
0x1800377b9  lea     rdi, [rdi+2]
0x1800377bd  add     r15, 2
0x1800377c1  cmp     r15, r13
0x1800377c4  jnz     short loc_1800377A6
0x1800377c6  lea     rax, [rbp+Src]
0x1800377ca  cmp     rax, rbx
0x1800377cd  jnb     short loc_180037803
0x1800377cf  lea     rax, [rbp+Src]
0x1800377d3  cmp     rsi, rax
0x1800377d6  ja      short loc_180037803
0x1800377d8  lea     rdi, [rbp+Src]
0x1800377dc  sub     rdi, rsi
0x1800377df  cmp     rbx, r12
0x1800377e2  jnz     short loc_1800377F9
0x1800377e4  lea     rcx, [rbp+var_58]
0x1800377e8  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800377ed  mov     r12, [rbp+var_48]
0x1800377f1  mov     rbx, [rbp+var_58+8]
0x1800377f5  mov     rsi, [rbp+var_58]
0x1800377f9  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1800377fd  lea     rdx, [rsi+rdi]
0x180037801  jmp     short loc_180037821
0x180037803  cmp     rbx, r12
0x180037806  jnz     short loc_18003781D
0x180037808  lea     rcx, [rbp+var_58]
0x18003780c  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180037811  mov     r12, [rbp+var_48]
0x180037815  mov     rbx, [rbp+var_58+8]
0x180037819  mov     rsi, [rbp+var_58]
0x18003781d  lea     rdx, [rbp+Src]
0x180037821  xor     r13d, r13d
0x180037824  mov     qword ptr [rbx+18h], 7
0x18003782c  mov     [rbx+10h], r13
0x180037830  or      r15, 0FFFFFFFFFFFFFFFFh
0x180037834  mov     [rbx], r13w
0x180037838  mov     r9, r15
0x18003783b  xor     r8d, r8d
0x18003783e  mov     rcx, rbx; void *
0x180037841  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180037846  add     rbx, 20h ; ' '
0x18003784a  mov     [rbp+var_58+8], rbx
0x18003784e  cmp     [rbp+var_10], 8
0x180037853  jb      short loc_18003785F
0x180037855  mov     rcx, [rbp+Src]
0x180037859  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003785f  mov     eax, [rbp+var_60]
0x180037862  inc     eax
0x180037864  mov     [rbp+var_60], eax
0x180037867  cmp     eax, [r14+20h]
0x18003786b  jb      loc_1800376C4
0x180037871  mov     rdi, [rbp+var_30]
0x180037875  mov     r8, rbx
0x180037878  sub     r8, rsi
0x18003787b  sar     r8, 5
0x18003787f  mov     rdx, rbx
0x180037882  mov     rcx, rsi
0x180037885  call    ??$_Sort@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0_J@Z; std::_Sort<std::wstring *,__int64>(std::wstring *,std::wstring *,__int64)
0x18003788a  mov     rdx, [r14+28h]; Src
0x18003788e  cmp     [rdx], r13w
0x180037892  jnz     short loc_1800378BA
0x180037894  mov     r8, r13
0x180037897  jmp     short loc_1800378C7
0x180037899  mov     edx, 0A1h; void *
0x18003789e  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800378a5  mov     r9d, eax; char *
0x1800378a8  mov     rcx, [rbp+38h]; this
0x1800378ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800378b1  jmp     short loc_180037922
0x1800378b3  mov     edx, 0A0h
0x1800378b8  jmp     short loc_18003789E
0x1800378ba  mov     r8, r15
0x1800378bd  inc     r8
0x1800378c0  cmp     [rdx+r8*2], r13w
0x1800378c5  jnz     short loc_1800378BD
0x1800378c7  mov     rcx, rdi; void *
0x1800378ca  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800378cf  lea     rdx, asc_18004C91C; "--"
0x1800378d6  mov     rcx, rdi; Src
0x1800378d9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800378de  mov     ebx, r13d
0x1800378e1  cmp     [r14+20h], r13d
0x1800378e5  jbe     short loc_18003791F
0x1800378e7  mov     edx, ebx
0x1800378e9  shl     rdx, 5
0x1800378ed  add     rdx, rsi
0x1800378f0  mov     r9, r15
0x1800378f3  xor     r8d, r8d
0x1800378f6  mov     rcx, rdi
0x1800378f9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800378fe  mov     eax, [r14+20h]
0x180037902  dec     eax
0x180037904  cmp     ebx, eax
0x180037906  jz      short loc_180037917
0x180037908  lea     rdx, asc_18004C91C; "--"
0x18003790f  mov     rcx, rdi; Src
0x180037912  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180037917  inc     ebx
0x180037919  cmp     ebx, [r14+20h]
0x18003791d  jb      short loc_1800378E7
0x18003791f  mov     edi, r13d
0x180037922  lea     rcx, [rbp+var_58]
0x180037926  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18003792b  mov     eax, edi
0x18003792d  mov     rcx, [rbp+var_8]
0x180037931  xor     rcx, rsp; StackCookie
0x180037934  call    __security_check_cookie
0x180037939  mov     rbx, [rsp+80h+arg_10]
0x180037941  add     rsp, 80h
0x180037948  pop     r15
0x18003794a  pop     r14
0x18003794c  pop     r13
0x18003794e  pop     r12
0x180037950  pop     rdi
0x180037951  pop     rsi
0x180037952  pop     rbp
0x180037953  retn
```
