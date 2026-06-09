# EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(ulong *,ushort * * *,EnrollmentStateTag,EnrollmentStateTag,unsigned __int64,ushort const *,int,int)

- ea: `0x18000f0ec`
- end: `0x18000f569`
- name: `?GetAllEnrollmentIDsFiltered@EnrollmentInfoEnumerator@@AEAAJPEAKPEAPEAPEAGW4EnrollmentStateTag@@2_KPEBGHH@Z`
- size: `1149`
- prototype: `__int64 __fastcall(__int64, DWORD *, _QWORD *, int, int, __int64, __int64, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f570`

## callees

- `0x180001a70`
- `0x180002554`
- `0x180005aec`
- `0x18000bcf8`
- `0x18000dcd8`
- `0x18000dd1c`
- `0x18000e938`
- `0x18000ec08`
- `0x18000ec2c`
- `0x18000eecc`
- `0x18000eff0`
- `0x18000f0ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f44d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f44d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000f466`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000f466`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f21d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f27b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f21d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f27b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f51e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f51e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f36f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f3b4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f36f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f3b4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f2ce`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f2ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f1db`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f1db`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f478`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f478`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4e8`

## pseudocode

```c
__int64 __fastcall EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(
        __int64 a1,
        DWORD *a2,
        _QWORD *a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9)
{
  DWORD v9; // esi
  LSTATUS v12; // eax
  int v13; // ebx
  LSTATUS InfoKeyW; // eax
  size_t v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // r14
  WCHAR *v18; // rdi
  __int64 v19; // rcx
  DWORD v20; // r12d
  LSTATUS v21; // eax
  const unsigned __int16 *EnrollmentsRootKey; // rax
  __int64 v23; // rdx
  __int64 v24; // r9
  unsigned __int16 *v25; // rcx
  const WCHAR *v26; // rdx
  unsigned __int8 v27; // si
  int v29; // eax
  __int64 v30; // r8
  BSTR v31; // rax
  OLECHAR *v32; // rcx
  SIZE_T cb; // [rsp+60h] [rbp-A0h] BYREF
  SIZE_T pvData; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v36; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v38; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v42; // [rsp+98h] [rbp-68h] BYREF
  int v43; // [rsp+9Ch] [rbp-64h]
  HKEY v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  _QWORD v46[2]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  v9 = 0;
  v43 = a4;
  v45 = a7;
  cb = 0;
  pvData = 0;
  hKey = 0;
  v44 = 0;
  v46[0] = 0;
  hkey = 0;
  SubKey[0] = 0;
  if ( !a2 || !a3 )
  {
    v13 = -2147024809;
    goto LABEL_57;
  }
  *a2 = 0;
  *a3 = 0;
  v12 = EEDBManager::OpenEnrollmentsHKEY(a1, &v44);
  v13 = v12;
  if ( v12 == -2147024894 )
  {
    v13 = 0;
    goto LABEL_57;
  }
  if ( v12 < 0 )
    goto LABEL_57;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    v44);
  InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)&pvData + 1, (LPDWORD)&cb + 1, 0, 0, 0, 0, 0, 0);
  v13 = InfoKeyW;
  if ( InfoKeyW )
  {
    if ( InfoKeyW > 0 )
      v13 = (unsigned __int16)InfoKeyW | 0x80070000;
    goto LABEL_57;
  }
  v13 = ULongLongToULong(8LL * HIDWORD(pvData), (unsigned int *)&cb);
  if ( v13 < 0 )
    goto LABEL_57;
  v15 = (unsigned int)cb;
  v16 = CoTaskMemAlloc((unsigned int)cb);
  v17 = v16;
  if ( !v16 )
  {
    v13 = -2147024882;
    goto LABEL_57;
  }
  v18 = 0;
  memset_0(v16, 0, v15);
  v19 = (unsigned int)(HIDWORD(cb) + 1);
  if ( (unsigned int)v19 < HIDWORD(cb) )
  {
    HIDWORD(cb) = -1;
    v13 = -2147024362;
  }
  else
  {
    ++HIDWORD(cb);
    v20 = 0;
    v13 = ULongLongToULong(2 * v19, (unsigned int *)&pvData);
    if ( v13 >= 0 )
    {
      v18 = (WCHAR *)CoTaskMemAlloc((unsigned int)pvData);
      if ( !v18 )
      {
        v13 = -2147024882;
        goto LABEL_54;
      }
      while ( 1 )
      {
        LODWORD(cb) = v9;
        if ( v9 >= HIDWORD(pvData) )
        {
          *a2 = v20;
          *a3 = v17;
          goto LABEL_55;
        }
        cchName = HIDWORD(cb);
        *v18 = 0;
        v21 = RegEnumKeyExW(hKey, v9, v18, &cchName, 0, 0, 0, 0);
        v13 = v21;
        if ( v21 )
          break;
        EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
        v13 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", EnrollmentsRootKey, v18);
        if ( v13 < 0 )
        {
          v9 = 0;
          goto LABEL_48;
        }
        v13 = EEDBManager::OpenHKEY(SubKey, v23, &hkey);
        if ( v13 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            v46,
            hkey);
          LODWORD(pvData) = 0;
          pcbData = 4;
          if ( !RegGetValueW(hkey, 0, L"EnrollmentState", 0x18u, 0, &pvData, &pcbData) )
          {
            v36 = 0;
            v42 = 4;
            RegGetValueW(hkey, 0, L"EnrollmentType", 0x18u, 0, &v36, &v42);
            v24 = v45;
            v25 = 0;
            v38 = 0;
            if ( v45 )
            {
              v26 = L"PartnerOpaqueID";
              if ( !a8 )
                v26 = L"AADOpaqueID";
              AllocAndGetEnrollmentString(hkey, v26, &v38);
              v25 = v38;
              v24 = v45;
            }
            if ( (_DWORD)pvData != 63 )
            {
              v27 = 0;
              if ( (_DWORD)pvData != a5 )
              {
                v27 = _bittest64(&a6, v36);
                if ( (_DWORD)pvData == v43 )
                  v27 = 1;
              }
              if ( v24 && v25 )
              {
                if ( a9 )
                {
                  v30 = -1;
                  do
                    ++v30;
                  while ( *(_WORD *)(v24 + 2 * v30) );
                  v29 = _o__wcsnicmp(v25, v24);
                }
                else
                {
                  v29 = _o__wcsicmp(v25, v24);
                }
                if ( !v29 )
                  goto LABEL_38;
              }
              if ( v27 )
              {
LABEL_38:
                v31 = SysAllocString(v18);
                v9 = 0;
                v17[v20] = v31;
                if ( !v31 )
                {
                  v13 = -2147024882;
                  CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v38);
                  goto LABEL_48;
                }
                ++v20;
              }
              v9 = cb;
            }
            CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v38);
          }
        }
        ++v9;
      }
      v9 = 0;
      if ( v21 > 0 )
        v13 = (unsigned __int16)v21 | 0x80070000;
    }
LABEL_48:
    if ( v20 )
    {
      do
      {
        v32 = (OLECHAR *)v17[v9];
        if ( v32 )
        {
          SysFreeString(v32);
          v17[v9] = 0;
        }
        ++v9;
      }
      while ( v9 < v20 );
    }
  }
LABEL_54:
  CoTaskMemFree(v17);
  if ( v18 )
LABEL_55:
    CoTaskMemFree(v18);
LABEL_57:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v46);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000f0ec  mov     [rsp-8+arg_0], rbx
0x18000f0f1  push    rbp
0x18000f0f2  push    rsi
0x18000f0f3  push    rdi
0x18000f0f4  push    r12
0x18000f0f6  push    r13
0x18000f0f8  push    r14
0x18000f0fa  push    r15
0x18000f0fc  lea     rbp, [rsp-1E0h]
0x18000f104  sub     rsp, 2E0h
0x18000f10b  mov     rax, cs:__security_cookie
0x18000f112  xor     rax, rsp
0x18000f115  mov     [rbp+210h+var_40], rax
0x18000f11c  mov     rax, [rbp+210h+arg_30]
0x18000f123  xor     esi, esi
0x18000f125  mov     [rbp+210h+var_274], r9d
0x18000f129  mov     r15, r8
0x18000f12c  mov     [rbp+210h+var_268], rax
0x18000f130  mov     r13, rdx
0x18000f133  mov     dword ptr [rsp+310h+pvData+4], esi
0x18000f137  mov     dword ptr [rsp+310h+cb+4], esi
0x18000f13b  mov     dword ptr [rsp+310h+cb], esi
0x18000f13f  mov     dword ptr [rsp+310h+pvData], esi
0x18000f143  mov     [rbp+210h+hKey], rsi
0x18000f147  mov     [rbp+210h+var_270], rsi
0x18000f14b  mov     [rbp+210h+var_260], rsi
0x18000f14f  mov     [rsp+310h+hkey], rsi
0x18000f154  mov     [rbp+210h+SubKey], si
0x18000f158  test    rdx, rdx
0x18000f15b  jz      loc_18000F526
0x18000f161  test    r8, r8
0x18000f164  jz      loc_18000F526
0x18000f16a  mov     [rdx], esi
0x18000f16c  lea     rdx, [rbp+210h+var_270]; HKEY *
0x18000f170  mov     [r8], rsi
0x18000f173  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x18000f178  mov     ebx, eax
0x18000f17a  cmp     eax, 80070002h
0x18000f17f  jnz     short loc_18000F188
0x18000f181  mov     ebx, esi
0x18000f183  jmp     loc_18000F52B
0x18000f188  test    eax, eax
0x18000f18a  js      loc_18000F52B
0x18000f190  mov     rdx, [rbp+210h+var_270]
0x18000f194  lea     rcx, [rbp+210h+hKey]
0x18000f198  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000f19d  mov     rcx, [rbp+210h+hKey]; hKey
0x18000f1a1  lea     rax, [rsp+310h+cb+4]
0x18000f1a6  mov     [rsp+310h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18000f1ab  xor     r9d, r9d; lpReserved
0x18000f1ae  mov     [rsp+310h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18000f1b3  xor     r8d, r8d; lpcchClass
0x18000f1b6  mov     [rsp+310h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18000f1bb  xor     edx, edx; lpClass
0x18000f1bd  mov     [rsp+310h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18000f1c2  mov     [rsp+310h+lpcValues], rsi; lpcValues
0x18000f1c7  mov     [rsp+310h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18000f1cc  mov     [rsp+310h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000f1d1  lea     rax, [rsp+310h+pvData+4]
0x18000f1d6  mov     [rsp+310h+lpcSubKeys], rax; lpcSubKeys
0x18000f1db  call    cs:__imp_RegQueryInfoKeyW
0x18000f1e1  mov     ebx, eax
0x18000f1e3  test    eax, eax
0x18000f1e5  jz      short loc_18000F1FB
0x18000f1e7  jle     loc_18000F52B
0x18000f1ed  movzx   ebx, ax
0x18000f1f0  or      ebx, 80070000h
0x18000f1f6  jmp     loc_18000F52B
0x18000f1fb  mov     ecx, dword ptr [rsp+310h+pvData+4]
0x18000f1ff  lea     rdx, [rsp+310h+cb]; unsigned int *
0x18000f204  shl     rcx, 3; unsigned __int64
0x18000f208  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000f20d  mov     ebx, eax
0x18000f20f  test    eax, eax
0x18000f211  js      loc_18000F52B
0x18000f217  mov     ebx, dword ptr [rsp+310h+cb]
0x18000f21b  mov     ecx, ebx; cb
0x18000f21d  call    cs:__imp_CoTaskMemAlloc
0x18000f223  mov     r14, rax
0x18000f226  test    rax, rax
0x18000f229  jnz     short loc_18000F235
0x18000f22b  mov     ebx, 8007000Eh
0x18000f230  jmp     loc_18000F52B
0x18000f235  mov     r8, rbx; Size
0x18000f238  xor     edx, edx; Val
0x18000f23a  mov     rcx, r14; void *
0x18000f23d  mov     rdi, rsi
0x18000f240  call    memset_0
0x18000f245  mov     eax, dword ptr [rsp+310h+cb+4]
0x18000f249  lea     ecx, [rax+1]
0x18000f24c  cmp     ecx, eax
0x18000f24e  jb      loc_18000F500
0x18000f254  mov     dword ptr [rsp+310h+cb+4], ecx
0x18000f258  lea     rdx, [rsp+310h+pvData]; unsigned int *
0x18000f25d  add     rcx, rcx; unsigned __int64
0x18000f260  mov     r12d, esi
0x18000f263  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000f268  mov     ebx, eax
0x18000f26a  mov     eax, 1
0x18000f26f  test    ebx, ebx
0x18000f271  js      loc_18000F4D4
0x18000f277  mov     ecx, dword ptr [rsp+310h+pvData]; cb
0x18000f27b  call    cs:__imp_CoTaskMemAlloc
0x18000f281  mov     rdi, rax
0x18000f284  test    rax, rax
0x18000f287  jnz     short loc_18000F293
0x18000f289  mov     ebx, 8007000Eh
0x18000f28e  jmp     loc_18000F50D
0x18000f293  mov     dword ptr [rsp+310h+cb], esi
0x18000f297  cmp     esi, dword ptr [rsp+310h+pvData+4]
0x18000f29b  jnb     loc_18000F4C4
0x18000f2a1  mov     eax, dword ptr [rsp+310h+cb+4]
0x18000f2a5  lea     r9, [rbp+210h+cchName]; lpcchName
0x18000f2a9  xor     ecx, ecx
0x18000f2ab  mov     [rbp+210h+cchName], eax
0x18000f2ae  mov     [rsp+310h+lpcValues], rcx; lpftLastWriteTime
0x18000f2b3  mov     r8, rdi; lpName
0x18000f2b6  mov     [rsp+310h+lpcbMaxClassLen], rcx; lpcchClass
0x18000f2bb  mov     edx, esi; dwIndex
0x18000f2bd  mov     [rsp+310h+lpcbMaxSubKeyLen], rcx; lpClass
0x18000f2c2  mov     [rsp+310h+lpcSubKeys], rcx; lpReserved
0x18000f2c7  mov     [rdi], cx
0x18000f2ca  mov     rcx, [rbp+210h+hKey]; hKey
0x18000f2ce  call    cs:__imp_RegEnumKeyExW
0x18000f2d4  mov     ebx, eax
0x18000f2d6  test    eax, eax
0x18000f2d8  jnz     loc_18000F4B3
0x18000f2de  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18000f2e3  mov     r9, rax
0x18000f2e6  mov     [rsp+310h+lpcSubKeys], rdi
0x18000f2eb  lea     r8, aSS; "%s\\%s"
0x18000f2f2  mov     edx, 104h; unsigned __int64
0x18000f2f7  lea     rcx, [rbp+210h+SubKey]; unsigned __int16 *
0x18000f2fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f300  mov     ebx, eax
0x18000f302  test    eax, eax
0x18000f304  js      loc_18000F4CD
0x18000f30a  lea     r8, [rsp+310h+hkey]; HKEY *
0x18000f30f  lea     rcx, [rbp+210h+SubKey]; lpSubKey
0x18000f313  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x18000f318  mov     ebx, eax
0x18000f31a  test    eax, eax
0x18000f31c  js      loc_18000F49C
0x18000f322  mov     rdx, [rsp+310h+hkey]
0x18000f327  lea     rcx, [rbp+210h+var_260]
0x18000f32b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000f330  mov     rcx, [rsp+310h+hkey]; hkey
0x18000f335  lea     rax, [rbp+210h+pcbData]
0x18000f339  mov     [rsp+310h+lpcbMaxClassLen], rax; pcbData
0x18000f33e  lea     r8, ValueName; "EnrollmentState"
0x18000f345  lea     rax, [rsp+310h+pvData]
0x18000f34a  mov     dword ptr [rsp+310h+pvData], 0
0x18000f352  mov     [rsp+310h+lpcbMaxSubKeyLen], rax; pvData
0x18000f357  mov     r9d, 18h; dwFlags
0x18000f35d  xor     edx, edx; lpSubKey
0x18000f35f  mov     [rsp+310h+lpcSubKeys], 0; pdwType
0x18000f368  mov     [rbp+210h+pcbData], 4
0x18000f36f  call    cs:__imp_RegGetValueW
0x18000f375  xor     ecx, ecx
0x18000f377  test    eax, eax
0x18000f379  jnz     loc_18000F49C
0x18000f37f  lea     rax, [rbp+210h+var_278]
0x18000f383  mov     [rsp+310h+var_2A0], ecx
0x18000f387  mov     [rsp+310h+lpcbMaxClassLen], rax; pcbData
0x18000f38c  lea     r9d, [rcx+18h]; dwFlags
0x18000f390  lea     rax, [rsp+310h+var_2A0]
0x18000f395  mov     [rbp+210h+var_278], 4
0x18000f39c  mov     [rsp+310h+lpcbMaxSubKeyLen], rax; pvData
0x18000f3a1  lea     r8, aEnrollmenttype; "EnrollmentType"
0x18000f3a8  mov     [rsp+310h+lpcSubKeys], rcx; pdwType
0x18000f3ad  xor     edx, edx; lpSubKey
0x18000f3af  mov     rcx, [rsp+310h+hkey]; hkey
0x18000f3b4  call    cs:__imp_RegGetValueW
0x18000f3ba  mov     r9, [rbp+210h+var_268]
0x18000f3be  xor     r10d, r10d
0x18000f3c1  mov     ecx, r10d
0x18000f3c4  mov     [rbp+210h+var_290], rcx
0x18000f3c8  test    r9, r9
0x18000f3cb  jz      short loc_18000F3FF
0x18000f3cd  cmp     [rbp+210h+arg_38], r10d
0x18000f3d4  lea     rax, aAadopaqueid; "AADOpaqueID"
0x18000f3db  mov     rcx, [rsp+310h+hkey]; hkey
0x18000f3e0  lea     rdx, aPartneropaquei; "PartnerOpaqueID"
0x18000f3e7  cmovz   rdx, rax; lpValue
0x18000f3eb  lea     r8, [rbp+210h+var_290]; unsigned __int16 **
0x18000f3ef  call    ?AllocAndGetEnrollmentString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; AllocAndGetEnrollmentString(HKEY__ *,ushort const *,ushort * *)
0x18000f3f4  mov     rcx, [rbp+210h+var_290]
0x18000f3f8  xor     r10d, r10d
0x18000f3fb  mov     r9, [rbp+210h+var_268]
0x18000f3ff  mov     edx, dword ptr [rsp+310h+pvData]
0x18000f403  cmp     edx, 3Fh ; '?'
0x18000f406  jz      loc_18000F493
0x18000f40c  mov     sil, r10b
0x18000f40f  cmp     edx, [rbp+210h+arg_20]
0x18000f415  jz      short loc_18000F437
0x18000f417  mov     eax, [rsp+310h+var_2A0]
0x18000f41b  mov     r8, [rbp+210h+arg_28]
0x18000f422  bt      r8, rax
0x18000f426  setb    al
0x18000f429  cmp     edx, [rbp+210h+var_274]
0x18000f42c  movzx   esi, al
0x18000f42f  mov     eax, 1
0x18000f434  cmovz   esi, eax
0x18000f437  test    r9, r9
0x18000f43a  jz      short loc_18000F470
0x18000f43c  test    rcx, rcx
0x18000f43f  jz      short loc_18000F470
0x18000f441  cmp     [rbp+210h+arg_40], r10d
0x18000f448  jnz     short loc_18000F455
0x18000f44a  mov     rdx, r9
0x18000f44d  call    cs:__imp__o__wcsicmp
0x18000f453  jmp     short loc_18000F46C
0x18000f455  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f459  inc     r8
0x18000f45c  cmp     [r9+r8*2], r10w
0x18000f461  jnz     short loc_18000F459
0x18000f463  mov     rdx, r9
0x18000f466  call    cs:__imp__o__wcsnicmp
0x18000f46c  test    eax, eax
0x18000f46e  jz      short loc_18000F475
0x18000f470  test    sil, sil
0x18000f473  jz      short loc_18000F48F
0x18000f475  mov     rcx, rdi; psz
0x18000f478  call    cs:__imp_SysAllocString
0x18000f47e  mov     ecx, r12d
0x18000f481  xor     esi, esi
0x18000f483  mov     [r14+rcx*8], rax
0x18000f487  test    rax, rax
0x18000f48a  jz      short loc_18000F4A3
0x18000f48c  inc     r12d
0x18000f48f  mov     esi, dword ptr [rsp+310h+cb]
0x18000f493  lea     rcx, [rbp+210h+var_290]
0x18000f497  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18000f49c  inc     esi
0x18000f49e  jmp     loc_18000F293
0x18000f4a3  lea     rcx, [rbp+210h+var_290]
0x18000f4a7  mov     ebx, 8007000Eh
0x18000f4ac  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18000f4b1  jmp     short loc_18000F4CF
0x18000f4b3  xor     esi, esi
0x18000f4b5  test    eax, eax
0x18000f4b7  jle     short loc_18000F4CF
0x18000f4b9  movzx   ebx, ax
0x18000f4bc  or      ebx, 80070000h
0x18000f4c2  jmp     short loc_18000F4CF
0x18000f4c4  mov     [r13+0], r12d
0x18000f4c8  mov     [r15], r14
0x18000f4cb  jmp     short loc_18000F51B
0x18000f4cd  xor     esi, esi
0x18000f4cf  mov     eax, 1
0x18000f4d4  xor     r13d, r13d
0x18000f4d7  test    r12d, r12d
0x18000f4da  jz      short loc_18000F50D
0x18000f4dc  mov     r15d, esi
0x18000f4df  mov     rcx, [r14+r15*8]; bstrString
0x18000f4e3  test    rcx, rcx
0x18000f4e6  jz      short loc_18000F4F7
0x18000f4e8  call    cs:__imp_SysFreeString
0x18000f4ee  mov     eax, 1
0x18000f4f3  mov     [r14+r15*8], r13
0x18000f4f7  add     esi, eax
0x18000f4f9  cmp     esi, r12d
0x18000f4fc  jb      short loc_18000F4DC
0x18000f4fe  jmp     short loc_18000F50D
0x18000f500  mov     dword ptr [rsp+310h+cb+4], 0FFFFFFFFh
0x18000f508  mov     ebx, 80070216h
0x18000f50d  mov     rcx, r14; pv
0x18000f510  call    cs:__imp_CoTaskMemFree
0x18000f516  test    rdi, rdi
0x18000f519  jz      short loc_18000F52B
0x18000f51b  mov     rcx, rdi; pv
0x18000f51e  call    cs:__imp_CoTaskMemFree
0x18000f524  jmp     short loc_18000F52B
0x18000f526  mov     ebx, 80070057h
0x18000f52b  lea     rcx, [rbp+210h+var_260]
0x18000f52f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000f534  lea     rcx, [rbp+210h+hKey]
0x18000f538  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000f53d  mov     eax, ebx
0x18000f53f  mov     rcx, [rbp+210h+var_40]
0x18000f546  xor     rcx, rsp; StackCookie
0x18000f549  call    __security_check_cookie
0x18000f54e  mov     rbx, [rsp+310h+arg_0]
0x18000f556  add     rsp, 2E0h
0x18000f55d  pop     r15
0x18000f55f  pop     r14
0x18000f561  pop     r13
0x18000f563  pop     r12
0x18000f565  pop     rdi
0x18000f566  pop     rsi
0x18000f567  pop     rbp
0x18000f568  retn
```
