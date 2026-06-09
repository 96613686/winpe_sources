# CProvisioningCommandsNode::FindCommandSet(ushort const *,ushort const *,CommandSet *)

- ea: `0x1800076ac`
- end: `0x1800077c6`
- name: `?FindCommandSet@CProvisioningCommandsNode@@CAJPEBG0PEAUCommandSet@@@Z`
- size: `282`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, struct CommandSet *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006e40`
- `0x18000751c`
- `0x1800096c0`

## callees

- `0x180002cb0`
- `0x180006ab4`
- `0x180006d20`
- `0x1800076ac`
- `0x1800079e0`
- `0x180007e9c`
- `0x18000aa28`
- `0x18000aab0`
- `0x18000b81c`
- `0x18000ccc0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000770d`
- `msvcrt!_wcsicmp` at `0x18000770d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProvisioningCommandsNode::FindCommandSet(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct HKEY__ *a3)
{
  HKEY v6; // rdi
  const wchar_t *v7; // rdx
  HKEY i; // rbx
  const char *v9; // r9
  __int64 result; // rax
  const char *v11; // r9
  __int64 v12; // r8
  int v13; // [rsp+20h] [rbp-68h]
  HKEY v14[2]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v15[40]; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    RegistryConfig::RegistryConfig((RegistryConfig *)v15);
    RegistryConfig::Parse((__int64)v15, v14, a1);
    v6 = v14[0];
    for ( i = *(HKEY *)v14[0]; i != v6; i = *(HKEY *)i )
    {
      v7 = (const wchar_t *)(i + 10);
      if ( *((_QWORD *)i + 8) >= 8u )
        v7 = *(const wchar_t **)v7;
      if ( !_wcsicmp(a2, v7) )
        break;
    }
    if ( i == v14[0] )
    {
      v11 = (const char *)(unsigned int)wil::verify_hresult<long>(2248146946LL);
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x107, v12, v11, v13);
    }
    if ( a3 )
    {
      *(_DWORD *)a3 = i[4];
      if ( a3 + 2 != i + 6 )
        std::list<Command>::assign<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(
          a3 + 2,
          **((_QWORD **)i + 3),
          *((_QWORD *)i + 3));
      if ( a3 + 6 != i + 10 )
        std::wstring::assign(a3 + 6);
    }
    std::list<CommandSet>::~list<CommandSet>(v14);
    RegistryConfig::~RegistryConfig((RegistryConfig *)v15);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x10E,
                           (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800076ac  mov     [rsp+arg_8], rbx
0x1800076b1  push    rsi
0x1800076b2  push    rdi
0x1800076b3  push    r14
0x1800076b5  sub     rsp, 70h
0x1800076b9  mov     rax, cs:__security_cookie
0x1800076c0  xor     rax, rsp
0x1800076c3  mov     [rsp+88h+var_28], rax
0x1800076c8  mov     rsi, r8
0x1800076cb  mov     r14, rdx
0x1800076ce  mov     rbx, rcx
0x1800076d1  lea     rcx, [rsp+88h+var_50]; this
0x1800076d6  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x1800076db  nop
0x1800076dc  mov     r8, rbx
0x1800076df  lea     rdx, [rsp+88h+var_60]
0x1800076e4  lea     rcx, [rsp+88h+var_50]
0x1800076e9  call    ?Parse@RegistryConfig@@QEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEBG@Z; RegistryConfig::Parse(ushort const *)
0x1800076ee  nop
0x1800076ef  mov     rdi, [rsp+88h+var_60]
0x1800076f4  mov     rbx, [rdi]
0x1800076f7  cmp     rbx, rdi
0x1800076fa  jz      short loc_180007722
0x1800076fc  lea     rdx, [rbx+28h]
0x180007700  cmp     qword ptr [rbx+40h], 8
0x180007705  jb      short loc_18000770A
0x180007707  mov     rdx, [rdx]; String2
0x18000770a  mov     rcx, r14; String1
0x18000770d  call    cs:__imp__wcsicmp
0x180007714  nop     dword ptr [rax+rax+00h]
0x180007719  test    eax, eax
0x18000771b  jz      short loc_180007722
0x18000771d  mov     rbx, [rbx]
0x180007720  jmp     short loc_1800076F7
0x180007722  cmp     rbx, [rsp+88h+var_60]
0x180007727  jz      short loc_1800077A5
0x180007729  test    rsi, rsi
0x18000772c  jz      short loc_180007768
0x18000772e  mov     eax, [rbx+10h]
0x180007731  mov     [rsi], eax
0x180007733  lea     rdx, [rbx+18h]
0x180007737  lea     rcx, [rsi+8]
0x18000773b  cmp     rcx, rdx
0x18000773e  jz      short loc_18000774E
0x180007740  mov     rdx, [rdx]
0x180007743  mov     r8, rdx
0x180007746  mov     rdx, [rdx]
0x180007749  call    ??$assign@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@1@0@Z; std::list<Command>::assign<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>)
0x18000774e  lea     rdx, [rbx+28h]
0x180007752  lea     rcx, [rsi+18h]; void *
0x180007756  cmp     rcx, rdx
0x180007759  jz      short loc_180007768
0x18000775b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000775f  xor     r8d, r8d
0x180007762  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180007767  nop
0x180007768  lea     rcx, [rsp+88h+var_60]; void *
0x18000776d  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x180007772  nop
0x180007773  lea     rcx, [rsp+88h+var_50]; this
0x180007778  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x18000777d  nop
0x18000777e  xor     eax, eax
0x180007780  jmp     short loc_180007786
0x180007782  mov     eax, [rsp+88h+var_68]
0x180007786  mov     rcx, [rsp+88h+var_28]
0x18000778b  xor     rcx, rsp; StackCookie
0x18000778e  call    __security_check_cookie
0x180007793  mov     rbx, [rsp+88h+arg_8]
0x18000779b  add     rsp, 70h
0x18000779f  pop     r14
0x1800077a1  pop     rdi
0x1800077a2  pop     rsi
0x1800077a3  retn
0x1800077a5  mov     ecx, 86000002h
0x1800077aa  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800077af  mov     r9d, eax; char *
0x1800077b2  mov     rcx, [rsp+88h]; this
0x1800077ba  mov     edx, 107h; void *
0x1800077bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
