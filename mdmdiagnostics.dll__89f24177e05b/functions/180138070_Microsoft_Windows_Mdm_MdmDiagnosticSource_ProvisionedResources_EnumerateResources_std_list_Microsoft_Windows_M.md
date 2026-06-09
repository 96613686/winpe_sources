# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord,std::allocator<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>> &)

- ea: `0x180138070`
- end: `0x180138263`
- name: `?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@Z`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012e86c`

## callees

- `0x180019000`
- `0x1800e7c08`
- `0x1800ece5c`
- `0x180104108`
- `0x18012886c`
- `0x180137508`
- `0x180138070`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013811b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013811b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180138180`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180138180`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801380cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801380cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801381cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801381cd`

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
0x180138070  mov     [rsp-8+arg_0], rbx
0x180138075  mov     [rsp-8+arg_10], rsi
0x18013807a  push    rbp
0x18013807b  push    rdi
0x18013807c  push    r14
0x18013807e  lea     rbp, [rsp-1A0h]
0x180138086  sub     rsp, 2A0h
0x18013808d  mov     rax, cs:__security_cookie
0x180138094  xor     rax, rsp
0x180138097  mov     [rbp+1B0h+var_20], rax
0x18013809e  mov     rsi, rdx
0x1801380a1  xor     r14d, r14d
0x1801380a4  mov     [rsp+2B0h+hKey], r14
0x1801380a9  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1801380ae  lea     rcx, [rsp+2B0h+hKey]
0x1801380b3  mov     [rsp+2B0h+phkResult], rcx; phkResult
0x1801380b8  mov     r9d, 20019h; samDesired
0x1801380be  xor     r8d, r8d; ulOptions
0x1801380c1  mov     rdx, rax; lpSubKey
0x1801380c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801380cb  call    cs:__imp_RegOpenKeyExW
0x1801380d1  test    eax, eax
0x1801380d3  jz      short loc_1801380DC
0x1801380d5  mov     edx, 162h
0x1801380da  jmp     short loc_18013812A
0x1801380dc  mov     [rsp+2B0h+cSubKeys], r14d
0x1801380e1  mov     [rsp+2B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1801380e6  mov     [rsp+2B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1801380eb  mov     [rsp+2B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1801380f0  mov     [rsp+2B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1801380f5  mov     [rsp+2B0h+lpcValues], r14; lpcValues
0x1801380fa  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1801380ff  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180138104  lea     rax, [rsp+2B0h+cSubKeys]
0x180138109  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x18013810e  xor     r9d, r9d; lpReserved
0x180138111  xor     r8d, r8d; lpcchClass
0x180138114  xor     edx, edx; lpClass
0x180138116  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18013811b  call    cs:__imp_RegQueryInfoKeyW
0x180138121  test    eax, eax
0x180138123  jz      short loc_180138147
0x180138125  mov     edx, 174h; void *
0x18013812a  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180138131  mov     r9d, eax; char *
0x180138134  mov     rcx, [rbp+1B8h]; this
0x18013813b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180138140  mov     ebx, eax
0x180138142  jmp     loc_180138230
0x180138147  mov     ebx, r14d
0x18013814a  cmp     ebx, [rsp+2B0h+cSubKeys]
0x18013814e  jnb     loc_18013822D
0x180138154  mov     [rsp+2B0h+cchName], 104h
0x18013815c  mov     [rsp+2B0h+lpcValues], r14; lpftLastWriteTime
0x180138161  mov     [rsp+2B0h+lpcbMaxClassLen], r14; lpcchClass
0x180138166  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r14; lpClass
0x18013816b  mov     [rsp+2B0h+phkResult], r14; lpReserved
0x180138170  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x180138175  lea     r8, [rbp+1B0h+Name]; lpName
0x180138179  mov     edx, ebx; dwIndex
0x18013817b  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180138180  call    cs:__imp_RegEnumKeyExW
0x180138186  test    eax, eax
0x180138188  jnz     loc_180138223
0x18013818e  mov     [rsp+2B0h+pvData], 3Fh ; '?'
0x180138196  mov     [rsp+2B0h+cchName], 4
0x18013819e  lea     rax, [rsp+2B0h+cchName]
0x1801381a3  mov     [rsp+2B0h+lpcbMaxClassLen], rax; pcbData
0x1801381a8  lea     rax, [rsp+2B0h+pvData]
0x1801381ad  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rax; pvData
0x1801381b2  mov     [rsp+2B0h+phkResult], r14; int
0x1801381b7  mov     r9d, 10h; dwFlags
0x1801381bd  lea     r8, aEnrollmenttype; "EnrollmentType"
0x1801381c4  lea     rdx, [rbp+1B0h+Name]; lpSubKey
0x1801381c8  mov     rcx, [rsp+2B0h+hKey]; hkey
0x1801381cd  call    cs:__imp_RegGetValueW
0x1801381d3  cmp     eax, 2
0x1801381d6  jz      short loc_1801381F3
0x1801381d8  test    eax, eax
0x1801381da  jnz     short loc_180138219
0x1801381dc  mov     r9, rsi
0x1801381df  mov     r8d, [rsp+2B0h+pvData]
0x1801381e4  lea     rdx, [rbp+1B0h+Name]
0x1801381e8  call    ?CollectAllResourcesForEnrollment@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBGKAEAV?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CollectAllResourcesForEnrollment(ushort const *,ulong,std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord> &)
0x1801381ed  mov     edi, eax
0x1801381ef  test    eax, eax
0x1801381f1  js      short loc_1801381FA
0x1801381f3  inc     ebx
0x1801381f5  jmp     loc_18013814A
0x1801381fa  mov     rcx, [rbp+1B8h]; this
0x180138201  mov     r9d, edi; char *
0x180138204  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013820b  mov     edx, 184h; void *
0x180138210  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138215  mov     ebx, edi
0x180138217  jmp     short loc_180138230
0x180138219  mov     edx, 182h
0x18013821e  jmp     loc_18013812A
0x180138223  mov     edx, 179h
0x180138228  jmp     loc_18013812A
0x18013822d  mov     ebx, r14d
0x180138230  lea     rcx, [rsp+2B0h+hKey]
0x180138235  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18013823a  mov     eax, ebx
0x18013823c  mov     rcx, [rbp+1B0h+var_20]
0x180138243  xor     rcx, rsp; StackCookie
0x180138246  call    __security_check_cookie
0x18013824b  lea     r11, [rsp+2B0h+var_10]
0x180138253  mov     rbx, [r11+20h]
0x180138257  mov     rsi, [r11+30h]
0x18013825b  mov     rsp, r11
0x18013825e  pop     r14
0x180138260  pop     rdi
0x180138261  pop     rbp
0x180138262  retn
```
