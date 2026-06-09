# PublicNlm::EnumerateAllConnections(void)

- ea: `0x18000f424`
- end: `0x18000f580`
- name: `?EnumerateAllConnections@PublicNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000f424`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x1800120d0`
- `0x18002a928`
- `0x18003e780`
- `0x180043010`

## string_xrefs

- `0x18000f48a`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18000f56e`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PublicNlm::EnumerateAllConnections(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rdx
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
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v3 + 72LL))(*v3, &v14);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF4,
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
        (void *)0xFC,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
        (const char *)(unsigned int)v6,
        v11);
    if ( !v6 )
    {
      PublicNlm::Log((__int64)retaddr, (__int64)v12, v13, ++v5);
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
0x18000f424  mov     [rsp-18h+arg_10], rbx
0x18000f429  push    rbp
0x18000f42a  push    rsi
0x18000f42b  push    rdi
0x18000f42c  mov     rbp, rsp
0x18000f42f  sub     rsp, 80h
0x18000f436  mov     rax, cs:__security_cookie
0x18000f43d  xor     rax, rsp
0x18000f440  mov     [rbp+var_8], rax
0x18000f444  mov     rsi, rdx
0x18000f447  mov     rdx, rcx
0x18000f44a  mov     [rbp+var_48], rsi
0x18000f44e  mov     [rbp+var_50], 0
0x18000f455  mov     rcx, rsi
0x18000f458  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f45d  mov     [rbp+var_50], 1
0x18000f464  mov     [rbp+var_18], 0
0x18000f46c  mov     rcx, [rdx]
0x18000f46f  mov     rax, [rcx]
0x18000f472  lea     rdx, [rbp+var_18]
0x18000f476  mov     rax, [rax+48h]
0x18000f47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f47f  mov     rcx, [rbp+18h]; this
0x18000f483  test    eax, eax
0x18000f485  jns     short loc_18000F49C
0x18000f487  mov     r9d, eax; char *
0x18000f48a  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f491  mov     edx, 0F4h; void *
0x18000f496  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f49c  xor     edi, edi
0x18000f49e  mov     [rbp+var_10], 0
0x18000f4a5  mov     [rbp+var_20], 0
0x18000f4ad  mov     rcx, [rbp+var_18]
0x18000f4b1  mov     rax, [rcx]
0x18000f4b4  lea     r9, [rbp+var_10]
0x18000f4b8  lea     r8, [rbp+var_20]
0x18000f4bc  mov     edx, 1
0x18000f4c1  mov     rax, [rax+40h]
0x18000f4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ca  mov     ebx, eax
0x18000f4cc  mov     rcx, [rbp+18h]; this
0x18000f4d0  test    eax, eax
0x18000f4d2  js      loc_18000F56B
0x18000f4d8  test    eax, eax
0x18000f4da  jnz     short loc_18000F505
0x18000f4dc  inc     edi
0x18000f4de  mov     r9d, edi
0x18000f4e1  mov     r8, [rbp+var_20]
0x18000f4e5  lea     rdx, [rbp+var_40]
0x18000f4e9  call    ?Log@PublicNlm@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkConnection@@K@Z; PublicNlm::Log(INetworkConnection *,ulong)
0x18000f4ee  nop
0x18000f4ef  mov     rdx, rax
0x18000f4f2  mov     rcx, rsi
0x18000f4f5  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000f4fa  nop
0x18000f4fb  lea     rcx, [rbp+var_40]
0x18000f4ff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f504  nop
0x18000f505  mov     rcx, [rbp+var_20]
0x18000f509  test    rcx, rcx
0x18000f50c  jz      short loc_18000F523
0x18000f50e  mov     [rbp+var_20], 0
0x18000f516  mov     rax, [rcx]
0x18000f519  mov     rax, [rax+10h]
0x18000f51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f522  nop
0x18000f523  test    ebx, ebx
0x18000f525  jz      loc_18000F49E
0x18000f52b  mov     rcx, [rbp+var_18]
0x18000f52f  test    rcx, rcx
0x18000f532  jz      short loc_18000F549
0x18000f534  mov     [rbp+var_18], 0
0x18000f53c  mov     rdx, [rcx]
0x18000f53f  mov     rax, [rdx+10h]
0x18000f543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f548  nop
0x18000f549  mov     rax, rsi
0x18000f54c  mov     rcx, [rbp+var_8]
0x18000f550  xor     rcx, rsp; StackCookie
0x18000f553  call    __security_check_cookie
0x18000f558  mov     rbx, [rsp+80h+arg_10]
0x18000f560  add     rsp, 80h
0x18000f567  pop     rdi
0x18000f568  pop     rsi
0x18000f569  pop     rbp
0x18000f56a  retn
0x18000f56b  mov     r9d, ebx; char *
0x18000f56e  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f575  mov     edx, 0FCh; void *
0x18000f57a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
