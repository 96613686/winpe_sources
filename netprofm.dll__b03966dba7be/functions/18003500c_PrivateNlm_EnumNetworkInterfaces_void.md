# PrivateNlm::EnumNetworkInterfaces(void)

- ea: `0x18003500c`
- end: `0x1800351c9`
- name: `?EnumNetworkInterfaces@PrivateNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x1800100d8`
- `0x180010124`
- `0x1800120d0`
- `0x18003500c`
- `0x180036a3c`
- `0x180037e38`
- `0x180043010`

## string_xrefs

- `0x1800350e8`: `onecore\net\netprofiles\service\src\netshnlmplugin\privatenetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PrivateNlm::EnumNetworkInterfaces(_QWORD *a1, __int64 a2)
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
  if ( (*(int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 40LL))(*a1, &v12) >= 0 )
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
        (void *)0x4C1,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\privatenetworklistmanager.cpp",
        v6,
        (int)"IEnumNetworkInterfacePrivate::Next",
        v10);
      if ( !(_DWORD)v6 )
      {
        LogINetworkInterface1((__int64)v11, v13, ++v5);
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
    wil::str_printf<std::wstring>(
      a2,
      (__int64)L"  ! <INetworkListManagerPrivate::EnumNetworkInterfaces failed (0x%x)>",
      1);
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
0x18003500c  mov     [rsp-8+arg_10], rbx
0x180035011  push    rbp
0x180035012  push    rsi
0x180035013  push    rdi
0x180035014  lea     rbp, [rsp-47h]
0x180035019  sub     rsp, 0A0h
0x180035020  mov     rax, cs:__security_cookie
0x180035027  xor     rax, rsp
0x18003502a  mov     [rbp+57h+var_20], rax
0x18003502e  mov     rbx, rdx
0x180035031  mov     [rbp+57h+var_50], rdx
0x180035035  mov     [rbp+57h+var_58], 0
0x18003503d  mov     rcx, [rcx]
0x180035040  mov     rax, [rcx]
0x180035043  lea     rdx, [rbp+57h+var_58]
0x180035047  mov     rax, [rax+28h]
0x18003504b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035050  test    eax, eax
0x180035052  jns     short loc_18003508B
0x180035054  mov     r8d, 1
0x18003505a  lea     rdx, aInetworklistma_20; "  ! <INetworkListManagerPrivate::EnumNe"...
0x180035061  mov     rcx, rbx
0x180035064  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035069  nop
0x18003506a  mov     rcx, [rbp+57h+var_58]
0x18003506e  test    rcx, rcx
0x180035071  jz      loc_1800351A7
0x180035077  mov     [rbp+57h+var_58], 0
0x18003507f  mov     rax, [rcx]
0x180035082  mov     rax, [rax+10h]
0x180035086  jmp     loc_1800351A1
0x18003508b  xorps   xmm0, xmm0
0x18003508e  movups  [rbp+57h+var_40], xmm0
0x180035092  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003509a  movdqu  [rbp+57h+var_30], xmm1
0x18003509f  xor     eax, eax
0x1800350a1  mov     word ptr [rbp+57h+var_40], ax
0x1800350a5  xor     edi, edi
0x1800350a7  mov     [rbp+57h+var_48], 0
0x1800350ae  mov     [rbp+57h+var_50], 0
0x1800350b6  mov     rcx, [rbp+57h+var_58]
0x1800350ba  mov     rax, [rcx]
0x1800350bd  lea     r9, [rbp+57h+var_48]
0x1800350c1  lea     r8, [rbp+57h+var_50]
0x1800350c5  mov     edx, 1
0x1800350ca  mov     rax, [rax+18h]
0x1800350ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350d3  mov     esi, eax
0x1800350d5  mov     rcx, [rbp+5Fh]; this
0x1800350d9  lea     rax, aIenumnetworkin; "IEnumNetworkInterfacePrivate::Next"
0x1800350e0  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800350e5  mov     r9d, esi; char *
0x1800350e8  lea     r8, aOnecoreNetNetp_3; "onecore\\net\\netprofiles\\service\\src"...
0x1800350ef  mov     edx, 4C1h; void *
0x1800350f4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800350f9  test    esi, esi
0x1800350fb  jnz     short loc_180035127
0x1800350fd  inc     edi
0x1800350ff  mov     r8d, edi
0x180035102  mov     rdx, [rbp+57h+var_50]
0x180035106  lea     rcx, [rbp+57h+var_78]
0x18003510a  call    ?LogINetworkInterface1@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkInterfacePrivate@@K@Z; LogINetworkInterface1(INetworkInterfacePrivate *,ulong)
0x18003510f  nop
0x180035110  mov     rdx, rax
0x180035113  lea     rcx, [rbp+57h+var_40]
0x180035117  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003511c  nop
0x18003511d  lea     rcx, [rbp+57h+var_78]
0x180035121  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035126  nop
0x180035127  mov     rcx, [rbp+57h+var_50]
0x18003512b  test    rcx, rcx
0x18003512e  jz      short loc_180035145
0x180035130  mov     [rbp+57h+var_50], 0
0x180035138  mov     rax, [rcx]
0x18003513b  mov     rax, [rax+10h]
0x18003513f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035144  nop
0x180035145  test    esi, esi
0x180035147  jz      loc_1800350A7
0x18003514d  mov     qword ptr [rbx+10h], 0
0x180035155  mov     qword ptr [rbx+18h], 0
0x18003515d  movups  xmm0, [rbp+57h+var_40]
0x180035161  movups  xmmword ptr [rbx], xmm0
0x180035164  movups  xmm1, [rbp+57h+var_30]
0x180035168  movups  xmmword ptr [rbx+10h], xmm1
0x18003516c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180035174  movdqu  [rbp+57h+var_30], xmm0
0x180035179  xor     eax, eax
0x18003517b  mov     word ptr [rbp+57h+var_40], ax
0x18003517f  lea     rcx, [rbp+57h+var_40]
0x180035183  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035188  nop
0x180035189  mov     rcx, [rbp+57h+var_58]
0x18003518d  test    rcx, rcx
0x180035190  jz      short loc_1800351A7
0x180035192  mov     [rbp+57h+var_58], 0
0x18003519a  mov     rdx, [rcx]
0x18003519d  mov     rax, [rdx+10h]
0x1800351a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351a6  nop
0x1800351a7  mov     rax, rbx
0x1800351aa  mov     rcx, [rbp+57h+var_20]
0x1800351ae  xor     rcx, rsp; StackCookie
0x1800351b1  call    __security_check_cookie
0x1800351b6  mov     rbx, [rsp+0B0h+arg_10]
0x1800351be  add     rsp, 0A0h
0x1800351c5  pop     rdi
0x1800351c6  pop     rsi
0x1800351c7  pop     rbp
0x1800351c8  retn
```
