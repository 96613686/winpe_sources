# Microsoft::IoT::ShellExtension::CCBTLauncher::GetAutoStartCBTs(std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>> &)

- ea: `0x180011c34`
- end: `0x180011df0`
- name: `?GetAutoStartCBTs@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJAEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013360`

## callees

- `0x180005fc4`
- `0x180009f7c`
- `0x18000a060`
- `0x18000a730`
- `0x18000f930`
- `0x18000ffb4`
- `0x180011b30`
- `0x180011c34`
- `0x180014f58`
- `0x180014f78`
- `0x180014fd0`
- `0x180015e98`
- `0x180017764`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::GetAutoStartCBTs(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int BackgroundTaskNames; // eax
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-58h] BYREF
  __int128 v12; // [rsp+28h] [rbp-50h]
  Microsoft::IoT::ShellExtension::CCBT *v13; // [rsp+38h] [rbp-40h] BYREF
  __int64 v14; // [rsp+48h] [rbp-30h]
  _BYTE v15[40]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  std::vector<Microsoft::IoT::ShellExtension::CCBT>::clear(a2);
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(&v13);
  v3 = Microsoft::IoT::ShellExtension::CAppManager::EnumBackgroundTaskEntryPoints(&v13, 0);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)v3,
      v11);
LABEL_3:
    if ( v13 )
    {
      std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v13);
      std::_Deallocate<16>(v13, 8 * ((v14 - (__int64)v13) >> 3));
    }
    return v4;
  }
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(&v11);
  BackgroundTaskNames = Microsoft::IoT::ShellExtension::CAppManager::GetBackgroundTaskNames((__int64)&v11);
  v4 = BackgroundTaskNames;
  if ( BackgroundTaskNames < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)BackgroundTaskNames,
      v11);
    if ( v11 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v11, v12);
      std::_Deallocate<16>(v11, (*((_QWORD *)&v12 + 1) - v11) & 0xFFFFFFFFFFFFFFE0uLL);
      v11 = 0;
      v12 = 0;
    }
    goto LABEL_3;
  }
  v7 = v11;
  v8 = v12;
  if ( v11 != (_QWORD)v12 )
  {
    do
    {
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
      if ( !(unsigned __int8)Microsoft::IoT::ShellExtension::CCBTLauncher::ExtractCbts(v10, &v13, a2, v9) )
      {
        std::wstring::wstring(v15, v7);
        std::wstring::_Tidy_deallocate(v15);
      }
      v7 += 32;
    }
    while ( v7 != v8 );
    v8 = v12;
    v7 = v11;
  }
  if ( v7 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v7, v8);
    std::_Deallocate<16>(v11, (*((_QWORD *)&v12 + 1) - v11) & 0xFFFFFFFFFFFFFFE0uLL);
    v11 = 0;
    v12 = 0;
  }
  if ( v13 )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v13);
    std::_Deallocate<16>(v13, 8 * ((v14 - (__int64)v13) >> 3));
  }
  return 0;
}

```

## disassembly

```asm
0x180011c34  push    rbp
0x180011c36  push    rbx
0x180011c37  push    rsi
0x180011c38  push    rdi
0x180011c39  mov     rbp, rsp
0x180011c3c  sub     rsp, 78h
0x180011c40  mov     rsi, rdx
0x180011c43  mov     rcx, rdx
0x180011c46  call    ?clear@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAAXXZ; std::vector<Microsoft::IoT::ShellExtension::CCBT>::clear(void)
0x180011c4b  lea     rcx, [rbp+var_40]
0x180011c4f  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x180011c54  nop
0x180011c55  xor     edx, edx
0x180011c57  lea     rcx, [rbp+var_40]
0x180011c5b  call    ?EnumBackgroundTaskEntryPoints@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@PEBG@Z; Microsoft::IoT::ShellExtension::CAppManager::EnumBackgroundTaskEntryPoints(std::vector<Microsoft::IoT::ShellExtension::CCBT> &,ushort const *)
0x180011c60  mov     ebx, eax
0x180011c62  test    eax, eax
0x180011c64  jns     short loc_180011CBE
0x180011c66  mov     rcx, [rbp+20h]; this
0x180011c6a  mov     r9d, eax; char *
0x180011c6d  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011c74  mov     edx, 82h; void *
0x180011c79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c7e  nop
0x180011c7f  mov     rcx, [rbp+var_40]; this
0x180011c83  test    rcx, rcx
0x180011c86  jz      short loc_180011CB7
0x180011c88  mov     rdx, [rbp+var_38]
0x180011c8c  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180011c91  mov     rcx, [rbp+var_40]
0x180011c95  mov     rax, [rbp+var_30]
0x180011c99  sub     rax, rcx
0x180011c9c  sar     rax, 3
0x180011ca0  mov     rdx, 2E8BA2E8BA2E8BA3h
0x180011caa  imul    rax, rdx
0x180011cae  imul    rdx, rax, 58h ; 'X'
0x180011cb2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011cb7  mov     eax, ebx
0x180011cb9  jmp     loc_180011DE7
0x180011cbe  lea     rcx, [rbp+var_58]
0x180011cc2  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x180011cc7  nop
0x180011cc8  lea     rcx, [rbp+var_58]
0x180011ccc  call    ?GetBackgroundTaskNames@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::IoT::ShellExtension::CAppManager::GetBackgroundTaskNames(std::vector<std::wstring> &)
0x180011cd1  mov     ebx, eax
0x180011cd3  test    eax, eax
0x180011cd5  jns     short loc_180011D2B
0x180011cd7  mov     rcx, [rbp+20h]; this
0x180011cdb  mov     r9d, eax; char *
0x180011cde  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011ce5  mov     edx, 85h; void *
0x180011cea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011cef  nop
0x180011cf0  mov     rcx, [rbp+var_58]
0x180011cf4  test    rcx, rcx
0x180011cf7  jz      short loc_180011C7F
0x180011cf9  mov     rdx, qword ptr [rbp+var_50]
0x180011cfd  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180011d02  mov     rcx, [rbp+var_58]
0x180011d06  mov     rdx, qword ptr [rbp+var_50+8]
0x180011d0a  sub     rdx, rcx
0x180011d0d  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180011d11  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011d16  mov     [rbp+var_58], 0
0x180011d1e  xorps   xmm0, xmm0
0x180011d21  movdqu  [rbp+var_50], xmm0
0x180011d26  jmp     loc_180011C7F
0x180011d2b  mov     rbx, [rbp+var_58]
0x180011d2f  mov     rdi, qword ptr [rbp+var_50]
0x180011d33  cmp     rbx, rdi
0x180011d36  jz      short loc_180011D79
0x180011d38  mov     rcx, rbx
0x180011d3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011d40  mov     r9, rax
0x180011d43  mov     r8, rsi
0x180011d46  lea     rdx, [rbp+var_40]
0x180011d4a  call    ?ExtractCbts@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAA_NAEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@0PEBG@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::ExtractCbts(std::vector<Microsoft::IoT::ShellExtension::CCBT> &,std::vector<Microsoft::IoT::ShellExtension::CCBT> &,ushort const *)
0x180011d4f  test    al, al
0x180011d51  jnz     short loc_180011D68
0x180011d53  mov     rdx, rbx
0x180011d56  lea     rcx, [rbp+var_28]
0x180011d5a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011d5f  lea     rcx, [rbp+var_28]
0x180011d63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011d68  add     rbx, 20h ; ' '
0x180011d6c  cmp     rbx, rdi
0x180011d6f  jnz     short loc_180011D38
0x180011d71  mov     rdi, qword ptr [rbp+var_50]
0x180011d75  mov     rbx, [rbp+var_58]
0x180011d79  test    rbx, rbx
0x180011d7c  jz      short loc_180011DAD
0x180011d7e  mov     rdx, rdi
0x180011d81  mov     rcx, rbx
0x180011d84  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180011d89  mov     rcx, [rbp+var_58]
0x180011d8d  mov     rdx, qword ptr [rbp+var_50+8]
0x180011d91  sub     rdx, rcx
0x180011d94  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180011d98  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011d9d  mov     [rbp+var_58], 0
0x180011da5  xorps   xmm0, xmm0
0x180011da8  movdqu  [rbp+var_50], xmm0
0x180011dad  mov     rcx, [rbp+var_40]; this
0x180011db1  test    rcx, rcx
0x180011db4  jz      short loc_180011DE5
0x180011db6  mov     rdx, [rbp+var_38]
0x180011dba  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180011dbf  mov     rcx, [rbp+var_40]
0x180011dc3  mov     rax, [rbp+var_30]
0x180011dc7  sub     rax, rcx
0x180011dca  sar     rax, 3
0x180011dce  mov     rdx, 2E8BA2E8BA2E8BA3h
0x180011dd8  imul    rax, rdx
0x180011ddc  imul    rdx, rax, 58h ; 'X'
0x180011de0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011de5  xor     eax, eax
0x180011de7  add     rsp, 78h
0x180011deb  pop     rdi
0x180011dec  pop     rsi
0x180011ded  pop     rbx
0x180011dee  pop     rbp
0x180011def  retn
```
