# CopyServerNameAndFilterToNewConnectionProperties(_EAPTLS_CONTROL_BLOCK const &,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,_EAPTLS_CONN_PROPERTIES_V1 *)

- ea: `0x180045100`
- end: `0x180045419`
- name: `?CopyServerNameAndFilterToNewConnectionProperties@@YAJAEBU_EAPTLS_CONTROL_BLOCK@@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002d950`

## callees

- `0x180002360`
- `0x18002077c`
- `0x180029110`
- `0x18002dc0c`
- `0x18002dc50`
- `0x180035f68`
- `0x180038270`
- `0x180045100`
- `0x18004d438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180045201`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180045266`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180045201`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180045266`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180045315`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180045315`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004517c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004517c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CopyServerNameAndFilterToNewConnectionProperties(__int64 a1, _BYTE *a2, __int64 a3)
{
  char *v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // edi
  char *v13; // rdi
  __int64 v14; // rax
  char *v15; // rsi
  unsigned int v16; // eax
  unsigned int v17; // edi
  _QWORD *v18; // r8
  unsigned int v19; // eax
  unsigned int v20; // edi
  _QWORD *v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // r8
  unsigned int v24; // eax
  unsigned int v25; // edi
  unsigned int v26; // eax
  unsigned int v27; // edi
  rsize_t SourceSize; // [rsp+20h] [rbp-88h] BYREF
  void *Source[2]; // [rsp+28h] [rbp-80h] BYREF
  _QWORD v30[2]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v31; // [rsp+48h] [rbp-60h]
  unsigned __int64 v32; // [rsp+50h] [rbp-58h]
  _QWORD v33[2]; // [rsp+58h] [rbp-50h] BYREF
  __int64 v34; // [rsp+68h] [rbp-40h]
  unsigned __int64 v35; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  Source[1] = a2;
  v5 = (char *)(a3 + 8 * (*(unsigned int *)(a3 + 12) + 2 * (*(unsigned int *)(a3 + 12) + 1LL)));
  v6 = *(_QWORD *)(a1 + 544)
     + 8
     * (*(unsigned int *)(*(_QWORD *)(a1 + 544) + 12LL) + 2 * (*(unsigned int *)(*(_QWORD *)(a1 + 544) + 12LL) + 1LL));
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v6 + 2 * v7) );
  if ( (_DWORD)v7 )
  {
    v8 = (unsigned int)v7;
    v9 = (unsigned int)(v7 + 1);
    v10 = _o_wcsncpy_s(v5, v9, v6, (unsigned int)v7);
    if ( v10 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x3B,
              (unsigned int)"onecoreuap\\net\\rras\\ras\\ppp\\eaptls\\moderntlsstackeaptls.cpp",
              (const char *)v10,
              SourceSize);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(a2);
      return v11;
    }
    v13 = &v5[2 * v9];
    if ( !a2[32] || !*(_QWORD *)(std::optional<std::wstring>::value(a2) + 16) )
      goto LABEL_23;
    v14 = std::optional<std::wstring>::value(a2);
    std::wstring::wstring(v30, v14);
    v15 = &v5[2 * v8];
    v16 = _o_wcscat_s(v15, 2, L";");
    if ( v16 )
    {
      v17 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x43,
              (unsigned int)"onecoreuap\\net\\rras\\ras\\ppp\\eaptls\\moderntlsstackeaptls.cpp",
              (const char *)v16,
              SourceSize);
      std::wstring::_Tidy_deallocate(v30);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(a2);
      return v17;
    }
    v18 = v30;
    if ( v32 > 7 )
      v18 = (_QWORD *)v30[0];
    v19 = _o_wcscat_s(v15 + 2, v31 + 1, v18);
    if ( v19 )
    {
      v20 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x45,
              (unsigned int)"onecoreuap\\net\\rras\\ras\\ppp\\eaptls\\moderntlsstackeaptls.cpp",
              (const char *)v19,
              SourceSize);
      std::wstring::_Tidy_deallocate(v30);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(a2);
      return v20;
    }
    v13 += 2 * v31 + 2;
    v21 = v30;
    goto LABEL_22;
  }
  v13 = v5;
  if ( a2[32] && *(_QWORD *)(std::optional<std::wstring>::value(a2) + 16) )
  {
    v22 = std::optional<std::wstring>::value(a2);
    std::wstring::wstring(v33, v22);
    v23 = v33;
    if ( v35 > 7 )
      v23 = (_QWORD *)v33[0];
    v24 = _o_wcscpy_s(v5, v34 + 1, v23);
    if ( v24 )
    {
      v25 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x4E,
              (unsigned int)"onecoreuap\\net\\rras\\ras\\ppp\\eaptls\\moderntlsstackeaptls.cpp",
              (const char *)v24,
              SourceSize);
      std::wstring::_Tidy_deallocate(v33);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(a2);
      return v25;
    }
    v13 = &v5[2 * v34 + 2];
    v21 = v33;
LABEL_22:
    std::wstring::_Tidy_deallocate(v21);
  }
LABEL_23:
  Source[0] = 0;
  LODWORD(SourceSize) = 0;
  if ( (unsigned int)isCertFilterLogicPresentInV1(
                       *(struct _EAPTLS_CONN_PROPERTIES_V1 **)(a1 + 544),
                       (unsigned __int8 **)Source,
                       (unsigned int *)&SourceSize)
    && (v26 = memcpy_s(v13, (unsigned int)SourceSize, Source[0], (unsigned int)SourceSize)) != 0 )
  {
    v27 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x59,
            (unsigned int)"onecoreuap\\net\\rras\\ras\\ppp\\eaptls\\moderntlsstackeaptls.cpp",
            (const char *)v26,
            SourceSize);
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(a2);
    return v27;
  }
  else
  {
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(a2);
    return 0;
  }
}

```

## disassembly

```asm
0x180045100  mov     [rsp+arg_18], rbx
0x180045105  push    rsi
0x180045106  push    rdi
0x180045107  push    r12
0x180045109  push    r14
0x18004510b  push    r15
0x18004510d  sub     rsp, 80h
0x180045114  mov     rax, cs:__security_cookie
0x18004511b  xor     rax, rsp
0x18004511e  mov     [rsp+0A8h+var_30], rax
0x180045123  mov     rbx, rdx
0x180045126  mov     r15, rcx
0x180045129  mov     [rsp+0A8h+var_78], rdx
0x18004512e  mov     eax, [r8+0Ch]
0x180045132  lea     rdx, [rax+1]
0x180045136  lea     rdx, [rax+rdx*2]
0x18004513a  lea     rsi, [r8+rdx*8]
0x18004513e  mov     rdx, [rcx+220h]
0x180045145  mov     eax, [rdx+0Ch]
0x180045148  lea     r8, [rax+1]
0x18004514c  lea     r8, [rax+r8*2]
0x180045150  lea     r8, [rdx+r8*8]
0x180045154  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045158  xor     r12d, r12d
0x18004515b  inc     rax
0x18004515e  cmp     [r8+rax*2], r12w
0x180045163  jnz     short loc_18004515B
0x180045165  test    eax, eax
0x180045167  jz      loc_1800452C5
0x18004516d  mov     r14d, eax
0x180045170  inc     eax
0x180045172  mov     edi, eax
0x180045174  mov     r9d, r14d
0x180045177  mov     edx, eax
0x180045179  mov     rcx, rsi
0x18004517c  call    cs:__imp__o_wcsncpy_s
0x180045183  nop     dword ptr [rax+rax+00h]
0x180045188  test    eax, eax
0x18004518a  jz      short loc_1800451B9
0x18004518c  mov     rcx, [rsp+0A8h]; this
0x180045194  mov     r9d, eax; char *
0x180045197  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x18004519e  mov     edx, 3Bh ; ';'; void *
0x1800451a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800451a8  mov     edi, eax
0x1800451aa  mov     rcx, rbx
0x1800451ad  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1800451b2  mov     eax, edi
0x1800451b4  jmp     loc_1800453F3
0x1800451b9  lea     rdi, [rsi+rdi*2]
0x1800451bd  cmp     [rbx+20h], r12b
0x1800451c1  jz      loc_180045373
0x1800451c7  mov     rcx, rbx
0x1800451ca  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1800451cf  cmp     [rax+10h], r12
0x1800451d3  jbe     loc_180045373
0x1800451d9  mov     rcx, rbx
0x1800451dc  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1800451e1  mov     rdx, rax
0x1800451e4  lea     rcx, [rsp+0A8h+var_70]
0x1800451e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800451ee  lea     rsi, [rsi+r14*2]
0x1800451f2  lea     r8, asc_180087BE0; ";"
0x1800451f9  mov     edx, 2
0x1800451fe  mov     rcx, rsi
0x180045201  call    cs:__imp__o_wcscat_s
0x180045208  nop     dword ptr [rax+rax+00h]
0x18004520d  test    eax, eax
0x18004520f  jz      short loc_180045249
0x180045211  mov     rcx, [rsp+0A8h]; this
0x180045219  mov     r9d, eax; char *
0x18004521c  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x180045223  mov     edx, 43h ; 'C'; void *
0x180045228  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004522d  mov     edi, eax
0x18004522f  lea     rcx, [rsp+0A8h+var_70]
0x180045234  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045239  nop
0x18004523a  mov     rcx, rbx
0x18004523d  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180045242  mov     eax, edi
0x180045244  jmp     loc_1800453F3
0x180045249  lea     rcx, [rsi+2]
0x18004524d  lea     r8, [rsp+0A8h+var_70]
0x180045252  cmp     [rsp+0A8h+var_58], 7
0x180045258  cmova   r8, [rsp+0A8h+var_70]
0x18004525e  mov     rdx, [rsp+0A8h+var_60]
0x180045263  inc     rdx
0x180045266  call    cs:__imp__o_wcscat_s
0x18004526d  nop     dword ptr [rax+rax+00h]
0x180045272  test    eax, eax
0x180045274  jz      short loc_1800452AE
0x180045276  mov     rcx, [rsp+0A8h]; this
0x18004527e  mov     r9d, eax; char *
0x180045281  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x180045288  mov     edx, 45h ; 'E'; void *
0x18004528d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180045292  mov     edi, eax
0x180045294  lea     rcx, [rsp+0A8h+var_70]
0x180045299  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004529e  nop
0x18004529f  mov     rcx, rbx
0x1800452a2  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1800452a7  mov     eax, edi
0x1800452a9  jmp     loc_1800453F3
0x1800452ae  mov     rax, [rsp+0A8h+var_60]
0x1800452b3  lea     rdi, [rdi+rax*2]
0x1800452b7  add     rdi, 2
0x1800452bb  lea     rcx, [rsp+0A8h+var_70]
0x1800452c0  jmp     loc_18004536E
0x1800452c5  mov     rdi, rsi
0x1800452c8  cmp     [rbx+20h], r12b
0x1800452cc  jz      loc_180045373
0x1800452d2  mov     rcx, rbx
0x1800452d5  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1800452da  cmp     [rax+10h], r12
0x1800452de  jbe     loc_180045373
0x1800452e4  mov     rcx, rbx
0x1800452e7  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1800452ec  mov     rdx, rax
0x1800452ef  lea     rcx, [rsp+0A8h+var_50]
0x1800452f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800452f9  lea     r8, [rsp+0A8h+var_50]
0x1800452fe  cmp     [rsp+0A8h+var_38], 7
0x180045304  cmova   r8, [rsp+0A8h+var_50]
0x18004530a  mov     rdx, [rsp+0A8h+var_40]
0x18004530f  inc     rdx
0x180045312  mov     rcx, rsi
0x180045315  call    cs:__imp__o_wcscpy_s
0x18004531c  nop     dword ptr [rax+rax+00h]
0x180045321  test    eax, eax
0x180045323  jz      short loc_18004535D
0x180045325  mov     rcx, [rsp+0A8h]; this
0x18004532d  mov     r9d, eax; char *
0x180045330  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x180045337  mov     edx, 4Eh ; 'N'; void *
0x18004533c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180045341  mov     edi, eax
0x180045343  lea     rcx, [rsp+0A8h+var_50]
0x180045348  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004534d  nop
0x18004534e  mov     rcx, rbx
0x180045351  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180045356  mov     eax, edi
0x180045358  jmp     loc_1800453F3
0x18004535d  mov     rax, [rsp+0A8h+var_40]
0x180045362  inc     rax
0x180045365  lea     rdi, [rsi+rax*2]
0x180045369  lea     rcx, [rsp+0A8h+var_50]
0x18004536e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045373  mov     [rsp+0A8h+Source], r12
0x180045378  mov     dword ptr [rsp+0A8h+SourceSize], r12d; unsigned int
0x18004537d  lea     r8, [rsp+0A8h+SourceSize]; unsigned int *
0x180045382  lea     rdx, [rsp+0A8h+Source]; unsigned __int8 **
0x180045387  mov     rcx, [r15+220h]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18004538e  call    ?isCertFilterLogicPresentInV1@@YAHPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAEPEAK@Z; isCertFilterLogicPresentInV1(_EAPTLS_CONN_PROPERTIES_V1 *,uchar * *,ulong *)
0x180045393  test    eax, eax
0x180045395  jz      short loc_1800453D9
0x180045397  mov     edx, dword ptr [rsp+0A8h+SourceSize]; DestinationSize
0x18004539b  mov     r9d, edx; SourceSize
0x18004539e  mov     r8, [rsp+0A8h+Source]; Source
0x1800453a3  mov     rcx, rdi; Destination
0x1800453a6  call    memcpy_s
0x1800453ab  test    eax, eax
0x1800453ad  jz      short loc_1800453D9
0x1800453af  mov     rcx, [rsp+0A8h]; this
0x1800453b7  mov     r9d, eax; char *
0x1800453ba  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x1800453c1  mov     edx, 59h ; 'Y'; void *
0x1800453c6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800453cb  mov     edi, eax
0x1800453cd  mov     rcx, rbx
0x1800453d0  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1800453d5  mov     eax, edi
0x1800453d7  jmp     short loc_1800453F3
0x1800453d9  mov     rcx, rbx
0x1800453dc  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1800453e1  xor     eax, eax
0x1800453e3  jmp     short loc_1800453F3
0x1800453e5  mov     rcx, [rsp+0A8h+var_78]
0x1800453ea  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1800453ef  mov     eax, dword ptr [rsp+0A8h+SourceSize]
0x1800453f3  mov     rcx, [rsp+0A8h+var_30]
0x1800453f8  xor     rcx, rsp; StackCookie
0x1800453fb  call    __security_check_cookie
0x180045400  mov     rbx, [rsp+0A8h+arg_18]
0x180045408  add     rsp, 80h
0x18004540f  pop     r15
0x180045411  pop     r14
0x180045413  pop     r12
0x180045415  pop     rdi
0x180045416  pop     rsi
0x180045417  retn
```
