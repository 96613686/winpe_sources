# Container::Manager::Tools::CommandLineParser::GetArgumentValue(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x140020c70`
- end: `0x140020d03`
- name: `?GetArgumentValue@CommandLineParser@Tools@Manager@Container@@QEBAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@6@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140020d0c`

## callees

- `0x140006fe4`
- `0x14000cd84`
- `0x14000d7bc`
- `0x140020b78`
- `0x140020c70`

## pseudocode

```c
int __fastcall Container::Manager::Tools::CommandLineParser::GetArgumentValue(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  unsigned int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1 + 32;
  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::find<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>>(
    a1 + 32,
    &v8,
    a2);
  if ( v8 == v4 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xE0,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\tools\\helpers\\helpers.cpp",
             (const char *)0x490,
             v6);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          a3,
                          *(_QWORD *)(v8 + 56),
                          (__int64)(*(_QWORD *)(v8 + 64) - *(_QWORD *)(v8 + 56)) >> 1) )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE3,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\tools\\helpers\\helpers.cpp",
    (const char *)0x8007000ELL,
    v6);
  return -2147024882;
}

```

## disassembly

```asm
0x140020c70  mov     [rsp+arg_8], rbx
0x140020c75  push    rdi; int
0x140020c76  sub     rsp, 20h
0x140020c7a  mov     rdi, r8
0x140020c7d  lea     rbx, [rcx+20h]
0x140020c81  mov     r8, rdx
0x140020c84  lea     rdx, [rsp+28h+arg_0]
0x140020c89  mov     rcx, rbx
0x140020c8c  call    ??$find@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEBA?AV?$_TreeConstIt@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@1@AEBV?$basic_string_view@GU?$char_traits@G@utl@@@1@@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::find<utl::basic_string_view<ushort,utl::char_traits<ushort>>>(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140020c91  mov     rax, [rsp+28h+arg_0]
0x140020c96  cmp     rax, rbx
0x140020c99  jnz     short loc_140020CB9
0x140020c9b  mov     rcx, [rsp+28h]; this
0x140020ca0  mov     r9d, 490h; char *
0x140020ca6  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\too"...
0x140020cad  mov     edx, 0E0h; void *
0x140020cb2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140020cb7  jmp     short loc_140020CF7
0x140020cb9  mov     rdx, [rax+38h]
0x140020cbd  mov     r8, [rax+40h]
0x140020cc1  sub     r8, rdx
0x140020cc4  sar     r8, 1
0x140020cc7  mov     rcx, rdi
0x140020cca  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140020ccf  test    al, al
0x140020cd1  jnz     short loc_140020CF5
0x140020cd3  mov     rcx, [rsp+28h]; this
0x140020cd8  mov     ebx, 8007000Eh
0x140020cdd  mov     r9d, ebx; char *
0x140020ce0  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\too"...
0x140020ce7  mov     edx, 0E3h; void *
0x140020cec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020cf1  mov     eax, ebx
0x140020cf3  jmp     short loc_140020CF7
0x140020cf5  xor     eax, eax
0x140020cf7  mov     rbx, [rsp+28h+arg_8]
0x140020cfc  add     rsp, 20h
0x140020d00  pop     rdi
0x140020d01  retn
```
