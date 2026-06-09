# GetFolderSizeInBytes(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180110aa8`
- end: `0x180110cce`
- name: `?GetFolderSizeInBytes@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `550`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010e480`
- `0x180110aa8`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800ef868`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x1800f809c`
- `0x1800f8b0c`
- `0x1801055a4`
- `0x180110aa8`
- `0x1801129e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180110c75`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180110c75`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180110b44`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180110b44`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180110c00`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180110c00`

## string_xrefs

- `0x180110c1a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

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
              (void *)0x8CE,
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
0x180110aa8  mov     [rsp-8+arg_8], rbx
0x180110aad  mov     [rsp-8+arg_10], rsi
0x180110ab2  push    rbp
0x180110ab3  push    rdi
0x180110ab4  push    r12
0x180110ab6  push    r14
0x180110ab8  push    r15
0x180110aba  lea     rbp, [rsp-1E0h]
0x180110ac2  sub     rsp, 2E0h
0x180110ac9  mov     rax, cs:__security_cookie
0x180110ad0  xor     rax, rsp
0x180110ad3  mov     [rbp+200h+var_30], rax
0x180110ada  mov     r15, rcx
0x180110add  xor     edx, edx; Val
0x180110adf  mov     r8d, 250h; Size
0x180110ae5  lea     rcx, [rbp+200h+FindFileData]; void *
0x180110ae9  call    memset_0
0x180110aee  mov     rcx, r15
0x180110af1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180110af6  mov     rdx, rax
0x180110af9  lea     rcx, [rsp+300h+var_2A0]
0x180110afe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180110b03  nop
0x180110b04  lea     rdx, asc_1801D5540; "\\*"
0x180110b0b  lea     rcx, [rsp+300h+var_2A0]
0x180110b10  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180110b15  mov     [rsp+300h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x180110b1e  lea     rcx, [rsp+300h+var_2A0]
0x180110b23  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180110b28  mov     rcx, rax; lpFileName
0x180110b2b  mov     [rsp+300h+dwAdditionalFlags], 4; dwAdditionalFlags
0x180110b33  xor     r12d, r12d
0x180110b36  mov     [rsp+300h+lpSearchFilter], r12; lpSearchFilter
0x180110b3b  xor     r9d, r9d; fSearchOp
0x180110b3e  lea     r8, [rbp+200h+FindFileData]; lpFindFileData
0x180110b42  xor     edx, edx; fInfoLevelId
0x180110b44  call    cs:__imp_FindFirstFileExW
0x180110b4b  nop     dword ptr [rax+rax+00h]
0x180110b50  mov     rdx, rax
0x180110b53  lea     rcx, [rsp+300h+hFindFile]
0x180110b58  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::reset(void *)
0x180110b5d  mov     esi, r12d
0x180110b60  mov     r14, [rsp+300h+hFindFile]
0x180110b65  lea     rax, [r14-1]
0x180110b69  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180110b6d  ja      loc_180110C8A
0x180110b73  lea     rcx, [rbp+200h+pszMore]; this
0x180110b77  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x180110b7c  test    al, al
0x180110b7e  jnz     loc_180110C6E
0x180110b84  test    [rbp+200h+FindFileData], 400h
0x180110b8b  jnz     loc_180110C6E
0x180110b91  test    byte ptr [rbp+200h+FindFileData], 10h
0x180110b95  jz      loc_180110C5B
0x180110b9b  lea     rcx, [rsp+300h+var_2C0]
0x180110ba0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180110ba5  nop
0x180110ba6  lea     rax, [rbp+200h+pszMore]
0x180110baa  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180110bae  inc     rcx
0x180110bb1  cmp     [rax+rcx*2], r12w
0x180110bb6  jnz     short loc_180110BAE
0x180110bb8  xor     r8d, r8d
0x180110bbb  mov     rdx, [r15+10h]
0x180110bbf  add     rdx, 2
0x180110bc3  add     rdx, rcx
0x180110bc6  lea     rcx, [rsp+300h+var_2C0]
0x180110bcb  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180110bd0  mov     rcx, r15
0x180110bd3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180110bd8  mov     rdi, rax
0x180110bdb  mov     rbx, [rsp+300h+var_2B0]
0x180110be0  lea     rcx, [rsp+300h+var_2C0]
0x180110be5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180110bea  mov     rcx, rax; pszPathOut
0x180110bed  mov     dword ptr [rsp+300h+lpSearchFilter], 1; int
0x180110bf5  lea     r9, [rbp+200h+pszMore]; pszMore
0x180110bf9  mov     r8, rdi; pszPathIn
0x180110bfc  lea     rdx, [rbx+1]; cchPathOut
0x180110c00  call    cs:__imp_PathCchCombineEx
0x180110c07  nop     dword ptr [rax+rax+00h]
0x180110c0c  mov     rcx, [rbp+208h]; this
0x180110c13  test    eax, eax
0x180110c15  jns     short loc_180110C2D
0x180110c17  mov     r9d, eax; char *
0x180110c1a  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180110c21  mov     edx, 8CEh; void *
0x180110c26  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180110c2b  jmp     short loc_180110C4F
0x180110c2d  xor     r8d, r8d
0x180110c30  mov     rdx, [rsp+300h+var_2B0]
0x180110c35  dec     rdx
0x180110c38  lea     rcx, [rsp+300h+var_2C0]
0x180110c3d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180110c42  lea     rcx, [rsp+300h+var_2C0]
0x180110c47  call    ?GetFolderSizeInBytes@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetFolderSizeInBytes(std::wstring const &)
0x180110c4c  add     rsi, rax
0x180110c4f  lea     rcx, [rsp+300h+var_2C0]
0x180110c54  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180110c59  jmp     short loc_180110C6E
0x180110c5b  mov     eax, [rbp+200h+var_264]
0x180110c5e  mov     dword ptr [rsp+300h+var_2C8+4], eax
0x180110c62  mov     eax, [rbp+200h+var_260]
0x180110c65  mov     dword ptr [rsp+300h+var_2C8], eax
0x180110c69  add     rsi, [rsp+300h+var_2C8]
0x180110c6e  lea     rdx, [rbp+200h+FindFileData]; lpFindFileData
0x180110c72  mov     rcx, r14; hFindFile
0x180110c75  call    cs:__imp_FindNextFileW
0x180110c7c  nop     dword ptr [rax+rax+00h]
0x180110c81  cmp     eax, 1
0x180110c84  jz      loc_180110B73
0x180110c8a  lea     rcx, [rsp+300h+hFindFile]
0x180110c8f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180110c94  nop
0x180110c95  lea     rcx, [rsp+300h+var_2A0]
0x180110c9a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180110c9f  mov     rax, rsi
0x180110ca2  mov     rcx, [rbp+200h+var_30]
0x180110ca9  xor     rcx, rsp; StackCookie
0x180110cac  call    __security_check_cookie
0x180110cb1  lea     r11, [rsp+300h+var_20]
0x180110cb9  mov     rbx, [r11+38h]
0x180110cbd  mov     rsi, [r11+40h]
0x180110cc1  mov     rsp, r11
0x180110cc4  pop     r15
0x180110cc6  pop     r14
0x180110cc8  pop     r12
0x180110cca  pop     rdi
0x180110ccb  pop     rbp
0x180110ccc  retn
```
