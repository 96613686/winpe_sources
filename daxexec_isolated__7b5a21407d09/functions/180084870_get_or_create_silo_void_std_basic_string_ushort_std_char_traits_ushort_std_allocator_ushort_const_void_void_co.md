# get_or_create_silo(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *,void * const &,ulong)

- ea: `0x180084870`
- end: `0x180084d1f`
- name: `?get_or_create_silo@@YA?AV?$shared_ptr@Vappinfosvc_jitv_silo@@@std@@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@0AEBQEAXK@Z`
- size: `1199`
- prototype: `_QWORD *(_QWORD *, void *, _QWORD *, __int64, void **, ...)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800843ac`

## callees

- `0x180004f70`
- `0x180005340`
- `0x18000afe4`
- `0x180013510`
- `0x1800210fc`
- `0x180025980`
- `0x18002bab4`
- `0x180035078`
- `0x180054ea0`
- `0x180082e58`
- `0x1800831e0`
- `0x180083278`
- `0x18008346c`
- `0x1800835bc`
- `0x1800839a4`
- `0x180084870`
- `0x180089fd8`
- `0x18008bc3c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180084cba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180084cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084c9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084cda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084cda`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008496b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008496b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180084916`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180084916`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800848f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800848f2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800848c6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800848c6`

## pseudocode

```c
_QWORD *get_or_create_silo(_QWORD *a1, void *a2, _QWORD *a3, __int64 a4, void **a5, ...)
{
  int v9; // edi
  __int64 v10; // rbx
  PSID *v11; // rsi
  unsigned __int64 LengthSid; // rbx
  PSID v13; // rsi
  __int64 v14; // rcx
  const char *v15; // r9
  PSID v16; // rcx
  int v17; // edi
  __int64 v18; // rcx
  __int64 v19; // rsi
  unsigned __int64 v20; // rax
  volatile signed __int32 *v21; // rbx
  __int64 v22; // rdx
  signed __int32 v23; // eax
  signed __int32 v24; // ett
  _QWORD *v25; // rbx
  volatile signed __int32 *v26; // rcx
  int v27; // edi
  int v28; // edi
  _QWORD *v29; // rdx
  __int64 v30; // rax
  _QWORD *v31; // rdx
  _QWORD *v32; // rcx
  __int64 *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  volatile signed __int32 *v36; // rbx
  volatile signed __int32 *v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  void *v42; // rbx
  void **v43; // rsi
  void *v44; // r15
  DWORD LastError; // edi
  void *v46; // rax
  __int128 v48; // [rsp+28h] [rbp-A1h] BYREF
  PSID pSid[2]; // [rsp+38h] [rbp-91h] BYREF
  void *v50; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v51[16]; // [rsp+50h] [rbp-79h] BYREF
  __int64 v52; // [rsp+60h] [rbp-69h]
  _QWORD *v53; // [rsp+68h] [rbp-61h]
  _QWORD *v54; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v55[16]; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int64 v56; // [rsp+88h] [rbp-41h]
  PSID v57; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v58[32]; // [rsp+A0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]
  va_list va; // [rsp+148h] [rbp+7Fh] BYREF

  va_start(va, a5);
  v53 = a1;
  v9 = 0;
  v10 = qword_180109A28;
  v11 = (PSID *)qword_180109A20;
  if ( qword_180109A20 == (void *)qword_180109A28 )
    goto LABEL_5;
  do
  {
    if ( EqualSid(a2, *v11) )
      break;
    ++v11;
  }
  while ( v11 != (PSID *)v10 );
  if ( v11 == (PSID *)qword_180109A28 )
  {
LABEL_5:
    LengthSid = GetLengthSid(a2);
    v13 = operator new[](LengthSid);
    if ( !CopySid(LengthSid, v13, a2) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\helper.cpp",
        v15);
    pSid[0] = v13;
    v9 = 2;
    if ( qword_180109A28 == qword_180109A30 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
        v14,
        qword_180109A28,
        pSid);
      v16 = pSid[0];
    }
    else
    {
      *(_QWORD *)qword_180109A28 = v13;
      v16 = 0;
      qword_180109A28 += 8;
    }
    if ( v16 )
      FreeSid(v16);
  }
  else
  {
    v13 = *v11;
  }
  pSid[0] = v13;
  v54 = v13;
  std::wstring::wstring(v55, a3);
  v17 = v9 | 8;
  std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,std::weak_ptr<appinfosvc_jitv_silo>>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,std::wstring>>(
    v18,
    v51,
    &v54);
  v19 = v52;
  if ( *(_BYTE *)(v52 + 25)
    || (v20 = *(_QWORD *)(v52 + 32), (unsigned __int64)v54 < v20)
    || (unsigned __int64)v54 <= v20 && (unsigned __int8)std::operator<<unsigned short>(v55, v52 + 40) )
  {
    v19 = qword_180109A10;
  }
  std::wstring::~wstring(v55);
  if ( v19 != qword_180109A10 )
  {
    v21 = 0;
    v22 = *(_QWORD *)(v19 + 80);
    if ( v22 )
    {
      v23 = *(_DWORD *)(v22 + 8);
      while ( v23 )
      {
        v24 = v23;
        v23 = _InterlockedCompareExchange((volatile signed __int32 *)(v22 + 8), v23 + 1, v23);
        if ( v24 == v23 )
        {
          v30 = *(_QWORD *)(v19 + 72);
          v21 = *(volatile signed __int32 **)(v19 + 80);
          if ( !v30 )
            break;
          a1[1] = 0;
          *a1 = v30;
          v27 = v17 | 4;
          goto LABEL_31;
        }
      }
    }
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    v25 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<Guid const,wil::com_ptr_t<InterceptedObject::InterceptedInterface,wil::err_returncode_policy>>>>::_Extract(
                      &qword_180109A10,
                      v19);
    v26 = (volatile signed __int32 *)v25[10];
    if ( v26 && _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    std::wstring::~wstring(v25 + 5);
    operator delete(v25, 0x58u);
  }
  *a1 = 0;
  v27 = v17 | 4;
  v21 = 0;
LABEL_31:
  a1[1] = v21;
  v28 = v27 | 1;
  if ( !*a1 )
  {
    if ( a3[3] <= 7u )
      v29 = a3;
    else
      v29 = (_QWORD *)*a3;
    package_fullname_from_familyname(&v54, v29, a2);
    v31 = &v54;
    if ( v56 > 7 )
      v31 = v54;
    if ( a3[3] <= 7u )
      v32 = a3;
    else
      v32 = (_QWORD *)*a3;
    helium::PrepareSystemForHeliumContainerWithoutLaunching(v32, v31, a4);
    vreg::appinfosvc::mount_hives_to_registry(v51, a3, a2, a4, v28);
    v33 = (__int64 *)std::make_shared<appinfosvc_jitv_silo,unsigned __int64 &,std::vector<vreg::appinfosvc::mounted_hive_file>>(
                       &v48,
                       pSid,
                       v51);
    v34 = *v33;
    v35 = v33[1];
    *v33 = 0;
    v33[1] = 0;
    *a1 = v34;
    v36 = (volatile signed __int32 *)a1[1];
    a1[1] = v35;
    if ( v36 )
    {
      if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    v37 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
    if ( *((_QWORD *)&v48 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    v48 = 0;
    v38 = a1[1];
    if ( v38 )
    {
      *(_QWORD *)&v48 = *a1;
      *((_QWORD *)&v48 + 1) = v38;
      _InterlockedIncrement((volatile signed __int32 *)(v38 + 12));
    }
    v57 = pSid[0];
    std::wstring::wstring(v58, a3);
    std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,std::weak_ptr<appinfosvc_jitv_silo>>>,0>>::emplace<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo> &>(
      v39,
      pSid,
      &v57,
      &v48,
      v28 | 0x10);
    std::wstring::~wstring(v58);
    v40 = *((_QWORD *)&v48 + 1);
    if ( *((_QWORD *)&v48 + 1) && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 12LL)) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
    std::vector<vreg::appinfosvc::mounted_hive_file>::~vector<vreg::appinfosvc::mounted_hive_file>(v51);
    std::wstring::~wstring(&v54);
  }
  v41 = *a1;
  v42 = *a5;
  v50 = *a5;
  v43 = (void **)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>,0>>::_Try_emplace<unsigned long const &,>(
                               v41 + 32,
                               &v48,
                               va)
                + 24LL);
  if ( v43 == &v50 )
  {
    v46 = v42;
  }
  else
  {
    v44 = *v43;
    if ( *v43 )
    {
      LastError = GetLastError();
      CloseHandle(v44);
      SetLastError(LastError);
    }
    *v43 = v42;
    v42 = 0;
    v46 = 0;
  }
  if ( v46 )
    CloseHandle(v42);
  return a1;
}

```

## disassembly

```asm
0x180084870  push    rbp
0x180084872  push    rbx
0x180084873  push    rsi
0x180084874  push    rdi
0x180084875  push    r12
0x180084877  push    r13
0x180084879  push    r14
0x18008487b  push    r15
0x18008487d  lea     rbp, [rsp-0Fh]
0x180084882  sub     rsp, 0D8h
0x180084889  mov     rax, cs:__security_cookie
0x180084890  xor     rax, rsp
0x180084893  mov     [rbp+47h+var_50], rax
0x180084897  mov     r13, r9
0x18008489a  mov     r15, r8
0x18008489d  mov     r12, rdx
0x1800848a0  mov     r14, rcx
0x1800848a3  mov     [rbp+47h+var_A8], rcx
0x1800848a7  xor     edi, edi
0x1800848a9  mov     [rsp+110h+var_F0], edi
0x1800848ad  mov     rbx, cs:qword_180109A28
0x1800848b4  mov     rsi, cs:qword_180109A20
0x1800848bb  cmp     rsi, rbx
0x1800848be  jz      short loc_1800848EF
0x1800848c0  mov     rdx, [rsi]; pSid2
0x1800848c3  mov     rcx, r12; pSid1
0x1800848c6  call    cs:__imp_EqualSid
0x1800848cd  nop     dword ptr [rax+rax+00h]
0x1800848d2  test    eax, eax
0x1800848d4  jnz     short loc_1800848DF
0x1800848d6  add     rsi, 8
0x1800848da  cmp     rsi, rbx
0x1800848dd  jnz     short loc_1800848C0
0x1800848df  mov     rbx, cs:qword_180109A28
0x1800848e6  cmp     rsi, rbx
0x1800848e9  jnz     loc_180084979
0x1800848ef  mov     rcx, r12; pSid
0x1800848f2  call    cs:__imp_GetLengthSid
0x1800848f9  nop     dword ptr [rax+rax+00h]
0x1800848fe  mov     ebx, eax
0x180084900  mov     ecx, eax; unsigned __int64
0x180084902  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180084907  mov     rsi, rax
0x18008490a  mov     rdi, [rbp+4Fh]
0x18008490e  mov     r8, r12; pSourceSid
0x180084911  mov     rdx, rax; pDestinationSid
0x180084914  mov     ecx, ebx; nDestinationSidLength
0x180084916  call    cs:__imp_CopySid
0x18008491d  nop     dword ptr [rax+rax+00h]
0x180084922  test    eax, eax
0x180084924  jz      loc_180084D0A
0x18008492a  mov     [rsp+110h+pSid], rsi
0x18008492f  mov     edi, 2
0x180084934  mov     [rsp+110h+var_F0], edi
0x180084938  mov     rdx, cs:qword_180109A28
0x18008493f  cmp     rdx, cs:qword_180109A30
0x180084946  jz      short loc_180084957
0x180084948  mov     [rdx], rsi
0x18008494b  xor     ecx, ecx
0x18008494d  add     cs:qword_180109A28, 8
0x180084955  jmp     short loc_180084966
0x180084957  lea     r8, [rsp+110h+pSid]
0x18008495c  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x180084961  mov     rcx, [rsp+110h+pSid]; pSid
0x180084966  test    rcx, rcx
0x180084969  jz      short loc_18008497C
0x18008496b  call    cs:__imp_FreeSid
0x180084972  nop     dword ptr [rax+rax+00h]
0x180084977  jmp     short loc_18008497C
0x180084979  mov     rsi, [rsi]
0x18008497c  mov     [rsp+110h+pSid], rsi
0x180084981  mov     [rbp+47h+var_A0], rsi
0x180084985  mov     rdx, r15
0x180084988  lea     rcx, [rbp+47h+var_98]
0x18008498c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180084991  or      edi, 8
0x180084994  lea     r8, [rbp+47h+var_A0]
0x180084998  lea     rdx, [rbp+47h+var_C0]
0x18008499c  call    ??$_Find_lower_bound@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@std@@PEAX@std@@@1@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,std::weak_ptr<appinfosvc_jitv_silo>>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,std::wstring>>(std::pair<unsigned __int64,std::wstring> const &)
0x1800849a1  mov     rsi, [rbp+47h+var_B0]
0x1800849a5  cmp     byte ptr [rsi+19h], 0
0x1800849a9  jnz     short loc_1800849C8
0x1800849ab  mov     rax, [rsi+20h]
0x1800849af  cmp     [rbp+47h+var_A0], rax
0x1800849b3  jb      short loc_1800849C8
0x1800849b5  ja      short loc_1800849CF
0x1800849b7  lea     rdx, [rsi+28h]
0x1800849bb  lea     rcx, [rbp+47h+var_98]
0x1800849bf  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800849c4  test    al, al
0x1800849c6  jz      short loc_1800849CF
0x1800849c8  mov     rsi, cs:qword_180109A10
0x1800849cf  lea     rcx, [rbp+47h+var_98]; void *
0x1800849d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800849d8  cmp     rsi, cs:qword_180109A10
0x1800849df  jz      loc_180084A8D
0x1800849e5  xor     ebx, ebx
0x1800849e7  mov     rdx, [rsi+50h]
0x1800849eb  test    rdx, rdx
0x1800849ee  jz      short loc_180084A07
0x1800849f0  mov     eax, [rdx+8]
0x1800849f3  jmp     short loc_180084A03
0x1800849f5  lea     ecx, [rax+1]
0x1800849f8  lock cmpxchg [rdx+8], ecx
0x1800849fd  jz      loc_180084ABA
0x180084a03  test    eax, eax
0x180084a05  jnz     short loc_1800849F5
0x180084a07  test    rbx, rbx
0x180084a0a  jz      short loc_180084A43
0x180084a0c  or      eax, 0FFFFFFFFh
0x180084a0f  lock xadd [rbx+8], eax
0x180084a14  cmp     eax, 1
0x180084a17  jnz     short loc_180084A43
0x180084a19  mov     rax, [rbx]
0x180084a1c  mov     rcx, rbx
0x180084a1f  mov     rax, [rax]
0x180084a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a27  or      eax, 0FFFFFFFFh
0x180084a2a  lock xadd [rbx+0Ch], eax
0x180084a2f  cmp     eax, 1
0x180084a32  jnz     short loc_180084A43
0x180084a34  mov     rax, [rbx]
0x180084a37  mov     rcx, rbx
0x180084a3a  mov     rax, [rax+8]
0x180084a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a43  mov     rdx, rsi
0x180084a46  lea     rcx, qword_180109A10
0x180084a4d  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUGuid@@V?$com_ptr_t@VInterceptedInterface@InterceptedObject@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUGuid@@V?$com_ptr_t@VInterceptedInterface@InterceptedObject@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUGuid@@V?$com_ptr_t@VInterceptedInterface@InterceptedObject@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Guid const,wil::com_ptr_t<InterceptedObject::InterceptedInterface,wil::err_returncode_policy>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Guid const,wil::com_ptr_t<InterceptedObject::InterceptedInterface,wil::err_returncode_policy>>>>,std::_Iterator_base0>)
0x180084a52  mov     rbx, rax
0x180084a55  mov     rcx, [rax+50h]
0x180084a59  test    rcx, rcx
0x180084a5c  jz      short loc_180084A77
0x180084a5e  or      edx, 0FFFFFFFFh
0x180084a61  lock xadd [rcx+0Ch], edx
0x180084a66  cmp     edx, 1
0x180084a69  jnz     short loc_180084A77
0x180084a6b  mov     rdx, [rcx]
0x180084a6e  mov     rax, [rdx+8]
0x180084a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a77  lea     rcx, [rbx+28h]; void *
0x180084a7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084a80  mov     edx, 58h ; 'X'; unsigned __int64
0x180084a85  mov     rcx, rbx; void *
0x180084a88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180084a8d  mov     qword ptr [r14], 0
0x180084a94  or      edi, 4
0x180084a97  xor     ebx, ebx
0x180084a99  mov     [r14+8], rbx
0x180084a9d  or      edi, 1
0x180084aa0  mov     [rsp+110h+var_F0], edi
0x180084aa4  cmp     qword ptr [r14], 0
0x180084aa8  jnz     loc_180084C61
0x180084aae  cmp     qword ptr [r15+18h], 7
0x180084ab3  jbe     short loc_180084ADB
0x180084ab5  mov     rdx, [r15]
0x180084ab8  jmp     short loc_180084ADE
0x180084aba  mov     rax, [rsi+48h]
0x180084abe  mov     rbx, [rsi+50h]
0x180084ac2  test    rax, rax
0x180084ac5  jz      loc_180084A07
0x180084acb  mov     qword ptr [r14+8], 0
0x180084ad3  mov     [r14], rax
0x180084ad6  or      edi, 4
0x180084ad9  jmp     short loc_180084A99
0x180084adb  mov     rdx, r15
0x180084ade  mov     r8, r12
0x180084ae1  lea     rcx, [rbp+47h+var_A0]
0x180084ae5  call    ?package_fullname_from_familyname@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAX@Z; package_fullname_from_familyname(ushort const *,void *)
0x180084aea  nop
0x180084aeb  lea     rdx, [rbp+47h+var_A0]
0x180084aef  cmp     [rbp+47h+var_88], 7
0x180084af4  cmova   rdx, [rbp+47h+var_A0]
0x180084af9  cmp     qword ptr [r15+18h], 7
0x180084afe  jbe     short loc_180084B05
0x180084b00  mov     rcx, [r15]
0x180084b03  jmp     short loc_180084B08
0x180084b05  mov     rcx, r15
0x180084b08  mov     r8, r13
0x180084b0b  call    ?PrepareSystemForHeliumContainerWithoutLaunching@helium@@YAXPEBG0PEAXW4ContainerType@1@@Z; helium::PrepareSystemForHeliumContainerWithoutLaunching(ushort const *,ushort const *,void *,helium::ContainerType)
0x180084b10  mov     r9, r13
0x180084b13  mov     r8, r12
0x180084b16  mov     rdx, r15
0x180084b19  lea     rcx, [rbp+47h+var_C0]
0x180084b1d  call    ?mount_hives_to_registry@appinfosvc@vreg@@YA?AV?$vector@Vmounted_hive_file@appinfosvc@vreg@@V?$allocator@Vmounted_hive_file@appinfosvc@vreg@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAX1@Z; vreg::appinfosvc::mount_hives_to_registry(std::wstring const &,void *,void *)
0x180084b22  nop
0x180084b23  lea     r8, [rbp+47h+var_C0]
0x180084b27  lea     rdx, [rsp+110h+pSid]
0x180084b2c  lea     rcx, [rsp+110h+var_E8]
0x180084b31  call    ??$make_shared@Vappinfosvc_jitv_silo@@AEA_KV?$vector@Vmounted_hive_file@appinfosvc@vreg@@V?$allocator@Vmounted_hive_file@appinfosvc@vreg@@@std@@@std@@@std@@YA?AV?$shared_ptr@Vappinfosvc_jitv_silo@@@0@AEA_K$$QEAV?$vector@Vmounted_hive_file@appinfosvc@vreg@@V?$allocator@Vmounted_hive_file@appinfosvc@vreg@@@std@@@0@@Z; std::make_shared<appinfosvc_jitv_silo,unsigned __int64 &,std::vector<vreg::appinfosvc::mounted_hive_file>>(unsigned __int64 &,std::vector<vreg::appinfosvc::mounted_hive_file> &&)
0x180084b36  mov     rcx, [rax]
0x180084b39  mov     rdx, [rax+8]
0x180084b3d  mov     qword ptr [rax], 0
0x180084b44  mov     qword ptr [rax+8], 0
0x180084b4c  mov     [r14], rcx
0x180084b4f  mov     rbx, [r14+8]
0x180084b53  mov     [r14+8], rdx
0x180084b57  or      esi, 0FFFFFFFFh
0x180084b5a  test    rbx, rbx
0x180084b5d  jz      short loc_180084B92
0x180084b5f  mov     eax, esi
0x180084b61  lock xadd [rbx+8], eax
0x180084b66  add     eax, esi
0x180084b68  jnz     short loc_180084B92
0x180084b6a  mov     rax, [rbx]
0x180084b6d  mov     rcx, rbx
0x180084b70  mov     rax, [rax]
0x180084b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b78  mov     eax, esi
0x180084b7a  lock xadd [rbx+0Ch], eax
0x180084b7f  add     eax, esi
0x180084b81  jnz     short loc_180084B92
0x180084b83  mov     rax, [rbx]
0x180084b86  mov     rcx, rbx
0x180084b89  mov     rax, [rax+8]
0x180084b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b92  mov     rbx, qword ptr [rsp+110h+var_E8+8]
0x180084b97  test    rbx, rbx
0x180084b9a  jz      short loc_180084BCF
0x180084b9c  mov     eax, esi
0x180084b9e  lock xadd [rbx+8], eax
0x180084ba3  add     eax, esi
0x180084ba5  jnz     short loc_180084BCF
0x180084ba7  mov     rax, [rbx]
0x180084baa  mov     rcx, rbx
0x180084bad  mov     rax, [rax]
0x180084bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bb5  mov     eax, esi
0x180084bb7  lock xadd [rbx+0Ch], eax
0x180084bbc  add     eax, esi
0x180084bbe  jnz     short loc_180084BCF
0x180084bc0  mov     rax, [rbx]
0x180084bc3  mov     rcx, rbx
0x180084bc6  mov     rax, [rax+8]
0x180084bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bcf  xorps   xmm0, xmm0
0x180084bd2  movdqu  [rsp+110h+var_E8], xmm0
0x180084bd8  mov     rcx, [r14+8]
0x180084bdc  test    rcx, rcx
0x180084bdf  jz      short loc_180084BF2
0x180084be1  mov     rax, [r14]
0x180084be4  mov     qword ptr [rsp+110h+var_E8], rax
0x180084be9  mov     qword ptr [rsp+110h+var_E8+8], rcx
0x180084bee  lock inc dword ptr [rcx+0Ch]
0x180084bf2  mov     rax, [rsp+110h+pSid]
0x180084bf7  mov     [rbp+47h+var_78], rax
0x180084bfb  mov     rdx, r15
0x180084bfe  lea     rcx, [rbp+47h+var_70]
0x180084c02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180084c07  or      edi, 10h
0x180084c0a  mov     [rsp+110h+var_F0], edi
0x180084c0e  lea     r9, [rsp+110h+var_E8]
0x180084c13  lea     r8, [rbp+47h+var_78]
0x180084c17  lea     rdx, [rsp+110h+pSid]
0x180084c1c  call    ??$emplace@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEAV?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$weak_ptr@Vappinfosvc_jitv_silo@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEAV?$weak_ptr@Vappinfosvc_jitv_silo@@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,std::weak_ptr<appinfosvc_jitv_silo>>>,0>>::emplace<std::pair<unsigned __int64,std::wstring>,std::weak_ptr<appinfosvc_jitv_silo> &>(std::pair<unsigned __int64,std::wstring> &&,std::weak_ptr<appinfosvc_jitv_silo> &)
0x180084c21  nop
0x180084c22  lea     rcx, [rbp+47h+var_70]; void *
0x180084c26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084c2b  nop
0x180084c2c  mov     rcx, qword ptr [rsp+110h+var_E8+8]
0x180084c31  test    rcx, rcx
0x180084c34  jz      short loc_180084C4E
0x180084c36  mov     eax, esi
0x180084c38  lock xadd [rcx+0Ch], eax
0x180084c3d  add     eax, esi
0x180084c3f  jnz     short loc_180084C4E
0x180084c41  mov     rax, [rcx]
0x180084c44  mov     rax, [rax+8]
0x180084c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c4d  nop
0x180084c4e  lea     rcx, [rbp+47h+var_C0]
0x180084c52  call    ??1?$vector@Vmounted_hive_file@appinfosvc@vreg@@V?$allocator@Vmounted_hive_file@appinfosvc@vreg@@@std@@@std@@QEAA@XZ; std::vector<vreg::appinfosvc::mounted_hive_file>::~vector<vreg::appinfosvc::mounted_hive_file>(void)
0x180084c57  nop
0x180084c58  lea     rcx, [rbp+47h+var_A0]; void *
0x180084c5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084c61  mov     rcx, [r14]
0x180084c64  mov     rbx, [rbp+47h+arg_20]
0x180084c68  mov     rbx, [rbx]
0x180084c6b  mov     [rsp+110h+var_C8], rbx
0x180084c70  add     rcx, 20h ; ' '
0x180084c74  lea     r8, [rbp+47h+arg_28]
0x180084c78  lea     rdx, [rsp+110h+var_E8]
0x180084c7d  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x180084c82  mov     rsi, [rax]
0x180084c85  add     rsi, 18h
0x180084c89  lea     rax, [rsp+110h+var_C8]
0x180084c8e  cmp     rsi, rax
0x180084c91  jz      short loc_180084CCF
0x180084c93  mov     r15, [rsi]
0x180084c96  test    r15, r15
0x180084c99  jz      short loc_180084CC6
0x180084c9b  call    cs:__imp_GetLastError
0x180084ca2  nop     dword ptr [rax+rax+00h]
0x180084ca7  mov     edi, eax
0x180084ca9  mov     rcx, r15; hObject
0x180084cac  call    cs:__imp_CloseHandle
0x180084cb3  nop     dword ptr [rax+rax+00h]
0x180084cb8  mov     ecx, edi; dwErrCode
0x180084cba  call    cs:__imp_SetLastError
0x180084cc1  nop     dword ptr [rax+rax+00h]
0x180084cc6  mov     [rsi], rbx
  ... truncated ...
```
