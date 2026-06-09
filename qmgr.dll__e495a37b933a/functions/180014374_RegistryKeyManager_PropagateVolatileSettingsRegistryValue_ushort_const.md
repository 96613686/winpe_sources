# RegistryKeyManager::PropagateVolatileSettingsRegistryValue(ushort const *)

- ea: `0x180014374`
- end: `0x180014a1b`
- name: `?PropagateVolatileSettingsRegistryValue@RegistryKeyManager@@QEAAJPEBG@Z`
- size: `1703`
- prototype: `__int64 __fastcall(RegistryKeyManager *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014a30`
- `0x1800466a4`
- `0x180046948`

## callees

- `0x180014374`
- `0x18002c6e0`
- `0x180045d90`
- `0x1800634e0`
- `0x18008ddc8`
- `0x18008df60`
- `0x18008fadc`
- `0x180091acc`
- `0x180091afc`
- `0x180091b20`
- `0x180099740`
- `0x18009c0b4`
- `0x18009cd0c`
- `0x18009d024`
- `0x1800a1114`
- `0x1800a3420`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800147a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001489d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800147a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001489d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001491b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001491b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800143e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014428`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800143e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014428`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001450c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014624`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014759`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001450c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014624`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014759`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegistryKeyManager::PropagateVolatileSettingsRegistryValue(
        RegistryKeyManager *this,
        const unsigned __int16 *a2)
{
  char *v4; // r14
  __int64 inserted; // rcx
  __int64 v6; // rax
  int v7; // r9d
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rdi
  size_t v15; // rdi
  const wchar_t *v16; // rdx
  size_t v17; // r14
  const wchar_t *v18; // rcx
  size_t v19; // r8
  __int64 result; // rax
  HKEY RegistryKey; // rbx
  HKEY v22; // rdi
  int v23; // eax
  int v24; // eax
  int v25; // eax
  const ComError *v26; // rbx
  DWORD Type; // [rsp+30h] [rbp-228h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-224h] BYREF
  __int128 v29; // [rsp+38h] [rbp-220h]
  __int128 v30; // [rsp+50h] [rbp-208h] BYREF
  __int128 v31; // [rsp+60h] [rbp-1F8h] BYREF
  char *v32; // [rsp+70h] [rbp-1E8h] BYREF
  __int64 v33; // [rsp+78h] [rbp-1E0h] BYREF
  __int64 v34; // [rsp+80h] [rbp-1D8h] BYREF
  const ComError *v35; // [rsp+88h] [rbp-1D0h] BYREF
  char *v36; // [rsp+90h] [rbp-1C8h]
  _BYTE v37[16]; // [rsp+98h] [rbp-1C0h] BYREF
  LPBYTE lpData[3]; // [rsp+A8h] [rbp-1B0h] BYREF
  void **pExceptionObject; // [rsp+C0h] [rbp-198h] BYREF
  __int128 v40; // [rsp+C8h] [rbp-190h]
  int v41; // [rsp+D8h] [rbp-180h]
  int v42; // [rsp+DCh] [rbp-17Ch]
  int v43; // [rsp+E0h] [rbp-178h]
  void **v44; // [rsp+120h] [rbp-138h] BYREF
  __int128 v45; // [rsp+128h] [rbp-130h]
  int v46; // [rsp+138h] [rbp-120h]
  int v47; // [rsp+13Ch] [rbp-11Ch]
  int v48; // [rsp+140h] [rbp-118h]
  void **v49; // [rsp+180h] [rbp-D8h] BYREF
  __int128 v50; // [rsp+188h] [rbp-D0h]
  int v51; // [rsp+198h] [rbp-C0h]
  int v52; // [rsp+19Ch] [rbp-BCh]
  int v53; // [rsp+1A0h] [rbp-B8h]
  wchar_t *S2[2]; // [rsp+1E0h] [rbp-78h] BYREF
  size_t v55; // [rsp+1F0h] [rbp-68h]
  unsigned __int64 v56; // [rsp+1F8h] [rbp-60h]
  wchar_t *S1[2]; // [rsp+200h] [rbp-58h] BYREF
  size_t N; // [rsp+210h] [rbp-48h]
  unsigned __int64 v59; // [rsp+218h] [rbp-40h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids, a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v32 = (char *)this + 8;
  v34 = 0;
  *(_OWORD *)S1 = 0;
  N = 0;
  v59 = 0;
  std::wstring::_Construct_empty(S1);
  LODWORD(v30) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v36 = (char *)this + 8;
  v4 = (char *)this + 48;
  inserted = *((_QWORD *)this + 6);
  v6 = *(_QWORD *)(inserted + 8);
  v29 = (unsigned __int64)v6;
  while ( !*(_BYTE *)(v6 + 25) )
  {
    *(_QWORD *)&v29 = v6;
    if ( *(int *)(v6 + 32) >= 0 )
    {
      DWORD2(v29) = 1;
      inserted = v6;
    }
    else
    {
      DWORD2(v29) = 0;
      v6 += 16;
    }
    v6 = *(_QWORD *)v6;
  }
  try
  {
    if ( *(_BYTE *)(inserted + 25) || *(int *)(inserted + 32) > 0 )
    {
      std::_Tree<std::_Tmap_traits<enum NotifiableSystemEvent,ITriggerableNotifier *,std::less<enum NotifiableSystemEvent>,std::allocator<std::pair<enum NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1((char *)this + 48);
      *(_QWORD *)&v31 = &v30;
      v8 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(
             (unsigned int)v37,
             (int)this + 48,
             *(_QWORD *)v4,
             v7,
             (__int64)&v31);
      v9 = *(_QWORD *)(v8 + 8);
      *(_QWORD *)(v8 + 8) = 0;
      std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>(v37);
      v31 = v29;
      inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
                   (char *)this + 48,
                   &v31,
                   v9);
    }
    (*(void (__fastcall **)(_QWORD, __int64 *, wchar_t **))(**(_QWORD **)(inserted + 40) + 24LL))(
      *(_QWORD *)(inserted + 40),
      &v34,
      S1);
    if ( this != (RegistryKeyManager *)-8LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v33 = 0;
    *(_OWORD *)S2 = 0;
    v55 = 0;
    v56 = 0;
    std::wstring::_Construct_empty(S2);
    LODWORD(v31) = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v36 = (char *)this + 8;
    v10 = *(_QWORD *)v4;
    v11 = *(_QWORD *)(*(_QWORD *)v4 + 8LL);
    v29 = (unsigned __int64)v11;
    while ( !*(_BYTE *)(v11 + 25) )
    {
      *(_QWORD *)&v29 = v11;
      if ( *(_DWORD *)(v11 + 32) >= (int)v31 )
      {
        DWORD2(v29) = 1;
        v10 = v11;
      }
      else
      {
        DWORD2(v29) = 0;
        v11 += 16;
      }
      v11 = *(_QWORD *)v11;
    }
    if ( *(_BYTE *)(v10 + 25) || (int)v31 < *(_DWORD *)(v10 + 32) )
    {
      std::_Tree<std::_Tmap_traits<enum NotifiableSystemEvent,ITriggerableNotifier *,std::less<enum NotifiableSystemEvent>,std::allocator<std::pair<enum NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1((char *)this + 48);
      *(_QWORD *)&v30 = &v31;
      v13 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(
              (unsigned int)v37,
              (int)this + 48,
              *(_QWORD *)v4,
              v12,
              (__int64)&v30);
      v14 = *(_QWORD *)(v13 + 8);
      *(_QWORD *)(v13 + 8) = 0;
      std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>(v37);
      v30 = v29;
      v10 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
              (char *)this + 48,
              &v30,
              v14);
    }
    (*(void (__fastcall **)(_QWORD, __int64 *, wchar_t **))(**(_QWORD **)(v10 + 40) + 24LL))(
      *(_QWORD *)(v10 + 40),
      &v33,
      S2);
    if ( this != (RegistryKeyManager *)-8LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( v34 != v33 )
      goto LABEL_46;
    v15 = v55;
    v16 = (const wchar_t *)S2;
    if ( v56 > 7 )
      v16 = S2[0];
    v17 = N;
    v18 = (const wchar_t *)S1;
    if ( v59 > 7 )
      v18 = S1[0];
    v19 = v55;
    if ( v55 >= N )
      v19 = N;
    if ( !wmemcmp(v18, v16, v19) && v17 >= v15 && v17 <= v15 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids);
      if ( v56 > 7 )
        std::_Deallocate<16>(S2[0], 2 * v56 + 2);
      v55 = 0;
      v56 = 7;
      LOWORD(S2[0]) = 0;
      if ( v59 > 7 )
        std::_Deallocate<16>(S1[0], 2 * v59 + 2);
      N = 0;
      v59 = 7;
      LOWORD(S1[0]) = 0;
      if ( this != (RegistryKeyManager *)-8LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      result = 0;
    }
    else
    {
LABEL_46:
      RegistryKey = (HKEY)RegistryKeyManager::GetRegistryKey(this, 0);
      v22 = (HKEY)RegistryKeyManager::GetRegistryKey(this, 1);
      Type = 0;
      cbData = 0;
      v23 = RegQueryValueExW(RegistryKey, a2, 0, &Type, 0, &cbData);
      if ( v23 == 2 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids, a2);
        std::wstring::~wstring(S2);
        std::wstring::~wstring(S1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v32);
        result = 0;
      }
      else
      {
        if ( v23 )
        {
          if ( v23 > 0 )
            v23 = (unsigned __int16)v23 | 0x80070000;
          v40 = 0;
          pExceptionObject = &ComError::`vftable';
          v41 = v23;
          v42 = 147;
          v43 = 1;
          throw (ComError *)&pExceptionObject;
        }
        std::vector<unsigned char>::vector<unsigned char>(lpData, cbData);
        v24 = RegQueryValueExW(RegistryKey, a2, 0, &Type, lpData[0], &cbData);
        if ( v24 )
        {
          if ( v24 > 0 )
            v24 = (unsigned __int16)v24 | 0x80070000;
          v45 = 0;
          v44 = &ComError::`vftable';
          v46 = v24;
          v47 = 157;
          v48 = 1;
          throw (ComError *)&v44;
        }
        v25 = RegSetValueExW(v22, a2, 0, Type, lpData[0], cbData);
        if ( v25 )
        {
          if ( v25 > 0 )
            v25 = (unsigned __int16)v25 | 0x80070000;
          v50 = 0;
          v49 = &ComError::`vftable';
          v51 = v25;
          v52 = 164;
          v53 = 1;
          throw (ComError *)&v49;
        }
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids, a2);
        std::vector<unsigned char>::_Tidy(lpData);
        std::wstring::~wstring(S2);
        std::wstring::~wstring(S1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v32);
        result = 0;
      }
    }
  }
  catch ( const ComError *v35 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v26 = v35;
    }
    else
    {
      v26 = v35;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids,
        *((unsigned int *)v26 + 6),
        *((_DWORD *)v26 + 7));
    }
    Type = *((_DWORD *)v26 + 6);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v32);
    return Type;
  }
  if ( *(_BYTE *)(inserted + 25) || *(int *)(inserted + 32) > 0 )
  {
    std::_Tree<std::_Tmap_traits<enum NotifiableSystemEvent,ITriggerableNotifier *,std::less<enum NotifiableSystemEvent>,std::allocator<std::pair<enum NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1((char *)this + 48);
    *(_QWORD *)&v31 = &v30;
    v8 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(
           (unsigned int)v37,
           (int)this + 48,
           *(_QWORD *)v4,
           v7,
           (__int64)&v31);
    v9 = *(_QWORD *)(v8 + 8);
    *(_QWORD *)(v8 + 8) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>(v37);
    v31 = v29;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
                 (char *)this + 48,
                 &v31,
                 v9);
  }
}

```

## disassembly

```asm
0x180014374  mov     [rsp+arg_10], rbx
0x180014379  mov     [rsp+arg_18], rsi
0x18001437e  push    rdi
0x18001437f  push    r12
0x180014381  push    r13
0x180014383  push    r14
0x180014385  push    r15
0x180014387  sub     rsp, 230h
0x18001438e  mov     rax, cs:__security_cookie
0x180014395  xor     rax, rsp
0x180014398  mov     [rsp+258h+var_38], rax
0x1800143a0  mov     r15, rdx
0x1800143a3  mov     r13, rcx
0x1800143a6  lea     rax, WPP_GLOBAL_Control
0x1800143ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143b4  mov     esi, 1
0x1800143b9  cmp     rcx, rax
0x1800143bc  jz      short loc_1800143DA
0x1800143be  test    [rcx+1Ch], sil
0x1800143c2  jz      short loc_1800143DA
0x1800143c4  lea     edx, [rsi+0Dh]
0x1800143c7  mov     r9, r15
0x1800143ca  lea     r8, WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids
0x1800143d1  mov     rcx, [rcx+10h]
0x1800143d5  call    WPP_SF_S
0x1800143da  lea     rbx, [r13+8]
0x1800143de  mov     rcx, rbx; lpCriticalSection
0x1800143e1  call    cs:__imp_EnterCriticalSection
0x1800143e7  mov     [rsp+258h+var_1E8], rbx
0x1800143ec  xor     r12d, r12d
0x1800143ef  mov     [rsp+258h+var_1D8], r12
0x1800143f7  xorps   xmm0, xmm0
0x1800143fa  movups  xmmword ptr [rsp+258h+S1], xmm0
0x180014402  mov     [rsp+258h+N], r12
0x18001440a  mov     [rsp+258h+var_40], r12
0x180014412  lea     rcx, [rsp+258h+S1]
0x18001441a  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001441f  nop
0x180014420  mov     dword ptr [rsp+258h+var_208], r12d
0x180014425  mov     rcx, rbx; lpCriticalSection
0x180014428  call    cs:__imp_EnterCriticalSection
0x18001442e  mov     [rsp+258h+var_1C8], rbx
0x180014436  lea     r14, [r13+30h]
0x18001443a  mov     rcx, [r14]
0x18001443d  mov     rax, [rcx+8]
0x180014441  mov     qword ptr [rsp+258h+var_220], rax
0x180014446  mov     qword ptr [rsp+258h+var_220+8], r12
0x18001444b  mov     edx, dword ptr [rsp+258h+var_208]
0x18001444f  cmp     [rax+19h], r12b
0x180014453  jnz     short loc_180014476
0x180014455  mov     qword ptr [rsp+258h+var_220], rax
0x18001445a  cmp     [rax+20h], edx
0x18001445d  jge     short loc_18001446A
0x18001445f  mov     dword ptr [rsp+258h+var_220+8], r12d
0x180014464  add     rax, 10h
0x180014468  jmp     short loc_180014471
0x18001446a  mov     dword ptr [rsp+258h+var_220+8], esi
0x18001446e  mov     rcx, rax
0x180014471  mov     rax, [rax]
0x180014474  jmp     short loc_18001444F
0x180014476  cmp     [rcx+19h], r12b
0x18001447a  jnz     short loc_180014481
0x18001447c  cmp     edx, [rcx+20h]
0x18001447f  jge     short loc_1800144E3
0x180014481  mov     rcx, r14
0x180014484  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@W4NotifiableSystemEvent@@PEAVITriggerableNotifier@@U?$less@W4NotifiableSystemEvent@@@std@@V?$allocator@U?$pair@$$CBW4NotifiableSystemEvent@@PEAVITriggerableNotifier@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<NotifiableSystemEvent,ITriggerableNotifier *,std::less<NotifiableSystemEvent>,std::allocator<std::pair<NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1(void)
0x180014489  lea     rax, [rsp+258h+var_208]
0x18001448e  mov     qword ptr [rsp+258h+var_1F8], rax
0x180014493  lea     rax, [rsp+258h+var_1F8]
0x180014498  mov     [rsp+258h+lpData], rax
0x18001449d  mov     r8, [r14]
0x1800144a0  mov     rdx, r14
0x1800144a3  lea     rcx, [rsp+258h+var_1C0]
0x1800144ab  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBW4RegistryKeyType@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBW4RegistryKeyType@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>> &,std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *> *,std::piecewise_construct_t const &,std::tuple<RegistryKeyType const &> &&,std::tuple<> &&)
0x1800144b0  mov     rdi, [rax+8]
0x1800144b4  mov     [rax+8], r12
0x1800144b8  lea     rcx, [rsp+258h+var_1C0]
0x1800144c0  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4_CRM_CLIENT_ID@@PEAX@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>(void)
0x1800144c5  movups  xmm0, [rsp+258h+var_220]
0x1800144ca  movdqu  [rsp+258h+var_1F8], xmm0
0x1800144d0  mov     r8, rdi
0x1800144d3  lea     rdx, [rsp+258h+var_1F8]
0x1800144d8  mov     rcx, r14
0x1800144db  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CEncryptedCredentials *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> *>,std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> * const)
0x1800144e0  mov     rcx, rax
0x1800144e3  mov     rcx, [rcx+28h]
0x1800144e7  mov     rax, [rcx]
0x1800144ea  lea     r8, [rsp+258h+S1]
0x1800144f2  lea     rdx, [rsp+258h+var_1D8]
0x1800144fa  mov     rax, [rax+18h]
0x1800144fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014503  nop
0x180014504  test    rbx, rbx
0x180014507  jz      short loc_180014512
0x180014509  mov     rcx, rbx; lpCriticalSection
0x18001450c  call    cs:__imp_LeaveCriticalSection
0x180014512  mov     [rsp+258h+var_1E0], r12
0x180014517  xorps   xmm0, xmm0
0x18001451a  movups  xmmword ptr [rsp+258h+S2], xmm0
0x180014522  mov     [rsp+258h+var_68], r12
0x18001452a  mov     [rsp+258h+var_60], r12
0x180014532  lea     rcx, [rsp+258h+S2]
0x18001453a  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001453f  nop
0x180014540  mov     dword ptr [rsp+258h+var_1F8], esi
0x180014544  mov     rcx, rbx; lpCriticalSection
0x180014547  call    cs:__imp_EnterCriticalSection
0x18001454d  mov     [rsp+258h+var_1C8], rbx
0x180014555  mov     rcx, [r14]
0x180014558  mov     rax, [rcx+8]
0x18001455c  mov     qword ptr [rsp+258h+var_220], rax
0x180014561  mov     qword ptr [rsp+258h+var_220+8], r12
0x180014566  mov     edx, dword ptr [rsp+258h+var_1F8]
0x18001456a  cmp     [rax+19h], r12b
0x18001456e  jnz     short loc_180014591
0x180014570  mov     qword ptr [rsp+258h+var_220], rax
0x180014575  cmp     [rax+20h], edx
0x180014578  jge     short loc_180014585
0x18001457a  mov     dword ptr [rsp+258h+var_220+8], r12d
0x18001457f  add     rax, 10h
0x180014583  jmp     short loc_18001458C
0x180014585  mov     dword ptr [rsp+258h+var_220+8], esi
0x180014589  mov     rcx, rax
0x18001458c  mov     rax, [rax]
0x18001458f  jmp     short loc_18001456A
0x180014591  cmp     [rcx+19h], r12b
0x180014595  jnz     short loc_18001459C
0x180014597  cmp     edx, [rcx+20h]
0x18001459a  jge     short loc_1800145FE
0x18001459c  mov     rcx, r14
0x18001459f  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@W4NotifiableSystemEvent@@PEAVITriggerableNotifier@@U?$less@W4NotifiableSystemEvent@@@std@@V?$allocator@U?$pair@$$CBW4NotifiableSystemEvent@@PEAVITriggerableNotifier@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<NotifiableSystemEvent,ITriggerableNotifier *,std::less<NotifiableSystemEvent>,std::allocator<std::pair<NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1(void)
0x1800145a4  lea     rax, [rsp+258h+var_1F8]
0x1800145a9  mov     qword ptr [rsp+258h+var_208], rax
0x1800145ae  lea     rax, [rsp+258h+var_208]
0x1800145b3  mov     [rsp+258h+lpData], rax
0x1800145b8  mov     r8, [r14]
0x1800145bb  mov     rdx, r14
0x1800145be  lea     rcx, [rsp+258h+var_1C0]
0x1800145c6  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBW4RegistryKeyType@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBW4RegistryKeyType@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>> &,std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *> *,std::piecewise_construct_t const &,std::tuple<RegistryKeyType const &> &&,std::tuple<> &&)
0x1800145cb  mov     rdi, [rax+8]
0x1800145cf  mov     [rax+8], r12
0x1800145d3  lea     rcx, [rsp+258h+var_1C0]
0x1800145db  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4_CRM_CLIENT_ID@@PEAX@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>(void)
0x1800145e0  movups  xmm0, [rsp+258h+var_220]
0x1800145e5  movdqu  [rsp+258h+var_208], xmm0
0x1800145eb  mov     r8, rdi
0x1800145ee  lea     rdx, [rsp+258h+var_208]
0x1800145f3  mov     rcx, r14
0x1800145f6  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CEncryptedCredentials *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> *>,std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> * const)
0x1800145fb  mov     rcx, rax
0x1800145fe  mov     rcx, [rcx+28h]
0x180014602  mov     rax, [rcx]
0x180014605  lea     r8, [rsp+258h+S2]
0x18001460d  lea     rdx, [rsp+258h+var_1E0]
0x180014612  mov     rax, [rax+18h]
0x180014616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001461b  nop
0x18001461c  test    rbx, rbx
0x18001461f  jz      short loc_18001462A
0x180014621  mov     rcx, rbx; lpCriticalSection
0x180014624  call    cs:__imp_LeaveCriticalSection
0x18001462a  mov     rax, [rsp+258h+var_1E0]
0x18001462f  cmp     [rsp+258h+var_1D8], rax
0x180014637  jnz     loc_180014766
0x18001463d  mov     rdi, [rsp+258h+var_68]
0x180014645  lea     rdx, [rsp+258h+S2]
0x18001464d  cmp     [rsp+258h+var_60], 7
0x180014656  cmova   rdx, [rsp+258h+S2]; S2
0x18001465f  mov     r14, [rsp+258h+N]
0x180014667  lea     rcx, [rsp+258h+S1]
0x18001466f  cmp     [rsp+258h+var_40], 7
0x180014678  cmova   rcx, [rsp+258h+S1]; S1
0x180014681  mov     r8, rdi
0x180014684  cmp     rdi, r14
0x180014687  cmovnb  r8, r14; N
0x18001468b  call    wmemcmp
0x180014690  test    eax, eax
0x180014692  jnz     loc_180014766
0x180014698  cmp     r14, rdi
0x18001469b  jb      loc_180014766
0x1800146a1  ja      loc_180014766
0x1800146a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146ae  lea     rax, WPP_GLOBAL_Control
0x1800146b5  cmp     rcx, rax
0x1800146b8  jz      short loc_1800146D6
0x1800146ba  test    [rcx+1Ch], sil
0x1800146be  jz      short loc_1800146D6
0x1800146c0  mov     edx, 0Fh
0x1800146c5  lea     r8, WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids
0x1800146cc  mov     rcx, [rcx+10h]
0x1800146d0  call    WPP_SF_
0x1800146d5  nop
0x1800146d6  mov     rdx, [rsp+258h+var_60]
0x1800146de  mov     edi, 7
0x1800146e3  cmp     rdx, rdi
0x1800146e6  jbe     short loc_1800146FD
0x1800146e8  lea     rdx, ds:2[rdx*2]
0x1800146f0  mov     rcx, [rsp+258h+S2]
0x1800146f8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800146fd  mov     [rsp+258h+var_68], r12
0x180014705  mov     [rsp+258h+var_60], rdi
0x18001470d  mov     word ptr [rsp+258h+S2], r12w
0x180014716  mov     rdx, [rsp+258h+var_40]
0x18001471e  cmp     rdx, rdi
0x180014721  jbe     short loc_180014738
0x180014723  lea     rdx, ds:2[rdx*2]
0x18001472b  mov     rcx, [rsp+258h+S1]
0x180014733  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014738  mov     [rsp+258h+N], r12
0x180014740  mov     [rsp+258h+var_40], rdi
0x180014748  mov     word ptr [rsp+258h+S1], r12w
0x180014751  test    rbx, rbx
0x180014754  jz      short loc_18001475F
0x180014756  mov     rcx, rbx; lpCriticalSection
0x180014759  call    cs:__imp_LeaveCriticalSection
0x18001475f  xor     eax, eax
0x180014761  jmp     loc_1800149EE
0x180014766  xor     edx, edx
0x180014768  mov     rcx, r13
0x18001476b  call    ?GetRegistryKey@RegistryKeyManager@@QEAAPEAUHKEY__@@W4RegistryKeyType@@@Z; RegistryKeyManager::GetRegistryKey(RegistryKeyType)
0x180014770  mov     rbx, rax
0x180014773  mov     edx, esi
0x180014775  mov     rcx, r13
0x180014778  call    ?GetRegistryKey@RegistryKeyManager@@QEAAPEAUHKEY__@@W4RegistryKeyType@@@Z; RegistryKeyManager::GetRegistryKey(RegistryKeyType)
0x18001477d  mov     rdi, rax
0x180014780  mov     [rsp+258h+Type], r12d
0x180014785  mov     [rsp+258h+cbData], r12d
0x18001478a  lea     rax, [rsp+258h+cbData]
0x18001478f  mov     [rsp+258h+lpcbData], rax; lpcbData
0x180014794  mov     [rsp+258h+lpData], r12; lpData
0x180014799  lea     r9, [rsp+258h+Type]; lpType
0x18001479e  xor     r8d, r8d; lpReserved
0x1800147a1  mov     rdx, r15; lpValueName
0x1800147a4  mov     rcx, rbx; hKey
0x1800147a7  call    cs:__imp_RegQueryValueExW
0x1800147ad  cmp     eax, 2
0x1800147b0  jnz     short loc_180014811
0x1800147b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147b9  lea     rax, WPP_GLOBAL_Control
0x1800147c0  cmp     rcx, rax
0x1800147c3  jz      short loc_1800147E4
0x1800147c5  test    [rcx+1Ch], sil
0x1800147c9  jz      short loc_1800147E4
0x1800147cb  mov     edx, 10h
0x1800147d0  mov     r9, r15
0x1800147d3  lea     r8, WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids
0x1800147da  mov     rcx, [rcx+10h]
0x1800147de  call    WPP_SF_S
0x1800147e3  nop
0x1800147e4  lea     rcx, [rsp+258h+S2]
0x1800147ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800147f1  nop
0x1800147f2  lea     rcx, [rsp+258h+S1]
0x1800147fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800147ff  nop
0x180014800  lea     rcx, [rsp+258h+var_1E8]
0x180014805  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001480a  xor     eax, eax
0x18001480c  jmp     loc_1800149EE
0x180014811  test    eax, eax
0x180014813  jz      short loc_180014866
0x180014815  jle     short loc_18001481F
0x180014817  movzx   eax, ax
0x18001481a  or      eax, 80070000h
0x18001481f  xorps   xmm0, xmm0
0x180014822  movups  [rsp+258h+var_190], xmm0
0x18001482a  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180014831  mov     [rsp+258h+pExceptionObject], rcx
0x180014839  mov     [rsp+258h+var_180], eax
0x180014840  mov     [rsp+258h+var_17C], 93h
0x18001484b  mov     [rsp+258h+var_178], esi
0x180014852  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180014859  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x180014861  call    _CxxThrowException_0
0x180014866  mov     edx, [rsp+258h+cbData]
0x18001486a  lea     rcx, [rsp+258h+var_1B0]
0x180014872  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180014877  nop
0x180014878  mov     rax, [rsp+258h+var_1B0]
0x180014880  lea     rcx, [rsp+258h+cbData]
0x180014885  mov     [rsp+258h+lpcbData], rcx; lpcbData
0x18001488a  mov     [rsp+258h+lpData], rax; lpData
0x18001488f  lea     r9, [rsp+258h+Type]; lpType
0x180014894  xor     r8d, r8d; lpReserved
0x180014897  mov     rdx, r15; lpValueName
0x18001489a  mov     rcx, rbx; hKey
0x18001489d  call    cs:__imp_RegQueryValueExW
0x1800148a3  test    eax, eax
0x1800148a5  jz      short loc_1800148F8
0x1800148a7  jle     short loc_1800148B1
0x1800148a9  movzx   eax, ax
0x1800148ac  or      eax, 80070000h
0x1800148b1  xorps   xmm0, xmm0
0x1800148b4  movups  [rsp+258h+var_130], xmm0
0x1800148bc  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800148c3  mov     [rsp+258h+var_138], rcx
0x1800148cb  mov     [rsp+258h+var_120], eax
0x1800148d2  mov     [rsp+258h+var_11C], 9Dh
0x1800148dd  mov     [rsp+258h+var_118], esi
0x1800148e4  lea     rdx, _TI2?AVComError@@; pThrowInfo
  ... truncated ...
```
