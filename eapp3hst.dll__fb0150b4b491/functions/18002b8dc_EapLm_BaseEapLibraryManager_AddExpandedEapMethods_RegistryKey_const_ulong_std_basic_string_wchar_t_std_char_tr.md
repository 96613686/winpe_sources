# EapLm::BaseEapLibraryManager::AddExpandedEapMethods(RegistryKey const &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x18002b8dc`
- end: `0x18002bbfb`
- name: `?AddExpandedEapMethods@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `799`
- prototype: `void __fastcall(__int64, _QWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d040`

## callees

- `0x1800017a0`
- `0x18000eb74`
- `0x180011ff0`
- `0x18002a514`
- `0x18002a738`
- `0x18002a7dc`
- `0x18002a8dc`
- `0x18002ae64`
- `0x18002b8dc`
- `0x18002c06c`
- `0x18002dc78`
- `0x18002dd1c`
- `0x18002df5c`
- `0x18002dfe8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002bab4`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002bac9`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002bab4`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002bac9`

## pseudocode

```c
void __fastcall EapLm::BaseEapLibraryManager::AddExpandedEapMethods(__int64 a1, HKEY *a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // esi
  __int64 v5; // r10
  _QWORD *i; // rbx
  _QWORD *v7; // rbx
  __int64 v8; // rax
  _QWORD *j; // rdi
  _QWORD *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rdx
  int v20; // r8d
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // r8d
  int v27; // r8d
  int v28; // eax
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // r8
  int v34; // eax
  __int64 v35; // r8
  __int128 v36; // [rsp+40h] [rbp-F8h] BYREF
  unsigned int v37; // [rsp+50h] [rbp-E8h]
  _QWORD *v38; // [rsp+58h] [rbp-E0h]
  _QWORD *v39; // [rsp+60h] [rbp-D8h]
  HKEY v40; // [rsp+68h] [rbp-D0h] BYREF
  int v41; // [rsp+70h] [rbp-C8h]
  __int64 v42; // [rsp+78h] [rbp-C0h] BYREF
  int v43; // [rsp+80h] [rbp-B8h]
  HKEY *v44; // [rsp+88h] [rbp-B0h]
  __int64 v45; // [rsp+90h] [rbp-A8h]
  __int64 v46; // [rsp+98h] [rbp-A0h]
  _QWORD *v47; // [rsp+A0h] [rbp-98h] BYREF
  _QWORD *v48; // [rsp+A8h] [rbp-90h]
  __int64 v49; // [rsp+B0h] [rbp-88h]
  _QWORD *v50; // [rsp+B8h] [rbp-80h] BYREF
  _QWORD *v51; // [rsp+C0h] [rbp-78h]
  __int64 v52; // [rsp+C8h] [rbp-70h]
  const EapHost::EapException *v53; // [rsp+D0h] [rbp-68h] BYREF
  const Exception *v54; // [rsp+D8h] [rbp-60h] BYREF
  const EapHost::EapException *v55; // [rsp+E0h] [rbp-58h] BYREF
  const Exception *v56; // [rsp+E8h] [rbp-50h] BYREF
  _BYTE v57[16]; // [rsp+F0h] [rbp-48h] BYREF

  v4 = a3;
  v46 = a1;
  v44 = a2;
  v37 = a3;
  v45 = a4;
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v47);
  RegistryKey::SubKeys(v5, &v47);
  v36 = 0xFEu;
  for ( i = v47; ; i += 4 )
  {
    v38 = i;
    if ( i == v48 )
      break;
    v40 = 0;
    v41 = 1;
    v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( !(unsigned int)RegistryKey::Open((__int64)&v40, *v44, (const WCHAR *)v8, 9) )
      {
        std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v50);
        RegistryKey::SubKeys(&v40, &v50);
        for ( j = v50; ; j += 4 )
        {
          v39 = j;
          if ( j == v51 )
          {
            v10 = v50;
            if ( v50 )
            {
              std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
                v50,
                v51);
              std::_Deallocate<16>(v10, (v52 - (_QWORD)v10) & 0xFFFFFFFFFFFFFFE0uLL);
            }
            goto LABEL_27;
          }
          v42 = 0;
          v43 = 1;
          v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          if ( __eh34_try(0, 1) )
          {
            __eh34_scope_strut(1);
            if ( (unsigned int)RegistryKey::Open((__int64)&v42, v40, (const WCHAR *)v11, 1) )
            {
              if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                McTemplateU0qzz_EtwEventWriteTransfer(v16, v15, v4, v14, v15);
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                WPP_SF_dSS(*(_QWORD *)(v18 + 16), v19, v18, v4, v17, v19);
              }
            }
            else
            {
              HIDWORD(v36) = v4;
              v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
              DWORD1(v36) = _o__wtol(v12);
              v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
              DWORD2(v36) = _o__wtol(v13);
              EapLm::BaseEapLibraryManager::AddOneEapMethod(v46, (__int64)&v42, &v36, v45);
            }
            RegistryKey::Clear((HKEY *)&v42);
          }
          if ( __eh34_catch(1) )
          {
            if ( __eh34_catch_type(1, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
                McGenEventWrite_EtwEventWriteTransfer(
                  (_QWORD *)(unsigned int)&eaphost_Context,
                  (unsigned int)OutOfMemory,
                  v20,
                  1,
                  (__int64)v57);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
              }
              throw;
            }
            if ( __eh34_catch_type(1, &EapHost::EapException `RTTI Type Descriptor', &v53) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v28 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v53 + 16LL))(v53);
                WPP_SF_ddddD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  45,
                  v29,
                  HIDWORD(v36),
                  (unsigned __int8)v36,
                  DWORD1(v36),
                  DWORD2(v36),
                  v28);
              }
              v4 = v37;
              j = v39;
              i = v38;
              __eh34_try_continuation(1, &EapHost::EapException `RTTI Type Descriptor', &loc_18002BB6A);
              continue;
            }
            if ( __eh34_catch_type(1, &Exception `RTTI Type Descriptor', &v54) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v30 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v54 + 16LL))(v54);
                WPP_SF_ddddD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  46,
                  v31,
                  HIDWORD(v36),
                  (unsigned __int8)v36,
                  DWORD1(v36),
                  DWORD2(v36),
                  v30);
              }
              v4 = v37;
              j = v39;
              i = v38;
              __eh34_try_continuation(1, &Exception `RTTI Type Descriptor', &loc_18002BB6C);
            }
          }
        }
      }
      if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
      {
        v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        McTemplateU0qz_EtwEventWriteTransfer(v23, v22, v4, v21);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        WPP_SF_dS(*(_QWORD *)(v25 + 16), v25, v26, v4, v24);
      }
LABEL_27:
      RegistryKey::Clear(&v40);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            (_QWORD *)(unsigned int)&eaphost_Context,
            (unsigned int)OutOfMemory,
            v27,
            1,
            (__int64)v57);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
        throw;
      }
      if ( __eh34_catch_type(0, &EapHost::EapException `RTTI Type Descriptor', &v55) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v32 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v55 + 16LL))(v55);
          WPP_SF_ddddD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            v33,
            HIDWORD(v36),
            (unsigned __int8)v36,
            DWORD1(v36),
            DWORD2(v36),
            v32);
        }
        v4 = v37;
        i = v38;
        __eh34_try_continuation(0, &EapHost::EapException `RTTI Type Descriptor', &loc_18002BBDF);
        continue;
      }
      if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v56) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v34 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v56 + 16LL))(v56);
          WPP_SF_ddddD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            v35,
            HIDWORD(v36),
            (unsigned __int8)v36,
            DWORD1(v36),
            DWORD2(v36),
            v34);
        }
        v4 = v37;
        i = v38;
        __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_18002BBE1);
      }
    }
  }
  v7 = v47;
  if ( v47 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v47,
      v48);
    std::_Deallocate<16>(v7, (v49 - (_QWORD)v7) & 0xFFFFFFFFFFFFFFE0uLL);
  }
}

```

## disassembly

```asm
0x18002b8dc  push    rbx
0x18002b8de  push    rsi
0x18002b8df  push    rdi
0x18002b8e0  push    r14
0x18002b8e2  sub     rsp, 118h
0x18002b8e9  mov     rax, cs:__security_cookie
0x18002b8f0  xor     rax, rsp
0x18002b8f3  mov     [rsp+138h+var_38], rax
0x18002b8fb  mov     esi, r8d
0x18002b8fe  mov     r10, rdx
0x18002b901  mov     [rsp+138h+var_A0], rcx
0x18002b909  mov     [rsp+138h+var_B0], rdx
0x18002b911  mov     [rsp+138h+var_E8], r8d
0x18002b916  mov     [rsp+138h+var_A8], r9
0x18002b91e  lea     rcx, [rsp+138h+var_98]
0x18002b926  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18002b92b  nop
0x18002b92c  lea     rdx, [rsp+138h+var_98]
0x18002b934  mov     rcx, r10
0x18002b937  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002b93c  xor     eax, eax
0x18002b93e  mov     [rsp+138h+var_F7], ax
0x18002b943  mov     [rsp+138h+var_F5], al
0x18002b947  mov     [rsp+138h+var_F4], rax
0x18002b94c  mov     [rsp+138h+var_EC], eax
0x18002b950  mov     [rsp+138h+var_F8], 0FEh
0x18002b955  mov     rbx, [rsp+138h+var_98]
0x18002b95d  lea     r14, WPP_GLOBAL_Control
0x18002b964  mov     [rsp+138h+var_E0], rbx
0x18002b969  mov     rdx, [rsp+138h+var_90]
0x18002b971  cmp     rbx, rdx
0x18002b974  jnz     short loc_18002B9BF
0x18002b976  mov     rbx, [rsp+138h+var_98]
0x18002b97e  test    rbx, rbx
0x18002b981  jz      short loc_18002B9A2
0x18002b983  mov     rcx, rbx
0x18002b986  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002b98b  mov     rdx, [rsp+138h+var_88]
0x18002b993  sub     rdx, rbx
0x18002b996  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b99a  mov     rcx, rbx
0x18002b99d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b9a2  mov     rcx, [rsp+138h+var_38]
0x18002b9aa  xor     rcx, rsp; StackCookie
0x18002b9ad  call    __security_check_cookie
0x18002b9b2  add     rsp, 118h
0x18002b9b9  pop     r14
0x18002b9bb  pop     rdi
0x18002b9bc  pop     rsi
0x18002b9bd  pop     rbx
0x18002b9be  retn
0x18002b9bf  mov     [rsp+138h+var_D0], 0
0x18002b9c8  mov     [rsp+138h+var_C8], 1
0x18002b9d0  mov     rcx, rbx
0x18002b9d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b9d8  mov     r9d, 9
0x18002b9de  mov     r8, rax
0x18002b9e1  mov     rdx, [rsp+138h+var_B0]
0x18002b9e9  mov     rdx, [rdx]
0x18002b9ec  lea     rcx, [rsp+138h+var_D0]
0x18002b9f1  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18002b9f6  test    eax, eax
0x18002b9f8  jnz     loc_18002BB8A
0x18002b9fe  lea     rcx, [rsp+138h+var_80]
0x18002ba06  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18002ba0b  nop
0x18002ba0c  lea     rdx, [rsp+138h+var_80]
0x18002ba14  lea     rcx, [rsp+138h+var_D0]
0x18002ba19  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002ba1e  mov     rdi, [rsp+138h+var_80]
0x18002ba26  mov     [rsp+138h+var_D8], rdi
0x18002ba2b  mov     rdx, [rsp+138h+var_78]
0x18002ba33  cmp     rdi, rdx
0x18002ba36  jnz     short loc_18002BA6D
0x18002ba38  mov     rdi, [rsp+138h+var_80]
0x18002ba40  test    rdi, rdi
0x18002ba43  jz      loc_18002BBD2
0x18002ba49  mov     rcx, rdi
0x18002ba4c  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002ba51  mov     rdx, [rsp+138h+var_70]
0x18002ba59  sub     rdx, rdi
0x18002ba5c  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002ba60  mov     rcx, rdi
0x18002ba63  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002ba68  jmp     loc_18002BBD2
0x18002ba6d  mov     [rsp+138h+var_C0], 0
0x18002ba76  mov     [rsp+138h+var_B8], 1
0x18002ba81  mov     rcx, rdi
0x18002ba84  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ba89  mov     r9d, 1
0x18002ba8f  mov     r8, rax
0x18002ba92  mov     rdx, [rsp+138h+var_D0]
0x18002ba97  lea     rcx, [rsp+138h+var_C0]
0x18002ba9c  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18002baa1  test    eax, eax
0x18002baa3  jnz     short loc_18002BAF4
0x18002baa5  mov     [rsp+138h+var_EC], esi
0x18002baa9  mov     rcx, rbx
0x18002baac  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bab1  mov     rcx, rax
0x18002bab4  call    cs:__imp__o__wtol
0x18002baba  mov     dword ptr [rsp+138h+var_F4], eax
0x18002babe  mov     rcx, rdi
0x18002bac1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bac6  mov     rcx, rax
0x18002bac9  call    cs:__imp__o__wtol
0x18002bacf  mov     dword ptr [rsp+138h+var_F4+4], eax
0x18002bad3  mov     r9, [rsp+138h+var_A8]
0x18002badb  lea     r8, [rsp+138h+var_F8]
0x18002bae0  lea     rdx, [rsp+138h+var_C0]
0x18002bae5  mov     rcx, [rsp+138h+var_A0]
0x18002baed  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002baf2  jmp     short loc_18002BB5D
0x18002baf4  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18002bafb  jz      short loc_18002BB20
0x18002bafd  mov     rcx, rdi
0x18002bb00  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bb05  mov     rdx, rax
0x18002bb08  mov     rcx, rbx
0x18002bb0b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bb10  mov     [rsp+138h+var_118], rdx
0x18002bb15  mov     r9, rax
0x18002bb18  mov     r8d, esi
0x18002bb1b  call    McTemplateU0qzz_EtwEventWriteTransfer
0x18002bb20  mov     r8, cs:WPP_GLOBAL_Control
0x18002bb27  cmp     r8, r14
0x18002bb2a  jz      short loc_18002BB5D
0x18002bb2c  test    byte ptr [r8+1Ch], 1
0x18002bb31  jz      short loc_18002BB5D
0x18002bb33  mov     rcx, rdi
0x18002bb36  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bb3b  mov     rdx, rax
0x18002bb3e  mov     rcx, rbx
0x18002bb41  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bb46  mov     [rsp+138h+var_110], rdx
0x18002bb4b  mov     [rsp+138h+var_118], rax
0x18002bb50  mov     r9d, esi
0x18002bb53  mov     rcx, [r8+10h]
0x18002bb57  call    WPP_SF_dSS
0x18002bb5c  nop
0x18002bb5d  lea     rcx, [rsp+138h+var_C0]; this
0x18002bb62  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002bb67  nop
0x18002bb68  jmp     short loc_18002BB81
0x18002bb6a  jmp     short $+2
0x18002bb6c  mov     esi, [rsp+138h+var_E8]
0x18002bb70  mov     rdi, [rsp+138h+var_D8]
0x18002bb75  mov     rbx, [rsp+138h+var_E0]
0x18002bb7a  lea     r14, WPP_GLOBAL_Control
0x18002bb81  add     rdi, 20h ; ' '
0x18002bb85  jmp     loc_18002BA26
0x18002bb8a  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18002bb91  jz      short loc_18002BBA6
0x18002bb93  mov     rcx, rbx
0x18002bb96  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bb9b  mov     r9, rax
0x18002bb9e  mov     r8d, esi
0x18002bba1  call    McTemplateU0qz_EtwEventWriteTransfer
0x18002bba6  mov     rdx, cs:WPP_GLOBAL_Control
0x18002bbad  cmp     rdx, r14
0x18002bbb0  jz      short loc_18002BBD2
0x18002bbb2  test    byte ptr [rdx+1Ch], 1
0x18002bbb6  jz      short loc_18002BBD2
0x18002bbb8  mov     rcx, rbx
0x18002bbbb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bbc0  mov     [rsp+138h+var_118], rax
0x18002bbc5  mov     r9d, esi
0x18002bbc8  mov     rcx, [rdx+10h]
0x18002bbcc  call    WPP_SF_dS
0x18002bbd1  nop
0x18002bbd2  lea     rcx, [rsp+138h+var_D0]; this
0x18002bbd7  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002bbdc  nop
0x18002bbdd  jmp     short loc_18002BBF1
0x18002bbdf  jmp     short $+2
0x18002bbe1  mov     esi, [rsp+138h+var_E8]
0x18002bbe5  mov     rbx, [rsp+138h+var_E0]
0x18002bbea  lea     r14, WPP_GLOBAL_Control
0x18002bbf1  add     rbx, 20h ; ' '
0x18002bbf5  jmp     loc_18002B964
```
