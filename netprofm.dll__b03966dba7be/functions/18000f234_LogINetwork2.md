# LogINetwork2

- ea: `0x18000f234`
- end: `0x18000f37f`
- name: `LogINetwork2`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000d654`

## callees

- `0x18000f234`
- `0x18000f388`
- `0x1800120d0`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x18000f283`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18000f2c5`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18000f307`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
__int64 __fastcall LogINetwork2(__int64 a1, __int64 *a2, unsigned int a3)
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
  v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v4 + 160))(a2, 0, &v16);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v7,
      v13);
  v8 = *a2;
  v15 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(v8 + 160))(a2, 1, &v15);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v9,
      v13);
  v10 = *a2;
  v14 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(v10 + 160))(a2, 2, &v14);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v11,
      v13);
  wil::str_printf<std::wstring>(
    a1,
    (__int64)L"\n"
              " >>>>>> INetwork2 [%u] <<<<<< \n"
              "    IsDomainAuthenticatedBy(None): %ws\n"
              "    IsDomainAuthenticatedBy(Ldap): %ws\n"
              "    IsDomainAuthenticatedBy(Tls): %ws\n",
    a3);
  return a1;
}

```

## disassembly

```asm
0x18000f234  push    rbx
0x18000f236  push    rsi
0x18000f237  push    rdi
0x18000f238  sub     rsp, 50h
0x18000f23c  mov     rax, cs:__security_cookie
0x18000f243  xor     rax, rsp
0x18000f246  mov     [rsp+68h+var_20], rax
0x18000f24b  mov     [rsp+68h+var_28], rcx
0x18000f250  mov     rbx, rdx
0x18000f253  mov     rax, [rdx]
0x18000f256  mov     esi, r8d
0x18000f259  mov     rdi, rcx
0x18000f25c  mov     dword ptr [rsp+68h+var_28], 0
0x18000f264  lea     r8, [rsp+68h+var_28]
0x18000f269  xor     edx, edx
0x18000f26b  mov     rcx, rbx
0x18000f26e  mov     rax, [rax+0A0h]
0x18000f275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f27a  test    eax, eax
0x18000f27c  jns     short loc_18000F298
0x18000f27e  mov     rcx, [rsp+68h]; this
0x18000f283  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f28a  mov     r9d, eax; char *
0x18000f28d  mov     edx, 164h; void *
0x18000f292  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f298  mov     rax, [rbx]
0x18000f29b  lea     r8, [rsp+68h+var_30]
0x18000f2a0  mov     edx, 1
0x18000f2a5  mov     [rsp+68h+var_30], 0
0x18000f2ad  mov     rcx, rbx
0x18000f2b0  mov     rax, [rax+0A0h]
0x18000f2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2bc  test    eax, eax
0x18000f2be  jns     short loc_18000F2DA
0x18000f2c0  mov     rcx, [rsp+68h]; this
0x18000f2c5  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f2cc  mov     r9d, eax; char *
0x18000f2cf  mov     edx, 167h; void *
0x18000f2d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f2da  mov     rax, [rbx]
0x18000f2dd  lea     r8, [rsp+68h+var_34]
0x18000f2e2  mov     edx, 2
0x18000f2e7  mov     [rsp+68h+var_34], 0
0x18000f2ef  mov     rcx, rbx
0x18000f2f2  mov     rax, [rax+0A0h]
0x18000f2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2fe  test    eax, eax
0x18000f300  jns     short loc_18000F31C
0x18000f302  mov     rcx, [rsp+68h]; this
0x18000f307  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f30e  mov     r9d, eax; char *
0x18000f311  mov     edx, 16Ah; void *
0x18000f316  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f31c  cmp     [rsp+68h+var_34], 0
0x18000f321  lea     rax, aFalse_0; "false"
0x18000f328  lea     r9, aTrue_0; "true"
0x18000f32f  mov     r8d, esi
0x18000f332  mov     rdx, r9
0x18000f335  mov     rcx, r9
0x18000f338  cmovz   rdx, rax
0x18000f33c  cmp     [rsp+68h+var_30], 0
0x18000f341  mov     [rsp+68h+var_40], rdx
0x18000f346  lea     rdx, aInetwork2UIsdo; "\n >>>>>> INetwork2 [%u] <<<<<< \n    I"...
0x18000f34d  cmovz   rcx, rax
0x18000f351  cmp     dword ptr [rsp+68h+var_28], 0
0x18000f356  mov     [rsp+68h+var_48], rcx
0x18000f35b  mov     rcx, rdi
0x18000f35e  cmovz   r9, rax
0x18000f362  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18000f367  mov     rax, rdi
0x18000f36a  mov     rcx, [rsp+68h+var_20]
0x18000f36f  xor     rcx, rsp; StackCookie
0x18000f372  call    __security_check_cookie
0x18000f377  add     rsp, 50h
0x18000f37b  pop     rdi
0x18000f37c  pop     rsi
0x18000f37d  pop     rbx
0x18000f37e  retn
```
