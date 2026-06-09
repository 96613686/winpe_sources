# EapLm::BaseEapLibraryManager::AddExpandedEapMethods(RegistryKey const &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x180019fbc`
- end: `0x18001a2e8`
- name: `?AddExpandedEapMethods@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `812`
- prototype: `void __fastcall(__int64, _QWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b7cc`

## callees

- `0x180002a90`
- `0x180009fd0`
- `0x1800118e8`
- `0x18001755c`
- `0x1800197d8`
- `0x180019cf0`
- `0x180019fbc`
- `0x18001a758`
- `0x18001c610`
- `0x18001c6b4`
- `0x18001cac8`
- `0x1800300fc`
- `0x1800301fc`
- `0x180030784`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001a194`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001a1a9`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001a194`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001a1a9`

## pseudocode

```c
void __fastcall EapLm::BaseEapLibraryManager::AddExpandedEapMethods(__int64 a1, HKEY *a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // esi
  __int64 v5; // r10
  __int64 v6; // r8
  __int64 v7; // r9
  _QWORD *i; // rbx
  _QWORD *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  _QWORD *j; // rdi
  _QWORD *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r10
  int v29; // eax
  __int64 v30; // r8
  int v31; // eax
  __int64 v32; // r8
  int v33; // eax
  __int64 v34; // r8
  int v35; // eax
  __int64 v36; // r8
  unsigned __int8 v37; // [rsp+40h] [rbp-F8h] BYREF
  __int16 v38; // [rsp+41h] [rbp-F7h]
  char v39; // [rsp+43h] [rbp-F5h]
  __int64 v40; // [rsp+44h] [rbp-F4h]
  unsigned int v41; // [rsp+4Ch] [rbp-ECh]
  unsigned int v42; // [rsp+50h] [rbp-E8h]
  _QWORD *v43; // [rsp+58h] [rbp-E0h]
  _QWORD *v44; // [rsp+60h] [rbp-D8h]
  HKEY v45; // [rsp+68h] [rbp-D0h] BYREF
  int v46; // [rsp+70h] [rbp-C8h]
  __int64 v47; // [rsp+78h] [rbp-C0h] BYREF
  int v48; // [rsp+80h] [rbp-B8h]
  HKEY *v49; // [rsp+88h] [rbp-B0h]
  __int64 v50; // [rsp+90h] [rbp-A8h]
  __int64 v51; // [rsp+98h] [rbp-A0h]
  _QWORD *v52; // [rsp+A0h] [rbp-98h] BYREF
  _QWORD *v53; // [rsp+A8h] [rbp-90h]
  __int64 v54; // [rsp+B0h] [rbp-88h]
  _QWORD *v55; // [rsp+B8h] [rbp-80h] BYREF
  _QWORD *v56; // [rsp+C0h] [rbp-78h]
  __int64 v57; // [rsp+C8h] [rbp-70h]
  const EapHost::EapException *v58; // [rsp+D0h] [rbp-68h] BYREF
  const Exception *v59; // [rsp+D8h] [rbp-60h] BYREF
  const EapHost::EapException *v60; // [rsp+E0h] [rbp-58h] BYREF
  const Exception *v61; // [rsp+E8h] [rbp-50h] BYREF
  _BYTE v62[16]; // [rsp+F0h] [rbp-48h] BYREF

  v4 = a3;
  v51 = a1;
  v49 = a2;
  v42 = a3;
  v50 = a4;
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v52);
  RegistryKey::SubKeys(v5, &v52);
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v37 = -2;
  for ( i = v52; ; i += 4 )
  {
    v43 = i;
    if ( i == v53 )
      break;
    v45 = 0;
    v46 = 1;
    v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( !(unsigned int)RegistryKey::Open((__int64)&v45, *v49, (const WCHAR *)v10, 9) )
      {
        std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v55);
        RegistryKey::SubKeys(&v45, &v55);
        for ( j = v55; ; j += 4 )
        {
          v44 = j;
          if ( j == v56 )
          {
            v14 = v55;
            if ( v55 )
            {
              std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
                v55,
                v56,
                v11,
                v12);
              std::_Deallocate<16>(v14, (v57 - (_QWORD)v14) & 0xFFFFFFFFFFFFFFE0uLL);
            }
            goto LABEL_28;
          }
          v47 = 0;
          v48 = 1;
          v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          if ( __eh34_try(0, 1) )
          {
            __eh34_scope_strut(1);
            if ( (unsigned int)RegistryKey::Open((__int64)&v47, v45, (const WCHAR *)v15, 1) )
            {
              if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                McTemplateU0qzz_EtwEventWriteTransfer(v20, v19, v4, v18, v19);
              }
              if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                WPP_SF_dSS(*(_QWORD *)(v22 + 16), v23, v22, v4, v21, v23);
              }
            }
            else
            {
              v41 = v4;
              v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
              LODWORD(v40) = _o__wtol(v16);
              v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
              HIDWORD(v40) = _o__wtol(v17);
              EapLm::BaseEapLibraryManager::AddOneEapMethod(v51, (__int64)&v47, (__int128 *)&v37, v50);
            }
            RegistryKey::Clear((HKEY *)&v47);
          }
          if ( __eh34_catch(1) )
          {
            if ( __eh34_catch_type(1, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
                McGenEventWrite_EtwEventWriteTransfer(
                  (_QWORD *)(unsigned int)&eaphost_Context,
                  (unsigned int)OutOfMemory,
                  (unsigned int)v11,
                  1,
                  (__int64)v62);
              if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
              }
              throw;
            }
            if ( __eh34_catch_type(1, &EapHost::EapException `RTTI Type Descriptor', &v58) )
            {
              if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v29 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v58 + 16LL))(v58);
                WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v30, v41, v37, v40, HIDWORD(v40), v29);
              }
              v4 = v42;
              j = v44;
              i = v43;
              __eh34_try_continuation(1, &EapHost::EapException `RTTI Type Descriptor', &loc_18001A24A);
              continue;
            }
            if ( __eh34_catch_type(1, &Exception `RTTI Type Descriptor', &v59) )
            {
              if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v31 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v59 + 16LL))(v59);
                WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v32, v41, v37, v40, HIDWORD(v40), v31);
              }
              v4 = v42;
              j = v44;
              i = v43;
              __eh34_try_continuation(1, &Exception `RTTI Type Descriptor', &loc_18001A24C);
            }
          }
        }
      }
      if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
      {
        v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        McTemplateU0qz_EtwEventWriteTransfer(v26, v25, v4, v24);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        WPP_SF_dS(*(_QWORD *)(v28 + 16), 47, (int)WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v4, v27);
      }
LABEL_28:
      RegistryKey::Clear(&v45);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            (_QWORD *)(unsigned int)&eaphost_Context,
            (unsigned int)OutOfMemory,
            (unsigned int)v6,
            1,
            (__int64)v62);
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
        }
        throw;
      }
      if ( __eh34_catch_type(0, &EapHost::EapException `RTTI Type Descriptor', &v60) )
      {
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v33 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v60 + 16LL))(v60);
          WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v34, v41, v37, v40, HIDWORD(v40), v33);
        }
        v4 = v42;
        i = v43;
        __eh34_try_continuation(0, &EapHost::EapException `RTTI Type Descriptor', &loc_18001A2CC);
        continue;
      }
      if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v61) )
      {
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v35 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v61 + 16LL))(v61);
          WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, v36, v41, v37, v40, HIDWORD(v40), v35);
        }
        v4 = v42;
        i = v43;
        __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_18001A2CE);
      }
    }
  }
  v9 = v52;
  if ( v52 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v52,
      v53,
      v6,
      v7);
    std::_Deallocate<16>(v9, (v54 - (_QWORD)v9) & 0xFFFFFFFFFFFFFFE0uLL);
  }
}

```

## disassembly

```asm
0x180019fbc  push    rbx
0x180019fbe  push    rsi
0x180019fbf  push    rdi
0x180019fc0  push    r14
0x180019fc2  sub     rsp, 118h
0x180019fc9  mov     rax, cs:__security_cookie
0x180019fd0  xor     rax, rsp
0x180019fd3  mov     [rsp+138h+var_38], rax
0x180019fdb  mov     esi, r8d
0x180019fde  mov     r10, rdx
0x180019fe1  mov     [rsp+138h+var_A0], rcx
0x180019fe9  mov     [rsp+138h+var_B0], rdx
0x180019ff1  mov     [rsp+138h+var_E8], r8d
0x180019ff6  mov     [rsp+138h+var_A8], r9
0x180019ffe  lea     rcx, [rsp+138h+var_98]
0x18001a006  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001a00b  nop
0x18001a00c  lea     rdx, [rsp+138h+var_98]
0x18001a014  mov     rcx, r10
0x18001a017  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001a01c  xor     eax, eax
0x18001a01e  mov     [rsp+138h+var_F7], ax
0x18001a023  mov     [rsp+138h+var_F5], al
0x18001a027  mov     [rsp+138h+var_F4], rax
0x18001a02c  mov     [rsp+138h+var_EC], eax
0x18001a030  mov     [rsp+138h+var_F8], 0FEh
0x18001a035  mov     rbx, [rsp+138h+var_98]
0x18001a03d  lea     r14, WPP_GLOBAL_Control
0x18001a044  mov     [rsp+138h+var_E0], rbx
0x18001a049  mov     rdx, [rsp+138h+var_90]
0x18001a051  cmp     rbx, rdx
0x18001a054  jnz     short loc_18001A09F
0x18001a056  mov     rbx, [rsp+138h+var_98]
0x18001a05e  test    rbx, rbx
0x18001a061  jz      short loc_18001A082
0x18001a063  mov     rcx, rbx
0x18001a066  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001a06b  mov     rdx, [rsp+138h+var_88]
0x18001a073  sub     rdx, rbx
0x18001a076  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001a07a  mov     rcx, rbx
0x18001a07d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a082  mov     rcx, [rsp+138h+var_38]
0x18001a08a  xor     rcx, rsp; StackCookie
0x18001a08d  call    __security_check_cookie
0x18001a092  add     rsp, 118h
0x18001a099  pop     r14
0x18001a09b  pop     rdi
0x18001a09c  pop     rsi
0x18001a09d  pop     rbx
0x18001a09e  retn
0x18001a09f  mov     [rsp+138h+var_D0], 0
0x18001a0a8  mov     [rsp+138h+var_C8], 1
0x18001a0b0  mov     rcx, rbx
0x18001a0b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a0b8  mov     r9d, 9
0x18001a0be  mov     r8, rax
0x18001a0c1  mov     rdx, [rsp+138h+var_B0]
0x18001a0c9  mov     rdx, [rdx]
0x18001a0cc  lea     rcx, [rsp+138h+var_D0]
0x18001a0d1  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001a0d6  test    eax, eax
0x18001a0d8  jnz     loc_18001A26A
0x18001a0de  lea     rcx, [rsp+138h+var_80]
0x18001a0e6  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001a0eb  nop
0x18001a0ec  lea     rdx, [rsp+138h+var_80]
0x18001a0f4  lea     rcx, [rsp+138h+var_D0]
0x18001a0f9  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001a0fe  mov     rdi, [rsp+138h+var_80]
0x18001a106  mov     [rsp+138h+var_D8], rdi
0x18001a10b  mov     rdx, [rsp+138h+var_78]
0x18001a113  cmp     rdi, rdx
0x18001a116  jnz     short loc_18001A14D
0x18001a118  mov     rdi, [rsp+138h+var_80]
0x18001a120  test    rdi, rdi
0x18001a123  jz      loc_18001A2BF
0x18001a129  mov     rcx, rdi
0x18001a12c  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001a131  mov     rdx, [rsp+138h+var_70]
0x18001a139  sub     rdx, rdi
0x18001a13c  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001a140  mov     rcx, rdi
0x18001a143  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a148  jmp     loc_18001A2BF
0x18001a14d  mov     [rsp+138h+var_C0], 0
0x18001a156  mov     [rsp+138h+var_B8], 1
0x18001a161  mov     rcx, rdi
0x18001a164  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a169  mov     r9d, 1
0x18001a16f  mov     r8, rax
0x18001a172  mov     rdx, [rsp+138h+var_D0]
0x18001a177  lea     rcx, [rsp+138h+var_C0]
0x18001a17c  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001a181  test    eax, eax
0x18001a183  jnz     short loc_18001A1D4
0x18001a185  mov     [rsp+138h+var_EC], esi
0x18001a189  mov     rcx, rbx
0x18001a18c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a191  mov     rcx, rax
0x18001a194  call    cs:__imp__o__wtol
0x18001a19a  mov     dword ptr [rsp+138h+var_F4], eax
0x18001a19e  mov     rcx, rdi
0x18001a1a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a1a6  mov     rcx, rax
0x18001a1a9  call    cs:__imp__o__wtol
0x18001a1af  mov     dword ptr [rsp+138h+var_F4+4], eax
0x18001a1b3  mov     r9, [rsp+138h+var_A8]
0x18001a1bb  lea     r8, [rsp+138h+var_F8]
0x18001a1c0  lea     rdx, [rsp+138h+var_C0]
0x18001a1c5  mov     rcx, [rsp+138h+var_A0]
0x18001a1cd  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001a1d2  jmp     short loc_18001A23D
0x18001a1d4  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001a1db  jz      short loc_18001A200
0x18001a1dd  mov     rcx, rdi
0x18001a1e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a1e5  mov     rdx, rax
0x18001a1e8  mov     rcx, rbx
0x18001a1eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a1f0  mov     [rsp+138h+var_118], rdx
0x18001a1f5  mov     r9, rax
0x18001a1f8  mov     r8d, esi
0x18001a1fb  call    McTemplateU0qzz_EtwEventWriteTransfer
0x18001a200  mov     r8, cs:WPP_GLOBAL_Control
0x18001a207  cmp     r8, r14
0x18001a20a  jz      short loc_18001A23D
0x18001a20c  test    byte ptr [r8+1Ch], 1
0x18001a211  jz      short loc_18001A23D
0x18001a213  mov     rcx, rdi
0x18001a216  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a21b  mov     rdx, rax
0x18001a21e  mov     rcx, rbx
0x18001a221  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a226  mov     [rsp+138h+var_110], rdx
0x18001a22b  mov     [rsp+138h+var_118], rax
0x18001a230  mov     r9d, esi
0x18001a233  mov     rcx, [r8+10h]
0x18001a237  call    WPP_SF_dSS
0x18001a23c  nop
0x18001a23d  lea     rcx, [rsp+138h+var_C0]; this
0x18001a242  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001a247  nop
0x18001a248  jmp     short loc_18001A261
0x18001a24a  jmp     short $+2
0x18001a24c  mov     esi, [rsp+138h+var_E8]
0x18001a250  mov     rdi, [rsp+138h+var_D8]
0x18001a255  mov     rbx, [rsp+138h+var_E0]
0x18001a25a  lea     r14, WPP_GLOBAL_Control
0x18001a261  add     rdi, 20h ; ' '
0x18001a265  jmp     loc_18001A106
0x18001a26a  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001a271  jz      short loc_18001A286
0x18001a273  mov     rcx, rbx
0x18001a276  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a27b  mov     r9, rax
0x18001a27e  mov     r8d, esi
0x18001a281  call    McTemplateU0qz_EtwEventWriteTransfer
0x18001a286  mov     r10, cs:WPP_GLOBAL_Control
0x18001a28d  cmp     r10, r14
0x18001a290  jz      short loc_18001A2BF
0x18001a292  test    byte ptr [r10+1Ch], 1
0x18001a297  jz      short loc_18001A2BF
0x18001a299  mov     rcx, rbx
0x18001a29c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a2a1  mov     edx, 2Fh ; '/'
0x18001a2a6  mov     [rsp+138h+var_118], rax
0x18001a2ab  mov     r9d, esi
0x18001a2ae  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001a2b5  mov     rcx, [r10+10h]
0x18001a2b9  call    WPP_SF_dS
0x18001a2be  nop
0x18001a2bf  lea     rcx, [rsp+138h+var_D0]; this
0x18001a2c4  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001a2c9  nop
0x18001a2ca  jmp     short loc_18001A2DE
0x18001a2cc  jmp     short $+2
0x18001a2ce  mov     esi, [rsp+138h+var_E8]
0x18001a2d2  mov     rbx, [rsp+138h+var_E0]
0x18001a2d7  lea     r14, WPP_GLOBAL_Control
0x18001a2de  add     rbx, 20h ; ' '
0x18001a2e2  jmp     loc_18001A044
```
