# PublicNlm::EnumNetworkConnectionCost(void)

- ea: `0x18000ef20`
- end: `0x18000f0e5`
- name: `?EnumNetworkConnectionCost@PublicNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f888`

## callees

- `0x18000e310`
- `0x18000ef20`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x180010164`
- `0x1800120d0`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x18000ef8c`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18000f0be`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18000f0d3`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PublicNlm::EnumNetworkConnectionCost(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rdx
  int v4; // eax
  int v5; // r15d
  int v6; // eax
  int v7; // esi
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-39h]
  _BYTE v15[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v16; // [rsp+60h] [rbp+7h] BYREF
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+70h] [rbp+17h] BYREF
  int v19; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  std::wstring::wstring(a2);
  v18 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v3 + 72LL))(*v3, &v18);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v4,
      v14);
  v5 = 0;
  do
  {
    v19 = 0;
    v17 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v18 + 64LL))(
           v18,
           1,
           &v17,
           &v19);
    v7 = v6;
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
        (const char *)(unsigned int)v6,
        v14);
    if ( !v6 )
    {
      v16 = 0;
      v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
      v9 = **v17;
      Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(&v16);
      v10 = v9(v8, &GUID_dcb0000a_570f_4a9b_8d69_199fdba5723b, &v16);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE7,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
          (const char *)(unsigned int)v10,
          v14);
      PublicNlm::Log(retaddr, v15, v16, (unsigned int)++v5);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v15);
      Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(&v16);
    }
    v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
    if ( v17 )
    {
      v17 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v11)[2])(v11);
    }
  }
  while ( !v7 );
  v12 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return a2;
}

```

## disassembly

```asm
0x18000ef20  mov     [rsp-8+arg_10], rbx
0x18000ef25  push    rbp
0x18000ef26  push    rsi
0x18000ef27  push    rdi
0x18000ef28  push    r14
0x18000ef2a  push    r15
0x18000ef2c  lea     rbp, [rsp-37h]
0x18000ef31  sub     rsp, 90h
0x18000ef38  mov     rax, cs:__security_cookie
0x18000ef3f  xor     rax, rsp
0x18000ef42  mov     [rbp+57h+var_30], rax
0x18000ef46  mov     r14, rdx
0x18000ef49  mov     rdx, rcx
0x18000ef4c  mov     [rbp+57h+var_78], r14
0x18000ef50  mov     [rbp+57h+var_80], 0
0x18000ef57  mov     rcx, r14
0x18000ef5a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ef5f  mov     [rbp+57h+var_80], 1
0x18000ef66  mov     [rbp+57h+var_40], 0
0x18000ef6e  mov     rcx, [rdx]
0x18000ef71  mov     rax, [rcx]
0x18000ef74  lea     rdx, [rbp+57h+var_40]
0x18000ef78  mov     rax, [rax+48h]
0x18000ef7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef81  mov     rcx, [rbp+5Fh]; this
0x18000ef85  test    eax, eax
0x18000ef87  jns     short loc_18000EF9E
0x18000ef89  mov     r9d, eax; char *
0x18000ef8c  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000ef93  mov     edx, 0DAh; void *
0x18000ef98  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ef9e  xor     r15d, r15d
0x18000efa1  mov     [rbp+57h+var_38], 0
0x18000efa8  mov     [rbp+57h+var_48], 0
0x18000efb0  mov     rcx, [rbp+57h+var_40]
0x18000efb4  mov     rax, [rcx]
0x18000efb7  lea     r9, [rbp+57h+var_38]
0x18000efbb  lea     r8, [rbp+57h+var_48]
0x18000efbf  mov     edx, 1
0x18000efc4  mov     rax, [rax+40h]
0x18000efc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efcd  mov     esi, eax
0x18000efcf  mov     rcx, [rbp+5Fh]; this
0x18000efd3  test    eax, eax
0x18000efd5  js      loc_18000F0D0
0x18000efdb  test    eax, eax
0x18000efdd  jnz     short loc_18000F051
0x18000efdf  mov     [rbp+57h+var_50], 0
0x18000efe7  mov     rbx, [rbp+57h+var_48]
0x18000efeb  mov     rax, [rbx]
0x18000efee  mov     rdi, [rax]
0x18000eff1  lea     rcx, [rbp+57h+var_50]
0x18000eff5  call    ?InternalRelease@?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(void)
0x18000effa  lea     r8, [rbp+57h+var_50]
0x18000effe  lea     rdx, _GUID_dcb0000a_570f_4a9b_8d69_199fdba5723b
0x18000f005  mov     rcx, rbx
0x18000f008  mov     rax, rdi
0x18000f00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f010  nop
0x18000f011  mov     rcx, [rbp+5Fh]; this
0x18000f015  test    eax, eax
0x18000f017  js      loc_18000F0BB
0x18000f01d  inc     r15d
0x18000f020  mov     r9d, r15d
0x18000f023  mov     r8, [rbp+57h+var_50]
0x18000f027  lea     rdx, [rbp+57h+var_70]
0x18000f02b  call    ?Log@PublicNlm@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkConnectionCost@@K@Z; PublicNlm::Log(INetworkConnectionCost *,ulong)
0x18000f030  nop
0x18000f031  mov     rdx, rax
0x18000f034  mov     rcx, r14
0x18000f037  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000f03c  nop
0x18000f03d  lea     rcx, [rbp+57h+var_70]
0x18000f041  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f046  nop
0x18000f047  lea     rcx, [rbp+57h+var_50]
0x18000f04b  call    ?InternalRelease@?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(void)
0x18000f050  nop
0x18000f051  mov     rcx, [rbp+57h+var_48]
0x18000f055  test    rcx, rcx
0x18000f058  jz      short loc_18000F06F
0x18000f05a  mov     [rbp+57h+var_48], 0
0x18000f062  mov     rax, [rcx]
0x18000f065  mov     rax, [rax+10h]
0x18000f069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06e  nop
0x18000f06f  test    esi, esi
0x18000f071  jz      loc_18000EFA1
0x18000f077  mov     rcx, [rbp+57h+var_40]
0x18000f07b  test    rcx, rcx
0x18000f07e  jz      short loc_18000F095
0x18000f080  mov     [rbp+57h+var_40], 0
0x18000f088  mov     rdx, [rcx]
0x18000f08b  mov     rax, [rdx+10h]
0x18000f08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f094  nop
0x18000f095  mov     rax, r14
0x18000f098  mov     rcx, [rbp+57h+var_30]
0x18000f09c  xor     rcx, rsp; StackCookie
0x18000f09f  call    __security_check_cookie
0x18000f0a4  mov     rbx, [rsp+0B0h+arg_10]
0x18000f0ac  add     rsp, 90h
0x18000f0b3  pop     r15
0x18000f0b5  pop     r14
0x18000f0b7  pop     rdi
0x18000f0b8  pop     rsi
0x18000f0b9  pop     rbp
0x18000f0ba  retn
0x18000f0bb  mov     r9d, eax; char *
0x18000f0be  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f0c5  mov     edx, 0E7h; void *
0x18000f0ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f0d0  mov     r9d, esi; char *
0x18000f0d3  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f0da  mov     edx, 0E2h; void *
0x18000f0df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
