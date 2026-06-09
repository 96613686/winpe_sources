# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180006af8`
- end: `0x180006cc6`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006aa0`

## callees

- `0x180001ba0`
- `0x18000296c`
- `0x180005964`
- `0x180006af8`
- `0x180009190`
- `0x18000ab88`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c81`

## string_xrefs

- `0x180006c64`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        char *a2)
{
  int v3; // edi
  unsigned __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rdx
  void *v7; // rbx
  unsigned __int64 v8; // rsi
  void *v9; // rsi
  DWORD LastError; // edi
  void *v11; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t *v15; // [rsp+30h] [rbp-D0h] BYREF
  char v16; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[13]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v19; // [rsp+B0h] [rbp-50h]
  _BYTE v20[512]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v15 = L"%SystemRoot%\\uus";
  v18[0] = ___7____func_V_lambda_1___1____ExpandEnvironmentStringsW_V__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJPEBGAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___2__Z___A6AJPEAG_KPEA_K_Z___function_wistd__6B_;
  v18[1] = &v15;
  v19 = v18;
  pv = 0;
  memset_0(v20, 0, sizeof(v20));
  v14 = 0;
  v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, v20, 256, &v14);
  if ( v3 >= 0 )
  {
    v4 = v14;
    if ( v14 > 0x100 )
    {
      while ( 1 )
      {
        v8 = v4;
        v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v4 - 1);
        v3 = v5;
        if ( v5 < 0 )
        {
          v6 = 378;
          goto LABEL_19;
        }
        v7 = pv;
        v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, pv, v8, &v14);
        if ( v3 < 0 )
          break;
        v4 = v14;
        if ( v14 <= v8 )
          goto LABEL_9;
      }
      if ( !v7 )
        goto LABEL_21;
      v11 = v7;
      goto LABEL_20;
    }
    v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
           &pv,
           v20,
           v14 - 1);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v7 = pv;
LABEL_9:
      if ( a2 == &v16 )
      {
        if ( v7 )
          CoTaskMemFree(v7);
      }
      else
      {
        v9 = *(void **)a2;
        if ( *(_QWORD *)a2 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v9);
          SetLastError(LastError);
        }
        *(_QWORD *)a2 = v7;
      }
      v3 = 0;
    }
    else
    {
      v6 = 367;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)(unsigned int)v5,
        (int)pv);
      v11 = pv;
      if ( pv )
LABEL_20:
        CoTaskMemFree(v11);
    }
  }
LABEL_21:
  if ( v19 )
    (*(void (__fastcall **)(_QWORD *))(*v19 + 24LL))(v19);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006af8  mov     [rsp-8+arg_0], rbx
0x180006afd  mov     [rsp-8+arg_10], rsi
0x180006b02  push    rbp
0x180006b03  push    rdi
0x180006b04  push    r14
0x180006b06  lea     rbp, [rsp-1D0h]
0x180006b0e  sub     rsp, 2D0h
0x180006b15  mov     rax, cs:__security_cookie
0x180006b1c  xor     rax, rsp
0x180006b1f  mov     [rbp+1E0h+var_20], rax
0x180006b26  mov     r14, rdx
0x180006b29  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x180006b30  mov     [rsp+2E0h+var_2B0], rax
0x180006b35  lea     rax, ??_7?$__func@V_lambda_1_@?1???$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180006b3c  mov     [rsp+2E0h+var_298], rax
0x180006b41  lea     rax, [rsp+2E0h+var_2B0]
0x180006b46  mov     [rsp+2E0h+var_290], rax
0x180006b4b  lea     rax, [rsp+2E0h+var_298]
0x180006b50  mov     [rbp+1E0h+var_230], rax
0x180006b54  mov     [rsp+2E0h+pv], 0; int
0x180006b5d  xor     edx, edx; Val
0x180006b5f  mov     r8d, 200h; Size
0x180006b65  lea     rcx, [rbp+1E0h+var_220]; void *
0x180006b69  call    memset_0
0x180006b6e  mov     [rsp+2E0h+var_2B8], 0
0x180006b77  lea     r9, [rsp+2E0h+var_2B8]
0x180006b7c  mov     ebx, 100h
0x180006b81  mov     r8d, ebx
0x180006b84  lea     rdx, [rbp+1E0h+var_220]
0x180006b88  lea     rcx, [rsp+2E0h+var_2A0]
0x180006b8d  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180006b92  mov     edi, eax
0x180006b94  test    eax, eax
0x180006b96  js      loc_180006C88
0x180006b9c  mov     rax, [rsp+2E0h+var_2B8]
0x180006ba1  cmp     rax, rbx
0x180006ba4  ja      short loc_180006BCD
0x180006ba6  lea     r8, [rax-1]
0x180006baa  lea     rdx, [rbp+1E0h+var_220]
0x180006bae  lea     rcx, [rsp+2E0h+pv]
0x180006bb3  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180006bb8  mov     edi, eax
0x180006bba  test    eax, eax
0x180006bbc  jns     short loc_180006BC6
0x180006bbe  lea     edx, [rbx+6Fh]
0x180006bc1  jmp     loc_180006C61
0x180006bc6  mov     rbx, [rsp+2E0h+pv]
0x180006bcb  jmp     short loc_180006C10
0x180006bcd  mov     rsi, rax
0x180006bd0  lea     r8, [rax-1]
0x180006bd4  xor     edx, edx
0x180006bd6  lea     rcx, [rsp+2E0h+pv]
0x180006bdb  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180006be0  mov     edi, eax
0x180006be2  test    eax, eax
0x180006be4  js      short loc_180006C5C
0x180006be6  lea     r9, [rsp+2E0h+var_2B8]
0x180006beb  mov     r8, rsi
0x180006bee  mov     rbx, [rsp+2E0h+pv]
0x180006bf3  mov     rdx, rbx
0x180006bf6  lea     rcx, [rsp+2E0h+var_2A0]
0x180006bfb  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180006c00  mov     edi, eax
0x180006c02  test    eax, eax
0x180006c04  js      short loc_180006C52
0x180006c06  mov     rax, [rsp+2E0h+var_2B8]
0x180006c0b  cmp     rax, rsi
0x180006c0e  ja      short loc_180006BCD
0x180006c10  lea     rax, [rsp+2E0h+var_2A8]
0x180006c15  cmp     r14, rax
0x180006c18  jz      short loc_180006C40
0x180006c1a  mov     rsi, [r14]
0x180006c1d  test    rsi, rsi
0x180006c20  jz      short loc_180006C3B
0x180006c22  call    cs:__imp_GetLastError
0x180006c28  mov     edi, eax
0x180006c2a  mov     rcx, rsi; pv
0x180006c2d  call    cs:__imp_CoTaskMemFree
0x180006c33  mov     ecx, edi; dwErrCode
0x180006c35  call    cs:__imp_SetLastError
0x180006c3b  mov     [r14], rbx
0x180006c3e  jmp     short loc_180006C4E
0x180006c40  test    rbx, rbx
0x180006c43  jz      short loc_180006C4E
0x180006c45  mov     rcx, rbx; pv
0x180006c48  call    cs:__imp_CoTaskMemFree
0x180006c4e  xor     edi, edi
0x180006c50  jmp     short loc_180006C88
0x180006c52  test    rbx, rbx
0x180006c55  jz      short loc_180006C88
0x180006c57  mov     rcx, rbx
0x180006c5a  jmp     short loc_180006C81
0x180006c5c  mov     edx, 17Ah; void *
0x180006c61  mov     r9d, eax; char *
0x180006c64  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006c6b  mov     rcx, [rbp+1E8h]; this
0x180006c72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c77  mov     rcx, [rsp+2E0h+pv]; pv
0x180006c7c  test    rcx, rcx
0x180006c7f  jz      short loc_180006C88
0x180006c81  call    cs:__imp_CoTaskMemFree
0x180006c87  nop
0x180006c88  mov     rcx, [rbp+1E0h+var_230]
0x180006c8c  test    rcx, rcx
0x180006c8f  jz      short loc_180006C9D
0x180006c91  mov     rdx, [rcx]
0x180006c94  mov     rax, [rdx+18h]
0x180006c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9d  mov     eax, edi
0x180006c9f  mov     rcx, [rbp+1E0h+var_20]
0x180006ca6  xor     rcx, rsp; StackCookie
0x180006ca9  call    __security_check_cookie
0x180006cae  lea     r11, [rsp+2E0h+var_10]
0x180006cb6  mov     rbx, [r11+20h]
0x180006cba  mov     rsi, [r11+30h]
0x180006cbe  mov     rsp, r11
0x180006cc1  pop     r14
0x180006cc3  pop     rdi
0x180006cc4  pop     rbp
0x180006cc5  retn
```
