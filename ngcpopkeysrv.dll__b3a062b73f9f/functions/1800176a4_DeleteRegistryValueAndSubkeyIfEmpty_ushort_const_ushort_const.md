# DeleteRegistryValueAndSubkeyIfEmpty(ushort const *,ushort const *)

- ea: `0x1800176a4`
- end: `0x1800177ed`
- name: `?DeleteRegistryValueAndSubkeyIfEmpty@@YAJPEBG0@Z`
- size: `329`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001923c`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x1800136b0`
- `0x1800153f0`
- `0x18001737c`
- `0x180017404`
- `0x1800176a4`
- `0x180022ef4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017711`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017711`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800176df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800176df`

## string_xrefs

- `0x1800176f1`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x180017723`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x180017770`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x1800177aa`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeleteRegistryValueAndSubkeyIfEmpty(const unsigned __int16 *a1, LPCWSTR lpValueName)
{
  HKEY *v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  const unsigned __int16 *v8; // rdx
  NgcUtils *v9; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  int v11; // eax
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-28h]
  int phkResulta; // [rsp+20h] [rbp-28h]
  unsigned __int16 *v15; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  hKey[0] = 0;
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a1, 0, 0xF003Fu, v4);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x6A,
           (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
           (const char *)v5,
           (unsigned int)phkResult);
  }
  else
  {
    v7 = RegDeleteValueW(hKey[0], lpValueName);
    if ( v7 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x6E,
             (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
             (const char *)v7,
             (unsigned int)phkResult);
    }
    else
    {
      v15 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v15,
        0);
      NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                            v9,
                                            v8,
                                            L"KeyTransportKey",
                                            (const unsigned __int16 *)&v15,
                                            phkResult);
      v6 = NgcStateSeparatedRegistryLocation;
      if ( NgcStateSeparatedRegistryLocation >= 0 )
      {
        v11 = DeleteNestedPopKeys(v15, a1);
        v6 = v11;
        if ( v11 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
          v6 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x79,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
            (const char *)(unsigned int)v11,
            phkResulta);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
          (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
          phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800176a4  mov     [rsp+arg_0], rbx
0x1800176a9  push    rdi
0x1800176aa  sub     rsp, 40h
0x1800176ae  mov     rbx, rdx
0x1800176b1  mov     rdi, rcx
0x1800176b4  mov     [rsp+48h+hKey], 0
0x1800176bd  lea     rcx, [rsp+48h+hKey]
0x1800176c2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800176c7  mov     [rsp+48h+phkResult], rax; int
0x1800176cc  mov     r9d, 0F003Fh; samDesired
0x1800176d2  xor     r8d, r8d; ulOptions
0x1800176d5  mov     rdx, rdi; lpSubKey
0x1800176d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800176df  call    cs:__imp_RegOpenKeyExW
0x1800176e5  test    eax, eax
0x1800176e7  jz      short loc_180017709
0x1800176e9  mov     rcx, [rsp+48h]; this
0x1800176ee  mov     r9d, eax; char *
0x1800176f1  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800176f8  mov     edx, 6Ah ; 'j'; void *
0x1800176fd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017702  mov     ebx, eax
0x180017704  jmp     loc_1800177D6
0x180017709  mov     rdx, rbx; lpValueName
0x18001770c  mov     rcx, [rsp+48h+hKey]; hKey
0x180017711  call    cs:__imp_RegDeleteValueW
0x180017717  test    eax, eax
0x180017719  jz      short loc_18001773C
0x18001771b  mov     rcx, [rsp+48h]; this
0x180017720  mov     r9d, eax; char *
0x180017723  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001772a  mov     edx, 6Eh ; 'n'; void *
0x18001772f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017734  nop
0x180017735  mov     ebx, eax
0x180017737  jmp     loc_1800177D6
0x18001773c  mov     [rsp+48h+var_18], 0
0x180017745  xor     edx, edx
0x180017747  lea     rcx, [rsp+48h+var_18]
0x18001774c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180017751  lea     r9, [rsp+48h+var_18]; unsigned __int16 *
0x180017756  lea     r8, aKeytransportke; "KeyTransportKey"
0x18001775d  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180017762  mov     ebx, eax
0x180017764  test    eax, eax
0x180017766  jns     short loc_18001778F
0x180017768  mov     rcx, [rsp+48h]; this
0x18001776d  mov     r9d, eax; char *
0x180017770  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017777  mov     edx, 73h ; 's'; void *
0x18001777c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017781  nop
0x180017782  lea     rcx, [rsp+48h+var_18]
0x180017787  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001778c  nop
0x18001778d  jmp     short loc_1800177D6
0x18001778f  mov     rdx, rdi; unsigned __int16 *
0x180017792  mov     rcx, [rsp+48h+var_18]; unsigned __int16 *
0x180017797  call    ?DeleteNestedPopKeys@@YAJPEBG0@Z; DeleteNestedPopKeys(ushort const *,ushort const *)
0x18001779c  mov     ebx, eax
0x18001779e  test    eax, eax
0x1800177a0  jns     short loc_1800177C9
0x1800177a2  mov     rcx, [rsp+48h]; this
0x1800177a7  mov     r9d, eax; char *
0x1800177aa  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800177b1  mov     edx, 79h ; 'y'; void *
0x1800177b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800177bb  nop
0x1800177bc  lea     rcx, [rsp+48h+var_18]
0x1800177c1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800177c6  nop
0x1800177c7  jmp     short loc_1800177D6
0x1800177c9  lea     rcx, [rsp+48h+var_18]
0x1800177ce  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800177d3  nop
0x1800177d4  xor     ebx, ebx
0x1800177d6  lea     rcx, [rsp+48h+hKey]
0x1800177db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800177e0  mov     eax, ebx
0x1800177e2  mov     rbx, [rsp+48h+arg_0]
0x1800177e7  add     rsp, 40h
0x1800177eb  pop     rdi
0x1800177ec  retn
```
