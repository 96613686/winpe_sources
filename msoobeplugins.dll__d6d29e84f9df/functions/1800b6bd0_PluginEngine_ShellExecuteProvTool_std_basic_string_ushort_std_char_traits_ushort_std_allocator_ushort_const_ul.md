# PluginEngine::ShellExecuteProvTool(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *,ulong)

- ea: `0x1800b6bd0`
- end: `0x1800b702d`
- name: `?ShellExecuteProvTool@PluginEngine@@MEAAJPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `1117`
- prototype: `__int64 __fastcall(unsigned int *, __int64, DWORD)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180008524`
- `0x180008544`
- `0x18003a98c`
- `0x18003e430`
- `0x18003e4d4`
- `0x18003e56c`
- `0x18003e870`
- `0x180048340`
- `0x180052100`
- `0x18005431c`
- `0x1800628a8`
- `0x18007198c`
- `0x1800b3e84`
- `0x1800b44fc`
- `0x1800b6bd0`
- `0x1800b73f0`
- `0x1800c4010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x1800b6deb`
- `SHELL32!ShellExecuteExW` at `0x1800b6deb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b6eb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b6eb8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6c0f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6c47`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6c0f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6c47`

## string_xrefs

- `0x1800b6c61`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6dfd`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6e5b`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6ed5`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6f29`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6f88`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall PluginEngine::ShellExecuteProvTool(unsigned int *a1, __int64 a2, DWORD a3)
{
  const WCHAR *v6; // rcx
  __int64 v7; // rbx
  const WCHAR *v8; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  const char *v18; // r9
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  DWORD v21; // eax
  const char *v22; // r9
  unsigned int LastError; // ebx
  HANDLE hHandle; // [rsp+20h] [rbp-158h] BYREF
  LPWSTR lpDst[3]; // [rsp+28h] [rbp-150h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-138h] BYREF
  _BYTE v27[32]; // [rsp+B0h] [rbp-C8h] BYREF
  _BYTE v28[32]; // [rsp+D0h] [rbp-A8h] BYREF
  _BYTE v29[32]; // [rsp+F0h] [rbp-88h] BYREF
  _BYTE v30[32]; // [rsp+110h] [rbp-68h] BYREF
  _BYTE v31[32]; // [rsp+130h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1801150C0);
  v7 = ExpandEnvironmentStringsW(v6, 0, 0);
  LOWORD(hHandle) = 0;
  std::vector<unsigned short>::vector<unsigned short>(lpDst, v7, &hHandle);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1801150C0);
  if ( ExpandEnvironmentStringsW(v8, lpDst[0], v7) == (_DWORD)v7 )
  {
    std::wstring::wstring(v28, lpDst[0]);
    std::wstring::wstring(v27, a2);
    v10 = std::wstring::wstring(v29, L" /source");
    v12 = std::_WChar_traits<unsigned short>::length(L" ", v11, v10);
    v15 = std::wstring::_Insert<unsigned short>(v14, v13, v14, v12);
    std::wstring::wstring(v31, v15);
    v16 = std::wstring::append(v31, L" ");
    std::wstring::wstring(v30, v16);
    std::wstring::append(v27, v30);
    std::wstring::_Tidy_deallocate(v30);
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(v29);
    v17 = (*(__int64 (__fastcall **)(unsigned int *, _BYTE *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, v29, a1[14]);
    std::wstring::append(v27, v17);
    std::wstring::_Tidy_deallocate(v29);
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    hHandle = 0;
    pExecInfo.cbSize = 112;
    pExecInfo.fMask = 64;
    pExecInfo.lpVerb = L"open";
    pExecInfo.lpFile = (LPCWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    pExecInfo.lpParameters = (LPCWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    pExecInfo.nShow = 0;
    if ( ShellExecuteExW(&pExecInfo) )
    {
      if ( pExecInfo.hProcess )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&hHandle);
        v21 = WaitForSingleObject(hHandle, a3);
        if ( v21 == 258 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEC,
            (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
            (const char *)0x800705B4LL,
            (int)hHandle);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
          std::wstring::_Tidy_deallocate(v27);
          std::wstring::_Tidy_deallocate(v28);
          std::vector<unsigned short>::_Tidy(lpDst);
          return 2147943860LL;
        }
        else if ( v21 == -1 )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xED,
                        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                        v22);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
          std::wstring::_Tidy_deallocate(v27);
          std::wstring::_Tidy_deallocate(v28);
          std::vector<unsigned short>::_Tidy(lpDst);
          return LastError;
        }
        else if ( v21 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEE,
            (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
            (const char *)0x8000FFFFLL,
            (int)hHandle);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
          std::wstring::_Tidy_deallocate(v27);
          std::wstring::_Tidy_deallocate(v28);
          std::vector<unsigned short>::_Tidy(lpDst);
          return 2147549183LL;
        }
        else
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
          std::wstring::_Tidy_deallocate(v27);
          std::wstring::_Tidy_deallocate(v28);
          std::vector<unsigned short>::_Tidy(lpDst);
          return 0;
        }
      }
      else
      {
        v20 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xE8,
                (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                v18);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
        std::wstring::_Tidy_deallocate(v27);
        std::wstring::_Tidy_deallocate(v28);
        std::vector<unsigned short>::_Tidy(lpDst);
        return v20;
      }
    }
    else
    {
      v19 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xE7,
              (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
              v18);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
      std::wstring::_Tidy_deallocate(v27);
      std::wstring::_Tidy_deallocate(v28);
      std::vector<unsigned short>::_Tidy(lpDst);
      return v19;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)0x8000FFFFLL,
      (int)hHandle);
    std::vector<unsigned short>::_Tidy(lpDst);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1800b6bd0  mov     [rsp+arg_18], rbx
0x1800b6bd5  push    rsi
0x1800b6bd6  push    rdi
0x1800b6bd7  push    r14
0x1800b6bd9  sub     rsp, 160h
0x1800b6be0  mov     rax, cs:__security_cookie
0x1800b6be7  xor     rax, rsp
0x1800b6bea  mov     [rsp+178h+var_28], rax
0x1800b6bf2  mov     r14d, r8d
0x1800b6bf5  mov     rdi, rdx
0x1800b6bf8  mov     rsi, rcx
0x1800b6bfb  lea     rcx, qword_1801150C0
0x1800b6c02  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6c07  mov     rcx, rax; lpSrc
0x1800b6c0a  xor     r8d, r8d; nSize
0x1800b6c0d  xor     edx, edx; lpDst
0x1800b6c0f  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b6c15  mov     ebx, eax
0x1800b6c17  xor     ecx, ecx
0x1800b6c19  mov     word ptr [rsp+178h+hHandle], cx; int
0x1800b6c1e  mov     edx, ebx
0x1800b6c20  lea     r8, [rsp+178h+hHandle]
0x1800b6c25  lea     rcx, [rsp+178h+lpDst]
0x1800b6c2a  call    ??$?0V?$allocator@G@std@@$0A@@?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBGAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,ushort const &,std::allocator<ushort> const &)
0x1800b6c2f  nop
0x1800b6c30  lea     rcx, qword_1801150C0
0x1800b6c37  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6c3c  mov     rcx, rax; lpSrc
0x1800b6c3f  mov     r8d, ebx; nSize
0x1800b6c42  mov     rdx, [rsp+178h+lpDst]; lpDst
0x1800b6c47  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b6c4d  cmp     eax, ebx
0x1800b6c4f  jz      short loc_1800B6C84
0x1800b6c51  mov     rcx, [rsp+178h]; this
0x1800b6c59  mov     ebx, 8000FFFFh
0x1800b6c5e  mov     r9d, ebx; char *
0x1800b6c61  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6c68  mov     edx, 0D6h; void *
0x1800b6c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6c72  nop
0x1800b6c73  lea     rcx, [rsp+178h+lpDst]
0x1800b6c78  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b6c7d  mov     eax, ebx
0x1800b6c7f  jmp     loc_1800B7008
0x1800b6c84  mov     rdx, [rsp+178h+lpDst]
0x1800b6c89  lea     rcx, [rsp+178h+var_A8]
0x1800b6c91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b6c96  nop
0x1800b6c97  mov     rdx, rdi
0x1800b6c9a  lea     rcx, [rsp+178h+var_C8]
0x1800b6ca2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b6ca7  nop
0x1800b6ca8  lea     rdx, ?c_provSourceCmdLine@@3QBGB; " /source"
0x1800b6caf  lea     rcx, [rsp+178h+var_88]
0x1800b6cb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b6cbc  mov     r8, rax
0x1800b6cbf  lea     rcx, asc_1800FC130; " "
0x1800b6cc6  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800b6ccb  mov     r9, rax
0x1800b6cce  mov     rcx, r8
0x1800b6cd1  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x1800b6cd6  mov     rdx, rax
0x1800b6cd9  lea     rcx, [rsp+178h+var_48]
0x1800b6ce1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800b6ce6  nop
0x1800b6ce7  lea     rdx, asc_1800FC130; " "
0x1800b6cee  lea     rcx, [rsp+178h+var_48]
0x1800b6cf6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800b6cfb  mov     rdx, rax
0x1800b6cfe  lea     rcx, [rsp+178h+var_68]
0x1800b6d06  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800b6d0b  nop
0x1800b6d0c  lea     rdx, [rsp+178h+var_68]
0x1800b6d14  lea     rcx, [rsp+178h+var_C8]
0x1800b6d1c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800b6d21  nop
0x1800b6d22  lea     rcx, [rsp+178h+var_68]
0x1800b6d2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6d2f  nop
0x1800b6d30  lea     rcx, [rsp+178h+var_48]
0x1800b6d38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6d3d  nop
0x1800b6d3e  lea     rcx, [rsp+178h+var_88]
0x1800b6d46  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6d4b  mov     rax, [rsi]
0x1800b6d4e  mov     r8d, [rsi+38h]
0x1800b6d52  lea     rdx, [rsp+178h+var_88]
0x1800b6d5a  mov     rcx, rsi
0x1800b6d5d  mov     rax, [rax+70h]
0x1800b6d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6d66  nop
0x1800b6d67  mov     rdx, rax
0x1800b6d6a  lea     rcx, [rsp+178h+var_C8]
0x1800b6d72  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800b6d77  nop
0x1800b6d78  lea     rcx, [rsp+178h+var_88]
0x1800b6d80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6d85  mov     ebx, 70h ; 'p'
0x1800b6d8a  mov     r8d, ebx; Size
0x1800b6d8d  xor     edx, edx; Val
0x1800b6d8f  lea     rcx, [rsp+178h+pExecInfo]; void *
0x1800b6d94  call    memset_0
0x1800b6d99  mov     [rsp+178h+hHandle], 0; int
0x1800b6da2  mov     [rsp+178h+pExecInfo.cbSize], ebx
0x1800b6da6  mov     [rsp+178h+pExecInfo.fMask], 40h ; '@'
0x1800b6dae  lea     rax, aOpen; "open"
0x1800b6db5  mov     [rsp+178h+pExecInfo.lpVerb], rax
0x1800b6dba  lea     rcx, [rsp+178h+var_A8]
0x1800b6dc2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6dc7  mov     [rsp+178h+pExecInfo.lpFile], rax
0x1800b6dcc  lea     rcx, [rsp+178h+var_C8]
0x1800b6dd4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6dd9  mov     [rsp+178h+pExecInfo.lpParameters], rax
0x1800b6dde  mov     [rsp+178h+pExecInfo.nShow], 0
0x1800b6de6  lea     rcx, [rsp+178h+pExecInfo]; pExecInfo
0x1800b6deb  call    cs:__imp_ShellExecuteExW
0x1800b6df1  test    eax, eax
0x1800b6df3  jnz     short loc_1800B6E46
0x1800b6df5  mov     rcx, [rsp+178h]; this
0x1800b6dfd  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6e04  lea     edx, [rbx+77h]; void *
0x1800b6e07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b6e0c  mov     ebx, eax
0x1800b6e0e  lea     rcx, [rsp+178h+hHandle]
0x1800b6e13  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b6e18  nop
0x1800b6e19  lea     rcx, [rsp+178h+var_C8]
0x1800b6e21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6e26  nop
0x1800b6e27  lea     rcx, [rsp+178h+var_A8]
0x1800b6e2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6e34  nop
0x1800b6e35  lea     rcx, [rsp+178h+lpDst]
0x1800b6e3a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b6e3f  mov     eax, ebx
0x1800b6e41  jmp     loc_1800B7008
0x1800b6e46  mov     rdx, [rsp+178h+pExecInfo.hProcess]
0x1800b6e4e  test    rdx, rdx
0x1800b6e51  jnz     short loc_1800B6EA6
0x1800b6e53  mov     rcx, [rsp+178h]; this
0x1800b6e5b  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6e62  mov     edx, 0E8h; void *
0x1800b6e67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b6e6c  mov     ebx, eax
0x1800b6e6e  lea     rcx, [rsp+178h+hHandle]
0x1800b6e73  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b6e78  nop
0x1800b6e79  lea     rcx, [rsp+178h+var_C8]
0x1800b6e81  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6e86  nop
0x1800b6e87  lea     rcx, [rsp+178h+var_A8]
0x1800b6e8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6e94  nop
0x1800b6e95  lea     rcx, [rsp+178h+lpDst]
0x1800b6e9a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b6e9f  mov     eax, ebx
0x1800b6ea1  jmp     loc_1800B7008
0x1800b6ea6  lea     rcx, [rsp+178h+hHandle]
0x1800b6eab  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b6eb0  mov     edx, r14d; dwMilliseconds
0x1800b6eb3  mov     rcx, [rsp+178h+hHandle]; hHandle
0x1800b6eb8  call    cs:__imp_WaitForSingleObject
0x1800b6ebe  cmp     eax, 102h
0x1800b6ec3  jnz     short loc_1800B6F1C
0x1800b6ec5  mov     rcx, [rsp+178h]; this
0x1800b6ecd  mov     ebx, 800705B4h
0x1800b6ed2  mov     r9d, ebx; char *
0x1800b6ed5  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6edc  lea     edx, [rax-16h]; void *
0x1800b6edf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6ee4  lea     rcx, [rsp+178h+hHandle]
0x1800b6ee9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b6eee  nop
0x1800b6eef  lea     rcx, [rsp+178h+var_C8]
0x1800b6ef7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6efc  nop
0x1800b6efd  lea     rcx, [rsp+178h+var_A8]
0x1800b6f05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6f0a  nop
0x1800b6f0b  lea     rcx, [rsp+178h+lpDst]
0x1800b6f10  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b6f15  mov     eax, ebx
0x1800b6f17  jmp     loc_1800B7008
0x1800b6f1c  cmp     eax, 0FFFFFFFFh
0x1800b6f1f  jnz     short loc_1800B6F74
0x1800b6f21  mov     rcx, [rsp+178h]; this
0x1800b6f29  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6f30  mov     edx, 0EDh; void *
0x1800b6f35  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b6f3a  mov     ebx, eax
0x1800b6f3c  lea     rcx, [rsp+178h+hHandle]
0x1800b6f41  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b6f46  nop
0x1800b6f47  lea     rcx, [rsp+178h+var_C8]
0x1800b6f4f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6f54  nop
0x1800b6f55  lea     rcx, [rsp+178h+var_A8]
0x1800b6f5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6f62  nop
0x1800b6f63  lea     rcx, [rsp+178h+lpDst]
0x1800b6f68  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b6f6d  mov     eax, ebx
0x1800b6f6f  jmp     loc_1800B7008
0x1800b6f74  test    eax, eax
0x1800b6f76  jz      short loc_1800B6FCE
0x1800b6f78  mov     rcx, [rsp+178h]; this
0x1800b6f80  mov     ebx, 8000FFFFh
0x1800b6f85  mov     r9d, ebx; char *
0x1800b6f88  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6f8f  mov     edx, 0EEh; void *
0x1800b6f94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6f99  lea     rcx, [rsp+178h+hHandle]
0x1800b6f9e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b6fa3  nop
0x1800b6fa4  lea     rcx, [rsp+178h+var_C8]
0x1800b6fac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6fb1  nop
0x1800b6fb2  lea     rcx, [rsp+178h+var_A8]
0x1800b6fba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6fbf  nop
0x1800b6fc0  lea     rcx, [rsp+178h+lpDst]
0x1800b6fc5  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b6fca  mov     eax, ebx
0x1800b6fcc  jmp     short loc_1800B7008
0x1800b6fce  lea     rcx, [rsp+178h+hHandle]
0x1800b6fd3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b6fd8  nop
0x1800b6fd9  lea     rcx, [rsp+178h+var_C8]
0x1800b6fe1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6fe6  nop
0x1800b6fe7  lea     rcx, [rsp+178h+var_A8]
0x1800b6fef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6ff4  nop
0x1800b6ff5  lea     rcx, [rsp+178h+lpDst]
0x1800b6ffa  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b6fff  nop
0x1800b7000  xor     eax, eax
0x1800b7002  jmp     short loc_1800B7008
0x1800b7004  mov     eax, dword ptr [rsp+178h+hHandle]
0x1800b7008  mov     rcx, [rsp+178h+var_28]
0x1800b7010  xor     rcx, rsp; StackCookie
0x1800b7013  call    __security_check_cookie
0x1800b7018  mov     rbx, [rsp+178h+arg_18]
0x1800b7020  add     rsp, 160h
0x1800b7027  pop     r14
0x1800b7029  pop     rdi
0x1800b702a  pop     rsi
0x1800b702b  retn
```
