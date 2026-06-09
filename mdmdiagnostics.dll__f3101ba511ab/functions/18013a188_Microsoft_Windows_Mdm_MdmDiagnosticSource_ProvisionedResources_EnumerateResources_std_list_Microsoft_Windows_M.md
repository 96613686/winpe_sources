# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord,std::allocator<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>> &)

- ea: `0x18013a188`
- end: `0x18013a394`
- name: `?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@Z`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801305b8`

## callees

- `0x180019080`
- `0x1800e7de8`
- `0x1800ed46c`
- `0x180105294`
- `0x18012a388`
- `0x18013959c`
- `0x18013a188`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013a239`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013a239`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18013a2a4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18013a2a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013a1e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013a1e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18013a2f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18013a2f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(
        __int64 a1,
        int a2)
{
  const WCHAR *v3; // rax
  unsigned int ValueW; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  DWORD i; // ebx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edi
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  int pvData; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  hKey[0] = 0;
  v3 = (const WCHAR *)DMGetKnownRegPath();
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, hKey);
  if ( ValueW )
  {
    v5 = 354;
LABEL_5:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
           (const char *)ValueW,
           phkResult);
    goto LABEL_17;
  }
  cSubKeys = 0;
  ValueW = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( ValueW )
  {
    v5 = 372;
    goto LABEL_5;
  }
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 260;
    ValueW = RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0);
    if ( ValueW )
    {
      v5 = 377;
      goto LABEL_5;
    }
    pvData = 63;
    cchName = 4;
    ValueW = RegGetValueW(hKey[0], Name, L"EnrollmentType", 0x10u, 0, &pvData, &cchName);
    if ( ValueW != 2 )
    {
      if ( ValueW )
      {
        v5 = 386;
        goto LABEL_5;
      }
      v9 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CollectAllResourcesForEnrollment(
             v8,
             (__int64)Name,
             pvData,
             a2);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x184,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)(unsigned int)v9,
          phkResult);
        v6 = v10;
        goto LABEL_17;
      }
    }
  }
  v6 = 0;
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return v6;
}

```

## disassembly

```asm
0x18013a188  mov     [rsp-8+arg_0], rbx
0x18013a18d  mov     [rsp-8+arg_10], rsi
0x18013a192  push    rbp
0x18013a193  push    rdi
0x18013a194  push    r14
0x18013a196  lea     rbp, [rsp-1A0h]
0x18013a19e  sub     rsp, 2A0h
0x18013a1a5  mov     rax, cs:__security_cookie
0x18013a1ac  xor     rax, rsp
0x18013a1af  mov     [rbp+1B0h+var_20], rax
0x18013a1b6  mov     rsi, rdx
0x18013a1b9  xor     r14d, r14d
0x18013a1bc  mov     [rsp+2B0h+hKey], r14
0x18013a1c1  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18013a1c6  lea     rcx, [rsp+2B0h+hKey]
0x18013a1cb  mov     [rsp+2B0h+phkResult], rcx; phkResult
0x18013a1d0  mov     r9d, 20019h; samDesired
0x18013a1d6  xor     r8d, r8d; ulOptions
0x18013a1d9  mov     rdx, rax; lpSubKey
0x18013a1dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013a1e3  call    cs:__imp_RegOpenKeyExW
0x18013a1ea  nop     dword ptr [rax+rax+00h]
0x18013a1ef  test    eax, eax
0x18013a1f1  jz      short loc_18013A1FA
0x18013a1f3  mov     edx, 162h
0x18013a1f8  jmp     short loc_18013A24E
0x18013a1fa  mov     [rsp+2B0h+cSubKeys], r14d
0x18013a1ff  mov     [rsp+2B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18013a204  mov     [rsp+2B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18013a209  mov     [rsp+2B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18013a20e  mov     [rsp+2B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18013a213  mov     [rsp+2B0h+lpcValues], r14; lpcValues
0x18013a218  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18013a21d  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18013a222  lea     rax, [rsp+2B0h+cSubKeys]
0x18013a227  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x18013a22c  xor     r9d, r9d; lpReserved
0x18013a22f  xor     r8d, r8d; lpcchClass
0x18013a232  xor     edx, edx; lpClass
0x18013a234  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18013a239  call    cs:__imp_RegQueryInfoKeyW
0x18013a240  nop     dword ptr [rax+rax+00h]
0x18013a245  test    eax, eax
0x18013a247  jz      short loc_18013A26B
0x18013a249  mov     edx, 174h; void *
0x18013a24e  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a255  mov     r9d, eax; char *
0x18013a258  mov     rcx, [rbp+1B8h]; this
0x18013a25f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013a264  mov     ebx, eax
0x18013a266  jmp     loc_18013A360
0x18013a26b  mov     ebx, r14d
0x18013a26e  cmp     ebx, [rsp+2B0h+cSubKeys]
0x18013a272  jnb     loc_18013A35D
0x18013a278  mov     [rsp+2B0h+cchName], 104h
0x18013a280  mov     [rsp+2B0h+lpcValues], r14; lpftLastWriteTime
0x18013a285  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpcchClass
0x18013a28a  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpClass
0x18013a28f  mov     [rsp+2B0h+phkResult], r14; lpReserved
0x18013a294  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18013a299  lea     r8, [rbp+1B0h+Name]; lpName
0x18013a29d  mov     edx, ebx; dwIndex
0x18013a29f  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18013a2a4  call    cs:__imp_RegEnumKeyExW
0x18013a2ab  nop     dword ptr [rax+rax+00h]
0x18013a2b0  test    eax, eax
0x18013a2b2  jnz     loc_18013A353
0x18013a2b8  mov     [rsp+2B0h+pvData], 3Fh ; '?'
0x18013a2c0  mov     [rsp+2B0h+cchName], 4
0x18013a2c8  lea     rax, [rsp+2B0h+cchName]
0x18013a2cd  mov     [rsp+2B0h+lpcbMaxClassLen], rax; pcbData
0x18013a2d2  lea     rax, [rsp+2B0h+pvData]
0x18013a2d7  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rax; pvData
0x18013a2dc  mov     [rsp+2B0h+phkResult], r14; int
0x18013a2e1  mov     r9d, 10h; dwFlags
0x18013a2e7  lea     r8, aEnrollmenttype; "EnrollmentType"
0x18013a2ee  lea     rdx, [rbp+1B0h+Name]; lpSubKey
0x18013a2f2  mov     rcx, [rsp+2B0h+hKey]; hkey
0x18013a2f7  call    cs:__imp_RegGetValueW
0x18013a2fe  nop     dword ptr [rax+rax+00h]
0x18013a303  cmp     eax, 2
0x18013a306  jz      short loc_18013A323
0x18013a308  test    eax, eax
0x18013a30a  jnz     short loc_18013A349
0x18013a30c  mov     r9, rsi
0x18013a30f  mov     r8d, [rsp+2B0h+pvData]
0x18013a314  lea     rdx, [rbp+1B0h+Name]
0x18013a318  call    ?CollectAllResourcesForEnrollment@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBGKAEAV?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CollectAllResourcesForEnrollment(ushort const *,ulong,std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord> &)
0x18013a31d  mov     edi, eax
0x18013a31f  test    eax, eax
0x18013a321  js      short loc_18013A32A
0x18013a323  inc     ebx
0x18013a325  jmp     loc_18013A26E
0x18013a32a  mov     rcx, [rbp+1B8h]; this
0x18013a331  mov     r9d, edi; char *
0x18013a334  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a33b  mov     edx, 184h; void *
0x18013a340  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a345  mov     ebx, edi
0x18013a347  jmp     short loc_18013A360
0x18013a349  mov     edx, 182h
0x18013a34e  jmp     loc_18013A24E
0x18013a353  mov     edx, 179h
0x18013a358  jmp     loc_18013A24E
0x18013a35d  mov     ebx, r14d
0x18013a360  lea     rcx, [rsp+2B0h+hKey]
0x18013a365  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18013a36a  mov     eax, ebx
0x18013a36c  mov     rcx, [rbp+1B0h+var_20]
0x18013a373  xor     rcx, rsp; StackCookie
0x18013a376  call    __security_check_cookie
0x18013a37b  lea     r11, [rsp+2B0h+var_10]
0x18013a383  mov     rbx, [r11+20h]
0x18013a387  mov     rsi, [r11+30h]
0x18013a38b  mov     rsp, r11
0x18013a38e  pop     r14
0x18013a390  pop     rdi
0x18013a391  pop     rbp
0x18013a392  retn
```
