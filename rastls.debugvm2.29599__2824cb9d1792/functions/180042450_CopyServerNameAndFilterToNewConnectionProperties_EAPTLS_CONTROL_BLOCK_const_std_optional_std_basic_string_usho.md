# CopyServerNameAndFilterToNewConnectionProperties(_EAPTLS_CONTROL_BLOCK const &,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,_EAPTLS_CONN_PROPERTIES_V1 *)

- ea: `0x180042450`
- end: `0x180042750`
- name: `?CopyServerNameAndFilterToNewConnectionProperties@@YAJAEBU_EAPTLS_CONTROL_BLOCK@@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002b4fc`

## callees

- `0x180002310`
- `0x18001ea34`
- `0x18002756c`
- `0x18002b798`
- `0x18002b7d8`
- `0x18003360c`
- `0x180035680`
- `0x180042450`
- `0x18004ab64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004254b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800425aa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004254b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800425aa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180042653`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180042653`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800424cc`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800424cc`

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
0x180042450  mov     [rsp+arg_18], rbx
0x180042455  push    rsi
0x180042456  push    rdi
0x180042457  push    r12
0x180042459  push    r14
0x18004245b  push    r15
0x18004245d  sub     rsp, 80h
0x180042464  mov     rax, cs:__security_cookie
0x18004246b  xor     rax, rsp
0x18004246e  mov     [rsp+0A8h+var_30], rax
0x180042473  mov     rbx, rdx
0x180042476  mov     r15, rcx
0x180042479  mov     [rsp+0A8h+var_78], rdx
0x18004247e  mov     eax, [r8+0Ch]
0x180042482  lea     rdx, [rax+1]
0x180042486  lea     rdx, [rax+rdx*2]
0x18004248a  lea     rsi, [r8+rdx*8]
0x18004248e  mov     rdx, [rcx+220h]
0x180042495  mov     eax, [rdx+0Ch]
0x180042498  lea     r8, [rax+1]
0x18004249c  lea     r8, [rax+r8*2]
0x1800424a0  lea     r8, [rdx+r8*8]
0x1800424a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800424a8  xor     r12d, r12d
0x1800424ab  inc     rax
0x1800424ae  cmp     [r8+rax*2], r12w
0x1800424b3  jnz     short loc_1800424AB
0x1800424b5  test    eax, eax
0x1800424b7  jz      loc_180042603
0x1800424bd  mov     r14d, eax
0x1800424c0  inc     eax
0x1800424c2  mov     edi, eax
0x1800424c4  mov     r9d, r14d
0x1800424c7  mov     edx, eax
0x1800424c9  mov     rcx, rsi
0x1800424cc  call    cs:__imp__o_wcsncpy_s
0x1800424d2  test    eax, eax
0x1800424d4  jz      short loc_180042503
0x1800424d6  mov     rcx, [rsp+0A8h]; this
0x1800424de  mov     r9d, eax; char *
0x1800424e1  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x1800424e8  mov     edx, 3Bh ; ';'; void *
0x1800424ed  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800424f2  mov     edi, eax
0x1800424f4  mov     rcx, rbx
0x1800424f7  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1800424fc  mov     eax, edi
0x1800424fe  jmp     loc_18004272B
0x180042503  lea     rdi, [rsi+rdi*2]
0x180042507  cmp     [rbx+20h], r12b
0x18004250b  jz      loc_1800426AB
0x180042511  mov     rcx, rbx
0x180042514  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180042519  cmp     [rax+10h], r12
0x18004251d  jbe     loc_1800426AB
0x180042523  mov     rcx, rbx
0x180042526  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x18004252b  mov     rdx, rax
0x18004252e  lea     rcx, [rsp+0A8h+var_70]
0x180042533  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180042538  lea     rsi, [rsi+r14*2]
0x18004253c  lea     r8, asc_180081BE0; ";"
0x180042543  mov     edx, 2
0x180042548  mov     rcx, rsi
0x18004254b  call    cs:__imp__o_wcscat_s
0x180042551  test    eax, eax
0x180042553  jz      short loc_18004258D
0x180042555  mov     rcx, [rsp+0A8h]; this
0x18004255d  mov     r9d, eax; char *
0x180042560  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x180042567  mov     edx, 43h ; 'C'; void *
0x18004256c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042571  mov     edi, eax
0x180042573  lea     rcx, [rsp+0A8h+var_70]
0x180042578  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004257d  nop
0x18004257e  mov     rcx, rbx
0x180042581  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180042586  mov     eax, edi
0x180042588  jmp     loc_18004272B
0x18004258d  lea     rcx, [rsi+2]
0x180042591  lea     r8, [rsp+0A8h+var_70]
0x180042596  cmp     [rsp+0A8h+var_58], 7
0x18004259c  cmova   r8, [rsp+0A8h+var_70]
0x1800425a2  mov     rdx, [rsp+0A8h+var_60]
0x1800425a7  inc     rdx
0x1800425aa  call    cs:__imp__o_wcscat_s
0x1800425b0  test    eax, eax
0x1800425b2  jz      short loc_1800425EC
0x1800425b4  mov     rcx, [rsp+0A8h]; this
0x1800425bc  mov     r9d, eax; char *
0x1800425bf  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x1800425c6  mov     edx, 45h ; 'E'; void *
0x1800425cb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800425d0  mov     edi, eax
0x1800425d2  lea     rcx, [rsp+0A8h+var_70]
0x1800425d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800425dc  nop
0x1800425dd  mov     rcx, rbx
0x1800425e0  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1800425e5  mov     eax, edi
0x1800425e7  jmp     loc_18004272B
0x1800425ec  mov     rax, [rsp+0A8h+var_60]
0x1800425f1  lea     rdi, [rdi+rax*2]
0x1800425f5  add     rdi, 2
0x1800425f9  lea     rcx, [rsp+0A8h+var_70]
0x1800425fe  jmp     loc_1800426A6
0x180042603  mov     rdi, rsi
0x180042606  cmp     [rbx+20h], r12b
0x18004260a  jz      loc_1800426AB
0x180042610  mov     rcx, rbx
0x180042613  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180042618  cmp     [rax+10h], r12
0x18004261c  jbe     loc_1800426AB
0x180042622  mov     rcx, rbx
0x180042625  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x18004262a  mov     rdx, rax
0x18004262d  lea     rcx, [rsp+0A8h+var_50]
0x180042632  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180042637  lea     r8, [rsp+0A8h+var_50]
0x18004263c  cmp     [rsp+0A8h+var_38], 7
0x180042642  cmova   r8, [rsp+0A8h+var_50]
0x180042648  mov     rdx, [rsp+0A8h+var_40]
0x18004264d  inc     rdx
0x180042650  mov     rcx, rsi
0x180042653  call    cs:__imp__o_wcscpy_s
0x180042659  test    eax, eax
0x18004265b  jz      short loc_180042695
0x18004265d  mov     rcx, [rsp+0A8h]; this
0x180042665  mov     r9d, eax; char *
0x180042668  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x18004266f  mov     edx, 4Eh ; 'N'; void *
0x180042674  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042679  mov     edi, eax
0x18004267b  lea     rcx, [rsp+0A8h+var_50]
0x180042680  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042685  nop
0x180042686  mov     rcx, rbx
0x180042689  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x18004268e  mov     eax, edi
0x180042690  jmp     loc_18004272B
0x180042695  mov     rax, [rsp+0A8h+var_40]
0x18004269a  inc     rax
0x18004269d  lea     rdi, [rsi+rax*2]
0x1800426a1  lea     rcx, [rsp+0A8h+var_50]
0x1800426a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800426ab  mov     [rsp+0A8h+Source], r12
0x1800426b0  mov     dword ptr [rsp+0A8h+SourceSize], r12d; unsigned int
0x1800426b5  lea     r8, [rsp+0A8h+SourceSize]; unsigned int *
0x1800426ba  lea     rdx, [rsp+0A8h+Source]; unsigned __int8 **
0x1800426bf  mov     rcx, [r15+220h]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x1800426c6  call    ?isCertFilterLogicPresentInV1@@YAHPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAEPEAK@Z; isCertFilterLogicPresentInV1(_EAPTLS_CONN_PROPERTIES_V1 *,uchar * *,ulong *)
0x1800426cb  test    eax, eax
0x1800426cd  jz      short loc_180042711
0x1800426cf  mov     edx, dword ptr [rsp+0A8h+SourceSize]; DestinationSize
0x1800426d3  mov     r9d, edx; SourceSize
0x1800426d6  mov     r8, [rsp+0A8h+Source]; Source
0x1800426db  mov     rcx, rdi; Destination
0x1800426de  call    memcpy_s
0x1800426e3  test    eax, eax
0x1800426e5  jz      short loc_180042711
0x1800426e7  mov     rcx, [rsp+0A8h]; this
0x1800426ef  mov     r9d, eax; char *
0x1800426f2  lea     r8, aOnecoreuapNetR_4; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x1800426f9  mov     edx, 59h ; 'Y'; void *
0x1800426fe  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042703  mov     edi, eax
0x180042705  mov     rcx, rbx
0x180042708  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x18004270d  mov     eax, edi
0x18004270f  jmp     short loc_18004272B
0x180042711  mov     rcx, rbx
0x180042714  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180042719  xor     eax, eax
0x18004271b  jmp     short loc_18004272B
0x18004271d  mov     rcx, [rsp+0A8h+var_78]
0x180042722  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180042727  mov     eax, dword ptr [rsp+0A8h+SourceSize]
0x18004272b  mov     rcx, [rsp+0A8h+var_30]
0x180042730  xor     rcx, rsp; StackCookie
0x180042733  call    __security_check_cookie
0x180042738  mov     rbx, [rsp+0A8h+arg_18]
0x180042740  add     rsp, 80h
0x180042747  pop     r15
0x180042749  pop     r14
0x18004274b  pop     r12
0x18004274d  pop     rdi
0x18004274e  pop     rsi
0x18004274f  retn
```
