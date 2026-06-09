# Rdp::Stack::Driver::CDriverControl3::LookupEncoderDllName(_GUID const &)

- ea: `0x1800140a8`
- end: `0x1800143b8`
- name: `?LookupEncoderDllName@CDriverControl3@Driver@Stack@Rdp@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014e40`

## callees

- `0x1800036f0`
- `0x180007db4`
- `0x180008380`
- `0x18000cf28`
- `0x18000d590`
- `0x18000ef54`
- `0x18001261c`
- `0x180012a48`
- `0x180012af8`
- `0x180012bf0`
- `0x180012f1c`
- `0x180013128`
- `0x180013e3c`
- `0x180013f70`
- `0x1800140a8`
- `0x18002834c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001423e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001423e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001414d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001414d`

## string_xrefs

- `0x18001411b`: `Failed to retrieve PKEY_ProtocolName property`
- `0x180014319`: `RdpAvenc.dll`
- `0x18001432f`: `RdpAvenc.dll`
- `0x180014351`: `Failed to set PKEY_EncodingDllName property`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Rdp::Stack::Driver::CDriverControl3::LookupEncoderDllName(__int64 a1, __int64 a2, const GUID *a3)
{
  unsigned int WString; // eax
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  const WCHAR *v11; // rbx
  HKEY *v12; // rax
  LSTATUS v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  bool v16; // sf
  __int64 v17; // rax
  _WORD *v18; // rbx
  unsigned int v19; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  wil::reg::reg_view_details *phkResulta; // [rsp+20h] [rbp-E0h]
  const char *v23; // [rsp+28h] [rbp-D8h]
  const char *v24; // [rsp+28h] [rbp-D8h]
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  int v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h]
  int v28[4]; // [rsp+50h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h]
  _OWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v31[2]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[32]; // [rsp+D0h] [rbp-30h] BYREF
  int v34[8]; // [rsp+F0h] [rbp-10h] BYREF
  OLECHAR sz[40]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v27 = a2;
  v30[0] = 0;
  v30[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v30[0]) = 0;
  WString = Rdp::Utils::Props::IPropertyStore_GetWString(*(_QWORD *)(a1 + 88), &PKEY_ProtocolName, v30);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3D9,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)WString,
    (int)"Failed to retrieve PKEY_ProtocolName property",
    v23);
  if ( !StringFromGUID2(a3, sz, 40) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3DC,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
      (const char *)0x80070057LL,
      phkResult);
  memset(v31, 0, sizeof(v31));
  v7 = -1;
  do
    ++v7;
  while ( sz[v7] );
  std::wstring::_Construct<1,unsigned short const *>(v31, sz);
  v8 = std::operator+<unsigned short>((int)v34);
  v9 = std::operator+<unsigned short>(v33, v8);
  std::wstring::wstring(lpSubKey, v10, v9, v31);
  std::wstring::_Tidy_deallocate(v33);
  std::wstring::_Tidy_deallocate(v34);
  std::wstring::_Tidy_deallocate(v31);
  v25 = 0;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  v11 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v11 = lpSubKey[0];
  v12 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v25);
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, v12);
  v16 = v13 < 0;
  if ( v13 > 0 )
    v16 = 1;
  if ( v16 )
  {
    v17 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_RdpAvenc.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_RdpAvenc.Data1 )
      v17 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_RdpAvenc.Data4;
    if ( !v17 )
    {
      if ( *(_QWORD *)(a2 + 24) < 0xCu )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          a2,
          12,
          v15,
          L"RdpAvenc.dll");
      }
      else
      {
        v18 = *(_WORD **)a2;
        *(_QWORD *)(a2 + 16) = 12;
        memmove_0(v18, L"RdpAvenc.dll", 0x18u);
        v18[12] = 0;
      }
    }
  }
  else
  {
    *(_OWORD *)v28 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v28[0]) = 0;
    *(_QWORD *)v26 = v25;
    LODWORD(phkResulta) = 268435462;
    wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::get_value_with_type<std::wstring,wil::err_exception_policy>(
      (int)v26,
      v14,
      v15,
      (int)v28,
      phkResulta);
    if ( (int *)a2 != v28 )
    {
      std::wstring::_Tidy_deallocate(a2);
      *(_OWORD *)a2 = *(_OWORD *)v28;
      *(__m128i *)(a2 + 16) = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v28[0]) = 0;
    }
    std::wstring::_Tidy_deallocate(v28);
  }
  v19 = Rdp::Utils::Props::IPropertyStore_SetWString(*(_QWORD *)(a1 + 88), v14, a2);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3FC,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v19,
    (int)"Failed to set PKEY_EncodingDllName property",
    v24);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
  std::wstring::_Tidy_deallocate(lpSubKey);
  std::wstring::_Tidy_deallocate(v30);
  return a2;
}

```

## disassembly

```asm
0x1800140a8  mov     [rsp-8+arg_18], rbx
0x1800140ad  push    rbp
0x1800140ae  push    rsi
0x1800140af  push    rdi
0x1800140b0  push    r14
0x1800140b2  push    r15
0x1800140b4  lea     rbp, [rsp-70h]
0x1800140b9  sub     rsp, 170h
0x1800140c0  mov     rax, cs:__security_cookie
0x1800140c7  xor     rax, rsp
0x1800140ca  mov     [rbp+90h+var_30], rax
0x1800140ce  mov     rsi, r8
0x1800140d1  mov     rdi, rdx
0x1800140d4  mov     r14, rcx
0x1800140d7  mov     [rsp+190h+var_148], rdx
0x1800140dc  xor     r15d, r15d
0x1800140df  mov     [rsp+190h+var_160], r15d
0x1800140e4  xorps   xmm0, xmm0
0x1800140e7  movups  [rsp+190h+var_120], xmm0
0x1800140ec  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800140f4  movdqu  [rbp+90h+var_110], xmm1
0x1800140f9  mov     word ptr [rsp+190h+var_120], r15w
0x1800140ff  lea     r8, [rsp+190h+var_120]
0x180014104  lea     rdx, PKEY_ProtocolName
0x18001410b  mov     rcx, [rcx+58h]
0x18001410f  call    ?IPropertyStore_GetWString@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Rdp::Utils::Props::IPropertyStore_GetWString(IPropertyStore *,_tagpropertykey const &,std::wstring &)
0x180014114  mov     rcx, [rbp+98h]; this
0x18001411b  lea     rdx, aFailedToRetrie_7; "Failed to retrieve PKEY_ProtocolName pr"...
0x180014122  mov     [rsp+190h+phkResult], rdx; int
0x180014127  mov     r9d, eax; char *
0x18001412a  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180014131  mov     edx, 3D9h; void *
0x180014136  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001413b  mov     rbx, [rbp+98h]
0x180014142  lea     r8d, [r15+28h]; cchMax
0x180014146  lea     rdx, [rbp+90h+sz]; lpsz
0x18001414a  mov     rcx, rsi; rguid
0x18001414d  call    cs:__imp_StringFromGUID2
0x180014153  test    eax, eax
0x180014155  jnz     short loc_180014172
0x180014157  mov     r9d, 80070057h; char *
0x18001415d  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180014164  mov     edx, 3DCh; void *
0x180014169  mov     rcx, rbx; this
0x18001416c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014172  xorps   xmm0, xmm0
0x180014175  movups  [rbp+90h+var_100], xmm0
0x180014179  xorps   xmm1, xmm1
0x18001417c  movdqu  [rbp+90h+var_F0], xmm1
0x180014181  lea     rax, [rbp+90h+sz]
0x180014185  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014189  inc     r8
0x18001418c  cmp     [rax+r8*2], r15w
0x180014191  jnz     short loc_180014189
0x180014193  lea     rdx, [rbp+90h+sz]
0x180014197  lea     rcx, [rbp+90h+var_100]
0x18001419b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800141a0  nop
0x1800141a1  lea     r8, [rsp+190h+var_120]
0x1800141a6  lea     rcx, [rbp+90h+var_A0]; int
0x1800141aa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800141af  nop
0x1800141b0  mov     rdx, rax
0x1800141b3  lea     rcx, [rbp+90h+var_C0]
0x1800141b7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800141bc  nop
0x1800141bd  lea     r9, [rbp+90h+var_100]
0x1800141c1  mov     r8, rax
0x1800141c4  lea     rcx, [rbp+90h+lpSubKey]
0x1800141c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800141cd  nop
0x1800141ce  lea     rcx, [rbp+90h+var_C0]
0x1800141d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800141d7  nop
0x1800141d8  lea     rcx, [rbp+90h+var_A0]
0x1800141dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800141e1  nop
0x1800141e2  lea     rcx, [rbp+90h+var_100]
0x1800141e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800141eb  mov     [rsp+190h+var_158], r15
0x1800141f0  xorps   xmm0, xmm0
0x1800141f3  movups  xmmword ptr [rdi], xmm0
0x1800141f6  mov     [rdi+10h], r15
0x1800141fa  mov     qword ptr [rdi+18h], 7
0x180014202  mov     [rdi], r15w
0x180014206  mov     [rsp+190h+var_160], 5
0x18001420e  lea     rbx, [rbp+90h+lpSubKey]
0x180014212  cmp     [rbp+90h+var_C8], 7
0x180014217  cmova   rbx, [rbp+90h+lpSubKey]
0x18001421c  lea     rcx, [rsp+190h+var_158]
0x180014221  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180014226  mov     [rsp+190h+phkResult], rax; phkResult
0x18001422b  mov     r9d, 20019h; samDesired
0x180014231  xor     r8d, r8d; ulOptions
0x180014234  mov     rdx, rbx; lpSubKey
0x180014237  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001423e  call    cs:__imp_RegOpenKeyExW
0x180014244  test    eax, eax
0x180014246  jle     short loc_180014252
0x180014248  movzx   eax, ax
0x18001424b  or      eax, 80070000h
0x180014250  test    eax, eax
0x180014252  js      loc_1800142E9
0x180014258  mov     rcx, [rsp+190h+var_158]
0x18001425d  xorps   xmm0, xmm0
0x180014260  movups  xmmword ptr [rsp+190h+var_140], xmm0
0x180014265  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001426d  movdqu  [rsp+190h+var_130], xmm1
0x180014273  mov     word ptr [rsp+190h+var_140], r15w
0x180014279  mov     [rsp+190h+var_160], 15h
0x180014281  mov     qword ptr [rsp+190h+var_150], rcx
0x180014286  mov     dword ptr [rsp+190h+phkResult], 10000006h; wil::reg::reg_view_details *
0x18001428e  lea     r9, [rsp+190h+var_140]; int
0x180014293  lea     rcx, [rsp+190h+var_150]; int
0x180014298  call    ??$get_value_with_type@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uerr_exception_policy@wil@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@AEBAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::get_value_with_type<std::wstring,wil::err_exception_policy>(ushort const *,ushort const *,std::wstring &,ulong)
0x18001429d  nop
0x18001429e  mov     [rsp+190h+var_160], 0Dh
0x1800142a6  lea     rax, [rsp+190h+var_140]
0x1800142ab  cmp     rdi, rax
0x1800142ae  jz      short loc_1800142DD
0x1800142b0  mov     rcx, rdi
0x1800142b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800142b8  movups  xmm0, xmmword ptr [rsp+190h+var_140]
0x1800142bd  movups  xmmword ptr [rdi], xmm0
0x1800142c0  movups  xmm1, [rsp+190h+var_130]
0x1800142c5  movups  xmmword ptr [rdi+10h], xmm1
0x1800142c9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800142d1  movdqu  [rsp+190h+var_130], xmm0
0x1800142d7  mov     word ptr [rsp+190h+var_140], r15w
0x1800142dd  lea     rcx, [rsp+190h+var_140]
0x1800142e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800142e7  jmp     short loc_18001433E
0x1800142e9  mov     rax, [rsi]
0x1800142ec  sub     rax, qword ptr cs:GUID_RdpAvenc.Data1
0x1800142f3  jnz     short loc_180014300
0x1800142f5  mov     rax, [rsi+8]
0x1800142f9  sub     rax, qword ptr cs:GUID_RdpAvenc.Data4
0x180014300  test    rax, rax
0x180014303  jnz     short loc_18001433E
0x180014305  lea     edx, [rax+0Ch]
0x180014308  cmp     [rdi+18h], rdx
0x18001430c  jb      short loc_18001432F
0x18001430e  mov     rbx, [rdi]
0x180014311  mov     [rdi+10h], rdx
0x180014315  lea     r8d, [rax+18h]; Size
0x180014319  lea     rdx, aRdpavencDll; "RdpAvenc.dll"
0x180014320  mov     rcx, rbx; void *
0x180014323  call    memmove_0
0x180014328  mov     [rbx+18h], r15w
0x18001432d  jmp     short loc_18001433E
0x18001432f  lea     r9, aRdpavencDll; "RdpAvenc.dll"
0x180014336  mov     rcx, rdi
0x180014339  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001433e  mov     r8, rdi
0x180014341  mov     rcx, [r14+58h]
0x180014345  call    ?IPropertyStore_SetWString@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Rdp::Utils::Props::IPropertyStore_SetWString(IPropertyStore *,_tagpropertykey const &,std::wstring const &)
0x18001434a  mov     rcx, [rbp+98h]; this
0x180014351  lea     rdx, aFailedToSetPke_42; "Failed to set PKEY_EncodingDllName prop"...
0x180014358  mov     [rsp+190h+phkResult], rdx; int
0x18001435d  mov     r9d, eax; char *
0x180014360  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180014367  mov     edx, 3FCh; void *
0x18001436c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014371  nop
0x180014372  lea     rcx, [rsp+190h+var_158]
0x180014377  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001437c  nop
0x18001437d  lea     rcx, [rbp+90h+lpSubKey]
0x180014381  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014386  nop
0x180014387  lea     rcx, [rsp+190h+var_120]
0x18001438c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014391  mov     rax, rdi
0x180014394  mov     rcx, [rbp+90h+var_30]
0x180014398  xor     rcx, rsp; StackCookie
0x18001439b  call    __security_check_cookie
0x1800143a0  mov     rbx, [rsp+190h+arg_18]
0x1800143a8  add     rsp, 170h
0x1800143af  pop     r15
0x1800143b1  pop     r14
0x1800143b3  pop     rdi
0x1800143b4  pop     rsi
0x1800143b5  pop     rbp
0x1800143b6  retn
```
