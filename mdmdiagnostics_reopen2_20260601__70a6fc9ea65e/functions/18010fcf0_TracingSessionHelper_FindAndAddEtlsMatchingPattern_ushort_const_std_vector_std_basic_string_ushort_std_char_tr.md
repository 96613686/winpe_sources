# TracingSessionHelper::FindAndAddEtlsMatchingPattern(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18010fcf0`
- end: `0x18010fefc`
- name: `?FindAndAddEtlsMatchingPattern@TracingSessionHelper@@CAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18010ff04`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e68b0`
- `0x1800ef868`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f1250`
- `0x1800f809c`
- `0x18010803c`
- `0x1801083a8`
- `0x1801083f4`
- `0x18010fcf0`
- `0x1801127c4`
- `0x180112804`
- `0x18011291c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010fea0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010fea0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010fde6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010fde6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18010fe5c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18010fe5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TracingSessionHelper::FindAndAddEtlsMatchingPattern(char *a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  const WCHAR *v5; // rax
  char *FirstFileW; // rbx
  size_t v7; // rdi
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rax
  const WCHAR *v12; // rax
  HRESULT v13; // eax
  int N; // [rsp+20h] [rbp-E0h]
  char *v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[16]; // [rsp+38h] [rbp-C8h] BYREF
  int v18[6]; // [rsp+48h] [rbp-B8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v20[4]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  v16 = a1;
  v20[0] = 6619182;
  v20[1] = 7078004;
  v20[2] = 46;
  std::wstring::wstring(v17, a1);
  v3 = std::wstring::find(v17, v20, 0);
  v4 = -1;
  if ( v3 == -1 )
  {
    std::vector<std::wstring>::emplace_back<unsigned short const * &>(a2, &v16);
  }
  else
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    do
      ++v4;
    while ( *((_WORD *)v20 + v4) );
    std::wstring::replace(v17, (2 * v3 + 2 * v4) >> 1, (2LL * *(_QWORD *)v18 - (2 * v3 + 2 * v4)) >> 1, L"*");
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    FirstFileW = (char *)FindFirstFileW(v5, &FindFileData);
    v16 = FirstFileW;
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v7 = std::_WChar_traits<unsigned short>::length(L"\\");
      v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      v11 = std::_Traits_find_last_of<std::char_traits<unsigned short>>(v8, v18[0], v9, v10, v7);
      std::wstring::erase(v17, v11);
      do
      {
        v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
        v13 = PathCchCombine(pszPathOut, 0x104u, v12, FindFileData.cFileName);
        if ( v13 >= 0 )
          std::vector<std::wstring>::emplace_back<unsigned short (&)[260]>(a2, pszPathOut);
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x43,
            (unsigned int)"onecoreuap\\internal\\analog\\inc\\tracingsessionhelper.h",
            (const char *)(unsigned int)v13,
            N);
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v16);
  }
  return std::wstring::_Tidy_deallocate(v17);
}

```

## disassembly

```asm
0x18010fcf0  mov     [rsp-8+arg_10], rbx
0x18010fcf5  mov     [rsp-8+arg_18], rsi
0x18010fcfa  push    rbp
0x18010fcfb  push    rdi
0x18010fcfc  push    r14
0x18010fcfe  lea     rbp, [rsp-3E0h]
0x18010fd06  sub     rsp, 4E0h
0x18010fd0d  mov     rax, cs:__security_cookie
0x18010fd14  xor     rax, rsp
0x18010fd17  mov     [rbp+3F0h+var_20], rax
0x18010fd1e  mov     rsi, rdx
0x18010fd21  mov     [rsp+4F0h+var_4C0], rcx
0x18010fd26  mov     [rbp+3F0h+var_240], 65002Eh
0x18010fd30  mov     [rbp+3F0h+var_23C], 6C0074h
0x18010fd3a  mov     [rbp+3F0h+var_238], 2Eh ; '.'
0x18010fd44  xor     r14d, r14d
0x18010fd47  mov     rdx, rcx
0x18010fd4a  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fd4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010fd54  nop
0x18010fd55  xor     r8d, r8d
0x18010fd58  lea     rdx, [rbp+3F0h+var_240]
0x18010fd5f  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fd64  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18010fd69  mov     rdi, rax
0x18010fd6c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18010fd70  cmp     rax, rbx
0x18010fd73  jz      loc_18010FEBC
0x18010fd79  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fd7e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010fd83  mov     rcx, qword ptr [rsp+4F0h+var_4A8]
0x18010fd88  lea     r8, [rax+rcx*2]
0x18010fd8c  lea     rcx, [rax+rdi*2]
0x18010fd90  lea     rdx, [rbp+3F0h+var_240]
0x18010fd97  inc     rbx
0x18010fd9a  cmp     [rdx+rbx*2], r14w
0x18010fd9f  jnz     short loc_18010FD97
0x18010fda1  lea     rdx, [rcx+rbx*2]
0x18010fda5  sub     r8, rdx
0x18010fda8  sar     r8, 1
0x18010fdab  sub     rdx, rax
0x18010fdae  sar     rdx, 1
0x18010fdb1  lea     r9, Delimiter; "*"
0x18010fdb8  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fdbd  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0QEBG@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const * const)
0x18010fdc2  xor     edx, edx; Val
0x18010fdc4  mov     r8d, 250h; Size
0x18010fdca  lea     rcx, [rsp+4F0h+FindFileData]; void *
0x18010fdcf  call    memset_0
0x18010fdd4  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fdd9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010fdde  mov     rcx, rax; lpFileName
0x18010fde1  lea     rdx, [rsp+4F0h+FindFileData]; lpFindFileData
0x18010fde6  call    cs:__imp_FindFirstFileW
0x18010fded  nop     dword ptr [rax+rax+00h]
0x18010fdf2  mov     rbx, rax
0x18010fdf5  mov     [rsp+4F0h+var_4C0], rax
0x18010fdfa  dec     rax
0x18010fdfd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010fe01  ja      loc_18010FEB0
0x18010fe07  lea     rcx, psz; "\\"
0x18010fe0e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18010fe13  mov     rdi, rax
0x18010fe16  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fe1b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010fe20  mov     rcx, rax; int
0x18010fe23  mov     qword ptr [rsp+4F0h+N], rdi; int
0x18010fe28  mov     rdx, qword ptr [rsp+4F0h+var_4A8]; int
0x18010fe2d  call    ??$_Traits_find_last_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18010fe32  mov     rdx, rax
0x18010fe35  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fe3a  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x18010fe3f  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fe44  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010fe49  mov     r8, rax; pszPathIn
0x18010fe4c  lea     r9, [rbp+3F0h+FindFileData.cFileName]; pszMore
0x18010fe50  mov     edx, 104h; cchPathOut
0x18010fe55  lea     rcx, [rbp+3F0h+pszPathOut]; pszPathOut
0x18010fe5c  call    cs:__imp_PathCchCombine
0x18010fe63  nop     dword ptr [rax+rax+00h]
0x18010fe68  mov     rcx, [rbp+3F8h]; this
0x18010fe6f  test    eax, eax
0x18010fe71  jns     short loc_18010FE89
0x18010fe73  mov     r9d, eax; char *
0x18010fe76  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\analog\\inc\\trac"...
0x18010fe7d  mov     edx, 43h ; 'C'; void *
0x18010fe82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010fe87  jmp     short loc_18010FE98
0x18010fe89  lea     rdx, [rbp+3F0h+pszPathOut]
0x18010fe90  mov     rcx, rsi
0x18010fe93  call    ??$emplace_back@AEAY0BAE@G@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY0BAE@G@Z; std::vector<std::wstring>::emplace_back<ushort (&)[260]>(ushort (&)[260])
0x18010fe98  lea     rdx, [rsp+4F0h+FindFileData]; lpFindFileData
0x18010fe9d  mov     rcx, rbx; hFindFile
0x18010fea0  call    cs:__imp_FindNextFileW
0x18010fea7  nop     dword ptr [rax+rax+00h]
0x18010feac  test    eax, eax
0x18010feae  jnz     short loc_18010FE3F
0x18010feb0  lea     rcx, [rsp+4F0h+var_4C0]
0x18010feb5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18010feba  jmp     short loc_18010FECA
0x18010febc  lea     rdx, [rsp+4F0h+var_4C0]
0x18010fec1  mov     rcx, rsi
0x18010fec4  call    ??$emplace_back@AEAPEBG@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAPEBG@Z; std::vector<std::wstring>::emplace_back<ushort const * &>(ushort const * &)
0x18010fec9  nop
0x18010feca  lea     rcx, [rsp+4F0h+var_4B8]
0x18010fecf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010fed4  mov     rcx, [rbp+3F0h+var_20]
0x18010fedb  xor     rcx, rsp; StackCookie
0x18010fede  call    __security_check_cookie
0x18010fee3  lea     r11, [rsp+4F0h+var_10]
0x18010feeb  mov     rbx, [r11+30h]
0x18010feef  mov     rsi, [r11+38h]
0x18010fef3  mov     rsp, r11
0x18010fef6  pop     r14
0x18010fef8  pop     rdi
0x18010fef9  pop     rbp
0x18010fefa  retn
```
