# TracingSessionHelper::FindAndAddEtlsMatchingPattern(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18010e75c`
- end: `0x18010e955`
- name: `?FindAndAddEtlsMatchingPattern@TracingSessionHelper@@CAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18010e95c`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e66dc`
- `0x1800ef134`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f09d8`
- `0x1800f7240`
- `0x180106d68`
- `0x1801070d4`
- `0x180107120`
- `0x18010e75c`
- `0x180111324`
- `0x180111360`
- `0x180111474`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010e900`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010e900`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010e852`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010e852`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18010e8c2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18010e8c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TracingSessionHelper::FindAndAddEtlsMatchingPattern(char *a1, __int64 a2)
{
  __int64 v3; // rbx
  const WCHAR *v4; // rax
  char *FirstFileW; // rbx
  size_t v6; // rdi
  int v7; // eax
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rax
  const WCHAR *v11; // rax
  HRESULT v12; // eax
  int N; // [rsp+20h] [rbp-E0h]
  char *v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE Src[16]; // [rsp+38h] [rbp-C8h] BYREF
  int v17[6]; // [rsp+48h] [rbp-B8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v19[4]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  v15 = a1;
  v19[0] = 6619182;
  v19[1] = 7078004;
  v19[2] = 46;
  std::wstring::wstring(Src, a1);
  v3 = -1;
  if ( std::wstring::find(Src, v19, 0) == -1 )
  {
    std::vector<std::wstring>::emplace_back<unsigned short const * &>(a2, &v15);
  }
  else
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    do
      ++v3;
    while ( *((_WORD *)v19 + v3) );
    std::wstring::replace(Src);
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    FirstFileW = (char *)FindFirstFileW(v4, &FindFileData);
    v15 = FirstFileW;
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v6 = std::_WChar_traits<unsigned short>::length(L"\\");
      v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      v10 = std::_Traits_find_last_of<std::char_traits<unsigned short>>(v7, v17[0], v8, v9, v6);
      std::wstring::erase(Src, v10);
      do
      {
        v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        v12 = PathCchCombine(pszPathOut, 0x104u, v11, FindFileData.cFileName);
        if ( v12 >= 0 )
          std::vector<std::wstring>::emplace_back<unsigned short (&)[260]>(a2, pszPathOut);
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x43,
            (unsigned int)"onecoreuap\\internal\\analog\\inc\\tracingsessionhelper.h",
            (const char *)(unsigned int)v12,
            N);
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v15);
  }
  return std::wstring::_Tidy_deallocate(Src);
}

```

## disassembly

```asm
0x18010e75c  mov     [rsp-8+arg_10], rbx
0x18010e761  mov     [rsp-8+arg_18], rsi
0x18010e766  push    rbp
0x18010e767  push    rdi
0x18010e768  push    r14
0x18010e76a  lea     rbp, [rsp-3E0h]
0x18010e772  sub     rsp, 4E0h
0x18010e779  mov     rax, cs:__security_cookie
0x18010e780  xor     rax, rsp
0x18010e783  mov     [rbp+3F0h+var_20], rax
0x18010e78a  mov     rsi, rdx
0x18010e78d  mov     [rsp+4F0h+var_4C0], rcx
0x18010e792  mov     [rbp+3F0h+var_240], 65002Eh
0x18010e79c  mov     [rbp+3F0h+var_23C], 6C0074h
0x18010e7a6  mov     [rbp+3F0h+var_238], 2Eh ; '.'
0x18010e7b0  xor     r14d, r14d
0x18010e7b3  mov     rdx, rcx
0x18010e7b6  lea     rcx, [rsp+4F0h+Src]
0x18010e7bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e7c0  nop
0x18010e7c1  xor     r8d, r8d
0x18010e7c4  lea     rdx, [rbp+3F0h+var_240]
0x18010e7cb  lea     rcx, [rsp+4F0h+Src]
0x18010e7d0  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18010e7d5  mov     rdi, rax
0x18010e7d8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18010e7dc  cmp     rax, rbx
0x18010e7df  jz      loc_18010E916
0x18010e7e5  lea     rcx, [rsp+4F0h+Src]
0x18010e7ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010e7ef  mov     rcx, qword ptr [rsp+4F0h+var_4A8]
0x18010e7f4  lea     r8, [rax+rcx*2]
0x18010e7f8  lea     rcx, [rax+rdi*2]
0x18010e7fc  lea     rdx, [rbp+3F0h+var_240]
0x18010e803  inc     rbx
0x18010e806  cmp     [rdx+rbx*2], r14w
0x18010e80b  jnz     short loc_18010E803
0x18010e80d  lea     rdx, [rcx+rbx*2]
0x18010e811  sub     r8, rdx
0x18010e814  sar     r8, 1
0x18010e817  sub     rdx, rax
0x18010e81a  sar     rdx, 1
0x18010e81d  lea     r9, Delimiter; "*"
0x18010e824  lea     rcx, [rsp+4F0h+Src]; Src
0x18010e829  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0QEBG@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const * const)
0x18010e82e  xor     edx, edx; Val
0x18010e830  mov     r8d, 250h; Size
0x18010e836  lea     rcx, [rsp+4F0h+FindFileData]; void *
0x18010e83b  call    memset_0
0x18010e840  lea     rcx, [rsp+4F0h+Src]
0x18010e845  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010e84a  mov     rcx, rax; lpFileName
0x18010e84d  lea     rdx, [rsp+4F0h+FindFileData]; lpFindFileData
0x18010e852  call    cs:__imp_FindFirstFileW
0x18010e858  mov     rbx, rax
0x18010e85b  mov     [rsp+4F0h+var_4C0], rax
0x18010e860  dec     rax
0x18010e863  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010e867  ja      loc_18010E90A
0x18010e86d  lea     rcx, psz; "\\"
0x18010e874  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18010e879  mov     rdi, rax
0x18010e87c  lea     rcx, [rsp+4F0h+Src]
0x18010e881  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010e886  mov     rcx, rax; int
0x18010e889  mov     qword ptr [rsp+4F0h+N], rdi; int
0x18010e88e  mov     rdx, qword ptr [rsp+4F0h+var_4A8]; int
0x18010e893  call    ??$_Traits_find_last_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18010e898  mov     rdx, rax
0x18010e89b  lea     rcx, [rsp+4F0h+Src]
0x18010e8a0  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x18010e8a5  lea     rcx, [rsp+4F0h+Src]
0x18010e8aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010e8af  mov     r8, rax; pszPathIn
0x18010e8b2  lea     r9, [rbp+3F0h+FindFileData.cFileName]; pszMore
0x18010e8b6  mov     edx, 104h; cchPathOut
0x18010e8bb  lea     rcx, [rbp+3F0h+pszPathOut]; pszPathOut
0x18010e8c2  call    cs:__imp_PathCchCombine
0x18010e8c8  mov     rcx, [rbp+3F8h]; this
0x18010e8cf  test    eax, eax
0x18010e8d1  jns     short loc_18010E8E9
0x18010e8d3  mov     r9d, eax; char *
0x18010e8d6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\analog\\inc\\trac"...
0x18010e8dd  mov     edx, 43h ; 'C'; void *
0x18010e8e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010e8e7  jmp     short loc_18010E8F8
0x18010e8e9  lea     rdx, [rbp+3F0h+pszPathOut]
0x18010e8f0  mov     rcx, rsi
0x18010e8f3  call    ??$emplace_back@AEAY0BAE@G@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY0BAE@G@Z; std::vector<std::wstring>::emplace_back<ushort (&)[260]>(ushort (&)[260])
0x18010e8f8  lea     rdx, [rsp+4F0h+FindFileData]; lpFindFileData
0x18010e8fd  mov     rcx, rbx; hFindFile
0x18010e900  call    cs:__imp_FindNextFileW
0x18010e906  test    eax, eax
0x18010e908  jnz     short loc_18010E8A5
0x18010e90a  lea     rcx, [rsp+4F0h+var_4C0]
0x18010e90f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18010e914  jmp     short loc_18010E924
0x18010e916  lea     rdx, [rsp+4F0h+var_4C0]
0x18010e91b  mov     rcx, rsi
0x18010e91e  call    ??$emplace_back@AEAPEBG@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAPEBG@Z; std::vector<std::wstring>::emplace_back<ushort const * &>(ushort const * &)
0x18010e923  nop
0x18010e924  lea     rcx, [rsp+4F0h+Src]
0x18010e929  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e92e  mov     rcx, [rbp+3F0h+var_20]
0x18010e935  xor     rcx, rsp; StackCookie
0x18010e938  call    __security_check_cookie
0x18010e93d  lea     r11, [rsp+4F0h+var_10]
0x18010e945  mov     rbx, [r11+30h]
0x18010e949  mov     rsi, [r11+38h]
0x18010e94d  mov     rsp, r11
0x18010e950  pop     r14
0x18010e952  pop     rdi
0x18010e953  pop     rbp
0x18010e954  retn
```
