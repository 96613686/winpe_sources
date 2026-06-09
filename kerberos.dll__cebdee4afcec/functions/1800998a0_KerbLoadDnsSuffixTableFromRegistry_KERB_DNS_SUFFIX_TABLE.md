# KerbLoadDnsSuffixTableFromRegistry(_KERB_DNS_SUFFIX_TABLE *)

- ea: `0x1800998a0`
- end: `0x180099c6a`
- name: `?KerbLoadDnsSuffixTableFromRegistry@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z`
- size: `970`
- prototype: `void __fastcall(struct _KERB_DNS_SUFFIX_TABLE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007e200`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x180034a4c`
- `0x18006a9e4`
- `0x180070680`
- `0x18007108c`
- `0x18008b70c`
- `0x1800965a0`
- `0x180097ab0`
- `0x180097d74`
- `0x180099414`
- `0x1800998a0`
- `0x18009a6ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800999d9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180099a56`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800999d9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180099a56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099c3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099c3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009995f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009995f`
- `ntdll!WinSqmSetDWORD` at `0x180099c11`
- `ntdll!WinSqmSetDWORD` at `0x180099c11`

## string_xrefs

- `0x180099916`: `Failed to create a temporary dns suffix table: %#x`
- `0x180099926`: `KerbLoadDnsSuffixTableFromRegistry`
- `0x180099b08`: `KerbLoadDnsSuffixTableFromRegistry`
- `0x180099b5e`: `KerbLoadDnsSuffixTableFromRegistry`
- `0x180099bf6`: `KerbLoadDnsSuffixTableFromRegistry`
- `0x180099b3a`: `RegEnumValueW failed to read data: %#x`
- `0x180099ada`: `Failed to add registry data to dns suffix table: %#x`
- `0x180099be5`: `RegOpenKeyEx failed: %#x`

## pseudocode

```c
void __fastcall KerbLoadDnsSuffixTableFromRegistry(struct _KERB_DNS_SUFFIX_TABLE *a1)
{
  BYTE *lpData; // rsi
  int inited; // eax
  int v3; // edi
  const char *v4; // r9
  __int64 v5; // r8
  DWORD v6; // r14d
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  struct _RTL_AVL_TABLE *v10; // rax
  __int128 v11; // xmm0
  struct _KERB_DNS_SUFFIX_TABLE *v12; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  LPDWORD lpType; // [rsp+28h] [rbp-D8h]
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v20; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v21; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[48]; // [rsp+80h] [rbp-80h] BYREF
  PRTL_AVL_TABLE v23; // [rsp+B0h] [rbp-50h]
  __int128 v24; // [rsp+B8h] [rbp-48h]
  WCHAR ValueName[264]; // [rsp+D0h] [rbp-30h] BYREF

  lpData = 0;
  hKey = 0;
  cchValueName = 0;
  Type = 0;
  cbData = 0;
  v20 = 0;
  v21 = 0;
  memset_0(v22, 0, 0x48u);
  inited = KerbInitDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)v22, 0);
  v3 = inited;
  if ( inited >= 0 )
  {
    v6 = 0;
    v7 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\KdcProxy\\ProxyServers",
           0,
           0x20019u,
           &hKey);
    v3 = v7;
    if ( v7 )
    {
      KerbTracerT::Log(13, "KerbLoadDnsSuffixTableFromRegistry", 6541, "RegOpenKeyEx failed: %#x", v7);
    }
    else
    {
      while ( 1 )
      {
        memset_0(ValueName, 0, 0x20Au);
        cchValueName = 261;
        if ( lpData )
        {
          KerbFree(lpData);
          lpData = 0;
        }
        cbData = 0;
        v8 = RegEnumValueW(hKey, v6, ValueName, &cchValueName, 0, &Type, 0, &cbData);
        if ( v8 == 259 )
          break;
        if ( v8 )
        {
          LODWORD(phkResulta) = v8;
          KerbTracerT::Log(
            1,
            "KerbLoadDnsSuffixTableFromRegistry",
            6448,
            "RegEnumValueW failed to return data size: %#x",
            phkResulta);
          goto LABEL_28;
        }
        if ( Type == 1 && cchValueName )
        {
          lpData = (BYTE *)MIDL_user_allocate(cbData);
          if ( !lpData )
          {
            LODWORD(phkResulta) = 8;
            KerbTracerT::Log(
              1,
              "KerbLoadDnsSuffixTableFromRegistry",
              6470,
              "Failed to allocate memory: %#x",
              phkResulta);
            goto LABEL_28;
          }
          cchValueName = 261;
          v9 = RegEnumValueW(hKey, v6, ValueName, &cchValueName, 0, &Type, lpData, &cbData);
          if ( v9 )
          {
            LODWORD(phkResult) = v9;
            KerbTracerT::Log(
              1,
              "KerbLoadDnsSuffixTableFromRegistry",
              6489,
              "RegEnumValueW failed to read data: %#x",
              phkResult);
            goto LABEL_28;
          }
          if ( (cbData & 1) != 0 || (unsigned __int64)cbData + 2 > 0xFFFF )
          {
            LODWORD(lpType) = 87;
            LODWORD(phkResult) = cbData;
            KerbTracerT::Log(
              1,
              "KerbLoadDnsSuffixTableFromRegistry",
              6496,
              "RegEnumValueW returns invalid data size (%ul): %#x",
              phkResult,
              lpType);
            goto LABEL_28;
          }
          v20.Length = cbData;
          v20.MaximumLength = cbData;
          v20.Buffer = (PWSTR)lpData;
          if ( 2 * (unsigned __int64)cchValueName + 2 > 0xFFFF )
          {
            LODWORD(lpType) = 87;
            KerbTracerT::Log(
              1,
              "KerbLoadDnsSuffixTableFromRegistry",
              6507,
              "RegEnumValueW returns invalid value name (%ul): %#x",
              2LL * cchValueName,
              lpType);
            goto LABEL_28;
          }
          v21.Length = 2 * cchValueName;
          v21.MaximumLength = 2 * cchValueName;
          v21.Buffer = ValueName;
          inited = KerbAddDnsSuffixToTable((struct _KERB_DNS_SUFFIX_TABLE *)v22, &v21, &v20);
          v3 = inited;
          if ( inited < 0 )
          {
            v4 = "Failed to add registry data to dns suffix table: %#x";
            v5 = 6523;
            goto LABEL_3;
          }
        }
        ++v6;
      }
      v3 = 0;
      KerbLockDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)&KerbGlobalDnsSuffixTable);
      KerbLockDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)v22);
      v10 = v23;
      v11 = v24;
      v23 = qword_180144DE0;
      v24 = xmmword_180144DE8;
      qword_180144DE0 = v10;
      xmmword_180144DE8 = v11;
      KerbUnlockDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)v22);
      KerbUnlockDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)&KerbGlobalDnsSuffixTable);
      KerbDumpDnsSuffixTable(v12);
    }
    WinSqmSetDWORD(0, 10687);
  }
  else
  {
    v4 = "Failed to create a temporary dns suffix table: %#x";
    v5 = 6404;
LABEL_3:
    LODWORD(phkResult) = inited;
    KerbTracerT::Log(1, "KerbLoadDnsSuffixTableFromRegistry", v5, v4, phkResult);
  }
  if ( v3 )
LABEL_28:
    KerbCleanupDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)&KerbGlobalDnsSuffixTable);
  if ( lpData )
    KerbFree(lpData);
  if ( hKey )
    RegCloseKey(hKey);
  KerbUninitDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)v22);
}

```

## disassembly

```asm
0x1800998a0  push    rbp
0x1800998a2  push    rbx
0x1800998a3  push    rsi
0x1800998a4  push    rdi
0x1800998a5  push    r14
0x1800998a7  lea     rbp, [rsp-1F0h]
0x1800998af  sub     rsp, 2F0h
0x1800998b6  mov     rax, cs:__security_cookie
0x1800998bd  xor     rax, rsp
0x1800998c0  mov     [rbp+210h+var_30], rax
0x1800998c7  xor     esi, esi
0x1800998c9  mov     [rsp+310h+hKey], 0
0x1800998d2  xorps   xmm0, xmm0
0x1800998d5  mov     [rsp+310h+cchValueName], 0
0x1800998dd  xorps   xmm1, xmm1
0x1800998e0  mov     [rsp+310h+Type], 0
0x1800998e8  xor     edx, edx; Val
0x1800998ea  mov     [rsp+310h+cbData], esi
0x1800998ee  lea     r8d, [rsi+48h]; Size
0x1800998f2  lea     rcx, [rbp+210h+var_290]; void *
0x1800998f6  movups  xmmword ptr [rsp+310h+var_2B8.Length], xmm0
0x1800998fb  movups  xmmword ptr [rsp+310h+var_2A8.Length], xmm1
0x180099900  call    memset_0
0x180099905  xor     edx, edx; unsigned __int8
0x180099907  lea     rcx, [rbp+210h+var_290]; struct _KERB_DNS_SUFFIX_TABLE *
0x18009990b  call    ?KerbInitDnsSuffixTable@@YAJPEAU_KERB_DNS_SUFFIX_TABLE@@E@Z; KerbInitDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *,uchar)
0x180099910  mov     edi, eax
0x180099912  test    eax, eax
0x180099914  jns     short loc_18009993B
0x180099916  lea     r9, aFailedToCreate_17; "Failed to create a temporary dns suffix"...
0x18009991d  mov     r8d, 1904h
0x180099923  lea     ecx, [rsi+1]
0x180099926  lea     rdx, aKerbloaddnssuf; "KerbLoadDnsSuffixTableFromRegistry"
0x18009992d  mov     dword ptr [rsp+310h+phkResult], eax
0x180099931  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180099936  jmp     loc_180099C17
0x18009993b  lea     rax, [rsp+310h+hKey]
0x180099940  mov     r9d, 20019h; samDesired
0x180099946  xor     r8d, r8d; ulOptions
0x180099949  mov     [rsp+310h+phkResult], rax; phkResult
0x18009994e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180099955  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009995c  xor     r14d, r14d
0x18009995f  call    cs:__imp_RegOpenKeyExW
0x180099965  mov     edi, eax
0x180099967  test    eax, eax
0x180099969  jnz     loc_180099BE5
0x18009996f  lea     ebx, [rax+1]
0x180099972  xor     edx, edx; Val
0x180099974  lea     rcx, [rbp+210h+ValueName]; void *
0x180099978  mov     r8d, 20Ah; Size
0x18009997e  call    memset_0
0x180099983  mov     [rsp+310h+cchValueName], 105h
0x18009998b  test    rsi, rsi
0x18009998e  jz      short loc_18009999A
0x180099990  mov     rcx, rsi
0x180099993  call    KerbFree
0x180099998  xor     esi, esi
0x18009999a  mov     rcx, [rsp+310h+hKey]; hKey
0x18009999f  lea     rax, [rsp+310h+cbData]
0x1800999a4  mov     [rsp+310h+lpcbData], rax; lpcbData
0x1800999a9  lea     r9, [rsp+310h+cchValueName]; lpcchValueName
0x1800999ae  lea     rax, [rsp+310h+Type]
0x1800999b3  mov     [rsp+310h+lpData], 0; lpData
0x1800999bc  mov     [rsp+310h+lpType], rax; lpType
0x1800999c1  lea     r8, [rbp+210h+ValueName]; lpValueName
0x1800999c5  mov     edx, r14d; dwIndex
0x1800999c8  mov     [rsp+310h+phkResult], 0; lpReserved
0x1800999d1  mov     [rsp+310h+cbData], 0
0x1800999d9  call    cs:__imp_RegEnumValueW
0x1800999df  cmp     eax, 103h
0x1800999e4  jz      loc_180099B84
0x1800999ea  test    eax, eax
0x1800999ec  jnz     loc_180099B71
0x1800999f2  cmp     [rsp+310h+Type], ebx
0x1800999f6  jnz     loc_180099AD2
0x1800999fc  cmp     [rsp+310h+cchValueName], eax
0x180099a00  jz      loc_180099AD2
0x180099a06  mov     ecx, [rsp+310h+cbData]; size
0x180099a0a  call    MIDL_user_allocate
0x180099a0f  mov     rsi, rax
0x180099a12  test    rax, rax
0x180099a15  jz      loc_180099B49
0x180099a1b  mov     rcx, [rsp+310h+hKey]; hKey
0x180099a20  lea     rax, [rsp+310h+cbData]
0x180099a25  mov     [rsp+310h+lpcbData], rax; lpcbData
0x180099a2a  lea     r9, [rsp+310h+cchValueName]; lpcchValueName
0x180099a2f  lea     rax, [rsp+310h+Type]
0x180099a34  mov     [rsp+310h+lpData], rsi; lpData
0x180099a39  mov     [rsp+310h+lpType], rax; lpType
0x180099a3e  lea     r8, [rbp+210h+ValueName]; lpValueName
0x180099a42  mov     edx, r14d; dwIndex
0x180099a45  mov     [rsp+310h+phkResult], 0; lpReserved
0x180099a4e  mov     [rsp+310h+cchValueName], 105h
0x180099a56  call    cs:__imp_RegEnumValueW
0x180099a5c  test    eax, eax
0x180099a5e  jnz     loc_180099B36
0x180099a64  mov     ecx, [rsp+310h+cbData]
0x180099a68  test    bl, cl
0x180099a6a  jnz     loc_180099B1B
0x180099a70  lea     rax, [rcx+2]
0x180099a74  cmp     rax, 0FFFFh
0x180099a7a  ja      loc_180099B1B
0x180099a80  mov     [rsp+310h+var_2B8.Length], cx
0x180099a85  mov     [rsp+310h+var_2B8.MaximumLength], cx
0x180099a8a  mov     ecx, [rsp+310h+cchValueName]
0x180099a8e  mov     [rsp+310h+var_2B8.Buffer], rsi
0x180099a93  lea     rdx, [rcx+rcx]
0x180099a97  lea     rax, [rdx+2]
0x180099a9b  cmp     rax, 0FFFFh
0x180099aa1  ja      short loc_180099AEE
0x180099aa3  add     cx, cx
0x180099aa6  lea     rax, [rbp+210h+ValueName]
0x180099aaa  mov     [rsp+310h+var_2A8.Length], cx
0x180099aaf  lea     r8, [rsp+310h+var_2B8]; struct _UNICODE_STRING *
0x180099ab4  mov     [rsp+310h+var_2A8.MaximumLength], cx
0x180099ab9  lea     rdx, [rsp+310h+var_2A8]; struct _UNICODE_STRING *
0x180099abe  lea     rcx, [rbp+210h+var_290]; struct _KERB_DNS_SUFFIX_TABLE *
0x180099ac2  mov     [rsp+310h+var_2A8.Buffer], rax
0x180099ac7  call    ?KerbAddDnsSuffixToTable@@YAJPEAU_KERB_DNS_SUFFIX_TABLE@@PEAU_UNICODE_STRING@@1@Z; KerbAddDnsSuffixToTable(_KERB_DNS_SUFFIX_TABLE *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180099acc  mov     edi, eax
0x180099ace  test    eax, eax
0x180099ad0  js      short loc_180099ADA
0x180099ad2  add     r14d, ebx
0x180099ad5  jmp     loc_180099972
0x180099ada  lea     r9, aFailedToAddReg; "Failed to add registry data to dns suff"...
0x180099ae1  mov     r8d, 197Bh
0x180099ae7  mov     ecx, ebx
0x180099ae9  jmp     loc_180099926
0x180099aee  mov     dword ptr [rsp+310h+lpType], 57h ; 'W'
0x180099af6  lea     r9, aRegenumvaluewR_0; "RegEnumValueW returns invalid value nam"...
0x180099afd  mov     [rsp+310h+phkResult], rdx
0x180099b02  mov     r8d, 196Bh
0x180099b08  lea     rdx, aKerbloaddnssuf; "KerbLoadDnsSuffixTableFromRegistry"
0x180099b0f  mov     ecx, ebx
0x180099b11  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180099b16  jmp     loc_180099C1B
0x180099b1b  mov     dword ptr [rsp+310h+lpType], 57h ; 'W'
0x180099b23  lea     r9, aRegenumvaluewR; "RegEnumValueW returns invalid data size"...
0x180099b2a  mov     dword ptr [rsp+310h+phkResult], ecx
0x180099b2e  mov     r8d, 1960h
0x180099b34  jmp     short loc_180099B08
0x180099b36  mov     dword ptr [rsp+310h+phkResult], eax
0x180099b3a  lea     r9, aRegenumvaluewF; "RegEnumValueW failed to read data: %#x"
0x180099b41  mov     r8d, 1959h
0x180099b47  jmp     short loc_180099B5E
0x180099b49  mov     dword ptr [rsp+310h+phkResult], 8
0x180099b51  lea     r9, aFailedToAlloca_9; "Failed to allocate memory: %#x"
0x180099b58  mov     r8d, 1946h
0x180099b5e  lea     rdx, aKerbloaddnssuf; "KerbLoadDnsSuffixTableFromRegistry"
0x180099b65  mov     ecx, ebx
0x180099b67  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180099b6c  jmp     loc_180099C1B
0x180099b71  mov     dword ptr [rsp+310h+phkResult], eax
0x180099b75  lea     r9, aRegenumvaluewF_0; "RegEnumValueW failed to return data siz"...
0x180099b7c  mov     r8d, 1930h
0x180099b82  jmp     short loc_180099B5E
0x180099b84  lea     rcx, ?KerbGlobalDnsSuffixTable@@3U_KERB_DNS_SUFFIX_TABLE@@A; struct _KERB_DNS_SUFFIX_TABLE *
0x180099b8b  xor     edi, edi
0x180099b8d  call    ?KerbLockDnsSuffixTable@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z; KerbLockDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *)
0x180099b92  lea     rcx, [rbp+210h+var_290]; struct _KERB_DNS_SUFFIX_TABLE *
0x180099b96  call    ?KerbLockDnsSuffixTable@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z; KerbLockDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *)
0x180099b9b  mov     rcx, cs:qword_180144DE0
0x180099ba2  movups  xmm1, cs:xmmword_180144DE8
0x180099ba9  mov     rax, [rbp+210h+var_260]
0x180099bad  movups  xmm0, [rbp+210h+var_258]
0x180099bb1  mov     [rbp+210h+var_260], rcx
0x180099bb5  lea     rcx, [rbp+210h+var_290]; struct _KERB_DNS_SUFFIX_TABLE *
0x180099bb9  movdqu  [rbp+210h+var_258], xmm1
0x180099bbe  mov     cs:qword_180144DE0, rax
0x180099bc5  movdqu  cs:xmmword_180144DE8, xmm0
0x180099bcd  call    ?KerbUnlockDnsSuffixTable@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z; KerbUnlockDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *)
0x180099bd2  lea     rcx, ?KerbGlobalDnsSuffixTable@@3U_KERB_DNS_SUFFIX_TABLE@@A; struct _KERB_DNS_SUFFIX_TABLE *
0x180099bd9  call    ?KerbUnlockDnsSuffixTable@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z; KerbUnlockDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *)
0x180099bde  call    ?KerbDumpDnsSuffixTable@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z; KerbDumpDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *)
0x180099be3  jmp     short loc_180099C07
0x180099be5  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx failed: %#x"
0x180099bec  mov     dword ptr [rsp+310h+phkResult], eax
0x180099bf0  mov     r8d, 198Dh
0x180099bf6  lea     rdx, aKerbloaddnssuf; "KerbLoadDnsSuffixTableFromRegistry"
0x180099bfd  mov     ecx, 0Dh
0x180099c02  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180099c07  mov     r8d, r14d
0x180099c0a  mov     edx, 29BFh
0x180099c0f  xor     ecx, ecx
0x180099c11  call    cs:__imp_WinSqmSetDWORD
0x180099c17  test    edi, edi
0x180099c19  jz      short loc_180099C27
0x180099c1b  lea     rcx, ?KerbGlobalDnsSuffixTable@@3U_KERB_DNS_SUFFIX_TABLE@@A; struct _KERB_DNS_SUFFIX_TABLE *
0x180099c22  call    ?KerbCleanupDnsSuffixTable@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z; KerbCleanupDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *)
0x180099c27  test    rsi, rsi
0x180099c2a  jz      short loc_180099C34
0x180099c2c  mov     rcx, rsi
0x180099c2f  call    KerbFree
0x180099c34  mov     rcx, [rsp+310h+hKey]; hKey
0x180099c39  test    rcx, rcx
0x180099c3c  jz      short loc_180099C44
0x180099c3e  call    cs:__imp_RegCloseKey
0x180099c44  lea     rcx, [rbp+210h+var_290]; struct _KERB_DNS_SUFFIX_TABLE *
0x180099c48  call    ?KerbUninitDnsSuffixTable@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z; KerbUninitDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *)
0x180099c4d  mov     rcx, [rbp+210h+var_30]
0x180099c54  xor     rcx, rsp; StackCookie
0x180099c57  call    __security_check_cookie
0x180099c5c  add     rsp, 2F0h
0x180099c63  pop     r14
0x180099c65  pop     rdi
0x180099c66  pop     rsi
0x180099c67  pop     rbx
0x180099c68  pop     rbp
0x180099c69  retn
```
