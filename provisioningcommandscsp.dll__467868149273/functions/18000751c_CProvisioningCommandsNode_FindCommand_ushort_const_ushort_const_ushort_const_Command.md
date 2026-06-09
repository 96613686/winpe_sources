# CProvisioningCommandsNode::FindCommand(ushort const *,ushort const *,ushort const *,Command *)

- ea: `0x18000751c`
- end: `0x1800076a3`
- name: `?FindCommand@CProvisioningCommandsNode@@CAJPEBG00PEAUCommand@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, wchar_t *String1, struct Command *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006e40`
- `0x180008dd0`

## callees

- `0x180002cb0`
- `0x18000751c`
- `0x1800076ac`
- `0x1800079e0`
- `0x180007e9c`
- `0x18000a418`
- `0x18000a50c`
- `0x18000aa28`
- `0x18000aab0`
- `0x18000ccc0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000759a`
- `msvcrt!_wcsicmp` at `0x18000759a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProvisioningCommandsNode::FindCommand(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        wchar_t *String1,
        struct Command *a4)
{
  __int64 *v8; // rdi
  __int64 *i; // rbx
  struct Command *v10; // rsi
  const wchar_t *v11; // rdx
  const char *v12; // r9
  __int64 result; // rax
  const char *v14; // r9
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // r8
  int v18; // [rsp+20h] [rbp-98h]
  _BYTE v19[8]; // [rsp+28h] [rbp-90h] BYREF
  __int64 *v20; // [rsp+30h] [rbp-88h]
  _BYTE v21[40]; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  try
  {
    RegistryConfig::RegistryConfig((RegistryConfig *)v21);
    CommandSet::CommandSet((CommandSet *)v19);
    if ( CProvisioningCommandsNode::FindCommandSet(a1, a2, (struct CommandSet *)v19) < 0 )
    {
      v14 = (const char *)(unsigned int)wil::verify_hresult<long>(2248146946LL);
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x11F, v15, v14, v18);
    }
    v8 = v20;
    for ( i = (__int64 *)*v20; ; i = (__int64 *)*i )
    {
      v10 = (struct Command *)(i + 2);
      if ( i == v8 )
        break;
      v11 = (unsigned __int64)i[5] < 8 ? (const wchar_t *)(i + 2) : *(const wchar_t **)v10;
      if ( !_wcsicmp(String1, v11) )
        break;
    }
    if ( i == v20 )
    {
      v16 = wil::verify_hresult<long>(2248146946LL);
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x12B, v17, (const char *)v16, v18);
    }
    if ( a4 )
    {
      if ( a4 != v10 )
        std::wstring::assign(a4);
      if ( (__int64 *)((char *)a4 + 32) != i + 6 )
        std::wstring::assign((char *)a4 + 32);
      if ( (__int64 *)((char *)a4 + 64) != i + 10 )
        std::wstring::assign((char *)a4 + 64);
      *((_DWORD *)a4 + 24) = *((_DWORD *)i + 28);
      *((_DWORD *)a4 + 25) = *((_DWORD *)i + 29);
      *((_DWORD *)a4 + 26) = *((_DWORD *)i + 30);
      *((_DWORD *)a4 + 27) = *((_DWORD *)i + 31);
    }
    CommandSet::~CommandSet((CommandSet *)v19);
    RegistryConfig::~RegistryConfig((RegistryConfig *)v21);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x132,
                           (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18000751c  push    rbx
0x18000751e  push    rsi
0x18000751f  push    rdi
0x180007520  push    r14
0x180007522  push    r15
0x180007524  sub     rsp, 90h
0x18000752b  mov     rax, cs:__security_cookie
0x180007532  xor     rax, rsp
0x180007535  mov     [rsp+0B8h+var_30], rax
0x18000753d  mov     r14, r9
0x180007540  mov     r15, r8
0x180007543  mov     rdi, rdx
0x180007546  mov     rbx, rcx
0x180007549  lea     rcx, [rsp+0B8h+var_58]; this
0x18000754e  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x180007553  nop
0x180007554  lea     rcx, [rsp+0B8h+var_90]; this
0x180007559  call    ??0CommandSet@@QEAA@XZ; CommandSet::CommandSet(void)
0x18000755e  nop
0x18000755f  lea     r8, [rsp+0B8h+var_90]; struct CommandSet *
0x180007564  mov     rdx, rdi; unsigned __int16 *
0x180007567  mov     rcx, rbx; unsigned __int16 *
0x18000756a  call    ?FindCommandSet@CProvisioningCommandsNode@@CAJPEBG0PEAUCommandSet@@@Z; CProvisioningCommandsNode::FindCommandSet(ushort const *,ushort const *,CommandSet *)
0x18000756f  test    eax, eax
0x180007571  js      loc_180007663
0x180007577  mov     rdi, [rsp+0B8h+var_88]
0x18000757c  mov     rbx, [rdi]
0x18000757f  lea     rsi, [rbx+10h]
0x180007583  cmp     rbx, rdi
0x180007586  jz      short loc_1800075AF
0x180007588  cmp     qword ptr [rbx+28h], 8
0x18000758d  jb      short loc_180007594
0x18000758f  mov     rdx, [rsi]
0x180007592  jmp     short loc_180007597
0x180007594  mov     rdx, rsi; String2
0x180007597  mov     rcx, r15; String1
0x18000759a  call    cs:__imp__wcsicmp
0x1800075a1  nop     dword ptr [rax+rax+00h]
0x1800075a6  test    eax, eax
0x1800075a8  jz      short loc_1800075AF
0x1800075aa  mov     rbx, [rbx]
0x1800075ad  jmp     short loc_18000757F
0x1800075af  cmp     rbx, [rsp+0B8h+var_88]
0x1800075b4  jz      loc_180007682
0x1800075ba  test    r14, r14
0x1800075bd  jz      short loc_180007625
0x1800075bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800075c3  cmp     r14, rsi
0x1800075c6  jz      short loc_1800075D9
0x1800075c8  mov     r9, rbx
0x1800075cb  xor     r8d, r8d
0x1800075ce  mov     rdx, rsi
0x1800075d1  mov     rcx, r14; void *
0x1800075d4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800075d9  lea     rdx, [rsi+20h]
0x1800075dd  lea     rcx, [r14+20h]; void *
0x1800075e1  cmp     rcx, rdx
0x1800075e4  jz      short loc_1800075F1
0x1800075e6  mov     r9, rbx
0x1800075e9  xor     r8d, r8d
0x1800075ec  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800075f1  lea     rdx, [rsi+40h]
0x1800075f5  lea     rcx, [r14+40h]; void *
0x1800075f9  cmp     rcx, rdx
0x1800075fc  jz      short loc_180007609
0x1800075fe  mov     r9, rbx
0x180007601  xor     r8d, r8d
0x180007604  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180007609  mov     eax, [rsi+60h]
0x18000760c  mov     [r14+60h], eax
0x180007610  mov     eax, [rsi+64h]
0x180007613  mov     [r14+64h], eax
0x180007617  mov     eax, [rsi+68h]
0x18000761a  mov     [r14+68h], eax
0x18000761e  mov     eax, [rsi+6Ch]
0x180007621  mov     [r14+6Ch], eax
0x180007625  lea     rcx, [rsp+0B8h+var_90]; this
0x18000762a  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x18000762f  nop
0x180007630  lea     rcx, [rsp+0B8h+var_58]; this
0x180007635  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x18000763a  nop
0x18000763b  xor     eax, eax
0x18000763d  jmp     short loc_180007643
0x18000763f  mov     eax, [rsp+0B8h+var_98]
0x180007643  mov     rcx, [rsp+0B8h+var_30]
0x18000764b  xor     rcx, rsp; StackCookie
0x18000764e  call    __security_check_cookie
0x180007653  add     rsp, 90h
0x18000765a  pop     r15
0x18000765c  pop     r14
0x18000765e  pop     rdi
0x18000765f  pop     rsi
0x180007660  pop     rbx
0x180007661  retn
0x180007663  mov     ecx, 86000002h
0x180007668  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000766d  mov     r9d, eax; char *
0x180007670  mov     rcx, [rsp+0B8h]; this
0x180007678  mov     edx, 11Fh; void *
0x18000767d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007682  mov     ecx, 86000002h
0x180007687  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000768c  mov     r9d, eax; char *
0x18000768f  mov     rcx, [rsp+0B8h]; this
0x180007697  mov     edx, 12Bh; void *
0x18000769c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
