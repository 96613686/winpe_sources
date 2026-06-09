# PrivateNlm::EnumNetworkConnectionProfiles(void)

- ea: `0x180034de8`
- end: `0x180035004`
- name: `?EnumNetworkConnectionProfiles@PrivateNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `540`
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
- `0x180034de8`
- `0x1800355a4`
- `0x180037e38`
- `0x180043010`

## string_xrefs

- `0x180034f1a`: `onecore\net\netprofiles\service\src\netshnlmplugin\privatenetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_OWORD *__fastcall PrivateNlm::EnumNetworkConnectionProfiles(_QWORD *a1, _OWORD *a2)
{
  __int64 v3; // rcx
  void (*v4)(void); // rax
  __int64 v5; // rcx
  int v6; // esi
  const char *v7; // r14
  _OWORD *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  const char *v12; // [rsp+28h] [rbp-31h]
  _BYTE v13[32]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v14; // [rsp+58h] [rbp-1h] BYREF
  __int64 v15; // [rsp+60h] [rbp+7h] BYREF
  _OWORD *v16; // [rsp+68h] [rbp+Fh] BYREF
  int v17; // [rsp+70h] [rbp+17h] BYREF
  __int128 v18; // [rsp+78h] [rbp+1Fh] BYREF
  __m128i si128; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v16 = a2;
  v14 = 0;
  if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1)(*a1, &GUID_5df486f8_50eb_427e_8da3_7122ccaf9415, &v14) < 0 )
  {
    wil::str_printf<std::wstring>(
      (__int64)a2,
      (__int64)L"  ! <INetworkListManagerPrivate::QueryInterface(INetworkListManagerPrivate2) failed (0x%x)>",
      1);
    goto LABEL_3;
  }
  v15 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v14 + 272LL))(v14, 1, &v15) < 0 )
  {
    wil::str_printf<std::wstring>(
      (__int64)a2,
      (__int64)L"  ! <INetworkListManagerPrivate2::EnumNetworkConnectionProfiles failed (0x%x)>",
      1);
    v5 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
LABEL_3:
    v3 = v14;
    if ( v14 )
    {
      v14 = 0;
      v4 = *(void (**)(void))(*(_QWORD *)v3 + 16LL);
LABEL_19:
      v4();
      return a2;
    }
    return a2;
  }
  v18 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v18) = 0;
  v6 = 0;
  do
  {
    v16 = 0;
    v17 = 0;
    v7 = (const char *)(*(unsigned int (__fastcall **)(__int64, __int64, _OWORD **, int *))(*(_QWORD *)v15 + 24LL))(
                         v15,
                         1,
                         &v16,
                         &v17);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x4E5,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\privatenetworklistmanager.cpp",
      v7,
      (int)"IEnumNetworkConnectionProfilePrivate::Next",
      v12);
    if ( !(_DWORD)v7 )
    {
      Log(v13, v16, (unsigned int)++v6);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v13);
    }
    v8 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  while ( !(_DWORD)v7 );
  *a2 = v18;
  a2[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v18) = 0;
  std::wstring::_Tidy_deallocate((__int64)&v18);
  v9 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = v14;
  if ( v14 )
  {
    v14 = 0;
    v4 = *(void (**)(void))(*(_QWORD *)v10 + 16LL);
    goto LABEL_19;
  }
  return a2;
}

```

## disassembly

```asm
0x180034de8  mov     [rsp-8+arg_10], rbx
0x180034ded  mov     [rsp-8+arg_18], rsi
0x180034df2  push    rbp
0x180034df3  push    r14
0x180034df5  push    r15
0x180034df7  lea     rbp, [rsp-47h]
0x180034dfc  sub     rsp, 0A0h
0x180034e03  mov     rax, cs:__security_cookie
0x180034e0a  xor     rax, rsp
0x180034e0d  mov     [rbp+57h+var_18], rax
0x180034e11  mov     rbx, rdx
0x180034e14  mov     [rbp+57h+var_48], rdx
0x180034e18  xor     r15d, r15d
0x180034e1b  mov     [rbp+57h+var_58], r15
0x180034e1f  mov     rcx, [rcx]
0x180034e22  mov     rax, [rcx]
0x180034e25  lea     r8, [rbp+57h+var_58]
0x180034e29  lea     rdx, _GUID_5df486f8_50eb_427e_8da3_7122ccaf9415
0x180034e30  mov     rax, [rax]
0x180034e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e38  test    eax, eax
0x180034e3a  jns     short loc_180034E6D
0x180034e3c  lea     r8d, [r15+1]
0x180034e40  lea     rdx, aInetworklistma_21; "  ! <INetworkListManagerPrivate::QueryI"...
0x180034e47  mov     rcx, rbx
0x180034e4a  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180034e4f  nop
0x180034e50  mov     rcx, [rbp+57h+var_58]
0x180034e54  test    rcx, rcx
0x180034e57  jz      loc_180034FDC
0x180034e5d  mov     [rbp+57h+var_58], r15
0x180034e61  mov     rax, [rcx]
0x180034e64  mov     rax, [rax+10h]
0x180034e68  jmp     loc_180034FD6
0x180034e6d  mov     [rbp+57h+var_50], r15
0x180034e71  mov     rcx, [rbp+57h+var_58]
0x180034e75  mov     rax, [rcx]
0x180034e78  lea     r8, [rbp+57h+var_50]
0x180034e7c  mov     edx, 1
0x180034e81  mov     rax, [rax+110h]
0x180034e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e8d  test    eax, eax
0x180034e8f  jns     short loc_180034EC3
0x180034e91  mov     r8d, 1
0x180034e97  lea     rdx, aInetworklistma_17; "  ! <INetworkListManagerPrivate2::EnumN"...
0x180034e9e  mov     rcx, rbx
0x180034ea1  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180034ea6  nop
0x180034ea7  mov     rcx, [rbp+57h+var_50]
0x180034eab  test    rcx, rcx
0x180034eae  jz      short loc_180034EC1
0x180034eb0  mov     [rbp+57h+var_50], r15
0x180034eb4  mov     rax, [rcx]
0x180034eb7  mov     rax, [rax+10h]
0x180034ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ec0  nop
0x180034ec1  jmp     short loc_180034E50
0x180034ec3  xorps   xmm0, xmm0
0x180034ec6  movups  [rbp+57h+var_38], xmm0
0x180034eca  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180034ed2  movdqu  [rbp+57h+var_28], xmm1
0x180034ed7  mov     word ptr [rbp+57h+var_38], r15w
0x180034edc  mov     esi, r15d
0x180034edf  mov     [rbp+57h+var_48], r15
0x180034ee3  mov     [rbp+57h+var_40], r15d
0x180034ee7  mov     rcx, [rbp+57h+var_50]
0x180034eeb  mov     rax, [rcx]
0x180034eee  lea     r9, [rbp+57h+var_40]
0x180034ef2  lea     r8, [rbp+57h+var_48]
0x180034ef6  mov     edx, 1
0x180034efb  mov     rax, [rax+18h]
0x180034eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f04  mov     r14d, eax
0x180034f07  mov     rcx, [rbp+5Fh]; this
0x180034f0b  lea     rax, aIenumnetworkco; "IEnumNetworkConnectionProfilePrivate::N"...
0x180034f12  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180034f17  mov     r9d, r14d; char *
0x180034f1a  lea     r8, aOnecoreNetNetp_3; "onecore\\net\\netprofiles\\service\\src"...
0x180034f21  mov     edx, 4E5h; void *
0x180034f26  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034f2b  test    r14d, r14d
0x180034f2e  jnz     short loc_180034F5A
0x180034f30  inc     esi
0x180034f32  mov     r8d, esi
0x180034f35  mov     rdx, [rbp+57h+var_48]
0x180034f39  lea     rcx, [rbp+57h+var_78]
0x180034f3d  call    ?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkConnectionProfilePrivate@@K@Z; Log(INetworkConnectionProfilePrivate *,ulong)
0x180034f42  nop
0x180034f43  mov     rdx, rax
0x180034f46  lea     rcx, [rbp+57h+var_38]
0x180034f4a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180034f4f  nop
0x180034f50  lea     rcx, [rbp+57h+var_78]
0x180034f54  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034f59  nop
0x180034f5a  mov     rcx, [rbp+57h+var_48]
0x180034f5e  test    rcx, rcx
0x180034f61  jz      short loc_180034F74
0x180034f63  mov     [rbp+57h+var_48], r15
0x180034f67  mov     rax, [rcx]
0x180034f6a  mov     rax, [rax+10h]
0x180034f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f73  nop
0x180034f74  test    r14d, r14d
0x180034f77  jz      loc_180034EDF
0x180034f7d  movups  xmm0, [rbp+57h+var_38]
0x180034f81  movups  xmmword ptr [rbx], xmm0
0x180034f84  movups  xmm1, [rbp+57h+var_28]
0x180034f88  movups  xmmword ptr [rbx+10h], xmm1
0x180034f8c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180034f94  movdqu  [rbp+57h+var_28], xmm0
0x180034f99  mov     word ptr [rbp+57h+var_38], r15w
0x180034f9e  lea     rcx, [rbp+57h+var_38]
0x180034fa2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034fa7  nop
0x180034fa8  mov     rcx, [rbp+57h+var_50]
0x180034fac  test    rcx, rcx
0x180034faf  jz      short loc_180034FC2
0x180034fb1  mov     [rbp+57h+var_50], r15
0x180034fb5  mov     rax, [rcx]
0x180034fb8  mov     rax, [rax+10h]
0x180034fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fc1  nop
0x180034fc2  mov     rcx, [rbp+57h+var_58]
0x180034fc6  test    rcx, rcx
0x180034fc9  jz      short loc_180034FDC
0x180034fcb  mov     [rbp+57h+var_58], r15
0x180034fcf  mov     rdx, [rcx]
0x180034fd2  mov     rax, [rdx+10h]
0x180034fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fdb  nop
0x180034fdc  mov     rax, rbx
0x180034fdf  mov     rcx, [rbp+57h+var_18]
0x180034fe3  xor     rcx, rsp; StackCookie
0x180034fe6  call    __security_check_cookie
0x180034feb  lea     r11, [rsp+0B0h+var_10]
0x180034ff3  mov     rbx, [r11+30h]
0x180034ff7  mov     rsi, [r11+38h]
0x180034ffb  mov     rsp, r11
0x180034ffe  pop     r15
0x180035000  pop     r14
0x180035002  pop     rbp
0x180035003  retn
```
