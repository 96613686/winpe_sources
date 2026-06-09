# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::get<_GUID,_GUID,0>(void)

- ea: `0x180016e28`
- end: `0x180016ece`
- name: `??$get@U_GUID@@U1@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AU_GUID@@XZ`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001cb44`
- `0x180028cc4`

## callees

- `0x180002490`
- `0x180008a68`
- `0x180008ad0`
- `0x180016e28`
- `0x180016ed4`
- `0x180021184`
- `0x18002229c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016e86`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016e86`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
GUID *__fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<_GUID,_GUID,0>(
        __int64 a1,
        GUID *a2)
{
  const OLECHAR *v3; // rcx
  HRESULT v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v8; // [rsp+20h] [rbp-58h]
  LPCOLESTR lpsz[4]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v10[16]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v11; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a2 = 0;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::string,std::string,0>(
    a1,
    v10);
  if ( v11 )
  {
    anonymous_namespace_::Utf8ToUtf16(lpsz, v10);
    v3 = (const OLECHAR *)lpsz;
    if ( lpsz[3] > (LPCOLESTR)7 )
      v3 = lpsz[0];
    v4 = CLSIDFromString(v3, a2);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x84, v6, (const char *)(unsigned int)v4, v8);
    std::wstring::~wstring(lpsz, v5, v6);
  }
  else
  {
    *a2 = 0;
  }
  std::string::~string(v10);
  return a2;
}

```

## disassembly

```asm
0x180016e28  push    rbx
0x180016e2a  sub     rsp, 70h
0x180016e2e  mov     rax, cs:__security_cookie
0x180016e35  xor     rax, rsp
0x180016e38  mov     [rsp+78h+var_10], rax
0x180016e3d  mov     rbx, rdx
0x180016e40  xorps   xmm0, xmm0
0x180016e43  movups  xmmword ptr [rdx], xmm0
0x180016e46  lea     rdx, [rsp+78h+var_30]
0x180016e4b  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<std::string,std::string,0>(void)
0x180016e50  nop
0x180016e51  cmp     [rsp+78h+var_20], 0
0x180016e57  jnz     short loc_180016E62
0x180016e59  xorps   xmm0, xmm0
0x180016e5c  movdqu  xmmword ptr [rbx], xmm0
0x180016e60  jmp     short loc_180016EA0
0x180016e62  lea     rdx, [rsp+78h+var_30]
0x180016e67  lea     rcx, [rsp+78h+lpsz]
0x180016e6c  call    _anonymous_namespace___Utf8ToUtf16
0x180016e71  nop
0x180016e72  lea     rcx, [rsp+78h+lpsz]
0x180016e77  cmp     [rsp+78h+var_38], 7
0x180016e7d  cmova   rcx, [rsp+78h+lpsz]; lpsz
0x180016e83  mov     rdx, rbx; pclsid
0x180016e86  call    cs:__imp_CLSIDFromString
0x180016e8c  mov     rcx, [rsp+78h]; this
0x180016e91  test    eax, eax
0x180016e93  js      short loc_180016EC0
0x180016e95  lea     rcx, [rsp+78h+lpsz]
0x180016e9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016e9f  nop
0x180016ea0  lea     rcx, [rsp+78h+var_30]
0x180016ea5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016eaa  mov     rax, rbx
0x180016ead  mov     rcx, [rsp+78h+var_10]
0x180016eb2  xor     rcx, rsp; StackCookie
0x180016eb5  call    __security_check_cookie
0x180016eba  add     rsp, 70h
0x180016ebe  pop     rbx
0x180016ebf  retn
0x180016ec0  mov     r9d, eax; char *
0x180016ec3  mov     edx, 84h; void *
0x180016ec8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
