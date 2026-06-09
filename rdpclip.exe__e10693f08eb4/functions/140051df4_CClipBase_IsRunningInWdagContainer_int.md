# CClipBase::IsRunningInWdagContainer(int *)

- ea: `0x140051df4`
- end: `0x140051fd3`
- name: `?IsRunningInWdagContainer@CClipBase@@AEAAJPEAH@Z`
- size: `479`
- prototype: `__int64 __fastcall(CClipBase *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14004f9dc`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x14004eea4`
- `0x140051df4`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051e94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051eea`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140051e0d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140051e0d`

## string_xrefs

- `0x140051e03`: `IsolatedWindowsEnvironmentUtils.dll`

## pseudocode

```c
__int64 __fastcall CClipBase::IsRunningInWdagContainer(CClipBase *this, int *a2)
{
  HMODULE LibraryW; // rax
  signed int v4; // eax
  signed int v5; // edi
  unsigned int v6; // eax
  FARPROC ProcAddress; // rax
  unsigned int v8; // eax
  signed int LastError; // eax
  unsigned int v10; // eax
  int v11; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  CClipBase *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = this;
  LibraryW = LoadLibraryW(L"IsolatedWindowsEnvironmentUtils.dll");
  v14 = (CClipBase *)LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "IsProcessInIsolatedWindowsEnvironment");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(int *))ProcAddress)(a2);
      if ( v5 >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v11 = *a2;
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            273,
            &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
            CurrentThreadActivityIdPrefix,
            v11);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          272,
          (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
          v10,
          (__int64)"IsProcessInIsolatedWindowsEnvironment failed",
          v5);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v8, 0);
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 270, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v6, v5);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140051df4  mov     [rsp+arg_8], rbx
0x140051df9  mov     [rsp+arg_0], rcx
0x140051dfe  push    rdi
0x140051dff  sub     rsp, 30h
0x140051e03  lea     rcx, aIsolatedwindow; "IsolatedWindowsEnvironmentUtils.dll"
0x140051e0a  mov     rbx, rdx
0x140051e0d  call    cs:__imp_LoadLibraryW
0x140051e13  mov     [rsp+38h+arg_0], rax
0x140051e18  test    rax, rax
0x140051e1b  jnz     short loc_140051E8A
0x140051e1d  call    cs:__imp_GetLastError
0x140051e23  mov     edi, eax
0x140051e25  test    eax, eax
0x140051e27  jle     short loc_140051E32
0x140051e29  movzx   edi, ax
0x140051e2c  or      edi, 80070000h
0x140051e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140051e39  lea     rax, WPP_GLOBAL_Control
0x140051e40  cmp     rcx, rax
0x140051e43  jz      loc_140051FBC
0x140051e49  test    byte ptr [rcx+1Ch], 1
0x140051e4d  jz      loc_140051FBC
0x140051e53  cmp     byte ptr [rcx+19h], 2
0x140051e57  jb      loc_140051FBC
0x140051e5d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051e62  mov     rcx, cs:WPP_GLOBAL_Control
0x140051e69  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051e70  mov     edx, 10Eh
0x140051e75  mov     dword ptr [rsp+38h+var_18], edi
0x140051e79  mov     r9d, eax
0x140051e7c  mov     rcx, [rcx+10h]
0x140051e80  call    WPP_SF_Dd
0x140051e85  jmp     loc_140051FBC
0x140051e8a  lea     rdx, aIsprocessiniso; "IsProcessInIsolatedWindowsEnvironment"
0x140051e91  mov     rcx, rax; hModule
0x140051e94  call    cs:__imp_GetProcAddress
0x140051e9a  test    rax, rax
0x140051e9d  jnz     short loc_140051F08
0x140051e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140051ea6  lea     rax, WPP_GLOBAL_Control
0x140051ead  cmp     rcx, rax
0x140051eb0  jz      short loc_140051EEA
0x140051eb2  test    byte ptr [rcx+1Ch], 1
0x140051eb6  jz      short loc_140051EEA
0x140051eb8  cmp     byte ptr [rcx+19h], 2
0x140051ebc  jb      short loc_140051EEA
0x140051ebe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x140051eca  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051ed1  mov     edx, 10Fh
0x140051ed6  mov     dword ptr [rsp+38h+var_18], 0
0x140051ede  mov     r9d, eax
0x140051ee1  mov     rcx, [rcx+10h]
0x140051ee5  call    WPP_SF_Dd
0x140051eea  call    cs:__imp_GetLastError
0x140051ef0  mov     edi, eax
0x140051ef2  test    eax, eax
0x140051ef4  jle     loc_140051FBC
0x140051efa  movzx   edi, ax
0x140051efd  or      edi, 80070000h
0x140051f03  jmp     loc_140051FBC
0x140051f08  mov     rcx, rbx
0x140051f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051f10  mov     edi, eax
0x140051f12  test    eax, eax
0x140051f14  jns     short loc_140051F73
0x140051f16  mov     rcx, cs:WPP_GLOBAL_Control
0x140051f1d  lea     rax, WPP_GLOBAL_Control
0x140051f24  cmp     rcx, rax
0x140051f27  jz      loc_140051FBC
0x140051f2d  test    byte ptr [rcx+1Ch], 8
0x140051f31  jz      loc_140051FBC
0x140051f37  cmp     byte ptr [rcx+19h], 2
0x140051f3b  jb      short loc_140051FBC
0x140051f3d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051f42  lea     rcx, aIsprocessiniso_0; "IsProcessInIsolatedWindowsEnvironment f"...
0x140051f49  mov     [rsp+38h+var_10], edi
0x140051f4d  mov     [rsp+38h+var_18], rcx
0x140051f52  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051f59  mov     rcx, cs:WPP_GLOBAL_Control
0x140051f60  mov     edx, 110h
0x140051f65  mov     r9d, eax
0x140051f68  mov     rcx, [rcx+10h]
0x140051f6c  call    WPP_SF_DsD
0x140051f71  jmp     short loc_140051FBC
0x140051f73  mov     rcx, cs:WPP_GLOBAL_Control
0x140051f7a  lea     rax, WPP_GLOBAL_Control
0x140051f81  cmp     rcx, rax
0x140051f84  jz      short loc_140051FBC
0x140051f86  test    byte ptr [rcx+1Ch], 1
0x140051f8a  jz      short loc_140051FBC
0x140051f8c  cmp     byte ptr [rcx+19h], 4
0x140051f90  jb      short loc_140051FBC
0x140051f92  mov     ebx, [rbx]
0x140051f94  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051f99  mov     rcx, cs:WPP_GLOBAL_Control
0x140051fa0  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051fa7  mov     edx, 111h
0x140051fac  mov     dword ptr [rsp+38h+var_18], ebx
0x140051fb0  mov     r9d, eax
0x140051fb3  mov     rcx, [rcx+10h]
0x140051fb7  call    WPP_SF_Dd
0x140051fbc  lea     rcx, [rsp+38h+arg_0]
0x140051fc1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x140051fc6  mov     rbx, [rsp+38h+arg_8]
0x140051fcb  mov     eax, edi
0x140051fcd  add     rsp, 30h
0x140051fd1  pop     rdi
0x140051fd2  retn
```
