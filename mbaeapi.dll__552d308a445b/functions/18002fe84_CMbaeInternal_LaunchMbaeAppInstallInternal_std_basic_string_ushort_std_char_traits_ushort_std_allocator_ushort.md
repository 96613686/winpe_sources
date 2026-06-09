# CMbaeInternal::_LaunchMbaeAppInstallInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002fe84`
- end: `0x18003003a`
- name: `?_LaunchMbaeAppInstallInternal@CMbaeInternal@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ec40`

## callees

- `0x1800024e0`
- `0x1800163ec`
- `0x1800171b8`
- `0x18002b724`
- `0x18002cb44`
- `0x18002f288`
- `0x18002f500`
- `0x18002fe84`
- `0x1800301c8`
- `0x180030790`
- `0x180031534`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ff91`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ff91`

## string_xrefs

- `0x18002fee4`: `CMbaeInternal::_LaunchMbaeAppInstallInternal`

## pseudocode

```c
__int64 __fastcall CMbaeInternal::_LaunchMbaeAppInstallInternal(_QWORD *a1, _QWORD *a2)
{
  int AppPackageFamilyName; // eax
  __int64 v5; // r8
  int AppStoreUri; // eax
  __int128 *v7; // rdx
  __int64 v8; // rcx
  CMbaeInternal *v9; // rcx
  int v11; // [rsp+20h] [rbp-60h]
  __int64 v12; // [rsp+30h] [rbp-50h] BYREF
  _DWORD *v13; // [rsp+38h] [rbp-48h] BYREF
  _DWORD v14[4]; // [rsp+40h] [rbp-40h] BYREF
  __int128 *v15; // [rsp+50h] [rbp-30h]
  __int128 v16; // [rsp+58h] [rbp-28h] BYREF
  __m128i si128; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( !a1[3] )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
      a1[3] == 0 ? (const char *)0x8007139FLL : 0,
      v11);
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    McTemplateU0szz_EventWriteTransfer(
      (_DWORD)retaddr,
      (unsigned int)CMbaeInternal_cpp355,
      (unsigned int)"CMbaeInternal::_LaunchMbaeAppInstallInternal",
      a1[4],
      a1[5]);
  AppPackageFamilyName = CMbaeInternal::_GetAppPackageFamilyName((__int64)a1, (__int64)a2);
  if ( AppPackageFamilyName < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
      (const char *)(unsigned int)AppPackageFamilyName,
      v11);
  v16 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v16) = 0;
  AppStoreUri = CMbaeInternal::_GetAppStoreUri(a2, &v16, v5);
  if ( AppStoreUri < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
      (const char *)(unsigned int)AppStoreUri,
      v11);
  if ( (Microsoft_Windows_Mobile_Broadband_Experience_Api_InternalEnableBits & 2) != 0 )
  {
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    McTemplateU0zz_EventWriteTransfer(retaddr, LaunchingAppstore, a1[5], a2);
  }
  v7 = &v16;
  if ( si128.m128i_i64[1] > 7uLL )
    v7 = (__int128 *)v16;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)v7 + v8) );
  if ( (_DWORD)v8 )
  {
    if ( *((_WORD *)v7 + (unsigned int)v8) )
      abort();
    v14[0] = 1;
    v14[1] = v8;
    v15 = v7;
    v13 = v14;
  }
  else
  {
    v13 = 0;
  }
  winrt::Windows::Foundation::Uri::Uri(
    (winrt::Windows::Foundation::Uri *)&v12,
    (const struct winrt::param::hstring *)&v13);
  CMbaeInternal::_LaunchUri(v9, (const struct winrt::Windows::Foundation::Uri *)&v12);
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  return std::wstring::~wstring((char **)&v16);
}

```

## disassembly

```asm
0x18002fe84  mov     [rsp-18h+arg_10], rbx
0x18002fe89  push    rbp
0x18002fe8a  push    rsi
0x18002fe8b  push    rdi
0x18002fe8c  mov     rbp, rsp
0x18002fe8f  sub     rsp, 80h
0x18002fe96  mov     rax, cs:__security_cookie
0x18002fe9d  xor     rax, rsp
0x18002fea0  mov     [rbp+var_8], rax
0x18002fea4  mov     rbx, rdx
0x18002fea7  mov     rdi, rcx
0x18002feaa  mov     rax, [rcx+18h]
0x18002feae  neg     rax
0x18002feb1  sbb     r9d, r9d
0x18002feb4  not     r9d
0x18002feb7  and     r9d, 8007139Fh; char *
0x18002febe  mov     rcx, [rbp+18h]; this
0x18002fec2  xor     esi, esi
0x18002fec4  cmp     [rdi+18h], rsi
0x18002fec8  jz      loc_180030013
0x18002fece  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x18002fed5  jz      short loc_18002FEF7
0x18002fed7  mov     rax, [rdi+28h]
0x18002fedb  mov     qword ptr [rsp+80h+var_60], rax; int
0x18002fee0  mov     r9, [rdi+20h]
0x18002fee4  lea     r8, aCmbaeinternalL_0; "CMbaeInternal::_LaunchMbaeAppInstallInt"...
0x18002feeb  lea     rdx, CMbaeInternal_cpp355
0x18002fef2  call    McTemplateU0szz_EventWriteTransfer
0x18002fef7  mov     rdx, rbx
0x18002fefa  mov     rcx, rdi
0x18002fefd  call    ?_GetAppPackageFamilyName@CMbaeInternal@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMbaeInternal::_GetAppPackageFamilyName(std::wstring &)
0x18002ff02  mov     rcx, [rbp+18h]; this
0x18002ff06  test    eax, eax
0x18002ff08  js      loc_180030025
0x18002ff0e  xorps   xmm0, xmm0
0x18002ff11  movups  [rbp+var_28], xmm0
0x18002ff15  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002ff1d  movdqu  [rbp+var_18], xmm1
0x18002ff22  mov     word ptr [rbp+var_28], si
0x18002ff26  lea     rdx, [rbp+var_28]; void *
0x18002ff2a  mov     rcx, rbx; Src
0x18002ff2d  call    ?_GetAppStoreUri@CMbaeInternal@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; CMbaeInternal::_GetAppStoreUri(std::wstring const &,std::wstring &)
0x18002ff32  mov     rcx, [rbp+18h]; this
0x18002ff36  test    eax, eax
0x18002ff38  js      loc_18002FFFE
0x18002ff3e  test    cs:Microsoft_Windows_Mobile_Broadband_Experience_Api_InternalEnableBits, 2
0x18002ff45  jz      short loc_18002FF64
0x18002ff47  cmp     qword ptr [rbx+18h], 7
0x18002ff4c  jbe     short loc_18002FF51
0x18002ff4e  mov     rbx, [rbx]
0x18002ff51  mov     r9, rbx
0x18002ff54  mov     r8, [rdi+28h]
0x18002ff58  lea     rdx, LaunchingAppstore
0x18002ff5f  call    McTemplateU0zz_EventWriteTransfer
0x18002ff64  lea     rdx, [rbp+var_28]
0x18002ff68  cmp     qword ptr [rbp+var_18+8], 7
0x18002ff6d  cmova   rdx, qword ptr [rbp+var_28]
0x18002ff72  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002ff76  inc     rcx
0x18002ff79  cmp     [rdx+rcx*2], si
0x18002ff7d  jnz     short loc_18002FF76
0x18002ff7f  test    ecx, ecx
0x18002ff81  jnz     short loc_18002FF89
0x18002ff83  mov     [rbp+var_48], rsi
0x18002ff87  jmp     short loc_18002FFAE
0x18002ff89  mov     eax, ecx
0x18002ff8b  cmp     [rdx+rax*2], si
0x18002ff8f  jz      short loc_18002FF98
0x18002ff91  call    cs:__imp_abort
0x18002ff98  mov     [rbp+var_40], 1
0x18002ff9f  mov     [rbp+var_3C], ecx
0x18002ffa2  mov     [rbp+var_30], rdx
0x18002ffa6  lea     rax, [rbp+var_40]
0x18002ffaa  mov     [rbp+var_48], rax
0x18002ffae  lea     rdx, [rbp+var_48]; struct winrt::param::hstring *
0x18002ffb2  lea     rcx, [rbp+var_50]; this
0x18002ffb6  call    ??0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@3@@Z; winrt::Windows::Foundation::Uri::Uri(winrt::param::hstring const &)
0x18002ffbb  nop
0x18002ffbc  lea     rdx, [rbp+var_50]; struct winrt::Windows::Foundation::Uri *
0x18002ffc0  call    ?_LaunchUri@CMbaeInternal@@AEAAXAEBUUri@Foundation@Windows@winrt@@@Z; CMbaeInternal::_LaunchUri(winrt::Windows::Foundation::Uri const &)
0x18002ffc5  nop
0x18002ffc6  cmp     [rbp+var_50], rsi
0x18002ffca  jz      short loc_18002FFD6
0x18002ffcc  lea     rcx, [rbp+var_50]
0x18002ffd0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002ffd5  nop
0x18002ffd6  lea     rcx, [rbp+var_28]
0x18002ffda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ffdf  mov     rcx, [rbp+var_8]
0x18002ffe3  xor     rcx, rsp; StackCookie
0x18002ffe6  call    __security_check_cookie
0x18002ffeb  mov     rbx, [rsp+80h+arg_10]
0x18002fff3  add     rsp, 80h
0x18002fffa  pop     rdi
0x18002fffb  pop     rsi
0x18002fffc  pop     rbp
0x18002fffd  retn
0x18002fffe  mov     r9d, eax; char *
0x180030001  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180030008  mov     edx, 168h; void *
0x18003000d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180030013  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003001a  mov     edx, 162h; void *
0x18003001f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180030025  mov     r9d, eax; char *
0x180030028  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003002f  mov     edx, 165h; void *
0x180030034  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
