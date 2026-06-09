# AdapterInfo_UpdateDnsInterfaceConfig

- ea: `0x18003d614`
- end: `0x18003da65`
- name: `AdapterInfo_UpdateDnsInterfaceConfig`
- size: `1105`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18003bda0`
- `0x18009bef0`

## callees

- `0x18003d614`
- `0x18003de30`
- `0x18007f24c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800cccb0`
- `0x1800dbb48`
- `0x1800dc4ac`
- `0x1800dc670`
- `0x1800dc9e0`
- `0x1800dcb7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d89c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d89c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d78e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d78e`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003d6b7`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003d6b7`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18003d83c`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18003d83c`

## string_xrefs

- `0x18003d69d`: `Dnscache`
- `0x18003d917`: `Dnscache`
- `0x18003d96d`: `Dnscache`
- `0x18003d9d1`: `Dnscache`
- `0x18003d683`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18003d91e`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18003d9c5`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall AdapterInfo_UpdateDnsInterfaceConfig(__int64 a1)
{
  int v2; // esi
  unsigned int v3; // r15d
  int v4; // edx
  int v5; // r8d
  int PersistedStateLocation; // eax
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  int v10; // r14d
  unsigned __int64 v11; // rdx
  _WORD *v12; // r8
  __int64 v13; // rax
  const wchar_t *v14; // rcx
  _WORD *v15; // rcx
  unsigned int v16; // ebx
  LSTATUS v17; // eax
  int v18; // ecx
  LSTATUS v19; // eax
  int v20; // ecx
  int v21; // eax
  int v23; // eax
  unsigned int v24; // eax
  int v25; // edx
  const wchar_t *v26; // r9
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v32[264]; // [rsp+60h] [rbp-A0h] BYREF

  phkResult = 0;
  v2 = 0;
  v3 = 0;
  memset_0(v32, 0, 0x20Au);
  hKey = 0;
  Type = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_SSSqd(
      (unsigned int)L"InterfaceSpecificParameters",
      v4,
      v5,
      (unsigned int)L"Dnscache",
      (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
      (__int64)L"InterfaceSpecificParameters",
      (__int64)v32,
      10);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"Dnscache",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                             0,
                             v32,
                             522,
                             &Type);
  v10 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      WPP_SF_SSSd(
        v8,
        v7,
        v9,
        (unsigned int)L"Dnscache",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
        (__int64)L"InterfaceSpecificParameters",
        PersistedStateLocation);
    v16 = HRESULT_FROM_NTSTATUS(v10);
  }
  else
  {
    v11 = (unsigned __int64)(522 - Type) >> 1;
    v12 = &v32[(unsigned __int64)Type >> 1];
    *(v12 - 1) = 92;
    if ( v11 )
    {
      v13 = 2147483646;
      v14 = L"InterfaceSpecificParameters";
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v12++ = *v14++;
        --v13;
        --v11;
      }
      while ( v11 );
      v15 = v12 - 1;
      if ( v11 )
        v15 = v12;
      *v15 = 0;
      v16 = v11 == 0 ? 0x8007007A : 0;
      if ( v11 )
      {
        if ( (BYTE3(xmmword_1801119E0) & 0x20) == 0 )
          goto LABEL_13;
        WPP_SF_SSSS(
          (_DWORD)v15,
          v11,
          (_DWORD)v12,
          (unsigned int)L"Dnscache",
          (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
          (__int64)L"InterfaceSpecificParameters",
          (__int64)v32);
        goto LABEL_41;
      }
    }
    else
    {
      v16 = -2147024809;
    }
    if ( (BYTE3(xmmword_1801119E0) & 0x20) == 0 )
      goto LABEL_13;
    WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, v16);
  }
LABEL_41:
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, v16);
LABEL_13:
  if ( (v16 & 0x80000000) == 0 )
    v17 = RegOpenKeyExInternalW(-2147483646, v32, 0, 131097, &hKey, 0);
  else
    v17 = WX_WIN32_FROM_HR(v16);
  if ( v17 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_19;
    v25 = 10;
    v26 = v32;
LABEL_44:
    WPP_SF_SD(v18, v25, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (_DWORD)v26, v17);
    goto LABEL_19;
  }
  v19 = RegOpenKeyExW(hKey, *(LPCWSTR *)a1, 0, 0x20019u, &phkResult);
  if ( v19 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_SSD(
        v20,
        344,
        (unsigned int)WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids,
        *(_QWORD *)(a1 + 120),
        *(_QWORD *)a1,
        v19);
    goto LABEL_19;
  }
  v18 = (int)phkResult;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  if ( phkResult && L"DisableUnConstrainedQueries" )
  {
    v17 = RegQueryValueExW(phkResult, L"DisableUnConstrainedQueries", 0, &Type, Data, &cbData);
    if ( v17 )
    {
      if ( v17 == 2 )
        goto LABEL_19;
    }
    else
    {
      if ( cbData == 4 && Type == 4 )
      {
        v2 = *(_DWORD *)Data;
        goto LABEL_19;
      }
      LOBYTE(v17) = -14;
    }
  }
  else
  {
    LOBYTE(v17) = 87;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    v25 = 12;
    v26 = L"DisableUnConstrainedQueries";
    goto LABEL_44;
  }
LABEL_19:
  v21 = v2 != 0;
  if ( *(_DWORD *)(a1 + 116) != v21 )
  {
    *(_DWORD *)(a1 + 116) = v21;
    v3 = 1;
    v23 = *(_DWORD *)(a1 + 68);
    if ( v2 )
      v24 = v23 | 0x10000000;
    else
      v24 = v23 & 0xEFFFFFFF;
    *(_DWORD *)(a1 + 68) = v24;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18003d614  mov     [rsp-8+arg_8], rbx
0x18003d619  mov     [rsp-8+arg_10], rsi
0x18003d61e  push    rbp
0x18003d61f  push    rdi
0x18003d620  push    r12
0x18003d622  push    r14
0x18003d624  push    r15
0x18003d626  lea     rbp, [rsp-180h]
0x18003d62e  sub     rsp, 280h
0x18003d635  mov     rax, cs:__security_cookie
0x18003d63c  xor     rax, rsp
0x18003d63f  mov     [rbp+1A0h+var_30], rax
0x18003d646  xor     r12d, r12d
0x18003d649  mov     rdi, rcx
0x18003d64c  mov     ebx, 20Ah
0x18003d651  mov     [rsp+2A0h+var_260], r12
0x18003d656  mov     r8d, ebx; Size
0x18003d659  lea     rcx, [rsp+2A0h+var_240]; void *
0x18003d65e  xor     edx, edx; Val
0x18003d660  mov     esi, r12d
0x18003d663  mov     r15d, r12d
0x18003d666  call    memset_0
0x18003d66b  mov     [rsp+2A0h+hKey], r12
0x18003d670  mov     [rsp+2A0h+Type], r12d
0x18003d675  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003d67c  lea     rcx, aInterfacespeci; "InterfaceSpecificParameters"
0x18003d683  lea     r14, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18003d68a  jnz     loc_18003D95F
0x18003d690  lea     rax, [rsp+2A0h+Type]
0x18003d695  xor     r9d, r9d
0x18003d698  mov     [rsp+2A0h+var_270], rax
0x18003d69d  lea     rcx, aDnscache_1; "Dnscache"
0x18003d6a4  lea     rax, [rsp+2A0h+var_240]
0x18003d6a9  mov     dword ptr [rsp+2A0h+lpcbData], ebx
0x18003d6ad  mov     r8, r14
0x18003d6b0  mov     [rsp+2A0h+phkResult], rax
0x18003d6b5  xor     edx, edx
0x18003d6b7  call    cs:__imp_RtlGetPersistedStateLocation
0x18003d6be  nop     dword ptr [rax+rax+00h]
0x18003d6c3  mov     r14d, eax
0x18003d6c6  test    eax, eax
0x18003d6c8  js      loc_18003D9B0
0x18003d6ce  sub     ebx, [rsp+2A0h+Type]
0x18003d6d2  lea     r8, [rsp+2A0h+var_240]
0x18003d6d7  mov     eax, [rsp+2A0h+Type]
0x18003d6db  shr     rax, 1
0x18003d6de  mov     edx, ebx
0x18003d6e0  shr     rdx, 1
0x18003d6e3  lea     r8, [r8+rax*2]
0x18003d6e7  mov     word ptr [r8-2], 5Ch ; '\'
0x18003d6ee  jz      loc_18003DA2E
0x18003d6f4  lea     r10, aInterfacespeci; "InterfaceSpecificParameters"
0x18003d6fb  mov     eax, 7FFFFFFEh
0x18003d700  mov     rcx, r10
0x18003d703  test    rax, rax
0x18003d706  jz      short loc_18003D727
0x18003d708  movzx   r9d, word ptr [rcx]
0x18003d70c  test    r9w, r9w
0x18003d710  jz      short loc_18003D727
0x18003d712  mov     [r8], r9w
0x18003d716  add     rcx, 2
0x18003d71a  add     r8, 2
0x18003d71e  dec     rax
0x18003d721  sub     rdx, 1
0x18003d725  jnz     short loc_18003D703
0x18003d727  mov     rax, rdx
0x18003d72a  lea     rcx, [r8-2]
0x18003d72e  neg     rax
0x18003d731  sbb     ebx, ebx
0x18003d733  test    rdx, rdx
0x18003d736  not     ebx
0x18003d738  cmovnz  rcx, r8
0x18003d73c  mov     [rcx], r12w
0x18003d740  and     ebx, 8007007Ah
0x18003d746  js      loc_18003D9F1
0x18003d74c  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003d753  jnz     loc_18003D90D
0x18003d759  mov     r14d, 20019h
0x18003d75f  test    ebx, ebx
0x18003d761  jns     loc_18003D81B
0x18003d767  mov     ecx, ebx
0x18003d769  call    WX_WIN32_FROM_HR
0x18003d76e  test    eax, eax
0x18003d770  jnz     loc_18003DA1C
0x18003d776  mov     rdx, [rdi]; lpSubKey
0x18003d779  lea     rax, [rsp+2A0h+var_260]
0x18003d77e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18003d783  mov     r9d, r14d; samDesired
0x18003d786  xor     r8d, r8d; ulOptions
0x18003d789  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18003d78e  call    cs:__imp_RegOpenKeyExW
0x18003d795  nop     dword ptr [rax+rax+00h]
0x18003d79a  test    eax, eax
0x18003d79c  jz      loc_18003D84D
0x18003d7a2  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18003d7a9  jnz     loc_18003DA35
0x18003d7af  test    esi, esi
0x18003d7b1  mov     eax, r12d
0x18003d7b4  setnz   al
0x18003d7b7  cmp     [rdi+74h], eax
0x18003d7ba  jnz     loc_18003D8CE
0x18003d7c0  mov     rcx, [rsp+2A0h+var_260]; hKey
0x18003d7c5  test    rcx, rcx
0x18003d7c8  jz      short loc_18003D7D6
0x18003d7ca  call    cs:__imp_RegCloseKey
0x18003d7d1  nop     dword ptr [rax+rax+00h]
0x18003d7d6  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18003d7db  test    rcx, rcx
0x18003d7de  jz      short loc_18003D7EC
0x18003d7e0  call    cs:__imp_RegCloseKey
0x18003d7e7  nop     dword ptr [rax+rax+00h]
0x18003d7ec  mov     eax, r15d
0x18003d7ef  mov     rcx, [rbp+1A0h+var_30]
0x18003d7f6  xor     rcx, rsp; StackCookie
0x18003d7f9  call    __security_check_cookie
0x18003d7fe  lea     r11, [rsp+2A0h+var_20]
0x18003d806  mov     rbx, [r11+38h]
0x18003d80a  mov     rsi, [r11+40h]
0x18003d80e  mov     rsp, r11
0x18003d811  pop     r15
0x18003d813  pop     r14
0x18003d815  pop     r12
0x18003d817  pop     rdi
0x18003d818  pop     rbp
0x18003d819  retn
0x18003d81b  lea     rax, [rsp+2A0h+hKey]
0x18003d820  mov     [rsp+2A0h+lpcbData], r12
0x18003d825  mov     r9d, r14d
0x18003d828  mov     [rsp+2A0h+phkResult], rax
0x18003d82d  xor     r8d, r8d
0x18003d830  lea     rdx, [rsp+2A0h+var_240]
0x18003d835  mov     rcx, 0FFFFFFFF80000002h
0x18003d83c  call    cs:__imp_RegOpenKeyExInternalW
0x18003d843  nop     dword ptr [rax+rax+00h]
0x18003d848  jmp     loc_18003D76E
0x18003d84d  mov     rcx, [rsp+2A0h+var_260]; hKey
0x18003d852  mov     rbx, cs:lpValueName
0x18003d859  mov     dword ptr [rsp+2A0h+Data], r12d
0x18003d85e  mov     [rsp+2A0h+Type], r12d
0x18003d863  mov     [rsp+2A0h+cbData], 4
0x18003d86b  test    rcx, rcx
0x18003d86e  jz      loc_18003DA5B
0x18003d874  test    rbx, rbx
0x18003d877  jz      loc_18003DA5B
0x18003d87d  lea     rax, [rsp+2A0h+cbData]
0x18003d882  xor     r8d, r8d; lpReserved
0x18003d885  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18003d88a  lea     r9, [rsp+2A0h+Type]; lpType
0x18003d88f  lea     rax, [rsp+2A0h+Data]
0x18003d894  mov     rdx, rbx; lpValueName
0x18003d897  mov     [rsp+2A0h+phkResult], rax; lpData
0x18003d89c  call    cs:__imp_RegQueryValueExW
0x18003d8a3  nop     dword ptr [rax+rax+00h]
0x18003d8a8  test    eax, eax
0x18003d8aa  jz      short loc_18003D8B7
0x18003d8ac  cmp     eax, 2
0x18003d8af  jz      loc_18003D7AF
0x18003d8b5  jmp     short loc_18003D8F3
0x18003d8b7  cmp     [rsp+2A0h+cbData], 4
0x18003d8bc  jnz     short loc_18003D8EE
0x18003d8be  cmp     [rsp+2A0h+Type], 4
0x18003d8c3  jnz     short loc_18003D8EE
0x18003d8c5  mov     esi, dword ptr [rsp+2A0h+Data]
0x18003d8c9  jmp     loc_18003D7AF
0x18003d8ce  mov     [rdi+74h], eax
0x18003d8d1  mov     r15d, 1
0x18003d8d7  mov     eax, [rdi+44h]
0x18003d8da  test    esi, esi
0x18003d8dc  jz      loc_18003D988
0x18003d8e2  bts     eax, 1Ch
0x18003d8e6  mov     [rdi+44h], eax
0x18003d8e9  jmp     loc_18003D7C0
0x18003d8ee  mov     eax, 3F2h
0x18003d8f3  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18003d8fa  jz      loc_18003D7AF
0x18003d900  mov     edx, 0Ch
0x18003d905  mov     r9, rbx
0x18003d908  jmp     loc_18003D99B
0x18003d90d  lea     rax, [rsp+2A0h+var_240]
0x18003d912  mov     [rsp+2A0h+var_270], rax
0x18003d917  lea     r9, aDnscache_1; "Dnscache"
0x18003d91e  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18003d925  mov     [rsp+2A0h+lpcbData], r10
0x18003d92a  mov     [rsp+2A0h+phkResult], rax
0x18003d92f  call    WPP_SF_SSSS
0x18003d934  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003d93b  jz      loc_18003D759
0x18003d941  mov     edx, 0Eh
0x18003d946  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18003d94d  mov     ecx, 41Dh
0x18003d952  mov     r9d, ebx
0x18003d955  call    WPP_SF_d
0x18003d95a  jmp     loc_18003D759
0x18003d95f  mov     [rsp+2A0h+var_268], ebx
0x18003d963  lea     rax, [rsp+2A0h+var_240]
0x18003d968  mov     [rsp+2A0h+var_270], rax
0x18003d96d  lea     r9, aDnscache_1; "Dnscache"
0x18003d974  mov     [rsp+2A0h+lpcbData], rcx
0x18003d979  mov     [rsp+2A0h+phkResult], r14
0x18003d97e  call    WPP_SF_SSSqd
0x18003d983  jmp     loc_18003D690
0x18003d988  btr     eax, 1Ch
0x18003d98c  jmp     loc_18003D8E6
0x18003d991  mov     edx, 0Ah
0x18003d996  lea     r9, [rsp+2A0h+var_240]
0x18003d99b  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x18003d9a2  mov     dword ptr [rsp+2A0h+phkResult], eax
0x18003d9a6  call    WPP_SF_SD
0x18003d9ab  jmp     loc_18003D7AF
0x18003d9b0  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003d9b7  jz      short loc_18003D9E2
0x18003d9b9  lea     r10, aInterfacespeci; "InterfaceSpecificParameters"
0x18003d9c0  mov     dword ptr [rsp+2A0h+var_270], r14d
0x18003d9c5  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18003d9cc  mov     [rsp+2A0h+lpcbData], r10
0x18003d9d1  lea     r9, aDnscache_1; "Dnscache"
0x18003d9d8  mov     [rsp+2A0h+phkResult], rax
0x18003d9dd  call    WPP_SF_SSSd
0x18003d9e2  mov     ecx, r14d; int
0x18003d9e5  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x18003d9ea  mov     ebx, eax
0x18003d9ec  jmp     loc_18003D934
0x18003d9f1  mov     r9d, ebx
0x18003d9f4  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003d9fb  jz      loc_18003D759
0x18003da01  mov     edx, 0Ch
0x18003da06  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18003da0d  mov     ecx, 41Dh
0x18003da12  call    WPP_SF_d
0x18003da17  jmp     loc_18003D934
0x18003da1c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18003da23  jz      loc_18003D7AF
0x18003da29  jmp     loc_18003D991
0x18003da2e  mov     ebx, 80070057h
0x18003da33  jmp     short loc_18003D9F1
0x18003da35  mov     r9, [rdi+78h]
0x18003da39  lea     r8, WPP_c97ed51ec62b33947f153285c0abcdba_Traceguids
0x18003da40  mov     dword ptr [rsp+2A0h+lpcbData], eax
0x18003da44  mov     edx, 158h
0x18003da49  mov     rax, [rdi]
0x18003da4c  mov     [rsp+2A0h+phkResult], rax
0x18003da51  call    WPP_SF_SSD
0x18003da56  jmp     loc_18003D7AF
0x18003da5b  mov     eax, 57h ; 'W'
0x18003da60  jmp     loc_18003D8F3
```
