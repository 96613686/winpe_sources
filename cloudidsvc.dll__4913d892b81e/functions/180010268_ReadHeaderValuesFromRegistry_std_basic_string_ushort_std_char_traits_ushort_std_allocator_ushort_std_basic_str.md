# ReadHeaderValuesFromRegistry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180010268`
- end: `0x180010482`
- name: `?ReadHeaderValuesFromRegistry@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b1d0`

## callees

- `0x180006d14`
- `0x180008d64`
- `0x18000a864`
- `0x18000c874`
- `0x18000ca74`
- `0x180010268`
- `0x180010488`
- `0x1800105f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800102b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800102b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001032e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001043e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001044d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001045c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001032e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001043e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001044d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001045c`

## string_xrefs

- `0x18001030f`: `onecoreuap\ds\ext\common\lib\registryhelpers\registryhelpers.cpp`
- `0x18001036d`: `onecoreuap\ds\ext\common\lib\registryhelpers\registryhelpers.cpp`
- `0x1800103c4`: `onecoreuap\ds\ext\common\lib\registryhelpers\registryhelpers.cpp`

## pseudocode

```c
__int64 __fastcall ReadHeaderValuesFromRegistry(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // r8d
  unsigned int v8; // ebx
  int RegistryString; // eax
  int v10; // eax
  int v11; // eax
  HLOCAL v12; // rbx
  __int64 v13; // rax
  HLOCAL v14; // rsi
  __int64 v15; // rax
  HLOCAL v16; // rdi
  __int64 v17; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  int phkResultb; // [rsp+20h] [rbp-30h]
  int phkResultc; // [rsp+20h] [rbp-30h]
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL v24; // [rsp+38h] [rbp-18h] BYREF
  HLOCAL v25[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY hkey; // [rsp+88h] [rbp+38h] BYREF

  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\TenantRestrictions\\Payload",
         0,
         0x20119u,
         &hkey);
  if ( v6 )
  {
    v8 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xBA, v7, (const char *)v6, phkResult);
    goto LABEL_21;
  }
  hMem = 0;
  RegistryString = ReadRegistryString(hkey, (__int64)&hMem);
  v8 = RegistryString;
  if ( RegistryString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\registryhelpers\\registryhelpers.cpp",
      (const char *)(unsigned int)RegistryString,
      phkResulta);
LABEL_5:
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_21;
  }
  v24 = 0;
  v10 = ReadRegistryString(hkey, (__int64)&v24);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\registryhelpers\\registryhelpers.cpp",
      (const char *)(unsigned int)v10,
      phkResultb);
LABEL_9:
    if ( v24 )
      LocalFree(v24);
    goto LABEL_5;
  }
  v25[0] = 0;
  v11 = ReadRegistryString(hkey, (__int64)v25);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\registryhelpers\\registryhelpers.cpp",
      (const char *)(unsigned int)v11,
      phkResultc);
    if ( v25[0] )
      LocalFree(v25[0]);
    goto LABEL_9;
  }
  v12 = hMem;
  v13 = std::_WChar_traits<unsigned short>::length(hMem);
  std::wstring::_Assign<unsigned short>(a1, v12, v13);
  v14 = v25[0];
  v15 = std::_WChar_traits<unsigned short>::length(v25[0]);
  std::wstring::_Assign<unsigned short>(a3, v14, v15);
  v16 = v24;
  v17 = std::_WChar_traits<unsigned short>::length(v24);
  std::wstring::_Assign<unsigned short>(a2, v16, v17);
  if ( v14 )
    LocalFree(v14);
  if ( v16 )
    LocalFree(v16);
  if ( v12 )
    LocalFree(v12);
  v8 = 0;
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v8;
}

```

## disassembly

```asm
0x180010268  mov     [rsp-18h+arg_0], rbx
0x18001026d  mov     [rsp-18h+arg_8], rsi
0x180010272  push    rbp
0x180010273  push    rdi
0x180010274  push    r14
0x180010276  mov     rbp, rsp
0x180010279  sub     rsp, 50h
0x18001027d  mov     rdi, r8
0x180010280  mov     r14, rdx
0x180010283  mov     rsi, rcx
0x180010286  mov     [rbp+hkey], 0
0x18001028e  xor     edx, edx
0x180010290  lea     rcx, [rbp+hkey]
0x180010294  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010299  lea     rax, [rbp+hkey]
0x18001029d  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x1800102a2  mov     r9d, 20119h; samDesired
0x1800102a8  xor     r8d, r8d; ulOptions
0x1800102ab  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800102b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800102b9  call    cs:__imp_RegOpenKeyExW
0x1800102bf  test    eax, eax
0x1800102c1  jz      short loc_1800102DB
0x1800102c3  mov     rcx, [rbp+18h]; this
0x1800102c7  mov     r9d, eax; char *
0x1800102ca  mov     edx, 0BAh; void *
0x1800102cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800102d4  mov     ebx, eax
0x1800102d6  jmp     loc_180010464
0x1800102db  mov     [rbp+hMem], 0
0x1800102e3  lea     rax, [rbp+hMem]
0x1800102e7  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800102ec  mov     r9d, 2
0x1800102f2  lea     r8, aCloudid; "cloudid"
0x1800102f9  mov     rcx, [rbp+hkey]; hkey
0x1800102fd  call    ?ReadRegistryString@@YAJPEAUHKEY__@@PEBG1KAEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@Z; ReadRegistryString(HKEY__ *,ushort const *,ushort const *,ulong,wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &)
0x180010302  mov     ebx, eax
0x180010304  test    eax, eax
0x180010306  jns     short loc_180010339
0x180010308  mov     rcx, [rbp+18h]; this
0x18001030c  mov     r9d, eax; char *
0x18001030f  lea     r8, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\common\\lib\\regis"...
0x180010316  mov     edx, 0C1h; void *
0x18001031b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010320  nop
0x180010321  mov     rcx, [rbp+hMem]; hMem
0x180010325  test    rcx, rcx
0x180010328  jz      loc_180010464
0x18001032e  call    cs:__imp_LocalFree
0x180010334  jmp     loc_180010464
0x180010339  mov     [rbp+var_18], 0
0x180010341  lea     rax, [rbp+var_18]
0x180010345  mov     qword ptr [rsp+50h+phkResult], rax; int
0x18001034a  mov     r9d, 2
0x180010350  lea     r8, aTenantid; "tenantid"
0x180010357  mov     rcx, [rbp+hkey]; hkey
0x18001035b  call    ?ReadRegistryString@@YAJPEAUHKEY__@@PEBG1KAEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@Z; ReadRegistryString(HKEY__ *,ushort const *,ushort const *,ulong,wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &)
0x180010360  mov     ebx, eax
0x180010362  test    eax, eax
0x180010364  jns     short loc_180010390
0x180010366  mov     rcx, [rbp+18h]; this
0x18001036a  mov     r9d, eax; char *
0x18001036d  lea     r8, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\common\\lib\\regis"...
0x180010374  mov     edx, 0C8h; void *
0x180010379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001037e  nop
0x18001037f  mov     rcx, [rbp+var_18]; hMem
0x180010383  test    rcx, rcx
0x180010386  jz      short loc_180010321
0x180010388  call    cs:__imp_LocalFree
0x18001038e  jmp     short loc_180010321
0x180010390  mov     [rbp+var_10], 0
0x180010398  lea     rax, [rbp+var_10]
0x18001039c  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800103a1  mov     r9d, 2
0x1800103a7  lea     r8, aPolicyid; "policyid"
0x1800103ae  mov     rcx, [rbp+hkey]; hkey
0x1800103b2  call    ?ReadRegistryString@@YAJPEAUHKEY__@@PEBG1KAEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@Z; ReadRegistryString(HKEY__ *,ushort const *,ushort const *,ulong,wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &)
0x1800103b7  mov     ebx, eax
0x1800103b9  test    eax, eax
0x1800103bb  jns     short loc_1800103E7
0x1800103bd  mov     rcx, [rbp+18h]; this
0x1800103c1  mov     r9d, eax; char *
0x1800103c4  lea     r8, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\common\\lib\\regis"...
0x1800103cb  mov     edx, 0CFh; void *
0x1800103d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103d5  nop
0x1800103d6  mov     rcx, [rbp+var_10]; hMem
0x1800103da  test    rcx, rcx
0x1800103dd  jz      short loc_18001037F
0x1800103df  call    cs:__imp_LocalFree
0x1800103e5  jmp     short loc_18001037F
0x1800103e7  mov     rbx, [rbp+hMem]
0x1800103eb  mov     rcx, rbx
0x1800103ee  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800103f3  mov     r8, rax
0x1800103f6  mov     rdx, rbx
0x1800103f9  mov     rcx, rsi
0x1800103fc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010401  mov     rsi, [rbp+var_10]
0x180010405  mov     rcx, rsi
0x180010408  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001040d  mov     r8, rax
0x180010410  mov     rdx, rsi
0x180010413  mov     rcx, rdi
0x180010416  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001041b  mov     rdi, [rbp+var_18]
0x18001041f  mov     rcx, rdi
0x180010422  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180010427  mov     r8, rax
0x18001042a  mov     rdx, rdi
0x18001042d  mov     rcx, r14
0x180010430  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180010435  nop
0x180010436  test    rsi, rsi
0x180010439  jz      short loc_180010445
0x18001043b  mov     rcx, rsi; hMem
0x18001043e  call    cs:__imp_LocalFree
0x180010444  nop
0x180010445  test    rdi, rdi
0x180010448  jz      short loc_180010454
0x18001044a  mov     rcx, rdi; hMem
0x18001044d  call    cs:__imp_LocalFree
0x180010453  nop
0x180010454  test    rbx, rbx
0x180010457  jz      short loc_180010462
0x180010459  mov     rcx, rbx; hMem
0x18001045c  call    cs:__imp_LocalFree
0x180010462  xor     ebx, ebx
0x180010464  lea     rcx, [rbp+hkey]
0x180010468  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001046d  mov     eax, ebx
0x18001046f  mov     rbx, [rsp+50h+arg_0]
0x180010474  mov     rsi, [rsp+50h+arg_8]
0x180010479  add     rsp, 50h
0x18001047d  pop     r14
0x18001047f  pop     rdi
0x180010480  pop     rbp
0x180010481  retn
```
