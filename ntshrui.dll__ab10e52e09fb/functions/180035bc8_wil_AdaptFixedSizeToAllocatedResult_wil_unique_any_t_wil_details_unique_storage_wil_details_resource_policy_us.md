# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180035bc8`
- end: `0x180035d44`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044d14`

## callees

- `0x18001ed38`
- `0x180020764`
- `0x1800214cc`
- `0x180021660`
- `0x1800254e0`
- `0x180026394`
- `0x180035bc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035cd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035cd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d15`

## string_xrefs

- `0x180035cf8`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v4; // rax
  int v5; // ebx
  __int64 v6; // rdx
  void *v7; // rbx
  unsigned __int64 v8; // rdi
  int v9; // esi
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v11; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v12[512]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  pv = 0;
  memset_0(v12, 0, sizeof(v12));
  v11 = 0;
  result = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v12, 256, &v11);
  if ( (int)result >= 0 )
  {
    v4 = v11;
    if ( v11 > 0x100 )
    {
      while ( 1 )
      {
        v8 = v4;
        v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v4 - 1);
        if ( v5 < 0 )
        {
          v6 = 378;
          goto LABEL_16;
        }
        v7 = pv;
        v9 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v8, &v11);
        if ( v9 < 0 )
          break;
        v4 = v11;
        if ( v11 <= v8 )
          goto LABEL_9;
      }
      if ( v7 )
        CoTaskMemFree(v7);
      return (unsigned int)v9;
    }
    else
    {
      v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
             &pv,
             v12,
             v11 - 1);
      if ( v5 >= 0 )
      {
        v7 = pv;
LABEL_9:
        pv = v7;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &lpSubKey,
          &pv);
        if ( pv )
          CoTaskMemFree(pv);
        return 0;
      }
      else
      {
        v6 = 367;
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v6,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
          (const char *)(unsigned int)v5,
          (int)pv);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180035bc8  mov     [rsp-8+arg_0], rbx
0x180035bcd  mov     [rsp-8+arg_10], rsi
0x180035bd2  push    rbp
0x180035bd3  push    rdi
0x180035bd4  push    r14
0x180035bd6  lea     rbp, [rsp-140h]
0x180035bde  sub     rsp, 240h
0x180035be5  mov     rax, cs:__security_cookie
0x180035bec  xor     rax, rsp
0x180035bef  mov     [rbp+150h+var_20], rax
0x180035bf6  mov     r14, rdx
0x180035bf9  mov     [rsp+250h+pv], 0; int
0x180035c02  xor     edx, edx; Val
0x180035c04  mov     r8d, 200h; Size
0x180035c0a  lea     rcx, [rsp+250h+var_220]; void *
0x180035c0f  call    memset_0
0x180035c14  mov     [rsp+250h+var_228], 0
0x180035c1d  lea     r9, [rsp+250h+var_228]
0x180035c22  mov     ebx, 100h
0x180035c27  mov     r8d, ebx
0x180035c2a  lea     rdx, [rsp+250h+var_220]
0x180035c2f  mov     rcx, r14
0x180035c32  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180035c37  test    eax, eax
0x180035c39  js      loc_180035D1D
0x180035c3f  mov     rax, [rsp+250h+var_228]
0x180035c44  cmp     rax, rbx
0x180035c47  ja      short loc_180035C73
0x180035c49  lea     r8, [rax-1]
0x180035c4d  lea     rdx, [rsp+250h+var_220]
0x180035c52  lea     rcx, [rsp+250h+pv]
0x180035c57  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180035c5c  mov     ebx, eax
0x180035c5e  test    eax, eax
0x180035c60  jns     short loc_180035C6C
0x180035c62  mov     edx, 16Fh
0x180035c67  jmp     loc_180035CF5
0x180035c6c  mov     rbx, [rsp+250h+pv]
0x180035c71  jmp     short loc_180035CB4
0x180035c73  mov     rdi, rax
0x180035c76  lea     r8, [rax-1]
0x180035c7a  xor     edx, edx
0x180035c7c  lea     rcx, [rsp+250h+pv]
0x180035c81  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180035c86  mov     ebx, eax
0x180035c88  test    eax, eax
0x180035c8a  js      short loc_180035CF0
0x180035c8c  lea     r9, [rsp+250h+var_228]
0x180035c91  mov     r8, rdi
0x180035c94  mov     rbx, [rsp+250h+pv]
0x180035c99  mov     rdx, rbx
0x180035c9c  mov     rcx, r14
0x180035c9f  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180035ca4  mov     esi, eax
0x180035ca6  test    eax, eax
0x180035ca8  js      short loc_180035CDE
0x180035caa  mov     rax, [rsp+250h+var_228]
0x180035caf  cmp     rax, rdi
0x180035cb2  ja      short loc_180035C73
0x180035cb4  mov     [rsp+250h+pv], rbx
0x180035cb9  lea     rdx, [rsp+250h+pv]
0x180035cbe  lea     rcx, lpSubKey
0x180035cc5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180035cca  mov     rcx, [rsp+250h+pv]; pv
0x180035ccf  test    rcx, rcx
0x180035cd2  jz      short loc_180035CDA
0x180035cd4  call    cs:__imp_CoTaskMemFree
0x180035cda  xor     eax, eax
0x180035cdc  jmp     short loc_180035D1D
0x180035cde  test    rbx, rbx
0x180035ce1  jz      short loc_180035CEC
0x180035ce3  mov     rcx, rbx; pv
0x180035ce6  call    cs:__imp_CoTaskMemFree
0x180035cec  mov     eax, esi
0x180035cee  jmp     short loc_180035D1D
0x180035cf0  mov     edx, 17Ah; void *
0x180035cf5  mov     r9d, ebx; char *
0x180035cf8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035cff  mov     rcx, [rbp+158h]; this
0x180035d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d0b  mov     rcx, [rsp+250h+pv]; pv
0x180035d10  test    rcx, rcx
0x180035d13  jz      short loc_180035D1B
0x180035d15  call    cs:__imp_CoTaskMemFree
0x180035d1b  mov     eax, ebx
0x180035d1d  mov     rcx, [rbp+150h+var_20]
0x180035d24  xor     rcx, rsp; StackCookie
0x180035d27  call    __security_check_cookie
0x180035d2c  lea     r11, [rsp+250h+var_10]
0x180035d34  mov     rbx, [r11+20h]
0x180035d38  mov     rsi, [r11+30h]
0x180035d3c  mov     rsp, r11
0x180035d3f  pop     r14
0x180035d41  pop     rdi
0x180035d42  pop     rbp
0x180035d43  retn
```
