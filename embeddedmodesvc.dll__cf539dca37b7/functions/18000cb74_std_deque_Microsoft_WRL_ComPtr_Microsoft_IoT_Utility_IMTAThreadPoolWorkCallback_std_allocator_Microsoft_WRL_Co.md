# std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>::_Emplace_back_internal<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback> &&)

- ea: `0x18000cb74`
- end: `0x18000cc0b`
- name: `??$_Emplace_back_internal@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAX$$QEAV?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000da64`

## callees

- `0x180009ebc`
- `0x18000a28c`
- `0x18000c2d8`
- `0x18000cb74`
- `0x18000e72c`
- `0x18000e88c`

## pseudocode

```c
__int64 __fastcall std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Emplace_back_internal<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 result; // rax

  v4 = *(_QWORD *)(a1 + 32);
  if ( ((*(_BYTE *)(a1 + 24) + (_BYTE)v4) & 1) == 0 && *(_QWORD *)(a1 + 16) <= (unsigned __int64)(v4 + 2) >> 1 )
    std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Growmap(a1);
  *(_QWORD *)(a1 + 24) &= 2LL * *(_QWORD *)(a1 + 16) - 1;
  v5 = *(_QWORD *)(a1 + 32) + *(_QWORD *)(a1 + 24);
  v6 = std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Getblock(a1, v5);
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v6) )
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v6) = std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
  v7 = std::_Deque_val<std::_Deque_simple_types<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>::_Address_subscript(
         a1,
         v5);
  result = std::_Default_allocator_traits<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>::construct<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(
             v8,
             v7,
             a2);
  ++*(_QWORD *)(a1 + 32);
  return result;
}

```

## disassembly

```asm
0x18000cb74  push    rbx
0x18000cb76  push    rbp
0x18000cb77  push    rsi
0x18000cb78  push    rdi
0x18000cb79  sub     rsp, 28h
0x18000cb7d  mov     rbx, rcx
0x18000cb80  mov     rbp, rdx
0x18000cb83  mov     rcx, [rcx+20h]
0x18000cb87  mov     al, cl
0x18000cb89  add     al, [rbx+18h]
0x18000cb8c  test    al, 1
0x18000cb8e  jnz     short loc_18000CBA5
0x18000cb90  lea     rax, [rcx+2]
0x18000cb94  shr     rax, 1
0x18000cb97  cmp     [rbx+10h], rax
0x18000cb9b  ja      short loc_18000CBA5
0x18000cb9d  mov     rcx, rbx
0x18000cba0  call    ?_Growmap@?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAX_K@Z; std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Growmap(unsigned __int64)
0x18000cba5  mov     rax, [rbx+10h]
0x18000cba9  mov     rcx, rbx
0x18000cbac  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rax*2]
0x18000cbb4  and     [rbx+18h], rax
0x18000cbb8  mov     rsi, [rbx+18h]
0x18000cbbc  add     rsi, [rbx+20h]
0x18000cbc0  mov     rdx, rsi
0x18000cbc3  call    ?_Getblock@?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEBA_J_K@Z; std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Getblock(unsigned __int64)
0x18000cbc8  mov     rcx, [rbx+8]
0x18000cbcc  mov     rdi, rax
0x18000cbcf  cmp     qword ptr [rcx+rax*8], 0
0x18000cbd4  jnz     short loc_18000CBE8
0x18000cbd6  mov     ecx, 10h
0x18000cbdb  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000cbe0  mov     rcx, [rbx+8]
0x18000cbe4  mov     [rcx+rdi*8], rax
0x18000cbe8  mov     rdx, rsi
0x18000cbeb  mov     rcx, rbx
0x18000cbee  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAAPEAV?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@_K@Z; std::_Deque_val<std::_Deque_simple_types<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>::_Address_subscript(unsigned __int64)
0x18000cbf3  mov     r8, rbp
0x18000cbf6  mov     rdx, rax
0x18000cbf9  call    ??$construct@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V123@@?$_Default_allocator_traits@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@SAXAEAV?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@1@QEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@$$QEAV345@@Z; std::_Default_allocator_traits<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>::construct<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>> &,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> &&)
0x18000cbfe  inc     qword ptr [rbx+20h]
0x18000cc02  add     rsp, 28h
0x18000cc06  pop     rdi
0x18000cc07  pop     rsi
0x18000cc08  pop     rbp
0x18000cc09  pop     rbx
0x18000cc0a  retn
```
