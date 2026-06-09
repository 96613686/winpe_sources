# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180025afc`
- end: `0x180025cb9`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027020`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x180025afc`
- `0x18002e028`
- `0x180036e4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025c1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025c1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c84`

## string_xrefs

- `0x180025c67`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        char *a1,
        __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  void *v8; // rbx
  unsigned __int64 v9; // rdi
  int v10; // esi
  void *v11; // rsi
  DWORD LastError; // edi
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  char v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[512]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  pv = 0;
  memset_0(v16, 0, sizeof(v16));
  v14 = 0;
  result = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v16, 256, &v14);
  if ( (int)result >= 0 )
  {
    v5 = v14;
    if ( v14 > 0x100 )
    {
      while ( 1 )
      {
        v9 = v5;
        v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v5 - 1);
        if ( v6 < 0 )
        {
          v7 = 378;
          goto LABEL_20;
        }
        v8 = pv;
        v10 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v9, &v14);
        if ( v10 < 0 )
          break;
        v5 = v14;
        if ( v14 <= v9 )
          goto LABEL_9;
      }
      if ( v8 )
        CoTaskMemFree(v8);
      return (unsigned int)v10;
    }
    else
    {
      v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
             &pv,
             v16,
             v14 - 1);
      if ( v6 >= 0 )
      {
        v8 = pv;
LABEL_9:
        if ( a1 == &v15 )
        {
          if ( v8 )
            CoTaskMemFree(v8);
        }
        else
        {
          v11 = *(void **)a1;
          if ( *(_QWORD *)a1 )
          {
            LastError = GetLastError();
            CoTaskMemFree(v11);
            SetLastError(LastError);
          }
          *(_QWORD *)a1 = v8;
        }
        return 0;
      }
      else
      {
        v7 = 367;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
          (const char *)(unsigned int)v6,
          (int)pv);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v6;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025afc  mov     [rsp-8+arg_10], rbx
0x180025b01  push    rbp
0x180025b02  push    rsi
0x180025b03  push    rdi
0x180025b04  push    r14
0x180025b06  push    r15
0x180025b08  lea     rbp, [rsp-150h]
0x180025b10  sub     rsp, 250h
0x180025b17  mov     rax, cs:__security_cookie
0x180025b1e  xor     rax, rsp
0x180025b21  mov     [rbp+170h+var_30], rax
0x180025b28  mov     r15, rdx
0x180025b2b  mov     r14, rcx
0x180025b2e  mov     [rsp+270h+pv], 0; int
0x180025b37  xor     edx, edx; Val
0x180025b39  mov     r8d, 200h; Size
0x180025b3f  lea     rcx, [rsp+270h+var_230]; void *
0x180025b44  call    memset_0
0x180025b49  mov     [rsp+270h+var_248], 0
0x180025b52  lea     r9, [rsp+270h+var_248]
0x180025b57  mov     ebx, 100h
0x180025b5c  mov     r8d, ebx
0x180025b5f  lea     rdx, [rsp+270h+var_230]
0x180025b64  mov     rcx, r15
0x180025b67  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180025b6c  test    eax, eax
0x180025b6e  js      loc_180025C92
0x180025b74  mov     rax, [rsp+270h+var_248]
0x180025b79  cmp     rax, rbx
0x180025b7c  ja      short loc_180025BA8
0x180025b7e  lea     r8, [rax-1]
0x180025b82  lea     rdx, [rsp+270h+var_230]
0x180025b87  lea     rcx, [rsp+270h+pv]
0x180025b8c  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180025b91  mov     ebx, eax
0x180025b93  test    eax, eax
0x180025b95  jns     short loc_180025BA1
0x180025b97  mov     edx, 16Fh
0x180025b9c  jmp     loc_180025C64
0x180025ba1  mov     rbx, [rsp+270h+pv]
0x180025ba6  jmp     short loc_180025BED
0x180025ba8  mov     rdi, rax
0x180025bab  lea     r8, [rax-1]
0x180025baf  xor     edx, edx
0x180025bb1  lea     rcx, [rsp+270h+pv]
0x180025bb6  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180025bbb  mov     ebx, eax
0x180025bbd  test    eax, eax
0x180025bbf  js      loc_180025C5F
0x180025bc5  lea     r9, [rsp+270h+var_248]
0x180025bca  mov     r8, rdi
0x180025bcd  mov     rbx, [rsp+270h+pv]
0x180025bd2  mov     rdx, rbx
0x180025bd5  mov     rcx, r15
0x180025bd8  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180025bdd  mov     esi, eax
0x180025bdf  test    eax, eax
0x180025be1  js      short loc_180025C47
0x180025be3  mov     rax, [rsp+270h+var_248]
0x180025be8  cmp     rax, rdi
0x180025beb  ja      short loc_180025BA8
0x180025bed  lea     rax, [rsp+270h+var_240]
0x180025bf2  cmp     r14, rax
0x180025bf5  jz      short loc_180025C2F
0x180025bf7  mov     rsi, [r14]
0x180025bfa  test    rsi, rsi
0x180025bfd  jz      short loc_180025C2A
0x180025bff  call    cs:__imp_GetLastError
0x180025c06  nop     dword ptr [rax+rax+00h]
0x180025c0b  mov     edi, eax
0x180025c0d  mov     rcx, rsi; pv
0x180025c10  call    cs:__imp_CoTaskMemFree
0x180025c17  nop     dword ptr [rax+rax+00h]
0x180025c1c  mov     ecx, edi; dwErrCode
0x180025c1e  call    cs:__imp_SetLastError
0x180025c25  nop     dword ptr [rax+rax+00h]
0x180025c2a  mov     [r14], rbx
0x180025c2d  jmp     short loc_180025C43
0x180025c2f  test    rbx, rbx
0x180025c32  jz      short loc_180025C43
0x180025c34  mov     rcx, rbx; pv
0x180025c37  call    cs:__imp_CoTaskMemFree
0x180025c3e  nop     dword ptr [rax+rax+00h]
0x180025c43  xor     eax, eax
0x180025c45  jmp     short loc_180025C92
0x180025c47  test    rbx, rbx
0x180025c4a  jz      short loc_180025C5B
0x180025c4c  mov     rcx, rbx; pv
0x180025c4f  call    cs:__imp_CoTaskMemFree
0x180025c56  nop     dword ptr [rax+rax+00h]
0x180025c5b  mov     eax, esi
0x180025c5d  jmp     short loc_180025C92
0x180025c5f  mov     edx, 17Ah; void *
0x180025c64  mov     r9d, ebx; char *
0x180025c67  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025c6e  mov     rcx, [rbp+178h]; this
0x180025c75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c7a  mov     rcx, [rsp+270h+pv]; pv
0x180025c7f  test    rcx, rcx
0x180025c82  jz      short loc_180025C90
0x180025c84  call    cs:__imp_CoTaskMemFree
0x180025c8b  nop     dword ptr [rax+rax+00h]
0x180025c90  mov     eax, ebx
0x180025c92  mov     rcx, [rbp+170h+var_30]
0x180025c99  xor     rcx, rsp; StackCookie
0x180025c9c  call    __security_check_cookie
0x180025ca1  mov     rbx, [rsp+270h+arg_10]
0x180025ca9  add     rsp, 250h
0x180025cb0  pop     r15
0x180025cb2  pop     r14
0x180025cb4  pop     rdi
0x180025cb5  pop     rsi
0x180025cb6  pop     rbp
0x180025cb7  retn
```
