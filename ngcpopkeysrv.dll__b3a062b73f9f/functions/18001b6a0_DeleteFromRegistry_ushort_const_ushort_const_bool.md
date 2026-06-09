# DeleteFromRegistry(ushort const *,ushort const *,bool)

- ea: `0x18001b6a0`
- end: `0x18001b7f6`
- name: `?DeleteFromRegistry@@YAJPEBG0_N@Z`
- size: `342`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b7fc`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x18001069c`
- `0x180010730`
- `0x1800153f0`
- `0x18001737c`
- `0x18001b6a0`
- `0x180022ef4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b79e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b79e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001b77c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001b77c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b72a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b72a`

## string_xrefs

- `0x18001b6e7`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b74b`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b7c1`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall DeleteFromRegistry(const unsigned __int16 *a1, const unsigned __int16 *a2, char a3)
{
  const unsigned __int16 *v6; // rdx
  NgcUtils *v7; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v9; // ebx
  HKEY *v10; // rax
  LSTATUS v11; // eax
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdx
  int phkResult; // [rsp+20h] [rbp-28h]
  int phkResulta; // [rsp+20h] [rbp-28h]
  LPCWSTR lpSubKey[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  lpSubKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v7,
                                        v6,
                                        a1,
                                        (unsigned __int16 *)lpSubKey);
  v9 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    hKey = 0;
    v10 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0xF003Fu, v10);
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x757,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)v9,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_18;
    }
    if ( a3 )
    {
      v12 = RegDeleteKeyExW(hKey, a2, 0, 0);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v13 = retaddr;
      if ( v12 >= 0 )
        goto LABEL_17;
      v14 = 1887;
    }
    else
    {
      v12 = RegDeleteValueW(hKey, a2);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v13 = retaddr;
      if ( v12 >= 0 )
        goto LABEL_17;
      v14 = 1893;
    }
    wil::details::in1diag3::_Log_Hr(
      v13,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v12,
      phkResulta);
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v9 = 0;
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x74F,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
    (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
    phkResult);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
  return v9;
}

```

## disassembly

```asm
0x18001b6a0  mov     rax, rsp
0x18001b6a3  mov     [rax+8], rbx
0x18001b6a7  mov     [rax+10h], rsi
0x18001b6ab  push    rdi
0x18001b6ac  sub     rsp, 40h
0x18001b6b0  mov     sil, r8b
0x18001b6b3  mov     rdi, rdx
0x18001b6b6  mov     rbx, rcx
0x18001b6b9  mov     qword ptr [rax-18h], 0
0x18001b6c1  xor     edx, edx
0x18001b6c3  lea     rcx, [rax-18h]
0x18001b6c7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b6cc  lea     r9, [rsp+48h+lpSubKey]; unsigned __int16 *
0x18001b6d1  mov     r8, rbx; unsigned __int16 *
0x18001b6d4  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001b6d9  mov     ebx, eax
0x18001b6db  test    eax, eax
0x18001b6dd  jns     short loc_18001B6FD
0x18001b6df  mov     rcx, [rsp+48h]; this
0x18001b6e4  mov     r9d, eax; char *
0x18001b6e7  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b6ee  mov     edx, 74Fh; void *
0x18001b6f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b6f8  jmp     loc_18001B7DA
0x18001b6fd  mov     [rsp+48h+hKey], 0
0x18001b706  lea     rcx, [rsp+48h+hKey]
0x18001b70b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001b710  mov     qword ptr [rsp+48h+phkResult], rax; int
0x18001b715  mov     r9d, 0F003Fh; samDesired
0x18001b71b  xor     r8d, r8d; ulOptions
0x18001b71e  mov     rdx, [rsp+48h+lpSubKey]; lpSubKey
0x18001b723  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b72a  call    cs:__imp_RegOpenKeyExW
0x18001b730  mov     ebx, eax
0x18001b732  test    eax, eax
0x18001b734  jle     short loc_18001B73F
0x18001b736  movzx   ebx, ax
0x18001b739  or      ebx, 80070000h
0x18001b73f  test    ebx, ebx
0x18001b741  jns     short loc_18001B769
0x18001b743  mov     rcx, [rsp+48h]; this
0x18001b748  mov     r9d, ebx; char *
0x18001b74b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b752  mov     edx, 757h; void *
0x18001b757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b75c  nop
0x18001b75d  lea     rcx, [rsp+48h+hKey]
0x18001b762  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001b767  jmp     short loc_18001B7DA
0x18001b769  mov     rdx, rdi; lpValueName
0x18001b76c  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b771  test    sil, sil
0x18001b774  jz      short loc_18001B79E
0x18001b776  xor     r9d, r9d; Reserved
0x18001b779  xor     r8d, r8d; samDesired
0x18001b77c  call    cs:__imp_RegDeleteKeyExW
0x18001b782  test    eax, eax
0x18001b784  jle     short loc_18001B78E
0x18001b786  movzx   eax, ax
0x18001b789  or      eax, 80070000h
0x18001b78e  mov     rcx, [rsp+48h]
0x18001b793  test    eax, eax
0x18001b795  jns     short loc_18001B7CE
0x18001b797  mov     edx, 75Fh
0x18001b79c  jmp     short loc_18001B7BE
0x18001b79e  call    cs:__imp_RegDeleteValueW
0x18001b7a4  test    eax, eax
0x18001b7a6  jle     short loc_18001B7B0
0x18001b7a8  movzx   eax, ax
0x18001b7ab  or      eax, 80070000h
0x18001b7b0  mov     rcx, [rsp+48h]; this
0x18001b7b5  test    eax, eax
0x18001b7b7  jns     short loc_18001B7CE
0x18001b7b9  mov     edx, 765h; void *
0x18001b7be  mov     r9d, eax; char *
0x18001b7c1  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b7c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b7cd  nop
0x18001b7ce  lea     rcx, [rsp+48h+hKey]
0x18001b7d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001b7d8  xor     ebx, ebx
0x18001b7da  lea     rcx, [rsp+48h+lpSubKey]
0x18001b7df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b7e4  mov     eax, ebx
0x18001b7e6  mov     rbx, [rsp+48h+arg_0]
0x18001b7eb  mov     rsi, [rsp+48h+arg_8]
0x18001b7f0  add     rsp, 40h
0x18001b7f4  pop     rdi
0x18001b7f5  retn
```
