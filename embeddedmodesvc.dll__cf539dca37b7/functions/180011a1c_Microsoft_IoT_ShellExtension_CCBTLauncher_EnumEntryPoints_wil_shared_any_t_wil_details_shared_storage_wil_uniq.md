# Microsoft::IoT::ShellExtension::CCBTLauncher::EnumEntryPoints(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> const &,std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>> &)

- ea: `0x180011a1c`
- end: `0x180011b27`
- name: `?EnumEntryPoints@CCBTLauncher@ShellExtension@IoT@Microsoft@@SAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(__int64 **, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b3e8`

## callees

- `0x180005fc4`
- `0x180009f7c`
- `0x18000a060`
- `0x18000a730`
- `0x18000fd84`
- `0x180011a1c`
- `0x180011df8`
- `0x180015e98`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::EnumEntryPoints(__int64 **a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  Microsoft::IoT::ShellExtension::CCBT *v7; // rbx
  Microsoft::IoT::ShellExtension::CCBT *v8; // rdi
  __int64 v9; // rdx
  Microsoft::IoT::ShellExtension::CCBT *v10; // [rsp+20h] [rbp-20h] BYREF
  Microsoft::IoT::ShellExtension::CCBT *v11; // [rsp+28h] [rbp-18h]
  __int64 v12; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(&v10);
  v4 = Microsoft::IoT::ShellExtension::CAppManager::EnumBackgroundTaskEntryPoints(&v10);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = v10;
    v8 = v11;
    if ( v10 != v11 )
    {
      do
      {
        if ( *a1 )
          v9 = **a1;
        else
          v9 = 0;
        if ( (unsigned int)Microsoft::IoT::ShellExtension::CCBT::GetMatchType(v7, v9) )
          std::vector<Microsoft::IoT::ShellExtension::CCBT>::emplace_back<Microsoft::IoT::ShellExtension::CCBT>(
            a2,
            (__int64)v7);
        v7 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)v7 + 88);
      }
      while ( v7 != v8 );
      v8 = v11;
      v7 = v10;
    }
    if ( v7 )
    {
      std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v7, v8);
      std::_Deallocate<16>(v10, 8 * ((v12 - (__int64)v10) >> 3));
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)v4,
      (int)v10);
    if ( v10 )
    {
      std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v10, v11);
      std::_Deallocate<16>(v10, 8 * ((v12 - (__int64)v10) >> 3));
    }
    return v5;
  }
}

```

## disassembly

```asm
0x180011a1c  push    rbp
0x180011a1e  push    rbx
0x180011a1f  push    rsi
0x180011a20  push    rdi
0x180011a21  push    r14
0x180011a23  mov     rbp, rsp
0x180011a26  sub     rsp, 40h
0x180011a2a  mov     r14, rdx
0x180011a2d  mov     rsi, rcx
0x180011a30  lea     rcx, [rbp+var_20]
0x180011a34  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x180011a39  nop
0x180011a3a  xor     edx, edx
0x180011a3c  lea     rcx, [rbp+var_20]
0x180011a40  call    ?EnumBackgroundTaskEntryPoints@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@PEBG@Z; Microsoft::IoT::ShellExtension::CAppManager::EnumBackgroundTaskEntryPoints(std::vector<Microsoft::IoT::ShellExtension::CCBT> &,ushort const *)
0x180011a45  mov     ebx, eax
0x180011a47  test    eax, eax
0x180011a49  jns     short loc_180011AA0
0x180011a4b  mov     rcx, [rbp+28h]; this
0x180011a4f  mov     r9d, eax; char *
0x180011a52  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011a59  mov     edx, 63h ; 'c'; void *
0x180011a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a63  nop
0x180011a64  mov     rcx, [rbp+var_20]; this
0x180011a68  test    rcx, rcx
0x180011a6b  jz      short loc_180011A9C
0x180011a6d  mov     rdx, [rbp+var_18]
0x180011a71  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180011a76  mov     rcx, [rbp+var_20]
0x180011a7a  mov     rax, [rbp+var_10]
0x180011a7e  sub     rax, rcx
0x180011a81  sar     rax, 3
0x180011a85  mov     rdx, 2E8BA2E8BA2E8BA3h
0x180011a8f  imul    rax, rdx
0x180011a93  imul    rdx, rax, 58h ; 'X'
0x180011a97  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011a9c  mov     eax, ebx
0x180011a9e  jmp     short loc_180011B1C
0x180011aa0  mov     rbx, [rbp+var_20]
0x180011aa4  mov     rdi, [rbp+var_18]
0x180011aa8  cmp     rbx, rdi
0x180011aab  jz      short loc_180011AE4
0x180011aad  mov     rax, [rsi]
0x180011ab0  test    rax, rax
0x180011ab3  jz      short loc_180011ABA
0x180011ab5  mov     rdx, [rax]
0x180011ab8  jmp     short loc_180011ABC
0x180011aba  xor     edx, edx
0x180011abc  mov     rcx, rbx
0x180011abf  call    ?GetMatchType@CCBT@ShellExtension@IoT@Microsoft@@QEBA?AW4MatchType@1234@PEBG0@Z; Microsoft::IoT::ShellExtension::CCBT::GetMatchType(ushort const *,ushort const *)
0x180011ac4  test    eax, eax
0x180011ac6  jz      short loc_180011AD3
0x180011ac8  mov     rdx, rbx
0x180011acb  mov     rcx, r14
0x180011ace  call    ??$emplace_back@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAAAEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::emplace_back<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT &&)
0x180011ad3  add     rbx, 58h ; 'X'
0x180011ad7  cmp     rbx, rdi
0x180011ada  jnz     short loc_180011AAD
0x180011adc  mov     rdi, [rbp+var_18]
0x180011ae0  mov     rbx, [rbp+var_20]
0x180011ae4  test    rbx, rbx
0x180011ae7  jz      short loc_180011B1A
0x180011ae9  mov     rdx, rdi
0x180011aec  mov     rcx, rbx; this
0x180011aef  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180011af4  mov     rcx, [rbp+var_20]
0x180011af8  mov     rax, [rbp+var_10]
0x180011afc  sub     rax, rcx
0x180011aff  sar     rax, 3
0x180011b03  mov     rdx, 2E8BA2E8BA2E8BA3h
0x180011b0d  imul    rax, rdx
0x180011b11  imul    rdx, rax, 58h ; 'X'
0x180011b15  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011b1a  xor     eax, eax
0x180011b1c  add     rsp, 40h
0x180011b20  pop     r14
0x180011b22  pop     rdi
0x180011b23  pop     rsi
0x180011b24  pop     rbx
0x180011b25  pop     rbp
0x180011b26  retn
```
