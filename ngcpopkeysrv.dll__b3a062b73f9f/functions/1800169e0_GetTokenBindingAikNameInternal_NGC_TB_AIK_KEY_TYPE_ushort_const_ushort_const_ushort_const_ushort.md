# GetTokenBindingAikNameInternal(_NGC_TB_AIK_KEY_TYPE,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x1800169e0`
- end: `0x180016db8`
- name: `?GetTokenBindingAikNameInternal@@YAJW4_NGC_TB_AIK_KEY_TYPE@@PEBG11PEAPEAG@Z`
- size: `984`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015644`
- `0x180016328`
- `0x180016718`

## callees

- `0x180004de0`
- `0x18000b0fc`
- `0x18000b7c8`
- `0x18000b854`
- `0x18000db5c`
- `0x180014e40`
- `0x180015314`
- `0x1800169e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180016a44`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180016a44`

## string_xrefs

- `0x180016a2e`: `PerDeviceTokenBindingAik`
- `0x180016a75`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016b3b`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016b7b`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016bbd`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016bf6`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016c36`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016c73`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016caf`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016ceb`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016d27`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016d63`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetTokenBindingAikNameInternal(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  const unsigned __int16 *v7; // r14
  int v8; // ebx
  unsigned __int64 v9; // r11
  __int64 v10; // rdx
  unsigned __int64 v12; // r11
  unsigned __int64 v13; // r11
  unsigned __int64 v14; // r11
  unsigned __int64 v15; // rdi
  unsigned __int16 *v16; // rbx
  int v17; // eax
  unsigned int v18; // esi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  unsigned int v27; // edi
  unsigned __int16 *v28; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v29; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int64 v30; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v31; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v32; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v33; // [rsp+48h] [rbp-30h] BYREF
  wchar_t Buffer[8]; // [rsp+50h] [rbp-28h] BYREF
  int v35; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v33 = 0;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  *(_OWORD *)Buffer = 0;
  v35 = 0;
  v7 = L"PerDeviceTokenBindingAik";
  if ( a4 )
    v7 = a4;
  _itow(a1, Buffer, 10);
  v8 = StringCchLengthW(L"tbaik", 0x104u, &v33);
  if ( v8 < 0 )
  {
    v10 = 455;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v8,
      (int)v28);
    return (unsigned int)v8;
  }
  v8 = StringCchLengthW(a2, v9, &v32);
  if ( v8 < 0 )
  {
    v10 = 460;
    goto LABEL_5;
  }
  v8 = StringCchLengthW(Buffer, v12, &v31);
  if ( v8 < 0 )
  {
    v10 = 465;
    goto LABEL_5;
  }
  v8 = StringCchLengthW(a3, v13, &v30);
  if ( v8 < 0 )
  {
    v10 = 470;
    goto LABEL_5;
  }
  v8 = StringCchLengthW(v7, v14, &v29);
  if ( v8 < 0 )
  {
    v10 = 475;
    goto LABEL_5;
  }
  v15 = v32 + v31 + v30 + v29 + v33 + 5;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v28,
    0,
    v15);
  v16 = v28;
  if ( !v28 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)0x8007000ELL,
      0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return (unsigned int)v8;
  }
  v17 = StringCchCopyW(v28, v15, L"tbaik");
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v17,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v18;
  }
  v19 = StringCchCatW(v16, v15, L"_");
  v18 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v19,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v18;
  }
  v20 = StringCchCatW(v16, v15, a2);
  v18 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v20,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v18;
  }
  v21 = StringCchCatW(v16, v15, L"_");
  v18 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v21,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v18;
  }
  v22 = StringCchCatW(v16, v15, Buffer);
  v18 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x201,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v22,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v18;
  }
  v23 = StringCchCatW(v16, v15, L"_");
  v18 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v23,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v18;
  }
  v24 = StringCchCatW(v16, v15, a3);
  v18 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v24,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v18;
  }
  v25 = StringCchCatW(v16, v15, L"_");
  v18 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v25,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v18;
  }
  v26 = StringCchCatW(v16, v15, v7);
  v27 = v26;
  if ( v26 >= 0 )
  {
    v28 = 0;
    *a5 = v16;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x215,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v26,
      (int)v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return v27;
  }
}

```

## disassembly

```asm
0x1800169e0  push    rbp
0x1800169e2  push    rbx
0x1800169e3  push    rsi
0x1800169e4  push    rdi
0x1800169e5  push    r12
0x1800169e7  push    r13
0x1800169e9  push    r14
0x1800169eb  push    r15
0x1800169ed  mov     rbp, rsp
0x1800169f0  sub     rsp, 78h
0x1800169f4  mov     rax, cs:__security_cookie
0x1800169fb  xor     rax, rsp
0x1800169fe  mov     [rbp+var_10], rax
0x180016a02  mov     r12, r8
0x180016a05  mov     r15, rdx
0x180016a08  mov     r13, [rbp+arg_20]
0x180016a0c  xor     esi, esi
0x180016a0e  mov     [rbp+var_30], rsi
0x180016a12  mov     [rbp+var_38], rsi
0x180016a16  mov     [rbp+var_40], rsi
0x180016a1a  mov     [rbp+var_48], rsi
0x180016a1e  mov     [rbp+var_50], rsi
0x180016a22  xorps   xmm0, xmm0
0x180016a25  xor     eax, eax
0x180016a27  movups  xmmword ptr [rbp+Buffer], xmm0
0x180016a2b  mov     [rbp+var_18], eax
0x180016a2e  lea     r14, aPerdevicetoken; "PerDeviceTokenBindingAik"
0x180016a35  test    r9, r9
0x180016a38  cmovnz  r14, r9
0x180016a3c  lea     r8d, [rsi+0Ah]; Radix
0x180016a40  lea     rdx, [rbp+Buffer]; Buffer
0x180016a44  call    cs:__imp__itow
0x180016a4a  lea     r8, [rbp+var_30]; unsigned __int64 *
0x180016a4e  mov     r11d, 104h
0x180016a54  mov     edx, r11d; unsigned __int64
0x180016a57  lea     rcx, aTbaik; "tbaik"
0x180016a5e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180016a63  mov     ebx, eax
0x180016a65  test    eax, eax
0x180016a67  jns     short loc_180016A88
0x180016a69  mov     edx, 1C7h; void *
0x180016a6e  mov     rcx, [rbp+40h]; this
0x180016a72  mov     r9d, ebx; char *
0x180016a75  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016a7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a81  mov     eax, ebx
0x180016a83  jmp     loc_180016D9B
0x180016a88  lea     r8, [rbp+var_38]; unsigned __int64 *
0x180016a8c  mov     rdx, r11; unsigned __int64
0x180016a8f  mov     rcx, r15; unsigned __int16 *
0x180016a92  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180016a97  mov     ebx, eax
0x180016a99  test    eax, eax
0x180016a9b  jns     short loc_180016AA4
0x180016a9d  mov     edx, 1CCh
0x180016aa2  jmp     short loc_180016A6E
0x180016aa4  lea     r8, [rbp+var_40]; unsigned __int64 *
0x180016aa8  mov     rdx, r11; unsigned __int64
0x180016aab  lea     rcx, [rbp+Buffer]; unsigned __int16 *
0x180016aaf  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180016ab4  mov     ebx, eax
0x180016ab6  test    eax, eax
0x180016ab8  jns     short loc_180016AC1
0x180016aba  mov     edx, 1D1h
0x180016abf  jmp     short loc_180016A6E
0x180016ac1  lea     r8, [rbp+var_48]; unsigned __int64 *
0x180016ac5  mov     rdx, r11; unsigned __int64
0x180016ac8  mov     rcx, r12; unsigned __int16 *
0x180016acb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180016ad0  mov     ebx, eax
0x180016ad2  test    eax, eax
0x180016ad4  jns     short loc_180016ADD
0x180016ad6  mov     edx, 1D6h
0x180016adb  jmp     short loc_180016A6E
0x180016add  lea     r8, [rbp+var_50]; unsigned __int64 *
0x180016ae1  mov     rdx, r11; unsigned __int64
0x180016ae4  mov     rcx, r14; unsigned __int16 *
0x180016ae7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180016aec  mov     ebx, eax
0x180016aee  test    eax, eax
0x180016af0  jns     short loc_180016AFC
0x180016af2  mov     edx, 1DBh
0x180016af7  jmp     loc_180016A6E
0x180016afc  mov     rdx, [rbp+var_50]
0x180016b00  add     rdx, [rbp+var_48]
0x180016b04  add     rdx, [rbp+var_40]
0x180016b08  add     rdx, [rbp+var_38]
0x180016b0c  mov     rdi, [rbp+var_30]
0x180016b10  add     rdi, 5
0x180016b14  add     rdi, rdx
0x180016b17  mov     r8, rdi
0x180016b1a  xor     edx, edx
0x180016b1c  lea     rcx, [rbp+var_58]
0x180016b20  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180016b25  nop
0x180016b26  mov     rbx, [rbp+var_58]
0x180016b2a  test    rbx, rbx
0x180016b2d  jnz     short loc_180016B5C
0x180016b2f  mov     rcx, [rbp+40h]; this
0x180016b33  mov     ebx, 8007000Eh
0x180016b38  mov     r9d, ebx; char *
0x180016b3b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016b42  mov     edx, 1E6h; void *
0x180016b47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b4c  nop
0x180016b4d  lea     rcx, [rbp+var_58]
0x180016b51  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016b56  nop
0x180016b57  jmp     loc_180016A81
0x180016b5c  lea     r8, aTbaik; "tbaik"
0x180016b63  mov     rdx, rdi; unsigned __int64
0x180016b66  mov     rcx, rbx; unsigned __int16 *
0x180016b69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016b6e  mov     esi, eax
0x180016b70  test    eax, eax
0x180016b72  jns     short loc_180016B9E
0x180016b74  mov     rcx, [rbp+40h]; this
0x180016b78  mov     r9d, eax; char *
0x180016b7b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016b82  mov     edx, 1EDh; void *
0x180016b87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b8c  nop
0x180016b8d  lea     rcx, [rbp+var_58]
0x180016b91  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016b96  nop
0x180016b97  mov     eax, esi
0x180016b99  jmp     loc_180016D9B
0x180016b9e  lea     r8, asc_18002ADA0; "_"
0x180016ba5  mov     rdx, rdi; unsigned __int64
0x180016ba8  mov     rcx, rbx; unsigned __int16 *
0x180016bab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016bb0  mov     esi, eax
0x180016bb2  test    eax, eax
0x180016bb4  jns     short loc_180016BDB
0x180016bb6  mov     rcx, [rbp+40h]; this
0x180016bba  mov     r9d, eax; char *
0x180016bbd  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016bc4  mov     edx, 1F2h; void *
0x180016bc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016bce  nop
0x180016bcf  lea     rcx, [rbp+var_58]
0x180016bd3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016bd8  nop
0x180016bd9  jmp     short loc_180016B97
0x180016bdb  mov     r8, r15; unsigned __int16 *
0x180016bde  mov     rdx, rdi; unsigned __int64
0x180016be1  mov     rcx, rbx; unsigned __int16 *
0x180016be4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016be9  mov     esi, eax
0x180016beb  test    eax, eax
0x180016bed  jns     short loc_180016C14
0x180016bef  mov     rcx, [rbp+40h]; this
0x180016bf3  mov     r9d, eax; char *
0x180016bf6  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016bfd  mov     edx, 1F7h; void *
0x180016c02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c07  nop
0x180016c08  lea     rcx, [rbp+var_58]
0x180016c0c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016c11  nop
0x180016c12  jmp     short loc_180016B97
0x180016c14  lea     r15, asc_18002ADA0; "_"
0x180016c1b  mov     r8, r15; unsigned __int16 *
0x180016c1e  mov     rdx, rdi; unsigned __int64
0x180016c21  mov     rcx, rbx; unsigned __int16 *
0x180016c24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016c29  mov     esi, eax
0x180016c2b  test    eax, eax
0x180016c2d  jns     short loc_180016C57
0x180016c2f  mov     rcx, [rbp+40h]; this
0x180016c33  mov     r9d, eax; char *
0x180016c36  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016c3d  mov     edx, 1FCh; void *
0x180016c42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c47  nop
0x180016c48  lea     rcx, [rbp+var_58]
0x180016c4c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016c51  nop
0x180016c52  jmp     loc_180016B97
0x180016c57  lea     r8, [rbp+Buffer]; unsigned __int16 *
0x180016c5b  mov     rdx, rdi; unsigned __int64
0x180016c5e  mov     rcx, rbx; unsigned __int16 *
0x180016c61  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016c66  mov     esi, eax
0x180016c68  test    eax, eax
0x180016c6a  jns     short loc_180016C94
0x180016c6c  mov     rcx, [rbp+40h]; this
0x180016c70  mov     r9d, eax; char *
0x180016c73  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016c7a  mov     edx, 201h; void *
0x180016c7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c84  nop
0x180016c85  lea     rcx, [rbp+var_58]
0x180016c89  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016c8e  nop
0x180016c8f  jmp     loc_180016B97
0x180016c94  mov     r8, r15; unsigned __int16 *
0x180016c97  mov     rdx, rdi; unsigned __int64
0x180016c9a  mov     rcx, rbx; unsigned __int16 *
0x180016c9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016ca2  mov     esi, eax
0x180016ca4  test    eax, eax
0x180016ca6  jns     short loc_180016CD0
0x180016ca8  mov     rcx, [rbp+40h]; this
0x180016cac  mov     r9d, eax; char *
0x180016caf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016cb6  mov     edx, 206h; void *
0x180016cbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cc0  nop
0x180016cc1  lea     rcx, [rbp+var_58]
0x180016cc5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016cca  nop
0x180016ccb  jmp     loc_180016B97
0x180016cd0  mov     r8, r12; unsigned __int16 *
0x180016cd3  mov     rdx, rdi; unsigned __int64
0x180016cd6  mov     rcx, rbx; unsigned __int16 *
0x180016cd9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016cde  mov     esi, eax
0x180016ce0  test    eax, eax
0x180016ce2  jns     short loc_180016D0C
0x180016ce4  mov     rcx, [rbp+40h]; this
0x180016ce8  mov     r9d, eax; char *
0x180016ceb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016cf2  mov     edx, 20Bh; void *
0x180016cf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cfc  nop
0x180016cfd  lea     rcx, [rbp+var_58]
0x180016d01  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016d06  nop
0x180016d07  jmp     loc_180016B97
0x180016d0c  mov     r8, r15; unsigned __int16 *
0x180016d0f  mov     rdx, rdi; unsigned __int64
0x180016d12  mov     rcx, rbx; unsigned __int16 *
0x180016d15  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016d1a  mov     esi, eax
0x180016d1c  test    eax, eax
0x180016d1e  jns     short loc_180016D48
0x180016d20  mov     rcx, [rbp+40h]; this
0x180016d24  mov     r9d, eax; char *
0x180016d27  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016d2e  mov     edx, 210h; void *
0x180016d33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d38  nop
0x180016d39  lea     rcx, [rbp+var_58]
0x180016d3d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016d42  nop
0x180016d43  jmp     loc_180016B97
0x180016d48  mov     r8, r14; unsigned __int16 *
0x180016d4b  mov     rdx, rdi; unsigned __int64
0x180016d4e  mov     rcx, rbx; unsigned __int16 *
0x180016d51  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016d56  mov     edi, eax
0x180016d58  test    eax, eax
0x180016d5a  jns     short loc_180016D83
0x180016d5c  mov     rcx, [rbp+40h]; this
0x180016d60  mov     r9d, eax; char *
0x180016d63  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016d6a  mov     edx, 215h; void *
0x180016d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d74  nop
0x180016d75  lea     rcx, [rbp+var_58]
0x180016d79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016d7e  nop
0x180016d7f  mov     eax, edi
0x180016d81  jmp     short loc_180016D9B
0x180016d83  mov     [rbp+var_58], 0
0x180016d8b  mov     [r13+0], rbx
0x180016d8f  lea     rcx, [rbp+var_58]
0x180016d93  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016d98  nop
0x180016d99  xor     eax, eax
0x180016d9b  mov     rcx, [rbp+var_10]
0x180016d9f  xor     rcx, rsp; StackCookie
0x180016da2  call    __security_check_cookie
0x180016da7  add     rsp, 78h
0x180016dab  pop     r15
0x180016dad  pop     r14
0x180016daf  pop     r13
0x180016db1  pop     r12
0x180016db3  pop     rdi
0x180016db4  pop     rsi
0x180016db5  pop     rbx
0x180016db6  pop     rbp
0x180016db7  retn
```
