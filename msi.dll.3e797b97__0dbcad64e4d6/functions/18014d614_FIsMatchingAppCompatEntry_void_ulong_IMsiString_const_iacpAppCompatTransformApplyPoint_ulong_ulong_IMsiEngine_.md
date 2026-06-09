# FIsMatchingAppCompatEntry(void *,ulong,IMsiString const &,iacpAppCompatTransformApplyPoint,ulong *,ulong *,IMsiEngine &,IMsiDatabase &)

- ea: `0x18014d614`
- end: `0x18014de6b`
- name: `?FIsMatchingAppCompatEntry@@YA_NPEAXKAEBVIMsiString@@W4iacpAppCompatTransformApplyPoint@@PEAK3AEAVIMsiEngine@@AEAVIMsiDatabase@@@Z`
- size: `2135`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180005b1c`

## callees

- `0x18000c4bc`
- `0x180019290`
- `0x180019cc0`
- `0x18014d614`
- `0x18014de74`
- `0x18015cc9c`
- `0x18021e770`
- `0x18021eae8`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18014da93`
- `msvcrt!_wcsnicmp` at `0x18014db8a`
- `msvcrt!_wcsnicmp` at `0x18014dc2e`
- `msvcrt!_wcsnicmp` at `0x18014da93`
- `msvcrt!_wcsnicmp` at `0x18014db8a`
- `msvcrt!_wcsnicmp` at `0x18014dc2e`
- `KERNEL32!lstrlenW` at `0x18014dcec`
- `KERNEL32!lstrlenW` at `0x18014dcec`
- `KERNEL32!lstrcmpiW` at `0x18014d9b6`
- `KERNEL32!lstrcmpiW` at `0x18014d9e1`
- `KERNEL32!lstrcmpiW` at `0x18014da0a`
- `KERNEL32!lstrcmpiW` at `0x18014da33`
- `KERNEL32!lstrcmpiW` at `0x18014da5c`
- `KERNEL32!lstrcmpiW` at `0x18014d9b6`
- `KERNEL32!lstrcmpiW` at `0x18014d9e1`
- `KERNEL32!lstrcmpiW` at `0x18014da0a`
- `KERNEL32!lstrcmpiW` at `0x18014da33`
- `KERNEL32!lstrcmpiW` at `0x18014da5c`

## string_xrefs

- `0x18014d820`: `SHIMSERVICEPACKLEVEL`
- `0x18014da52`: `SHIMSERVICEPACKLEVEL`
- `0x18014d6b4`: `MINMSIVERSION`
- `0x18014d9ac`: `MINMSIVERSION`
- `0x18014dd8f`: `APPCOMPAT: SdbQueryData failed unexpectedly.  Sdb may be invalid.`
- `0x18014d720`: `APPCOMPAT: invalid minimum version string '%s' found.`
- `0x18014d7a4`: `APPCOMPAT: skipping this entry.  Minimum MSI version required: '%s'; current version: %d.%02d.%04d.%02d.`
- `0x18014da89`: `MSIPROPERTY_`
- `0x18014d8b7`: `APPCOMPAT: skipping transform because it should be applied at a different point of the install.`
- `0x18014dd28`: `APPCOMPAT: mismatched attributes.  Property: '%s'; expected value: '%s'; true value: '%s'`
- `0x18014dad5`: `APPCOMPAT: testing Property value.  Property: '%s'; expected value: '%s'`
- `0x18014dbaf`: `APPCOMPAT: testing PackageCode.  Expected value: '%s'`
- `0x18014dc4c`: `APPCOMPAT: testing cell data in '%s' table.`
- `0x18014dc24`: `MSIDBCELL`
- `0x18014ddf0`: `APPCOMPAT: PackageCode attribute(s) exist, but no matching PackageCode found.  Actual PackageCode: '%s'`
- `0x18014dcb4`: `APPCOMPAT: ignoring unknown data.  Data name: '%s', data type: %d`

## pseudocode

```c
char __fastcall FIsMatchingAppCompatEntry(
        void *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        _DWORD *a6,
        __int64 a7,
        struct IMsiDatabase *a8)
{
  void *v9; // r12
  char v10; // r13
  char v12; // r15
  int v14; // ebx
  LPCWSTR v15; // r14
  char v16; // bl
  const unsigned __int16 *v17; // rax
  __int64 v18; // rbx
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // rax
  unsigned int v21; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+64h] [rbp-9Ch]
  unsigned __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  __int64 v26; // [rsp+80h] [rbp-80h]
  void *v27; // [rsp+88h] [rbp-78h]
  struct IMsiDatabase *v28; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v29; // [rsp+A0h] [rbp-60h] BYREF
  int v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+ACh] [rbp-54h]
  _BYTE v32[256]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpString1; // [rsp+1B0h] [rbp+B0h] BYREF
  int v34; // [rsp+1B8h] [rbp+B8h]
  int v35; // [rsp+1BCh] [rbp+BCh]
  _BYTE v36[256]; // [rsp+1C0h] [rbp+C0h] BYREF

  v9 = a1;
  v26 = a7;
  v10 = 0;
  v25 = a3;
  v24 = a2;
  v27 = a1;
  v28 = a8;
  v21 = 0;
  memset_0(v32, 0, sizeof(v32));
  v29 = (unsigned __int16 *)v32;
  v30 = 256;
  v31 = 256;
  v12 = 1;
  if ( !(unsigned int)LocalSdbQueryData(
                        (_DWORD)v9,
                        a2,
                        (unsigned int)L"MINMSIVERSION",
                        (unsigned int)&v21,
                        (__int64)&v29,
                        0)
    && v21 == 1 )
  {
    v23 = 0;
    if ( !(unsigned int)ParseVersionString(v29, (char *)&v23 + 4, &v23) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: invalid minimum version string '%s' found.",
          v29,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( v30 > 256 )
        operator delete(v29);
      return 0;
    }
    if ( v23 > 0x50000271B0000LL )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: skipping this entry.  Minimum MSI version required: '%s'; current version: %d.%02d.%04d.%02d.",
          v29,
          (const unsigned __int16 *)5,
          0,
          (const unsigned __int16 *)0x271B,
          0,
          L"(NULL)",
          0,
          0);
LABEL_23:
      CTempBuffer<unsigned short,256>::~CTempBuffer<unsigned short,256>(&v29);
      return 0;
    }
  }
  v31 = 256;
  if ( !(unsigned int)LocalSdbQueryData(
                        (_DWORD)v9,
                        a2,
                        (unsigned int)L"SHIMVERSIONNT",
                        (unsigned int)&v21,
                        (__int64)&v29,
                        0)
    && v21 == 4 )
  {
    *a5 = *(_DWORD *)v29;
    v31 = 256;
    if ( !(unsigned int)LocalSdbQueryData(
                          (_DWORD)v9,
                          a2,
                          (unsigned int)L"SHIMSERVICEPACKLEVEL",
                          (unsigned int)&v21,
                          (__int64)&v29,
                          0)
      && v21 == 4 )
    {
      *a6 = *(_DWORD *)v29;
    }
  }
  v31 = 256;
  v14 = 1;
  if ( !(unsigned int)LocalSdbQueryData(
                        (_DWORD)v9,
                        a2,
                        (unsigned int)L"APPLYPOINT",
                        (unsigned int)&v21,
                        (__int64)&v29,
                        0)
    && v21 == 4 )
  {
    v14 = *(_DWORD *)v29;
  }
  if ( v14 != a4 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: skipping transform because it should be applied at a different point of the install.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_23;
  }
  memset_0(v36, 0, sizeof(v36));
  v34 = 256;
  lpString1 = (LPCWSTR)v36;
  v35 = 256;
  if ( !(unsigned __int8)GetSdbDataNames(v9, a2, &lpString1) )
    goto LABEL_74;
  v15 = lpString1;
  v16 = 0;
  v22 = 0;
  while ( *v15 )
  {
    LODWORD(v23) = 0;
    v31 = 256;
    if ( (unsigned int)LocalSdbQueryData((_DWORD)v9, v24, (_DWORD)v15, (unsigned int)&v21, (__int64)&v29, (__int64)&v23) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: SdbQueryData failed unexpectedly.  Sdb may be invalid.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_66;
    }
    v17 = (const unsigned __int16 *)v21;
    if ( v21 == 1 )
    {
      if ( !lstrcmpiW(v15, L"MINMSIVERSION") )
        goto LABEL_62;
      v17 = (const unsigned __int16 *)v21;
    }
    if ( (_DWORD)v17 == 4 )
    {
      if ( !lstrcmpiW(v15, L"APPLYPOINT") )
        goto LABEL_62;
      v17 = (const unsigned __int16 *)v21;
      if ( v21 == 4 )
      {
        if ( !lstrcmpiW(v15, L"SHIMFLAGS") )
          goto LABEL_62;
        v17 = (const unsigned __int16 *)v21;
        if ( v21 == 4 )
        {
          if ( !lstrcmpiW(v15, L"SHIMVERSIONNT") )
            goto LABEL_62;
          v17 = (const unsigned __int16 *)v21;
          if ( v21 == 4 )
          {
            if ( !lstrcmpiW(v15, L"SHIMSERVICEPACKLEVEL") )
              goto LABEL_62;
            v17 = (const unsigned __int16 *)v21;
          }
        }
      }
    }
    if ( (unsigned int)v17 > 1 )
      goto LABEL_60;
    if ( _wcsnicmp(v15, L"MSIPROPERTY_", 0xCu) )
    {
      v17 = (const unsigned __int16 *)v21;
      if ( v21 != 1 )
        goto LABEL_60;
      if ( !_wcsnicmp(v15, L"PACKAGECODE", 0xBu) )
      {
        v16 = 1;
        v22 = 1;
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: testing PackageCode.  Expected value: '%s'",
            v29,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v25 + 200LL))(
               v25,
               1,
               v29) )
        {
          v10 = 1;
        }
        goto LABEL_62;
      }
      v17 = (const unsigned __int16 *)v21;
      if ( v21 != 1 )
        goto LABEL_60;
      if ( _wcsnicmp(v15, L"MSIDBCELL", 9u) )
      {
        v17 = (const unsigned __int16 *)v21;
LABEL_60:
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: ignoring unknown data.  Data name: '%s', data type: %d",
            v15,
            v17,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_62;
      }
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: testing cell data in '%s' table.",
          v29,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( !FCheckDatabaseCell(v9, v23, v28, v29) )
        goto LABEL_66;
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(__int64, LPCWSTR))(*(_QWORD *)v26 + 184LL))(v26, v15 + 12);
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: testing Property value.  Property: '%s'; expected value: '%s'",
          v15 + 12,
          v29,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v18 + 200LL))(v18, 0, v29)
        || !(*(unsigned int (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v18 + 200LL))(v18, 7, v29) )
      {
        if ( g_dmDiagnosticMode )
        {
          v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 80LL))(v18);
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: mismatched attributes.  Property: '%s'; expected value: '%s'; true value: '%s'",
            v15 + 12,
            v29,
            v19,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_66:
        CTempBuffer<unsigned short,256>::~CTempBuffer<unsigned short,256>(&lpString1);
        goto LABEL_23;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v16 = v22;
      v9 = v27;
    }
LABEL_62:
    v15 += lstrlenW(v15) + 1;
  }
  if ( v16 == 1 && !v10 )
  {
    if ( g_dmDiagnosticMode )
    {
      v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: PackageCode attribute(s) exist, but no matching PackageCode found.  Actual PackageCode: '%s'",
        v20,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v12 = 0;
  }
LABEL_74:
  CTempBuffer<unsigned short,256>::~CTempBuffer<unsigned short,256>(&lpString1);
  CTempBuffer<unsigned short,256>::~CTempBuffer<unsigned short,256>(&v29);
  return v12;
}

```

## disassembly

```asm
0x18014d614  mov     [rsp-8+arg_18], rbx
0x18014d619  push    rbp
0x18014d61a  push    rsi
0x18014d61b  push    rdi
0x18014d61c  push    r12
0x18014d61e  push    r13
0x18014d620  push    r14
0x18014d622  push    r15
0x18014d624  lea     rbp, [rsp-1D0h]
0x18014d62c  sub     rsp, 2D0h
0x18014d633  mov     rax, cs:__security_cookie
0x18014d63a  xor     rax, rsp
0x18014d63d  mov     [rbp+200h+var_40], rax
0x18014d644  mov     rax, [rbp+200h+arg_30]
0x18014d64b  mov     r14d, edx
0x18014d64e  mov     rdi, [rbp+200h+arg_20]
0x18014d655  mov     r12, rcx
0x18014d658  mov     rbx, [rbp+200h+arg_28]
0x18014d65f  mov     r15d, 100h
0x18014d665  mov     [rbp+200h+var_280], rax
0x18014d669  xor     r13d, r13d
0x18014d66c  mov     rax, [rbp+200h+arg_38]
0x18014d673  mov     esi, r9d
0x18014d676  mov     [rsp+300h+var_288], r8
0x18014d67b  mov     r8d, r15d; Size
0x18014d67e  mov     [rsp+300h+var_290], edx
0x18014d682  xor     edx, edx; Val
0x18014d684  mov     [rbp+200h+var_278], rcx
0x18014d688  lea     rcx, [rbp+200h+var_250]; void *
0x18014d68c  mov     [rbp+200h+var_270], rax
0x18014d690  mov     dword ptr [rsp+300h+var_2A0], r13d
0x18014d695  call    memset_0
0x18014d69a  lea     rax, [rbp+200h+var_250]
0x18014d69e  mov     [rsp+300h+var_2D8], r13
0x18014d6a3  mov     [rbp+200h+var_260], rax
0x18014d6a7  lea     r9, [rsp+300h+var_2A0]
0x18014d6ac  lea     rax, [rbp+200h+var_260]
0x18014d6b0  mov     [rbp+200h+var_258], r15d
0x18014d6b4  lea     r8, aMinmsiversion; "MINMSIVERSION"
0x18014d6bb  mov     [rsp+300h+var_2E0], rax
0x18014d6c0  mov     edx, r14d
0x18014d6c3  mov     [rbp+200h+var_254], r15d
0x18014d6c7  mov     rcx, r12
0x18014d6ca  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x18014d6cf  lea     r15d, [r13+1]
0x18014d6d3  test    eax, eax
0x18014d6d5  jnz     loc_18014D7DB
0x18014d6db  cmp     dword ptr [rsp+300h+var_2A0], r15d
0x18014d6e0  jnz     loc_18014D7DB
0x18014d6e6  mov     rcx, [rbp+200h+var_260]
0x18014d6ea  lea     r8, [rsp+300h+var_298]
0x18014d6ef  lea     rdx, [rsp+300h+var_298+4]
0x18014d6f4  mov     dword ptr [rsp+300h+var_298+4], r13d
0x18014d6f9  mov     dword ptr [rsp+300h+var_298], r13d
0x18014d6fe  call    ?ParseVersionString@@YA?AW4Bool@@PEBGAEAK1@Z; ParseVersionString(ushort const *,ulong &,ulong &)
0x18014d703  test    eax, eax
0x18014d705  jnz     short loc_18014D770
0x18014d707  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18014d70e  jz      short loc_18014D757
0x18014d710  mov     rax, [rbp+200h+var_260]
0x18014d714  lea     rdi, aNull; "(NULL)"
0x18014d71b  mov     [rsp+300h+var_2A8], r13; void *
0x18014d720  lea     r9, aAppcompatInval; "APPCOMPAT: invalid minimum version stri"...
0x18014d727  mov     [rsp+300h+var_2B0], r13d; unsigned int
0x18014d72c  xor     edx, edx; unsigned __int16
0x18014d72e  mov     [rsp+300h+var_2B8], rdi; unsigned __int16 *
0x18014d733  xor     r8d, r8d; int
0x18014d736  mov     [rsp+300h+var_2C0], rdi; unsigned __int16 *
0x18014d73b  mov     [rsp+300h+var_2C8], rdi; unsigned __int16 *
0x18014d740  mov     [rsp+300h+var_2D0], rdi; unsigned __int16 *
0x18014d745  lea     ecx, [rdx+9]; int
0x18014d748  mov     [rsp+300h+var_2D8], rdi; unsigned __int16 *
0x18014d74d  mov     [rsp+300h+var_2E0], rax; unsigned __int16 *
0x18014d752  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18014d757  cmp     [rbp+200h+var_258], 100h
0x18014d75e  jle     short loc_18014D769
0x18014d760  mov     rcx, [rbp+200h+var_260]; void *
0x18014d764  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18014d769  xor     al, al
0x18014d76b  jmp     loc_18014DE40
0x18014d770  mov     eax, 50000h
0x18014d775  cmp     dword ptr [rsp+300h+var_298+4], eax
0x18014d779  ja      short loc_18014D787
0x18014d77b  jnz     short loc_18014D7DB
0x18014d77d  cmp     dword ptr [rsp+300h+var_298], 271B0000h
0x18014d785  jbe     short loc_18014D7DB
0x18014d787  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18014d78e  jz      loc_18014D8E9
0x18014d794  mov     rax, [rbp+200h+var_260]
0x18014d798  lea     rdi, aNull; "(NULL)"
0x18014d79f  mov     [rsp+300h+var_2A8], r13
0x18014d7a4  lea     r9, aAppcompatSkipp; "APPCOMPAT: skipping this entry.  Minimu"...
0x18014d7ab  mov     [rsp+300h+var_2B0], r13d
0x18014d7b0  mov     [rsp+300h+var_2B8], rdi
0x18014d7b5  mov     [rsp+300h+var_2C0], r13
0x18014d7ba  mov     [rsp+300h+var_2C8], 271Bh
0x18014d7c3  mov     [rsp+300h+var_2D0], r13
0x18014d7c8  mov     [rsp+300h+var_2D8], 5
0x18014d7d1  mov     [rsp+300h+var_2E0], rax
0x18014d7d6  jmp     loc_18014D8DC
0x18014d7db  lea     rax, [rbp+200h+var_260]
0x18014d7df  mov     [rsp+300h+var_2D8], r13
0x18014d7e4  lea     r9, [rsp+300h+var_2A0]
0x18014d7e9  mov     [rsp+300h+var_2E0], rax
0x18014d7ee  lea     r8, aShimversionnt_1; "SHIMVERSIONNT"
0x18014d7f5  mov     [rbp+200h+var_254], 100h
0x18014d7fc  mov     edx, r14d
0x18014d7ff  mov     rcx, r12
0x18014d802  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x18014d807  test    eax, eax
0x18014d809  jnz     short loc_18014D859
0x18014d80b  cmp     dword ptr [rsp+300h+var_2A0], 4
0x18014d810  jnz     short loc_18014D859
0x18014d812  mov     rax, [rbp+200h+var_260]
0x18014d816  lea     r9, [rsp+300h+var_2A0]
0x18014d81b  mov     [rsp+300h+var_2D8], r13
0x18014d820  lea     r8, aShimservicepac_0; "SHIMSERVICEPACKLEVEL"
0x18014d827  mov     edx, r14d
0x18014d82a  mov     ecx, [rax]
0x18014d82c  lea     rax, [rbp+200h+var_260]
0x18014d830  mov     [rdi], ecx
0x18014d832  mov     rcx, r12
0x18014d835  mov     [rsp+300h+var_2E0], rax
0x18014d83a  mov     [rbp+200h+var_254], 100h
0x18014d841  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x18014d846  test    eax, eax
0x18014d848  jnz     short loc_18014D859
0x18014d84a  cmp     dword ptr [rsp+300h+var_2A0], 4
0x18014d84f  jnz     short loc_18014D859
0x18014d851  mov     rax, [rbp+200h+var_260]
0x18014d855  mov     ecx, [rax]
0x18014d857  mov     [rbx], ecx
0x18014d859  lea     rax, [rbp+200h+var_260]
0x18014d85d  mov     [rsp+300h+var_2D8], r13
0x18014d862  lea     r9, [rsp+300h+var_2A0]
0x18014d867  mov     [rsp+300h+var_2E0], rax
0x18014d86c  lea     r8, aApplypoint; "APPLYPOINT"
0x18014d873  mov     [rbp+200h+var_254], 100h
0x18014d87a  mov     edx, r14d
0x18014d87d  mov     rcx, r12
0x18014d880  mov     ebx, r15d
0x18014d883  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x18014d888  test    eax, eax
0x18014d88a  jnz     short loc_18014D899
0x18014d88c  cmp     dword ptr [rsp+300h+var_2A0], 4
0x18014d891  jnz     short loc_18014D899
0x18014d893  mov     rax, [rbp+200h+var_260]
0x18014d897  mov     ebx, [rax]
0x18014d899  cmp     ebx, esi
0x18014d89b  jz      short loc_18014D8F7
0x18014d89d  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18014d8a4  jz      short loc_18014D8E9
0x18014d8a6  mov     [rsp+300h+var_2A8], r13; void *
0x18014d8ab  lea     rdi, aNull; "(NULL)"
0x18014d8b2  mov     [rsp+300h+var_2B0], r13d; unsigned int
0x18014d8b7  lea     r9, aAppcompatSkipp_0; "APPCOMPAT: skipping transform because i"...
0x18014d8be  mov     [rsp+300h+var_2B8], rdi; unsigned __int16 *
0x18014d8c3  mov     [rsp+300h+var_2C0], rdi; unsigned __int16 *
0x18014d8c8  mov     [rsp+300h+var_2C8], rdi; unsigned __int16 *
0x18014d8cd  mov     [rsp+300h+var_2D0], rdi; unsigned __int16 *
0x18014d8d2  mov     [rsp+300h+var_2D8], rdi; unsigned __int16 *
0x18014d8d7  mov     [rsp+300h+var_2E0], rdi; unsigned __int16 *
0x18014d8dc  xor     edx, edx; unsigned __int16
0x18014d8de  xor     r8d, r8d; int
0x18014d8e1  lea     ecx, [rdx+9]; int
0x18014d8e4  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18014d8e9  lea     rcx, [rbp+200h+var_260]
0x18014d8ed  call    ??1?$CTempBuffer@G$0BAA@@@QEAA@XZ; CTempBuffer<ushort,256>::~CTempBuffer<ushort,256>(void)
0x18014d8f2  jmp     loc_18014D769
0x18014d8f7  mov     ebx, 100h
0x18014d8fc  lea     rcx, [rbp+200h+var_140]; void *
0x18014d903  mov     r8d, ebx; Size
0x18014d906  xor     edx, edx; Val
0x18014d908  call    memset_0
0x18014d90d  lea     rax, [rbp+200h+var_140]
0x18014d914  mov     [rbp+200h+var_148], ebx
0x18014d91a  lea     r8, [rbp+200h+lpString1]
0x18014d921  mov     [rbp+200h+lpString1], rax
0x18014d928  mov     edx, r14d
0x18014d92b  mov     [rbp+200h+var_144], ebx
0x18014d931  mov     rcx, r12
0x18014d934  call    ?GetSdbDataNames@@YA_NPEAXKAEAV?$CTempBufferRef@E@@@Z; GetSdbDataNames(void *,ulong,CTempBufferRef<uchar> &)
0x18014d939  test    al, al
0x18014d93b  jz      loc_18014DE28
0x18014d941  mov     r14, [rbp+200h+lpString1]
0x18014d948  lea     rdi, aNull; "(NULL)"
0x18014d94f  mov     bl, r13b
0x18014d952  mov     esi, 9
0x18014d957  mov     byte ptr [rsp+300h+var_2A0+4], bl
0x18014d95b  xor     eax, eax
0x18014d95d  cmp     [r14], ax
0x18014d961  jz      loc_18014DDC6
0x18014d967  mov     edx, [rsp+300h+var_290]
0x18014d96b  lea     r9, [rsp+300h+var_2A0]
0x18014d970  mov     dword ptr [rsp+300h+var_298], eax
0x18014d974  mov     r8, r14
0x18014d977  lea     rax, [rsp+300h+var_298]
0x18014d97c  mov     [rbp+200h+var_254], 100h
0x18014d983  mov     [rsp+300h+var_2D8], rax
0x18014d988  mov     rcx, r12
0x18014d98b  lea     rax, [rbp+200h+var_260]
0x18014d98f  mov     [rsp+300h+var_2E0], rax
0x18014d994  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x18014d999  xor     ecx, ecx
0x18014d99b  test    eax, eax
0x18014d99d  jnz     loc_18014DD82
0x18014d9a3  mov     eax, dword ptr [rsp+300h+var_2A0]
0x18014d9a7  cmp     eax, r15d
0x18014d9aa  jnz     short loc_18014D9CE
0x18014d9ac  lea     rdx, aMinmsiversion; "MINMSIVERSION"
0x18014d9b3  mov     rcx, r14; lpString1
0x18014d9b6  call    cs:__imp_lstrcmpiW
0x18014d9bd  nop     dword ptr [rax+rax+00h]
0x18014d9c2  test    eax, eax
0x18014d9c4  jz      loc_18014DCE9
0x18014d9ca  mov     eax, dword ptr [rsp+300h+var_2A0]
0x18014d9ce  cmp     eax, 4
0x18014d9d1  jnz     loc_18014DA78
0x18014d9d7  lea     rdx, aApplypoint; "APPLYPOINT"
0x18014d9de  mov     rcx, r14; lpString1
0x18014d9e1  call    cs:__imp_lstrcmpiW
0x18014d9e8  nop     dword ptr [rax+rax+00h]
0x18014d9ed  xor     ecx, ecx
0x18014d9ef  test    eax, eax
0x18014d9f1  jz      loc_18014DCE9
0x18014d9f7  mov     eax, dword ptr [rsp+300h+var_2A0]
0x18014d9fb  cmp     eax, 4
0x18014d9fe  jnz     short loc_18014DA7A
0x18014da00  lea     rdx, aShimflags; "SHIMFLAGS"
0x18014da07  mov     rcx, r14; lpString1
0x18014da0a  call    cs:__imp_lstrcmpiW
0x18014da11  nop     dword ptr [rax+rax+00h]
0x18014da16  xor     ecx, ecx
0x18014da18  test    eax, eax
0x18014da1a  jz      loc_18014DCE9
0x18014da20  mov     eax, dword ptr [rsp+300h+var_2A0]
0x18014da24  cmp     eax, 4
0x18014da27  jnz     short loc_18014DA7A
0x18014da29  lea     rdx, aShimversionnt_1; "SHIMVERSIONNT"
0x18014da30  mov     rcx, r14; lpString1
0x18014da33  call    cs:__imp_lstrcmpiW
0x18014da3a  nop     dword ptr [rax+rax+00h]
0x18014da3f  xor     ecx, ecx
0x18014da41  test    eax, eax
0x18014da43  jz      loc_18014DCE9
0x18014da49  mov     eax, dword ptr [rsp+300h+var_2A0]
0x18014da4d  cmp     eax, 4
0x18014da50  jnz     short loc_18014DA7A
0x18014da52  lea     rdx, aShimservicepac_0; "SHIMSERVICEPACKLEVEL"
0x18014da59  mov     rcx, r14; lpString1
0x18014da5c  call    cs:__imp_lstrcmpiW
0x18014da63  nop     dword ptr [rax+rax+00h]
0x18014da68  xor     ecx, ecx
0x18014da6a  test    eax, eax
0x18014da6c  jz      loc_18014DCE9
0x18014da72  mov     eax, dword ptr [rsp+300h+var_2A0]
0x18014da76  jmp     short loc_18014DA7A
0x18014da78  xor     ecx, ecx
0x18014da7a  cmp     eax, r15d
0x18014da7d  ja      loc_18014DCA7
0x18014da83  mov     r8d, 0Ch; MaxCount
0x18014da89  lea     rdx, aMsiproperty; "MSIPROPERTY_"
0x18014da90  mov     rcx, r14; String1
0x18014da93  call    cs:__imp__wcsnicmp
0x18014da9a  nop     dword ptr [rax+rax+00h]
0x18014da9f  xor     ecx, ecx
0x18014daa1  test    eax, eax
0x18014daa3  jnz     loc_18014DB6D
0x18014daa9  mov     rcx, [rbp+200h+var_280]
0x18014daad  lea     r12, [r14+18h]
0x18014dab1  mov     rdx, r12
0x18014dab4  mov     rax, [rcx]
0x18014dab7  mov     rax, [rax+0B8h]
0x18014dabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dac3  mov     rbx, rax
0x18014dac6  xor     eax, eax
0x18014dac8  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18014dace  jz      short loc_18014DB0E
0x18014dad0  mov     [rsp+300h+var_2A8], rax; void *
0x18014dad5  lea     r9, aAppcompatTesti_0; "APPCOMPAT: testing Property value.  Pro"...
0x18014dadc  mov     [rsp+300h+var_2B0], eax; unsigned int
0x18014dae0  xor     edx, edx; unsigned __int16
0x18014dae2  mov     rax, [rbp+200h+var_260]
0x18014dae6  xor     r8d, r8d; int
0x18014dae9  mov     [rsp+300h+var_2B8], rdi; unsigned __int16 *
0x18014daee  mov     ecx, esi; int
0x18014daf0  mov     [rsp+300h+var_2C0], rdi; unsigned __int16 *
0x18014daf5  mov     [rsp+300h+var_2C8], rdi; unsigned __int16 *
0x18014dafa  mov     [rsp+300h+var_2D0], rdi; unsigned __int16 *
0x18014daff  mov     [rsp+300h+var_2D8], rax; unsigned __int16 *
0x18014db04  mov     [rsp+300h+var_2E0], r12; unsigned __int16 *
0x18014db09  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18014db0e  mov     rax, [rbx]
0x18014db11  xor     edx, edx
0x18014db13  mov     r8, [rbp+200h+var_260]
0x18014db17  mov     rcx, rbx
0x18014db1a  mov     rax, [rax+0C8h]
0x18014db21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014db26  test    eax, eax
0x18014db28  jz      loc_18014DD08
  ... truncated ...
```
