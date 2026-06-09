# MdmLogCollector::DumpRegistryKey(_iobuf *,HKEY__ *,ushort const *)

- ea: `0x18010e23c`
- end: `0x18010e67c`
- name: `?DumpRegistryKey@MdmLogCollector@@CAJPEAU_iobuf@@PEAUHKEY__@@PEBG@Z`
- size: `1088`
- prototype: `__int64 __fastcall(struct _iobuf *, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x18010c120`
- `0x18010e23c`

## callees

- `0x180019000`
- `0x180019514`
- `0x180019fc4`
- `0x1800e66dc`
- `0x1800e7c08`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x180104108`
- `0x180107e60`
- `0x18010e114`
- `0x18010e190`
- `0x18010e23c`
- `0x1801109fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010e35a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010e35a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010e53e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010e53e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010e421`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010e421`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e28e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e28e`

## string_xrefs

- `0x18010e2bb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e36b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e60a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e639`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e65d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
             (void *)0x3C7,
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
                 (void *)0x3E1,
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
              (void *)0x413,
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
               (void *)0x40D,
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
        (void *)0x3BA,
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
0x18010e23c  mov     [rsp-8+arg_18], rbx
0x18010e241  push    rbp
0x18010e242  push    rsi
0x18010e243  push    rdi
0x18010e244  push    r12
0x18010e246  push    r13
0x18010e248  push    r14
0x18010e24a  push    r15
0x18010e24c  lea     rbp, [rsp-27h]
0x18010e251  sub     rsp, 0D0h
0x18010e258  mov     rax, cs:__security_cookie
0x18010e25f  xor     rax, rsp
0x18010e262  mov     [rbp+57h+var_38], rax
0x18010e266  mov     r12, r8
0x18010e269  mov     r15, rdx
0x18010e26c  mov     rsi, rcx
0x18010e26f  xor     r13d, r13d
0x18010e272  mov     [rbp+57h+hKey], r13
0x18010e276  lea     rax, [rbp+57h+hKey]
0x18010e27a  mov     [rsp+100h+phkResult], rax; int
0x18010e27f  mov     r9d, 20019h; samDesired
0x18010e285  xor     r8d, r8d; ulOptions
0x18010e288  mov     rdx, r12; lpSubKey
0x18010e28b  mov     rcx, r15; hKey
0x18010e28e  call    cs:__imp_RegOpenKeyExW
0x18010e294  mov     edi, eax
0x18010e296  test    eax, eax
0x18010e298  jle     short loc_18010E2A3
0x18010e29a  movzx   edi, ax
0x18010e29d  or      edi, 80070000h
0x18010e2a3  test    edi, edi
0x18010e2a5  jns     short loc_18010E2D3
0x18010e2a7  mov     ebx, 80070002h
0x18010e2ac  cmp     edi, ebx
0x18010e2ae  jz      loc_18010E5D1
0x18010e2b4  mov     rcx, [rbp+5Fh]; this
0x18010e2b8  mov     r9d, edi; char *
0x18010e2bb  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e2c2  mov     edx, 3BAh; void *
0x18010e2c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e2cc  mov     ebx, edi
0x18010e2ce  jmp     loc_18010E5D1
0x18010e2d3  lea     rax, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x18010e2da  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18010e2e1  cmp     r15, 0FFFFFFFF80000002h
0x18010e2e8  cmovnz  r8, rax
0x18010e2ec  mov     r9, r12
0x18010e2ef  lea     rdx, aSS_3; "[%s\\%s]\n"
0x18010e2f6  mov     rcx, rsi; struct _iobuf *
0x18010e2f9  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e2fe  mov     [rbp+57h+cSubKeys], r13d
0x18010e302  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18010e306  mov     [rbp+57h+cValues], r13d
0x18010e30a  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x18010e30e  mov     [rbp+57h+cbMaxValueLen], r13d
0x18010e312  mov     [rsp+100h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18010e317  mov     [rsp+100h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18010e31c  lea     rax, [rbp+57h+cbMaxValueLen]
0x18010e320  mov     [rsp+100h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18010e325  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18010e329  mov     [rsp+100h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18010e32e  lea     rax, [rbp+57h+cValues]
0x18010e332  mov     [rsp+100h+lpcValues], rax; lpcValues
0x18010e337  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18010e33c  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18010e340  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18010e345  lea     rax, [rbp+57h+cSubKeys]
0x18010e349  mov     [rsp+100h+phkResult], rax; unsigned int
0x18010e34e  xor     r9d, r9d; lpReserved
0x18010e351  xor     r8d, r8d; lpcchClass
0x18010e354  xor     edx, edx; lpClass
0x18010e356  mov     rcx, [rbp+57h+hKey]; hKey
0x18010e35a  call    cs:__imp_RegQueryInfoKeyW
0x18010e360  test    eax, eax
0x18010e362  jz      short loc_18010E383
0x18010e364  mov     rcx, [rbp+5Fh]; this
0x18010e368  mov     r9d, eax; char *
0x18010e36b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e372  mov     edx, 3C7h; void *
0x18010e377  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010e37c  mov     ebx, eax
0x18010e37e  jmp     loc_18010E5D1
0x18010e383  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18010e386  inc     eax
0x18010e388  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18010e38b  mov     ecx, eax
0x18010e38d  mov     eax, 2
0x18010e392  mul     rcx
0x18010e395  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010e39c  cmovb   rax, rcx
0x18010e3a0  mov     rcx, rax; unsigned __int64
0x18010e3a3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010e3a8  mov     r14, rax
0x18010e3ab  mov     [rbp+57h+var_70], rax
0x18010e3af  mov     ecx, [rbp+57h+cbMaxValueLen]; unsigned __int64
0x18010e3b2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010e3b7  mov     rbx, rax
0x18010e3ba  mov     [rbp+57h+var_78], rax
0x18010e3be  mov     edi, r13d
0x18010e3c1  cmp     [rbp+57h+cValues], r13d
0x18010e3c5  jbe     loc_18010E4CF
0x18010e3cb  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18010e3ce  mov     [rbp+57h+cchValueName], ecx
0x18010e3d1  mov     r8d, ecx
0x18010e3d4  add     r8, r8; Size
0x18010e3d7  xor     edx, edx; Val
0x18010e3d9  mov     rcx, r14; void *
0x18010e3dc  call    memset_0
0x18010e3e1  mov     eax, [rbp+57h+cbMaxValueLen]
0x18010e3e4  mov     [rbp+57h+cbData], eax
0x18010e3e7  mov     r8d, eax; Size
0x18010e3ea  xor     edx, edx; Val
0x18010e3ec  mov     rcx, rbx; void *
0x18010e3ef  call    memset_0
0x18010e3f4  mov     [rbp+57h+Type], r13d
0x18010e3f8  lea     rax, [rbp+57h+cbData]
0x18010e3fc  mov     [rsp+100h+lpcValues], rax; lpcbData
0x18010e401  mov     [rsp+100h+lpcbMaxClassLen], rbx; lpData
0x18010e406  lea     rax, [rbp+57h+Type]
0x18010e40a  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpType
0x18010e40f  mov     [rsp+100h+phkResult], r13; unsigned int
0x18010e414  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18010e418  mov     r8, r14; lpValueName
0x18010e41b  mov     edx, edi; dwIndex
0x18010e41d  mov     rcx, [rbp+57h+hKey]; hKey
0x18010e421  call    cs:__imp_RegEnumValueW
0x18010e427  cmp     eax, 103h
0x18010e42c  jz      loc_18010E4CF
0x18010e432  test    eax, eax
0x18010e434  jnz     loc_18010E603
0x18010e43a  mov     rcx, rsi; struct _iobuf *
0x18010e43d  cmp     [r14], r13w
0x18010e441  jz      short loc_18010E454
0x18010e443  mov     r8, r14
0x18010e446  lea     rdx, aS_1; "    \"%s\"="
0x18010e44d  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e452  jmp     short loc_18010E460
0x18010e454  lea     rdx, asc_1801D2008; "    @="
0x18010e45b  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e460  mov     edx, [rbp+57h+Type]; unsigned int
0x18010e463  mov     eax, edx
0x18010e465  sub     eax, 1
0x18010e468  mov     rcx, rsi; struct _iobuf *
0x18010e46b  jz      short loc_18010E4B5
0x18010e46d  sub     eax, 3
0x18010e470  jz      short loc_18010E4A4
0x18010e472  sub     eax, 3
0x18010e475  jz      short loc_18010E496
0x18010e477  cmp     eax, 4
0x18010e47a  jz      short loc_18010E48A
0x18010e47c  mov     r9d, [rbp+57h+cbData]; unsigned int
0x18010e480  mov     r8, rbx; unsigned __int8 *
0x18010e483  call    ?DumpRegByte@MdmLogCollector@@CAXPEAU_iobuf@@KPEBEK@Z; MdmLogCollector::DumpRegByte(_iobuf *,ulong,uchar const *,ulong)
0x18010e488  jmp     short loc_18010E4C4
0x18010e48a  mov     r8, [rbx]
0x18010e48d  lea     rdx, aQwordI64x; "QWORD:%I64x\n"
0x18010e494  jmp     short loc_18010E4BF
0x18010e496  mov     r8d, [rbp+57h+cbData]; unsigned int
0x18010e49a  mov     rdx, rbx; unsigned __int16 *
0x18010e49d  call    ?DumpRegMultiSz@MdmLogCollector@@CAXPEAU_iobuf@@PEBGK@Z; MdmLogCollector::DumpRegMultiSz(_iobuf *,ushort const *,ulong)
0x18010e4a2  jmp     short loc_18010E4C4
0x18010e4a4  mov     r8d, [rbx]
0x18010e4a7  lea     rdx, aDword08x; "DWORD:%08x\n"
0x18010e4ae  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e4b3  jmp     short loc_18010E4C4
0x18010e4b5  mov     r8, rbx
0x18010e4b8  lea     rdx, aS_4; "\"%s\"\n"
0x18010e4bf  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e4c4  inc     edi
0x18010e4c6  cmp     edi, [rbp+57h+cValues]
0x18010e4c9  jb      loc_18010E3CB
0x18010e4cf  lea     rdx, asc_1801B9CF8; "\n"
0x18010e4d6  mov     rcx, rsi; struct _iobuf *
0x18010e4d9  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e4de  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18010e4e1  inc     ecx
0x18010e4e3  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x18010e4e6  mov     edx, ecx
0x18010e4e8  mov     eax, 2
0x18010e4ed  mul     rdx
0x18010e4f0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010e4f7  cmovb   rax, rcx
0x18010e4fb  mov     rcx, rax; unsigned __int64
0x18010e4fe  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010e503  mov     r14, rax
0x18010e506  mov     [rbp+57h+var_60], rax
0x18010e50a  mov     edi, r13d
0x18010e50d  cmp     [rbp+57h+cSubKeys], r13d
0x18010e511  jbe     loc_18010E5B1
0x18010e517  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18010e51a  mov     [rbp+57h+cchName], ecx
0x18010e51d  mov     [rsp+100h+lpcValues], r13; lpftLastWriteTime
0x18010e522  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcchClass
0x18010e527  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpClass
0x18010e52c  mov     [rsp+100h+phkResult], r13; unsigned int
0x18010e531  lea     r9, [rbp+57h+cchName]; lpcchName
0x18010e535  mov     r8, r14; lpName
0x18010e538  mov     edx, edi; dwIndex
0x18010e53a  mov     rcx, [rbp+57h+hKey]; hKey
0x18010e53e  call    cs:__imp_RegEnumKeyExW
0x18010e544  cmp     eax, 103h
0x18010e549  jz      short loc_18010E5B1
0x18010e54b  test    eax, eax
0x18010e54d  jnz     loc_18010E656
0x18010e553  mov     rdx, r12
0x18010e556  lea     rcx, [rbp+57h+var_58]
0x18010e55a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e55f  nop
0x18010e560  lea     rdx, psz; "\\"
0x18010e567  lea     rcx, [rbp+57h+var_58]
0x18010e56b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010e570  mov     rdx, r14
0x18010e573  lea     rcx, [rbp+57h+var_58]
0x18010e577  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010e57c  lea     rcx, [rbp+57h+var_58]
0x18010e580  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010e585  mov     r8, rax; unsigned __int16 *
0x18010e588  mov     rdx, r15; HKEY
0x18010e58b  mov     rcx, rsi; struct _iobuf *
0x18010e58e  call    ?DumpRegistryKey@MdmLogCollector@@CAJPEAU_iobuf@@PEAUHKEY__@@PEBG@Z; MdmLogCollector::DumpRegistryKey(_iobuf *,HKEY__ *,ushort const *)
0x18010e593  mov     ebx, eax
0x18010e595  test    eax, eax
0x18010e597  js      loc_18010E632
0x18010e59d  lea     rcx, [rbp+57h+var_58]
0x18010e5a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e5a6  inc     edi
0x18010e5a8  cmp     edi, [rbp+57h+cSubKeys]
0x18010e5ab  jb      loc_18010E517
0x18010e5b1  lea     rcx, [rbp+57h+var_60]
0x18010e5b5  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010e5ba  nop
0x18010e5bb  lea     rcx, [rbp+57h+var_78]
0x18010e5bf  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010e5c4  nop
0x18010e5c5  lea     rcx, [rbp+57h+var_70]
0x18010e5c9  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010e5ce  mov     ebx, r13d
0x18010e5d1  lea     rcx, [rbp+57h+hKey]
0x18010e5d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010e5da  mov     eax, ebx
0x18010e5dc  mov     rcx, [rbp+57h+var_38]
0x18010e5e0  xor     rcx, rsp; StackCookie
0x18010e5e3  call    __security_check_cookie
0x18010e5e8  mov     rbx, [rsp+100h+arg_18]
0x18010e5f0  add     rsp, 0D0h
0x18010e5f7  pop     r15
0x18010e5f9  pop     r14
0x18010e5fb  pop     r13
0x18010e5fd  pop     r12
0x18010e5ff  pop     rdi
0x18010e600  pop     rsi
0x18010e601  pop     rbp
0x18010e602  retn
0x18010e603  mov     rcx, [rbp+5Fh]; this
0x18010e607  mov     r9d, eax; char *
0x18010e60a  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e611  mov     edx, 3E1h; void *
0x18010e616  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010e61b  mov     ebx, eax
0x18010e61d  lea     rcx, [rbp+57h+var_78]
0x18010e621  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010e626  nop
0x18010e627  lea     rcx, [rbp+57h+var_70]
0x18010e62b  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010e630  jmp     short loc_18010E5D1
0x18010e632  mov     rcx, [rbp+5Fh]; this
0x18010e636  mov     r9d, eax; char *
0x18010e639  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e640  mov     edx, 413h; void *
0x18010e645  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e64a  nop
0x18010e64b  lea     rcx, [rbp+57h+var_58]
0x18010e64f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e654  jmp     short loc_18010E670
0x18010e656  mov     rcx, [rbp+5Fh]; this
0x18010e65a  mov     r9d, eax; char *
0x18010e65d  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e664  mov     edx, 40Dh; void *
0x18010e669  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010e66e  mov     ebx, eax
0x18010e670  lea     rcx, [rbp+57h+var_60]
0x18010e674  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010e679  jmp     short loc_18010E61D
```
