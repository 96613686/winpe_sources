# GetMsaPerDeviceKeyRegLocation(ushort * *)

- ea: `0x18001e1a4`
- end: `0x18001e323`
- name: `?GetMsaPerDeviceKeyRegLocation@@YAJPEAPEAG@Z`
- size: `383`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e4f0`

## callees

- `0x18000b0fc`
- `0x18000b898`
- `0x18000db5c`
- `0x180010730`
- `0x180014478`
- `0x180014e40`
- `0x18001e1a4`
- `0x180022ef4`

## string_xrefs

- `0x18001e1cf`: `login.live.com`
- `0x18001e1e8`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\tpmsymmetricpopkey.cpp`
- `0x18001e22a`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\tpmsymmetricpopkey.cpp`
- `0x18001e29a`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\tpmsymmetricpopkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetMsaPerDeviceKeyRegLocation(unsigned __int16 **a1)
{
  unsigned __int16 **v2; // r8
  unsigned __int16 **v3; // r9
  int v4; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rdx
  NgcUtils *v7; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdi
  unsigned __int64 v12; // r14
  unsigned __int16 *v13; // rsi
  __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  const unsigned __int16 *v18; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  __int64 v20; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int16 *v21; // [rsp+80h] [rbp+50h] BYREF
  __int64 v22; // [rsp+88h] [rbp+58h] BYREF

  v22 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v22,
    0);
  v4 = NgcUtils::HashStringIntoHexString((NgcUtils *)L"login.live.com", (const unsigned __int16 *)&v22, v2, v3);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v20 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v20,
      0);
    NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                          v7,
                                          v6,
                                          L"KeyTransportKey",
                                          (unsigned __int16 *)&v20);
    v5 = NgcStateSeparatedRegistryLocation;
    if ( NgcStateSeparatedRegistryLocation >= 0 )
    {
      v9 = -1;
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v22 + 2 * v10) );
      v11 = v20;
      do
        ++v9;
      while ( *(_WORD *)(v20 + 2 * v9) );
      v12 = (unsigned int)(v10 + 27 + v9);
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v21,
        0,
        v12);
      v13 = v21;
      if ( v21 )
      {
        v18 = L"PerDeviceKeyTransportKey";
        v16 = StringCchPrintfW(v21, v12, L"%s\\%s\\%s", v11);
        v5 = v16;
        if ( v16 >= 0 )
        {
          v21 = 0;
          *a1 = v13;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
          v5 = 0;
          goto LABEL_16;
        }
        v14 = (unsigned int)v16;
        v15 = 39;
      }
      else
      {
        v5 = -2147024882;
        v14 = 2147942414LL;
        v15 = 31;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
        (const char *)v14,
        (int)v18);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
        (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
        (int)v18);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)(unsigned int)v4,
      (int)v18);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  return v5;
}

```

## disassembly

```asm
0x18001e1a4  push    rbp
0x18001e1a6  push    rbx
0x18001e1a7  push    rsi
0x18001e1a8  push    rdi
0x18001e1a9  push    r12
0x18001e1ab  push    r14
0x18001e1ad  push    r15
0x18001e1af  mov     rbp, rsp
0x18001e1b2  sub     rsp, 30h
0x18001e1b6  mov     r15, rcx
0x18001e1b9  xor     r12d, r12d
0x18001e1bc  mov     [rbp+arg_18], r12
0x18001e1c0  xor     edx, edx
0x18001e1c2  lea     rcx, [rbp+arg_18]
0x18001e1c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001e1cb  lea     rdx, [rbp+arg_18]; unsigned __int16 *
0x18001e1cf  lea     rcx, aLoginLiveCom; "login.live.com"
0x18001e1d6  call    ?HashStringIntoHexString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::HashStringIntoHexString(ushort const *,ushort * *)
0x18001e1db  mov     ebx, eax
0x18001e1dd  test    eax, eax
0x18001e1df  jns     short loc_18001E1FE
0x18001e1e1  mov     rcx, [rbp+38h]; this
0x18001e1e5  mov     r9d, eax; char *
0x18001e1e8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e1ef  lea     edx, [r12+12h]; void *
0x18001e1f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e1f9  jmp     loc_18001E309
0x18001e1fe  mov     [rbp+arg_8], r12
0x18001e202  xor     edx, edx
0x18001e204  lea     rcx, [rbp+arg_8]
0x18001e208  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001e20d  lea     r9, [rbp+arg_8]; unsigned __int16 *
0x18001e211  lea     r8, aKeytransportke; "KeyTransportKey"
0x18001e218  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001e21d  mov     ebx, eax
0x18001e21f  test    eax, eax
0x18001e221  jns     short loc_18001E24A
0x18001e223  mov     rcx, [rbp+38h]; this
0x18001e227  mov     r9d, eax; char *
0x18001e22a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e231  mov     edx, 17h; void *
0x18001e236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e23b  nop
0x18001e23c  lea     rcx, [rbp+arg_8]
0x18001e240  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e245  jmp     loc_18001E309
0x18001e24a  mov     rbx, [rbp+arg_18]
0x18001e24e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e252  mov     rcx, rax
0x18001e255  inc     rcx
0x18001e258  cmp     [rbx+rcx*2], r12w
0x18001e25d  jnz     short loc_18001E255
0x18001e25f  mov     rdi, [rbp+arg_8]
0x18001e263  inc     rax
0x18001e266  cmp     [rdi+rax*2], r12w
0x18001e26b  jnz     short loc_18001E263
0x18001e26d  add     rcx, 1Bh
0x18001e271  add     rax, rcx
0x18001e274  mov     r14d, eax
0x18001e277  mov     r8d, eax
0x18001e27a  xor     edx, edx
0x18001e27c  lea     rcx, [rbp+arg_10]
0x18001e280  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001e285  nop
0x18001e286  mov     rsi, [rbp+arg_10]
0x18001e28a  test    rsi, rsi
0x18001e28d  jnz     short loc_18001E2B6
0x18001e28f  mov     ebx, 8007000Eh
0x18001e294  mov     r9d, ebx; char *
0x18001e297  lea     edx, [rsi+1Fh]; void *
0x18001e29a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e2a1  mov     rcx, [rbp+38h]; this
0x18001e2a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e2aa  nop
0x18001e2ab  lea     rcx, [rbp+arg_10]
0x18001e2af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e2b4  jmp     short loc_18001E23C
0x18001e2b6  mov     [rsp+30h+var_8], rbx
0x18001e2bb  lea     rax, aPerdevicekeytr; "PerDeviceKeyTransportKey"
0x18001e2c2  mov     [rsp+30h+var_10], rax
0x18001e2c7  mov     r9, rdi
0x18001e2ca  lea     r8, aSSS; "%s\\%s\\%s"
0x18001e2d1  mov     rdx, r14; unsigned __int64
0x18001e2d4  mov     rcx, rsi; unsigned __int16 *
0x18001e2d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e2dc  mov     ebx, eax
0x18001e2de  test    eax, eax
0x18001e2e0  jns     short loc_18001E2EC
0x18001e2e2  mov     r9d, eax
0x18001e2e5  mov     edx, 27h ; '''
0x18001e2ea  jmp     short loc_18001E29A
0x18001e2ec  mov     [rbp+arg_10], r12
0x18001e2f0  mov     [r15], rsi
0x18001e2f3  lea     rcx, [rbp+arg_10]
0x18001e2f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e2fc  nop
0x18001e2fd  lea     rcx, [rbp+arg_8]
0x18001e301  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e306  mov     ebx, r12d
0x18001e309  lea     rcx, [rbp+arg_18]
0x18001e30d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e312  mov     eax, ebx
0x18001e314  add     rsp, 30h
0x18001e318  pop     r15
0x18001e31a  pop     r14
0x18001e31c  pop     r12
0x18001e31e  pop     rdi
0x18001e31f  pop     rsi
0x18001e320  pop     rbx
0x18001e321  pop     rbp
0x18001e322  retn
```
