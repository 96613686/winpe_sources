# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>(_GUID const &)

- ea: `0x180012910`
- end: `0x180012a34`
- name: `??$?0AEBU_GUID@@U0@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@AEBU_GUID@@@Z`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001fb28`
- `0x18002b264`

## callees

- `0x180002490`
- `0x18000289c`
- `0x180008594`
- `0x180008a68`
- `0x180008ad0`
- `0x180012910`
- `0x180021000`
- `0x18002229c`
- `0x180022cf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001294d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001294d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
        char *a1,
        const IID *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // r8d
  __int64 v5; // rbx
  _QWORD *v6; // rcx
  char v7; // dl
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  LPOLESTR lpsz; // [rsp+20h] [rbp-60h] BYREF
  char v13; // [rsp+28h] [rbp-58h]
  __int64 v14; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  *a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  lpsz = 0;
  v3 = StringFromCLSID(a2, &lpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x76, v4, (const char *)(unsigned int)v3, (int)lpsz);
  std::wstring::wstring(v15, lpsz);
  v5 = anonymous_namespace_::Utf16ToUtf8(v16, v15);
  v6 = operator new(0x20u);
  *(_OWORD *)v6 = 0;
  v6[2] = 0;
  v6[3] = 0;
  *(_OWORD *)v6 = *(_OWORD *)v5;
  *((_OWORD *)v6 + 1) = *(_OWORD *)(v5 + 16);
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 15;
  *(_BYTE *)v5 = 0;
  v7 = *a1;
  *a1 = 3;
  v13 = v7;
  v8 = *((_QWORD *)a1 + 1);
  *((_QWORD *)a1 + 1) = v6;
  v14 = v8;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v14);
  std::string::~string(v16);
  std::wstring::~wstring(v15, v9, v10);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return a1;
}

```

## disassembly

```asm
0x180012910  mov     [rsp-8+arg_10], rbx
0x180012915  mov     [rsp-8+arg_18], rdi
0x18001291a  push    rbp
0x18001291b  mov     rbp, rsp
0x18001291e  sub     rsp, 80h
0x180012925  mov     rax, cs:__security_cookie
0x18001292c  xor     rax, rsp
0x18001292f  mov     [rbp+var_8], rax
0x180012933  mov     rax, rdx
0x180012936  mov     rdi, rcx
0x180012939  mov     byte ptr [rcx], 0
0x18001293c  xor     ecx, ecx
0x18001293e  mov     [rdi+8], rcx
0x180012942  mov     [rbp+lpsz], rcx
0x180012946  lea     rdx, [rbp+lpsz]; lplpsz
0x18001294a  mov     rcx, rax; rclsid
0x18001294d  call    cs:__imp_StringFromCLSID
0x180012953  mov     rcx, [rbp+8]; this
0x180012957  test    eax, eax
0x180012959  js      loc_180012A26
0x18001295f  mov     rdx, [rbp+lpsz]
0x180012963  lea     rcx, [rbp+var_48]
0x180012967  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001296c  nop
0x18001296d  lea     rdx, [rbp+var_48]
0x180012971  lea     rcx, [rbp+var_28]
0x180012975  call    _anonymous_namespace___Utf16ToUtf8
0x18001297a  mov     rbx, rax
0x18001297d  mov     ecx, 20h ; ' '; Size
0x180012982  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012987  mov     rcx, rax
0x18001298a  xorps   xmm0, xmm0
0x18001298d  movups  xmmword ptr [rax], xmm0
0x180012990  mov     qword ptr [rax+10h], 0
0x180012998  mov     qword ptr [rax+18h], 0
0x1800129a0  movups  xmm0, xmmword ptr [rbx]
0x1800129a3  movups  xmmword ptr [rax], xmm0
0x1800129a6  movups  xmm1, xmmword ptr [rbx+10h]
0x1800129aa  movups  xmmword ptr [rax+10h], xmm1
0x1800129ae  mov     qword ptr [rbx+10h], 0
0x1800129b6  mov     qword ptr [rbx+18h], 0Fh
0x1800129be  mov     byte ptr [rbx], 0
0x1800129c1  mov     dl, [rdi]
0x1800129c3  mov     byte ptr [rdi], 3
0x1800129c6  mov     [rbp+var_58], dl
0x1800129c9  mov     rax, [rdi+8]
0x1800129cd  mov     [rdi+8], rcx
0x1800129d1  mov     [rbp+var_50], rax
0x1800129d5  lea     rcx, [rbp+var_50]
0x1800129d9  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800129de  nop
0x1800129df  lea     rcx, [rbp+var_28]
0x1800129e3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800129e8  nop
0x1800129e9  lea     rcx, [rbp+var_48]
0x1800129ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800129f2  nop
0x1800129f3  mov     rcx, [rbp+lpsz]; pv
0x1800129f7  test    rcx, rcx
0x1800129fa  jz      short loc_180012A02
0x1800129fc  call    cs:__imp_CoTaskMemFree
0x180012a02  mov     rax, rdi
0x180012a05  mov     rcx, [rbp+var_8]
0x180012a09  xor     rcx, rsp; StackCookie
0x180012a0c  call    __security_check_cookie
0x180012a11  lea     r11, [rsp+80h+var_s0]
0x180012a19  mov     rbx, [r11+20h]
0x180012a1d  mov     rdi, [r11+28h]
0x180012a21  mov     rsp, r11
0x180012a24  pop     rbp
0x180012a25  retn
0x180012a26  mov     r9d, eax; char *
0x180012a29  mov     edx, 76h ; 'v'; void *
0x180012a2e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
