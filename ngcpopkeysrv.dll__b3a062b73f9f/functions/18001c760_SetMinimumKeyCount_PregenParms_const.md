# SetMinimumKeyCount(_PregenParms const *)

- ea: `0x18001c760`
- end: `0x18001c8cb`
- name: `?SetMinimumKeyCount@@YAJPEBU_PregenParms@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(const struct _PregenParms *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b950`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x18001069c`
- `0x180010730`
- `0x1800136b0`
- `0x1800153f0`
- `0x18001737c`
- `0x18001c760`
- `0x180022ef4`
- `0x18002308c`
- `0x180023318`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c7fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c7fc`

## string_xrefs

- `0x18001c79d`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c80d`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c860`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c894`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetMinimumKeyCount(const unsigned __int16 **a1)
{
  const unsigned __int16 *v2; // rdx
  NgcUtils *v3; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // ebx
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  int RegistryDwordValue; // eax
  unsigned int v9; // r9d
  int v10; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-30h]
  unsigned int *dwOptionsa; // [rsp+20h] [rbp-30h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  int v16; // [rsp+60h] [rbp+10h] BYREF
  NgcUtils *v17; // [rsp+68h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp+20h] BYREF

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v3,
                                        v2,
                                        a1[3],
                                        (unsigned __int16 *)&lpSubKey);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v17 = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v17);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
    if ( Key )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xCD,
             (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
             (const char *)Key,
             (unsigned int)dwOptionsa);
    }
    else
    {
      v16 = 0;
      RegistryDwordValue = NgcUtils::GetRegistryDwordValue(
                             v17,
                             0,
                             (const unsigned __int16 *)&stru_18002B260,
                             (const unsigned __int16 *)&v16,
                             dwOptionsa);
      if ( RegistryDwordValue >= 0 && v16 )
        goto LABEL_12;
      if ( RegistryDwordValue < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD7,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)RegistryDwordValue,
          dwOptionsb);
      v10 = NgcUtils::SetRegistryDwordValue(v17, (HKEY)&stru_18002B260, (const unsigned __int16 *)1, v9);
      v5 = v10;
      if ( v10 >= 0 )
      {
LABEL_12:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
        v5 = 0;
        goto LABEL_13;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v10,
        dwOptionsb);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      dwOptions);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  return v5;
}

```

## disassembly

```asm
0x18001c760  mov     [rsp-8+arg_18], rbx
0x18001c765  push    rbp
0x18001c766  mov     rbp, rsp
0x18001c769  sub     rsp, 50h
0x18001c76d  mov     rbx, rcx
0x18001c770  mov     [rbp+lpSubKey], 0
0x18001c778  xor     edx, edx
0x18001c77a  lea     rcx, [rbp+lpSubKey]
0x18001c77e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001c783  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x18001c787  mov     r8, [rbx+18h]; unsigned __int16 *
0x18001c78b  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001c790  mov     ebx, eax
0x18001c792  test    eax, eax
0x18001c794  jns     short loc_18001C7B3
0x18001c796  mov     rcx, [rbp+8]; this
0x18001c79a  mov     r9d, eax; char *
0x18001c79d  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c7a4  mov     edx, 0C1h; void *
0x18001c7a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7ae  jmp     loc_18001C8B5
0x18001c7b3  mov     [rbp+arg_8], 0
0x18001c7bb  lea     rcx, [rbp+arg_8]
0x18001c7bf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001c7c4  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x18001c7cd  mov     [rsp+50h+phkResult], rax; phkResult
0x18001c7d2  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001c7db  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x18001c7e3  mov     dword ptr [rsp+50h+dwOptions], 0; int
0x18001c7eb  xor     r9d, r9d; lpClass
0x18001c7ee  xor     r8d, r8d; Reserved
0x18001c7f1  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001c7f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c7fc  call    cs:__imp_RegCreateKeyExW
0x18001c802  test    eax, eax
0x18001c804  jz      short loc_18001C82E
0x18001c806  mov     rcx, [rbp+8]; this
0x18001c80a  mov     r9d, eax; char *
0x18001c80d  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c814  mov     edx, 0CDh; void *
0x18001c819  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c81e  mov     ebx, eax
0x18001c820  lea     rcx, [rbp+arg_8]
0x18001c824  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c829  jmp     loc_18001C8B5
0x18001c82e  mov     [rbp+arg_0], 0
0x18001c835  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x18001c839  lea     r8, stru_18002B260; unsigned __int16 *
0x18001c840  xor     edx, edx; HKEY
0x18001c842  mov     rcx, [rbp+arg_8]; this
0x18001c846  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001c84b  test    eax, eax
0x18001c84d  js      short loc_18001C855
0x18001c84f  cmp     [rbp+arg_0], 0
0x18001c853  jnz     short loc_18001C8AA
0x18001c855  mov     rcx, [rbp+8]; this
0x18001c859  test    eax, eax
0x18001c85b  jns     short loc_18001C871
0x18001c85d  mov     r9d, eax; char *
0x18001c860  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c867  mov     edx, 0D7h; void *
0x18001c86c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c871  mov     r8d, 1; unsigned __int16 *
0x18001c877  lea     rdx, stru_18002B260; HKEY
0x18001c87e  mov     rcx, [rbp+arg_8]; this
0x18001c882  call    ?SetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBGK@Z; NgcUtils::SetRegistryDwordValue(HKEY__ *,ushort const *,ulong)
0x18001c887  mov     ebx, eax
0x18001c889  test    eax, eax
0x18001c88b  jns     short loc_18001C8AA
0x18001c88d  mov     rcx, [rbp+8]; this
0x18001c891  mov     r9d, eax; char *
0x18001c894  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c89b  mov     edx, 0DCh; void *
0x18001c8a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8a5  jmp     loc_18001C820
0x18001c8aa  lea     rcx, [rbp+arg_8]
0x18001c8ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c8b3  xor     ebx, ebx
0x18001c8b5  lea     rcx, [rbp+lpSubKey]
0x18001c8b9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001c8be  mov     eax, ebx
0x18001c8c0  mov     rbx, [rsp+50h+arg_18]
0x18001c8c5  add     rsp, 50h
0x18001c8c9  pop     rbp
0x18001c8ca  retn
```
