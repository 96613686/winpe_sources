# get_or_create_silo(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *,void * const &,ulong)

- ea: `0x1800830d4`
- end: `0x180083592`
- name: `?get_or_create_silo@@YA?AV?$shared_ptr@Vappinfosvc_jitv_silo@@@std@@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@0AEBQEAXK@Z`
- size: `1214`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180082ba8`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180009484`
- `0x180011820`
- `0x18002031c`
- `0x180024fdc`
- `0x18002b240`
- `0x180033538`
- `0x180053390`
- `0x1800817e4`
- `0x180081b9c`
- `0x180081c30`
- `0x180081e58`
- `0x180081fc4`
- `0x1800822f0`
- `0x1800830d4`
- `0x180088994`
- `0x18008a580`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800834f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800834f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008350f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008350f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008352a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008352a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800831d3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800831d3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008317a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008317a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180083156`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180083156`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008312a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008312a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *get_or_create_silo(_QWORD *a1, void *a2, _QWORD *a3, __int64 a4, _QWORD *a5, ...)
{
  PSID *v9; // rbx
  __int64 v10; // rdi
  unsigned __int64 LengthSid; // rbx
  PSID v12; // rdi
  __int64 v13; // rcx
  const char *v14; // r9
  PSID v15; // rcx
  __int64 v16; // rcx
  _QWORD *v17; // rdi
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rdx
  signed __int32 v20; // eax
  signed __int32 v21; // ett
  _QWORD *v22; // rbx
  volatile signed __int32 *v23; // rcx
  _QWORD *v24; // rdx
  _QWORD *v25; // rdx
  _QWORD *v26; // rcx
  __int64 *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  volatile signed __int32 *v30; // rbx
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  void *v35; // rbx
  void **v36; // r14
  void *v37; // rax
  void *v38; // r15
  DWORD LastError; // edi
  __int64 v41; // rax
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  PSID v46; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v47; // [rsp+30h] [rbp-D0h] BYREF
  PSID pSid[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v49[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v50[8]; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int32 *v51; // [rsp+68h] [rbp-98h]
  _BYTE v52[24]; // [rsp+70h] [rbp-90h] BYREF
  char v53[16]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h]
  char v55[16]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v56[4]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v57; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v58[32]; // [rsp+D8h] [rbp-28h] BYREF
  PSID v59; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v60[32]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  va_list va; // [rsp+1A8h] [rbp+A8h] BYREF

  va_start(va, a5);
  v49[1] = a1;
  v42 = 0;
  v9 = (PSID *)qword_180107EA0;
  v10 = qword_180107EA8;
  if ( qword_180107EA0 == (void *)qword_180107EA8 )
    goto LABEL_5;
  do
  {
    if ( EqualSid(a2, *v9) )
      break;
    ++v9;
  }
  while ( v9 != (PSID *)v10 );
  if ( v9 == (PSID *)qword_180107EA8 )
  {
LABEL_5:
    LengthSid = GetLengthSid(a2);
    v12 = operator new[](LengthSid);
    if ( !CopySid(LengthSid, v12, a2) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\helper.cpp",
        v14);
    pSid[0] = v12;
    v42 = 2;
    if ( qword_180107EA8 == qword_180107EB0 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
        v13,
        qword_180107EA8,
        pSid);
      v15 = pSid[0];
    }
    else
    {
      *(_QWORD *)qword_180107EA8 = v12;
      v15 = 0;
      pSid[0] = 0;
      qword_180107EA8 += 8;
    }
    if ( v15 )
      FreeSid(v15);
  }
  else
  {
    v12 = *v9;
  }
  v46 = v12;
  v57 = (unsigned __int64)v12;
  std::wstring::wstring(v58, a3);
  v43 = v42 | 8;
  std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,std::weak_ptr<appinfosvc_jitv_silo>>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,std::wstring>>(
    v16,
    v53,
    &v57);
  v17 = (_QWORD *)v54;
  if ( *(_BYTE *)(v54 + 25)
    || v57 < *(_QWORD *)(v54 + 32)
    || v57 <= *(_QWORD *)(v54 + 32) && (unsigned __int8)std::operator<<unsigned short>(v58, v54 + 40) )
  {
    v17 = qword_180107E70;
  }
  std::wstring::~wstring(v58);
  if ( v17 != qword_180107E70 )
  {
    v18 = 0;
    v19 = v17[10];
    if ( v19 )
    {
      v20 = *(_DWORD *)(v19 + 8);
      while ( v20 )
      {
        v21 = v20;
        v20 = _InterlockedCompareExchange((volatile signed __int32 *)(v19 + 8), v20 + 1, v20);
        if ( v21 == v20 )
        {
          v41 = v17[9];
          v18 = (volatile signed __int32 *)v17[10];
          if ( !v41 )
            break;
          a1[1] = 0;
          *a1 = v41;
          v44 = v43 | 4;
          goto LABEL_31;
        }
      }
    }
    if ( v18 )
    {
      if ( !_InterlockedDecrement(v18 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( !_InterlockedDecrement(v18 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v22 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<Guid const,wil::com_ptr_t<InterceptedObject::InterceptedInterface,wil::err_returncode_policy>>>>::_Extract(
                      &qword_180107E70,
                      v17);
    v23 = (volatile signed __int32 *)v22[10];
    if ( v23 && _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    std::wstring::~wstring(v22 + 5);
    operator delete(v22, 0x58u);
  }
  *a1 = 0;
  v44 = v43 | 4;
  v18 = 0;
LABEL_31:
  a1[1] = v18;
  v45 = v44 | 1;
  if ( !*a1 )
  {
    v24 = a3;
    if ( a3[3] > 7u )
      v24 = (_QWORD *)*a3;
    package_fullname_from_familyname(v56, v24, a2);
    v25 = v56;
    if ( v56[3] > 7u )
      v25 = (_QWORD *)v56[0];
    v26 = a3;
    if ( a3[3] > 7u )
      v26 = (_QWORD *)*a3;
    helium::PrepareSystemForHeliumContainerWithoutLaunching(v26, v25, a4);
    vreg::appinfosvc::mount_hives_to_registry(v52, a3, a2, a4);
    v27 = (__int64 *)std::make_shared<appinfosvc_jitv_silo,unsigned __int64 &,std::vector<vreg::appinfosvc::mounted_hive_file>>(
                       v50,
                       &v46,
                       v52);
    v28 = *v27;
    v29 = v27[1];
    *v27 = 0;
    v27[1] = 0;
    *a1 = v28;
    v30 = (volatile signed __int32 *)a1[1];
    a1[1] = v29;
    if ( v30 )
    {
      if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
        if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
      }
    }
    v31 = v51;
    if ( v51 )
    {
      if ( _InterlockedExchangeAdd(v51 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    v47 = 0;
    v32 = a1[1];
    if ( v32 )
    {
      *(_QWORD *)&v47 = *a1;
      *((_QWORD *)&v47 + 1) = v32;
      _InterlockedIncrement((volatile signed __int32 *)(v32 + 12));
    }
    v59 = v46;
    std::wstring::wstring(v60, a3);
    std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,std::weak_ptr<appinfosvc_jitv_silo>>>,0>>::emplace<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo> &>(
      v33,
      v55,
      &v59,
      &v47,
      v45 | 0x10);
    std::wstring::~wstring(v60);
    if ( *((_QWORD *)&v47 + 1) && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 12LL)) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v47 + 1) + 8LL))(*((_QWORD *)&v47 + 1));
    std::vector<vreg::appinfosvc::mounted_hive_file>::~vector<vreg::appinfosvc::mounted_hive_file>(v52);
    std::wstring::~wstring(v56);
  }
  v34 = *a1;
  v49[0] = *a5;
  v35 = (void *)v49[0];
  v36 = (void **)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>,0>>::_Try_emplace<unsigned long const &,>(
                               v34 + 32,
                               pSid,
                               va)
                + 24LL);
  v37 = v35;
  if ( v36 != v49 )
  {
    v38 = *v36;
    if ( *v36 )
    {
      LastError = GetLastError();
      CloseHandle(v38);
      SetLastError(LastError);
    }
    *v36 = v35;
    v35 = 0;
    v37 = 0;
  }
  if ( v37 )
    CloseHandle(v35);
  return a1;
}

```

## disassembly

```asm
0x1800830d4  push    rbp
0x1800830d6  push    rbx
0x1800830d7  push    rsi
0x1800830d8  push    rdi
0x1800830d9  push    r12
0x1800830db  push    r13
0x1800830dd  push    r14
0x1800830df  push    r15
0x1800830e1  lea     rbp, [rsp-38h]
0x1800830e6  sub     rsp, 138h
0x1800830ed  mov     rax, cs:__security_cookie
0x1800830f4  xor     rax, rsp
0x1800830f7  mov     [rbp+70h+var_50], rax
0x1800830fb  mov     r13, r9
0x1800830fe  mov     r14, r8
0x180083101  mov     r12, rdx
0x180083104  mov     rsi, rcx
0x180083107  mov     [rsp+170h+var_118], rcx
0x18008310c  and     [rsp+170h+var_150], 0
0x180083111  mov     rbx, cs:qword_180107EA0
0x180083118  mov     rdi, cs:qword_180107EA8
0x18008311f  cmp     rbx, rdi
0x180083122  jz      short loc_180083153
0x180083124  mov     rdx, [rbx]; pSid2
0x180083127  mov     rcx, r12; pSid1
0x18008312a  call    cs:__imp_EqualSid
0x180083131  nop     dword ptr [rax+rax+00h]
0x180083136  test    eax, eax
0x180083138  jnz     short loc_180083143
0x18008313a  add     rbx, 8
0x18008313e  cmp     rbx, rdi
0x180083141  jnz     short loc_180083124
0x180083143  mov     rdi, cs:qword_180107EA8
0x18008314a  cmp     rbx, rdi
0x18008314d  jnz     loc_1800831E1
0x180083153  mov     rcx, r12; pSid
0x180083156  call    cs:__imp_GetLengthSid
0x18008315d  nop     dword ptr [rax+rax+00h]
0x180083162  mov     ebx, eax
0x180083164  mov     ecx, eax; unsigned __int64
0x180083166  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008316b  mov     rdi, rax
0x18008316e  mov     r15, [rbp+78h]
0x180083172  mov     r8, r12; pSourceSid
0x180083175  mov     rdx, rax; pDestinationSid
0x180083178  mov     ecx, ebx; nDestinationSidLength
0x18008317a  call    cs:__imp_CopySid
0x180083181  nop     dword ptr [rax+rax+00h]
0x180083186  test    eax, eax
0x180083188  jz      loc_18008357D
0x18008318e  mov     [rsp+170h+pSid], rdi
0x180083193  mov     [rsp+170h+var_150], 2
0x18008319b  mov     rdx, cs:qword_180107EA8
0x1800831a2  cmp     rdx, cs:qword_180107EB0
0x1800831a9  jz      short loc_1800831BF
0x1800831ab  mov     [rdx], rdi
0x1800831ae  xor     ecx, ecx
0x1800831b0  mov     [rsp+170h+pSid], rcx
0x1800831b5  add     cs:qword_180107EA8, 8
0x1800831bd  jmp     short loc_1800831CE
0x1800831bf  lea     r8, [rsp+170h+pSid]
0x1800831c4  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1800831c9  mov     rcx, [rsp+170h+pSid]; pSid
0x1800831ce  test    rcx, rcx
0x1800831d1  jz      short loc_1800831E4
0x1800831d3  call    cs:__imp_FreeSid
0x1800831da  nop     dword ptr [rax+rax+00h]
0x1800831df  jmp     short loc_1800831E4
0x1800831e1  mov     rdi, [rbx]
0x1800831e4  mov     [rsp+170h+var_148], rdi
0x1800831e9  mov     [rbp+70h+var_A0], rdi
0x1800831ed  mov     rdx, r14
0x1800831f0  lea     rcx, [rbp+70h+var_98]
0x1800831f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800831f9  or      [rsp+170h+var_150], 8
0x1800831fe  lea     r8, [rbp+70h+var_A0]
0x180083202  lea     rdx, [rbp+70h+var_E8]
0x180083206  call    ??$_Find_lower_bound@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@std@@PEAX@std@@@1@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,std::weak_ptr<appinfosvc_jitv_silo>>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,std::wstring>>(std::pair<unsigned __int64,std::wstring> const &)
0x18008320b  mov     rdi, [rbp+70h+var_D8]
0x18008320f  cmp     byte ptr [rdi+19h], 0
0x180083213  jnz     short loc_180083232
0x180083215  mov     rax, [rbp+70h+var_A0]
0x180083219  cmp     rax, [rdi+20h]
0x18008321d  jb      short loc_180083232
0x18008321f  ja      short loc_180083239
0x180083221  lea     rdx, [rdi+28h]
0x180083225  lea     rcx, [rbp+70h+var_98]
0x180083229  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18008322e  test    al, al
0x180083230  jz      short loc_180083239
0x180083232  mov     rdi, cs:qword_180107E70
0x180083239  lea     rcx, [rbp+70h+var_98]; void *
0x18008323d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083242  or      r15d, 0FFFFFFFFh
0x180083246  cmp     rdi, cs:qword_180107E70
0x18008324d  jz      loc_1800832FB
0x180083253  xor     ebx, ebx
0x180083255  mov     rdx, [rdi+50h]
0x180083259  test    rdx, rdx
0x18008325c  jz      short loc_180083275
0x18008325e  mov     eax, [rdx+8]
0x180083261  jmp     short loc_180083271
0x180083263  lea     ecx, [rax+1]
0x180083266  lock cmpxchg [rdx+8], ecx
0x18008326b  jz      loc_18008355A
0x180083271  test    eax, eax
0x180083273  jnz     short loc_180083263
0x180083275  test    rbx, rbx
0x180083278  jz      short loc_1800832B1
0x18008327a  mov     eax, r15d
0x18008327d  lock xadd [rbx+8], eax
0x180083282  add     eax, r15d
0x180083285  jnz     short loc_1800832B1
0x180083287  mov     rax, [rbx]
0x18008328a  mov     rcx, rbx
0x18008328d  mov     rax, [rax]
0x180083290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083295  mov     eax, r15d
0x180083298  lock xadd [rbx+0Ch], eax
0x18008329d  add     eax, r15d
0x1800832a0  jnz     short loc_1800832B1
0x1800832a2  mov     rax, [rbx]
0x1800832a5  mov     rcx, rbx
0x1800832a8  mov     rax, [rax+8]
0x1800832ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800832b1  mov     rdx, rdi
0x1800832b4  lea     rcx, qword_180107E70
0x1800832bb  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUGuid@@V?$com_ptr_t@VInterceptedInterface@InterceptedObject@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUGuid@@V?$com_ptr_t@VInterceptedInterface@InterceptedObject@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUGuid@@V?$com_ptr_t@VInterceptedInterface@InterceptedObject@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Guid const,wil::com_ptr_t<InterceptedObject::InterceptedInterface,wil::err_returncode_policy>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Guid const,wil::com_ptr_t<InterceptedObject::InterceptedInterface,wil::err_returncode_policy>>>>,std::_Iterator_base0>)
0x1800832c0  mov     rbx, rax
0x1800832c3  mov     rcx, [rax+50h]
0x1800832c7  test    rcx, rcx
0x1800832ca  jz      short loc_1800832E5
0x1800832cc  mov     edx, r15d
0x1800832cf  lock xadd [rcx+0Ch], edx
0x1800832d4  add     edx, r15d
0x1800832d7  jnz     short loc_1800832E5
0x1800832d9  mov     rdx, [rcx]
0x1800832dc  mov     rax, [rdx+8]
0x1800832e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800832e5  lea     rcx, [rbx+28h]; void *
0x1800832e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800832ee  mov     edx, 58h ; 'X'; unsigned __int64
0x1800832f3  mov     rcx, rbx; void *
0x1800832f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800832fb  and     qword ptr [rsi], 0
0x1800832ff  or      [rsp+170h+var_150], 4
0x180083304  xor     ebx, ebx
0x180083306  mov     [rsi+8], rbx
0x18008330a  or      [rsp+170h+var_150], 1
0x18008330f  cmp     qword ptr [rsi], 0
0x180083313  jnz     loc_1800834AD
0x180083319  mov     rdx, r14
0x18008331c  cmp     qword ptr [r14+18h], 7
0x180083321  jbe     short loc_180083326
0x180083323  mov     rdx, [r14]
0x180083326  mov     r8, r12
0x180083329  lea     rcx, [rbp+70h+var_C0]
0x18008332d  call    ?package_fullname_from_familyname@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAX@Z; package_fullname_from_familyname(ushort const *,void *)
0x180083332  nop
0x180083333  lea     rdx, [rbp+70h+var_C0]
0x180083337  cmp     [rbp+70h+var_A8], 7
0x18008333c  cmova   rdx, [rbp+70h+var_C0]
0x180083341  mov     rcx, r14
0x180083344  cmp     qword ptr [r14+18h], 7
0x180083349  jbe     short loc_18008334E
0x18008334b  mov     rcx, [r14]
0x18008334e  mov     r8, r13
0x180083351  call    ?PrepareSystemForHeliumContainerWithoutLaunching@helium@@YAXPEBG0PEAXW4ContainerType@1@@Z; helium::PrepareSystemForHeliumContainerWithoutLaunching(ushort const *,ushort const *,void *,helium::ContainerType)
0x180083356  mov     r9, r13
0x180083359  mov     r8, r12
0x18008335c  mov     rdx, r14
0x18008335f  lea     rcx, [rsp+170h+var_100]
0x180083364  call    ?mount_hives_to_registry@appinfosvc@vreg@@YA?AV?$vector@Vmounted_hive_file@appinfosvc@vreg@@V?$allocator@Vmounted_hive_file@appinfosvc@vreg@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAX1@Z; vreg::appinfosvc::mount_hives_to_registry(std::wstring const &,void *,void *)
0x180083369  nop
0x18008336a  lea     r8, [rsp+170h+var_100]
0x18008336f  lea     rdx, [rsp+170h+var_148]
0x180083374  lea     rcx, [rsp+170h+var_110]
0x180083379  call    ??$make_shared@Vappinfosvc_jitv_silo@@AEA_KV?$vector@Vmounted_hive_file@appinfosvc@vreg@@V?$allocator@Vmounted_hive_file@appinfosvc@vreg@@@std@@@std@@@std@@YA?AV?$shared_ptr@Vappinfosvc_jitv_silo@@@0@AEA_K$$QEAV?$vector@Vmounted_hive_file@appinfosvc@vreg@@V?$allocator@Vmounted_hive_file@appinfosvc@vreg@@@std@@@0@@Z; std::make_shared<appinfosvc_jitv_silo,unsigned __int64 &,std::vector<vreg::appinfosvc::mounted_hive_file>>(unsigned __int64 &,std::vector<vreg::appinfosvc::mounted_hive_file> &&)
0x18008337e  mov     rcx, [rax]
0x180083381  mov     rdx, [rax+8]
0x180083385  and     qword ptr [rax], 0
0x180083389  and     qword ptr [rax+8], 0
0x18008338e  mov     [rsi], rcx
0x180083391  mov     rbx, [rsi+8]
0x180083395  mov     [rsi+8], rdx
0x180083399  test    rbx, rbx
0x18008339c  jz      short loc_1800833D5
0x18008339e  mov     eax, r15d
0x1800833a1  lock xadd [rbx+8], eax
0x1800833a6  add     eax, r15d
0x1800833a9  jnz     short loc_1800833D5
0x1800833ab  mov     rax, [rbx]
0x1800833ae  mov     rcx, rbx
0x1800833b1  mov     rax, [rax]
0x1800833b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800833b9  mov     eax, r15d
0x1800833bc  lock xadd [rbx+0Ch], eax
0x1800833c1  add     eax, r15d
0x1800833c4  jnz     short loc_1800833D5
0x1800833c6  mov     rax, [rbx]
0x1800833c9  mov     rcx, rbx
0x1800833cc  mov     rax, [rax+8]
0x1800833d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800833d5  mov     rbx, [rsp+170h+var_108]
0x1800833da  test    rbx, rbx
0x1800833dd  jz      short loc_180083416
0x1800833df  mov     eax, r15d
0x1800833e2  lock xadd [rbx+8], eax
0x1800833e7  add     eax, r15d
0x1800833ea  jnz     short loc_180083416
0x1800833ec  mov     rax, [rbx]
0x1800833ef  mov     rcx, rbx
0x1800833f2  mov     rax, [rax]
0x1800833f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800833fa  mov     eax, r15d
0x1800833fd  lock xadd [rbx+0Ch], eax
0x180083402  add     eax, r15d
0x180083405  jnz     short loc_180083416
0x180083407  mov     rax, [rbx]
0x18008340a  mov     rcx, rbx
0x18008340d  mov     rax, [rax+8]
0x180083411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083416  xorps   xmm0, xmm0
0x180083419  movdqu  [rsp+170h+var_140], xmm0
0x18008341f  mov     rcx, [rsi+8]
0x180083423  test    rcx, rcx
0x180083426  jz      short loc_180083439
0x180083428  mov     rax, [rsi]
0x18008342b  mov     qword ptr [rsp+170h+var_140], rax
0x180083430  mov     qword ptr [rsp+170h+var_140+8], rcx
0x180083435  lock inc dword ptr [rcx+0Ch]
0x180083439  mov     rax, [rsp+170h+var_148]
0x18008343e  mov     [rbp+70h+var_78], rax
0x180083442  mov     rdx, r14
0x180083445  lea     rcx, [rbp+70h+var_70]
0x180083449  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008344e  or      [rsp+170h+var_150], 10h
0x180083453  lea     r9, [rsp+170h+var_140]
0x180083458  lea     r8, [rbp+70h+var_78]
0x18008345c  lea     rdx, [rbp+70h+var_D0]
0x180083460  call    ??$emplace@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEAV?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEAV?$weak_ptr@Vappinfosvc_jitv_silo@@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,std::weak_ptr<appinfosvc_jitv_silo>>>,0>>::emplace<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo> &>(std::pair<unsigned __int64,std::wstring> &&,std::weak_ptr<appinfosvc_jitv_silo> &)
0x180083465  nop
0x180083466  lea     rcx, [rbp+70h+var_70]; void *
0x18008346a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008346f  nop
0x180083470  mov     rcx, qword ptr [rsp+170h+var_140+8]
0x180083475  test    rcx, rcx
0x180083478  jz      short loc_180083499
0x18008347a  mov     eax, r15d
0x18008347d  lock xadd [rcx+0Ch], eax
0x180083482  add     eax, r15d
0x180083485  jnz     short loc_180083499
0x180083487  mov     rcx, qword ptr [rsp+170h+var_140+8]
0x18008348c  mov     rax, [rcx]
0x18008348f  mov     rax, [rax+8]
0x180083493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083498  nop
0x180083499  lea     rcx, [rsp+170h+var_100]
0x18008349e  call    ??1?$vector@Vmounted_hive_file@appinfosvc@vreg@@V?$allocator@Vmounted_hive_file@appinfosvc@vreg@@@std@@@std@@QEAA@XZ; std::vector<vreg::appinfosvc::mounted_hive_file>::~vector<vreg::appinfosvc::mounted_hive_file>(void)
0x1800834a3  nop
0x1800834a4  lea     rcx, [rbp+70h+var_C0]; void *
0x1800834a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800834ad  mov     rcx, [rsi]
0x1800834b0  mov     rbx, [rbp+70h+arg_20]
0x1800834b7  mov     rbx, [rbx]
0x1800834ba  mov     [rsp+170h+var_120], rbx
0x1800834bf  add     rcx, 20h ; ' '
0x1800834c3  lea     r8, [rbp+70h+arg_28]
0x1800834ca  lea     rdx, [rsp+170h+pSid]
0x1800834cf  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x1800834d4  mov     r14, [rax]
0x1800834d7  add     r14, 18h
0x1800834db  mov     rax, rbx
0x1800834de  lea     rcx, [rsp+170h+var_120]
0x1800834e3  cmp     r14, rcx
0x1800834e6  jz      short loc_180083522
0x1800834e8  mov     r15, [r14]
0x1800834eb  test    r15, r15
0x1800834ee  jz      short loc_18008351B
0x1800834f0  call    cs:__imp_GetLastError
0x1800834f7  nop     dword ptr [rax+rax+00h]
0x1800834fc  mov     edi, eax
0x1800834fe  mov     rcx, r15; hObject
0x180083501  call    cs:__imp_CloseHandle
0x180083508  nop     dword ptr [rax+rax+00h]
0x18008350d  mov     ecx, edi; dwErrCode
0x18008350f  call    cs:__imp_SetLastError
0x180083516  nop     dword ptr [rax+rax+00h]
0x18008351b  mov     [r14], rbx
0x18008351e  xor     ebx, ebx
0x180083520  xor     eax, eax
0x180083522  test    rax, rax
0x180083525  jz      short loc_180083536
0x180083527  mov     rcx, rbx; hObject
0x18008352a  call    cs:__imp_CloseHandle
0x180083531  nop     dword ptr [rax+rax+00h]
0x180083536  mov     rax, rsi
0x180083539  mov     rcx, [rbp+70h+var_50]
0x18008353d  xor     rcx, rsp; StackCookie
0x180083540  call    __security_check_cookie
  ... truncated ...
```
