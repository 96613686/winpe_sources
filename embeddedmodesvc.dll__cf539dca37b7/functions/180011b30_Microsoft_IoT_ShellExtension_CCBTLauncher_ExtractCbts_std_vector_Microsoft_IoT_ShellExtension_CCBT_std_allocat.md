# Microsoft::IoT::ShellExtension::CCBTLauncher::ExtractCbts(std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>> &,std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>> &,ushort const *)

- ea: `0x180011b30`
- end: `0x180011c2b`
- name: `?ExtractCbts@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAA_NAEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@0PEBG@Z`
- size: `251`
- prototype: `char __fastcall(__int64, __int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011c34`

## callees

- `0x180002b10`
- `0x18000fd84`
- `0x18000fffc`
- `0x180011b30`
- `0x180011df8`
- `0x180014f78`
- `0x180015000`
- `0x180015be8`
- `0x180015cd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::ExtractCbts(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  char v7; // si
  __int64 v8; // rbx
  int MatchType; // eax
  int v10; // edi
  __int64 *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v17; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v18[32]; // [rsp+28h] [rbp-50h] BYREF

  v7 = 0;
  v8 = *a2;
  while ( v8 != a2[1] )
  {
    MatchType = Microsoft::IoT::ShellExtension::CCBT::GetMatchType(v8, a4);
    if ( MatchType )
    {
      v7 = 1;
      if ( MatchType == 2 )
      {
        std::wstring::wstring(v18, *(_QWORD *)(v8 + 32));
        v10 = Microsoft::IoT::ShellExtension::CAppManager::AddBackgroundTask((__int64)v18);
        std::wstring::_Tidy_deallocate((__int64)v18);
        if ( !v10 )
        {
          v11 = *(__int64 **)(v8 + 16);
          if ( v11 )
            v12 = *v11;
          else
            v12 = 0;
          std::wstring::wstring(v18, v12);
          Microsoft::IoT::ShellExtension::CAppManager::DeleteBackgroundTask((__int64)v18, v13, v14, v15);
          std::wstring::_Tidy_deallocate((__int64)v18);
        }
      }
      std::vector<Microsoft::IoT::ShellExtension::CCBT>::emplace_back<Microsoft::IoT::ShellExtension::CCBT>(a3, v8);
      v8 = *std::vector<Microsoft::IoT::ShellExtension::CCBT>::erase((__int64)a2, &v17, v8);
    }
    else
    {
      v8 += 88;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180011b30  mov     [rsp+arg_0], rbx
0x180011b35  push    rbp
0x180011b36  push    rsi
0x180011b37  push    rdi
0x180011b38  push    r14
0x180011b3a  push    r15
0x180011b3c  sub     rsp, 50h
0x180011b40  mov     rax, cs:__security_cookie
0x180011b47  xor     rax, rsp
0x180011b4a  mov     [rsp+78h+var_30], rax
0x180011b4f  mov     rbp, r9
0x180011b52  mov     r15, r8
0x180011b55  mov     r14, rdx
0x180011b58  xor     sil, sil
0x180011b5b  mov     rbx, [rdx]
0x180011b5e  cmp     rbx, [r14+8]
0x180011b62  jz      loc_180011C07
0x180011b68  mov     rdx, rbp
0x180011b6b  mov     rcx, rbx
0x180011b6e  call    ?GetMatchType@CCBT@ShellExtension@IoT@Microsoft@@QEBA?AW4MatchType@1234@PEBG0@Z; Microsoft::IoT::ShellExtension::CCBT::GetMatchType(ushort const *,ushort const *)
0x180011b73  test    eax, eax
0x180011b75  jz      loc_180011BFE
0x180011b7b  mov     sil, 1
0x180011b7e  cmp     eax, 2
0x180011b81  jnz     short loc_180011BDB
0x180011b83  mov     rdx, [rbx+20h]
0x180011b87  lea     rcx, [rsp+78h+var_50]
0x180011b8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011b91  lea     rcx, [rsp+78h+var_50]
0x180011b96  call    ?AddBackgroundTask@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::IoT::ShellExtension::CAppManager::AddBackgroundTask(std::wstring const &)
0x180011b9b  mov     edi, eax
0x180011b9d  lea     rcx, [rsp+78h+var_50]
0x180011ba2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011ba7  test    edi, edi
0x180011ba9  jnz     short loc_180011BDB
0x180011bab  mov     rax, [rbx+10h]
0x180011baf  test    rax, rax
0x180011bb2  jz      short loc_180011BB9
0x180011bb4  mov     rdx, [rax]
0x180011bb7  jmp     short loc_180011BBB
0x180011bb9  xor     edx, edx
0x180011bbb  lea     rcx, [rsp+78h+var_50]
0x180011bc0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011bc5  nop
0x180011bc6  lea     rcx, [rsp+78h+var_50]
0x180011bcb  call    ?DeleteBackgroundTask@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::IoT::ShellExtension::CAppManager::DeleteBackgroundTask(std::wstring const &)
0x180011bd0  nop
0x180011bd1  lea     rcx, [rsp+78h+var_50]
0x180011bd6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011bdb  mov     rdx, rbx
0x180011bde  mov     rcx, r15
0x180011be1  call    ??$emplace_back@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAAAEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::emplace_back<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT &&)
0x180011be6  mov     r8, rbx
0x180011be9  lea     rdx, [rsp+78h+var_58]
0x180011bee  mov     rcx, r14
0x180011bf1  call    ?erase@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@2@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::IoT::ShellExtension::CCBT>>>)
0x180011bf6  mov     rbx, [rax]
0x180011bf9  jmp     loc_180011B5E
0x180011bfe  add     rbx, 58h ; 'X'
0x180011c02  jmp     loc_180011B5E
0x180011c07  mov     al, sil
0x180011c0a  mov     rcx, [rsp+78h+var_30]
0x180011c0f  xor     rcx, rsp; StackCookie
0x180011c12  call    __security_check_cookie
0x180011c17  mov     rbx, [rsp+78h+arg_0]
0x180011c1f  add     rsp, 50h
0x180011c23  pop     r15
0x180011c25  pop     r14
0x180011c27  pop     rdi
0x180011c28  pop     rsi
0x180011c29  pop     rbp
0x180011c2a  retn
```
