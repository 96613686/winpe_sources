# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>> &&)

- ea: `0x18000aa50`
- end: `0x18000aaec`
- name: `??4?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b67c`

## callees

- `0x18000aa50`
- `0x18000c648`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::operator=(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

  if ( a1 != a2 )
  {
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear();
    *(_DWORD *)a1 = *(_DWORD *)a2;
    v4 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
    *(_QWORD *)(a2 + 8) = v4;
    v5 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = v5;
    v6 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = *(_QWORD *)(a2 + 24);
    *(_QWORD *)(a2 + 24) = v6;
    v7 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = *(_QWORD *)(a2 + 32);
    *(_QWORD *)(a2 + 32) = v7;
    v8 = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a2 + 40);
    *(_QWORD *)(a2 + 40) = v8;
    v9 = *(_QWORD *)(a1 + 48);
    *(_QWORD *)(a1 + 48) = *(_QWORD *)(a2 + 48);
    *(_QWORD *)(a2 + 48) = v9;
    v10 = *(_QWORD *)(a1 + 56);
    *(_QWORD *)(a1 + 56) = *(_QWORD *)(a2 + 56);
    *(_QWORD *)(a2 + 56) = v10;
  }
  return a1;
}

```

## disassembly

```asm
0x18000aa50  mov     [rsp+arg_0], rbx
0x18000aa55  push    rdi
0x18000aa56  sub     rsp, 20h
0x18000aa5a  mov     rdi, rdx
0x18000aa5d  mov     rbx, rcx
0x18000aa60  cmp     rcx, rdx
0x18000aa63  jz      short loc_18000AADE
0x18000aa65  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x18000aa6a  mov     eax, [rdi]
0x18000aa6c  mov     [rbx], eax
0x18000aa6e  mov     rax, [rdi+8]
0x18000aa72  mov     rcx, [rbx+8]
0x18000aa76  mov     [rbx+8], rax
0x18000aa7a  mov     [rdi+8], rcx
0x18000aa7e  mov     rax, [rdi+10h]
0x18000aa82  mov     rcx, [rbx+10h]
0x18000aa86  mov     [rbx+10h], rax
0x18000aa8a  mov     [rdi+10h], rcx
0x18000aa8e  mov     rax, [rdi+18h]
0x18000aa92  mov     rcx, [rbx+18h]
0x18000aa96  mov     [rbx+18h], rax
0x18000aa9a  mov     [rdi+18h], rcx
0x18000aa9e  mov     rax, [rdi+20h]
0x18000aaa2  mov     rcx, [rbx+20h]
0x18000aaa6  mov     [rbx+20h], rax
0x18000aaaa  mov     [rdi+20h], rcx
0x18000aaae  mov     rax, [rdi+28h]
0x18000aab2  mov     rcx, [rbx+28h]
0x18000aab6  mov     [rbx+28h], rax
0x18000aaba  mov     [rdi+28h], rcx
0x18000aabe  mov     rax, [rdi+30h]
0x18000aac2  mov     rcx, [rbx+30h]
0x18000aac6  mov     [rbx+30h], rax
0x18000aaca  mov     [rdi+30h], rcx
0x18000aace  mov     rax, [rdi+38h]
0x18000aad2  mov     rcx, [rbx+38h]
0x18000aad6  mov     [rbx+38h], rax
0x18000aada  mov     [rdi+38h], rcx
0x18000aade  mov     rax, rbx
0x18000aae1  mov     rbx, [rsp+28h+arg_0]
0x18000aae6  add     rsp, 20h
0x18000aaea  pop     rdi
0x18000aaeb  retn
```
