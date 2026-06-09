# EapLm::BaseEapLibraryManager::AddExpandedEapMethods(RegistryKey const &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x18001a99c`
- end: `0x18001acd5`
- name: `?AddExpandedEapMethods@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c1e4`

## callees

- `0x180002af0`
- `0x18000a44c`
- `0x18001204c`
- `0x180017e48`
- `0x18001a1c0`
- `0x18001a6d4`
- `0x18001a99c`
- `0x18001b14c`
- `0x18001d080`
- `0x18001d124`
- `0x18001d544`
- `0x180031314`
- `0x180031424`
- `0x180031930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001ab75`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001ab90`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001ab75`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001ab90`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall EapLm::BaseEapLibraryManager::AddExpandedEapMethods(__int64 a1, HKEY *a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // esi
  __int64 v5; // r10
  __int64 i; // rbx
  __int64 v7; // rbx
  const WCHAR *v8; // rax
  __int64 j; // rdi
  __int64 v10; // rdi
  const WCHAR *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r10
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // r8
  int v29; // eax
  __int64 v30; // r8
  int v31; // eax
  __int64 v32; // r8
  int v33; // eax
  __int64 v34; // r8
  __int128 v35; // [rsp+40h] [rbp-F8h] BYREF
  unsigned int v36; // [rsp+50h] [rbp-E8h]
  __int64 v37; // [rsp+58h] [rbp-E0h]
  __int64 v38; // [rsp+60h] [rbp-D8h]
  HKEY v39; // [rsp+68h] [rbp-D0h] BYREF
  int v40; // [rsp+70h] [rbp-C8h]
  __int64 v41; // [rsp+78h] [rbp-C0h] BYREF
  int v42; // [rsp+80h] [rbp-B8h]
  HKEY *v43; // [rsp+88h] [rbp-B0h]
  __int64 v44; // [rsp+90h] [rbp-A8h]
  __int64 v45; // [rsp+98h] [rbp-A0h]
  __int64 v46; // [rsp+A0h] [rbp-98h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-90h]
  __int64 v48; // [rsp+B0h] [rbp-88h]
  __int64 v49; // [rsp+B8h] [rbp-80h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-78h]
  __int64 v51; // [rsp+C8h] [rbp-70h]
  const EapHost::EapException *v52; // [rsp+D0h] [rbp-68h] BYREF
  const Exception *v53; // [rsp+D8h] [rbp-60h] BYREF
  const EapHost::EapException *v54; // [rsp+E0h] [rbp-58h] BYREF
  const Exception *v55; // [rsp+E8h] [rbp-50h] BYREF
  _BYTE v56[16]; // [rsp+F0h] [rbp-48h] BYREF

  v4 = a3;
  v45 = a1;
  v43 = a2;
  v36 = a3;
  v44 = a4;
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v46);
  RegistryKey::SubKeys(v5, &v46);
  v35 = 0xFEu;
  for ( i = v46; ; i += 32 )
  {
    v37 = i;
    if ( i == v47 )
      break;
    v39 = 0;
    v40 = 1;
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
    try
    {
      if ( (unsigned int)RegistryKey::Open((RegistryKey *)&v39, *v43, v8, 9) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
        {
          v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
          McTemplateU0qz_EtwEventWriteTransfer(v23, v22, v4, v21);
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
          WPP_SF_dS(*(_QWORD *)(v25 + 16), 47, (unsigned int)WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v4, v24);
        }
      }
      else
      {
        std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v49);
        RegistryKey::SubKeys(&v39, &v49);
        for ( j = v49; ; j += 32 )
        {
          v38 = j;
          if ( j == v50 )
            break;
          v41 = 0;
          v42 = 1;
          v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(j);
          try
          {
            if ( (unsigned int)RegistryKey::Open((RegistryKey *)&v41, v39, v11, 1) )
            {
              if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(j);
                v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
                McTemplateU0qzz_EtwEventWriteTransfer(v16, v15, v4, v14, v15);
              }
              if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(j);
                v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
                WPP_SF_dSS(*(_QWORD *)(v18 + 16), v19, v18, v4, v17, v19);
              }
            }
            else
            {
              HIDWORD(v35) = v4;
              v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
              DWORD1(v35) = _o__wtol(v12);
              v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(j);
              DWORD2(v35) = _o__wtol(v13);
              EapLm::BaseEapLibraryManager::AddOneEapMethod(v45, (__int64)&v41, &v35, v44);
            }
            RegistryKey::Clear((RegistryKey *)&v41);
          }
          catch ( std::bad_alloc )
          {
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
              McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)OutOfMemory, v20, 1, (__int64)v56);
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
            }
            throw;
          }
          catch ( const EapHost::EapException *v52 )
          {
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v27 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v52 + 16LL))(v52);
              WPP_SF_ddddD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                45,
                v28,
                HIDWORD(v35),
                (unsigned __int8)v35,
                DWORD1(v35),
                DWORD2(v35),
                v27);
            }
            v4 = v36;
            j = v38;
            i = v37;
            continue;
          }
          catch ( const Exception *v53 )
          {
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v29 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v53 + 16LL))(v53);
              WPP_SF_ddddD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                46,
                v30,
                HIDWORD(v35),
                (unsigned __int8)v35,
                DWORD1(v35),
                DWORD2(v35),
                v29);
            }
            v4 = v36;
            j = v38;
            i = v37;
            continue;
          }
        }
        v10 = v49;
        if ( v49 )
        {
          std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
            v49,
            v50);
          std::_Deallocate<16>(v10, (v51 - v10) & 0xFFFFFFFFFFFFFFE0uLL);
        }
      }
      RegistryKey::Clear((RegistryKey *)&v39);
    }
    catch ( std::bad_alloc )
    {
      if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)OutOfMemory, v26, 1, (__int64)v56);
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
      }
      throw;
    }
    catch ( const EapHost::EapException *v54 )
    {
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v31 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v54 + 16LL))(v54);
        WPP_SF_ddddD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          v32,
          HIDWORD(v35),
          (unsigned __int8)v35,
          DWORD1(v35),
          DWORD2(v35),
          v31);
      }
      v4 = v36;
      i = v37;
      continue;
    }
    catch ( const Exception *v55 )
    {
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v33 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v55 + 16LL))(v55);
        WPP_SF_ddddD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          v34,
          HIDWORD(v35),
          (unsigned __int8)v35,
          DWORD1(v35),
          DWORD2(v35),
          v33);
      }
      v4 = v36;
      i = v37;
      continue;
    }
  }
  v7 = v46;
  if ( v46 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v46,
      v47);
    std::_Deallocate<16>(v7, (v48 - v7) & 0xFFFFFFFFFFFFFFE0uLL);
  }
}

```

## disassembly

```asm
0x18001a99c  push    rbx
0x18001a99e  push    rsi
0x18001a99f  push    rdi
0x18001a9a0  push    r14
0x18001a9a2  sub     rsp, 118h
0x18001a9a9  mov     rax, cs:__security_cookie
0x18001a9b0  xor     rax, rsp
0x18001a9b3  mov     [rsp+138h+var_38], rax
0x18001a9bb  mov     esi, r8d
0x18001a9be  mov     r10, rdx
0x18001a9c1  mov     [rsp+138h+var_A0], rcx
0x18001a9c9  mov     [rsp+138h+var_B0], rdx
0x18001a9d1  mov     [rsp+138h+var_E8], r8d
0x18001a9d6  mov     [rsp+138h+var_A8], r9
0x18001a9de  lea     rcx, [rsp+138h+var_98]
0x18001a9e6  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001a9eb  nop
0x18001a9ec  lea     rdx, [rsp+138h+var_98]
0x18001a9f4  mov     rcx, r10
0x18001a9f7  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001a9fc  xor     eax, eax
0x18001a9fe  mov     [rsp+138h+var_F7], ax
0x18001aa03  mov     [rsp+138h+var_F5], al
0x18001aa07  mov     [rsp+138h+var_F4], rax
0x18001aa0c  mov     [rsp+138h+var_EC], eax
0x18001aa10  mov     [rsp+138h+var_F8], 0FEh
0x18001aa15  mov     rbx, [rsp+138h+var_98]
0x18001aa1d  lea     r14, WPP_GLOBAL_Control
0x18001aa24  mov     [rsp+138h+var_E0], rbx
0x18001aa29  mov     rdx, [rsp+138h+var_90]
0x18001aa31  cmp     rbx, rdx
0x18001aa34  jnz     short loc_18001AA80
0x18001aa36  mov     rbx, [rsp+138h+var_98]
0x18001aa3e  test    rbx, rbx
0x18001aa41  jz      short loc_18001AA62
0x18001aa43  mov     rcx, rbx
0x18001aa46  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001aa4b  mov     rdx, [rsp+138h+var_88]
0x18001aa53  sub     rdx, rbx
0x18001aa56  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001aa5a  mov     rcx, rbx
0x18001aa5d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001aa62  mov     rcx, [rsp+138h+var_38]
0x18001aa6a  xor     rcx, rsp; StackCookie
0x18001aa6d  call    __security_check_cookie
0x18001aa72  add     rsp, 118h
0x18001aa79  pop     r14
0x18001aa7b  pop     rdi
0x18001aa7c  pop     rsi
0x18001aa7d  pop     rbx
0x18001aa7e  retn
0x18001aa80  mov     [rsp+138h+var_D0], 0
0x18001aa89  mov     [rsp+138h+var_C8], 1
0x18001aa91  mov     rcx, rbx
0x18001aa94  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001aa99  mov     r9d, 9
0x18001aa9f  mov     r8, rax
0x18001aaa2  mov     rdx, [rsp+138h+var_B0]
0x18001aaaa  mov     rdx, [rdx]
0x18001aaad  lea     rcx, [rsp+138h+var_D0]
0x18001aab2  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001aab7  test    eax, eax
0x18001aab9  jnz     loc_18001AC57
0x18001aabf  lea     rcx, [rsp+138h+var_80]
0x18001aac7  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001aacc  nop
0x18001aacd  lea     rdx, [rsp+138h+var_80]
0x18001aad5  lea     rcx, [rsp+138h+var_D0]
0x18001aada  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001aadf  mov     rdi, [rsp+138h+var_80]
0x18001aae7  mov     [rsp+138h+var_D8], rdi
0x18001aaec  mov     rdx, [rsp+138h+var_78]
0x18001aaf4  cmp     rdi, rdx
0x18001aaf7  jnz     short loc_18001AB2E
0x18001aaf9  mov     rdi, [rsp+138h+var_80]
0x18001ab01  test    rdi, rdi
0x18001ab04  jz      loc_18001ACAC
0x18001ab0a  mov     rcx, rdi
0x18001ab0d  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001ab12  mov     rdx, [rsp+138h+var_70]
0x18001ab1a  sub     rdx, rdi
0x18001ab1d  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001ab21  mov     rcx, rdi
0x18001ab24  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ab29  jmp     loc_18001ACAC
0x18001ab2e  mov     [rsp+138h+var_C0], 0
0x18001ab37  mov     [rsp+138h+var_B8], 1
0x18001ab42  mov     rcx, rdi
0x18001ab45  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ab4a  mov     r9d, 1
0x18001ab50  mov     r8, rax
0x18001ab53  mov     rdx, [rsp+138h+var_D0]
0x18001ab58  lea     rcx, [rsp+138h+var_C0]
0x18001ab5d  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001ab62  test    eax, eax
0x18001ab64  jnz     short loc_18001ABC1
0x18001ab66  mov     [rsp+138h+var_EC], esi
0x18001ab6a  mov     rcx, rbx
0x18001ab6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ab72  mov     rcx, rax
0x18001ab75  call    cs:__imp__o__wtol
0x18001ab7c  nop     dword ptr [rax+rax+00h]
0x18001ab81  mov     dword ptr [rsp+138h+var_F4], eax
0x18001ab85  mov     rcx, rdi
0x18001ab88  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ab8d  mov     rcx, rax
0x18001ab90  call    cs:__imp__o__wtol
0x18001ab97  nop     dword ptr [rax+rax+00h]
0x18001ab9c  mov     dword ptr [rsp+138h+var_F4+4], eax
0x18001aba0  mov     r9, [rsp+138h+var_A8]
0x18001aba8  lea     r8, [rsp+138h+var_F8]
0x18001abad  lea     rdx, [rsp+138h+var_C0]
0x18001abb2  mov     rcx, [rsp+138h+var_A0]
0x18001abba  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001abbf  jmp     short loc_18001AC2A
0x18001abc1  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001abc8  jz      short loc_18001ABED
0x18001abca  mov     rcx, rdi
0x18001abcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001abd2  mov     rdx, rax
0x18001abd5  mov     rcx, rbx
0x18001abd8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001abdd  mov     [rsp+138h+var_118], rdx
0x18001abe2  mov     r9, rax
0x18001abe5  mov     r8d, esi
0x18001abe8  call    McTemplateU0qzz_EtwEventWriteTransfer
0x18001abed  mov     r8, cs:WPP_GLOBAL_Control
0x18001abf4  cmp     r8, r14
0x18001abf7  jz      short loc_18001AC2A
0x18001abf9  test    byte ptr [r8+1Ch], 1
0x18001abfe  jz      short loc_18001AC2A
0x18001ac00  mov     rcx, rdi
0x18001ac03  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ac08  mov     rdx, rax
0x18001ac0b  mov     rcx, rbx
0x18001ac0e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ac13  mov     [rsp+138h+var_110], rdx
0x18001ac18  mov     [rsp+138h+var_118], rax
0x18001ac1d  mov     r9d, esi
0x18001ac20  mov     rcx, [r8+10h]
0x18001ac24  call    WPP_SF_dSS
0x18001ac29  nop
0x18001ac2a  lea     rcx, [rsp+138h+var_C0]; this
0x18001ac2f  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001ac34  nop
0x18001ac35  jmp     short loc_18001AC4E
0x18001ac37  jmp     short $+2
0x18001ac39  mov     esi, [rsp+138h+var_E8]
0x18001ac3d  mov     rdi, [rsp+138h+var_D8]
0x18001ac42  mov     rbx, [rsp+138h+var_E0]
0x18001ac47  lea     r14, WPP_GLOBAL_Control
0x18001ac4e  add     rdi, 20h ; ' '
0x18001ac52  jmp     loc_18001AAE7
0x18001ac57  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001ac5e  jz      short loc_18001AC73
0x18001ac60  mov     rcx, rbx
0x18001ac63  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ac68  mov     r9, rax
0x18001ac6b  mov     r8d, esi
0x18001ac6e  call    McTemplateU0qz_EtwEventWriteTransfer
0x18001ac73  mov     r10, cs:WPP_GLOBAL_Control
0x18001ac7a  cmp     r10, r14
0x18001ac7d  jz      short loc_18001ACAC
0x18001ac7f  test    byte ptr [r10+1Ch], 1
0x18001ac84  jz      short loc_18001ACAC
0x18001ac86  mov     rcx, rbx
0x18001ac89  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ac8e  mov     edx, 2Fh ; '/'
0x18001ac93  mov     [rsp+138h+var_118], rax
0x18001ac98  mov     r9d, esi
0x18001ac9b  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001aca2  mov     rcx, [r10+10h]
0x18001aca6  call    WPP_SF_dS
0x18001acab  nop
0x18001acac  lea     rcx, [rsp+138h+var_D0]; this
0x18001acb1  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001acb6  nop
0x18001acb7  jmp     short loc_18001ACCB
0x18001acb9  jmp     short $+2
0x18001acbb  mov     esi, [rsp+138h+var_E8]
0x18001acbf  mov     rbx, [rsp+138h+var_E0]
0x18001acc4  lea     r14, WPP_GLOBAL_Control
0x18001accb  add     rbx, 20h ; ' '
0x18001accf  jmp     loc_18001AA24
```
