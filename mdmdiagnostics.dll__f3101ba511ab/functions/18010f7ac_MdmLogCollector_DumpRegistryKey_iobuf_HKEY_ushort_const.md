# MdmLogCollector::DumpRegistryKey(_iobuf *,HKEY__ *,ushort const *)

- ea: `0x18010f7ac`
- end: `0x18010fc05`
- name: `?DumpRegistryKey@MdmLogCollector@@CAJPEAU_iobuf@@PEAUHKEY__@@PEBG@Z`
- size: `1113`
- prototype: `__int64 __fastcall(struct _iobuf *, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x18010d5a0`
- `0x18010f7ac`

## callees

- `0x180019080`
- `0x180019594`
- `0x18001a054`
- `0x1800e68b0`
- `0x1800e7de8`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x180105294`
- `0x180109140`
- `0x18010f684`
- `0x18010f700`
- `0x18010f7ac`
- `0x180111ec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010f8d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010f8d0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010fac0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010fac0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010f99d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010f99d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010f7fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010f7fe`

## string_xrefs

- `0x18010f831`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f8e7`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010fb93`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010fbc2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010fbe6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MdmLogCollector::DumpRegistryKey(struct _iobuf *a1, HKEY a2, const unsigned __int16 *a3)
{
  LSTATUS v6; // eax
  signed int v7; // edi
  unsigned int v8; // ebx
  const wchar_t *v9; // r8
  unsigned int v10; // eax
  _WORD *v11; // r14
  unsigned int *v12; // rbx
  DWORD i; // edi
  unsigned int v14; // eax
  WCHAR *v15; // r14
  DWORD v16; // edi
  unsigned int v17; // eax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  int phkResult; // [rsp+20h] [rbp-89h]
  unsigned int phkResulta; // [rsp+20h] [rbp-89h]
  unsigned int phkResultb; // [rsp+20h] [rbp-89h]
  unsigned int phkResultc; // [rsp+20h] [rbp-89h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-49h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-45h] BYREF
  DWORD cbMaxValueLen; // [rsp+68h] [rbp-41h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-3Dh] BYREF
  DWORD cValues; // [rsp+70h] [rbp-39h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-35h] BYREF
  DWORD Type; // [rsp+78h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-29h] BYREF
  unsigned int *v33; // [rsp+88h] [rbp-21h] BYREF
  _WORD *v34; // [rsp+90h] [rbp-19h] BYREF
  DWORD cchValueName; // [rsp+98h] [rbp-11h] BYREF
  DWORD cchName; // [rsp+9Ch] [rbp-Dh] BYREF
  WCHAR *v37; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v38[32]; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  hKey = 0;
  v6 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    v9 = L"HKEY_LOCAL_MACHINE";
    if ( a2 != HKEY_LOCAL_MACHINE )
      v9 = L"HKEY_CURRENT_USER";
    MdmLogCollector::WriteToFile(a1, L"[%s\\%s]\n", v9, a3);
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    cValues = 0;
    cbMaxValueNameLen = 0;
    cbMaxValueLen = 0;
    v10 = RegQueryInfoKeyW(
            hKey,
            0,
            0,
            0,
            &cSubKeys,
            &cbMaxSubKeyLen,
            0,
            &cValues,
            &cbMaxValueNameLen,
            &cbMaxValueLen,
            0,
            0);
    if ( v10 )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3C6,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
             (const char *)v10,
             phkResulta);
    }
    else
    {
      v11 = operator new[](saturated_mul(++cbMaxValueNameLen, 2u));
      v34 = v11;
      v12 = (unsigned int *)operator new[](cbMaxValueLen);
      v33 = v12;
      for ( i = 0; i < cValues; ++i )
      {
        cchValueName = cbMaxValueNameLen;
        memset_0(v11, 0, 2LL * cbMaxValueNameLen);
        cbData = cbMaxValueLen;
        memset_0(v12, 0, cbMaxValueLen);
        Type = 0;
        v14 = RegEnumValueW(hKey, i, v11, &cchValueName, 0, &Type, (LPBYTE)v12, &cbData);
        if ( v14 == 259 )
          break;
        if ( v14 )
        {
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x3E0,
                 (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                 (const char *)v14,
                 phkResultb);
LABEL_34:
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v33);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v34);
          goto LABEL_32;
        }
        if ( *v11 )
          MdmLogCollector::WriteToFile(a1, L"    \"%s\"=", v11);
        else
          MdmLogCollector::WriteToFile(a1, L"    @=");
        switch ( Type )
        {
          case 1u:
            MdmLogCollector::WriteToFile(a1, L"\"%s\"\n", v12);
            break;
          case 4u:
            MdmLogCollector::WriteToFile(a1, L"DWORD:%08x\n", *v12);
            break;
          case 7u:
            MdmLogCollector::DumpRegMultiSz(a1, (const unsigned __int16 *)v12, cbData);
            break;
          case 0xBu:
            MdmLogCollector::WriteToFile(a1, L"QWORD:%I64x\n", *(_QWORD *)v12);
            break;
          default:
            MdmLogCollector::DumpRegByte(a1, Type, (const unsigned __int8 *)v12, cbData);
            break;
        }
      }
      MdmLogCollector::WriteToFile(a1, L"\n");
      v15 = (WCHAR *)operator new[](saturated_mul(++cbMaxSubKeyLen, 2u));
      v37 = v15;
      v16 = 0;
      if ( cSubKeys )
      {
        while ( 1 )
        {
          cchName = cbMaxSubKeyLen;
          v17 = RegEnumKeyExW(hKey, v16, v15, &cchName, 0, 0, 0, 0);
          if ( v17 == 259 )
            goto LABEL_31;
          if ( v17 )
            break;
          std::wstring::wstring(v38, a3);
          std::wstring::append(v38, L"\\");
          std::wstring::append(v38, v15);
          v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
          v19 = MdmLogCollector::DumpRegistryKey(a1, a2, v18);
          v8 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x412,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
              (const char *)(unsigned int)v19,
              phkResultc);
            std::wstring::_Tidy_deallocate(v38);
LABEL_37:
            std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v37);
            goto LABEL_34;
          }
          std::wstring::_Tidy_deallocate(v38);
          if ( ++v16 >= cSubKeys )
            goto LABEL_31;
        }
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x40C,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
               (const char *)v17,
               phkResultc);
        goto LABEL_37;
      }
LABEL_31:
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v37);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v33);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v34);
      v8 = 0;
    }
  }
  else
  {
    v8 = -2147024894;
    if ( v7 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v7,
        phkResult);
      v8 = v7;
    }
  }
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x18010f7ac  mov     [rsp-8+arg_18], rbx
0x18010f7b1  push    rbp
0x18010f7b2  push    rsi
0x18010f7b3  push    rdi
0x18010f7b4  push    r12
0x18010f7b6  push    r13
0x18010f7b8  push    r14
0x18010f7ba  push    r15
0x18010f7bc  lea     rbp, [rsp-27h]
0x18010f7c1  sub     rsp, 0D0h
0x18010f7c8  mov     rax, cs:__security_cookie
0x18010f7cf  xor     rax, rsp
0x18010f7d2  mov     [rbp+57h+var_38], rax
0x18010f7d6  mov     r12, r8
0x18010f7d9  mov     r15, rdx
0x18010f7dc  mov     rsi, rcx
0x18010f7df  xor     r13d, r13d
0x18010f7e2  mov     [rbp+57h+hKey], r13
0x18010f7e6  lea     rax, [rbp+57h+hKey]
0x18010f7ea  mov     [rsp+100h+phkResult], rax; int
0x18010f7ef  mov     r9d, 20019h; samDesired
0x18010f7f5  xor     r8d, r8d; ulOptions
0x18010f7f8  mov     rdx, r12; lpSubKey
0x18010f7fb  mov     rcx, r15; hKey
0x18010f7fe  call    cs:__imp_RegOpenKeyExW
0x18010f805  nop     dword ptr [rax+rax+00h]
0x18010f80a  mov     edi, eax
0x18010f80c  test    eax, eax
0x18010f80e  jle     short loc_18010F819
0x18010f810  movzx   edi, ax
0x18010f813  or      edi, 80070000h
0x18010f819  test    edi, edi
0x18010f81b  jns     short loc_18010F849
0x18010f81d  mov     ebx, 80070002h
0x18010f822  cmp     edi, ebx
0x18010f824  jz      loc_18010FB59
0x18010f82a  mov     rcx, [rbp+5Fh]; this
0x18010f82e  mov     r9d, edi; char *
0x18010f831  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f838  mov     edx, 3B9h; void *
0x18010f83d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f842  mov     ebx, edi
0x18010f844  jmp     loc_18010FB59
0x18010f849  lea     rax, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x18010f850  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18010f857  cmp     r15, 0FFFFFFFF80000002h
0x18010f85e  cmovnz  r8, rax
0x18010f862  mov     r9, r12
0x18010f865  lea     rdx, aSS_3; "[%s\\%s]\n"
0x18010f86c  mov     rcx, rsi; struct _iobuf *
0x18010f86f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f874  mov     [rbp+57h+cSubKeys], r13d
0x18010f878  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18010f87c  mov     [rbp+57h+cValues], r13d
0x18010f880  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x18010f884  mov     [rbp+57h+cbMaxValueLen], r13d
0x18010f888  mov     [rsp+100h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18010f88d  mov     [rsp+100h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18010f892  lea     rax, [rbp+57h+cbMaxValueLen]
0x18010f896  mov     [rsp+100h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18010f89b  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18010f89f  mov     [rsp+100h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18010f8a4  lea     rax, [rbp+57h+cValues]
0x18010f8a8  mov     [rsp+100h+lpcValues], rax; lpcValues
0x18010f8ad  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18010f8b2  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18010f8b6  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18010f8bb  lea     rax, [rbp+57h+cSubKeys]
0x18010f8bf  mov     [rsp+100h+phkResult], rax; unsigned int
0x18010f8c4  xor     r9d, r9d; lpReserved
0x18010f8c7  xor     r8d, r8d; lpcchClass
0x18010f8ca  xor     edx, edx; lpClass
0x18010f8cc  mov     rcx, [rbp+57h+hKey]; hKey
0x18010f8d0  call    cs:__imp_RegQueryInfoKeyW
0x18010f8d7  nop     dword ptr [rax+rax+00h]
0x18010f8dc  test    eax, eax
0x18010f8de  jz      short loc_18010F8FF
0x18010f8e0  mov     rcx, [rbp+5Fh]; this
0x18010f8e4  mov     r9d, eax; char *
0x18010f8e7  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f8ee  mov     edx, 3C6h; void *
0x18010f8f3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010f8f8  mov     ebx, eax
0x18010f8fa  jmp     loc_18010FB59
0x18010f8ff  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18010f902  inc     eax
0x18010f904  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18010f907  mov     ecx, eax
0x18010f909  mov     eax, 2
0x18010f90e  mul     rcx
0x18010f911  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010f918  cmovb   rax, rcx
0x18010f91c  mov     rcx, rax; unsigned __int64
0x18010f91f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010f924  mov     r14, rax
0x18010f927  mov     [rbp+57h+var_70], rax
0x18010f92b  mov     ecx, [rbp+57h+cbMaxValueLen]; unsigned __int64
0x18010f92e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010f933  mov     rbx, rax
0x18010f936  mov     [rbp+57h+var_78], rax
0x18010f93a  mov     edi, r13d
0x18010f93d  cmp     [rbp+57h+cValues], r13d
0x18010f941  jbe     loc_18010FA51
0x18010f947  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18010f94a  mov     [rbp+57h+cchValueName], ecx
0x18010f94d  mov     r8d, ecx
0x18010f950  add     r8, r8; Size
0x18010f953  xor     edx, edx; Val
0x18010f955  mov     rcx, r14; void *
0x18010f958  call    memset_0
0x18010f95d  mov     eax, [rbp+57h+cbMaxValueLen]
0x18010f960  mov     [rbp+57h+cbData], eax
0x18010f963  mov     r8d, eax; Size
0x18010f966  xor     edx, edx; Val
0x18010f968  mov     rcx, rbx; void *
0x18010f96b  call    memset_0
0x18010f970  mov     [rbp+57h+Type], r13d
0x18010f974  lea     rax, [rbp+57h+cbData]
0x18010f978  mov     [rsp+100h+lpcValues], rax; lpcbData
0x18010f97d  mov     [rsp+100h+lpcbMaxClassLen], rbx; lpData
0x18010f982  lea     rax, [rbp+57h+Type]
0x18010f986  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpType
0x18010f98b  mov     [rsp+100h+phkResult], r13; unsigned int
0x18010f990  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18010f994  mov     r8, r14; lpValueName
0x18010f997  mov     edx, edi; dwIndex
0x18010f999  mov     rcx, [rbp+57h+hKey]; hKey
0x18010f99d  call    cs:__imp_RegEnumValueW
0x18010f9a4  nop     dword ptr [rax+rax+00h]
0x18010f9a9  cmp     eax, 103h
0x18010f9ae  jz      loc_18010FA51
0x18010f9b4  test    eax, eax
0x18010f9b6  jnz     loc_18010FB8C
0x18010f9bc  mov     rcx, rsi; struct _iobuf *
0x18010f9bf  cmp     [r14], r13w
0x18010f9c3  jz      short loc_18010F9D6
0x18010f9c5  mov     r8, r14
0x18010f9c8  lea     rdx, aS_1; "    \"%s\"="
0x18010f9cf  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f9d4  jmp     short loc_18010F9E2
0x18010f9d6  lea     rdx, asc_1801D3FF8; "    @="
0x18010f9dd  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f9e2  mov     edx, [rbp+57h+Type]; unsigned int
0x18010f9e5  mov     eax, edx
0x18010f9e7  sub     eax, 1
0x18010f9ea  mov     rcx, rsi; struct _iobuf *
0x18010f9ed  jz      short loc_18010FA37
0x18010f9ef  sub     eax, 3
0x18010f9f2  jz      short loc_18010FA26
0x18010f9f4  sub     eax, 3
0x18010f9f7  jz      short loc_18010FA18
0x18010f9f9  cmp     eax, 4
0x18010f9fc  jz      short loc_18010FA0C
0x18010f9fe  mov     r9d, [rbp+57h+cbData]; unsigned int
0x18010fa02  mov     r8, rbx; unsigned __int8 *
0x18010fa05  call    ?DumpRegByte@MdmLogCollector@@CAXPEAU_iobuf@@KPEBEK@Z; MdmLogCollector::DumpRegByte(_iobuf *,ulong,uchar const *,ulong)
0x18010fa0a  jmp     short loc_18010FA46
0x18010fa0c  mov     r8, [rbx]
0x18010fa0f  lea     rdx, aQwordI64x; "QWORD:%I64x\n"
0x18010fa16  jmp     short loc_18010FA41
0x18010fa18  mov     r8d, [rbp+57h+cbData]; unsigned int
0x18010fa1c  mov     rdx, rbx; unsigned __int16 *
0x18010fa1f  call    ?DumpRegMultiSz@MdmLogCollector@@CAXPEAU_iobuf@@PEBGK@Z; MdmLogCollector::DumpRegMultiSz(_iobuf *,ushort const *,ulong)
0x18010fa24  jmp     short loc_18010FA46
0x18010fa26  mov     r8d, [rbx]
0x18010fa29  lea     rdx, aDword08x; "DWORD:%08x\n"
0x18010fa30  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010fa35  jmp     short loc_18010FA46
0x18010fa37  mov     r8, rbx
0x18010fa3a  lea     rdx, aS_4; "\"%s\"\n"
0x18010fa41  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010fa46  inc     edi
0x18010fa48  cmp     edi, [rbp+57h+cValues]
0x18010fa4b  jb      loc_18010F947
0x18010fa51  lea     rdx, asc_1801BBCF8; "\n"
0x18010fa58  mov     rcx, rsi; struct _iobuf *
0x18010fa5b  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010fa60  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18010fa63  inc     ecx
0x18010fa65  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x18010fa68  mov     edx, ecx
0x18010fa6a  mov     eax, 2
0x18010fa6f  mul     rdx
0x18010fa72  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010fa79  cmovb   rax, rcx
0x18010fa7d  mov     rcx, rax; unsigned __int64
0x18010fa80  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010fa85  mov     r14, rax
0x18010fa88  mov     [rbp+57h+var_60], rax
0x18010fa8c  mov     edi, r13d
0x18010fa8f  cmp     [rbp+57h+cSubKeys], r13d
0x18010fa93  jbe     loc_18010FB39
0x18010fa99  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18010fa9c  mov     [rbp+57h+cchName], ecx
0x18010fa9f  mov     [rsp+100h+lpcValues], r13; lpftLastWriteTime
0x18010faa4  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcchClass
0x18010faa9  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpClass
0x18010faae  mov     [rsp+100h+phkResult], r13; unsigned int
0x18010fab3  lea     r9, [rbp+57h+cchName]; lpcchName
0x18010fab7  mov     r8, r14; lpName
0x18010faba  mov     edx, edi; dwIndex
0x18010fabc  mov     rcx, [rbp+57h+hKey]; hKey
0x18010fac0  call    cs:__imp_RegEnumKeyExW
0x18010fac7  nop     dword ptr [rax+rax+00h]
0x18010facc  cmp     eax, 103h
0x18010fad1  jz      short loc_18010FB39
0x18010fad3  test    eax, eax
0x18010fad5  jnz     loc_18010FBDF
0x18010fadb  mov     rdx, r12
0x18010fade  lea     rcx, [rbp+57h+var_58]
0x18010fae2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010fae7  nop
0x18010fae8  lea     rdx, psz; "\\"
0x18010faef  lea     rcx, [rbp+57h+var_58]
0x18010faf3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010faf8  mov     rdx, r14
0x18010fafb  lea     rcx, [rbp+57h+var_58]
0x18010faff  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010fb04  lea     rcx, [rbp+57h+var_58]
0x18010fb08  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010fb0d  mov     r8, rax; unsigned __int16 *
0x18010fb10  mov     rdx, r15; HKEY
0x18010fb13  mov     rcx, rsi; struct _iobuf *
0x18010fb16  call    ?DumpRegistryKey@MdmLogCollector@@CAJPEAU_iobuf@@PEAUHKEY__@@PEBG@Z; MdmLogCollector::DumpRegistryKey(_iobuf *,HKEY__ *,ushort const *)
0x18010fb1b  mov     ebx, eax
0x18010fb1d  test    eax, eax
0x18010fb1f  js      loc_18010FBBB
0x18010fb25  lea     rcx, [rbp+57h+var_58]
0x18010fb29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010fb2e  inc     edi
0x18010fb30  cmp     edi, [rbp+57h+cSubKeys]
0x18010fb33  jb      loc_18010FA99
0x18010fb39  lea     rcx, [rbp+57h+var_60]
0x18010fb3d  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010fb42  nop
0x18010fb43  lea     rcx, [rbp+57h+var_78]
0x18010fb47  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010fb4c  nop
0x18010fb4d  lea     rcx, [rbp+57h+var_70]
0x18010fb51  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010fb56  mov     ebx, r13d
0x18010fb59  lea     rcx, [rbp+57h+hKey]
0x18010fb5d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010fb62  mov     eax, ebx
0x18010fb64  mov     rcx, [rbp+57h+var_38]
0x18010fb68  xor     rcx, rsp; StackCookie
0x18010fb6b  call    __security_check_cookie
0x18010fb70  mov     rbx, [rsp+100h+arg_18]
0x18010fb78  add     rsp, 0D0h
0x18010fb7f  pop     r15
0x18010fb81  pop     r14
0x18010fb83  pop     r13
0x18010fb85  pop     r12
0x18010fb87  pop     rdi
0x18010fb88  pop     rsi
0x18010fb89  pop     rbp
0x18010fb8a  retn
0x18010fb8c  mov     rcx, [rbp+5Fh]; this
0x18010fb90  mov     r9d, eax; char *
0x18010fb93  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010fb9a  mov     edx, 3E0h; void *
0x18010fb9f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010fba4  mov     ebx, eax
0x18010fba6  lea     rcx, [rbp+57h+var_78]
0x18010fbaa  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010fbaf  nop
0x18010fbb0  lea     rcx, [rbp+57h+var_70]
0x18010fbb4  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010fbb9  jmp     short loc_18010FB59
0x18010fbbb  mov     rcx, [rbp+5Fh]; this
0x18010fbbf  mov     r9d, eax; char *
0x18010fbc2  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010fbc9  mov     edx, 412h; void *
0x18010fbce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010fbd3  nop
0x18010fbd4  lea     rcx, [rbp+57h+var_58]
0x18010fbd8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010fbdd  jmp     short loc_18010FBF9
0x18010fbdf  mov     rcx, [rbp+5Fh]; this
0x18010fbe3  mov     r9d, eax; char *
0x18010fbe6  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010fbed  mov     edx, 40Ch; void *
0x18010fbf2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010fbf7  mov     ebx, eax
0x18010fbf9  lea     rcx, [rbp+57h+var_60]
0x18010fbfd  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010fc02  jmp     short loc_18010FBA6
```
