# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180003030`
- end: `0x180003214`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `484`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002fcc`

## callees

- `0x180002b40`
- `0x180003030`
- `0x180003220`
- `0x180003290`
- `0x1800033c8`
- `0x180003be0`
- `0x180005020`
- `0x180005b2c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000319d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000319d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031d7`

## string_xrefs

- `0x180003113`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x1800031bc`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  int v3; // edi
  unsigned __int64 v4; // rax
  int v5; // eax
  void *v6; // rcx
  void *v7; // rbx
  unsigned __int64 v8; // r14
  int v9; // eax
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t *v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 *v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v16; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v18[13]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v19; // [rsp+C0h] [rbp-40h]
  _BYTE v20[512]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v13 = L"%SystemRoot%\\uus";
  v18[0] = ___7____func_V_lambda_1___1____ExpandEnvironmentStringsW_V__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJPEBGAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___2__Z___A6AJPEAG_KPEA_K_Z___function_wistd__6B_;
  v18[1] = &v13;
  v19 = v18;
  pv = 0;
  memset_0(v20, 0, sizeof(v20));
  v12 = 0;
  v14 = &v12;
  v15 = 256;
  v16 = v20;
  v3 = __R____func_V_lambda_1___1____ExpandEnvironmentStringsW_V__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJPEBGAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___2__Z___A6AJPEAG_KPEA_K_Z___function_wistd__UEAAJ__QEAPEAG__QEA_K__QEAPEA_K_Z(
         v18,
         &v16,
         &v15,
         &v14);
  if ( v3 >= 0 )
  {
    v4 = v12;
    if ( v12 > 0x100 )
    {
      while ( 1 )
      {
        v8 = v4;
        v9 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v4 - 1);
        v3 = v9;
        if ( v9 < 0 )
          break;
        v7 = pv;
        v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, pv, v8, &v12);
        if ( v3 < 0 )
        {
          if ( !v7 )
            goto LABEL_17;
          v6 = v7;
          goto LABEL_16;
        }
        v4 = v12;
        if ( v12 <= v8 )
          goto LABEL_10;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)(unsigned int)v9,
        (int)pv);
      v6 = pv;
      if ( !pv )
        goto LABEL_17;
      goto LABEL_16;
    }
    v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
           &pv,
           v20,
           v12 - 1);
    v3 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)(unsigned int)v5,
        (int)pv);
      v6 = pv;
      if ( !pv )
        goto LABEL_17;
LABEL_16:
      CoTaskMemFree(v6);
      goto LABEL_17;
    }
    v7 = pv;
LABEL_10:
    pv = v7;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a2,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v3 = 0;
  }
LABEL_17:
  if ( v19 )
    (*(void (__fastcall **)(_QWORD *))(*v19 + 24LL))(v19);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003030  push    rbp
0x180003032  push    rbx
0x180003033  push    rsi
0x180003034  push    rdi
0x180003035  push    r14
0x180003037  push    r15
0x180003039  lea     rbp, [rsp-1E8h]
0x180003041  sub     rsp, 2E8h
0x180003048  mov     rax, cs:__security_cookie
0x18000304f  xor     rax, rsp
0x180003052  mov     [rbp+210h+var_40], rax
0x180003059  mov     rsi, rdx
0x18000305c  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x180003063  mov     [rsp+310h+var_2E0], rax
0x180003068  lea     rax, ??_7?$__func@V_lambda_1_@?1???$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000306f  mov     [rsp+310h+var_2B8], rax
0x180003074  lea     rax, [rsp+310h+var_2E0]
0x180003079  mov     [rsp+310h+var_2B0], rax
0x18000307e  lea     rax, [rsp+310h+var_2B8]
0x180003083  mov     [rbp+210h+var_250], rax
0x180003087  xor     r15d, r15d
0x18000308a  mov     [rsp+310h+pv], r15; int
0x18000308f  xor     edx, edx; Val
0x180003091  mov     r8d, 200h; Size
0x180003097  lea     rcx, [rbp+210h+var_240]; void *
0x18000309b  call    memset_0
0x1800030a0  mov     [rsp+310h+var_2E8], r15
0x1800030a5  lea     rax, [rsp+310h+var_2E8]
0x1800030aa  mov     [rsp+310h+var_2D8], rax
0x1800030af  mov     [rsp+310h+var_2D0], 100h
0x1800030b8  lea     rax, [rbp+210h+var_240]
0x1800030bc  mov     [rsp+310h+var_2C8], rax
0x1800030c1  lea     r9, [rsp+310h+var_2D8]
0x1800030c6  lea     r8, [rsp+310h+var_2D0]
0x1800030cb  lea     rdx, [rsp+310h+var_2C8]
0x1800030d0  lea     rcx, [rsp+310h+var_2B8]
0x1800030d5  call    ??R?$__func@V_lambda_1_@?1???$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z; wistd::__function::__func<`wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)
0x1800030da  mov     edi, eax
0x1800030dc  test    eax, eax
0x1800030de  js      loc_1800031DE
0x1800030e4  mov     rax, [rsp+310h+var_2E8]
0x1800030e9  cmp     rax, 100h
0x1800030ef  ja      short loc_18000313E
0x1800030f1  lea     r8, [rax-1]
0x1800030f5  lea     rdx, [rbp+210h+var_240]
0x1800030f9  lea     rcx, [rsp+310h+pv]
0x1800030fe  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180003103  mov     edi, eax
0x180003105  test    eax, eax
0x180003107  jns     short loc_180003137
0x180003109  mov     rcx, [rbp+218h]; this
0x180003110  mov     r9d, eax; char *
0x180003113  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000311a  mov     edx, 16Fh; void *
0x18000311f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003124  mov     rcx, [rsp+310h+pv]
0x180003129  test    rcx, rcx
0x18000312c  jnz     loc_1800031D7
0x180003132  jmp     loc_1800031DE
0x180003137  mov     rbx, [rsp+310h+pv]
0x18000313c  jmp     short loc_180003181
0x18000313e  mov     r14, rax
0x180003141  lea     r8, [rax-1]
0x180003145  xor     edx, edx
0x180003147  lea     rcx, [rsp+310h+pv]
0x18000314c  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180003151  mov     edi, eax
0x180003153  test    eax, eax
0x180003155  js      short loc_1800031B2
0x180003157  lea     r9, [rsp+310h+var_2E8]
0x18000315c  mov     r8, r14
0x18000315f  mov     rbx, [rsp+310h+pv]
0x180003164  mov     rdx, rbx
0x180003167  lea     rcx, [rsp+310h+var_2C0]
0x18000316c  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180003171  mov     edi, eax
0x180003173  test    eax, eax
0x180003175  js      short loc_1800031A8
0x180003177  mov     rax, [rsp+310h+var_2E8]
0x18000317c  cmp     rax, r14
0x18000317f  ja      short loc_18000313E
0x180003181  mov     [rsp+310h+pv], rbx
0x180003186  lea     rdx, [rsp+310h+pv]
0x18000318b  mov     rcx, rsi
0x18000318e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180003193  mov     rcx, [rsp+310h+pv]; pv
0x180003198  test    rcx, rcx
0x18000319b  jz      short loc_1800031A3
0x18000319d  call    cs:__imp_CoTaskMemFree
0x1800031a3  mov     edi, r15d
0x1800031a6  jmp     short loc_1800031DE
0x1800031a8  test    rbx, rbx
0x1800031ab  jz      short loc_1800031DE
0x1800031ad  mov     rcx, rbx
0x1800031b0  jmp     short loc_1800031D7
0x1800031b2  mov     rcx, [rbp+218h]; this
0x1800031b9  mov     r9d, eax; char *
0x1800031bc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800031c3  mov     edx, 17Ah; void *
0x1800031c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031cd  mov     rcx, [rsp+310h+pv]; pv
0x1800031d2  test    rcx, rcx
0x1800031d5  jz      short loc_1800031DE
0x1800031d7  call    cs:__imp_CoTaskMemFree
0x1800031dd  nop
0x1800031de  mov     rcx, [rbp+210h+var_250]
0x1800031e2  test    rcx, rcx
0x1800031e5  jz      short loc_1800031F3
0x1800031e7  mov     rax, [rcx]
0x1800031ea  mov     rax, [rax+18h]
0x1800031ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f3  mov     eax, edi
0x1800031f5  mov     rcx, [rbp+210h+var_40]
0x1800031fc  xor     rcx, rsp; StackCookie
0x1800031ff  call    __security_check_cookie
0x180003204  add     rsp, 2E8h
0x18000320b  pop     r15
0x18000320d  pop     r14
0x18000320f  pop     rdi
0x180003210  pop     rsi
0x180003211  pop     rbx
0x180003212  pop     rbp
0x180003213  retn
```
