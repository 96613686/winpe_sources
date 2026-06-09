# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,char * &)

- ea: `0x180020a7c`
- end: `0x180020b76`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBGAEAPEAD@Z`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800388bc`

## callees

- `0x180020764`
- `0x180020a7c`
- `0x1800214cc`
- `0x180021660`
- `0x180026424`
- `0x18004ebe8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b5b`

## string_xrefs

- `0x180020ac8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180020b19`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        wchar_t *a2,
        va_list *a3)
{
  __int64 v6; // rbp
  int v7; // eax
  unsigned __int16 **v8; // r8
  unsigned __int64 *v9; // r9
  unsigned int v10; // ebx
  void *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  v6 = vscwprintf(a2, *a3);
  pv = 0;
  v7 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         &pv,
         0,
         v6);
  v10 = v7;
  if ( v7 >= 0 )
  {
    v12 = pv;
    v13 = StringCchVPrintfExW((unsigned __int16 *)pv, v6 + 1, v8, v9, v15, a2, *a3);
    v14 = v13;
    if ( v13 >= 0 )
    {
      pv = v12;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        a1,
        &pv);
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D1,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v13,
        v16);
      if ( v12 )
        CoTaskMemFree(v12);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v7,
      v15);
    if ( pv )
      CoTaskMemFree(pv);
    return v10;
  }
}

```

## disassembly

```asm
0x180020a7c  mov     [rsp+arg_0], rbx
0x180020a81  mov     [rsp+arg_8], rbp
0x180020a86  push    rsi
0x180020a87  push    rdi
0x180020a88  push    r14
0x180020a8a  sub     rsp, 40h
0x180020a8e  mov     rsi, rdx
0x180020a91  mov     r14, rcx
0x180020a94  mov     rdx, [r8]; ArgList
0x180020a97  mov     rcx, rsi; Format
0x180020a9a  mov     rdi, r8
0x180020a9d  call    _vscwprintf
0x180020aa2  movsxd  rbp, eax
0x180020aa5  lea     rcx, [rsp+58h+pv]
0x180020aaa  mov     r8, rbp
0x180020aad  mov     [rsp+58h+pv], 0
0x180020ab6  xor     edx, edx
0x180020ab8  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180020abd  mov     ebx, eax
0x180020abf  test    eax, eax
0x180020ac1  jns     short loc_180020AF0
0x180020ac3  mov     rcx, [rsp+58h]; this
0x180020ac8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020acf  mov     r9d, eax; char *
0x180020ad2  mov     edx, 7CDh; void *
0x180020ad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020adc  mov     rcx, [rsp+58h+pv]; pv
0x180020ae1  test    rcx, rcx
0x180020ae4  jz      short loc_180020AEC
0x180020ae6  call    cs:__imp_CoTaskMemFree
0x180020aec  mov     eax, ebx
0x180020aee  jmp     short loc_180020B63
0x180020af0  mov     rax, [rdi]
0x180020af3  lea     rdx, [rbp+1]; unsigned __int64
0x180020af7  mov     rbx, [rsp+58h+pv]
0x180020afc  mov     [rsp+58h+Args], rax; Args
0x180020b01  mov     rcx, rbx; unsigned __int16 *
0x180020b04  mov     [rsp+58h+Format], rsi; Format
0x180020b09  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x180020b0e  mov     edi, eax
0x180020b10  test    eax, eax
0x180020b12  jns     short loc_180020B3F
0x180020b14  mov     rcx, [rsp+58h]; this
0x180020b19  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020b20  mov     r9d, eax; char *
0x180020b23  mov     edx, 7D1h; void *
0x180020b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b2d  test    rbx, rbx
0x180020b30  jz      short loc_180020B3B
0x180020b32  mov     rcx, rbx; pv
0x180020b35  call    cs:__imp_CoTaskMemFree
0x180020b3b  mov     eax, edi
0x180020b3d  jmp     short loc_180020B63
0x180020b3f  lea     rdx, [rsp+58h+pv]
0x180020b44  mov     [rsp+58h+pv], rbx
0x180020b49  mov     rcx, r14
0x180020b4c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180020b51  mov     rcx, [rsp+58h+pv]; pv
0x180020b56  test    rcx, rcx
0x180020b59  jz      short loc_180020B61
0x180020b5b  call    cs:__imp_CoTaskMemFree
0x180020b61  xor     eax, eax
0x180020b63  mov     rbx, [rsp+58h+arg_0]
0x180020b68  mov     rbp, [rsp+58h+arg_8]
0x180020b6d  add     rsp, 40h
0x180020b71  pop     r14
0x180020b73  pop     rdi
0x180020b74  pop     rsi
0x180020b75  retn
```
