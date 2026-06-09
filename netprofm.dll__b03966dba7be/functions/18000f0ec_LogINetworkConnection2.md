# LogINetworkConnection2

- ea: `0x18000f0ec`
- end: `0x18000f22e`
- name: `LogINetworkConnection2`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18003e780`

## callees

- `0x18000f0ec`
- `0x18000f388`
- `0x1800120d0`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x18000f138`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18000f177`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18000f1b6`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
__int64 __fastcall LogINetworkConnection2(__int64 a1, __int64 *a2, unsigned int a3)
{
  __int64 v4; // rax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  int v13; // [rsp+20h] [rbp-48h]
  int v14; // [rsp+34h] [rbp-34h] BYREF
  int v15; // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v16 = a1;
  v4 = *a2;
  LODWORD(v16) = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v4 + 112))(a2, 0, &v16);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v7,
      v13);
  v8 = *a2;
  v15 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(v8 + 112))(a2, 1, &v15);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v9,
      v13);
  v10 = *a2;
  v14 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(v10 + 112))(a2, 2, &v14);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v11,
      v13);
  wil::str_printf<std::wstring>(
    a1,
    (__int64)L"\n"
              " >>>>>> INetworkConnection2 [%u] <<<<<< \n"
              "    IsDomainAuthenticatedBy(None): %ws\n"
              "    IsDomainAuthenticatedBy(Ldap): %ws\n"
              "    IsDomainAuthenticatedBy(Tls): %ws\n",
    a3);
  return a1;
}

```

## disassembly

```asm
0x18000f0ec  push    rbx
0x18000f0ee  push    rsi
0x18000f0ef  push    rdi
0x18000f0f0  sub     rsp, 50h
0x18000f0f4  mov     rax, cs:__security_cookie
0x18000f0fb  xor     rax, rsp
0x18000f0fe  mov     [rsp+68h+var_20], rax
0x18000f103  mov     [rsp+68h+var_28], rcx
0x18000f108  mov     rbx, rdx
0x18000f10b  mov     rax, [rdx]
0x18000f10e  mov     esi, r8d
0x18000f111  mov     rdi, rcx
0x18000f114  mov     dword ptr [rsp+68h+var_28], 0
0x18000f11c  lea     r8, [rsp+68h+var_28]
0x18000f121  xor     edx, edx
0x18000f123  mov     rcx, rbx
0x18000f126  mov     rax, [rax+70h]
0x18000f12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f12f  test    eax, eax
0x18000f131  jns     short loc_18000F14D
0x18000f133  mov     rcx, [rsp+68h]; this
0x18000f138  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f13f  mov     r9d, eax; char *
0x18000f142  mov     edx, 122h; void *
0x18000f147  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f14d  mov     rax, [rbx]
0x18000f150  lea     r8, [rsp+68h+var_30]
0x18000f155  mov     edx, 1
0x18000f15a  mov     [rsp+68h+var_30], 0
0x18000f162  mov     rcx, rbx
0x18000f165  mov     rax, [rax+70h]
0x18000f169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f16e  test    eax, eax
0x18000f170  jns     short loc_18000F18C
0x18000f172  mov     rcx, [rsp+68h]; this
0x18000f177  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f17e  mov     r9d, eax; char *
0x18000f181  mov     edx, 125h; void *
0x18000f186  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f18c  mov     rax, [rbx]
0x18000f18f  lea     r8, [rsp+68h+var_34]
0x18000f194  mov     edx, 2
0x18000f199  mov     [rsp+68h+var_34], 0
0x18000f1a1  mov     rcx, rbx
0x18000f1a4  mov     rax, [rax+70h]
0x18000f1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1ad  test    eax, eax
0x18000f1af  jns     short loc_18000F1CB
0x18000f1b1  mov     rcx, [rsp+68h]; this
0x18000f1b6  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f1bd  mov     r9d, eax; char *
0x18000f1c0  mov     edx, 128h; void *
0x18000f1c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f1cb  cmp     [rsp+68h+var_34], 0
0x18000f1d0  lea     rax, aFalse_0; "false"
0x18000f1d7  lea     r9, aTrue_0; "true"
0x18000f1de  mov     r8d, esi
0x18000f1e1  mov     rdx, r9
0x18000f1e4  mov     rcx, r9
0x18000f1e7  cmovz   rdx, rax
0x18000f1eb  cmp     [rsp+68h+var_30], 0
0x18000f1f0  mov     [rsp+68h+var_40], rdx
0x18000f1f5  lea     rdx, aInetworkconnec_0; "\n >>>>>> INetworkConnection2 [%u] <<<<"...
0x18000f1fc  cmovz   rcx, rax
0x18000f200  cmp     dword ptr [rsp+68h+var_28], 0
0x18000f205  mov     [rsp+68h+var_48], rcx
0x18000f20a  mov     rcx, rdi
0x18000f20d  cmovz   r9, rax
0x18000f211  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18000f216  mov     rax, rdi
0x18000f219  mov     rcx, [rsp+68h+var_20]
0x18000f21e  xor     rcx, rsp; StackCookie
0x18000f221  call    __security_check_cookie
0x18000f226  add     rsp, 50h
0x18000f22a  pop     rdi
0x18000f22b  pop     rsi
0x18000f22c  pop     rbx
0x18000f22d  retn
```
