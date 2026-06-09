# PublicNlm::GetNetworkCost(void)

- ea: `0x180010f64`
- end: `0x180011013`
- name: `?GetNetworkCost@PublicNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f888`

## callees

- `0x18000e310`
- `0x180010f64`
- `0x18001101c`
- `0x1800120d0`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x180010fc9`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PublicNlm::GetNetworkCost(__int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *), __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rbx
  int v5; // eax
  int v7; // [rsp+20h] [rbp-28h]
  __int64 v8; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v8 = 0;
  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(&v8);
  v5 = v4(v3, &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b, &v8);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v5,
      v7);
  PublicNlm::Log((__int64)retaddr, a2, v8);
  Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(&v8);
  return a2;
}

```

## disassembly

```asm
0x180010f64  mov     r11, rsp
0x180010f67  mov     [r11+18h], rbx
0x180010f6b  mov     [r11+20h], rsi
0x180010f6f  push    rdi
0x180010f70  sub     rsp, 40h
0x180010f74  mov     rax, cs:__security_cookie
0x180010f7b  xor     rax, rsp
0x180010f7e  mov     [rsp+48h+var_18], rax
0x180010f83  mov     rsi, rdx
0x180010f86  mov     [rsp+48h+var_20], rdx
0x180010f8b  mov     qword ptr [r11-20h], 0
0x180010f93  mov     rdi, [rcx]
0x180010f96  mov     rax, [rdi]
0x180010f99  mov     rbx, [rax]
0x180010f9c  lea     rcx, [r11-20h]
0x180010fa0  call    ?InternalRelease@?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(void)
0x180010fa5  lea     r8, [rsp+48h+var_20]
0x180010faa  lea     rdx, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b
0x180010fb1  mov     rcx, rdi
0x180010fb4  mov     rax, rbx
0x180010fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fbc  nop
0x180010fbd  mov     rcx, [rsp+48h]; this
0x180010fc2  test    eax, eax
0x180010fc4  jns     short loc_180010FDB
0x180010fc6  mov     r9d, eax; char *
0x180010fc9  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x180010fd0  mov     edx, 0D0h; void *
0x180010fd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010fdb  mov     r8, [rsp+48h+var_20]
0x180010fe0  mov     rdx, rsi
0x180010fe3  call    ?Log@PublicNlm@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkCostManager@@@Z; PublicNlm::Log(INetworkCostManager *)
0x180010fe8  nop
0x180010fe9  lea     rcx, [rsp+48h+var_20]
0x180010fee  call    ?InternalRelease@?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(void)
0x180010ff3  mov     rax, rsi
0x180010ff6  mov     rcx, [rsp+48h+var_18]
0x180010ffb  xor     rcx, rsp; StackCookie
0x180010ffe  call    __security_check_cookie
0x180011003  mov     rbx, [rsp+48h+arg_10]
0x180011008  mov     rsi, [rsp+48h+arg_18]
0x18001100d  add     rsp, 40h
0x180011011  pop     rdi
0x180011012  retn
```
