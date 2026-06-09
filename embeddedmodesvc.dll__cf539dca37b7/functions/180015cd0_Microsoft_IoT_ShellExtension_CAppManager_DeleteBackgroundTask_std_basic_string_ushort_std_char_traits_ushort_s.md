# Microsoft::IoT::ShellExtension::CAppManager::DeleteBackgroundTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180015cd0`
- end: `0x180015e91`
- name: `?DeleteBackgroundTask@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011b30`

## callees

- `0x180002b10`
- `0x180005fc4`
- `0x180009f7c`
- `0x18000a060`
- `0x18000a730`
- `0x18000fffc`
- `0x180011df8`
- `0x180014f58`
- `0x180014f78`
- `0x180015cd0`
- `0x180015e98`
- `0x1800176fc`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CAppManager::DeleteBackgroundTask(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  Microsoft::IoT::ShellExtension::CCBT *v7; // rcx
  Microsoft::IoT::ShellExtension::CCBT *v9; // rbx
  Microsoft::IoT::ShellExtension::CCBT *i; // rdi
  __int64 v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // edi
  Microsoft::IoT::ShellExtension::CCBT *v22; // [rsp+20h] [rbp-48h] BYREF
  Microsoft::IoT::ShellExtension::CCBT *v23; // [rsp+28h] [rbp-40h]
  __int64 v24; // [rsp+30h] [rbp-38h]
  _BYTE v25[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  if ( Microsoft::IoT::ShellExtension::CAppManager::ExactDeleteBackgroundTask(a1, a2, a3, a4, (unsigned int)v22) < 0 )
  {
    std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(&v22);
    v5 = Microsoft::IoT::ShellExtension::CAppManager::EnumBackgroundTaskEntryPoints(&v22);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v9 = v22;
      for ( i = v22; ; i = (Microsoft::IoT::ShellExtension::CCBT *)((char *)i + 88) )
      {
        if ( i == v23 )
        {
          if ( v9 )
          {
            std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v9, v23);
            std::_Deallocate<16>(v22, 8 * ((v24 - (__int64)v22) >> 3));
          }
          return 2147946712LL;
        }
        v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
        if ( (unsigned int)Microsoft::IoT::ShellExtension::CCBT::GetMatchType(i, v11) - 1 < 2 )
          break;
      }
      v12 = (__int64 *)*((_QWORD *)i + 2);
      if ( v12 )
        v13 = *v12;
      else
        v13 = 0;
      std::wstring::wstring(v25, v13);
      v17 = Microsoft::IoT::ShellExtension::CAppManager::ExactDeleteBackgroundTask(
              (__int64)v25,
              v14,
              v15,
              v16,
              (unsigned int)v22);
      std::wstring::_Tidy_deallocate((__int64)v25);
      std::wstring::wstring(v25, *((_QWORD *)i + 4));
      v21 = Microsoft::IoT::ShellExtension::CAppManager::ExactDeleteBackgroundTask(
              (__int64)v25,
              v18,
              v19,
              v20,
              (unsigned int)v22);
      std::wstring::_Tidy_deallocate((__int64)v25);
      if ( v17 >= 0 || v21 >= 0 )
        v6 = 0;
      else
        v6 = -2147020584;
      v7 = v22;
      if ( !v22 )
        return v6;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\iotappmanager.cpp",
        (const char *)(unsigned int)v5,
        (int)v22);
      v7 = v22;
      if ( !v22 )
        return v6;
    }
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v7, v23);
    std::_Deallocate<16>(v22, 8 * ((v24 - (__int64)v22) >> 3));
    return v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180015cd0  push    rbp
0x180015cd2  push    rbx
0x180015cd3  push    rsi
0x180015cd4  push    rdi
0x180015cd5  mov     rbp, rsp
0x180015cd8  sub     rsp, 68h
0x180015cdc  mov     rax, cs:__security_cookie
0x180015ce3  xor     rax, rsp
0x180015ce6  mov     [rbp+var_10], rax
0x180015cea  mov     rsi, rcx
0x180015ced  call    ?ExactDeleteBackgroundTask@CAppManager@ShellExtension@IoT@Microsoft@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::IoT::ShellExtension::CAppManager::ExactDeleteBackgroundTask(std::wstring const &)
0x180015cf2  test    eax, eax
0x180015cf4  jns     loc_180015E7A
0x180015cfa  lea     rcx, [rbp+var_48]
0x180015cfe  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x180015d03  nop
0x180015d04  xor     edx, edx
0x180015d06  lea     rcx, [rbp+var_48]
0x180015d0a  call    ?EnumBackgroundTaskEntryPoints@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@PEBG@Z; Microsoft::IoT::ShellExtension::CAppManager::EnumBackgroundTaskEntryPoints(std::vector<Microsoft::IoT::ShellExtension::CCBT> &,ushort const *)
0x180015d0f  mov     ebx, eax
0x180015d11  test    eax, eax
0x180015d13  jns     short loc_180015D6D
0x180015d15  mov     rcx, [rbp+20h]; this
0x180015d19  mov     r9d, eax; char *
0x180015d1c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180015d23  mov     edx, 6Fh ; 'o'; void *
0x180015d28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015d2d  nop
0x180015d2e  mov     rcx, [rbp+var_48]; this
0x180015d32  test    rcx, rcx
0x180015d35  jz      short loc_180015D66
0x180015d37  mov     rdx, [rbp+var_40]
0x180015d3b  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180015d40  mov     rcx, [rbp+var_48]
0x180015d44  mov     rax, [rbp+var_38]
0x180015d48  sub     rax, rcx
0x180015d4b  sar     rax, 3
0x180015d4f  mov     r8, 2E8BA2E8BA2E8BA3h
0x180015d59  imul    rax, r8
0x180015d5d  imul    rdx, rax, 58h ; 'X'
0x180015d61  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015d66  mov     eax, ebx
0x180015d68  jmp     loc_180015E7C
0x180015d6d  mov     rbx, [rbp+var_48]
0x180015d71  mov     rdi, rbx
0x180015d74  cmp     rdi, [rbp+var_40]
0x180015d78  jz      loc_180015E3C
0x180015d7e  mov     rcx, rsi
0x180015d81  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015d86  mov     rdx, rax
0x180015d89  mov     rcx, rdi
0x180015d8c  call    ?GetMatchType@CCBT@ShellExtension@IoT@Microsoft@@QEBA?AW4MatchType@1234@PEBG0@Z; Microsoft::IoT::ShellExtension::CCBT::GetMatchType(ushort const *,ushort const *)
0x180015d91  sub     eax, 1
0x180015d94  jz      short loc_180015DA1
0x180015d96  cmp     eax, 1
0x180015d99  jz      short loc_180015DA1
0x180015d9b  add     rdi, 58h ; 'X'
0x180015d9f  jmp     short loc_180015D74
0x180015da1  mov     rax, [rdi+10h]
0x180015da5  test    rax, rax
0x180015da8  jz      short loc_180015DAF
0x180015daa  mov     rdx, [rax]
0x180015dad  jmp     short loc_180015DB1
0x180015daf  xor     edx, edx
0x180015db1  lea     rcx, [rbp+var_30]
0x180015db5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015dba  lea     rcx, [rbp+var_30]
0x180015dbe  call    ?ExactDeleteBackgroundTask@CAppManager@ShellExtension@IoT@Microsoft@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::IoT::ShellExtension::CAppManager::ExactDeleteBackgroundTask(std::wstring const &)
0x180015dc3  mov     ebx, eax
0x180015dc5  lea     rcx, [rbp+var_30]
0x180015dc9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015dce  mov     rdx, [rdi+20h]
0x180015dd2  lea     rcx, [rbp+var_30]
0x180015dd6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015ddb  lea     rcx, [rbp+var_30]
0x180015ddf  call    ?ExactDeleteBackgroundTask@CAppManager@ShellExtension@IoT@Microsoft@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::IoT::ShellExtension::CAppManager::ExactDeleteBackgroundTask(std::wstring const &)
0x180015de4  mov     edi, eax
0x180015de6  lea     rcx, [rbp+var_30]
0x180015dea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015def  test    ebx, ebx
0x180015df1  jns     short loc_180015DFE
0x180015df3  test    edi, edi
0x180015df5  jns     short loc_180015DFE
0x180015df7  mov     ebx, 800710D8h
0x180015dfc  jmp     short loc_180015E00
0x180015dfe  xor     ebx, ebx
0x180015e00  mov     rcx, [rbp+var_48]; this
0x180015e04  test    rcx, rcx
0x180015e07  jz      loc_180015D66
0x180015e0d  mov     rdx, [rbp+var_40]
0x180015e11  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180015e16  mov     rcx, [rbp+var_48]
0x180015e1a  mov     rdx, [rbp+var_38]
0x180015e1e  sub     rdx, rcx
0x180015e21  sar     rdx, 3
0x180015e25  mov     r8, 2E8BA2E8BA2E8BA3h
0x180015e2f  imul    rdx, r8
0x180015e33  imul    rdx, 58h ; 'X'
0x180015e37  jmp     loc_180015D61
0x180015e3c  test    rbx, rbx
0x180015e3f  jz      short loc_180015E73
0x180015e41  mov     rdx, [rbp+var_40]
0x180015e45  mov     rcx, rbx; this
0x180015e48  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180015e4d  mov     rcx, [rbp+var_48]
0x180015e51  mov     rax, [rbp+var_38]
0x180015e55  sub     rax, rcx
0x180015e58  sar     rax, 3
0x180015e5c  mov     r8, 2E8BA2E8BA2E8BA3h
0x180015e66  imul    rax, r8
0x180015e6a  imul    rdx, rax, 58h ; 'X'
0x180015e6e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015e73  mov     eax, 800710D8h
0x180015e78  jmp     short loc_180015E7C
0x180015e7a  xor     eax, eax
0x180015e7c  mov     rcx, [rbp+var_10]
0x180015e80  xor     rcx, rsp; StackCookie
0x180015e83  call    __security_check_cookie
0x180015e88  add     rsp, 68h
0x180015e8c  pop     rdi
0x180015e8d  pop     rsi
0x180015e8e  pop     rbx
0x180015e8f  pop     rbp
0x180015e90  retn
```
