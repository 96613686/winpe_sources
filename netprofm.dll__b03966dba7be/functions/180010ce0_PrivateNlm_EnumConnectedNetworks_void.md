# PrivateNlm::EnumConnectedNetworks(void)

- ea: `0x180010ce0`
- end: `0x180010ea2`
- name: `?EnumConnectedNetworks@PrivateNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `450`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x1800100d8`
- `0x180010124`
- `0x180010ce0`
- `0x1800120d0`
- `0x18003580c`
- `0x180037e38`
- `0x180043010`

## string_xrefs

- `0x180010dc1`: `onecore\net\netprofiles\service\src\netshnlmplugin\privatenetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PrivateNlm::EnumConnectedNetworks(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rcx
  void (*v4)(void); // rax
  int v5; // edi
  const char *v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rcx
  const char *v10; // [rsp+28h] [rbp-31h]
  _BYTE v11[32]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v12; // [rsp+58h] [rbp-1h] BYREF
  __int64 v13; // [rsp+60h] [rbp+7h] BYREF
  int v14; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v15; // [rsp+70h] [rbp+17h] BYREF
  __m128i si128; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v13 = a2;
  v12 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64 *))(*(_QWORD *)*a1 + 32LL))(*a1, 1, &v12) >= 0 )
  {
    v15 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15) = 0;
    v5 = 0;
    do
    {
      v14 = 0;
      v13 = 0;
      v6 = (const char *)(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v12 + 24LL))(
                           v12,
                           1,
                           &v13,
                           &v14);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4A7,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\privatenetworklistmanager.cpp",
        v6,
        (int)"IEnumNetworkPrivate::Next",
        v10);
      if ( !(_DWORD)v6 )
      {
        Log(v11, v13, (unsigned int)++v5);
        std::wstring::append();
        std::wstring::_Tidy_deallocate((__int64)v11);
      }
      v7 = v13;
      if ( v13 )
      {
        v13 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    while ( !(_DWORD)v6 );
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    *(_OWORD *)a2 = v15;
    *(__m128i *)(a2 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15) = 0;
    std::wstring::_Tidy_deallocate((__int64)&v15);
    v8 = v12;
    if ( v12 )
    {
      v12 = 0;
      v4 = *(void (**)(void))(*(_QWORD *)v8 + 16LL);
      goto LABEL_12;
    }
  }
  else
  {
    wil::str_printf<std::wstring>(a2, (__int64)L"  ! <INetworkListManagerPrivate::EnumNetworks failed (0x%x)>", 1);
    v3 = v12;
    if ( v12 )
    {
      v12 = 0;
      v4 = *(void (**)(void))(*(_QWORD *)v3 + 16LL);
LABEL_12:
      v4();
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180010ce0  mov     [rsp-8+arg_10], rbx
0x180010ce5  push    rbp
0x180010ce6  push    rsi
0x180010ce7  push    rdi
0x180010ce8  lea     rbp, [rsp-47h]
0x180010ced  sub     rsp, 0A0h
0x180010cf4  mov     rax, cs:__security_cookie
0x180010cfb  xor     rax, rsp
0x180010cfe  mov     [rbp+57h+var_20], rax
0x180010d02  mov     rbx, rdx
0x180010d05  mov     [rbp+57h+var_50], rdx
0x180010d09  mov     [rbp+57h+var_58], 0
0x180010d11  mov     rcx, [rcx]
0x180010d14  mov     rax, [rcx]
0x180010d17  lea     r8, [rbp+57h+var_58]
0x180010d1b  mov     edx, 1
0x180010d20  mov     rax, [rax+20h]
0x180010d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d29  test    eax, eax
0x180010d2b  jns     short loc_180010D64
0x180010d2d  mov     r8d, 1
0x180010d33  lea     rdx, aInetworklistma_22; "  ! <INetworkListManagerPrivate::EnumNe"...
0x180010d3a  mov     rcx, rbx
0x180010d3d  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180010d42  nop
0x180010d43  mov     rcx, [rbp+57h+var_58]
0x180010d47  test    rcx, rcx
0x180010d4a  jz      loc_180010E80
0x180010d50  mov     [rbp+57h+var_58], 0
0x180010d58  mov     rax, [rcx]
0x180010d5b  mov     rax, [rax+10h]
0x180010d5f  jmp     loc_180010E7A
0x180010d64  xorps   xmm0, xmm0
0x180010d67  movups  [rbp+57h+var_40], xmm0
0x180010d6b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180010d73  movdqu  [rbp+57h+var_30], xmm1
0x180010d78  xor     eax, eax
0x180010d7a  mov     word ptr [rbp+57h+var_40], ax
0x180010d7e  xor     edi, edi
0x180010d80  mov     [rbp+57h+var_48], 0
0x180010d87  mov     [rbp+57h+var_50], 0
0x180010d8f  mov     rcx, [rbp+57h+var_58]
0x180010d93  mov     rax, [rcx]
0x180010d96  lea     r9, [rbp+57h+var_48]
0x180010d9a  lea     r8, [rbp+57h+var_50]
0x180010d9e  mov     edx, 1
0x180010da3  mov     rax, [rax+18h]
0x180010da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dac  mov     esi, eax
0x180010dae  mov     rcx, [rbp+5Fh]; this
0x180010db2  lea     rax, aIenumnetworkpr; "IEnumNetworkPrivate::Next"
0x180010db9  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180010dbe  mov     r9d, esi; char *
0x180010dc1  lea     r8, aOnecoreNetNetp_3; "onecore\\net\\netprofiles\\service\\src"...
0x180010dc8  mov     edx, 4A7h; void *
0x180010dcd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180010dd2  test    esi, esi
0x180010dd4  jnz     short loc_180010E00
0x180010dd6  inc     edi
0x180010dd8  mov     r8d, edi
0x180010ddb  mov     rdx, [rbp+57h+var_50]
0x180010ddf  lea     rcx, [rbp+57h+var_78]
0x180010de3  call    ?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkPrivate@@K@Z; Log(INetworkPrivate *,ulong)
0x180010de8  nop
0x180010de9  mov     rdx, rax
0x180010dec  lea     rcx, [rbp+57h+var_40]
0x180010df0  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180010df5  nop
0x180010df6  lea     rcx, [rbp+57h+var_78]
0x180010dfa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010dff  nop
0x180010e00  mov     rcx, [rbp+57h+var_50]
0x180010e04  test    rcx, rcx
0x180010e07  jz      short loc_180010E1E
0x180010e09  mov     [rbp+57h+var_50], 0
0x180010e11  mov     rax, [rcx]
0x180010e14  mov     rax, [rax+10h]
0x180010e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e1d  nop
0x180010e1e  test    esi, esi
0x180010e20  jz      loc_180010D80
0x180010e26  mov     qword ptr [rbx+10h], 0
0x180010e2e  mov     qword ptr [rbx+18h], 0
0x180010e36  movups  xmm0, [rbp+57h+var_40]
0x180010e3a  movups  xmmword ptr [rbx], xmm0
0x180010e3d  movups  xmm1, [rbp+57h+var_30]
0x180010e41  movups  xmmword ptr [rbx+10h], xmm1
0x180010e45  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180010e4d  movdqu  [rbp+57h+var_30], xmm0
0x180010e52  xor     eax, eax
0x180010e54  mov     word ptr [rbp+57h+var_40], ax
0x180010e58  lea     rcx, [rbp+57h+var_40]
0x180010e5c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010e61  nop
0x180010e62  mov     rcx, [rbp+57h+var_58]
0x180010e66  test    rcx, rcx
0x180010e69  jz      short loc_180010E80
0x180010e6b  mov     [rbp+57h+var_58], 0
0x180010e73  mov     rdx, [rcx]
0x180010e76  mov     rax, [rdx+10h]
0x180010e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e7f  nop
0x180010e80  mov     rax, rbx
0x180010e83  mov     rcx, [rbp+57h+var_20]
0x180010e87  xor     rcx, rsp; StackCookie
0x180010e8a  call    __security_check_cookie
0x180010e8f  mov     rbx, [rsp+0B0h+arg_10]
0x180010e97  add     rsp, 0A0h
0x180010e9e  pop     rdi
0x180010e9f  pop     rsi
0x180010ea0  pop     rbp
0x180010ea1  retn
```
