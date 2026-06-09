# PublicNlm::EnumerateNetworks(NLM_ENUM_NETWORK)

- ea: `0x18000f588`
- end: `0x18000f6f7`
- name: `?EnumerateNetworks@PublicNlm@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4NLM_ENUM_NETWORK@@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000d654`
- `0x18000f588`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x1800120d0`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x18000f5f9`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18000f6e5`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PublicNlm::EnumerateNetworks(_QWORD *a1, __int64 a2)
{
  int v4; // eax
  int v5; // edi
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v11; // [rsp+20h] [rbp-60h]
  _BYTE v12[32]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v13; // [rsp+60h] [rbp-20h] BYREF
  __int64 v14; // [rsp+68h] [rbp-18h] BYREF
  int v15; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  std::wstring::wstring(a2);
  v14 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(*(_QWORD *)*a1 + 56LL))(*a1, 1, &v14);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v4,
      v11);
  v5 = 0;
  do
  {
    v15 = 0;
    v13 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v14 + 64LL))(v14, 1, &v13, &v15);
    v7 = v6;
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
        (const char *)(unsigned int)v6,
        v11);
    if ( !v6 )
    {
      PublicNlm::Log((__int64)a1, (__int64)v12, v13, ++v5);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v12);
    }
    v8 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  while ( !v7 );
  v9 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return a2;
}

```

## disassembly

```asm
0x18000f588  mov     [rsp-18h+arg_10], rbx
0x18000f58d  mov     [rsp-18h+arg_18], rsi
0x18000f592  push    rbp
0x18000f593  push    rdi
0x18000f594  push    r14
0x18000f596  mov     rbp, rsp
0x18000f599  sub     rsp, 80h
0x18000f5a0  mov     rax, cs:__security_cookie
0x18000f5a7  xor     rax, rsp
0x18000f5aa  mov     [rbp+var_8], rax
0x18000f5ae  mov     rsi, rdx
0x18000f5b1  mov     r14, rcx
0x18000f5b4  mov     [rbp+var_48], rdx
0x18000f5b8  mov     [rbp+var_50], 0
0x18000f5bf  mov     rcx, rdx
0x18000f5c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f5c7  mov     [rbp+var_50], 1
0x18000f5ce  mov     [rbp+var_18], 0
0x18000f5d6  mov     rcx, [r14]
0x18000f5d9  mov     rax, [rcx]
0x18000f5dc  lea     r8, [rbp+var_18]
0x18000f5e0  mov     edx, 1
0x18000f5e5  mov     rax, [rax+38h]
0x18000f5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5ee  mov     rcx, [rbp+18h]; this
0x18000f5f2  test    eax, eax
0x18000f5f4  jns     short loc_18000F60B
0x18000f5f6  mov     r9d, eax; char *
0x18000f5f9  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f600  mov     edx, 10Ch; void *
0x18000f605  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f60b  xor     edi, edi
0x18000f60d  mov     [rbp+var_10], 0
0x18000f614  mov     [rbp+var_20], 0
0x18000f61c  mov     rcx, [rbp+var_18]
0x18000f620  mov     rax, [rcx]
0x18000f623  lea     r9, [rbp+var_10]
0x18000f627  lea     r8, [rbp+var_20]
0x18000f62b  mov     edx, 1
0x18000f630  mov     rax, [rax+40h]
0x18000f634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f639  mov     ebx, eax
0x18000f63b  mov     rcx, [rbp+18h]; this
0x18000f63f  test    eax, eax
0x18000f641  js      loc_18000F6E2
0x18000f647  test    eax, eax
0x18000f649  jnz     short loc_18000F677
0x18000f64b  inc     edi
0x18000f64d  mov     r9d, edi
0x18000f650  mov     r8, [rbp+var_20]
0x18000f654  lea     rdx, [rbp+var_40]
0x18000f658  mov     rcx, r14
0x18000f65b  call    ?Log@PublicNlm@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetwork@@K@Z; PublicNlm::Log(INetwork *,ulong)
0x18000f660  nop
0x18000f661  mov     rdx, rax
0x18000f664  mov     rcx, rsi
0x18000f667  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000f66c  nop
0x18000f66d  lea     rcx, [rbp+var_40]
0x18000f671  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f676  nop
0x18000f677  mov     rcx, [rbp+var_20]
0x18000f67b  test    rcx, rcx
0x18000f67e  jz      short loc_18000F695
0x18000f680  mov     [rbp+var_20], 0
0x18000f688  mov     rax, [rcx]
0x18000f68b  mov     rax, [rax+10h]
0x18000f68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f694  nop
0x18000f695  test    ebx, ebx
0x18000f697  jz      loc_18000F60D
0x18000f69d  mov     rcx, [rbp+var_18]
0x18000f6a1  test    rcx, rcx
0x18000f6a4  jz      short loc_18000F6BB
0x18000f6a6  mov     [rbp+var_18], 0
0x18000f6ae  mov     rdx, [rcx]
0x18000f6b1  mov     rax, [rdx+10h]
0x18000f6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6ba  nop
0x18000f6bb  mov     rax, rsi
0x18000f6be  mov     rcx, [rbp+var_8]
0x18000f6c2  xor     rcx, rsp; StackCookie
0x18000f6c5  call    __security_check_cookie
0x18000f6ca  lea     r11, [rsp+80h+var_s0]
0x18000f6d2  mov     rbx, [r11+30h]
0x18000f6d6  mov     rsi, [r11+38h]
0x18000f6da  mov     rsp, r11
0x18000f6dd  pop     r14
0x18000f6df  pop     rdi
0x18000f6e0  pop     rbp
0x18000f6e1  retn
0x18000f6e2  mov     r9d, ebx; char *
0x18000f6e5  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f6ec  mov     edx, 114h; void *
0x18000f6f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
