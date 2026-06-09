# CProvisioningCommandsNode::FindCommandSet(ushort const *,ushort const *,CommandSet *)

- ea: `0x180007360`
- end: `0x180007473`
- name: `?FindCommandSet@CProvisioningCommandsNode@@CAJPEBG0PEAUCommandSet@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct HKEY__ *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006b10`
- `0x1800071d8`
- `0x180009290`

## callees

- `0x180002c68`
- `0x1800067a0`
- `0x180006a00`
- `0x180007360`
- `0x180007670`
- `0x180007b08`
- `0x18000a4d4`
- `0x18000a550`
- `0x18000b1c8`
- `0x18000c600`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800073c1`
- `msvcrt!_wcsicmp` at `0x1800073c1`

## pseudocode

```c
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
  unsigned int v12; // r8d
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
0x180007360  mov     [rsp+arg_8], rbx
0x180007365  push    rsi
0x180007366  push    rdi
0x180007367  push    r14
0x180007369  sub     rsp, 70h
0x18000736d  mov     rax, cs:__security_cookie
0x180007374  xor     rax, rsp
0x180007377  mov     [rsp+88h+var_28], rax
0x18000737c  mov     rsi, r8
0x18000737f  mov     r14, rdx
0x180007382  mov     rbx, rcx
0x180007385  lea     rcx, [rsp+88h+var_50]; this
0x18000738a  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x18000738f  nop
0x180007390  mov     r8, rbx
0x180007393  lea     rdx, [rsp+88h+var_60]
0x180007398  lea     rcx, [rsp+88h+var_50]
0x18000739d  call    ?Parse@RegistryConfig@@QEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEBG@Z; RegistryConfig::Parse(ushort const *)
0x1800073a2  nop
0x1800073a3  mov     rdi, [rsp+88h+var_60]
0x1800073a8  mov     rbx, [rdi]
0x1800073ab  cmp     rbx, rdi
0x1800073ae  jz      short loc_1800073D0
0x1800073b0  lea     rdx, [rbx+28h]
0x1800073b4  cmp     qword ptr [rbx+40h], 8
0x1800073b9  jb      short loc_1800073BE
0x1800073bb  mov     rdx, [rdx]; String2
0x1800073be  mov     rcx, r14; String1
0x1800073c1  call    cs:__imp__wcsicmp
0x1800073c7  test    eax, eax
0x1800073c9  jz      short loc_1800073D0
0x1800073cb  mov     rbx, [rbx]
0x1800073ce  jmp     short loc_1800073AB
0x1800073d0  cmp     rbx, [rsp+88h+var_60]
0x1800073d5  jz      short loc_180007452
0x1800073d7  test    rsi, rsi
0x1800073da  jz      short loc_180007416
0x1800073dc  mov     eax, [rbx+10h]
0x1800073df  mov     [rsi], eax
0x1800073e1  lea     rdx, [rbx+18h]
0x1800073e5  lea     rcx, [rsi+8]
0x1800073e9  cmp     rcx, rdx
0x1800073ec  jz      short loc_1800073FC
0x1800073ee  mov     rdx, [rdx]
0x1800073f1  mov     r8, rdx
0x1800073f4  mov     rdx, [rdx]
0x1800073f7  call    ??$assign@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@1@0@Z; std::list<Command>::assign<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>)
0x1800073fc  lea     rdx, [rbx+28h]
0x180007400  lea     rcx, [rsi+18h]; void *
0x180007404  cmp     rcx, rdx
0x180007407  jz      short loc_180007416
0x180007409  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000740d  xor     r8d, r8d
0x180007410  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180007415  nop
0x180007416  lea     rcx, [rsp+88h+var_60]; void *
0x18000741b  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x180007420  nop
0x180007421  lea     rcx, [rsp+88h+var_50]; this
0x180007426  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x18000742b  nop
0x18000742c  xor     eax, eax
0x18000742e  jmp     short loc_180007434
0x180007430  mov     eax, [rsp+88h+var_68]
0x180007434  mov     rcx, [rsp+88h+var_28]
0x180007439  xor     rcx, rsp; StackCookie
0x18000743c  call    __security_check_cookie
0x180007441  mov     rbx, [rsp+88h+arg_8]
0x180007449  add     rsp, 70h
0x18000744d  pop     r14
0x18000744f  pop     rdi
0x180007450  pop     rsi
0x180007451  retn
0x180007452  mov     ecx, 86000002h
0x180007457  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000745c  mov     r9d, eax; char *
0x18000745f  mov     rcx, [rsp+88h]; this
0x180007467  mov     edx, 107h; void *
0x18000746c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
