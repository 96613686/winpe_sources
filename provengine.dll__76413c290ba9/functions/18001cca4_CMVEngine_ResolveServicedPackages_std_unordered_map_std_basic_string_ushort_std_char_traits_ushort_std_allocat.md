# CMVEngine::ResolveServicedPackages(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>> const &)

- ea: `0x18001cca4`
- end: `0x18001cf77`
- name: `?ResolveServicedPackages@CMVEngine@@AEAAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@3@@Z`
- size: `723`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180014cf8`

## callees

- `0x1800018ec`
- `0x1800098dc`
- `0x18000f840`
- `0x18001cca4`
- `0x1800224cc`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ccfa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cd3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ce41`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cedc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ccfa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cd3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ce41`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cedc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cda5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cda5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CMVEngine::ResolveServicedPackages(__int64 a1, LPVOID *a2, _QWORD *a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  __int64 v7; // rax
  bool v8; // cc
  HRESULT v9; // eax
  unsigned int v10; // edi
  LPVOID v11; // rcx
  LPVOID v13; // rdi
  __int64 v14; // r14
  _QWORD *v15; // rax
  int v16; // edi
  __int64 v17; // r9
  __int64 *v18; // rax
  LPVOID v19; // rdi
  __int64 v20; // r14
  _QWORD *v21; // rax
  int v22; // edi
  __int64 v23; // r9
  __int64 *v24; // rbx
  LPVOID v25; // rcx
  int ppv; // [rsp+20h] [rbp-78h]
  int v27; // [rsp+30h] [rbp-68h] BYREF
  LPVOID v28; // [rsp+38h] [rbp-60h] BYREF
  int v29; // [rsp+40h] [rbp-58h]
  int v30; // [rsp+44h] [rbp-54h]
  unsigned __int64 v31; // [rsp+50h] [rbp-48h]
  __int64 *v32; // [rsp+58h] [rbp-40h] BYREF
  int v33; // [rsp+60h] [rbp-38h]
  int v34; // [rsp+64h] [rbp-34h]
  unsigned __int64 v35; // [rsp+70h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v5 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 16LL))(*a3, &v32);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
    a2,
    &v28,
    v5);
  if ( v35 >= 8 )
    operator delete(v32);
  v6 = v28;
  if ( v28 == *a2 )
    return 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 24LL))(*a3, &v28);
  ProvPackage::PackageVersion::PackageVersion(&v32, v7);
  if ( v31 >= 8 )
    operator delete(v28);
  ProvPackage::PackageVersion::PackageVersion(&v28, v6 + 6);
  v8 = (int)v32 <= (int)v28;
  if ( (_DWORD)v32 == (_DWORD)v28 )
  {
    v8 = SHIDWORD(v32) <= SHIDWORD(v28);
    if ( HIDWORD(v32) == HIDWORD(v28) )
    {
      v8 = v33 <= v29;
      if ( v33 == v29 )
        v8 = v34 <= v30;
    }
  }
  if ( v8 )
    return 0;
  v28 = 0;
  v9 = CoCreateInstance(
         &GUID_5b89deeb_4df1_4cf6_9979_c79185cb95a0,
         0,
         1u,
         &GUID_9051683d_92ab_4ffd_bb73_1f80a11ae5c2,
         &v28);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v13 = v28;
    v14 = *(_QWORD *)v28;
    v15 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 16LL))(*a3, &v32);
    if ( v15[3] >= 8u )
      v15 = (_QWORD *)*v15;
    v16 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, const wchar_t *))(v14 + 56))(
            v13,
            v15,
            L"EnterpriseModernAppManagement");
    if ( v35 >= 8 )
      operator delete(v32);
    if ( v16 < 0 && (unsigned int)dword_18005A000 > 2 )
    {
      v27 = v16;
      v18 = v6 + 2;
      if ( v6[5] >= 8u )
        v18 = (__int64 *)*v18;
      v32 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)&dword_18005A000,
        (__int64)&byte_18004F15F,
        0,
        v17,
        &v32,
        (__int64)&v27);
    }
    v19 = v28;
    v20 = *(_QWORD *)v28;
    v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 16LL))(*a3, &v32);
    if ( v21[3] >= 8u )
      v21 = (_QWORD *)*v21;
    v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(v20 + 40))(v19, v21);
    if ( v35 >= 8 )
      operator delete(v32);
    if ( v22 < 0 && (unsigned int)dword_18005A000 > 2 )
    {
      v27 = v22;
      v24 = v6 + 2;
      if ( (unsigned __int64)v24[3] >= 8 )
        v24 = (__int64 *)*v24;
      v32 = v24;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)&dword_18005A000,
        (__int64)&unk_18004E840,
        0,
        v23,
        &v32,
        (__int64)&v27);
    }
    v25 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x65E,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
    (const char *)(unsigned int)v9,
    ppv);
  v11 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return v10;
}

```

## disassembly

```asm
0x18001cca4  mov     [rsp+arg_0], rbx
0x18001cca9  push    rsi
0x18001ccaa  push    rdi
0x18001ccab  push    r14
0x18001ccad  sub     rsp, 80h
0x18001ccb4  mov     rax, cs:__security_cookie
0x18001ccbb  xor     rax, rsp
0x18001ccbe  mov     [rsp+98h+var_20], rax
0x18001ccc3  mov     rsi, r8
0x18001ccc6  mov     rdi, rdx
0x18001ccc9  mov     rcx, [r8]
0x18001cccc  mov     rax, [rcx]
0x18001cccf  lea     rdx, [rsp+98h+var_40]
0x18001ccd4  mov     rax, [rax+10h]
0x18001ccd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccdd  mov     r8, rax
0x18001cce0  lea     rdx, [rsp+98h+var_60]
0x18001cce5  mov     rcx, rdi
0x18001cce8  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18001cced  cmp     [rsp+98h+var_28], 8
0x18001ccf3  jb      short loc_18001CD00
0x18001ccf5  mov     rcx, [rsp+98h+var_40]
0x18001ccfa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001cd00  mov     rbx, [rsp+98h+var_60]
0x18001cd05  cmp     rbx, [rdi]
0x18001cd08  jz      loc_18001CF53
0x18001cd0e  mov     rcx, [rsi]
0x18001cd11  mov     rax, [rcx]
0x18001cd14  lea     rdx, [rsp+98h+var_60]
0x18001cd19  mov     rax, [rax+18h]
0x18001cd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd22  nop
0x18001cd23  mov     rdx, rax
0x18001cd26  lea     rcx, [rsp+98h+var_40]
0x18001cd2b  call    ??0PackageVersion@ProvPackage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProvPackage::PackageVersion::PackageVersion(std::wstring const &)
0x18001cd30  nop
0x18001cd31  cmp     [rsp+98h+var_48], 8
0x18001cd37  jb      short loc_18001CD44
0x18001cd39  mov     rcx, [rsp+98h+var_60]
0x18001cd3e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001cd44  lea     rdx, [rbx+30h]
0x18001cd48  lea     rcx, [rsp+98h+var_60]
0x18001cd4d  call    ??0PackageVersion@ProvPackage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProvPackage::PackageVersion::PackageVersion(std::wstring const &)
0x18001cd52  mov     eax, dword ptr [rsp+98h+var_60]
0x18001cd56  cmp     dword ptr [rsp+98h+var_40], eax
0x18001cd5a  jnz     short loc_18001CD78
0x18001cd5c  mov     eax, dword ptr [rsp+98h+var_60+4]
0x18001cd60  cmp     dword ptr [rsp+98h+var_40+4], eax
0x18001cd64  jnz     short loc_18001CD78
0x18001cd66  mov     eax, [rsp+98h+var_58]
0x18001cd6a  cmp     [rsp+98h+var_38], eax
0x18001cd6e  jnz     short loc_18001CD78
0x18001cd70  mov     eax, [rsp+98h+var_54]
0x18001cd74  cmp     [rsp+98h+var_34], eax
0x18001cd78  jle     loc_18001CF53
0x18001cd7e  mov     [rsp+98h+var_60], 0
0x18001cd87  lea     rax, [rsp+98h+var_60]
0x18001cd8c  mov     [rsp+98h+ppv], rax; int
0x18001cd91  lea     r9, _GUID_9051683d_92ab_4ffd_bb73_1f80a11ae5c2; riid
0x18001cd98  xor     edx, edx; pUnkOuter
0x18001cd9a  lea     r8d, [rdx+1]; dwClsContext
0x18001cd9e  lea     rcx, _GUID_5b89deeb_4df1_4cf6_9979_c79185cb95a0; rclsid
0x18001cda5  call    cs:__imp_CoCreateInstance
0x18001cdab  mov     edi, eax
0x18001cdad  test    eax, eax
0x18001cdaf  jns     short loc_18001CDF5
0x18001cdb1  mov     rcx, [rsp+98h]; this
0x18001cdb9  mov     r9d, eax; char *
0x18001cdbc  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001cdc3  mov     edx, 65Eh; void *
0x18001cdc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cdcd  nop
0x18001cdce  mov     rcx, [rsp+98h+var_60]
0x18001cdd3  test    rcx, rcx
0x18001cdd6  jz      short loc_18001CDEE
0x18001cdd8  mov     [rsp+98h+var_60], 0
0x18001cde1  mov     rax, [rcx]
0x18001cde4  mov     rax, [rax+10h]
0x18001cde8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cded  nop
0x18001cdee  mov     eax, edi
0x18001cdf0  jmp     loc_18001CF55
0x18001cdf5  mov     rdi, [rsp+98h+var_60]
0x18001cdfa  mov     r14, [rdi]
0x18001cdfd  mov     rcx, [rsi]
0x18001ce00  mov     rax, [rcx]
0x18001ce03  lea     rdx, [rsp+98h+var_40]
0x18001ce08  mov     rax, [rax+10h]
0x18001ce0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce11  nop
0x18001ce12  cmp     qword ptr [rax+18h], 8
0x18001ce17  jb      short loc_18001CE1C
0x18001ce19  mov     rax, [rax]
0x18001ce1c  lea     r8, aEnterprisemode; "EnterpriseModernAppManagement"
0x18001ce23  mov     rdx, rax
0x18001ce26  mov     rcx, rdi
0x18001ce29  mov     rax, [r14+38h]
0x18001ce2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce32  mov     edi, eax
0x18001ce34  cmp     [rsp+98h+var_28], 8
0x18001ce3a  jb      short loc_18001CE47
0x18001ce3c  mov     rcx, [rsp+98h+var_40]
0x18001ce41  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ce47  test    edi, edi
0x18001ce49  jns     short loc_18001CE97
0x18001ce4b  mov     ecx, cs:dword_18005A000
0x18001ce51  cmp     ecx, 2
0x18001ce54  jbe     short loc_18001CE97
0x18001ce56  mov     [rsp+98h+var_68], edi
0x18001ce5a  lea     rax, [rbx+10h]
0x18001ce5e  cmp     qword ptr [rax+18h], 8
0x18001ce63  jb      short loc_18001CE68
0x18001ce65  mov     rax, [rax]
0x18001ce68  mov     [rsp+98h+var_40], rax
0x18001ce6d  lea     rax, [rsp+98h+var_68]
0x18001ce72  mov     [rsp+98h+var_70], rax
0x18001ce77  lea     rax, [rsp+98h+var_40]
0x18001ce7c  mov     [rsp+98h+ppv], rax
0x18001ce81  xor     r8d, r8d
0x18001ce84  lea     rdx, byte_18004F15F
0x18001ce8b  lea     rcx, dword_18005A000
0x18001ce92  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001ce97  mov     rdi, [rsp+98h+var_60]
0x18001ce9c  mov     r14, [rdi]
0x18001ce9f  mov     rcx, [rsi]
0x18001cea2  mov     rax, [rcx]
0x18001cea5  lea     rdx, [rsp+98h+var_40]
0x18001ceaa  mov     rax, [rax+10h]
0x18001ceae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceb3  nop
0x18001ceb4  cmp     qword ptr [rax+18h], 8
0x18001ceb9  jb      short loc_18001CEBE
0x18001cebb  mov     rax, [rax]
0x18001cebe  mov     rdx, rax
0x18001cec1  mov     rcx, rdi
0x18001cec4  mov     rax, [r14+28h]
0x18001cec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cecd  mov     edi, eax
0x18001cecf  cmp     [rsp+98h+var_28], 8
0x18001ced5  jb      short loc_18001CEE2
0x18001ced7  mov     rcx, [rsp+98h+var_40]
0x18001cedc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001cee2  test    edi, edi
0x18001cee4  jns     short loc_18001CF33
0x18001cee6  mov     ecx, cs:dword_18005A000
0x18001ceec  cmp     ecx, 2
0x18001ceef  jbe     short loc_18001CF33
0x18001cef1  mov     [rsp+98h+var_68], edi
0x18001cef5  add     rbx, 10h
0x18001cef9  cmp     qword ptr [rbx+18h], 8
0x18001cefe  jb      short loc_18001CF03
0x18001cf00  mov     rbx, [rbx]
0x18001cf03  mov     [rsp+98h+var_40], rbx
0x18001cf08  lea     rax, [rsp+98h+var_68]
0x18001cf0d  mov     [rsp+98h+var_70], rax
0x18001cf12  lea     rax, [rsp+98h+var_40]
0x18001cf17  mov     [rsp+98h+ppv], rax
0x18001cf1c  xor     r8d, r8d
0x18001cf1f  lea     rdx, unk_18004E840
0x18001cf26  lea     rcx, dword_18005A000
0x18001cf2d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001cf32  nop
0x18001cf33  mov     rcx, [rsp+98h+var_60]
0x18001cf38  test    rcx, rcx
0x18001cf3b  jz      short loc_18001CF53
0x18001cf3d  mov     [rsp+98h+var_60], 0
0x18001cf46  mov     rax, [rcx]
0x18001cf49  mov     rax, [rax+10h]
0x18001cf4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf52  nop
0x18001cf53  xor     eax, eax
0x18001cf55  mov     rcx, [rsp+98h+var_20]
0x18001cf5a  xor     rcx, rsp; StackCookie
0x18001cf5d  call    __security_check_cookie
0x18001cf62  mov     rbx, [rsp+98h+arg_0]
0x18001cf6a  add     rsp, 80h
0x18001cf71  pop     r14
0x18001cf73  pop     rdi
0x18001cf74  pop     rsi
0x18001cf75  retn
```
