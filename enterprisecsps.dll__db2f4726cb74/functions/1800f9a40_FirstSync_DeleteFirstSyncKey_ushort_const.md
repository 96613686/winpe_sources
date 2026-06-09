# FirstSync::DeleteFirstSyncKey(ushort const *)

- ea: `0x1800f9a40`
- end: `0x1800f9b8e`
- name: `?DeleteFirstSyncKey@FirstSync@@YAJPEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(PCWSTR pszMore, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800343d0`

## callees

- `0x18000d4d4`
- `0x18002201c`
- `0x180025a78`
- `0x180025ac0`
- `0x18002aed0`
- `0x18002dc38`
- `0x18002dcc8`
- `0x18002df7c`
- `0x1800f9a40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800f9b38`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800f9b38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f9af8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f9af8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f9a99`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f9a99`

## pseudocode

```c
__int64 __fastcall FirstSync::DeleteFirstSyncKey(PCWSTR pszMore, const unsigned __int16 *a2)
{
  const WCHAR *v3; // rax
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  unsigned int v7; // eax
  const char *v8; // r9
  int phkResult; // [rsp+20h] [rbp-10h]
  unsigned int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF
  PWSTR ppszPathOut; // [rsp+50h] [rbp+20h] BYREF

  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MDM_ENTERPRISE_DIAGNOSTICS_Context,
      EnterpriseDiagnosticsDeleteFirstSyncKey,
      pszMore);
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v3 = (const WCHAR *)DMGetKnownRegPath(2);
  v4 = PathAllocCombine(v3, pszMore, 0, &ppszPathOut);
  v5 = v4;
  if ( v4 >= 0 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, ppszPathOut, 0, 0x2001Fu, &hKey);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = RegDeleteTreeW(hKey, L"FirstSync");
      v8 = 0;
      if ( v7 != 2 )
        v8 = (const char *)v7;
      if ( !(_DWORD)v8 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        v5 = 0;
        goto LABEL_13;
      }
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1A6,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
             v8,
             phkResulta);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v6,
        phkResulta);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  return v5;
}

```

## disassembly

```asm
0x1800f9a40  mov     [rsp-8+arg_0], rbx
0x1800f9a45  push    rbp
0x1800f9a46  mov     rbp, rsp
0x1800f9a49  sub     rsp, 30h
0x1800f9a4d  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x1800f9a54  mov     rbx, rcx
0x1800f9a57  jz      short loc_1800F9A6F
0x1800f9a59  mov     r8, rcx
0x1800f9a5c  lea     rdx, EnterpriseDiagnosticsDeleteFirstSyncKey
0x1800f9a63  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x1800f9a6a  call    McTemplateU0z_EventWriteTransfer
0x1800f9a6f  xor     edx, edx
0x1800f9a71  mov     [rbp+ppszPathOut], 0
0x1800f9a79  lea     rcx, [rbp+ppszPathOut]
0x1800f9a7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9a82  mov     ecx, 2
0x1800f9a87  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800f9a8c  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x1800f9a90  xor     r8d, r8d; dwFlags
0x1800f9a93  mov     rdx, rbx; pszMore
0x1800f9a96  mov     rcx, rax; pszPathIn
0x1800f9a99  call    cs:__imp_PathAllocCombine
0x1800f9aa0  nop     dword ptr [rax+rax+00h]
0x1800f9aa5  mov     ebx, eax
0x1800f9aa7  test    eax, eax
0x1800f9aa9  jns     short loc_1800F9AC8
0x1800f9aab  mov     rcx, [rbp+8]; this
0x1800f9aaf  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9ab6  mov     r9d, eax; char *
0x1800f9ab9  mov     edx, 19Fh; void *
0x1800f9abe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9ac3  jmp     loc_1800F9B77
0x1800f9ac8  xor     edx, edx
0x1800f9aca  mov     [rbp+hKey], 0
0x1800f9ad2  lea     rcx, [rbp+hKey]
0x1800f9ad6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800f9adb  mov     rdx, [rbp+ppszPathOut]; lpSubKey
0x1800f9adf  lea     rax, [rbp+hKey]
0x1800f9ae3  mov     r9d, 2001Fh; samDesired
0x1800f9ae9  mov     qword ptr [rsp+30h+phkResult], rax; unsigned int
0x1800f9aee  xor     r8d, r8d; ulOptions
0x1800f9af1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f9af8  call    cs:__imp_RegOpenKeyExW
0x1800f9aff  nop     dword ptr [rax+rax+00h]
0x1800f9b04  mov     ebx, eax
0x1800f9b06  test    eax, eax
0x1800f9b08  jns     short loc_1800F9B2D
0x1800f9b0a  mov     rcx, [rbp+8]; this
0x1800f9b0e  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9b15  mov     r9d, eax; char *
0x1800f9b18  mov     edx, 1A2h; void *
0x1800f9b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9b22  lea     rcx, [rbp+hKey]
0x1800f9b26  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f9b2b  jmp     short loc_1800F9B77
0x1800f9b2d  mov     rcx, [rbp+hKey]; hKey
0x1800f9b31  lea     rdx, aFirstsync; "FirstSync"
0x1800f9b38  call    cs:__imp_RegDeleteTreeW
0x1800f9b3f  nop     dword ptr [rax+rax+00h]
0x1800f9b44  xor     r9d, r9d
0x1800f9b47  cmp     eax, 2
0x1800f9b4a  cmovnz  r9d, eax; char *
0x1800f9b4e  test    r9d, r9d
0x1800f9b51  jz      short loc_1800F9B6C
0x1800f9b53  mov     rcx, [rbp+8]; this
0x1800f9b57  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800f9b5e  mov     edx, 1A6h; void *
0x1800f9b63  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f9b68  mov     ebx, eax
0x1800f9b6a  jmp     short loc_1800F9B22
0x1800f9b6c  lea     rcx, [rbp+hKey]
0x1800f9b70  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f9b75  xor     ebx, ebx
0x1800f9b77  lea     rcx, [rbp+ppszPathOut]
0x1800f9b7b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f9b80  mov     eax, ebx
0x1800f9b82  mov     rbx, [rsp+30h+arg_0]
0x1800f9b87  add     rsp, 30h
0x1800f9b8b  pop     rbp
0x1800f9b8c  retn
```
