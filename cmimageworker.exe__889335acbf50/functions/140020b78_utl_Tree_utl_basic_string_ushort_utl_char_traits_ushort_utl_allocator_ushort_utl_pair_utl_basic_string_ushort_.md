# utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::find<utl::basic_string_view<ushort,utl::char_traits<ushort>>>(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)

- ea: `0x140020b78`
- end: `0x140020c00`
- name: `??$find@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEBA?AV?$_TreeConstIt@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@1@AEBV?$basic_string_view@GU?$char_traits@G@utl@@@1@@Z`
- size: `136`
- prototype: `void ***__fastcall(void **, void ***, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400094c8`
- `0x140020c08`
- `0x140020c70`

## callees

- `0x140020b78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140020ba0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140020bdb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140020ba0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140020bdb`

## pseudocode

```c
void ***__fastcall utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::find<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>>(
        void **a1,
        void ***a2,
        _QWORD *a3)
{
  void **v6; // rdi
  void **v7; // rsi
  __int64 v8; // rax

  v6 = a1;
  if ( a1[2] != a1 )
  {
    v7 = (void **)*a1;
    do
    {
      if ( (int)_o__wcsicmp(v7[3], *a3) >= 0 )
      {
        v6 = v7;
        v8 = 1;
      }
      else
      {
        v8 = 2;
      }
      v7 = (void **)v7[v8];
    }
    while ( v7 != &utl::_TreeSentinel );
    if ( v6 != a1 && (int)_o__wcsicmp(*a3, v6[3]) < 0 )
      v6 = a1;
  }
  *a2 = v6;
  return a2;
}

```

## disassembly

```asm
0x140020b78  push    rbx
0x140020b7a  push    rsi
0x140020b7b  push    rdi
0x140020b7c  push    r14
0x140020b7e  push    r15
0x140020b80  sub     rsp, 20h
0x140020b84  mov     r15, r8
0x140020b87  mov     r14, rdx
0x140020b8a  mov     rbx, rcx
0x140020b8d  mov     rdi, rcx
0x140020b90  cmp     [rcx+10h], rcx
0x140020b94  jz      short loc_140020BED
0x140020b96  mov     rsi, [rcx]
0x140020b99  mov     rdx, [r15]
0x140020b9c  mov     rcx, [rsi+18h]
0x140020ba0  call    cs:__imp__o__wcsicmp
0x140020ba7  nop     dword ptr [rax+rax+00h]
0x140020bac  test    eax, eax
0x140020bae  jns     short loc_140020BB7
0x140020bb0  mov     eax, 10h
0x140020bb5  jmp     short loc_140020BBF
0x140020bb7  mov     rdi, rsi
0x140020bba  mov     eax, 8
0x140020bbf  mov     rsi, [rax+rsi]
0x140020bc3  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140020bca  cmp     rsi, rax
0x140020bcd  jnz     short loc_140020B99
0x140020bcf  cmp     rdi, rbx
0x140020bd2  jz      short loc_140020BED
0x140020bd4  mov     rdx, [rdi+18h]
0x140020bd8  mov     rcx, [r15]
0x140020bdb  call    cs:__imp__o__wcsicmp
0x140020be2  nop     dword ptr [rax+rax+00h]
0x140020be7  test    eax, eax
0x140020be9  cmovs   rdi, rbx
0x140020bed  mov     [r14], rdi
0x140020bf0  mov     rax, r14
0x140020bf3  add     rsp, 20h
0x140020bf7  pop     r15
0x140020bf9  pop     r14
0x140020bfb  pop     rdi
0x140020bfc  pop     rsi
0x140020bfd  pop     rbx
0x140020bfe  retn
```
