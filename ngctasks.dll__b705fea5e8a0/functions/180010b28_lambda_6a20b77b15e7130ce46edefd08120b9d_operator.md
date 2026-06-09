# _lambda_6a20b77b15e7130ce46edefd08120b9d_::operator()

- ea: `0x180010b28`
- end: `0x180010d8e`
- name: `_lambda_6a20b77b15e7130ce46edefd08120b9d_::operator()`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013b08`

## callees

- `0x180006330`
- `0x180008c74`
- `0x18000cc34`
- `0x18000ebc0`
- `0x18000ef9c`
- `0x180010310`
- `0x180010b28`
- `0x1800142d4`
- `0x180014314`
- `0x180014bcc`
- `0x18001c9ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010cca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010d30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010cca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010d30`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010bce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010bce`

## string_xrefs

- `0x180010b78`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180010bee`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180010ce7`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180010d4d`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall lambda_6a20b77b15e7130ce46edefd08120b9d_::operator()(__int64 a1)
{
  const unsigned __int16 *v2; // rdx
  NgcUtils *v3; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  const BYTE *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  int dwOptions; // [rsp+20h] [rbp-39h]
  int dwOptionsa; // [rsp+20h] [rbp-39h]
  HKEY hKey; // [rsp+50h] [rbp-9h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-1h] BYREF
  _OWORD v17[2]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v3,
                                        v2,
                                        L"AIKCertEnroll",
                                        (unsigned __int16 *)&lpSubKey);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
    {
      memset(v17, 0, sizeof(v17));
      if ( **(_BYTE **)a1 )
      {
        v7 = *(_QWORD *)(a1 + 8);
        DWORD2(v17[0]) = *(_DWORD *)(*(_QWORD *)v7 + 8LL);
        *(_QWORD *)v7 = v17;
      }
      SetRegDWordOrDelete(hKey, L"ErrorCount", ***(_DWORD ***)(a1 + 8));
      SetRegDWordOrDelete(hKey, L"RetryAction", *(_DWORD *)(**(_QWORD **)(a1 + 8) + 4LL));
      SetRegQWordOrDelete(hKey, L"ErrorTimeLast", (const struct _LLFILETIME *)(**(_QWORD **)(a1 + 8) + 24LL));
      SetRegQWordOrDelete(hKey, L"ErrorTimeFirst", (const struct _LLFILETIME *)(**(_QWORD **)(a1 + 8) + 16LL));
      v8 = RegSetValueExW(hKey, L"ErrorCode", 0, 4u, (const BYTE *)(**(_QWORD **)(a1 + 8) + 8LL), 4u);
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x37F,
          (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v8);
      v9 = **(const BYTE ***)(a1 + 16);
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&v9[2 * v10] );
      v11 = RegSetValueExW(hKey, L"Container", 0, 1u, v9, 2 * v10 + 2);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x388,
          (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v11);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35E,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)v5,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x352,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      dwOptions);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpSubKey);
  return v5;
}

```

## disassembly

```asm
0x180010b28  push    rbp
0x180010b2a  push    rbx
0x180010b2b  push    rsi
0x180010b2c  push    rdi
0x180010b2d  lea     rbp, [rsp-3Fh]
0x180010b32  sub     rsp, 98h
0x180010b39  mov     rax, cs:__security_cookie
0x180010b40  xor     rax, rsp
0x180010b43  mov     [rbp+57h+var_30], rax
0x180010b47  mov     rdi, rcx
0x180010b4a  xor     esi, esi
0x180010b4c  mov     [rbp+57h+lpSubKey], rsi
0x180010b50  xor     edx, edx
0x180010b52  lea     rcx, [rbp+57h+lpSubKey]
0x180010b56  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010b5b  lea     r9, [rbp+57h+lpSubKey]; unsigned __int16 *
0x180010b5f  lea     r8, aAikcertenroll; "AIKCertEnroll"
0x180010b66  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180010b6b  mov     ebx, eax
0x180010b6d  test    eax, eax
0x180010b6f  jns     short loc_180010B8F
0x180010b71  mov     rcx, [rbp+5Fh]; this
0x180010b75  mov     r9d, eax; char *
0x180010b78  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180010b7f  mov     edx, 352h; void *
0x180010b84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b89  nop
0x180010b8a  jmp     loc_180010D6B
0x180010b8f  mov     [rbp+57h+hKey], rsi
0x180010b93  xor     edx, edx
0x180010b95  lea     rcx, [rbp+57h+hKey]
0x180010b99  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010b9e  mov     [rsp+0B0h+lpdwDisposition], rsi; lpdwDisposition
0x180010ba3  lea     rax, [rbp+57h+hKey]
0x180010ba7  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180010bac  mov     [rsp+0B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180010bb1  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x180010bb9  mov     [rsp+0B0h+dwOptions], esi; int
0x180010bbd  xor     r9d, r9d; lpClass
0x180010bc0  xor     r8d, r8d; Reserved
0x180010bc3  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180010bc7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010bce  call    cs:__imp_RegCreateKeyExW
0x180010bd4  mov     ebx, eax
0x180010bd6  test    eax, eax
0x180010bd8  jle     short loc_180010BE3
0x180010bda  movzx   ebx, ax
0x180010bdd  or      ebx, 80070000h
0x180010be3  test    ebx, ebx
0x180010be5  jns     short loc_180010C0F
0x180010be7  mov     rcx, [rbp+5Fh]; this
0x180010beb  mov     r9d, ebx; char *
0x180010bee  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180010bf5  mov     edx, 35Eh; void *
0x180010bfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bff  nop
0x180010c00  lea     rcx, [rbp+57h+hKey]
0x180010c04  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010c09  nop
0x180010c0a  jmp     loc_180010D6B
0x180010c0f  xorps   xmm0, xmm0
0x180010c12  movups  [rbp+57h+var_50], xmm0
0x180010c16  movups  [rbp+57h+var_40], xmm0
0x180010c1a  mov     rax, [rdi]
0x180010c1d  cmp     [rax], sil
0x180010c20  jz      short loc_180010C36
0x180010c22  mov     rdx, [rdi+8]
0x180010c26  mov     rax, [rdx]
0x180010c29  mov     ecx, [rax+8]
0x180010c2c  mov     dword ptr [rbp+57h+var_50+8], ecx
0x180010c2f  lea     rax, [rbp+57h+var_50]
0x180010c33  mov     [rdx], rax
0x180010c36  mov     rax, [rdi+8]
0x180010c3a  mov     r8, [rax]
0x180010c3d  mov     r8d, [r8]; unsigned int
0x180010c40  lea     rdx, aErrorcount; "ErrorCount"
0x180010c47  mov     rcx, [rbp+57h+hKey]; HKEY
0x180010c4b  call    ?SetRegDWordOrDelete@@YAXPEAUHKEY__@@PEBGK@Z; SetRegDWordOrDelete(HKEY__ *,ushort const *,ulong)
0x180010c50  mov     rax, [rdi+8]
0x180010c54  mov     r8, [rax]
0x180010c57  mov     r8d, [r8+4]; unsigned int
0x180010c5b  lea     rdx, aRetryaction; "RetryAction"
0x180010c62  mov     rcx, [rbp+57h+hKey]; HKEY
0x180010c66  call    ?SetRegDWordOrDelete@@YAXPEAUHKEY__@@PEBGK@Z; SetRegDWordOrDelete(HKEY__ *,ushort const *,ulong)
0x180010c6b  mov     rax, [rdi+8]
0x180010c6f  mov     r8, [rax]
0x180010c72  add     r8, 18h; struct _LLFILETIME *
0x180010c76  lea     rdx, aErrortimelast; "ErrorTimeLast"
0x180010c7d  mov     rcx, [rbp+57h+hKey]; HKEY
0x180010c81  call    ?SetRegQWordOrDelete@@YAXPEAUHKEY__@@PEBGPEBU_LLFILETIME@@@Z; SetRegQWordOrDelete(HKEY__ *,ushort const *,_LLFILETIME const *)
0x180010c86  mov     rax, [rdi+8]
0x180010c8a  mov     r8, [rax]
0x180010c8d  add     r8, 10h; struct _LLFILETIME *
0x180010c91  lea     rdx, aErrortimefirst; "ErrorTimeFirst"
0x180010c98  mov     rcx, [rbp+57h+hKey]; HKEY
0x180010c9c  call    ?SetRegQWordOrDelete@@YAXPEAUHKEY__@@PEBGPEBU_LLFILETIME@@@Z; SetRegQWordOrDelete(HKEY__ *,ushort const *,_LLFILETIME const *)
0x180010ca1  mov     rax, [rdi+8]
0x180010ca5  mov     rdx, [rax]
0x180010ca8  add     rdx, 8
0x180010cac  mov     r9d, 4; dwType
0x180010cb2  mov     [rsp+0B0h+samDesired], r9d; cbData
0x180010cb7  mov     qword ptr [rsp+0B0h+dwOptions], rdx; int
0x180010cbc  xor     r8d, r8d; Reserved
0x180010cbf  lea     rdx, aErrorcode; "ErrorCode"
0x180010cc6  mov     rcx, [rbp+57h+hKey]; hKey
0x180010cca  call    cs:__imp_RegSetValueExW
0x180010cd0  test    eax, eax
0x180010cd2  jle     short loc_180010CDC
0x180010cd4  movzx   eax, ax
0x180010cd7  or      eax, 80070000h
0x180010cdc  mov     rcx, [rbp+5Fh]; this
0x180010ce0  test    eax, eax
0x180010ce2  jns     short loc_180010CF8
0x180010ce4  mov     r9d, eax; char *
0x180010ce7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180010cee  mov     edx, 37Fh; void *
0x180010cf3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010cf8  mov     rax, [rdi+10h]
0x180010cfc  mov     rcx, [rax]
0x180010cff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010d03  inc     rax
0x180010d06  cmp     [rcx+rax*2], si
0x180010d0a  jnz     short loc_180010D03
0x180010d0c  lea     eax, ds:2[rax*2]
0x180010d13  mov     [rsp+0B0h+samDesired], eax; cbData
0x180010d17  mov     qword ptr [rsp+0B0h+dwOptions], rcx; int
0x180010d1c  mov     r9d, 1; dwType
0x180010d22  xor     r8d, r8d; Reserved
0x180010d25  lea     rdx, aContainer; "Container"
0x180010d2c  mov     rcx, [rbp+57h+hKey]; hKey
0x180010d30  call    cs:__imp_RegSetValueExW
0x180010d36  test    eax, eax
0x180010d38  jle     short loc_180010D42
0x180010d3a  movzx   eax, ax
0x180010d3d  or      eax, 80070000h
0x180010d42  mov     rcx, [rbp+5Fh]; this
0x180010d46  test    eax, eax
0x180010d48  jns     short loc_180010D5F
0x180010d4a  mov     r9d, eax; char *
0x180010d4d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180010d54  mov     edx, 388h; void *
0x180010d59  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010d5e  nop
0x180010d5f  lea     rcx, [rbp+57h+hKey]
0x180010d63  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010d68  nop
0x180010d69  mov     ebx, esi
0x180010d6b  lea     rcx, [rbp+57h+lpSubKey]
0x180010d6f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010d74  mov     eax, ebx
0x180010d76  mov     rcx, [rbp+57h+var_30]
0x180010d7a  xor     rcx, rsp; StackCookie
0x180010d7d  call    __security_check_cookie
0x180010d82  add     rsp, 98h
0x180010d89  pop     rdi
0x180010d8a  pop     rsi
0x180010d8b  pop     rbx
0x180010d8c  pop     rbp
0x180010d8d  retn
```
