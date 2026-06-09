# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x180025214`
- end: `0x180025459`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800267a8`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180025214`
- `0x18002ade4`
- `0x18002cacc`
- `0x18002d40c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800252d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800252d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253d4`

## string_xrefs

- `0x1800252fe`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x180025407`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  unsigned __int64 v7; // rax
  __int64 v8; // rax
  void *v9; // rbx
  __int64 v10; // rcx
  void (*v11)(void); // rax
  unsigned __int64 v12; // rsi
  __int64 v13; // rax
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  LPVOID v18; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[512]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v18 = 0;
  memset_0(v21, 0, sizeof(v21));
  v19 = 0;
  v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v21, 256, &v19);
  if ( v4 < 0 )
  {
    v5 = *(_QWORD *)(a2 + 112);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 24LL))(*(_QWORD *)(a2 + 112));
    return (unsigned int)v4;
  }
  v7 = v19;
  if ( v19 > 0x100 )
  {
    while ( 1 )
    {
      v12 = v7;
      v13 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              pv,
              0,
              v7 - 1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v18,
        v13);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      v9 = v18;
      if ( !v18 )
        break;
      v14 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v18, v12, &v19);
      if ( v14 < 0 )
      {
        CoTaskMemFree(v9);
        v16 = *(_QWORD *)(a2 + 112);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
        return (unsigned int)v14;
      }
      v7 = v19;
      if ( v19 <= v12 )
        goto LABEL_16;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      (const char *)0x8007000ELL,
      0);
    v17 = *(_QWORD *)(a2 + 112);
    if ( !v17 )
      return 2147942414LL;
    v11 = *(void (**)(void))(*(_QWORD *)v17 + 24LL);
    goto LABEL_26;
  }
  v8 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         pv,
         v21,
         v19 - 1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v18,
    v8);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  v9 = v18;
  if ( !v18 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      (const char *)0x8007000ELL,
      0);
    v10 = *(_QWORD *)(a2 + 112);
    if ( !v10 )
      return 2147942414LL;
    v11 = *(void (**)(void))(*(_QWORD *)v10 + 24LL);
LABEL_26:
    v11();
    return 2147942414LL;
  }
LABEL_16:
  v18 = v9;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a1,
    &v18);
  if ( v18 )
    CoTaskMemFree(v18);
  v15 = *(_QWORD *)(a2 + 112);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
  return 0;
}

```

## disassembly

```asm
0x180025214  mov     [rsp-8+arg_10], rbx
0x180025219  push    rbp
0x18002521a  push    rsi
0x18002521b  push    rdi
0x18002521c  push    r14
0x18002521e  push    r15
0x180025220  lea     rbp, [rsp-150h]
0x180025228  sub     rsp, 250h
0x18002522f  mov     rax, cs:__security_cookie
0x180025236  xor     rax, rsp
0x180025239  mov     [rbp+170h+var_30], rax
0x180025240  mov     rdi, rdx
0x180025243  mov     r15, rcx
0x180025246  and     [rsp+270h+var_250], 0
0x18002524c  xor     edx, edx; Val
0x18002524e  mov     r8d, 200h; Size
0x180025254  lea     rcx, [rsp+270h+var_230]; void *
0x180025259  call    memset_0
0x18002525e  and     [rsp+270h+var_248], 0
0x180025264  lea     r9, [rsp+270h+var_248]
0x180025269  mov     esi, 100h
0x18002526e  mov     r8d, esi
0x180025271  lea     rdx, [rsp+270h+var_230]
0x180025276  mov     rcx, rdi
0x180025279  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18002527e  mov     ebx, eax
0x180025280  test    eax, eax
0x180025282  jns     short loc_1800252A3
0x180025284  mov     rdx, [rdi+70h]
0x180025288  test    rdx, rdx
0x18002528b  jz      short loc_18002529C
0x18002528d  mov     rcx, [rdx]
0x180025290  mov     rax, [rcx+18h]
0x180025294  mov     rcx, rdx
0x180025297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002529c  mov     eax, ebx
0x18002529e  jmp     loc_180025432
0x1800252a3  mov     rax, [rsp+270h+var_248]
0x1800252a8  cmp     rax, rsi
0x1800252ab  ja      short loc_180025328
0x1800252ad  lea     r8, [rax-1]
0x1800252b1  lea     rdx, [rsp+270h+var_230]
0x1800252b6  lea     rcx, [rsp+270h+pv]
0x1800252bb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800252c0  mov     rdx, rax
0x1800252c3  lea     rcx, [rsp+270h+var_250]
0x1800252c8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800252cd  mov     rcx, [rsp+270h+pv]; pv
0x1800252d2  test    rcx, rcx
0x1800252d5  jz      short loc_1800252E3
0x1800252d7  call    cs:__imp_CoTaskMemFree
0x1800252de  nop     dword ptr [rax+rax+00h]
0x1800252e3  mov     rbx, [rsp+270h+var_250]
0x1800252e8  test    rbx, rbx
0x1800252eb  jnz     loc_180025390
0x1800252f1  mov     rcx, [rbp+178h]; this
0x1800252f8  mov     r9d, 8007000Eh; char *
0x1800252fe  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025305  mov     edx, 165h; void *
0x18002530a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002530f  mov     rcx, [rdi+70h]
0x180025313  test    rcx, rcx
0x180025316  jz      loc_18002542D
0x18002531c  mov     rax, [rcx]
0x18002531f  mov     rax, [rax+18h]
0x180025323  jmp     loc_180025428
0x180025328  mov     rsi, rax
0x18002532b  lea     r8, [rax-1]
0x18002532f  xor     edx, edx
0x180025331  lea     rcx, [rsp+270h+pv]
0x180025336  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002533b  mov     rdx, rax
0x18002533e  lea     rcx, [rsp+270h+var_250]
0x180025343  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180025348  mov     rcx, [rsp+270h+pv]; pv
0x18002534d  test    rcx, rcx
0x180025350  jz      short loc_18002535E
0x180025352  call    cs:__imp_CoTaskMemFree
0x180025359  nop     dword ptr [rax+rax+00h]
0x18002535e  mov     rbx, [rsp+270h+var_250]
0x180025363  test    rbx, rbx
0x180025366  jz      loc_1800253FA
0x18002536c  lea     r9, [rsp+270h+var_248]
0x180025371  mov     r8, rsi
0x180025374  mov     rdx, rbx
0x180025377  mov     rcx, rdi
0x18002537a  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18002537f  mov     r14d, eax
0x180025382  test    eax, eax
0x180025384  js      short loc_1800253D1
0x180025386  mov     rax, [rsp+270h+var_248]
0x18002538b  cmp     rax, rsi
0x18002538e  ja      short loc_180025328
0x180025390  mov     [rsp+270h+var_250], rbx
0x180025395  lea     rdx, [rsp+270h+var_250]
0x18002539a  mov     rcx, r15
0x18002539d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800253a2  mov     rcx, [rsp+270h+var_250]; pv
0x1800253a7  test    rcx, rcx
0x1800253aa  jz      short loc_1800253B8
0x1800253ac  call    cs:__imp_CoTaskMemFree
0x1800253b3  nop     dword ptr [rax+rax+00h]
0x1800253b8  mov     rcx, [rdi+70h]
0x1800253bc  test    rcx, rcx
0x1800253bf  jz      short loc_1800253CD
0x1800253c1  mov     rax, [rcx]
0x1800253c4  mov     rax, [rax+18h]
0x1800253c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253cd  xor     eax, eax
0x1800253cf  jmp     short loc_180025432
0x1800253d1  mov     rcx, rbx; pv
0x1800253d4  call    cs:__imp_CoTaskMemFree
0x1800253db  nop     dword ptr [rax+rax+00h]
0x1800253e0  mov     rcx, [rdi+70h]
0x1800253e4  test    rcx, rcx
0x1800253e7  jz      short loc_1800253F5
0x1800253e9  mov     rax, [rcx]
0x1800253ec  mov     rax, [rax+18h]
0x1800253f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253f5  mov     eax, r14d
0x1800253f8  jmp     short loc_180025432
0x1800253fa  mov     rcx, [rbp+178h]; this
0x180025401  mov     r9d, 8007000Eh; char *
0x180025407  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002540e  mov     edx, 170h; void *
0x180025413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025418  mov     rcx, [rdi+70h]
0x18002541c  test    rcx, rcx
0x18002541f  jz      short loc_18002542D
0x180025421  mov     rdx, [rcx]
0x180025424  mov     rax, [rdx+18h]
0x180025428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002542d  mov     eax, 8007000Eh
0x180025432  mov     rcx, [rbp+170h+var_30]
0x180025439  xor     rcx, rsp; StackCookie
0x18002543c  call    __security_check_cookie
0x180025441  mov     rbx, [rsp+270h+arg_10]
0x180025449  add     rsp, 250h
0x180025450  pop     r15
0x180025452  pop     r14
0x180025454  pop     rdi
0x180025455  pop     rsi
0x180025456  pop     rbp
0x180025457  retn
```
