# HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001e3ec`
- end: `0x18001e4af`
- name: `??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800031b0`

## callees

- `0x180006330`
- `0x18001aaa0`
- `0x18001c6dc`

## pseudocode

```c
__int64 __fastcall HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  std::wstring::wstring(a1, a2);
  std::wstring::wstring(a1 + 32, a3);
  std::wstring::wstring(a1 + 64, a4);
  *(_DWORD *)(a1 + 96) = a5;
  *(_DWORD *)(a1 + 100) = a6;
  std::wstring::wstring(a1 + 104, a7);
  std::wstring::_Tidy_deallocate(a2);
  std::wstring::_Tidy_deallocate(a3);
  std::wstring::_Tidy_deallocate(a4);
  std::wstring::_Tidy_deallocate(a7);
  return a1;
}

```

## disassembly

```asm
0x18001e3ec  mov     r11, rsp
0x18001e3ef  push    rbx
0x18001e3f0  push    rbp
0x18001e3f1  push    rsi
0x18001e3f2  push    rdi
0x18001e3f3  push    r14
0x18001e3f5  sub     rsp, 60h
0x18001e3f9  mov     rax, cs:__security_cookie
0x18001e400  xor     rax, rsp
0x18001e403  mov     [rsp+88h+var_38], rax
0x18001e408  mov     r14, r9
0x18001e40b  mov     rsi, r8
0x18001e40e  mov     rdi, rdx
0x18001e411  mov     rbp, rcx
0x18001e414  mov     [r11-68h], rcx
0x18001e418  mov     [r11-58h], rdx
0x18001e41c  mov     [r11-50h], r8
0x18001e420  mov     [r11-48h], r9
0x18001e424  mov     rbx, [rsp+88h+arg_30]
0x18001e42c  mov     [r11-40h], rbx
0x18001e430  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e435  nop
0x18001e436  lea     rcx, [rbp+20h]
0x18001e43a  mov     rdx, rsi
0x18001e43d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e442  nop
0x18001e443  lea     rcx, [rbp+40h]
0x18001e447  mov     rdx, r14
0x18001e44a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e44f  nop
0x18001e450  mov     eax, [rsp+88h+arg_20]
0x18001e457  mov     [rbp+60h], eax
0x18001e45a  mov     eax, [rsp+88h+arg_28]
0x18001e461  mov     [rbp+64h], eax
0x18001e464  lea     rcx, [rbp+68h]
0x18001e468  mov     rdx, rbx
0x18001e46b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e470  nop
0x18001e471  mov     rcx, rdi
0x18001e474  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e479  nop
0x18001e47a  mov     rcx, rsi
0x18001e47d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e482  nop
0x18001e483  mov     rcx, r14
0x18001e486  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e48b  nop
0x18001e48c  mov     rcx, rbx
0x18001e48f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e494  mov     rax, rbp
0x18001e497  mov     rcx, [rsp+88h+var_38]
0x18001e49c  xor     rcx, rsp; StackCookie
0x18001e49f  call    __security_check_cookie
0x18001e4a4  add     rsp, 60h
0x18001e4a8  pop     r14
0x18001e4aa  pop     rdi
0x18001e4ab  pop     rsi
0x18001e4ac  pop     rbp
0x18001e4ad  pop     rbx
0x18001e4ae  retn
```
