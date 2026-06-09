# GetAASsigningKeys

- ea: `0x100474a74`
- end: `0x1004750e7`
- name: `GetAASsigningKeys`
- size: `1651`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x100475a58`

## callees

- `0x10040126c`
- `0x10040128c`
- `0x100430674`
- `0x1004306f0`
- `0x100431c4c`
- `0x10046ffa4`
- `0x100472534`
- `0x1004725b4`
- `0x1004727f4`
- `0x100473380`
- `0x100473a00`
- `0x100474a74`
- `0x1004754dc`
- `0x100475548`
- `0x1004764d0`
- `0x100476654`
- `0x10047699c`
- `0x100477e90`
- `0x100478034`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x100474b28`
- `KERNEL32!GetTickCount` at `0x100474e21`
- `KERNEL32!GetTickCount` at `0x100474b28`
- `KERNEL32!GetTickCount` at `0x100474e21`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100474df7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100474f76`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100474f7d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100475096`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100474df7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100474f76`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100474f7d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100475096`

## string_xrefs

- `0x100474b74`: `/.well-known/openid-configuration`
- `0x100474c1e`: `"jwks_uri"`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetAASsigningKeys(void (__fastcall **a1)(_QWORD, __int64, _QWORD), __int64 a2, __int64 a3, int a4)
{
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  __int64 CacheLock; // rax
  __int64 v11; // rbx
  DWORD v12; // eax
  int v13; // ebx
  __int64 v14; // rax
  const wchar_t *v15; // rax
  __int64 v16; // r8
  const wchar_t *v17; // rdx
  void *v18; // rdx
  unsigned int v19; // ebx
  __int64 v20; // r9
  _QWORD *v21; // r8
  char *v22; // r8
  _QWORD *v23; // rdx
  int *v24; // rdx
  bool v25; // r14
  int *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  __int64 v30; // rax
  void *v31; // rax
  void *v32; // rcx
  void *v33; // rcx
  __int64 v34; // rax
  void *v35; // rdx
  void *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r9
  __int64 v39; // rax
  void *v40; // rdx
  char v41; // [rsp+38h] [rbp-D0h]
  void *v42[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B8h]
  void *v44[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-A0h]
  _QWORD v46[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v47; // [rsp+88h] [rbp-80h]
  __int64 v48; // [rsp+90h] [rbp-78h]
  __int64 v49; // [rsp+98h] [rbp-70h]
  int v50[2]; // [rsp+A0h] [rbp-68h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-58h]
  _QWORD v52[3]; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int64 v53; // [rsp+D8h] [rbp-30h]
  _QWORD v54[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v55; // [rsp+F8h] [rbp-10h]
  int v56; // [rsp+108h] [rbp+0h]
  __int128 v57; // [rsp+110h] [rbp+8h]
  __int64 v58; // [rsp+120h] [rbp+18h]

  v48 = -2;
  v49 = a3;
  v8 = *(_QWORD **)&`Instance<std::map<std::basic_string<char16_t>,std::pair<unsigned long,std::vector<unsigned char>>>>::operator()'::`2'::s_var;
  if ( !*(_QWORD *)&`Instance<std::map<std::basic_string<char16_t>,std::pair<unsigned long,std::vector<unsigned char>>>>::operator()'::`2'::s_var )
  {
    v9 = operator new(0x10u);
    v8 = v9;
    *(_QWORD *)v50 = v9;
    if ( v9 )
    {
      *v9 = 0;
      v9[1] = 0;
      *v9 = std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<char16_t>,std::pair<unsigned long,std::vector<unsigned char>>,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,std::pair<unsigned long,std::vector<unsigned char>>>>,0>>::_Buyheadnode(v9);
    }
    else
    {
      v8 = 0;
    }
    *(_QWORD *)&`Instance<std::map<std::basic_string<char16_t>,std::pair<unsigned long,std::vector<unsigned char>>>>::operator()'::`2'::s_var = v8;
  }
  CacheLock = GetCacheLock();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)CacheLock + 8LL))(CacheLock);
  std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,DNSCacheEntry *,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,DNSCacheEntry *>>,0>>::find(
    v8,
    v50,
    a3);
  v11 = *(_QWORD *)v50;
  if ( *(_QWORD *)v50 == *v8 || (v12 = GetTickCount() - *(_DWORD *)(v11 + 64), v13 = 1, v12 >= 0x5265C00) )
    v13 = 0;
  v14 = GetCacheLock();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
  if ( !a4 && v13 )
  {
LABEL_81:
    v37 = GetCacheLock();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
    std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,DNSCacheEntry *,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,DNSCacheEntry *>>,0>>::find(
      v8,
      v50,
      a3);
    if ( *(_QWORD *)v50 != *v8 && a2 != *(_QWORD *)v50 + 72LL )
    {
      LOBYTE(v38) = v41;
      std::vector<unsigned char>::_Assign_range<unsigned char *>(
        a2,
        *(_QWORD *)(*(_QWORD *)v50 + 72LL),
        *(_QWORD *)(*(_QWORD *)v50 + 80LL),
        v38);
    }
    v39 = GetCacheLock();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39);
    std::basic_string<char16_t>::_Tidy_deallocate(a3);
    return 0;
  }
  *(_OWORD *)v42 = 0u;
  v43 = 0;
  v15 = L"/.well-known/openid-configuration";
  v16 = 0;
  do
  {
    ++v16;
    ++v15;
  }
  while ( *v15 );
  std::basic_string<char16_t>::append(a3, L"/.well-known/openid-configuration", v16);
  v17 = (const wchar_t *)a3;
  if ( *(_QWORD *)(a3 + 24) >= 8u )
    v17 = *(const wchar_t **)a3;
  if ( !(unsigned int)GetURLContents(a1, v17, v42) )
  {
    v18 = v42[0];
    if ( !v42[0] )
    {
LABEL_22:
      v19 = 400;
LABEL_52:
      std::basic_string<char16_t>::_Tidy_deallocate(a3);
      return v19;
    }
    if ( v43 - (unsigned __int64)v42[0] < 0x1000
      || ((__int64)v42[0] & 0x1F) == 0
      && (v18 = (void *)*((_QWORD *)v42[0] - 1), v18 < v42[0])
      && (unsigned __int64)((char *)v42[0] - (char *)v18 - 8) <= 0x1F )
    {
      operator delete(v18);
      *(_OWORD *)v42 = 0;
      v43 = 0;
      goto LABEL_22;
    }
LABEL_90:
    _invalid_parameter_noinfo_noreturn();
  }
  if ( jsonstr(v42[0], "\"jwks_uri\"", v50) && *(_QWORD *)v50 )
  {
    std::string::string(v52);
    *(_OWORD *)v44 = 0u;
    v45 = 0;
    v21 = v52;
    if ( v53 >= 0x10 )
      v21 = (_QWORD *)v52[0];
    v22 = (char *)v21 + v52[2];
    v23 = v52;
    if ( v53 >= 0x10 )
      v23 = (_QWORD *)v52[0];
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v50[0]) = 0;
    LOBYTE(v20) = v41;
    std::basic_string<char16_t>::_Construct<char *>(v50, v23, v22, v20);
    v24 = v50;
    if ( si128.m128i_i64[1] >= 8uLL )
      v24 = *(int **)v50;
    v25 = (unsigned int)GetURLContents(a1, (const wchar_t *)v24, v44) == 0;
    if ( si128.m128i_i64[1] >= 8uLL )
    {
      v26 = *(int **)v50;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
        || (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000
        && ((v50[0] & 0x1F) != 0
         || (v26 = *(int **)(*(_QWORD *)v50 - 8LL), (unsigned __int64)v26 >= *(_QWORD *)v50)
         || (unsigned __int64)(*(_QWORD *)v50 - (_QWORD)v26 - 8LL) > 0x1F) )
      {
        _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v26);
    }
    if ( v25 )
    {
      v27 = v44[0];
      if ( !v44[0] )
        goto LABEL_45;
      if ( v45 - (unsigned __int64)v44[0] < 0x1000
        || ((__int64)v44[0] & 0x1F) == 0
        && (v27 = (void *)*((_QWORD *)v44[0] - 1), v27 < v44[0])
        && (unsigned __int64)((char *)v44[0] - (char *)v27 - 8) <= 0x1F )
      {
        operator delete(v27);
        *(_OWORD *)v44 = 0;
        v45 = 0;
LABEL_45:
        std::string::_Tidy_deallocate(v52);
        v28 = v42[0];
        if ( v42[0] )
        {
          if ( v43 - (unsigned __int64)v42[0] >= 0x1000 )
          {
            if ( ((__int64)v42[0] & 0x1F) != 0 )
              goto LABEL_90;
            v28 = (void *)*((_QWORD *)v42[0] - 1);
            if ( v28 >= v42[0] || (unsigned __int64)((char *)v42[0] - (char *)v28 - 8) > 0x1F )
              goto LABEL_90;
          }
          operator delete(v28);
          *(_OWORD *)v42 = 0;
          v43 = 0;
        }
        v19 = 402;
        goto LABEL_52;
      }
LABEL_72:
      _invalid_parameter_noinfo_noreturn();
    }
    v30 = GetCacheLock();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,std::pair<unsigned long,std::vector<unsigned char>>,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,std::pair<unsigned long,std::vector<unsigned char>>>>,0>>::erase(
      v8,
      a3);
    LODWORD(v46[0]) = GetTickCount();
    std::vector<unsigned char>::vector<unsigned char>(&v46[1], v44);
    v55 = 0;
    std::basic_string<char16_t>::_Construct_lv_contents(v54, a3);
    v56 = v46[0];
    v57 = *(_OWORD *)&v46[1];
    v58 = v47;
    *(_OWORD *)&v46[1] = 0;
    v47 = 0;
    v31 = (void *)std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<char16_t>,std::pair<unsigned long,std::vector<unsigned char>>,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,std::pair<unsigned long,std::vector<unsigned char>>>>,0>>::_Buynode<std::pair<std::basic_string<char16_t>,std::pair<unsigned long,std::vector<unsigned char>>>>(
                    v8,
                    v54);
    std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,std::pair<unsigned long,std::vector<unsigned char>>,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,std::pair<unsigned long,std::vector<unsigned char>>>>,0>>::_Insert_nohint<std::pair<std::basic_string<char16_t> const,std::pair<unsigned long,std::vector<unsigned char>>> &,std::_Tree_node<std::pair<std::basic_string<char16_t> const,std::pair<unsigned long,std::vector<unsigned char>>>,void *> *>(
      (int)v8,
      (int)v50,
      0,
      (_DWORD)v31 + 32,
      v31);
    v32 = (void *)v57;
    if ( (_QWORD)v57 )
    {
      if ( (unsigned __int64)(v58 - v57) >= 0x1000 )
      {
        if ( (v57 & 0x1F) != 0 )
          goto LABEL_73;
        v32 = *(void **)(v57 - 8);
        if ( (unsigned __int64)v32 >= (unsigned __int64)v57 || (unsigned __int64)(v57 - (_QWORD)v32 - 8) > 0x1F )
          goto LABEL_73;
      }
      operator delete(v32);
    }
    if ( *((_QWORD *)&v55 + 1) < 8u )
    {
LABEL_67:
      v34 = GetCacheLock();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 24LL))(v34);
      v35 = v44[0];
      if ( v44[0] )
      {
        if ( v45 - (unsigned __int64)v44[0] >= 0x1000 )
        {
          if ( ((__int64)v44[0] & 0x1F) != 0 )
            goto LABEL_72;
          v35 = (void *)*((_QWORD *)v44[0] - 1);
          if ( v35 >= v44[0] || (unsigned __int64)((char *)v44[0] - (char *)v35 - 8) > 0x1F )
            goto LABEL_72;
        }
        operator delete(v35);
        *(_OWORD *)v44 = 0;
        v45 = 0;
      }
      std::string::_Tidy_deallocate(v52);
      v36 = v42[0];
      if ( v42[0] )
      {
        if ( v43 - (unsigned __int64)v42[0] >= 0x1000 )
        {
          if ( ((__int64)v42[0] & 0x1F) != 0 )
            goto LABEL_90;
          v36 = (void *)*((_QWORD *)v42[0] - 1);
          if ( v36 >= v42[0] || (unsigned __int64)((char *)v42[0] - (char *)v36 - 8) > 0x1F )
            goto LABEL_90;
        }
        operator delete(v36);
      }
      goto LABEL_81;
    }
    v33 = (void *)v54[0];
    if ( (unsigned __int64)(*((_QWORD *)&v55 + 1) + 1LL) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( (unsigned __int64)(2 * (*((_QWORD *)&v55 + 1) + 1LL)) < 0x1000
        || (v54[0] & 0x1F) == 0
        && (v33 = *(void **)(v54[0] - 8LL), (unsigned __int64)v33 < v54[0])
        && (unsigned __int64)(v54[0] - (_QWORD)v33 - 8LL) <= 0x1F )
      {
        operator delete(v33);
        goto LABEL_67;
      }
    }
LABEL_73:
    _invalid_parameter_noinfo_noreturn();
  }
  v40 = v42[0];
  if ( v42[0] )
  {
    if ( v43 - (unsigned __int64)v42[0] >= 0x1000 )
    {
      if ( ((__int64)v42[0] & 0x1F) != 0 )
        goto LABEL_90;
      v40 = (void *)*((_QWORD *)v42[0] - 1);
      if ( v40 >= v42[0] || (unsigned __int64)((char *)v42[0] - (char *)v40 - 8) > 0x1F )
        goto LABEL_90;
    }
    operator delete(v40);
    *(_OWORD *)v42 = 0;
    v43 = 0;
  }
  std::basic_string<char16_t>::_Tidy_deallocate(a3);
  return 401;
}

```

## disassembly

```asm
0x100474a74  mov     rax, rsp
0x100474a77  push    rbp
0x100474a78  push    rsi
0x100474a79  push    rdi
0x100474a7a  push    r12
0x100474a7c  push    r13
0x100474a7e  push    r14
0x100474a80  push    r15
0x100474a82  lea     rbp, [rax-68h]
0x100474a86  sub     rsp, 130h
0x100474a8d  mov     [rbp+60h+var_D8], 0FFFFFFFFFFFFFFFEh
0x100474a95  mov     [rax+20h], rbx
0x100474a99  mov     rax, cs:__security_cookie
0x100474aa0  xor     rax, rsp
0x100474aa3  mov     [rbp+60h+var_40], rax
0x100474aa7  mov     r14d, r9d
0x100474aaa  mov     rsi, r8
0x100474aad  mov     r12, rdx
0x100474ab0  mov     r15, rcx
0x100474ab3  mov     [rbp+60h+var_D0], r8
0x100474ab7  mov     rdi, cs:?s_var@?1???R?$Instance@V?$map@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@2@@std@@@@QEAAAEAV?$map@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@2@@std@@XZ@4PEAV23@EA; std::map<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>> * `Instance<std::map<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>>>::operator()(void)'::`2'::s_var
0x100474abe  xor     r13d, r13d
0x100474ac1  test    rdi, rdi
0x100474ac4  jnz     short loc_100474AF8
0x100474ac6  lea     ecx, [rdi+10h]; unsigned __int64
0x100474ac9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x100474ace  mov     rdi, rax
0x100474ad1  mov     qword ptr [rbp+60h+var_C8], rax
0x100474ad5  test    rax, rax
0x100474ad8  jz      short loc_100474AEE
0x100474ada  mov     [rax], r13
0x100474add  mov     [rax+8], r13
0x100474ae1  mov     rcx, rax
0x100474ae4  call    ?_Buyheadnode@?$_Tree_comp_alloc@V?$_Tmap_traits@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@PEAX@2@XZ; std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,std::pair<ulong,std::vector<uchar>>>>,0>>::_Buyheadnode(void)
0x100474ae9  mov     [rdi], rax
0x100474aec  jmp     short loc_100474AF1
0x100474aee  mov     rdi, r13
0x100474af1  mov     cs:?s_var@?1???R?$Instance@V?$map@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@2@@std@@@@QEAAAEAV?$map@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@2@@std@@XZ@4PEAV23@EA, rdi; std::map<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>> * `Instance<std::map<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>>>::operator()(void)'::`2'::s_var
0x100474af8  call    GetCacheLock
0x100474afd  mov     rdx, rax
0x100474b00  mov     rcx, [rax]
0x100474b03  mov     rax, [rcx+8]
0x100474b07  mov     rcx, rdx
0x100474b0a  call    cs:__guard_dispatch_icall_fptr
0x100474b10  mov     r8, rsi
0x100474b13  lea     rdx, [rbp+60h+var_C8]
0x100474b17  mov     rcx, rdi
0x100474b1a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUDNSCacheEntry@@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUDNSCacheEntry@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEAUDNSCacheEntry@@@std@@@std@@@std@@@2@AEBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,DNSCacheEntry *,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,DNSCacheEntry *>>,0>>::find(std::basic_string<char16_t> const &)
0x100474b1f  mov     rbx, qword ptr [rbp+60h+var_C8]
0x100474b23  cmp     rbx, [rdi]
0x100474b26  jz      short loc_100474B3D
0x100474b28  call    cs:__imp_GetTickCount
0x100474b2e  sub     eax, [rbx+40h]
0x100474b31  cmp     eax, 5265C00h
0x100474b36  mov     ebx, 1
0x100474b3b  jb      short loc_100474B40
0x100474b3d  mov     ebx, r13d
0x100474b40  call    GetCacheLock
0x100474b45  mov     rdx, rax
0x100474b48  mov     rcx, [rax]
0x100474b4b  mov     rax, [rcx+18h]
0x100474b4f  mov     rcx, rdx
0x100474b52  call    cs:__guard_dispatch_icall_fptr
0x100474b58  test    r14d, r14d
0x100474b5b  jnz     short loc_100474B65
0x100474b5d  test    ebx, ebx
0x100474b5f  jnz     loc_100474FEA
0x100474b65  mov     [rsp+160h+var_130+8], r13
0x100474b6a  mov     [rsp+160h+var_120], r13
0x100474b6f  mov     [rsp+160h+var_118], r13
0x100474b74  lea     rdx, aWellKnownOpeni; "/.well-known/openid-configuration"
0x100474b7b  mov     rax, rdx
0x100474b7e  mov     r8, r13
0x100474b81  inc     r8
0x100474b84  lea     rax, [rax+2]
0x100474b88  cmp     [rax], r13w
0x100474b8c  jnz     short loc_100474B81
0x100474b8e  mov     rcx, rsi
0x100474b91  call    ?append@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::append(char16_t const * const,unsigned __int64)
0x100474b96  mov     rdx, rsi
0x100474b99  cmp     qword ptr [rsi+18h], 8
0x100474b9e  jb      short loc_100474BA3
0x100474ba0  mov     rdx, [rsi]
0x100474ba3  lea     r8, [rsp+160h+var_130+8]
0x100474ba8  mov     rcx, r15
0x100474bab  call    GetURLContents
0x100474bb0  test    eax, eax
0x100474bb2  jnz     short loc_100474C1A
0x100474bb4  mov     rdx, [rsp+160h+var_130+8]
0x100474bb9  test    rdx, rdx
0x100474bbc  jz      short loc_100474C10
0x100474bbe  mov     rax, [rsp+160h+var_118]
0x100474bc3  sub     rax, rdx
0x100474bc6  mov     rcx, rdx
0x100474bc9  mov     ebx, 1000h
0x100474bce  cmp     rax, rbx
0x100474bd1  jb      short loc_100474BFA
0x100474bd3  test    cl, 1Fh
0x100474bd6  jnz     loc_100475096
0x100474bdc  mov     rdx, [rdx-8]
0x100474be0  cmp     rdx, rcx
0x100474be3  jnb     loc_100475096
0x100474be9  sub     rcx, rdx
0x100474bec  sub     rcx, 8
0x100474bf0  cmp     rcx, 1Fh
0x100474bf4  ja      loc_100475096
0x100474bfa  mov     rcx, rdx; void *
0x100474bfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100474c02  xorps   xmm0, xmm0
0x100474c05  movdqu  xmmword ptr [rsp+160h+var_130+8], xmm0
0x100474c0b  mov     [rsp+160h+var_118], r13
0x100474c10  mov     ebx, 190h
0x100474c15  jmp     loc_100474DE8
0x100474c1a  lea     r8, [rbp+60h+var_C8]
0x100474c1e  lea     rdx, aJwksUri; "\"jwks_uri\""
0x100474c25  mov     rcx, [rsp+160h+var_130+8]
0x100474c2a  call    jsonstr
0x100474c2f  test    rax, rax
0x100474c32  jz      loc_10047505C
0x100474c38  mov     r8, qword ptr [rbp+60h+var_C8]
0x100474c3c  test    r8, r8
0x100474c3f  jz      loc_10047505C
0x100474c45  lea     r9, [rsp+160h+var_130]
0x100474c4a  mov     rdx, rax
0x100474c4d  lea     rcx, [rbp+60h+var_A8]; void *
0x100474c51  call    ??$?0PEADX@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEAD0AEBV?$allocator@D@1@@Z; std::string::string(char *,char *,std::allocator<char> const &)
0x100474c56  nop
0x100474c57  mov     [rsp+160h+var_118+8], r13
0x100474c5c  mov     [rsp+160h+var_108], r13
0x100474c61  mov     [rsp+160h+var_100], r13
0x100474c66  lea     r8, [rbp+60h+var_A8]
0x100474c6a  cmp     [rbp+60h+var_90], 10h
0x100474c6f  cmovnb  r8, [rbp+60h+var_A8]
0x100474c74  add     r8, [rbp+60h+var_98]
0x100474c78  lea     rdx, [rbp+60h+var_A8]
0x100474c7c  cmp     [rbp+60h+var_90], 10h
0x100474c81  cmovnb  rdx, [rbp+60h+var_A8]
0x100474c86  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100474c8e  movdqu  [rbp+60h+var_B8], xmm0
0x100474c93  mov     word ptr [rbp+60h+var_C8], r13w
0x100474c98  mov     r9b, byte ptr [rsp+160h+var_130]
0x100474c9d  lea     rcx, [rbp+60h+var_C8]
0x100474ca1  call    ??$_Construct@PEAD@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXQEAD0Uforward_iterator_tag@1@@Z; std::basic_string<char16_t>::_Construct<char *>(char * const,char * const,std::forward_iterator_tag)
0x100474ca6  nop
0x100474ca7  lea     rdx, [rbp+60h+var_C8]
0x100474cab  cmp     qword ptr [rbp+60h+var_B8+8], 8
0x100474cb0  cmovnb  rdx, qword ptr [rbp+60h+var_C8]
0x100474cb5  lea     r8, [rsp+160h+var_118+8]
0x100474cba  mov     rcx, r15
0x100474cbd  call    GetURLContents
0x100474cc2  test    eax, eax
0x100474cc4  setz    r14b
0x100474cc8  mov     ebx, 1000h
0x100474ccd  mov     r15, 7FFFFFFFFFFFFFFFh
0x100474cd7  mov     rax, qword ptr [rbp+60h+var_B8+8]
0x100474cdb  cmp     rax, 8
0x100474cdf  jb      short loc_100474D28
0x100474ce1  inc     rax
0x100474ce4  mov     rcx, qword ptr [rbp+60h+var_C8]
0x100474ce8  mov     rdx, rcx
0x100474ceb  cmp     rax, r15
0x100474cee  ja      loc_100474DF7
0x100474cf4  add     rax, rax
0x100474cf7  cmp     rax, rbx
0x100474cfa  jb      short loc_100474D23
0x100474cfc  test    dl, 1Fh
0x100474cff  jnz     loc_100474DF7
0x100474d05  mov     rcx, [rcx-8]; void *
0x100474d09  cmp     rcx, rdx
0x100474d0c  jnb     loc_100474DF7
0x100474d12  sub     rdx, rcx
0x100474d15  sub     rdx, 8
0x100474d19  cmp     rdx, 1Fh
0x100474d1d  ja      loc_100474DF7
0x100474d23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100474d28  test    r14b, r14b
0x100474d2b  jz      loc_100474DFE
0x100474d31  mov     rcx, [rsp+160h+var_118+8]
0x100474d36  test    rcx, rcx
0x100474d39  jz      short loc_100474D85
0x100474d3b  mov     rax, [rsp+160h+var_100]
0x100474d40  sub     rax, rcx
0x100474d43  mov     rdx, rcx
0x100474d46  cmp     rax, rbx
0x100474d49  jb      short loc_100474D72
0x100474d4b  test    dl, 1Fh
0x100474d4e  jnz     loc_100474F76
0x100474d54  mov     rcx, [rcx-8]; void *
0x100474d58  cmp     rcx, rdx
0x100474d5b  jnb     loc_100474F76
0x100474d61  sub     rdx, rcx
0x100474d64  sub     rdx, 8
0x100474d68  cmp     rdx, 1Fh
0x100474d6c  ja      loc_100474F76
0x100474d72  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100474d77  xorps   xmm0, xmm0
0x100474d7a  movdqu  xmmword ptr [rsp+160h+var_118+8], xmm0
0x100474d80  mov     [rsp+160h+var_100], r13
0x100474d85  lea     rcx, [rbp+60h+var_A8]
0x100474d89  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::string::_Tidy_deallocate(void)
0x100474d8e  nop
0x100474d8f  mov     rcx, [rsp+160h+var_130+8]
0x100474d94  test    rcx, rcx
0x100474d97  jz      short loc_100474DE3
0x100474d99  mov     rax, [rsp+160h+var_118]
0x100474d9e  sub     rax, rcx
0x100474da1  mov     rdx, rcx
0x100474da4  cmp     rax, rbx
0x100474da7  jb      short loc_100474DD0
0x100474da9  test    dl, 1Fh
0x100474dac  jnz     loc_100475096
0x100474db2  mov     rcx, [rcx-8]; void *
0x100474db6  cmp     rcx, rdx
0x100474db9  jnb     loc_100475096
0x100474dbf  sub     rdx, rcx
0x100474dc2  sub     rdx, 8
0x100474dc6  cmp     rdx, 1Fh
0x100474dca  ja      loc_100475096
0x100474dd0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100474dd5  xorps   xmm0, xmm0
0x100474dd8  movdqu  xmmword ptr [rsp+160h+var_130+8], xmm0
0x100474dde  mov     [rsp+160h+var_118], r13
0x100474de3  mov     ebx, 192h
0x100474de8  mov     rcx, rsi
0x100474deb  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x100474df0  mov     eax, ebx
0x100474df2  jmp     loc_1004750C0
0x100474df7  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x100474dfe  call    GetCacheLock
0x100474e03  mov     rdx, rax
0x100474e06  mov     rcx, [rax]
0x100474e09  mov     rax, [rcx+8]
0x100474e0d  mov     rcx, rdx
0x100474e10  call    cs:__guard_dispatch_icall_fptr
0x100474e16  mov     rdx, rsi
0x100474e19  mov     rcx, rdi
0x100474e1c  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,std::pair<ulong,std::vector<uchar>>>>,0>>::erase(std::basic_string<char16_t> const &)
0x100474e21  call    cs:__imp_GetTickCount
0x100474e27  mov     dword ptr [rsp+160h+var_F8], eax
0x100474e2b  lea     rdx, [rsp+160h+var_118+8]
0x100474e30  lea     rcx, [rsp+160h+var_F8+8]
0x100474e35  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x100474e3a  nop
0x100474e3b  xorps   xmm0, xmm0
0x100474e3e  movdqa  [rbp+60h+var_70], xmm0
0x100474e43  mov     rdx, rsi
0x100474e46  lea     rcx, [rbp+60h+var_80]
0x100474e4a  call    ?_Construct_lv_contents@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXAEBV12@@Z; std::basic_string<char16_t>::_Construct_lv_contents(std::basic_string<char16_t> const &)
0x100474e4f  mov     eax, dword ptr [rsp+160h+var_F8]
0x100474e53  mov     [rbp+60h+var_60], eax
0x100474e56  mov     rax, qword ptr [rsp+160h+var_F8+8]
0x100474e5b  mov     [rbp+60h+var_58], rax
0x100474e5f  mov     rax, qword ptr [rsp+160h+var_F8+10h]
0x100474e64  mov     [rbp+60h+var_50], rax
0x100474e68  mov     rax, [rbp+60h+var_E0]
0x100474e6c  mov     [rbp+60h+var_48], rax
0x100474e70  xorps   xmm0, xmm0
0x100474e73  movdqu  xmmword ptr [rsp+160h+var_F8+8], xmm0
0x100474e79  mov     [rbp+60h+var_E0], r13
0x100474e7d  lea     rdx, [rbp+60h+var_80]
0x100474e81  mov     rcx, rdi
0x100474e84  call    ??$_Buynode@U?$pair@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@?$_Tree_comp_alloc@V?$_Tmap_traits@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@PEAX@1@$$QEAU?$pair@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@1@@Z; std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,std::pair<ulong,std::vector<uchar>>>>,0>>::_Buynode<std::pair<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>>>(std::pair<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>> &&)
0x100474e89  lea     r9, [rax+20h]; int
0x100474e8d  mov     [rsp+20h], rax; void *
0x100474e92  xor     r8d, r8d; int
0x100474e95  lea     rdx, [rbp+60h+var_C8]; int
0x100474e99  mov     rcx, rdi; int
0x100474e9c  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@U?$less@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@U?$pair@KV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<char16_t>,std::pair<ulong,std::vector<uchar>>,std::less<std::basic_string<char16_t>>,std::allocator<std::pair<std::basic_string<char16_t> const,std::pair<ulong,std::vector<uchar>>>>,0>>::_Insert_nohint<std::pair<std::basic_string<char16_t> const,std::pair<ulong,std::vector<uchar>>> &,std::_Tree_node<std::pair<std::basic_string<char16_t> const,std::pair<ulong,std::vector<uchar>>>,void *> *>(bool,std::pair<std::basic_string<char16_t> const,std::pair<ulong,std::vector<uchar>>> &,std::_Tree_node<std::pair<std::basic_string<char16_t> const,std::pair<ulong,std::vector<uchar>>>,void *> *)
0x100474ea1  nop
0x100474ea2  mov     rcx, [rbp+60h+var_58]
0x100474ea6  test    rcx, rcx
0x100474ea9  jz      short loc_100474EE6
0x100474eab  mov     rax, [rbp+60h+var_48]
0x100474eaf  sub     rax, rcx
0x100474eb2  mov     rdx, rcx
0x100474eb5  cmp     rax, rbx
0x100474eb8  jb      short loc_100474EE1
0x100474eba  test    dl, 1Fh
0x100474ebd  jnz     loc_100474F7D
0x100474ec3  mov     rcx, [rcx-8]; void *
0x100474ec7  cmp     rcx, rdx
0x100474eca  jnb     loc_100474F7D
0x100474ed0  sub     rdx, rcx
0x100474ed3  sub     rdx, 8
0x100474ed7  cmp     rdx, 1Fh
0x100474edb  ja      loc_100474F7D
0x100474ee1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100474ee6  mov     rax, qword ptr [rbp+60h+var_70+8]
0x100474eea  cmp     rax, 8
0x100474eee  jb      short loc_100474F28
0x100474ef0  inc     rax
0x100474ef3  mov     rcx, [rbp+60h+var_80]
0x100474ef7  mov     rdx, rcx
0x100474efa  cmp     rax, r15
0x100474efd  ja      short loc_100474F7D
0x100474eff  add     rax, rax
0x100474f02  cmp     rax, rbx
0x100474f05  jb      short loc_100474F22
0x100474f07  test    dl, 1Fh
0x100474f0a  jnz     short loc_100474F7D
  ... truncated ...
```
