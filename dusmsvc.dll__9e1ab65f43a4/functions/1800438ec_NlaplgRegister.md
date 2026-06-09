# NlaplgRegister

- ea: `0x1800438ec`
- end: `0x1800439f0`
- name: `NlaplgRegister`
- size: `260`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180042034`
- `0x1800422d4`

## callees

- `0x180007c90`
- `0x18000809c`
- `0x180008704`
- `0x18000d6ec`
- `0x1800172c8`
- `0x180042f3c`
- `0x180043214`
- `0x1800438ec`
- `0x180043f48`

## string_xrefs

- `0x180043982`: `onecore\net\netprofiles\service\src\l2manager\clientlib\pluginclient.cpp`
- `0x1800439bd`: `onecore\net\netprofiles\service\src\l2manager\clientlib\pluginclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall NlaplgRegister(__int64 a1, _QWORD *a2)
{
  int v3; // esi
  _QWORD *v4; // rdi
  ULONG v5; // eax
  unsigned int v7[2]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = a1;
  if ( !a1 || !a2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\pluginclient.cpp",
      (const char *)0x57,
      v7[0]);
  }
  *a2 = 0;
  v4 = operator new(0x50u);
  memset_0(v4, 0, 0x50u);
  std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(v4);
  std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(v4 + 3);
  std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(v4 + 6);
  v4[9] = 0;
  *(_QWORD *)v7 = v4;
  v5 = RpcRegisterPlugin(v3);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\pluginclient.cpp",
      (const char *)v5,
      v7[0]);
  *(_QWORD *)v7 = 0;
  *a2 = v4;
  std::unique_ptr<ClientData>::~unique_ptr<ClientData>(v7);
  return 0;
}

```

## disassembly

```asm
0x1800438ec  mov     [rsp+arg_10], rbx
0x1800438f1  mov     [rsp+arg_18], rsi
0x1800438f6  push    rdi
0x1800438f7  sub     rsp, 30h
0x1800438fb  mov     rax, cs:__security_cookie
0x180043902  xor     rax, rsp
0x180043905  mov     [rsp+38h+var_10], rax
0x18004390a  mov     rbx, rdx
0x18004390d  mov     rsi, rcx
0x180043910  test    rcx, rcx
0x180043913  jz      loc_1800439AD
0x180043919  test    rdx, rdx
0x18004391c  jz      loc_1800439AD
0x180043922  mov     qword ptr [rdx], 0
0x180043929  mov     ecx, 50h ; 'P'; Size
0x18004392e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043933  mov     rdi, rax
0x180043936  xor     edx, edx; Val
0x180043938  lea     r8d, [rdx+50h]; Size
0x18004393c  mov     rcx, rax; void *
0x18004393f  call    memset_0
0x180043944  mov     rcx, rdi
0x180043947  call    ??0?$vector@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@V?$allocator@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(void)
0x18004394c  lea     rcx, [rdi+18h]
0x180043950  call    ??0?$vector@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@V?$allocator@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(void)
0x180043955  lea     rcx, [rdi+30h]
0x180043959  call    ??0?$vector@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@V?$allocator@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(void)
0x18004395e  lea     rdx, [rdi+48h]
0x180043962  mov     qword ptr [rdx], 0
0x180043969  mov     qword ptr [rsp+38h+var_18], rdi; unsigned int
0x18004396e  mov     rcx, rsi; int
0x180043971  call    RpcRegisterPlugin
0x180043976  mov     rcx, [rsp+38h]; this
0x18004397b  test    eax, eax
0x18004397d  jz      short loc_180043993
0x18004397f  mov     r9d, eax; char *
0x180043982  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x180043989  mov     edx, 37h ; '7'; void *
0x18004398e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180043993  mov     qword ptr [rsp+38h+var_18], 0
0x18004399c  mov     [rbx], rdi
0x18004399f  lea     rcx, [rsp+38h+var_18]
0x1800439a4  call    ??1?$unique_ptr@UClientData@@U?$default_delete@UClientData@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClientData>::~unique_ptr<ClientData>(void)
0x1800439a9  xor     eax, eax
0x1800439ab  jmp     short loc_1800439D2
0x1800439ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800439b2  mov     rcx, [rsp+38h]; this
0x1800439b7  mov     r9d, 57h ; 'W'; char *
0x1800439bd  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x1800439c4  lea     edx, [r9-28h]; void *
0x1800439c8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800439ce  mov     eax, [rsp+38h+var_18]
0x1800439d2  mov     rcx, [rsp+38h+var_10]
0x1800439d7  xor     rcx, rsp; StackCookie
0x1800439da  call    __security_check_cookie
0x1800439df  mov     rbx, [rsp+38h+arg_10]
0x1800439e4  mov     rsi, [rsp+38h+arg_18]
0x1800439e9  add     rsp, 30h
0x1800439ed  pop     rdi
0x1800439ee  retn
```
