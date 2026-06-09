# DeviceManagebilityCSP::Provider::GetAllEnrollmentInfo(utl::map<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>> *)

- ea: `0x180010a0c`
- end: `0x180010cdd`
- name: `?GetAllEnrollmentInfo@Provider@DeviceManagebilityCSP@@YAJPEAV?$map@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@@utl@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800141d0`

## callees

- `0x1800071c0`
- `0x180010a0c`
- `0x1800118f8`
- `0x180011938`
- `0x180016508`
- `0x18002e1a0`
- `0x18002e5ac`
- `0x180043590`
- `0x18004c594`
- `0x180051dfc`
- `0x180059f88`
- `0x18005e000`
- `0x18007013c`
- `0x180070244`
- `0x180070274`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010af4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010a6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010a6a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010b51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010bf2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010b51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010bf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010ca1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010cb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010ca1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010cb7`

## pseudocode

```c
__int64 __fastcall DeviceManagebilityCSP::Provider::GetAllEnrollmentInfo(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  DWORD v6; // esi
  LSTATUS ValueW; // ebx
  PVOID *v8; // rax
  __int64 v9; // rcx
  PVOID *v10; // rbx
  __int64 v11; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-2B8h]
  int phkResulta; // [rsp+20h] [rbp-2B8h]
  HKEY hKey; // [rsp+40h] [rbp-298h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-290h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-28Ch] BYREF
  PVOID *v17; // [rsp+50h] [rbp-288h] BYREF
  PVOID pvData[4]; // [rsp+58h] [rbp-280h] BYREF
  _BYTE v19[24]; // [rsp+78h] [rbp-260h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::clear(a1);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DeviceManageabilityCSP\\Provider", 0, 0x20119u, &hKey);
  if ( v2 == 2 )
  {
LABEL_25:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( !v2 )
  {
    v6 = 0;
LABEL_9:
    cchName = 260;
    while ( 1 )
    {
      v2 = RegEnumKeyExW(hKey, v6, Name, &cchName, 0, 0, 0, 0);
      if ( v2 == 259 )
        goto LABEL_25;
      if ( v2 )
      {
        v3 = 44;
        goto LABEL_4;
      }
      pcbData = 0;
      if ( RegGetValueW(hKey, Name, L"EnrollmentInfo", 2u, 0, 0, &pcbData) )
      {
        ++v6;
        goto LABEL_9;
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(pvData);
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::reserve(
                               pvData,
                               (unsigned __int64)pcbData >> 1) )
      {
        v4 = -2147024888;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\externalhelpers.cpp",
          (const char *)0x80070008LL,
          phkResulta);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pvData);
        goto LABEL_5;
      }
      v17 = pvData;
      ValueW = RegGetValueW(hKey, Name, L"EnrollmentInfo", 2u, 0, pvData[0], &pcbData);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Buffer::~_Buffer(&v17);
      if ( !ValueW )
      {
        v8 = (PVOID *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
        v10 = v8;
        v17 = v8;
        if ( v8
          && (unsigned __int8)utl::construct<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::operator()<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,unsigned short (&)[260],utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> &>(
                                v9,
                                v8 + 3,
                                Name,
                                pvData) )
        {
          v17 = 0;
        }
        else if ( v10 )
        {
          utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::~pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(v10 + 3);
          v10 = 0;
        }
        utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>>>(&v17);
        utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_EmplaceImpl(
          a1,
          v19,
          v11,
          v10);
      }
      ++v6;
      cchName = 260;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pvData);
    }
  }
  v3 = 28;
LABEL_4:
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v3,
         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\externalhelpers.cpp",
         (const char *)v2,
         phkResult);
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180010a0c  push    rbx
0x180010a0e  push    rsi
0x180010a0f  push    r14
0x180010a11  push    r15
0x180010a13  sub     rsp, 2B8h
0x180010a1a  mov     rax, cs:__security_cookie
0x180010a21  xor     rax, rsp
0x180010a24  mov     [rsp+2D8h+var_38], rax
0x180010a2c  mov     r15, rcx
0x180010a2f  call    ?clear@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::clear(void)
0x180010a34  mov     [rsp+2D8h+hKey], 0
0x180010a3d  xor     edx, edx
0x180010a3f  lea     rcx, [rsp+2D8h+hKey]
0x180010a44  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010a49  lea     rax, [rsp+2D8h+hKey]
0x180010a4e  mov     [rsp+2D8h+phkResult], rax; unsigned int
0x180010a53  mov     r9d, 20119h; samDesired
0x180010a59  xor     r8d, r8d; ulOptions
0x180010a5c  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\DeviceManageabilit"...
0x180010a63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010a6a  call    cs:__imp_RegOpenKeyExW
0x180010a70  cmp     eax, 2
0x180010a73  jz      loc_180010CAD
0x180010a79  test    eax, eax
0x180010a7b  jz      short loc_180010AB2
0x180010a7d  mov     edx, 1Ch; void *
0x180010a82  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180010a89  mov     r9d, eax; char *
0x180010a8c  mov     rcx, [rsp+2D8h]; this
0x180010a94  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010a99  mov     ebx, eax
0x180010a9b  mov     rcx, [rsp+2D8h+hKey]; hKey
0x180010aa0  test    rcx, rcx
0x180010aa3  jz      short loc_180010AAB
0x180010aa5  call    cs:__imp_RegCloseKey
0x180010aab  mov     eax, ebx
0x180010aad  jmp     loc_180010CBF
0x180010ab2  xor     esi, esi
0x180010ab4  mov     [rsp+2D8h+cchName], 104h
0x180010abc  mov     [rsp+2D8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180010ac5  mov     [rsp+2D8h+lpcchClass], 0; lpcchClass
0x180010ace  mov     [rsp+2D8h+lpClass], 0; lpClass
0x180010ad7  mov     [rsp+2D8h+phkResult], 0; lpReserved
0x180010ae0  lea     r9, [rsp+2D8h+cchName]; lpcchName
0x180010ae5  lea     r8, [rsp+2D8h+Name]; lpName
0x180010aed  mov     edx, esi; dwIndex
0x180010aef  mov     rcx, [rsp+2D8h+hKey]; hKey
0x180010af4  call    cs:__imp_RegEnumKeyExW
0x180010afa  cmp     eax, 103h
0x180010aff  jz      loc_180010CAD
0x180010b05  test    eax, eax
0x180010b07  jz      short loc_180010B13
0x180010b09  mov     edx, 2Ch ; ','
0x180010b0e  jmp     loc_180010A82
0x180010b13  mov     [rsp+2D8h+pcbData], 0
0x180010b1b  lea     rax, [rsp+2D8h+pcbData]
0x180010b20  mov     [rsp+2D8h+lpcchClass], rax; pcbData
0x180010b25  mov     [rsp+2D8h+lpClass], 0; pvData
0x180010b2e  mov     [rsp+2D8h+phkResult], 0; int
0x180010b37  mov     r9d, 2; dwFlags
0x180010b3d  lea     r8, aEnrollmentinfo; "EnrollmentInfo"
0x180010b44  lea     rdx, [rsp+2D8h+Name]; lpSubKey
0x180010b4c  mov     rcx, [rsp+2D8h+hKey]; hkey
0x180010b51  call    cs:__imp_RegGetValueW
0x180010b57  test    eax, eax
0x180010b59  jz      short loc_180010B62
0x180010b5b  inc     esi
0x180010b5d  jmp     loc_180010AB4
0x180010b62  lea     rcx, [rsp+2D8h+pvData]
0x180010b67  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180010b6c  mov     edx, [rsp+2D8h+pcbData]
0x180010b70  shr     rdx, 1
0x180010b73  lea     rcx, [rsp+2D8h+pvData]
0x180010b78  call    ?reserve@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::reserve(unsigned __int64)
0x180010b7d  test    al, al
0x180010b7f  jnz     short loc_180010BB1
0x180010b81  mov     rcx, [rsp+2D8h]; this
0x180010b89  mov     ebx, 80070008h
0x180010b8e  mov     r9d, ebx; char *
0x180010b91  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180010b98  mov     edx, 3Fh ; '?'; void *
0x180010b9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ba2  lea     rcx, [rsp+2D8h+pvData]
0x180010ba7  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180010bac  jmp     loc_180010A9B
0x180010bb1  lea     rax, [rsp+2D8h+pvData]
0x180010bb6  mov     [rsp+2D8h+var_288], rax
0x180010bbb  mov     rax, [rsp+2D8h+pvData]
0x180010bc0  lea     rcx, [rsp+2D8h+pcbData]
0x180010bc5  mov     [rsp+2D8h+lpcchClass], rcx; pcbData
0x180010bca  mov     [rsp+2D8h+lpClass], rax; pvData
0x180010bcf  mov     [rsp+2D8h+phkResult], 0; pdwType
0x180010bd8  mov     r9d, 2; dwFlags
0x180010bde  lea     r8, aEnrollmentinfo; "EnrollmentInfo"
0x180010be5  lea     rdx, [rsp+2D8h+Name]; lpSubKey
0x180010bed  mov     rcx, [rsp+2D8h+hKey]; hkey
0x180010bf2  call    cs:__imp_RegGetValueW
0x180010bf8  mov     ebx, eax
0x180010bfa  lea     rcx, [rsp+2D8h+var_288]
0x180010bff  call    ??1_Buffer@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Buffer::~_Buffer(void)
0x180010c04  test    ebx, ebx
0x180010c06  jnz     short loc_180010C74
0x180010c08  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010c0f  lea     ecx, [rbx+58h]; unsigned __int64
0x180010c12  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010c17  mov     rbx, rax
0x180010c1a  mov     [rsp+2D8h+var_288], rax
0x180010c1f  test    rax, rax
0x180010c22  jz      short loc_180010C49
0x180010c24  lea     r9, [rsp+2D8h+pvData]
0x180010c29  lea     r8, [rsp+2D8h+Name]
0x180010c31  lea     rdx, [rax+18h]
0x180010c35  call    ??$?RU?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@AEAY0BAE@GAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@?$construct@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@QEBA_NPEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@1@AEAY0BAE@GAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::construct<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::operator()<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,ushort (&)[260],utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &>(utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *,ushort (&)[260],utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180010c3a  test    al, al
0x180010c3c  jz      short loc_180010C49
0x180010c3e  mov     [rsp+2D8h+var_288], 0
0x180010c47  jmp     short loc_180010C59
0x180010c49  test    rbx, rbx
0x180010c4c  jz      short loc_180010C59
0x180010c4e  lea     rcx, [rbx+18h]
0x180010c52  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@QEAA@XZ; utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::~pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(void)
0x180010c57  xor     ebx, ebx
0x180010c59  lea     rcx, [rsp+2D8h+var_288]
0x180010c5e  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>>>(void)
0x180010c63  mov     r9, rbx
0x180010c66  lea     rdx, [rsp+2D8h+var_260]
0x180010c6b  mov     rcx, r15
0x180010c6e  call    ?_EmplaceImpl@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@AEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@0@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::_EmplaceImpl(utl::_TreeNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *,utl::_TreeNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)
0x180010c73  nop
0x180010c74  inc     esi
0x180010c76  mov     [rsp+2D8h+cchName], 104h
0x180010c7e  lea     rcx, [rsp+2D8h+pvData]
0x180010c83  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180010c88  jmp     loc_180010ABC
0x180010c8d  lea     rcx, [rsp+2D8h+pvData]
0x180010c92  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180010c97  mov     rcx, [rsp+2D8h+hKey]; hKey
0x180010c9c  test    rcx, rcx
0x180010c9f  jz      short loc_180010CA7
0x180010ca1  call    cs:__imp_RegCloseKey
0x180010ca7  mov     eax, dword ptr [rsp+2D8h+var_288]
0x180010cab  jmp     short loc_180010CBF
0x180010cad  mov     rcx, [rsp+2D8h+hKey]; hKey
0x180010cb2  test    rcx, rcx
0x180010cb5  jz      short loc_180010CBD
0x180010cb7  call    cs:__imp_RegCloseKey
0x180010cbd  xor     eax, eax
0x180010cbf  mov     rcx, [rsp+2D8h+var_38]
0x180010cc7  xor     rcx, rsp; StackCookie
0x180010cca  call    __security_check_cookie
0x180010ccf  add     rsp, 2B8h
0x180010cd6  pop     r15
0x180010cd8  pop     r14
0x180010cda  pop     rsi
0x180010cdb  pop     rbx
0x180010cdc  retn
```
