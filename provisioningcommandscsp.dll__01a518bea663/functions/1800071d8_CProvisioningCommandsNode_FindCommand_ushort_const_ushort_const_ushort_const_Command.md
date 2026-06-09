# CProvisioningCommandsNode::FindCommand(ushort const *,ushort const *,ushort const *,Command *)

- ea: `0x1800071d8`
- end: `0x180007358`
- name: `?FindCommand@CProvisioningCommandsNode@@CAJPEBG00PEAUCommand@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, wchar_t *String1, struct Command *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006b10`
- `0x1800089c0`

## callees

- `0x180002c68`
- `0x1800071d8`
- `0x180007360`
- `0x180007670`
- `0x180007b08`
- `0x180009f34`
- `0x18000a010`
- `0x18000a4d4`
- `0x18000a550`
- `0x18000c600`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007256`
- `msvcrt!_wcsicmp` at `0x180007256`

## pseudocode

```c
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
  unsigned int v15; // r8d
  unsigned int v16; // eax
  unsigned int v17; // r8d
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
0x1800071d8  push    rbx
0x1800071da  push    rsi
0x1800071db  push    rdi
0x1800071dc  push    r14
0x1800071de  push    r15
0x1800071e0  sub     rsp, 90h
0x1800071e7  mov     rax, cs:__security_cookie
0x1800071ee  xor     rax, rsp
0x1800071f1  mov     [rsp+0B8h+var_30], rax
0x1800071f9  mov     r14, r9
0x1800071fc  mov     r15, r8
0x1800071ff  mov     rdi, rdx
0x180007202  mov     rbx, rcx
0x180007205  lea     rcx, [rsp+0B8h+var_58]; this
0x18000720a  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x18000720f  nop
0x180007210  lea     rcx, [rsp+0B8h+var_90]; this
0x180007215  call    ??0CommandSet@@QEAA@XZ; CommandSet::CommandSet(void)
0x18000721a  nop
0x18000721b  lea     r8, [rsp+0B8h+var_90]; struct CommandSet *
0x180007220  mov     rdx, rdi; unsigned __int16 *
0x180007223  mov     rcx, rbx; unsigned __int16 *
0x180007226  call    ?FindCommandSet@CProvisioningCommandsNode@@CAJPEBG0PEAUCommandSet@@@Z; CProvisioningCommandsNode::FindCommandSet(ushort const *,ushort const *,CommandSet *)
0x18000722b  test    eax, eax
0x18000722d  js      loc_180007318
0x180007233  mov     rdi, [rsp+0B8h+var_88]
0x180007238  mov     rbx, [rdi]
0x18000723b  lea     rsi, [rbx+10h]
0x18000723f  cmp     rbx, rdi
0x180007242  jz      short loc_180007265
0x180007244  cmp     qword ptr [rbx+28h], 8
0x180007249  jb      short loc_180007250
0x18000724b  mov     rdx, [rsi]
0x18000724e  jmp     short loc_180007253
0x180007250  mov     rdx, rsi; String2
0x180007253  mov     rcx, r15; String1
0x180007256  call    cs:__imp__wcsicmp
0x18000725c  test    eax, eax
0x18000725e  jz      short loc_180007265
0x180007260  mov     rbx, [rbx]
0x180007263  jmp     short loc_18000723B
0x180007265  cmp     rbx, [rsp+0B8h+var_88]
0x18000726a  jz      loc_180007337
0x180007270  test    r14, r14
0x180007273  jz      short loc_1800072DB
0x180007275  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007279  cmp     r14, rsi
0x18000727c  jz      short loc_18000728F
0x18000727e  mov     r9, rbx
0x180007281  xor     r8d, r8d
0x180007284  mov     rdx, rsi
0x180007287  mov     rcx, r14; void *
0x18000728a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000728f  lea     rdx, [rsi+20h]
0x180007293  lea     rcx, [r14+20h]; void *
0x180007297  cmp     rcx, rdx
0x18000729a  jz      short loc_1800072A7
0x18000729c  mov     r9, rbx
0x18000729f  xor     r8d, r8d
0x1800072a2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800072a7  lea     rdx, [rsi+40h]
0x1800072ab  lea     rcx, [r14+40h]; void *
0x1800072af  cmp     rcx, rdx
0x1800072b2  jz      short loc_1800072BF
0x1800072b4  mov     r9, rbx
0x1800072b7  xor     r8d, r8d
0x1800072ba  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800072bf  mov     eax, [rsi+60h]
0x1800072c2  mov     [r14+60h], eax
0x1800072c6  mov     eax, [rsi+64h]
0x1800072c9  mov     [r14+64h], eax
0x1800072cd  mov     eax, [rsi+68h]
0x1800072d0  mov     [r14+68h], eax
0x1800072d4  mov     eax, [rsi+6Ch]
0x1800072d7  mov     [r14+6Ch], eax
0x1800072db  lea     rcx, [rsp+0B8h+var_90]; this
0x1800072e0  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x1800072e5  nop
0x1800072e6  lea     rcx, [rsp+0B8h+var_58]; this
0x1800072eb  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800072f0  nop
0x1800072f1  xor     eax, eax
0x1800072f3  jmp     short loc_1800072F9
0x1800072f5  mov     eax, [rsp+0B8h+var_98]
0x1800072f9  mov     rcx, [rsp+0B8h+var_30]
0x180007301  xor     rcx, rsp; StackCookie
0x180007304  call    __security_check_cookie
0x180007309  add     rsp, 90h
0x180007310  pop     r15
0x180007312  pop     r14
0x180007314  pop     rdi
0x180007315  pop     rsi
0x180007316  pop     rbx
0x180007317  retn
0x180007318  mov     ecx, 86000002h
0x18000731d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180007322  mov     r9d, eax; char *
0x180007325  mov     rcx, [rsp+0B8h]; this
0x18000732d  mov     edx, 11Fh; void *
0x180007332  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007337  mov     ecx, 86000002h
0x18000733c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180007341  mov     r9d, eax; char *
0x180007344  mov     rcx, [rsp+0B8h]; this
0x18000734c  mov     edx, 12Bh; void *
0x180007351  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
