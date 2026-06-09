# Container::Manager::Tools::CommandLineParser::GetArgumentValue(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,Csl::Path &)

- ea: `0x140020d0c`
- end: `0x140020df7`
- name: `?GetArgumentValue@CommandLineParser@Tools@Manager@Container@@QEBAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@AEAVPath@Csl@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400094c8`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000aa58`
- `0x140020c70`
- `0x140020d0c`

## pseudocode

```c
__int64 __fastcall Container::Manager::Tools::CommandLineParser::GetArgumentValue(
        __int64 a1,
        __int64 a2,
        Csl::Path *a3)
{
  int ArgumentValue; // eax
  unsigned int v5; // ebx
  void *v6; // rcx
  bool v7; // zf
  _QWORD v9[2]; // [rsp+20h] [rbp-30h] BYREF
  void *v10; // [rsp+30h] [rbp-20h] BYREF
  char *v11; // [rsp+38h] [rbp-18h]
  _WORD v12[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v10 = v12;
  v11 = (char *)v12;
  v12[0] = 0;
  ArgumentValue = Container::Manager::Tools::CommandLineParser::GetArgumentValue(a1, a2, (__int64)&v10);
  v5 = ArgumentValue;
  if ( ArgumentValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\tools\\helpers\\helpers.cpp",
      (const char *)(unsigned int)ArgumentValue,
      v9[0]);
    v6 = v10;
    v7 = v10 == v12;
LABEL_3:
    if ( !v7 )
      operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
    return v5;
  }
  v9[0] = v10;
  v9[1] = (v11 - (_BYTE *)v10) >> 1;
  if ( !Csl::Path::Assign(a3, v9) )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\tools\\helpers\\helpers.cpp",
      (const char *)0x8007000ELL,
      v9[0]);
    v6 = v10;
    v7 = v10 == v12;
    goto LABEL_3;
  }
  if ( v10 != v12 )
    operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x140020d0c  mov     [rsp-8+arg_0], rbx
0x140020d11  mov     [rsp-8+arg_8], rdi
0x140020d16  push    rbp
0x140020d17  mov     rbp, rsp
0x140020d1a  sub     rsp, 50h
0x140020d1e  lea     rax, [rbp+var_10]
0x140020d22  mov     rdi, r8
0x140020d25  mov     [rbp+var_20], rax
0x140020d29  lea     r8, [rbp+var_20]
0x140020d2d  lea     rax, [rbp+var_10]
0x140020d31  mov     [rbp+var_18], rax
0x140020d35  xor     eax, eax
0x140020d37  mov     [rbp+var_10], ax
0x140020d3b  call    ?GetArgumentValue@CommandLineParser@Tools@Manager@Container@@QEBAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@6@@Z; Container::Manager::Tools::CommandLineParser::GetArgumentValue(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x140020d40  mov     ebx, eax
0x140020d42  test    eax, eax
0x140020d44  jns     short loc_140020D7B
0x140020d46  mov     rcx, [rbp+8]; this
0x140020d4a  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\too"...
0x140020d51  mov     r9d, eax; char *
0x140020d54  mov     edx, 101h; void *
0x140020d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020d5e  mov     rcx, [rbp+var_20]; void *
0x140020d62  lea     rax, [rbp+var_10]
0x140020d66  cmp     rcx, rax
0x140020d69  jz      short loc_140020D77
0x140020d6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140020d72  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140020d77  mov     eax, ebx
0x140020d79  jmp     short loc_140020DE6
0x140020d7b  mov     rax, [rbp+var_20]
0x140020d7f  lea     rdx, [rbp+var_30]
0x140020d83  mov     rcx, [rbp+var_18]
0x140020d87  sub     rcx, rax
0x140020d8a  mov     [rbp+var_30], rax
0x140020d8e  sar     rcx, 1
0x140020d91  mov     [rbp+var_28], rcx
0x140020d95  mov     rcx, rdi; this
0x140020d98  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140020d9d  test    al, al
0x140020d9f  jnz     short loc_140020DCB
0x140020da1  mov     rcx, [rbp+8]; this
0x140020da5  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\too"...
0x140020dac  mov     ebx, 8007000Eh
0x140020db1  mov     edx, 103h; void *
0x140020db6  mov     r9d, ebx; char *
0x140020db9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020dbe  mov     rcx, [rbp+var_20]
0x140020dc2  lea     rdx, [rbp+var_10]
0x140020dc6  cmp     rcx, rdx
0x140020dc9  jmp     short loc_140020D69
0x140020dcb  mov     rcx, [rbp+var_20]; void *
0x140020dcf  lea     rax, [rbp+var_10]
0x140020dd3  cmp     rcx, rax
0x140020dd6  jz      short loc_140020DE4
0x140020dd8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140020ddf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140020de4  xor     eax, eax
0x140020de6  mov     rbx, [rsp+50h+arg_0]
0x140020deb  mov     rdi, [rsp+50h+arg_8]
0x140020df0  add     rsp, 50h
0x140020df4  pop     rbp
0x140020df5  retn
```
