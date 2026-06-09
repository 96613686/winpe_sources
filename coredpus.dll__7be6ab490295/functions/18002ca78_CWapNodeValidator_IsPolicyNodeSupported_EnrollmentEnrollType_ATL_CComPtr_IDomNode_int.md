# CWapNodeValidator::IsPolicyNodeSupported(EnrollmentEnrollType,ATL::CComPtr<IDomNode>,int *)

- ea: `0x18002ca78`
- end: `0x18002cdf7`
- name: `?IsPolicyNodeSupported@CWapNodeValidator@@AEAAJW4EnrollmentEnrollType@@V?$CComPtr@UIDomNode@@@ATL@@PEAH@Z`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d810`

## callees

- `0x1800107a0`
- `0x1800110bc`
- `0x180011758`
- `0x1800117c4`
- `0x1800118a0`
- `0x1800118e4`
- `0x180011d9c`
- `0x180012b54`
- `0x180014330`
- `0x180022874`
- `0x18002b9b8`
- `0x18002bee8`
- `0x18002ca78`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002cb13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002cb13`
- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x18002ccec`
- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x18002ccec`
- `policymanager!EnterprisePolicyManagerStore_IsValidArea` at `0x18002cc56`
- `policymanager!EnterprisePolicyManagerStore_IsValidArea` at `0x18002cc56`
- `policymanager!EnterprisePolicyManagerStore_IsValidPolicy` at `0x18002cc9f`
- `policymanager!EnterprisePolicyManagerStore_IsValidPolicy` at `0x18002cc9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CWapNodeValidator::IsPolicyNodeSupported(__int64 a1, unsigned int a2, __int64 *a3, int *a4)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, unsigned __int16 **); // rbx
  __int64 v14; // r9
  unsigned int v15; // edi
  unsigned int i; // ebx
  _QWORD *v17; // rcx
  const unsigned __int16 *v18; // rdx
  int IsValidArea; // eax
  __int64 v20; // rdx
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // rdx
  _QWORD *v23; // r8
  _QWORD *v24; // rdx
  int v26; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v27; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v29[176]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v30[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v31; // [rsp+118h] [rbp+18h]
  _QWORD v32[3]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v33; // [rsp+138h] [rbp+38h]
  _BYTE v34[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v35[40]; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v36; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v28[1] = a3;
  v28[0] = 0;
  v27 = 0;
  *a4 = 1;
  v7 = *a3;
  if ( !*a3 )
  {
    v10 = -2147024809;
    v14 = 2147942487LL;
    v11 = 511;
    goto LABEL_43;
  }
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v28,
    0);
  v9 = v8(v7, v28);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 512;
LABEL_8:
    v14 = (unsigned int)v9;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)v14,
      v26);
    goto LABEL_44;
  }
  if ( (unsigned int)_o__wcsicmp(v28[0], L"parm") )
  {
LABEL_5:
    v10 = 0;
    goto LABEL_44;
  }
  v12 = *a3;
  v13 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)*a3 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v27,
    0);
  v9 = v13(v12, &v27);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 514;
    goto LABEL_8;
  }
  IriSegmentReader::IriSegmentReader((IriSegmentReader *)v35, v27);
  std::wstring::wstring(v30);
  std::wstring::wstring(v32);
  v15 = v36;
  PolicyManagerScopeData::PolicyManagerScopeData((PolicyManagerScopeData *)v29);
  if ( v15 < 3 )
    goto LABEL_41;
  for ( i = 0; i < v15; ++i )
  {
    std::wstring::wstring(v34);
    if ( (int)IriSegmentReader::GetNextSegment(v35, v34) < 0 )
    {
      std::wstring::_Tidy_deallocate(v34);
      PolicyManagerScopeData::~PolicyManagerScopeData((PolicyManagerScopeData *)v29);
      std::wstring::_Tidy_deallocate(v32);
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v35);
      goto LABEL_5;
    }
    if ( i == v15 - 2 )
    {
      v17 = v30;
    }
    else
    {
      if ( i != v15 - 1 )
        goto LABEL_18;
      v17 = v32;
    }
    std::wstring::operator=(v17, v34);
LABEL_18:
    std::wstring::_Tidy_deallocate(v34);
  }
  if ( !v30[2] || !v32[2] )
    goto LABEL_41;
  v18 = (const unsigned __int16 *)v30;
  if ( v31 > 7 )
    v18 = (const unsigned __int16 *)v30[0];
  IsValidArea = EnterprisePolicyManagerStore_IsValidArea((struct PolicyManagerScopeData *)v29, v18, a4);
  v10 = IsValidArea;
  if ( IsValidArea < 0 )
  {
    v20 = 545;
    goto LABEL_40;
  }
  if ( !*a4 )
    goto LABEL_41;
  v21 = (const unsigned __int16 *)v32;
  if ( v33 > 7 )
    v21 = (const unsigned __int16 *)v32[0];
  v22 = (const unsigned __int16 *)v30;
  if ( v31 > 7 )
    v22 = (const unsigned __int16 *)v30[0];
  IsValidArea = EnterprisePolicyManagerStore_IsValidPolicy((struct PolicyManagerScopeData *)v29, v22, v21, a4);
  v10 = IsValidArea;
  if ( IsValidArea < 0 )
  {
    v20 = 549;
    goto LABEL_40;
  }
  if ( !*a4 )
    goto LABEL_41;
  v23 = v32;
  if ( v33 > 7 )
    v23 = (_QWORD *)v32[0];
  v24 = v30;
  if ( v31 > 7 )
    v24 = (_QWORD *)v30[0];
  v26 = 0;
  IsValidArea = EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed(a2, v24, v23, a4);
  v10 = IsValidArea;
  if ( IsValidArea >= 0 )
  {
LABEL_41:
    PolicyManagerScopeData::~PolicyManagerScopeData((PolicyManagerScopeData *)v29);
    std::wstring::_Tidy_deallocate(v32);
    std::wstring::_Tidy_deallocate(v30);
    std::wstring::_Tidy_deallocate(v35);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v28);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
    return 0;
  }
  v20 = 552;
LABEL_40:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
    (const char *)(unsigned int)IsValidArea,
    v26);
  PolicyManagerScopeData::~PolicyManagerScopeData((PolicyManagerScopeData *)v29);
  std::wstring::_Tidy_deallocate(v32);
  std::wstring::_Tidy_deallocate(v30);
  std::wstring::_Tidy_deallocate(v35);
LABEL_44:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v28);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
  return v10;
}

```

## disassembly

```asm
0x18002ca78  mov     [rsp-8+arg_0], rbx
0x18002ca7d  push    rbp
0x18002ca7e  push    rsi
0x18002ca7f  push    rdi
0x18002ca80  push    r14
0x18002ca82  push    r15
0x18002ca84  lea     rbp, [rsp-0A0h]
0x18002ca8c  sub     rsp, 1A0h
0x18002ca93  mov     rax, cs:__security_cookie
0x18002ca9a  xor     rax, rsp
0x18002ca9d  mov     [rbp+0C0h+var_30], rax
0x18002caa4  mov     rsi, r9
0x18002caa7  mov     r14, r8
0x18002caaa  mov     r15d, edx
0x18002caad  mov     [rsp+1C0h+var_180], r8
0x18002cab2  mov     [rsp+1C0h+var_188], 0
0x18002cabb  mov     [rsp+1C0h+var_190], 0
0x18002cac4  mov     dword ptr [r9], 1
0x18002cacb  mov     rdi, [r8]
0x18002cace  test    rdi, rdi
0x18002cad1  jz      loc_18002CD8F
0x18002cad7  mov     rax, [rdi]
0x18002cada  mov     rbx, [rax+28h]
0x18002cade  xor     edx, edx
0x18002cae0  lea     rcx, [rsp+1C0h+var_188]
0x18002cae5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002caea  lea     rdx, [rsp+1C0h+var_188]
0x18002caef  mov     rcx, rdi
0x18002caf2  mov     rax, rbx
0x18002caf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cafa  mov     ebx, eax
0x18002cafc  test    eax, eax
0x18002cafe  jns     short loc_18002CB07
0x18002cb00  mov     edx, 200h
0x18002cb05  jmp     short loc_18002CB5B
0x18002cb07  lea     rdx, aParm; "parm"
0x18002cb0e  mov     rcx, [rsp+1C0h+var_188]
0x18002cb13  call    cs:__imp__o__wcsicmp
0x18002cb1a  nop     dword ptr [rax+rax+00h]
0x18002cb1f  test    eax, eax
0x18002cb21  jz      short loc_18002CB2A
0x18002cb23  xor     ebx, ebx
0x18002cb25  jmp     loc_18002CDB0
0x18002cb2a  mov     rdi, [r14]
0x18002cb2d  mov     rax, [rdi]
0x18002cb30  mov     rbx, [rax+50h]
0x18002cb34  xor     edx, edx
0x18002cb36  lea     rcx, [rsp+1C0h+var_190]
0x18002cb3b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002cb40  lea     rdx, [rsp+1C0h+var_190]
0x18002cb45  mov     rcx, rdi
0x18002cb48  mov     rax, rbx
0x18002cb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb50  mov     ebx, eax
0x18002cb52  test    eax, eax
0x18002cb54  jns     short loc_18002CB63
0x18002cb56  mov     edx, 202h
0x18002cb5b  mov     r9d, eax
0x18002cb5e  jmp     loc_18002CD9C
0x18002cb63  mov     rdx, [rsp+1C0h+var_190]; unsigned __int16 *
0x18002cb68  lea     rcx, [rbp+0C0h+var_60]; this
0x18002cb6c  call    ??0IriSegmentReader@@QEAA@PEBG@Z; IriSegmentReader::IriSegmentReader(ushort const *)
0x18002cb71  nop
0x18002cb72  lea     rcx, [rbp+0C0h+var_C0]
0x18002cb76  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb7b  nop
0x18002cb7c  lea     rcx, [rbp+0C0h+var_A0]
0x18002cb80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb85  nop
0x18002cb86  mov     edi, [rbp+0C0h+var_38]
0x18002cb8c  lea     rcx, [rsp+1C0h+var_170]; this
0x18002cb91  call    ??0PolicyManagerScopeData@@QEAA@XZ; PolicyManagerScopeData::PolicyManagerScopeData(void)
0x18002cb96  nop
0x18002cb97  cmp     edi, 3
0x18002cb9a  jb      loc_18002CD44
0x18002cba0  xor     ebx, ebx
0x18002cba2  cmp     ebx, edi
0x18002cba4  jnb     loc_18002CC2A
0x18002cbaa  lea     rcx, [rbp+0C0h+var_80]
0x18002cbae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cbb3  nop
0x18002cbb4  lea     rdx, [rbp+0C0h+var_80]
0x18002cbb8  lea     rcx, [rbp+0C0h+var_60]
0x18002cbbc  call    ?GetNextSegment@IriSegmentReader@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IriSegmentReader::GetNextSegment(std::wstring &)
0x18002cbc1  test    eax, eax
0x18002cbc3  js      short loc_18002CBF3
0x18002cbc5  lea     eax, [rdi-2]
0x18002cbc8  cmp     ebx, eax
0x18002cbca  jnz     short loc_18002CBD2
0x18002cbcc  lea     rcx, [rbp+0C0h+var_C0]
0x18002cbd0  jmp     short loc_18002CBDD
0x18002cbd2  lea     eax, [rdi-1]
0x18002cbd5  cmp     ebx, eax
0x18002cbd7  jnz     short loc_18002CBE6
0x18002cbd9  lea     rcx, [rbp+0C0h+var_A0]
0x18002cbdd  lea     rdx, [rbp+0C0h+var_80]
0x18002cbe1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002cbe6  inc     ebx
0x18002cbe8  lea     rcx, [rbp+0C0h+var_80]; void *
0x18002cbec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cbf1  jmp     short loc_18002CBA2
0x18002cbf3  lea     rcx, [rbp+0C0h+var_80]; void *
0x18002cbf7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cbfc  nop
0x18002cbfd  lea     rcx, [rsp+1C0h+var_170]; this
0x18002cc02  call    ??1PolicyManagerScopeData@@QEAA@XZ; PolicyManagerScopeData::~PolicyManagerScopeData(void)
0x18002cc07  nop
0x18002cc08  lea     rcx, [rbp+0C0h+var_A0]; void *
0x18002cc0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cc11  nop
0x18002cc12  lea     rcx, [rbp+0C0h+var_C0]; void *
0x18002cc16  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cc1b  nop
0x18002cc1c  lea     rcx, [rbp+0C0h+var_60]; void *
0x18002cc20  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cc25  jmp     loc_18002CB23
0x18002cc2a  cmp     [rbp+0C0h+var_B0], 0
0x18002cc2f  jz      loc_18002CD44
0x18002cc35  cmp     [rbp+0C0h+var_90], 0
0x18002cc3a  jz      loc_18002CD44
0x18002cc40  lea     rdx, [rbp+0C0h+var_C0]
0x18002cc44  cmp     [rbp+0C0h+var_A8], 7
0x18002cc49  cmova   rdx, [rbp+0C0h+var_C0]
0x18002cc4e  mov     r8, rsi
0x18002cc51  lea     rcx, [rsp+1C0h+var_170]
0x18002cc56  call    cs:__imp_?EnterprisePolicyManagerStore_IsValidArea@@YAJPEAUPolicyManagerScopeData@@PEBGPEAH@Z; EnterprisePolicyManagerStore_IsValidArea(PolicyManagerScopeData *,ushort const *,int *)
0x18002cc5d  nop     dword ptr [rax+rax+00h]
0x18002cc62  mov     ebx, eax
0x18002cc64  test    eax, eax
0x18002cc66  jns     short loc_18002CC72
0x18002cc68  mov     edx, 221h
0x18002cc6d  jmp     loc_18002CD03
0x18002cc72  cmp     dword ptr [rsi], 0
0x18002cc75  jz      loc_18002CD44
0x18002cc7b  lea     r8, [rbp+0C0h+var_A0]
0x18002cc7f  cmp     [rbp+0C0h+var_88], 7
0x18002cc84  cmova   r8, [rbp+0C0h+var_A0]
0x18002cc89  lea     rdx, [rbp+0C0h+var_C0]
0x18002cc8d  cmp     [rbp+0C0h+var_A8], 7
0x18002cc92  cmova   rdx, [rbp+0C0h+var_C0]
0x18002cc97  mov     r9, rsi
0x18002cc9a  lea     rcx, [rsp+1C0h+var_170]
0x18002cc9f  call    cs:__imp_?EnterprisePolicyManagerStore_IsValidPolicy@@YAJPEAUPolicyManagerScopeData@@PEBG1PEAH@Z; EnterprisePolicyManagerStore_IsValidPolicy(PolicyManagerScopeData *,ushort const *,ushort const *,int *)
0x18002cca6  nop     dword ptr [rax+rax+00h]
0x18002ccab  mov     ebx, eax
0x18002ccad  test    eax, eax
0x18002ccaf  jns     short loc_18002CCB8
0x18002ccb1  mov     edx, 225h
0x18002ccb6  jmp     short loc_18002CD03
0x18002ccb8  cmp     dword ptr [rsi], 0
0x18002ccbb  jz      loc_18002CD44
0x18002ccc1  lea     r8, [rbp+0C0h+var_A0]
0x18002ccc5  cmp     [rbp+0C0h+var_88], 7
0x18002ccca  cmova   r8, [rbp+0C0h+var_A0]
0x18002cccf  lea     rdx, [rbp+0C0h+var_C0]
0x18002ccd3  cmp     [rbp+0C0h+var_A8], 7
0x18002ccd8  cmova   rdx, [rbp+0C0h+var_C0]
0x18002ccdd  mov     qword ptr [rsp+1C0h+var_1A0], 0; int
0x18002cce6  mov     r9, rsi
0x18002cce9  mov     ecx, r15d
0x18002ccec  call    cs:__imp_?EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed@@YAJW4EnrollmentEnrollType@@PEBG1PEAHPEAPEAE@Z; EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed(EnrollmentEnrollType,ushort const *,ushort const *,int *,uchar * *)
0x18002ccf3  nop     dword ptr [rax+rax+00h]
0x18002ccf8  mov     ebx, eax
0x18002ccfa  test    eax, eax
0x18002ccfc  jns     short loc_18002CD44
0x18002ccfe  mov     edx, 228h; void *
0x18002cd03  mov     r9d, eax; char *
0x18002cd06  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002cd0d  mov     rcx, [rbp+0C8h]; this
0x18002cd14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd19  nop
0x18002cd1a  lea     rcx, [rsp+1C0h+var_170]; this
0x18002cd1f  call    ??1PolicyManagerScopeData@@QEAA@XZ; PolicyManagerScopeData::~PolicyManagerScopeData(void)
0x18002cd24  nop
0x18002cd25  lea     rcx, [rbp+0C0h+var_A0]; void *
0x18002cd29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd2e  nop
0x18002cd2f  lea     rcx, [rbp+0C0h+var_C0]; void *
0x18002cd33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd38  nop
0x18002cd39  lea     rcx, [rbp+0C0h+var_60]; void *
0x18002cd3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd42  jmp     short loc_18002CDB0
0x18002cd44  lea     rcx, [rsp+1C0h+var_170]; this
0x18002cd49  call    ??1PolicyManagerScopeData@@QEAA@XZ; PolicyManagerScopeData::~PolicyManagerScopeData(void)
0x18002cd4e  nop
0x18002cd4f  lea     rcx, [rbp+0C0h+var_A0]; void *
0x18002cd53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd58  nop
0x18002cd59  lea     rcx, [rbp+0C0h+var_C0]; void *
0x18002cd5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd62  nop
0x18002cd63  lea     rcx, [rbp+0C0h+var_60]; void *
0x18002cd67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd6c  nop
0x18002cd6d  lea     rcx, [rsp+1C0h+var_190]
0x18002cd72  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cd77  nop
0x18002cd78  lea     rcx, [rsp+1C0h+var_188]
0x18002cd7d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cd82  nop
0x18002cd83  mov     rcx, r14
0x18002cd86  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002cd8b  xor     eax, eax
0x18002cd8d  jmp     short loc_18002CDD0
0x18002cd8f  mov     ebx, 80070057h
0x18002cd94  mov     r9d, ebx; char *
0x18002cd97  mov     edx, 1FFh; void *
0x18002cd9c  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002cda3  mov     rcx, [rbp+0C8h]; this
0x18002cdaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdaf  nop
0x18002cdb0  lea     rcx, [rsp+1C0h+var_190]
0x18002cdb5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cdba  nop
0x18002cdbb  lea     rcx, [rsp+1C0h+var_188]
0x18002cdc0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cdc5  nop
0x18002cdc6  mov     rcx, r14
0x18002cdc9  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002cdce  mov     eax, ebx
0x18002cdd0  mov     rcx, [rbp+0C0h+var_30]
0x18002cdd7  xor     rcx, rsp; StackCookie
0x18002cdda  call    __security_check_cookie
0x18002cddf  mov     rbx, [rsp+1C0h+arg_0]
0x18002cde7  add     rsp, 1A0h
0x18002cdee  pop     r15
0x18002cdf0  pop     r14
0x18002cdf2  pop     rdi
0x18002cdf3  pop     rsi
0x18002cdf4  pop     rbp
0x18002cdf5  retn
```
