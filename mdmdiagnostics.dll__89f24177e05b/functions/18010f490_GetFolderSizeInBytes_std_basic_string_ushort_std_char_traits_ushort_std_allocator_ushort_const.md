# GetFolderSizeInBytes(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18010f490`
- end: `0x18010f6a3`
- name: `?GetFolderSizeInBytes@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `531`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010cf98`
- `0x18010f490`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800ef134`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1800f7240`
- `0x1800f7c2c`
- `0x18010438c`
- `0x18010f490`
- `0x18011150c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010f651`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010f651`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18010f52c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18010f52c`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18010f5e2`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18010f5e2`

## string_xrefs

- `0x18010f5f6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetFolderSizeInBytes(__int64 a1)
{
  __int64 v2; // rax
  const WCHAR *v3; // rax
  HANDLE FirstFile; // rax
  const unsigned __int16 *v5; // rdx
  __int64 v6; // rsi
  HANDLE v7; // r14
  __int64 v8; // rcx
  const WCHAR *v9; // rdi
  __int64 v10; // rbx
  WCHAR *v11; // rax
  HRESULT v12; // eax
  int lpSearchFilter; // [rsp+20h] [rbp-E0h]
  HANDLE hFindFile[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h]
  _BYTE v18[32]; // [rsp+60h] [rbp-A0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  std::wstring::wstring(v18, v2);
  std::wstring::append(v18, L"\\*");
  hFindFile[0] = (HANDLE)-1LL;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
  FirstFile = FindFirstFileExW(v3, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 4u);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::reset(
    hFindFile,
    FirstFile);
  v6 = 0;
  v7 = hFindFile[0];
  if ( (unsigned __int64)hFindFile[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    do
    {
      if ( !wil::path_is_dot_or_dotdot((wil *)FindFileData.cFileName, v5)
        && (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          std::wstring::wstring(v16);
          v8 = -1;
          do
            ++v8;
          while ( FindFileData.cFileName[v8] );
          std::wstring::resize(v16, v8 + *(_QWORD *)(a1 + 16) + 2LL, 0);
          v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
          v10 = v17;
          v11 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
          v12 = PathCchCombineEx(v11, v10 + 1, v9, FindFileData.cFileName, 1u);
          if ( v12 >= 0 )
          {
            std::wstring::resize(v16, v17 - 1, 0);
            v6 += GetFolderSizeInBytes(v16);
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8F7,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
              (const char *)(unsigned int)v12,
              lpSearchFilter);
          }
          std::wstring::_Tidy_deallocate(v16);
        }
        else
        {
          hFindFile[1] = (HANDLE)__PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
          v6 += __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
        }
      }
    }
    while ( FindNextFileW(v7, &FindFileData) );
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(hFindFile);
  std::wstring::_Tidy_deallocate(v18);
  return v6;
}

```

## disassembly

```asm
0x18010f490  mov     [rsp-8+arg_8], rbx
0x18010f495  mov     [rsp-8+arg_10], rsi
0x18010f49a  push    rbp
0x18010f49b  push    rdi
0x18010f49c  push    r12
0x18010f49e  push    r14
0x18010f4a0  push    r15
0x18010f4a2  lea     rbp, [rsp-1E0h]
0x18010f4aa  sub     rsp, 2E0h
0x18010f4b1  mov     rax, cs:__security_cookie
0x18010f4b8  xor     rax, rsp
0x18010f4bb  mov     [rbp+200h+var_30], rax
0x18010f4c2  mov     r15, rcx
0x18010f4c5  xor     edx, edx; Val
0x18010f4c7  mov     r8d, 250h; Size
0x18010f4cd  lea     rcx, [rbp+200h+FindFileData]; void *
0x18010f4d1  call    memset_0
0x18010f4d6  mov     rcx, r15
0x18010f4d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f4de  mov     rdx, rax
0x18010f4e1  lea     rcx, [rsp+300h+var_2A0]
0x18010f4e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010f4eb  nop
0x18010f4ec  lea     rdx, asc_1801D3550; "\\*"
0x18010f4f3  lea     rcx, [rsp+300h+var_2A0]
0x18010f4f8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010f4fd  mov     [rsp+300h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18010f506  lea     rcx, [rsp+300h+var_2A0]
0x18010f50b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f510  mov     rcx, rax; lpFileName
0x18010f513  mov     [rsp+300h+dwAdditionalFlags], 4; dwAdditionalFlags
0x18010f51b  xor     r12d, r12d
0x18010f51e  mov     [rsp+300h+lpSearchFilter], r12; lpSearchFilter
0x18010f523  xor     r9d, r9d; fSearchOp
0x18010f526  lea     r8, [rbp+200h+FindFileData]; lpFindFileData
0x18010f52a  xor     edx, edx; fInfoLevelId
0x18010f52c  call    cs:__imp_FindFirstFileExW
0x18010f532  mov     rdx, rax
0x18010f535  lea     rcx, [rsp+300h+hFindFile]
0x18010f53a  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::reset(void *)
0x18010f53f  mov     esi, r12d
0x18010f542  mov     r14, [rsp+300h+hFindFile]
0x18010f547  lea     rax, [r14-1]
0x18010f54b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010f54f  ja      loc_18010F660
0x18010f555  lea     rcx, [rbp+200h+pszMore]; this
0x18010f559  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x18010f55e  test    al, al
0x18010f560  jnz     loc_18010F64A
0x18010f566  test    [rbp+200h+FindFileData], 400h
0x18010f56d  jnz     loc_18010F64A
0x18010f573  test    byte ptr [rbp+200h+FindFileData], 10h
0x18010f577  jz      loc_18010F637
0x18010f57d  lea     rcx, [rsp+300h+var_2C0]
0x18010f582  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010f587  nop
0x18010f588  lea     rax, [rbp+200h+pszMore]
0x18010f58c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18010f590  inc     rcx
0x18010f593  cmp     [rax+rcx*2], r12w
0x18010f598  jnz     short loc_18010F590
0x18010f59a  xor     r8d, r8d
0x18010f59d  mov     rdx, [r15+10h]
0x18010f5a1  add     rdx, 2
0x18010f5a5  add     rdx, rcx
0x18010f5a8  lea     rcx, [rsp+300h+var_2C0]
0x18010f5ad  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18010f5b2  mov     rcx, r15
0x18010f5b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f5ba  mov     rdi, rax
0x18010f5bd  mov     rbx, [rsp+300h+var_2B0]
0x18010f5c2  lea     rcx, [rsp+300h+var_2C0]
0x18010f5c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f5cc  mov     rcx, rax; pszPathOut
0x18010f5cf  mov     dword ptr [rsp+300h+lpSearchFilter], 1; int
0x18010f5d7  lea     r9, [rbp+200h+pszMore]; pszMore
0x18010f5db  mov     r8, rdi; pszPathIn
0x18010f5de  lea     rdx, [rbx+1]; cchPathOut
0x18010f5e2  call    cs:__imp_PathCchCombineEx
0x18010f5e8  mov     rcx, [rbp+208h]; this
0x18010f5ef  test    eax, eax
0x18010f5f1  jns     short loc_18010F609
0x18010f5f3  mov     r9d, eax; char *
0x18010f5f6  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f5fd  mov     edx, 8F7h; void *
0x18010f602  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010f607  jmp     short loc_18010F62B
0x18010f609  xor     r8d, r8d
0x18010f60c  mov     rdx, [rsp+300h+var_2B0]
0x18010f611  dec     rdx
0x18010f614  lea     rcx, [rsp+300h+var_2C0]
0x18010f619  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18010f61e  lea     rcx, [rsp+300h+var_2C0]
0x18010f623  call    ?GetFolderSizeInBytes@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetFolderSizeInBytes(std::wstring const &)
0x18010f628  add     rsi, rax
0x18010f62b  lea     rcx, [rsp+300h+var_2C0]
0x18010f630  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f635  jmp     short loc_18010F64A
0x18010f637  mov     eax, [rbp+200h+var_264]
0x18010f63a  mov     dword ptr [rsp+300h+var_2C8+4], eax
0x18010f63e  mov     eax, [rbp+200h+var_260]
0x18010f641  mov     dword ptr [rsp+300h+var_2C8], eax
0x18010f645  add     rsi, [rsp+300h+var_2C8]
0x18010f64a  lea     rdx, [rbp+200h+FindFileData]; lpFindFileData
0x18010f64e  mov     rcx, r14; hFindFile
0x18010f651  call    cs:__imp_FindNextFileW
0x18010f657  cmp     eax, 1
0x18010f65a  jz      loc_18010F555
0x18010f660  lea     rcx, [rsp+300h+hFindFile]
0x18010f665  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18010f66a  nop
0x18010f66b  lea     rcx, [rsp+300h+var_2A0]
0x18010f670  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f675  mov     rax, rsi
0x18010f678  mov     rcx, [rbp+200h+var_30]
0x18010f67f  xor     rcx, rsp; StackCookie
0x18010f682  call    __security_check_cookie
0x18010f687  lea     r11, [rsp+300h+var_20]
0x18010f68f  mov     rbx, [r11+38h]
0x18010f693  mov     rsi, [r11+40h]
0x18010f697  mov     rsp, r11
0x18010f69a  pop     r15
0x18010f69c  pop     r14
0x18010f69e  pop     r12
0x18010f6a0  pop     rdi
0x18010f6a1  pop     rbp
0x18010f6a2  retn
```
