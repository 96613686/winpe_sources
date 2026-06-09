# DeleteNestedPopKeys(ushort const *,ushort const *)

- ea: `0x180017404`
- end: `0x18001769e`
- name: `?DeleteNestedPopKeys@@YAJPEBG0@Z`
- size: `666`
- prototype: `__int64 __fastcall(const unsigned __int16 *, NgcUtils *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800176a4`

## callees

- `0x180004de0`
- `0x180005858`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x1800136b0`
- `0x180015288`
- `0x1800153f0`
- `0x18001737c`
- `0x180017404`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017577`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017577`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800175a1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800175a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174df`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001752c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001752c`

## string_xrefs

- `0x180017469`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x1800175f9`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x180017670`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeleteNestedPopKeys(const unsigned __int16 *a1, NgcUtils *a2)
{
  unsigned __int16 **v4; // r8
  int v5; // eax
  unsigned int v6; // ebx
  const WCHAR *v8; // rdi
  const unsigned __int16 *v9; // rax
  int v10; // r8d
  int v11; // ecx
  HKEY *v12; // rax
  unsigned int v13; // eax
  LSTATUS v14; // ebx
  LSTATUS v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rax
  const WCHAR *v18; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchValueName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName[3]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  v5 = NgcUtils::DuplicateString(a2, (const unsigned __int16 *)&lpSubKey, v4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = lpSubKey;
    while ( 1 )
    {
      v9 = a1;
      do
      {
        v10 = *(const unsigned __int16 *)((char *)v9 + (char *)v8 - (char *)a1);
        v11 = *v9 - v10;
        if ( v11 )
          break;
        ++v9;
      }
      while ( v10 );
      if ( !v11 )
        goto LABEL_23;
      hKey = 0;
      v12 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
      v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0xF003Fu, v12);
      if ( v13 )
        break;
      memset_0(ValueName, 0, 0x208u);
      cchValueName = 260;
      v14 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, 0, 0, 0);
      memset_0(Name, 0, 0x208u);
      cchName[0] = 260;
      v15 = RegEnumKeyExW(hKey, 0, Name, cchName, 0, 0, 0, 0);
      if ( v14 != 259 || v15 != 259 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_23:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
        return 0;
      }
      v16 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0);
      if ( v16 )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x46,
               (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
               (const char *)v16,
               phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
        return v6;
      }
      v17 = -1;
      do
        ++v17;
      while ( v8[v17] );
      v18 = &v8[v17 - 1];
      if ( *v18 == 92 )
        goto LABEL_19;
      do
      {
        if ( v18 == v8 )
          break;
        --v18;
      }
      while ( *v18 != 92 );
      if ( *v18 == 92 )
LABEL_19:
        *v18 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x24,
           (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
           (const char *)v13,
           phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  }
  return v6;
}

```

## disassembly

```asm
0x180017404  mov     [rsp-8+arg_0], rbx
0x180017409  mov     [rsp-8+arg_10], rsi
0x18001740e  push    rbp
0x18001740f  push    rdi
0x180017410  push    r14
0x180017412  lea     rbp, [rsp-390h]
0x18001741a  sub     rsp, 490h
0x180017421  mov     rax, cs:__security_cookie
0x180017428  xor     rax, rsp
0x18001742b  mov     [rbp+3A0h+var_20], rax
0x180017432  mov     rbx, rdx
0x180017435  mov     rsi, rcx
0x180017438  xor     r14d, r14d
0x18001743b  mov     [rsp+4A0h+lpSubKey], r14
0x180017440  xor     edx, edx
0x180017442  lea     rcx, [rsp+4A0h+lpSubKey]
0x180017447  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001744c  lea     rdx, [rsp+4A0h+lpSubKey]; unsigned __int16 *
0x180017451  mov     rcx, rbx; this
0x180017454  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x180017459  mov     ebx, eax
0x18001745b  test    eax, eax
0x18001745d  jns     short loc_18001748C
0x18001745f  mov     rcx, [rbp+3A8h]; this
0x180017466  mov     r9d, eax; char *
0x180017469  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017470  lea     edx, [r14+16h]; void *
0x180017474  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017479  nop
0x18001747a  lea     rcx, [rsp+4A0h+lpSubKey]
0x18001747f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017484  nop
0x180017485  mov     eax, ebx
0x180017487  jmp     loc_18001763F
0x18001748c  mov     rdi, [rsp+4A0h+lpSubKey]
0x180017491  mov     rax, rsi
0x180017494  mov     rdx, rdi
0x180017497  sub     rdx, rsi
0x18001749a  movzx   ecx, word ptr [rax]
0x18001749d  movzx   r8d, word ptr [rax+rdx]
0x1800174a2  sub     ecx, r8d
0x1800174a5  jnz     short loc_1800174B0
0x1800174a7  add     rax, 2
0x1800174ab  test    r8d, r8d
0x1800174ae  jnz     short loc_18001749A
0x1800174b0  test    ecx, ecx
0x1800174b2  jz      loc_180017632
0x1800174b8  mov     [rsp+4A0h+hKey], r14
0x1800174bd  lea     rcx, [rsp+4A0h+hKey]
0x1800174c2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800174c7  mov     [rsp+4A0h+phkResult], rax; unsigned int
0x1800174cc  mov     r9d, 0F003Fh; samDesired
0x1800174d2  xor     r8d, r8d; ulOptions
0x1800174d5  mov     rdx, rdi; lpSubKey
0x1800174d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800174df  call    cs:__imp_RegOpenKeyExW
0x1800174e5  test    eax, eax
0x1800174e7  jnz     loc_180017666
0x1800174ed  xor     edx, edx; Val
0x1800174ef  mov     r8d, 208h; Size
0x1800174f5  lea     rcx, [rsp+4A0h+ValueName]; void *
0x1800174fa  call    memset_0
0x1800174ff  mov     [rsp+4A0h+cchValueName], 104h
0x180017507  mov     [rsp+4A0h+lpcbData], r14; lpcbData
0x18001750c  mov     [rsp+4A0h+lpData], r14; lpData
0x180017511  mov     [rsp+4A0h+lpType], r14; lpType
0x180017516  mov     [rsp+4A0h+phkResult], r14; lpReserved
0x18001751b  lea     r9, [rsp+4A0h+cchValueName]; lpcchValueName
0x180017520  lea     r8, [rsp+4A0h+ValueName]; lpValueName
0x180017525  xor     edx, edx; dwIndex
0x180017527  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001752c  call    cs:__imp_RegEnumValueW
0x180017532  mov     ebx, eax
0x180017534  xor     edx, edx; Val
0x180017536  mov     r8d, 208h; Size
0x18001753c  lea     rcx, [rbp+3A0h+Name]; void *
0x180017543  call    memset_0
0x180017548  mov     [rsp+4A0h+cchName], 104h
0x180017550  mov     [rsp+4A0h+lpcbData], r14; lpftLastWriteTime
0x180017555  mov     [rsp+4A0h+lpData], r14; lpcchClass
0x18001755a  mov     [rsp+4A0h+lpType], r14; lpClass
0x18001755f  mov     [rsp+4A0h+phkResult], r14; unsigned int
0x180017564  lea     r9, [rsp+4A0h+cchName]; lpcchName
0x180017569  lea     r8, [rbp+3A0h+Name]; lpName
0x180017570  xor     edx, edx; dwIndex
0x180017572  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180017577  call    cs:__imp_RegEnumKeyExW
0x18001757d  cmp     ebx, 103h
0x180017583  jnz     loc_180017627
0x180017589  cmp     eax, ebx
0x18001758b  jnz     loc_180017627
0x180017591  xor     r9d, r9d; Reserved
0x180017594  xor     r8d, r8d; samDesired
0x180017597  mov     rdx, rdi; lpSubKey
0x18001759a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800175a1  call    cs:__imp_RegDeleteKeyExW
0x1800175a7  test    eax, eax
0x1800175a9  jnz     short loc_1800175EF
0x1800175ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800175af  inc     rax
0x1800175b2  cmp     [rdi+rax*2], r14w
0x1800175b7  jnz     short loc_1800175AF
0x1800175b9  lea     rcx, [rdi-2]
0x1800175bd  lea     rcx, [rcx+rax*2]
0x1800175c1  cmp     word ptr [rcx], 5Ch ; '\'
0x1800175c5  jz      short loc_1800175DC
0x1800175c7  cmp     rcx, rdi
0x1800175ca  jz      short loc_1800175D6
0x1800175cc  sub     rcx, 2
0x1800175d0  cmp     word ptr [rcx], 5Ch ; '\'
0x1800175d4  jnz     short loc_1800175C7
0x1800175d6  cmp     word ptr [rcx], 5Ch ; '\'
0x1800175da  jnz     short loc_1800175E0
0x1800175dc  mov     [rcx], r14w
0x1800175e0  lea     rcx, [rsp+4A0h+hKey]
0x1800175e5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800175ea  jmp     loc_180017491
0x1800175ef  mov     rcx, [rbp+3A8h]; this
0x1800175f6  mov     r9d, eax; char *
0x1800175f9  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017600  mov     edx, 46h ; 'F'; void *
0x180017605  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001760a  mov     ebx, eax
0x18001760c  lea     rcx, [rsp+4A0h+hKey]
0x180017611  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017616  nop
0x180017617  lea     rcx, [rsp+4A0h+lpSubKey]
0x18001761c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017621  nop
0x180017622  jmp     loc_180017485
0x180017627  lea     rcx, [rsp+4A0h+hKey]
0x18001762c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017631  nop
0x180017632  lea     rcx, [rsp+4A0h+lpSubKey]
0x180017637  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001763c  nop
0x18001763d  xor     eax, eax
0x18001763f  mov     rcx, [rbp+3A0h+var_20]
0x180017646  xor     rcx, rsp; StackCookie
0x180017649  call    __security_check_cookie
0x18001764e  lea     r11, [rsp+4A0h+var_10]
0x180017656  mov     rbx, [r11+20h]
0x18001765a  mov     rsi, [r11+30h]
0x18001765e  mov     rsp, r11
0x180017661  pop     r14
0x180017663  pop     rdi
0x180017664  pop     rbp
0x180017665  retn
0x180017666  mov     rcx, [rbp+3A8h]; this
0x18001766d  mov     r9d, eax; char *
0x180017670  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017677  mov     edx, 24h ; '$'; void *
0x18001767c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017681  mov     ebx, eax
0x180017683  lea     rcx, [rsp+4A0h+hKey]
0x180017688  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001768d  nop
0x18001768e  lea     rcx, [rsp+4A0h+lpSubKey]
0x180017693  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017698  nop
0x180017699  jmp     loc_180017485
```
