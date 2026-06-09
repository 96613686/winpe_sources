# CActiveXInstallBroker::UpdateDistributionUnit2(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,int *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)

- ea: `0x1400061e4`
- end: `0x140006a7a`
- name: `?UpdateDistributionUnit2@CActiveXInstallBroker@@QEAAJPEAGPEBG1KPEAK1H11J111KPEAPEBGPEAHK3K33@Z`
- size: `2198`
- prototype: `int(CActiveXInstallBroker *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 **, int *, unsigned int, const unsigned __int16 **, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400083b0`
- `0x1400084a0`

## callees

- `0x140006104`
- `0x1400061e4`
- `0x140006a80`
- `0x14000d314`
- `0x1400109c0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1400065fe`
- `ADVAPI32!RegDeleteValueW` at `0x14000668a`
- `ADVAPI32!RegDeleteValueW` at `0x1400065fe`
- `ADVAPI32!RegDeleteValueW` at `0x14000668a`
- `ADVAPI32!RegSetValueExW` at `0x1400063fd`
- `ADVAPI32!RegSetValueExW` at `0x140006438`
- `ADVAPI32!RegSetValueExW` at `0x140006475`
- `ADVAPI32!RegSetValueExW` at `0x1400064ae`
- `ADVAPI32!RegSetValueExW` at `0x140006550`
- `ADVAPI32!RegSetValueExW` at `0x1400066cb`
- `ADVAPI32!RegSetValueExW` at `0x140006717`
- `ADVAPI32!RegSetValueExW` at `0x140006816`
- `ADVAPI32!RegSetValueExW` at `0x14000685f`
- `ADVAPI32!RegSetValueExW` at `0x1400068b3`
- `ADVAPI32!RegSetValueExW` at `0x1400068fc`
- `ADVAPI32!RegSetValueExW` at `0x1400063fd`
- `ADVAPI32!RegSetValueExW` at `0x140006438`
- `ADVAPI32!RegSetValueExW` at `0x140006475`
- `ADVAPI32!RegSetValueExW` at `0x1400064ae`
- `ADVAPI32!RegSetValueExW` at `0x140006550`
- `ADVAPI32!RegSetValueExW` at `0x1400066cb`
- `ADVAPI32!RegSetValueExW` at `0x140006717`
- `ADVAPI32!RegSetValueExW` at `0x140006816`
- `ADVAPI32!RegSetValueExW` at `0x14000685f`
- `ADVAPI32!RegSetValueExW` at `0x1400068b3`
- `ADVAPI32!RegSetValueExW` at `0x1400068fc`
- `ADVAPI32!RegCloseKey` at `0x1400069c1`
- `ADVAPI32!RegCloseKey` at `0x1400069d7`
- `ADVAPI32!RegCloseKey` at `0x1400069ed`
- `ADVAPI32!RegCloseKey` at `0x140006a03`
- `ADVAPI32!RegCloseKey` at `0x140006a19`
- `ADVAPI32!RegCloseKey` at `0x1400069c1`
- `ADVAPI32!RegCloseKey` at `0x1400069d7`
- `ADVAPI32!RegCloseKey` at `0x1400069ed`
- `ADVAPI32!RegCloseKey` at `0x140006a03`
- `ADVAPI32!RegCloseKey` at `0x140006a19`
- `ADVAPI32!RegQueryValueExW` at `0x1400065b1`
- `ADVAPI32!RegQueryValueExW` at `0x140006641`
- `ADVAPI32!RegQueryValueExW` at `0x1400065b1`
- `ADVAPI32!RegQueryValueExW` at `0x140006641`
- `ADVAPI32!RegCreateKeyW` at `0x140006364`
- `ADVAPI32!RegCreateKeyW` at `0x1400063b2`
- `ADVAPI32!RegCreateKeyW` at `0x140006505`
- `ADVAPI32!RegCreateKeyW` at `0x14000676b`
- `ADVAPI32!RegCreateKeyW` at `0x1400067dc`
- `ADVAPI32!RegCreateKeyW` at `0x140006950`
- `ADVAPI32!RegCreateKeyW` at `0x140006364`
- `ADVAPI32!RegCreateKeyW` at `0x1400063b2`
- `ADVAPI32!RegCreateKeyW` at `0x140006505`
- `ADVAPI32!RegCreateKeyW` at `0x14000676b`
- `ADVAPI32!RegCreateKeyW` at `0x1400067dc`
- `ADVAPI32!RegCreateKeyW` at `0x140006950`
- `ADVAPI32!RegOpenKeyExW` at `0x140006343`
- `ADVAPI32!RegOpenKeyExW` at `0x140006393`
- `ADVAPI32!RegOpenKeyExW` at `0x1400064e4`
- `ADVAPI32!RegOpenKeyExW` at `0x14000674a`
- `ADVAPI32!RegOpenKeyExW` at `0x1400067bb`
- `ADVAPI32!RegOpenKeyExW` at `0x14000692f`
- `ADVAPI32!RegOpenKeyExW` at `0x140006343`
- `ADVAPI32!RegOpenKeyExW` at `0x140006393`
- `ADVAPI32!RegOpenKeyExW` at `0x1400064e4`
- `ADVAPI32!RegOpenKeyExW` at `0x14000674a`
- `ADVAPI32!RegOpenKeyExW` at `0x1400067bb`
- `ADVAPI32!RegOpenKeyExW` at `0x14000692f`
- `ADVAPI32!RegDeleteKeyW` at `0x14000678b`
- `ADVAPI32!RegDeleteKeyW` at `0x14000678b`
- `KERNEL32!lstrcmpiW` at `0x1400065cd`
- `KERNEL32!lstrcmpiW` at `0x14000665d`
- `KERNEL32!lstrcmpiW` at `0x1400065cd`
- `KERNEL32!lstrcmpiW` at `0x14000665d`
- `KERNEL32!LeaveCriticalSection` at `0x140006a41`
- `KERNEL32!LeaveCriticalSection` at `0x140006a41`
- `KERNEL32!EnterCriticalSection` at `0x1400062b5`
- `KERNEL32!EnterCriticalSection` at `0x1400062b5`
- `KERNEL32!DeleteFileW` at `0x1400065e1`
- `KERNEL32!DeleteFileW` at `0x140006671`
- `KERNEL32!DeleteFileW` at `0x1400065e1`
- `KERNEL32!DeleteFileW` at `0x140006671`

## string_xrefs

- `0x140006460`: `Installer`
- `0x140006743`: `InstalledVersion`
- `0x140006764`: `InstalledVersion`
- `0x140006802`: `Precache`
- `0x140006421`: `SystemComponent`
- `0x140006451`: `MSICD`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::UpdateDistributionUnit2(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        unsigned int Data,
        BYTE *lpData,
        BYTE *a7,
        int a8,
        LPCWSTR lpString1,
        LPCWSTR a10,
        int a11,
        BYTE *a12,
        BYTE *a13,
        BYTE *a14,
        unsigned int a15,
        unsigned __int16 **a16,
        int *a17,
        unsigned int a18,
        unsigned __int16 **a19)
{
  const BYTE *v21; // r14
  const BYTE *v23; // r15
  const WCHAR *v24; // r13
  const WCHAR *v25; // r12
  struct _RTL_CRITICAL_SECTION *v26; // rax
  signed int RegistrationRootKeyFromIntegrityLevel; // ebx
  __int64 v28; // rdx
  int v29; // eax
  int v30; // ecx
  LSTATUS updated; // eax
  __int64 v32; // rdi
  __int64 v33; // rax
  bool v34; // cc
  __int64 v35; // rax
  int v36; // esi
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  CActiveXInstallBroker *v41; // rcx
  CActiveXInstallBroker *v42; // rcx
  HKEY v44; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v45; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v46; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v47; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v49; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  CActiveXInstallBroker *v51; // [rsp+68h] [rbp-98h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-90h]
  BYTE *v53; // [rsp+78h] [rbp-88h]
  BYTE *v54; // [rsp+80h] [rbp-80h]
  BYTE *v55; // [rsp+88h] [rbp-78h]
  int *v56; // [rsp+90h] [rbp-70h]
  unsigned __int16 **v57; // [rsp+98h] [rbp-68h]
  unsigned __int16 **v58; // [rsp+A0h] [rbp-60h]
  WCHAR v59[259]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v60; // [rsp+2B6h] [rbp+1B6h]

  v21 = lpData;
  v23 = a7;
  v24 = lpString1;
  v25 = a10;
  v53 = a12;
  v54 = a13;
  v57 = a16;
  v56 = a17;
  v55 = a14;
  v58 = a19;
  v26 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 8);
  v51 = this;
  hKey = 0;
  phkResult = 0;
  v44 = 0;
  v45 = 0;
  v49 = 0;
  v46 = 0;
  if ( !*(_DWORD *)this )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147024882;
    LODWORD(v21) = 0;
    goto LABEL_88;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)v51 + 12) < 7 )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147019873;
LABEL_75:
    LODWORD(v21) = 0;
    goto LABEL_76;
  }
  if ( !a2 || !a3 )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147024809;
    goto LABEL_75;
  }
  v28 = *((_QWORD *)v51 + 8) - (_QWORD)a2;
  do
  {
    v29 = *(unsigned __int16 *)((char *)a2 + v28);
    v30 = *a2 - v29;
    if ( v30 )
      break;
    ++a2;
  }
  while ( v29 );
  if ( v30 )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147024891;
    goto LABEL_75;
  }
  RegistrationRootKeyFromIntegrityLevel = GetRegistrationRootKeyFromIntegrityLevel(&hKey);
  if ( RegistrationRootKeyFromIntegrityLevel )
    goto LABEL_75;
  if ( RegOpenKeyExW(hKey, L"Software\\Microsoft\\Code Store Database\\Distribution Units", 0, 0x2001Fu, &phkResult) )
  {
    updated = RegCreateKeyW(hKey, L"Software\\Microsoft\\Code Store Database\\Distribution Units", &phkResult);
    if ( updated )
      goto LABEL_71;
  }
  if ( RegOpenKeyExW(phkResult, a3, 0, 0x2001Fu, &v44) )
  {
    updated = RegCreateKeyW(phkResult, a3, &v44);
    if ( updated )
      goto LABEL_71;
  }
  v32 = -1;
  if ( a4 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *(_WORD *)&a4[2 * v33] );
    updated = RegSetValueExW(v44, 0, 0, 1u, a4, 2 * v33 + 2);
    if ( updated )
      goto LABEL_71;
  }
  updated = RegSetValueExW(v44, L"SystemComponent", 0, 4u, (const BYTE *)&Data, 4u);
  if ( updated || (updated = RegSetValueExW(v44, L"Installer", 0, 1u, L"MSICD", 0xCu)) != 0 )
  {
LABEL_71:
    LODWORD(v21) = 0;
    v34 = updated <= 0;
    goto LABEL_72;
  }
  if ( v21 )
  {
    updated = RegSetValueExW(v44, L"Expire", 0, 4u, v21, 4u);
    LODWORD(v21) = 0;
    v34 = updated <= 0;
    if ( updated )
      goto LABEL_72;
  }
  if ( RegOpenKeyExW(v44, L"DownloadInformation", 0, 0x2001Fu, &v45) )
  {
    updated = RegCreateKeyW(v44, L"DownloadInformation", &v45);
    v34 = updated <= 0;
    if ( updated )
      goto LABEL_72;
  }
  if ( v23 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *(_WORD *)&v23[2 * v35] != (_WORD)v21 );
    updated = RegSetValueExW(v45, L"CODEBASE", 0, 1u, v23, 2 * v35 + 2);
    v34 = updated <= 0;
    if ( updated )
    {
LABEL_72:
      if ( !v34 )
      {
        RegistrationRootKeyFromIntegrityLevel = (unsigned __int16)updated | 0x80070000;
        goto LABEL_76;
      }
      goto LABEL_70;
    }
  }
  v36 = a8;
  if ( !a8 )
  {
    LODWORD(hKey) = (_DWORD)v21;
    v47 = 259;
    v60 = (__int16)v21;
    if ( !RegQueryValueExW(v45, L"INF", 0, (LPDWORD)&hKey, (LPBYTE)v59, &v47) && (!v24 || lstrcmpiW(v24, v59)) )
    {
      DeleteFileW(v59);
      if ( !v24 )
        RegDeleteValueW(v45, L"INF");
    }
    v47 = 259;
    v60 = (__int16)v21;
    if ( RegQueryValueExW(v45, L"OSD", 0, (LPDWORD)&hKey, (LPBYTE)v59, &v47) )
    {
      if ( !v25 )
        goto LABEL_45;
    }
    else if ( !v25 || lstrcmpiW(v25, v59) )
    {
      DeleteFileW(v59);
      if ( !v25 )
      {
        RegDeleteValueW(v45, L"OSD");
LABEL_45:
        if ( v24 )
        {
          v38 = -1;
          do
            ++v38;
          while ( v24[v38] != (_WORD)v21 );
          updated = RegSetValueExW(v45, L"INF", 0, 1u, (const BYTE *)v24, 2 * v38 + 2);
          v34 = updated <= 0;
          if ( updated )
            goto LABEL_72;
        }
        if ( RegOpenKeyExW(v44, L"InstalledVersion", 0, 0x2001Fu, &v46) )
        {
          updated = RegCreateKeyW(v44, L"InstalledVersion", &v46);
          v34 = updated <= 0;
          if ( updated )
            goto LABEL_72;
        }
        RegDeleteKeyW(v44, L"AvailableVersion");
        goto LABEL_55;
      }
    }
    v37 = -1;
    do
      ++v37;
    while ( v25[v37] != (_WORD)v21 );
    updated = RegSetValueExW(v45, L"OSD", 0, 1u, (const BYTE *)v25, 2 * v37 + 2);
    v34 = updated <= 0;
    if ( updated )
      goto LABEL_72;
    goto LABEL_45;
  }
  if ( RegOpenKeyExW(v44, L"AvailableVersion", 0, 0x2001Fu, &v46) )
  {
    updated = RegCreateKeyW(v44, L"AvailableVersion", &v46);
    v34 = updated <= 0;
    if ( updated )
      goto LABEL_72;
  }
  updated = RegSetValueExW(v46, L"Precache", 0, 4u, (const BYTE *)&a11, 4u);
  v34 = updated <= 0;
  if ( updated )
    goto LABEL_72;
LABEL_55:
  v39 = -1;
  do
    ++v39;
  while ( *(_WORD *)&v53[2 * v39] != (_WORD)v21 );
  updated = RegSetValueExW(v46, 0, 0, 1u, v53, 2 * v39 + 2);
  v34 = updated <= 0;
  if ( updated )
    goto LABEL_72;
  if ( v36 )
    goto LABEL_76;
  if ( v54 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *(_WORD *)&v54[2 * v40] != (_WORD)v21 );
    updated = RegSetValueExW(v46, L"LastModified", 0, 1u, v54, 2 * v40 + 2);
    v34 = updated <= 0;
    if ( updated )
      goto LABEL_72;
  }
  if ( v55 )
  {
    do
      ++v32;
    while ( *(_WORD *)&v55[2 * v32] != (_WORD)v21 );
    updated = RegSetValueExW(v46, L"Etag", 0, 1u, v55, 2 * v32 + 2);
    v34 = updated <= 0;
    if ( updated )
      goto LABEL_72;
  }
  if ( RegOpenKeyExW(v44, L"Contains", 0, 0x2001Fu, &v49) )
  {
    updated = RegCreateKeyW(v44, L"Contains", &v49);
    v34 = updated <= 0;
    if ( updated )
      goto LABEL_72;
  }
  RegistrationRootKeyFromIntegrityLevel = CActiveXInstallBroker::UpdateFileList(
                                            v41,
                                            v49,
                                            a15,
                                            (const unsigned __int16 **)v57,
                                            v56);
  if ( RegistrationRootKeyFromIntegrityLevel >= 0 )
  {
    updated = CActiveXInstallBroker::UpdateDependencyList(v42, v49, a18, (const unsigned __int16 **)v58);
LABEL_70:
    RegistrationRootKeyFromIntegrityLevel = updated;
  }
LABEL_76:
  if ( v49 )
    RegCloseKey(v49);
  if ( v45 )
    RegCloseKey(v45);
  if ( v46 )
    RegCloseKey(v46);
  if ( v44 )
    RegCloseKey(v44);
  if ( phkResult )
    RegCloseKey(phkResult);
  v26 = lpCriticalSection;
  this = v51;
LABEL_88:
  if ( *(_DWORD *)this != (_DWORD)v21 )
    LeaveCriticalSection(v26);
  return (unsigned int)RegistrationRootKeyFromIntegrityLevel;
}

```

## disassembly

```asm
0x1400061e4  mov     [rsp-8+arg_8], rbx
0x1400061e9  push    rbp
0x1400061ea  push    rsi
0x1400061eb  push    rdi
0x1400061ec  push    r12
0x1400061ee  push    r13
0x1400061f0  push    r14
0x1400061f2  push    r15
0x1400061f4  lea     rbp, [rsp-1D0h]
0x1400061fc  sub     rsp, 2D0h
0x140006203  mov     rax, cs:__security_cookie
0x14000620a  xor     rax, rsp
0x14000620d  mov     [rbp+200h+var_40], rax
0x140006214  mov     rax, [rbp+200h+arg_58]
0x14000621b  mov     rbx, rdx
0x14000621e  mov     rdx, [rbp+200h+arg_68]
0x140006225  mov     rsi, r9
0x140006228  mov     r14, [rbp+200h+lpData]
0x14000622f  mov     rdi, r8
0x140006232  mov     r15, [rbp+200h+arg_30]
0x140006239  mov     r13, [rbp+200h+lpString1]
0x140006240  mov     r12, [rbp+200h+arg_48]
0x140006247  mov     [rsp+300h+var_288], rax
0x14000624c  mov     rax, [rbp+200h+arg_60]
0x140006253  mov     [rbp+200h+var_280], rax
0x140006257  mov     rax, [rbp+200h+arg_78]
0x14000625e  mov     [rbp+200h+var_268], rax
0x140006262  mov     rax, [rbp+200h+arg_80]
0x140006269  mov     [rbp+200h+var_270], rax
0x14000626d  mov     rax, [rbp+200h+arg_90]
0x140006274  mov     [rbp+200h+var_278], rdx
0x140006278  xor     edx, edx
0x14000627a  mov     [rbp+200h+var_260], rax
0x14000627e  lea     rax, [rcx+8]
0x140006282  mov     [rsp+300h+lpCriticalSection], rax
0x140006287  mov     [rsp+300h+var_298], rcx
0x14000628c  mov     [rsp+300h+hKey], rdx
0x140006291  mov     [rsp+300h+var_2A0], rdx
0x140006296  mov     [rsp+300h+var_2D0], rdx
0x14000629b  mov     [rsp+300h+var_2C8], rdx
0x1400062a0  mov     [rsp+300h+var_2A8], rdx
0x1400062a5  mov     [rsp+300h+var_2C0], rdx
0x1400062aa  cmp     [rcx], edx
0x1400062ac  jz      loc_140006A31
0x1400062b2  mov     rcx, rax; lpCriticalSection
0x1400062b5  call    cs:__imp_EnterCriticalSection
0x1400062bc  nop     dword ptr [rax+rax+00h]
0x1400062c1  mov     rdx, [rsp+300h+var_298]
0x1400062c6  cmp     dword ptr [rdx+30h], 7
0x1400062ca  jge     short loc_1400062D6
0x1400062cc  mov     ebx, 8007139Fh
0x1400062d1  jmp     loc_1400069B4
0x1400062d6  test    rbx, rbx
0x1400062d9  jz      loc_1400069AF
0x1400062df  test    rdi, rdi
0x1400062e2  jz      loc_1400069AF
0x1400062e8  mov     rdx, [rdx+40h]
0x1400062ec  sub     rdx, rbx
0x1400062ef  movzx   ecx, word ptr [rbx]
0x1400062f2  movzx   eax, word ptr [rbx+rdx]
0x1400062f6  sub     ecx, eax
0x1400062f8  jnz     short loc_140006302
0x1400062fa  add     rbx, 2
0x1400062fe  test    eax, eax
0x140006300  jnz     short loc_1400062EF
0x140006302  test    ecx, ecx
0x140006304  jz      short loc_140006310
0x140006306  mov     ebx, 80070005h
0x14000630b  jmp     loc_1400069B4
0x140006310  lea     rcx, [rsp+300h+hKey]; HKEY *
0x140006315  call    ?GetRegistrationRootKeyFromIntegrityLevel@@YAJPEAPEAUHKEY__@@@Z; GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)
0x14000631a  mov     ebx, eax
0x14000631c  test    eax, eax
0x14000631e  jnz     loc_1400069B4
0x140006324  mov     rcx, [rsp+300h+hKey]; hKey
0x140006329  lea     rax, [rsp+300h+var_2A0]
0x14000632e  mov     r9d, 2001Fh; samDesired
0x140006334  mov     [rsp+300h+phkResult], rax; phkResult
0x140006339  xor     r8d, r8d; ulOptions
0x14000633c  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Code Store Databas"...
0x140006343  call    cs:__imp_RegOpenKeyExW
0x14000634a  nop     dword ptr [rax+rax+00h]
0x14000634f  test    eax, eax
0x140006351  jz      short loc_140006378
0x140006353  mov     rcx, [rsp+300h+hKey]; hKey
0x140006358  lea     r8, [rsp+300h+var_2A0]; phkResult
0x14000635d  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Code Store Databas"...
0x140006364  call    cs:__imp_RegCreateKeyW
0x14000636b  nop     dword ptr [rax+rax+00h]
0x140006370  test    eax, eax
0x140006372  jnz     loc_14000699D
0x140006378  mov     rcx, [rsp+300h+var_2A0]; hKey
0x14000637d  lea     rax, [rsp+300h+var_2D0]
0x140006382  mov     r9d, 2001Fh; samDesired
0x140006388  mov     [rsp+300h+phkResult], rax; phkResult
0x14000638d  xor     r8d, r8d; ulOptions
0x140006390  mov     rdx, rdi; lpSubKey
0x140006393  call    cs:__imp_RegOpenKeyExW
0x14000639a  nop     dword ptr [rax+rax+00h]
0x14000639f  xor     ecx, ecx
0x1400063a1  test    eax, eax
0x1400063a3  jz      short loc_1400063C8
0x1400063a5  mov     rcx, [rsp+300h+var_2A0]; hKey
0x1400063aa  lea     r8, [rsp+300h+var_2D0]; phkResult
0x1400063af  mov     rdx, rdi; lpSubKey
0x1400063b2  call    cs:__imp_RegCreateKeyW
0x1400063b9  nop     dword ptr [rax+rax+00h]
0x1400063be  xor     ecx, ecx
0x1400063c0  test    eax, eax
0x1400063c2  jnz     loc_14000699D
0x1400063c8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400063cc  test    rsi, rsi
0x1400063cf  jz      short loc_140006411
0x1400063d1  mov     rax, rdi
0x1400063d4  inc     rax
0x1400063d7  cmp     [rsi+rax*2], cx
0x1400063db  jnz     short loc_1400063D4
0x1400063dd  mov     rcx, [rsp+300h+var_2D0]; hKey
0x1400063e2  lea     eax, ds:2[rax*2]
0x1400063e9  mov     [rsp+300h+cbData], eax; cbData
0x1400063ed  mov     r9d, 1; dwType
0x1400063f3  xor     r8d, r8d; Reserved
0x1400063f6  mov     [rsp+300h+phkResult], rsi; lpData
0x1400063fb  xor     edx, edx; lpValueName
0x1400063fd  call    cs:__imp_RegSetValueExW
0x140006404  nop     dword ptr [rax+rax+00h]
0x140006409  test    eax, eax
0x14000640b  jnz     loc_14000699D
0x140006411  mov     ecx, 4
0x140006416  lea     rax, [rbp+200h+Data]
0x14000641d  mov     [rsp+300h+cbData], ecx; cbData
0x140006421  lea     rdx, aSystemcomponen; "SystemComponent"
0x140006428  mov     r9d, ecx; dwType
0x14000642b  mov     [rsp+300h+phkResult], rax; lpData
0x140006430  mov     rcx, [rsp+300h+var_2D0]; hKey
0x140006435  xor     r8d, r8d; Reserved
0x140006438  call    cs:__imp_RegSetValueExW
0x14000643f  nop     dword ptr [rax+rax+00h]
0x140006444  test    eax, eax
0x140006446  jnz     loc_14000699D
0x14000644c  mov     rcx, [rsp+300h+var_2D0]; hKey
0x140006451  lea     rax, aMsicd; "MSICD"
0x140006458  mov     [rsp+300h+cbData], 0Ch; cbData
0x140006460  lea     rdx, aInstaller; "Installer"
0x140006467  mov     r9d, 1; dwType
0x14000646d  mov     [rsp+300h+phkResult], rax; lpData
0x140006472  xor     r8d, r8d; Reserved
0x140006475  call    cs:__imp_RegSetValueExW
0x14000647c  nop     dword ptr [rax+rax+00h]
0x140006481  test    eax, eax
0x140006483  jnz     loc_14000699D
0x140006489  test    r14, r14
0x14000648c  jz      short loc_1400064C5
0x14000648e  mov     rcx, [rsp+300h+var_2D0]; hKey
0x140006493  lea     rdx, aExpire; "Expire"
0x14000649a  mov     eax, 4
0x14000649f  xor     r8d, r8d; Reserved
0x1400064a2  mov     [rsp+300h+cbData], eax; cbData
0x1400064a6  mov     r9d, eax; dwType
0x1400064a9  mov     [rsp+300h+phkResult], r14; lpData
0x1400064ae  call    cs:__imp_RegSetValueExW
0x1400064b5  nop     dword ptr [rax+rax+00h]
0x1400064ba  xor     r14d, r14d
0x1400064bd  test    eax, eax
0x1400064bf  jnz     loc_1400069A2
0x1400064c5  mov     rcx, [rsp+300h+var_2D0]; hKey
0x1400064ca  lea     rax, [rsp+300h+var_2C8]
0x1400064cf  mov     r9d, 2001Fh; samDesired
0x1400064d5  mov     [rsp+300h+phkResult], rax; phkResult
0x1400064da  xor     r8d, r8d; ulOptions
0x1400064dd  lea     rdx, aDownloadinform; "DownloadInformation"
0x1400064e4  call    cs:__imp_RegOpenKeyExW
0x1400064eb  nop     dword ptr [rax+rax+00h]
0x1400064f0  test    eax, eax
0x1400064f2  jz      short loc_140006519
0x1400064f4  mov     rcx, [rsp+300h+var_2D0]; hKey
0x1400064f9  lea     r8, [rsp+300h+var_2C8]; phkResult
0x1400064fe  lea     rdx, aDownloadinform; "DownloadInformation"
0x140006505  call    cs:__imp_RegCreateKeyW
0x14000650c  nop     dword ptr [rax+rax+00h]
0x140006511  test    eax, eax
0x140006513  jnz     loc_1400069A2
0x140006519  test    r15, r15
0x14000651c  jz      short loc_140006564
0x14000651e  mov     rax, rdi
0x140006521  inc     rax
0x140006524  cmp     [r15+rax*2], r14w
0x140006529  jnz     short loc_140006521
0x14000652b  mov     rcx, [rsp+300h+var_2C8]; hKey
0x140006530  lea     eax, ds:2[rax*2]
0x140006537  mov     [rsp+300h+cbData], eax; cbData
0x14000653b  lea     rdx, aCodebase; "CODEBASE"
0x140006542  mov     r9d, 1; dwType
0x140006548  mov     [rsp+300h+phkResult], r15; lpData
0x14000654d  xor     r8d, r8d; Reserved
0x140006550  call    cs:__imp_RegSetValueExW
0x140006557  nop     dword ptr [rax+rax+00h]
0x14000655c  test    eax, eax
0x14000655e  jnz     loc_1400069A2
0x140006564  mov     esi, [rbp+200h+arg_38]
0x14000656a  test    esi, esi
0x14000656c  jnz     loc_14000679C
0x140006572  mov     rcx, [rsp+300h+var_2C8]; hKey
0x140006577  lea     rax, [rsp+300h+var_2B8]
0x14000657c  mov     qword ptr [rsp+300h+cbData], rax; lpcbData
0x140006581  lea     r9, [rsp+300h+hKey]; lpType
0x140006586  lea     rax, [rbp+200h+var_250]
0x14000658a  mov     dword ptr [rsp+300h+hKey], r14d
0x14000658f  mov     r15d, 103h
0x140006595  mov     [rsp+300h+phkResult], rax; lpData
0x14000659a  xor     r8d, r8d; lpReserved
0x14000659d  mov     [rsp+300h+var_2B8], r15d
0x1400065a2  lea     rdx, aInf; "INF"
0x1400065a9  mov     [rbp+200h+var_4A], r14w
0x1400065b1  call    cs:__imp_RegQueryValueExW
0x1400065b8  nop     dword ptr [rax+rax+00h]
0x1400065bd  test    eax, eax
0x1400065bf  jnz     short loc_14000660A
0x1400065c1  test    r13, r13
0x1400065c4  jz      short loc_1400065DD
0x1400065c6  lea     rdx, [rbp+200h+var_250]; lpString2
0x1400065ca  mov     rcx, r13; lpString1
0x1400065cd  call    cs:__imp_lstrcmpiW
0x1400065d4  nop     dword ptr [rax+rax+00h]
0x1400065d9  test    eax, eax
0x1400065db  jz      short loc_14000660A
0x1400065dd  lea     rcx, [rbp+200h+var_250]; lpFileName
0x1400065e1  call    cs:__imp_DeleteFileW
0x1400065e8  nop     dword ptr [rax+rax+00h]
0x1400065ed  test    r13, r13
0x1400065f0  jnz     short loc_14000660A
0x1400065f2  mov     rcx, [rsp+300h+var_2C8]; hKey
0x1400065f7  lea     rdx, aInf; "INF"
0x1400065fe  call    cs:__imp_RegDeleteValueW
0x140006605  nop     dword ptr [rax+rax+00h]
0x14000660a  mov     rcx, [rsp+300h+var_2C8]; hKey
0x14000660f  lea     rax, [rsp+300h+var_2B8]
0x140006614  mov     qword ptr [rsp+300h+cbData], rax; lpcbData
0x140006619  lea     r9, [rsp+300h+hKey]; lpType
0x14000661e  mov     [rsp+300h+var_2B8], r15d
0x140006623  lea     rax, [rbp+200h+var_250]
0x140006627  lea     r15, aOsd; "OSD"
0x14000662e  mov     [rsp+300h+phkResult], rax; lpData
0x140006633  xor     r8d, r8d; lpReserved
0x140006636  mov     [rbp+200h+var_4A], r14w
0x14000663e  mov     rdx, r15; lpValueName
0x140006641  call    cs:__imp_RegQueryValueExW
0x140006648  nop     dword ptr [rax+rax+00h]
0x14000664d  test    eax, eax
0x14000664f  jnz     short loc_140006698
0x140006651  test    r12, r12
0x140006654  jz      short loc_14000666D
0x140006656  lea     rdx, [rbp+200h+var_250]; lpString2
0x14000665a  mov     rcx, r12; lpString1
0x14000665d  call    cs:__imp_lstrcmpiW
0x140006664  nop     dword ptr [rax+rax+00h]
0x140006669  test    eax, eax
0x14000666b  jz      short loc_14000669D
0x14000666d  lea     rcx, [rbp+200h+var_250]; lpFileName
0x140006671  call    cs:__imp_DeleteFileW
0x140006678  nop     dword ptr [rax+rax+00h]
0x14000667d  test    r12, r12
0x140006680  jnz     short loc_14000669D
0x140006682  mov     rcx, [rsp+300h+var_2C8]; hKey
0x140006687  mov     rdx, r15; lpValueName
0x14000668a  call    cs:__imp_RegDeleteValueW
0x140006691  nop     dword ptr [rax+rax+00h]
0x140006696  jmp     short loc_1400066DF
0x140006698  test    r12, r12
0x14000669b  jz      short loc_1400066DF
0x14000669d  mov     rax, rdi
0x1400066a0  inc     rax
0x1400066a3  cmp     [r12+rax*2], r14w
0x1400066a8  jnz     short loc_1400066A0
0x1400066aa  mov     rcx, [rsp+300h+var_2C8]; hKey
0x1400066af  lea     eax, ds:2[rax*2]
0x1400066b6  mov     [rsp+300h+cbData], eax; cbData
0x1400066ba  mov     r9d, 1; dwType
0x1400066c0  xor     r8d, r8d; Reserved
0x1400066c3  mov     [rsp+300h+phkResult], r12; lpData
0x1400066c8  mov     rdx, r15; lpValueName
0x1400066cb  call    cs:__imp_RegSetValueExW
0x1400066d2  nop     dword ptr [rax+rax+00h]
0x1400066d7  test    eax, eax
0x1400066d9  jnz     loc_1400069A2
0x1400066df  test    r13, r13
0x1400066e2  jz      short loc_14000672B
0x1400066e4  mov     rax, rdi
0x1400066e7  inc     rax
0x1400066ea  cmp     [r13+rax*2+0], r14w
0x1400066f0  jnz     short loc_1400066E7
0x1400066f2  mov     rcx, [rsp+300h+var_2C8]; hKey
0x1400066f7  lea     eax, ds:2[rax*2]
0x1400066fe  mov     [rsp+300h+cbData], eax; cbData
0x140006702  lea     rdx, aInf; "INF"
0x140006709  mov     r9d, 1; dwType
0x14000670f  mov     [rsp+300h+phkResult], r13; lpData
0x140006714  xor     r8d, r8d; Reserved
0x140006717  call    cs:__imp_RegSetValueExW
0x14000671e  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
