# ProvisioningPaths::GetProvisioningDiagnosticsFolderPath(void)

- ea: `0x18002490c`
- end: `0x180024c54`
- name: `?GetProvisioningDiagnosticsFolderPath@ProvisioningPaths@@SAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `840`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ebbc`
- `0x180010b40`
- `0x180012e94`

## callees

- `0x180002f44`
- `0x18000c538`
- `0x18001b388`
- `0x18001b3a8`
- `0x1800210f0`
- `0x1800245fc`
- `0x180024818`
- `0x18002490c`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180024b0b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024b90`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024ba5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024b0b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024b90`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024ba5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180024bb3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180024bb3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180024a27`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180024a27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024bd2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800249cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800249cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002496c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002496c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024bc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024bc2`

## string_xrefs

- `0x180024c06`: `onecoreuap\admin\prov\lib\provpaths.cpp`
- `0x180024c18`: `onecoreuap\admin\prov\lib\provpaths.cpp`
- `0x180024c2d`: `onecoreuap\admin\prov\lib\provpaths.cpp`
- `0x180024c42`: `onecoreuap\admin\prov\lib\provpaths.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 ProvisioningPaths::GetProvisioningDiagnosticsFolderPath()
{
  struct ProvisioningPaths *Instance; // r15
  int v1; // eax
  int v2; // eax
  const char *v3; // r9
  char *v4; // r14
  int v5; // eax
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r8
  void **v8; // rax
  void **i; // rbx
  __int64 v10; // r10
  __int16 *v11; // rcx
  void **v12; // rdx
  void **v13; // rax
  __int64 v14; // rbx
  void **v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  char *v18; // rdx
  __int64 v19; // rbx
  int phkResult; // [rsp+20h] [rbp-99h]
  int phkResulta; // [rsp+20h] [rbp-99h]
  unsigned int phkResultb; // [rsp+20h] [rbp-99h]
  __int16 v24; // [rsp+60h] [rbp-59h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-49h] BYREF
  DWORD Type; // [rsp+78h] [rbp-41h] BYREF
  DWORD cchValueName; // [rsp+7Ch] [rbp-3Dh] BYREF
  LPWSTR lpValueName; // [rsp+80h] [rbp-39h] BYREF
  void *Src[3]; // [rsp+88h] [rbp-31h] BYREF
  void *v31[2]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-9h]
  unsigned __int64 v33; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  Instance = ProvisioningPaths::GetInstance();
  if ( !*((_QWORD *)Instance + 3) )
  {
    hKey = 0;
    v1 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\MdmDiagnostics\\Area\\DeviceProvisioning\\FileEntry",
           0,
           0x20019u,
           &hKey);
    if ( v1 > 0 )
      v1 = (unsigned __int16)v1 | 0x80070000;
    if ( v1 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpaths.cpp",
        (const char *)(unsigned int)v1,
        phkResult);
    Type = 0;
    cbMaxValueNameLen = 0;
    v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, 0, 0, 0);
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpaths.cpp",
        (const char *)(unsigned int)v2,
        phkResulta);
    cchValueName = cbMaxValueNameLen + 1;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpValueName,
      0,
      cbMaxValueNameLen + 1,
      v3);
    v4 = (char *)lpValueName;
    v5 = RegEnumValueW(hKey, 0, lpValueName, &cchValueName, 0, &Type, 0, 0);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpaths.cpp",
        (const char *)(unsigned int)v5,
        phkResultb);
    v33 = 7;
    v32 = 0;
    LOWORD(v31[0]) = 0;
    v6 = -1;
    if ( *(_WORD *)v4 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&v4[2 * v7] );
    }
    else
    {
      v7 = 0;
    }
    std::wstring::assign(v31, v4, v7);
    v24 = 92;
    if ( v32 )
    {
      v8 = v31;
      if ( v33 >= 8 )
        v8 = (void **)v31[0];
      for ( i = (void **)((char *)v8 + 2 * v32 - 2); ; i = (void **)((char *)i - 2) )
      {
        if ( *(_WORD *)i == 92 )
        {
          v10 = 1;
          v11 = &v24;
          v12 = i;
          while ( *(_WORD *)v12 == *v11 )
          {
            v12 = (void **)((char *)v12 + 2);
            ++v11;
            if ( !--v10 )
            {
              v13 = v31;
              if ( v33 >= 8 )
                v13 = (void **)v31[0];
              v14 = ((char *)i - (char *)v13) >> 1;
              goto LABEL_31;
            }
          }
        }
        v15 = v31;
        if ( v33 >= 8 )
          v15 = (void **)v31[0];
        if ( i == v15 )
          break;
      }
    }
    v14 = -1;
LABEL_31:
    if ( v33 >= 8 )
      operator delete(v31[0]);
    if ( v14 == -1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpaths.cpp",
        (const char *)3,
        phkResultb);
    *(_WORD *)&v4[2 * v14 + 2] = 0;
    expanded_wstring::expanded_wstring((expanded_wstring *)Src, (const unsigned __int16 *)v4);
    v16 = operator new(0x20u);
    v17 = v16;
    Src[2] = v16;
    if ( v16 )
    {
      v18 = (char *)Src[0];
      v16[3] = 7;
      v16[2] = 0;
      *(_WORD *)v16 = 0;
      if ( *(_WORD *)v18 )
      {
        do
          ++v6;
        while ( *(_WORD *)&v18[2 * v6] );
      }
      else
      {
        v6 = 0;
      }
      std::wstring::assign(v16, v18, v6);
    }
    else
    {
      v17 = 0;
    }
    v19 = *((_QWORD *)Instance + 3);
    if ( v17 != (_QWORD *)v19 )
    {
      if ( v19 )
      {
        if ( *(_QWORD *)(v19 + 24) >= 8u )
          operator delete(*(void **)v19);
        *(_QWORD *)(v19 + 24) = 7;
        *(_QWORD *)(v19 + 16) = 0;
        *(_WORD *)v19 = 0;
        operator delete((void *)v19);
      }
      *((_QWORD *)Instance + 3) = v17;
    }
    operator delete[](Src[0]);
    if ( v4 )
      LocalFree(v4);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return *((_QWORD *)Instance + 3);
}

```

## disassembly

```asm
0x18002490c  push    rbp
0x18002490e  push    rbx
0x18002490f  push    rsi
0x180024910  push    rdi
0x180024911  push    r12
0x180024913  push    r13
0x180024915  push    r14
0x180024917  push    r15
0x180024919  lea     rbp, [rsp-1Fh]
0x18002491e  sub     rsp, 0D8h
0x180024925  mov     rax, cs:__security_cookie
0x18002492c  xor     rax, rsp
0x18002492f  mov     [rbp+57h+var_50], rax
0x180024933  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x180024938  mov     r15, rax
0x18002493b  xor     r12d, r12d
0x18002493e  cmp     [rax+18h], r12
0x180024942  jnz     loc_180024BD8
0x180024948  mov     [rbp+57h+hKey], r12
0x18002494c  lea     rax, [rbp+57h+hKey]
0x180024950  mov     [rsp+110h+phkResult], rax; int
0x180024955  mov     r9d, 20019h; samDesired
0x18002495b  xor     r8d, r8d; ulOptions
0x18002495e  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\MdmDiagnostics\\Ar"...
0x180024965  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002496c  call    cs:__imp_RegOpenKeyExW
0x180024972  mov     ebx, 80070000h
0x180024977  test    eax, eax
0x180024979  jle     short loc_180024980
0x18002497b  movzx   eax, ax
0x18002497e  or      eax, ebx
0x180024980  mov     rcx, [rbp+5Fh]; this
0x180024984  test    eax, eax
0x180024986  js      loc_180024C15
0x18002498c  mov     [rbp+57h+Type], r12d
0x180024990  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x180024994  mov     [rsp+110h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180024999  mov     [rsp+110h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18002499e  mov     [rsp+110h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800249a3  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800249a7  mov     [rsp+110h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800249ac  mov     [rsp+110h+lpcValues], r12; lpcValues
0x1800249b1  mov     [rsp+110h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800249b6  mov     [rsp+110h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800249bb  mov     [rsp+110h+phkResult], r12; int
0x1800249c0  xor     r9d, r9d; lpReserved
0x1800249c3  xor     r8d, r8d; lpcchClass
0x1800249c6  xor     edx, edx; lpClass
0x1800249c8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800249cc  call    cs:__imp_RegQueryInfoKeyW
0x1800249d2  test    eax, eax
0x1800249d4  jle     short loc_1800249DB
0x1800249d6  movzx   eax, ax
0x1800249d9  or      eax, ebx
0x1800249db  mov     rcx, [rbp+5Fh]; this
0x1800249df  test    eax, eax
0x1800249e1  js      loc_180024C2A
0x1800249e7  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800249ea  inc     eax
0x1800249ec  mov     [rbp+57h+cchValueName], eax
0x1800249ef  mov     r8d, eax
0x1800249f2  xor     edx, edx
0x1800249f4  lea     rcx, [rbp+57h+lpValueName]
0x1800249f8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800249fd  nop
0x1800249fe  mov     [rsp+110h+lpcValues], r12; lpcbData
0x180024a03  mov     [rsp+110h+lpcbMaxClassLen], r12; lpData
0x180024a08  lea     rax, [rbp+57h+Type]
0x180024a0c  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpType
0x180024a11  mov     [rsp+110h+phkResult], r12; int
0x180024a16  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180024a1a  mov     r14, [rbp+57h+lpValueName]
0x180024a1e  mov     r8, r14; lpValueName
0x180024a21  xor     edx, edx; dwIndex
0x180024a23  mov     rcx, [rbp+57h+hKey]; hKey
0x180024a27  call    cs:__imp_RegEnumValueW
0x180024a2d  test    eax, eax
0x180024a2f  jle     short loc_180024A36
0x180024a31  movzx   eax, ax
0x180024a34  or      eax, ebx
0x180024a36  mov     rcx, [rbp+5Fh]; this
0x180024a3a  test    eax, eax
0x180024a3c  js      loc_180024C3F
0x180024a42  mov     r13d, 7
0x180024a48  mov     [rbp+57h+var_58], r13
0x180024a4c  mov     [rbp+57h+var_60], r12
0x180024a50  mov     word ptr [rbp+57h+var_70], r12w
0x180024a55  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024a59  cmp     [r14], r12w
0x180024a5d  jnz     short loc_180024A64
0x180024a5f  mov     r8, r12
0x180024a62  jmp     short loc_180024A71
0x180024a64  mov     r8, rsi
0x180024a67  inc     r8
0x180024a6a  cmp     [r14+r8*2], r12w
0x180024a6f  jnz     short loc_180024A67
0x180024a71  mov     rdx, r14; Src
0x180024a74  lea     rcx, [rbp+57h+var_70]; void *
0x180024a78  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180024a7d  mov     edi, 5Ch ; '\'
0x180024a82  mov     [rbp+57h+var_B0], di
0x180024a86  mov     rcx, [rbp+57h+var_60]
0x180024a8a  mov     r8, [rbp+57h+var_58]
0x180024a8e  mov     r9, [rbp+57h+var_70]
0x180024a92  cmp     rcx, 1
0x180024a96  jb      short loc_180024AFF
0x180024a98  lea     rax, [rbp+57h+var_70]
0x180024a9c  cmp     r8, 8
0x180024aa0  cmovnb  rax, r9
0x180024aa4  lea     rbx, [rcx-1]
0x180024aa8  lea     rbx, [rax+rbx*2]
0x180024aac  cmp     [rbx], di
0x180024aaf  jnz     short loc_180024AE8
0x180024ab1  mov     r10d, 1
0x180024ab7  lea     rcx, [rbp+57h+var_B0]
0x180024abb  mov     rdx, rbx
0x180024abe  movzx   eax, word ptr [rcx]
0x180024ac1  cmp     [rdx], ax
0x180024ac4  jnz     short loc_180024AE8
0x180024ac6  add     rdx, 2
0x180024aca  add     rcx, 2
0x180024ace  sub     r10, 1
0x180024ad2  jnz     short loc_180024ABE
0x180024ad4  lea     rax, [rbp+57h+var_70]
0x180024ad8  cmp     r8, 8
0x180024adc  cmovnb  rax, r9
0x180024ae0  sub     rbx, rax
0x180024ae3  sar     rbx, 1
0x180024ae6  jmp     short loc_180024B02
0x180024ae8  lea     rax, [rbp+57h+var_70]
0x180024aec  cmp     r8, 8
0x180024af0  cmovnb  rax, r9
0x180024af4  cmp     rbx, rax
0x180024af7  jz      short loc_180024AFF
0x180024af9  sub     rbx, 2
0x180024afd  jmp     short loc_180024AAC
0x180024aff  mov     rbx, rsi
0x180024b02  cmp     r8, 8
0x180024b06  jb      short loc_180024B11
0x180024b08  mov     rcx, r9
0x180024b0b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180024b11  cmp     rbx, rsi
0x180024b14  jz      loc_180024BFC
0x180024b1a  mov     [r14+rbx*2+2], r12w
0x180024b20  mov     rdx, r14; unsigned __int16 *
0x180024b23  lea     rcx, [rbp+57h+Src]; this
0x180024b27  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180024b2c  nop
0x180024b2d  mov     ecx, 20h ; ' '; Size
0x180024b32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024b37  mov     rdi, rax
0x180024b3a  mov     [rbp+57h+var_78], rax
0x180024b3e  test    rax, rax
0x180024b41  jz      short loc_180024B75
0x180024b43  mov     rdx, [rbp+57h+Src]; Src
0x180024b47  mov     [rax+18h], r13
0x180024b4b  mov     [rax+10h], r12
0x180024b4f  mov     [rax], r12w
0x180024b53  cmp     [rdx], r12w
0x180024b57  jnz     short loc_180024B5E
0x180024b59  mov     rsi, r12
0x180024b5c  jmp     short loc_180024B68
0x180024b5e  inc     rsi
0x180024b61  cmp     [rdx+rsi*2], r12w
0x180024b66  jnz     short loc_180024B5E
0x180024b68  mov     r8, rsi
0x180024b6b  mov     rcx, rax; void *
0x180024b6e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180024b73  jmp     short loc_180024B78
0x180024b75  mov     rdi, r12
0x180024b78  mov     rbx, [r15+18h]
0x180024b7c  cmp     rdi, rbx
0x180024b7f  jz      short loc_180024BAF
0x180024b81  test    rbx, rbx
0x180024b84  jz      short loc_180024BAB
0x180024b86  cmp     qword ptr [rbx+18h], 8
0x180024b8b  jb      short loc_180024B96
0x180024b8d  mov     rcx, [rbx]
0x180024b90  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180024b96  mov     [rbx+18h], r13
0x180024b9a  mov     [rbx+10h], r12
0x180024b9e  mov     [rbx], r12w
0x180024ba2  mov     rcx, rbx
0x180024ba5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180024bab  mov     [r15+18h], rdi
0x180024baf  mov     rcx, [rbp+57h+Src]
0x180024bb3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180024bb9  nop
0x180024bba  test    r14, r14
0x180024bbd  jz      short loc_180024BC9
0x180024bbf  mov     rcx, r14; hMem
0x180024bc2  call    cs:__imp_LocalFree
0x180024bc8  nop
0x180024bc9  mov     rcx, [rbp+57h+hKey]; hKey
0x180024bcd  test    rcx, rcx
0x180024bd0  jz      short loc_180024BD8
0x180024bd2  call    cs:__imp_RegCloseKey
0x180024bd8  mov     rax, [r15+18h]
0x180024bdc  mov     rcx, [rbp+57h+var_50]
0x180024be0  xor     rcx, rsp; StackCookie
0x180024be3  call    __security_check_cookie
0x180024be8  add     rsp, 0D8h
0x180024bef  pop     r15
0x180024bf1  pop     r14
0x180024bf3  pop     r13
0x180024bf5  pop     r12
0x180024bf7  pop     rdi
0x180024bf8  pop     rsi
0x180024bf9  pop     rbx
0x180024bfa  pop     rbp
0x180024bfb  retn
0x180024bfc  mov     rcx, [rbp+5Fh]; this
0x180024c00  mov     r9d, 3; char *
0x180024c06  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\lib\\provpaths"...
0x180024c0d  mov     edx, edi; void *
0x180024c0f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180024c15  mov     r9d, eax; char *
0x180024c18  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\lib\\provpaths"...
0x180024c1f  mov     edx, 36h ; '6'; void *
0x180024c24  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024c2a  mov     r9d, eax; char *
0x180024c2d  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\lib\\provpaths"...
0x180024c34  mov     edx, 48h ; 'H'; void *
0x180024c39  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024c3f  mov     r9d, eax; char *
0x180024c42  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\lib\\provpaths"...
0x180024c49  mov     edx, 56h ; 'V'; void *
0x180024c4e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
