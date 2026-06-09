# ReadVdiSettingsFromRegistry(_VDI_SETTINGS &,int)

- ea: `0x18005f7fc`
- end: `0x18005ff8d`
- name: `?ReadVdiSettingsFromRegistry@@YAJAEAU_VDI_SETTINGS@@H@Z`
- size: `1937`
- prototype: `__int64 __fastcall(unsigned __int16 **, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058074`
- `0x1800a4b04`

## callees

- `0x18000468c`
- `0x1800048cc`
- `0x1800059d0`
- `0x180005ba0`
- `0x180006450`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x1800097c0`
- `0x18000bac0`
- `0x18000ddf0`
- `0x180011fc0`
- `0x180032418`
- `0x18003334c`
- `0x1800371e0`
- `0x18003d7d8`
- `0x18004654c`
- `0x18005f6ec`
- `0x18005f794`
- `0x18005f7c8`
- `0x18005f7fc`
- `0x18005ff94`
- `0x18008c04c`
- `0x18008cc34`
- `0x18008cf9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005fba3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005fba3`

## string_xrefs

- `0x18005f885`: `RegistryPath::InitializePersistedStatePath`
- `0x18005fe97`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18005f8c5`: `RegistryPath::ReadStringValue`
- `0x18005f9a8`: `RegistryPath::ReadDwordValue`
- `0x18005fa48`: `RegistryPath::ReadDwordValue`
- `0x18005fd4c`: `CopyStringW`
- `0x18005fd5f`: `CopyStringW`
- `0x18005ff2f`: `EventWriteGetVirtualDesktopAttributeFailureEvent`
- `0x18005ff36`: `Logger::WriteGetVirtualDesktopAttributeFailureEvent`
- `0x18005f95d`: `CopyStringNullSafeW`
- `0x18005f88c`: `ReadVdiSettingsFromRegistry`
- `0x18005f8cc`: `ReadVdiSettingsFromRegistry`
- `0x18005f8fa`: `ReadVdiSettingsFromRegistry`
- `0x18005f856`: `SOFTWARE\AzureAD\VirtualDesktop`
- `0x18005f925`: `%s: VDI provider from registry is longer than %lu characters. Truncating...`
- `0x18005f940`: `%s: VDI provider from registry: %s`
- `0x18005f9ee`: `%s: Virtual desktop type (%lu) is invalid. Registry path: %s@%s.`
- `0x18005fa1e`: `%s: VDI type from registry: %lu (%s).`
- `0x18005fa8a`: `%s: Virtual desktop user mode (%lu) is invalid. Registry path: %s@%s.`
- `0x18005fab4`: `%s: VDI user mode from registry: %lu (%s).`
- `0x18005fe90`: `RegistryPath::ReadMultiStringValue`
- `0x18005feac`: `RegistryPath::ReadMultiStringValue`
- `0x18005fd7b`: `%s: Maximum number (%d) of extension attributes reached. Skipping remaining extensions...`
- `0x18005fb7b`: `%s: This extension begin with "%s" contains more than %lu characters. Skipping it...`
- `0x18005fb8f`: `%s: Parsing extension attribute "%s".`
- `0x18005fbd6`: `%s: The value of this extension attribute "%s" is empty. Skipping it...`
- `0x18005fc04`: `%s: The key of this extension attribute is empty. Skipping it...`
- `0x18005fc52`: `%s: Duplicate key "%s" in this extension attribute. Skipping it...`
- `0x18005fd22`: `%s: VDI extension read from registry. Key: "%s". Value: "%s".`
- `0x18005fe6b`: `%s: Missing %lu VDI setting(s). VDI registry settings are invalid.`
- `0x18005ff03`: `HKEY_LOCAL_MACHINE\SOFTWARE\AzureAD\VirtualDesktop`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadVdiSettingsFromRegistry(unsigned __int16 **a1, int a2)
{
  wchar_t *v3; // r13
  int v4; // esi
  int v5; // eax
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // r12
  int v8; // r15d
  unsigned int v9; // eax
  const wchar_t *v10; // rax
  size_t v11; // rdx
  const wchar_t *v12; // rbx
  const wchar_t *v13; // r8
  int v14; // eax
  unsigned int DwordValue; // eax
  unsigned int v16; // esi
  const unsigned __int16 *VdiTypeName; // rax
  unsigned int v18; // eax
  const wchar_t *v19; // r8
  unsigned int v20; // esi
  const unsigned __int16 *VdiUserMode; // rax
  unsigned int v22; // esi
  const unsigned __int16 *v23; // r8
  HKEY v24; // rcx
  const WCHAR *v25; // rdx
  wchar_t *v26; // rcx
  unsigned __int64 v27; // rax
  wchar_t *v28; // rsi
  wchar_t *v29; // rax
  const unsigned __int16 *v30; // r10
  unsigned int i; // r8d
  const unsigned __int16 *v32; // rdx
  int v33; // eax
  int v34; // ecx
  unsigned __int16 *v35; // rcx
  __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  int v38; // eax
  unsigned __int64 v39; // rdx
  unsigned __int16 *v40; // rsi
  const unsigned __int16 *v41; // rcx
  const wchar_t *v42; // r9
  int v43; // eax
  __int64 v44; // rcx
  unsigned int v45; // eax
  int v47; // [rsp+30h] [rbp-69h]
  wchar_t *Str; // [rsp+38h] [rbp-61h] BYREF
  int v49; // [rsp+40h] [rbp-59h]
  unsigned __int16 *Source; // [rsp+48h] [rbp-51h] BYREF
  const unsigned __int16 *v51; // [rsp+50h] [rbp-49h]
  unsigned __int16 *v52[2]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v53; // [rsp+68h] [rbp-31h]
  unsigned __int16 *v54[4]; // [rsp+70h] [rbp-29h] BYREF
  __int128 v55; // [rsp+90h] [rbp-9h]
  __int64 v56; // [rsp+A0h] [rbp+7h]
  __int64 v57; // [rsp+A8h] [rbp+Fh]

  v49 = a2;
  v3 = 0;
  Str = 0;
  LODWORD(Source) = 0;
  v4 = 0;
  v47 = 0;
  memset(v54, 0, sizeof(v54));
  v55 = 0;
  v56 = 0;
  v57 = 0;
  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  v5 = RegistryPath::InitializePersistedStatePath(
         (RegistryPath *)v54,
         L"AadVdiParameters",
         L"SOFTWARE\\AzureAD\\VirtualDesktop",
         0);
  v6 = v5;
  v7 = v54[0];
  if ( v5 < 0 )
  {
    v8 = 0;
    Logger::TraceError(
      L"%s: %s(%s) failed with error code: 0x%08x.",
      L"ReadVdiSettingsFromRegistry",
      L"RegistryPath::InitializePersistedStatePath",
      L"AadVdiParameters",
      v5);
    goto LABEL_88;
  }
  v9 = RegistryPath::ReadStringValue((RegistryPath *)v54, L"Provider", &Str);
  v8 = v9;
  if ( v9 )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"ReadVdiSettingsFromRegistry",
      L"RegistryPath::ReadStringValue",
      v9);
    v3 = Str;
    goto LABEL_88;
  }
  v3 = Str;
  v10 = StringTrimSpace(Str);
  v12 = v10;
  if ( v10 )
  {
    if ( wcsnlen_s(v10, v11) == 512 )
    {
      *((_WORD *)v12 + 512) = 0;
      Logger::TraceWarning(
        (wchar_t *)L"%s: VDI provider from registry is longer than %lu characters. Truncating...",
        L"ReadVdiSettingsFromRegistry");
    }
    v13 = v12;
  }
  else
  {
    v13 = L"<NULL>";
  }
  Logger::TraceVerbose((wchar_t *)L"%s: VDI provider from registry: %s", L"ReadVdiSettingsFromRegistry", v13);
  v14 = CopyStringNullSafeW(v12, a1);
  v6 = v14;
  if ( v14 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"ReadVdiSettingsFromRegistry",
      L"CopyStringNullSafeW",
      (unsigned int)v14);
    goto LABEL_88;
  }
  SafeFree(v3);
  v3 = 0;
  Str = 0;
  DwordValue = RegistryPath::ReadDwordValue((RegistryPath *)v54, L"Type", (unsigned int *)&Source, 0);
  v8 = DwordValue;
  if ( DwordValue )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"ReadVdiSettingsFromRegistry",
      L"RegistryPath::ReadDwordValue",
      DwordValue);
    goto LABEL_88;
  }
  v16 = (unsigned int)Source;
  if ( (unsigned int)Source >= 3 )
  {
    v47 = 1;
    Logger::WriteInvalidVirtualDesktopAttributeEvent(v7, L"Type", (unsigned int)Source);
    Logger::TraceError(
      L"%s: Virtual desktop type (%lu) is invalid. Registry path: %s@%s.",
      L"ReadVdiSettingsFromRegistry",
      v16,
      v7,
      L"Type");
    if ( v49 )
      goto LABEL_16;
  }
  *((_DWORD *)a1 + 2) = v16;
  VdiTypeName = GetVdiTypeName(v16);
  Logger::TraceVerbose(
    (wchar_t *)L"%s: VDI type from registry: %lu (%s).",
    L"ReadVdiSettingsFromRegistry",
    v16,
    VdiTypeName);
  v18 = RegistryPath::ReadDwordValue((RegistryPath *)v54, L"User", (unsigned int *)&Source, 0);
  v8 = v18;
  if ( v18 )
  {
    v19 = L"RegistryPath::ReadDwordValue";
LABEL_86:
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"ReadVdiSettingsFromRegistry", v19, v18);
    goto LABEL_87;
  }
  v20 = (unsigned int)Source;
  if ( (unsigned int)Source < 3
    || (v47 = 1,
        Logger::WriteInvalidVirtualDesktopAttributeEvent(v7, L"User", (unsigned int)Source),
        Logger::TraceError(
          L"%s: Virtual desktop user mode (%lu) is invalid. Registry path: %s@%s.",
          L"ReadVdiSettingsFromRegistry",
          v20,
          v7,
          L"User"),
        !v49) )
  {
    *((_DWORD *)a1 + 3) = v20;
    VdiUserMode = GetVdiUserMode(v20);
    Logger::TraceVerbose(
      (wchar_t *)L"%s: VDI user mode from registry: %lu (%s).",
      L"ReadVdiSettingsFromRegistry",
      v20,
      VdiUserMode);
    v22 = 0;
    if ( !(_QWORD)v55 || (unsigned int)IsEmptyString(v7) )
    {
      Logger::TraceError(
        L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
        L"RegistryPath::ReadMultiStringValue");
      v8 = 87;
      v18 = 87;
    }
    else
    {
      v24 = (HKEY)*((_QWORD *)&v55 + 1);
      if ( *((_QWORD *)&v55 + 1) )
      {
        v25 = 0;
      }
      else
      {
        v25 = RegistryPath::SubPath((RegistryPath *)v54);
        v24 = (HKEY)v23;
      }
      v18 = RegReadMultiStringValue(v24, v25, v23, v7, &Str);
      v8 = v18;
      v3 = Str;
      if ( !v18 )
      {
        if ( !Str )
        {
LABEL_66:
          if ( !(unsigned int)IsEmptyString(*a1)
            || *((_DWORD *)a1 + 2)
            || *((_DWORD *)a1 + 3)
            || *((_DWORD *)a1 + 4) && a1[3] )
          {
            *(_OWORD *)v52 = 0;
            v53 = 0;
            if ( (unsigned int)IsEmptyString(v41) )
            {
              v52[0] = L"Provider";
              Logger::TraceError(L"%s: VDI setting \"%s@%s\" is missing.", L"ReadVdiSettingsFromRegistry", v7);
              v22 = 1;
            }
            if ( !*((_DWORD *)a1 + 2) )
            {
              v52[v22] = L"Type";
              Logger::TraceError(L"%s: VDI setting \"%s@%s\" is missing.", L"ReadVdiSettingsFromRegistry", v7, L"Type");
              ++v22;
            }
            if ( !*((_DWORD *)a1 + 3) )
            {
              v52[v22] = L"User";
              Logger::TraceError(L"%s: VDI setting \"%s@%s\" is missing.", L"ReadVdiSettingsFromRegistry", v7, L"User");
              ++v22;
            }
            if ( v22 )
            {
              Logger::WriteVirtualDesktopAttributeMissingEvent(v7, v22, (const unsigned __int16 **)v52);
              Logger::TraceError(
                L"%s: Missing %lu VDI setting(s). VDI registry settings are invalid.",
                L"ReadVdiSettingsFromRegistry",
                v22);
              v4 = 1;
            }
            else
            {
              v4 = v47;
              if ( v47 != 1 )
              {
                v4 = 2;
                goto LABEL_88;
              }
            }
          }
          else
          {
            v4 = v47;
            if ( v47 != 1 )
              goto LABEL_88;
          }
          v6 = -2145648506;
          goto LABEL_88;
        }
        v26 = Str + 1;
        if ( *Str )
          v26 = Str;
        while ( 1 )
        {
          if ( !*v26 )
            goto LABEL_66;
          if ( *((_DWORD *)a1 + 4) >= 0xAu )
          {
            Logger::TraceWarning(
              (wchar_t *)L"%s: Maximum number (%d) of extension attributes reached. Skipping remaining extensions...",
              L"ReadVdiSettingsFromRegistry",
              10);
            goto LABEL_66;
          }
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v26;
          Str = &v26[v27 + 1];
          if ( v27 > 0x400 )
          {
            v26[10] = 0;
            Logger::TraceWarning(
              (wchar_t *)L"%s: This extension begin with \"%s\" contains more than %lu characters. Skipping it...",
              L"ReadVdiSettingsFromRegistry",
              v26,
              1024);
            goto LABEL_36;
          }
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Parsing extension attribute \"%s\".",
            L"ReadVdiSettingsFromRegistry",
            v26);
          v29 = wcschr(v28, 0x3Au);
          Source = v29;
          if ( v29 )
          {
            *v29 = 0;
            v29 = StringTrimSpace(v29 + 1);
            Source = v29;
          }
          if ( (unsigned int)IsEmptyString(v29) )
            break;
          v51 = StringTrimSpace(v28);
          v22 = 0;
          if ( (unsigned int)IsEmptyString(v51) )
          {
            Logger::TraceWarning(
              (wchar_t *)L"%s: The key of this extension attribute is empty. Skipping it...",
              L"ReadVdiSettingsFromRegistry");
LABEL_51:
            v26 = Str;
          }
          else
          {
            for ( i = 0; i < *((_DWORD *)a1 + 4); ++i )
            {
              v32 = v30;
              do
              {
                v33 = *(const unsigned __int16 *)((char *)v32 + *(_QWORD *)&a1[3][8 * i] - (_QWORD)v30);
                v34 = *v32 - v33;
                if ( v34 )
                  break;
                ++v32;
              }
              while ( v33 );
              if ( !v34 )
              {
                Logger::TraceWarning(
                  (wchar_t *)L"%s: Duplicate key \"%s\" in this extension attribute. Skipping it...",
                  L"ReadVdiSettingsFromRegistry",
                  v30);
                goto LABEL_51;
              }
            }
            v35 = a1[3];
            if ( !v35 )
            {
              v35 = (unsigned __int16 *)operator new[](0xA0u, (const struct std::nothrow_t *)&std::nothrow);
              a1[3] = v35;
              if ( !v35 )
              {
                v6 = -2147024882;
                Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"ReadVdiSettingsFromRegistry");
                goto LABEL_87;
              }
              v30 = v51;
            }
            *(_QWORD *)&v35[8 * *((unsigned int *)a1 + 4)] = 0;
            *(_QWORD *)&a1[3][8 * *((unsigned int *)a1 + 4) + 4] = 0;
            v36 = *((unsigned int *)a1 + 4);
            *((_DWORD *)a1 + 4) = v36 + 1;
            v37 = -1;
            do
              ++v37;
            while ( v30[v37] );
            v38 = CopyStringW(v30, v37, (unsigned __int16 **)&a1[3][8 * v36]);
            v6 = v38;
            if ( v38 < 0 )
              goto LABEL_63;
            v39 = -1;
            v40 = Source;
            do
              ++v39;
            while ( Source[v39] );
            v38 = CopyStringW(Source, v39, (unsigned __int16 **)&a1[3][8 * (*((_DWORD *)a1 + 4) - 1) + 4]);
            v6 = v38;
            if ( v38 < 0 )
            {
LABEL_63:
              Logger::TraceError(
                L"%s: %s failed with error code: 0x%08x.",
                L"ReadVdiSettingsFromRegistry",
                L"CopyStringW",
                (unsigned int)v38);
              goto LABEL_87;
            }
            Logger::TraceVerbose(
              (wchar_t *)L"%s: VDI extension read from registry. Key: \"%s\". Value: \"%s\".",
              L"ReadVdiSettingsFromRegistry",
              v51,
              v40);
LABEL_36:
            v26 = Str;
            v22 = 0;
          }
        }
        Logger::TraceWarning(
          (wchar_t *)L"%s: The value of this extension attribute \"%s\" is empty. Skipping it...",
          L"ReadVdiSettingsFromRegistry",
          v28);
        goto LABEL_36;
      }
    }
    v19 = L"RegistryPath::ReadMultiStringValue";
    goto LABEL_86;
  }
LABEL_16:
  v6 = -2145648506;
LABEL_87:
  v4 = v47;
LABEL_88:
  SafeFree(v3);
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    else
      v6 = v8;
  }
  if ( (v6 & 0x80000000) == 0 )
  {
    if ( v4 == 2 )
      Logger::WriteGetVirtualDesktopAttributeSuccessEvent(v7, (const struct _VDI_SETTINGS *)a1);
  }
  else
  {
    if ( v49 )
      FreeVdiSettings((struct _VDI_SETTINGS *)a1);
    v43 = IsEmptyString(v7);
    v42 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\AzureAD\\VirtualDesktop";
    if ( !v43 )
      v42 = v7;
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v45 = McTemplateU0dz_EventWriteTransfer(v44, GetVirtualDesktopAttributeFailureEvent, v6, v42);
      if ( v45 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteGetVirtualDesktopAttributeFailureEvent",
          L"EventWriteGetVirtualDesktopAttributeFailureEvent",
          v45);
    }
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"ReadVdiSettingsFromRegistry", v6, v42);
  RegistryPath::Reset((RegistryPath *)v54);
  return v6;
}

```

## disassembly

```asm
0x18005f7fc  push    rbp
0x18005f7fe  push    rbx
0x18005f7ff  push    rsi
0x18005f800  push    rdi
0x18005f801  push    r12
0x18005f803  push    r13
0x18005f805  push    r14
0x18005f807  push    r15
0x18005f809  lea     rbp, [rsp-1Fh]
0x18005f80e  sub     rsp, 0B8h
0x18005f815  mov     [rbp+57h+var_B0], edx
0x18005f818  mov     r14, rcx
0x18005f81b  xor     edi, edi
0x18005f81d  mov     r13d, edi
0x18005f820  mov     [rbp+57h+Str], rdi
0x18005f824  mov     dword ptr [rbp+57h+Source], edi
0x18005f827  mov     esi, edi
0x18005f829  mov     [rbp+57h+var_C0], edi
0x18005f82c  mov     [rbp+57h+var_80], rdi
0x18005f830  mov     [rbp+57h+var_78], rdi
0x18005f834  mov     [rbp+57h+var_70], rdi
0x18005f838  mov     [rbp+57h+var_68], rdi
0x18005f83c  xorps   xmm0, xmm0
0x18005f83f  movdqa  [rbp+57h+var_60], xmm0
0x18005f844  mov     [rbp+57h+var_50], rdi
0x18005f848  mov     [rbp+57h+var_48], rdi
0x18005f84c  movups  xmmword ptr [rcx], xmm0
0x18005f84f  movups  xmmword ptr [rcx+10h], xmm0
0x18005f853  xor     r9d, r9d; unsigned __int16 *
0x18005f856  lea     r8, aSoftwareAzurea; "SOFTWARE\\AzureAD\\VirtualDesktop"
0x18005f85d  lea     rdx, aAadvdiparamete; "AadVdiParameters"
0x18005f864  lea     rcx, [rbp+57h+var_80]; this
0x18005f868  call    ?InitializePersistedStatePath@RegistryPath@@QEAAJPEBG00@Z; RegistryPath::InitializePersistedStatePath(ushort const *,ushort const *,ushort const *)
0x18005f86d  mov     ebx, eax
0x18005f86f  mov     r12, [rbp+57h+var_80]
0x18005f873  test    eax, eax
0x18005f875  jns     short loc_18005F8A7
0x18005f877  mov     r15d, edi
0x18005f87a  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18005f87e  lea     r9, aAadvdiparamete; "AadVdiParameters"
0x18005f885  lea     r8, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x18005f88c  lea     rdi, aReadvdisetting; "ReadVdiSettingsFromRegistry"
0x18005f893  mov     rdx, rdi
0x18005f896  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x18005f89d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005f8a2  jmp     loc_18005FEC8
0x18005f8a7  lea     r8, [rbp+57h+Str]; unsigned __int16 **
0x18005f8ab  lea     rdx, aProvider; "Provider"
0x18005f8b2  lea     rcx, [rbp+57h+var_80]; this
0x18005f8b6  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18005f8bb  mov     r15d, eax
0x18005f8be  test    eax, eax
0x18005f8c0  jz      short loc_18005F8EB
0x18005f8c2  mov     r9d, eax
0x18005f8c5  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18005f8cc  lea     rdi, aReadvdisetting; "ReadVdiSettingsFromRegistry"
0x18005f8d3  mov     rdx, rdi
0x18005f8d6  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005f8dd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005f8e2  mov     r13, [rbp+57h+Str]
0x18005f8e6  jmp     loc_18005FEC8
0x18005f8eb  mov     r13, [rbp+57h+Str]
0x18005f8ef  mov     rcx, r13; unsigned __int16 *
0x18005f8f2  call    ?StringTrimSpace@@YAPEAGPEAG@Z; StringTrimSpace(ushort *)
0x18005f8f7  mov     rbx, rax
0x18005f8fa  lea     rdi, aReadvdisetting; "ReadVdiSettingsFromRegistry"
0x18005f901  test    rax, rax
0x18005f904  jz      short loc_18005F936
0x18005f906  mov     rcx, rax; Source
0x18005f909  call    wcsnlen_s
0x18005f90e  mov     r8d, 200h
0x18005f914  cmp     rax, r8
0x18005f917  jnz     short loc_18005F931
0x18005f919  xor     ecx, ecx
0x18005f91b  mov     [rbx+400h], cx
0x18005f922  mov     rdx, rdi
0x18005f925  lea     rcx, aSVdiProviderFr; "%s: VDI provider from registry is longe"...
0x18005f92c  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005f931  mov     r8, rbx
0x18005f934  jmp     short loc_18005F93D
0x18005f936  lea     r8, aNull_2; "<NULL>"
0x18005f93d  mov     rdx, rdi
0x18005f940  lea     rcx, aSVdiProviderFr_0; "%s: VDI provider from registry: %s"
0x18005f947  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005f94c  mov     rdx, r14; unsigned __int16 **
0x18005f94f  mov     rcx, rbx; Source
0x18005f952  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18005f957  mov     ebx, eax
0x18005f959  test    eax, eax
0x18005f95b  jns     short loc_18005F97B
0x18005f95d  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x18005f964  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005f96b  mov     rdx, rdi
0x18005f96e  mov     r9d, eax
0x18005f971  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005f976  jmp     loc_18005FEC8
0x18005f97b  mov     rcx, r13; lpMem
0x18005f97e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18005f983  xor     r13d, r13d
0x18005f986  mov     [rbp+57h+Str], r13
0x18005f98a  xor     r9d, r9d; unsigned int
0x18005f98d  lea     r8, [rbp+57h+Source]; unsigned int *
0x18005f991  lea     rdx, aType; "Type"
0x18005f998  lea     rcx, [rbp+57h+var_80]; this
0x18005f99c  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18005f9a1  mov     r15d, eax
0x18005f9a4  test    eax, eax
0x18005f9a6  jz      short loc_18005F9B8
0x18005f9a8  lea     r8, aRegistrypathRe_5; "RegistryPath::ReadDwordValue"
0x18005f9af  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005f9b6  jmp     short loc_18005F96B
0x18005f9b8  mov     esi, dword ptr [rbp+57h+Source]
0x18005f9bb  cmp     esi, 3
0x18005f9be  jb      short loc_18005FA0A
0x18005f9c0  mov     [rbp+57h+var_C0], 1
0x18005f9c7  mov     r8d, esi; unsigned int
0x18005f9ca  lea     rdx, aType; "Type"
0x18005f9d1  mov     rcx, r12; unsigned __int16 *
0x18005f9d4  call    ?WriteInvalidVirtualDesktopAttributeEvent@Logger@@SAJPEBG0K@Z; Logger::WriteInvalidVirtualDesktopAttributeEvent(ushort const *,ushort const *,ulong)
0x18005f9d9  lea     rax, aType; "Type"
0x18005f9e0  mov     [rsp+0F0h+var_D0], rax
0x18005f9e5  mov     r9, r12
0x18005f9e8  mov     r8d, esi
0x18005f9eb  mov     rdx, rdi
0x18005f9ee  lea     rcx, aSVirtualDeskto; "%s: Virtual desktop type (%lu) is inval"...
0x18005f9f5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005f9fa  cmp     [rbp+57h+var_B0], r13d
0x18005f9fe  jz      short loc_18005FA0A
0x18005fa00  mov     ebx, 801C0086h
0x18005fa05  jmp     loc_18005FEC5
0x18005fa0a  mov     [r14+8], esi
0x18005fa0e  mov     ecx, esi; unsigned int
0x18005fa10  call    ?GetVdiTypeName@@YAPEBGK@Z; GetVdiTypeName(ulong)
0x18005fa15  mov     r9, rax
0x18005fa18  mov     r8d, esi
0x18005fa1b  mov     rdx, rdi
0x18005fa1e  lea     rcx, aSVdiTypeFromRe; "%s: VDI type from registry: %lu (%s)."
0x18005fa25  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005fa2a  xor     r9d, r9d; unsigned int
0x18005fa2d  lea     r8, [rbp+57h+Source]; unsigned int *
0x18005fa31  lea     rdx, aUser; "User"
0x18005fa38  lea     rcx, [rbp+57h+var_80]; this
0x18005fa3c  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18005fa41  mov     r15d, eax
0x18005fa44  test    eax, eax
0x18005fa46  jz      short loc_18005FA54
0x18005fa48  lea     r8, aRegistrypathRe_5; "RegistryPath::ReadDwordValue"
0x18005fa4f  jmp     loc_18005FEB3
0x18005fa54  mov     esi, dword ptr [rbp+57h+Source]
0x18005fa57  cmp     esi, 3
0x18005fa5a  jb      short loc_18005FAA0
0x18005fa5c  mov     [rbp+57h+var_C0], 1
0x18005fa63  mov     r8d, esi; unsigned int
0x18005fa66  lea     rdx, aUser; "User"
0x18005fa6d  mov     rcx, r12; unsigned __int16 *
0x18005fa70  call    ?WriteInvalidVirtualDesktopAttributeEvent@Logger@@SAJPEBG0K@Z; Logger::WriteInvalidVirtualDesktopAttributeEvent(ushort const *,ushort const *,ulong)
0x18005fa75  lea     rax, aUser; "User"
0x18005fa7c  mov     [rsp+0F0h+var_D0], rax
0x18005fa81  mov     r9, r12
0x18005fa84  mov     r8d, esi
0x18005fa87  mov     rdx, rdi
0x18005fa8a  lea     rcx, aSVirtualDeskto_0; "%s: Virtual desktop user mode (%lu) is "...
0x18005fa91  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005fa96  cmp     [rbp+57h+var_B0], r13d
0x18005fa9a  jnz     loc_18005FA00
0x18005faa0  mov     [r14+0Ch], esi
0x18005faa4  mov     ecx, esi; unsigned int
0x18005faa6  call    ?GetVdiUserMode@@YAPEBGK@Z; GetVdiUserMode(ulong)
0x18005faab  mov     r9, rax
0x18005faae  mov     r8d, esi
0x18005fab1  mov     rdx, rdi
0x18005fab4  lea     rcx, aSVdiUserModeFr; "%s: VDI user mode from registry: %lu (%"...
0x18005fabb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005fac0  mov     r8, qword ptr [rbp+57h+var_60]
0x18005fac4  xor     esi, esi
0x18005fac6  test    r8, r8
0x18005fac9  jz      loc_18005FE90
0x18005facf  mov     rcx, r12; unsigned __int16 *
0x18005fad2  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18005fad7  test    eax, eax
0x18005fad9  jnz     loc_18005FE90
0x18005fadf  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x18005fae3  test    rcx, rcx
0x18005fae6  jz      short loc_18005FAEC
0x18005fae8  xor     edx, edx
0x18005faea  jmp     short loc_18005FAFB
0x18005faec  lea     rcx, [rbp+57h+var_80]; this
0x18005faf0  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x18005faf5  mov     rdx, rax; lpSubKey
0x18005faf8  mov     rcx, r8; hkey
0x18005fafb  lea     rax, [rbp+57h+Str]
0x18005faff  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 **
0x18005fb04  mov     r9, r12; unsigned __int16 *
0x18005fb07  call    ?RegReadMultiStringValue@@YAKPEAUHKEY__@@PEBG11PEAPEAG@Z; RegReadMultiStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort * *)
0x18005fb0c  mov     r15d, eax
0x18005fb0f  mov     r13, [rbp+57h+Str]
0x18005fb13  test    eax, eax
0x18005fb15  jnz     loc_18005FEAC
0x18005fb1b  test    r13, r13
0x18005fb1e  jz      loc_18005FD87
0x18005fb24  lea     rcx, [r13+2]
0x18005fb28  cmp     [r13+0], si
0x18005fb2d  cmovnz  rcx, r13
0x18005fb31  cmp     [rcx], si
0x18005fb34  jz      loc_18005FD87
0x18005fb3a  cmp     dword ptr [r14+10h], 0Ah
0x18005fb3f  jnb     loc_18005FD72
0x18005fb45  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005fb49  inc     rax
0x18005fb4c  cmp     [rcx+rax*2], si
0x18005fb50  jnz     short loc_18005FB49
0x18005fb52  mov     rsi, rcx
0x18005fb55  lea     rcx, [rcx+rax*2]
0x18005fb59  add     rcx, 2
0x18005fb5d  mov     [rbp+57h+Str], rcx
0x18005fb61  mov     r8, rsi
0x18005fb64  mov     rdx, rdi
0x18005fb67  cmp     rax, 400h
0x18005fb6d  jbe     short loc_18005FB8F
0x18005fb6f  xor     eax, eax
0x18005fb71  mov     [rsi+14h], ax
0x18005fb75  mov     r9d, 400h
0x18005fb7b  lea     rcx, aSThisExtension; "%s: This extension begin with \"%s\" co"...
0x18005fb82  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005fb87  mov     rcx, [rbp+57h+Str]
0x18005fb8b  xor     esi, esi
0x18005fb8d  jmp     short loc_18005FB31
0x18005fb8f  lea     rcx, aSParsingExtens; "%s: Parsing extension attribute \"%s\"."
0x18005fb96  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005fb9b  mov     edx, 3Ah ; ':'; Ch
0x18005fba0  mov     rcx, rsi; Str
0x18005fba3  call    cs:__imp_wcschr
0x18005fba9  mov     [rbp+57h+Source], rax
0x18005fbad  xor     ecx, ecx
0x18005fbaf  test    rax, rax
0x18005fbb2  jz      short loc_18005FBC4
0x18005fbb4  mov     [rax], cx
0x18005fbb7  lea     rcx, [rax+2]; unsigned __int16 *
0x18005fbbb  call    ?StringTrimSpace@@YAPEAGPEAG@Z; StringTrimSpace(ushort *)
0x18005fbc0  mov     [rbp+57h+Source], rax
0x18005fbc4  mov     rcx, rax; unsigned __int16 *
0x18005fbc7  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18005fbcc  test    eax, eax
0x18005fbce  jz      short loc_18005FBE4
0x18005fbd0  mov     r8, rsi
0x18005fbd3  mov     rdx, rdi
0x18005fbd6  lea     rcx, aSTheValueOfThi; "%s: The value of this extension attribu"...
0x18005fbdd  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005fbe2  jmp     short loc_18005FB87
0x18005fbe4  mov     rcx, rsi; unsigned __int16 *
0x18005fbe7  call    ?StringTrimSpace@@YAPEAGPEAG@Z; StringTrimSpace(ushort *)
0x18005fbec  mov     r10, rax
0x18005fbef  mov     [rbp+57h+var_A0], rax
0x18005fbf3  mov     rcx, rax; unsigned __int16 *
0x18005fbf6  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18005fbfb  xor     esi, esi
0x18005fbfd  test    eax, eax
0x18005fbff  jz      short loc_18005FC12
0x18005fc01  mov     rdx, rdi
0x18005fc04  lea     rcx, aSTheKeyOfThisE; "%s: The key of this extension attribute"...
0x18005fc0b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005fc10  jmp     short loc_18005FC5E
0x18005fc12  mov     r8d, esi
0x18005fc15  cmp     r8d, [r14+10h]
0x18005fc19  jnb     short loc_18005FC67
0x18005fc1b  mov     ecx, r8d
0x18005fc1e  add     rcx, rcx
0x18005fc21  mov     rax, [r14+18h]
0x18005fc25  mov     rdx, r10
0x18005fc28  mov     r9, [rax+rcx*8]
0x18005fc2c  sub     r9, r10
0x18005fc2f  movzx   ecx, word ptr [rdx]
0x18005fc32  movzx   eax, word ptr [rdx+r9]
0x18005fc37  sub     ecx, eax
0x18005fc39  jnz     short loc_18005FC43
0x18005fc3b  add     rdx, 2
0x18005fc3f  test    eax, eax
0x18005fc41  jnz     short loc_18005FC2F
0x18005fc43  test    ecx, ecx
0x18005fc45  jz      short loc_18005FC4C
0x18005fc47  inc     r8d
0x18005fc4a  jmp     short loc_18005FC15
0x18005fc4c  mov     r8, r10
0x18005fc4f  mov     rdx, rdi
0x18005fc52  lea     rcx, aSDuplicateKeyS; "%s: Duplicate key \"%s\" in this extens"...
0x18005fc59  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005fc5e  mov     rcx, [rbp+57h+Str]
0x18005fc62  jmp     loc_18005FB31
0x18005fc67  mov     rcx, [r14+18h]
0x18005fc6b  test    rcx, rcx
0x18005fc6e  jnz     short loc_18005FC95
0x18005fc70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005fc77  mov     ecx, 0A0h; unsigned __int64
0x18005fc7c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005fc81  mov     rcx, rax
0x18005fc84  mov     [r14+18h], rax
0x18005fc88  test    rax, rax
0x18005fc8b  jz      loc_18005FD33
0x18005fc91  mov     r10, [rbp+57h+var_A0]
0x18005fc95  mov     eax, [r14+10h]
  ... truncated ...
```
