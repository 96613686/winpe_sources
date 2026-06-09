# UnSetMultiTenancySettings

- ea: `0x1800295e4`
- end: `0x180029983`
- name: `UnSetMultiTenancySettings`
- size: `927`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026b90`

## callees

- `0x1800151cc`
- `0x1800295e4`
- `0x180030498`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `msvcrt!_time64` at `0x180029623`
- `msvcrt!_time64` at `0x180029623`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002994a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002995f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002994a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002995f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029752`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800298c0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029752`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800298c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029664`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800297f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029664`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800297f8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180029850`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180029850`

## string_xrefs

- `0x180029656`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x180029685`: `UnSetMultiTenancySettings: RegOpenKeyEx failed with error %d`
- `0x180029771`: `UnSetMultiTenancySettings: RegSetValueEx failed with error %d.`
- `0x180029819`: `UnSetMultiTenancySettings: RegOpenKeyEx for RoutingDomains key failed with error %d.`
- `0x180029871`: `UnSetMultiTenancySettings: RegDeleteTree failed with error %d.`
- `0x1800298dd`: `UnSetMultiTenancySettings: RegSetValueEx for RoutingDomains Default key failed with error %d.`
- `0x1800297ea`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`

## pseudocode

```c
__int64 UnSetMultiTenancySettings()
{
  unsigned int v0; // eax
  unsigned int v1; // edi
  __int64 v2; // r8
  __int64 v3; // rbx
  __int64 v4; // r8
  unsigned int v5; // eax
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v16[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[16]; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+70h] [rbp-90h]
  int v20; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v21[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  hKey = 0;
  phkResult = 0;
  v12 = 0;
  *(_DWORD *)Data = 0;
  v20 = 0;
  *(_QWORD *)v16 = _time64(0);
  memset_0(v21, 0, sizeof(v21));
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
         0,
         0x2001Fu,
         &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( byte_180078D92 < 0 )
    {
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"UnSetMultiTenancySettings: RegOpenKeyEx failed with error %d", v0);
      if ( byte_180078D92 < 0 )
      {
        v3 = -1;
        do
          ++v3;
        while ( *(_WORD *)&v21[2 * v3 - 4] );
LABEL_30:
        v19 = (unsigned int)(2 * v3 + 2);
        v18 = (const wchar_t *)&v20;
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RRAS_MPRAPI_TRACE_ERROR,
          v2,
          2,
          v17);
      }
    }
  }
  else
  {
    RegGetDword(hKey, L"MultiTenancyEnabled", 0, 1, 0, &v12);
    if ( !v12 )
      goto LABEL_31;
    if ( (byte_180078D93 & 1) != 0 )
    {
      v19 = 134;
      v18 = L"UnSetMultiTenancySettings: Multi-tenancy is enabled on the server.";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_MPRAPI_TRACE_INFO, v4, 2, v17);
    }
    v5 = RegSetValueExW(hKey, L"MultiTenancyEnabled", 0, 4u, Data, 4u);
    v3 = -1;
    if ( v5 )
    {
      if ( byte_180078D92 < 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"UnSetMultiTenancySettings: RegSetValueEx failed with error %d.", v5);
        if ( byte_180078D92 < 0 )
        {
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)&v21[2 * v7 - 4] );
          v19 = (unsigned int)(2 * v7 + 2);
          v18 = (const wchar_t *)&v20;
          McGenEventWrite_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RRAS_MPRAPI_TRACE_ERROR,
            v6,
            2,
            v17);
        }
      }
    }
    v8 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
           0,
           0x2001Fu,
           &phkResult);
    v1 = v8;
    if ( v8 )
    {
      if ( byte_180078D92 < 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(
          &v20,
          L"UnSetMultiTenancySettings: RegOpenKeyEx for RoutingDomains key failed with error %d.",
          v8);
        if ( byte_180078D92 < 0 )
        {
          do
            ++v3;
          while ( *(_WORD *)&v21[2 * v3 - 4] );
          goto LABEL_30;
        }
      }
    }
    else
    {
      v9 = RegDeleteTreeW(phkResult, 0);
      v1 = v9;
      if ( v9 )
      {
        if ( byte_180078D92 < 0 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(&v20, L"UnSetMultiTenancySettings: RegDeleteTree failed with error %d.", v9);
          if ( byte_180078D92 < 0 )
          {
            do
              ++v3;
            while ( *(_WORD *)&v21[2 * v3 - 4] );
            goto LABEL_30;
          }
        }
      }
      else
      {
        v10 = RegSetValueExW(phkResult, 0, 0, 0xBu, v16, 8u);
        v1 = v10;
        if ( v10 )
        {
          if ( byte_180078D92 < 0 )
          {
            LOWORD(v20) = 0;
            FormatRRASErrorString(
              &v20,
              L"UnSetMultiTenancySettings: RegSetValueEx for RoutingDomains Default key failed with error %d.",
              v10);
            if ( byte_180078D92 < 0 )
            {
              do
                ++v3;
              while ( *(_WORD *)&v21[2 * v3 - 4] );
              goto LABEL_30;
            }
          }
        }
      }
    }
  }
LABEL_31:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v1;
}

```

## disassembly

```asm
0x1800295e4  push    rbp
0x1800295e6  push    rbx
0x1800295e7  push    rdi
0x1800295e8  push    r12
0x1800295ea  lea     rbp, [rsp-798h]
0x1800295f2  sub     rsp, 898h
0x1800295f9  mov     rax, cs:__security_cookie
0x180029600  xor     rax, rsp
0x180029603  mov     [rbp+7B0h+var_30], rax
0x18002960a  xor     r12d, r12d
0x18002960d  xor     ecx, ecx; Time
0x18002960f  mov     [rsp+8B0h+hKey], r12
0x180029614  mov     [rsp+8B0h+var_870], r12
0x180029619  mov     [rsp+8B0h+var_880], r12d
0x18002961e  mov     dword ptr [rsp+8B0h+Data], r12d
0x180029623  call    cs:__imp__time64
0x180029629  xor     edx, edx; Val
0x18002962b  mov     [rbp+7B0h+var_830], r12d
0x18002962f  mov     r8d, 7FCh; Size
0x180029635  mov     qword ptr [rsp+8B0h+var_860], rax
0x18002963a  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18002963e  call    memset_0
0x180029643  lea     rax, [rsp+8B0h+hKey]
0x180029648  mov     r9d, 2001Fh; samDesired
0x18002964e  xor     r8d, r8d; ulOptions
0x180029651  mov     [rsp+8B0h+phkResult], rax; phkResult
0x180029656  lea     rdx, c_szRegKeyRemoteAccessParameters; "System\\CurrentControlSet\\Services\\Re"...
0x18002965d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029664  call    cs:__imp_RegOpenKeyExW
0x18002966a  mov     edi, eax
0x18002966c  test    eax, eax
0x18002966e  jz      short loc_1800296B9
0x180029670  cmp     cs:byte_180078D92, r12b
0x180029677  jge     loc_180029940
0x18002967d  mov     r8d, eax
0x180029680  mov     word ptr [rbp+7B0h+var_830], r12w
0x180029685  lea     rdx, aUnsetmultitena_1; "UnSetMultiTenancySettings: RegOpenKeyEx"...
0x18002968c  lea     rcx, [rbp+7B0h+var_830]
0x180029690  call    FormatRRASErrorString
0x180029695  cmp     cs:byte_180078D92, r12b
0x18002969c  jge     loc_180029940
0x1800296a2  lea     rax, [rbp+7B0h+var_830]
0x1800296a6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800296aa  inc     rbx
0x1800296ad  cmp     [rax+rbx*2], r12w
0x1800296b2  jnz     short loc_1800296AA
0x1800296b4  jmp     loc_180029904
0x1800296b9  mov     rcx, [rsp+8B0h+hKey]
0x1800296be  lea     rax, [rsp+8B0h+var_880]
0x1800296c3  mov     qword ptr [rsp+8B0h+cbData], rax
0x1800296c8  lea     rdx, c_szMultiTenancyEnabled; "MultiTenancyEnabled"
0x1800296cf  mov     r9d, 1
0x1800296d5  mov     dword ptr [rsp+8B0h+phkResult], r12d
0x1800296da  xor     r8d, r8d
0x1800296dd  call    RegGetDword
0x1800296e2  cmp     [rsp+8B0h+var_880], r12d
0x1800296e7  jz      loc_180029940
0x1800296ed  test    cs:byte_180078D93, 1
0x1800296f4  jz      short loc_18002972E
0x1800296f6  lea     rax, aUnsetmultitena_4; "UnSetMultiTenancySettings: Multi-tenanc"...
0x1800296fd  mov     [rsp+8B0h+var_840], 86h
0x180029706  mov     [rsp+8B0h+var_848], rax
0x18002970b  lea     rdx, RRAS_MPRAPI_TRACE_INFO
0x180029712  lea     rax, [rsp+8B0h+var_858]
0x180029717  mov     r9d, 2
0x18002971d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180029724  mov     [rsp+8B0h+phkResult], rax
0x180029729  call    McGenEventWrite_EventWriteTransfer
0x18002972e  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180029733  lea     rax, [rsp+8B0h+Data]
0x180029738  mov     r9d, 4; dwType
0x18002973e  lea     rdx, c_szMultiTenancyEnabled; "MultiTenancyEnabled"
0x180029745  mov     [rsp+8B0h+cbData], r9d; cbData
0x18002974a  xor     r8d, r8d; Reserved
0x18002974d  mov     [rsp+8B0h+phkResult], rax; lpData
0x180029752  call    cs:__imp_RegSetValueExW
0x180029758  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002975c  test    eax, eax
0x18002975e  jz      short loc_1800297D7
0x180029760  cmp     cs:byte_180078D92, r12b
0x180029767  jge     short loc_1800297D7
0x180029769  mov     r8d, eax
0x18002976c  mov     word ptr [rbp+7B0h+var_830], r12w
0x180029771  lea     rdx, aUnsetmultitena_3; "UnSetMultiTenancySettings: RegSetValueE"...
0x180029778  lea     rcx, [rbp+7B0h+var_830]
0x18002977c  call    FormatRRASErrorString
0x180029781  cmp     cs:byte_180078D92, r12b
0x180029788  jge     short loc_1800297D7
0x18002978a  lea     rcx, [rbp+7B0h+var_830]
0x18002978e  mov     rax, rbx
0x180029791  inc     rax
0x180029794  cmp     [rcx+rax*2], r12w
0x180029799  jnz     short loc_180029791
0x18002979b  lea     eax, ds:2[rax*2]
0x1800297a2  mov     dword ptr [rsp+8B0h+var_840+4], r12d
0x1800297a7  lea     rcx, [rbp+7B0h+var_830]
0x1800297ab  mov     dword ptr [rsp+8B0h+var_840], eax
0x1800297af  lea     rax, [rsp+8B0h+var_858]
0x1800297b4  mov     [rsp+8B0h+var_848], rcx
0x1800297b9  mov     r9d, 2
0x1800297bf  mov     [rsp+8B0h+phkResult], rax
0x1800297c4  lea     rdx, RRAS_MPRAPI_TRACE_ERROR
0x1800297cb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800297d2  call    McGenEventWrite_EventWriteTransfer
0x1800297d7  lea     rax, [rsp+8B0h+var_870]
0x1800297dc  mov     r9d, 2001Fh; samDesired
0x1800297e2  xor     r8d, r8d; ulOptions
0x1800297e5  mov     [rsp+8B0h+phkResult], rax; phkResult
0x1800297ea  lea     rdx, c_szRegKeyRemoteAccessRoutingDomains; "System\\CurrentControlSet\\Services\\Re"...
0x1800297f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800297f8  call    cs:__imp_RegOpenKeyExW
0x1800297fe  mov     edi, eax
0x180029800  test    eax, eax
0x180029802  jz      short loc_180029849
0x180029804  cmp     cs:byte_180078D92, r12b
0x18002980b  jge     loc_180029940
0x180029811  mov     r8d, eax
0x180029814  mov     word ptr [rbp+7B0h+var_830], r12w
0x180029819  lea     rdx, aUnsetmultitena_0; "UnSetMultiTenancySettings: RegOpenKeyEx"...
0x180029820  lea     rcx, [rbp+7B0h+var_830]
0x180029824  call    FormatRRASErrorString
0x180029829  cmp     cs:byte_180078D92, r12b
0x180029830  jge     loc_180029940
0x180029836  lea     rax, [rbp+7B0h+var_830]
0x18002983a  inc     rbx
0x18002983d  cmp     [rax+rbx*2], r12w
0x180029842  jnz     short loc_18002983A
0x180029844  jmp     loc_180029904
0x180029849  mov     rcx, [rsp+8B0h+var_870]; hKey
0x18002984e  xor     edx, edx; lpSubKey
0x180029850  call    cs:__imp_RegDeleteTreeW
0x180029856  mov     edi, eax
0x180029858  test    eax, eax
0x18002985a  jz      short loc_18002989E
0x18002985c  cmp     cs:byte_180078D92, r12b
0x180029863  jge     loc_180029940
0x180029869  mov     r8d, eax
0x18002986c  mov     word ptr [rbp+7B0h+var_830], r12w
0x180029871  lea     rdx, aUnsetmultitena_5; "UnSetMultiTenancySettings: RegDeleteTre"...
0x180029878  lea     rcx, [rbp+7B0h+var_830]
0x18002987c  call    FormatRRASErrorString
0x180029881  cmp     cs:byte_180078D92, r12b
0x180029888  jge     loc_180029940
0x18002988e  lea     rax, [rbp+7B0h+var_830]
0x180029892  inc     rbx
0x180029895  cmp     [rax+rbx*2], r12w
0x18002989a  jnz     short loc_180029892
0x18002989c  jmp     short loc_180029904
0x18002989e  mov     rcx, [rsp+8B0h+var_870]; hKey
0x1800298a3  lea     rax, [rsp+8B0h+var_860]
0x1800298a8  mov     [rsp+8B0h+cbData], 8; cbData
0x1800298b0  mov     r9d, 0Bh; dwType
0x1800298b6  xor     r8d, r8d; Reserved
0x1800298b9  mov     [rsp+8B0h+phkResult], rax; lpData
0x1800298be  xor     edx, edx; lpValueName
0x1800298c0  call    cs:__imp_RegSetValueExW
0x1800298c6  mov     edi, eax
0x1800298c8  test    eax, eax
0x1800298ca  jz      short loc_180029940
0x1800298cc  cmp     cs:byte_180078D92, r12b
0x1800298d3  jge     short loc_180029940
0x1800298d5  mov     r8d, eax
0x1800298d8  mov     word ptr [rbp+7B0h+var_830], r12w
0x1800298dd  lea     rdx, aUnsetmultitena_6; "UnSetMultiTenancySettings: RegSetValueE"...
0x1800298e4  lea     rcx, [rbp+7B0h+var_830]
0x1800298e8  call    FormatRRASErrorString
0x1800298ed  cmp     cs:byte_180078D92, r12b
0x1800298f4  jge     short loc_180029940
0x1800298f6  lea     rax, [rbp+7B0h+var_830]
0x1800298fa  inc     rbx
0x1800298fd  cmp     [rax+rbx*2], r12w
0x180029902  jnz     short loc_1800298FA
0x180029904  lea     eax, ds:2[rbx*2]
0x18002990b  mov     dword ptr [rsp+8B0h+var_840+4], r12d
0x180029910  lea     rcx, [rbp+7B0h+var_830]
0x180029914  mov     dword ptr [rsp+8B0h+var_840], eax
0x180029918  lea     rax, [rsp+8B0h+var_858]
0x18002991d  mov     [rsp+8B0h+var_848], rcx
0x180029922  mov     r9d, 2
0x180029928  mov     [rsp+8B0h+phkResult], rax
0x18002992d  lea     rdx, RRAS_MPRAPI_TRACE_ERROR
0x180029934  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002993b  call    McGenEventWrite_EventWriteTransfer
0x180029940  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180029945  test    rcx, rcx
0x180029948  jz      short loc_180029955
0x18002994a  call    cs:__imp_RegCloseKey
0x180029950  mov     [rsp+8B0h+hKey], r12
0x180029955  mov     rcx, [rsp+8B0h+var_870]; hKey
0x18002995a  test    rcx, rcx
0x18002995d  jz      short loc_180029965
0x18002995f  call    cs:__imp_RegCloseKey
0x180029965  mov     eax, edi
0x180029967  mov     rcx, [rbp+7B0h+var_30]
0x18002996e  xor     rcx, rsp; StackCookie
0x180029971  call    __security_check_cookie
0x180029976  add     rsp, 898h
0x18002997d  pop     r12
0x18002997f  pop     rdi
0x180029980  pop     rbx
0x180029981  pop     rbp
0x180029982  retn
```
