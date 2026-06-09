# DnsGetNrptRuleNamesList

- ea: `0x1800174b0`
- end: `0x1800178f9`
- name: `DnsGetNrptRuleNamesList`
- size: `1097`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800174b0`
- `0x180017e00`
- `0x180029d80`
- `0x18003de30`
- `0x180076130`
- `0x18007f24c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800cccb0`
- `0x1800dbb48`
- `0x1800dc4ac`
- `0x1800dc670`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001776a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001776a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017668`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017668`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001763c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001763c`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001757b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001757b`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x1800176c4`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x1800176c4`

## string_xrefs

- `0x180017537`: `Parameters\DnsPolicyConfig`
- `0x18001759d`: `Parameters\DnsPolicyConfig`
- `0x1800177b1`: `Parameters\DnsPolicyConfig`
- `0x18001754c`: `Dnscache`
- `0x180017545`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x1800177bc`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18001781a`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsGetNrptRuleNamesList(__int64 *a1, DWORD *a2)
{
  __int64 v4; // rdi
  int v5; // edx
  int v6; // r8d
  int PersistedStateLocation; // eax
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // edi
  size_t v12; // rdx
  wchar_t *v13; // rcx
  HRESULT v14; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  __int64 v18; // r10
  int v19; // ebx
  unsigned int v20; // eax
  int v21; // ecx
  unsigned int v22; // ebx
  unsigned int v23; // eax
  DWORD i; // esi
  DWORD v26; // eax
  WCHAR *v27; // rax
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r9
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxSubKeyLen[4]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v36[264]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  v32 = 0;
  v4 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen[0] = 0;
  cchName = 0;
  if ( a1 && a2 )
  {
    *a1 = 0;
    *a2 = 0;
    memset_0(v36, 0, 0x20Au);
    LODWORD(v32) = 0;
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      WPP_SF_SSSqd(
        (unsigned int)L"Parameters\\DnsPolicyConfig",
        v5,
        v6,
        (unsigned int)L"Dnscache",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
        (__int64)L"Parameters\\DnsPolicyConfig",
        (__int64)v36,
        10);
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"Dnscache",
                               0,
                               L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                               0,
                               v36,
                               522,
                               &v32);
    v11 = PersistedStateLocation;
    if ( PersistedStateLocation < 0 )
    {
      if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
        WPP_SF_SSSd(
          v9,
          v8,
          v10,
          (unsigned int)L"Dnscache",
          (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
          (__int64)L"Parameters\\DnsPolicyConfig",
          PersistedStateLocation);
      v19 = HRESULT_FROM_NTSTATUS(v11);
    }
    else
    {
      v12 = (unsigned int)(522 - v32);
      v13 = &v36[(unsigned __int64)(unsigned int)v32 >> 1];
      *(v13 - 1) = 92;
      v14 = StringCbCopyW(v13, v12, L"Parameters\\DnsPolicyConfig");
      v19 = v14;
      if ( v14 < 0 )
      {
        if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
          WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v14);
      }
      else if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      {
        WPP_SF_SSSS(
          v16,
          v15,
          v17,
          (unsigned int)L"Dnscache",
          (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
          v18,
          (__int64)v36);
      }
    }
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v19);
    if ( v19 >= 0 )
      v20 = RegOpenKeyExInternalW(-2147483646, v36, 0, 9, &hKey, 0);
    else
      v20 = WX_WIN32_FROM_HR((unsigned int)v19);
    v22 = v20;
    if ( v20 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_16;
      WPP_SF_SD(v21, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v36, v20);
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_16;
      v29 = 12;
      v30 = v22;
    }
    else
    {
      v23 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      v22 = v23;
      if ( !v23 )
      {
        if ( !cSubKeys )
          goto LABEL_16;
        v32 = Dns_Allocate(8LL * cSubKeys);
        v4 = v32;
        if ( v32 )
        {
          v22 = 0;
          for ( i = 0; ; ++i )
          {
            v26 = cSubKeys;
            if ( i >= cSubKeys )
            {
              *a1 = v4;
              *a2 = v26;
              goto LABEL_16;
            }
            cchName = cbMaxSubKeyLen[0] + 1;
            v27 = (WCHAR *)Dns_Allocate(2LL * (cbMaxSubKeyLen[0] + 1));
            *(_QWORD *)(v4 + 8LL * i) = v27;
            if ( !v27 )
              goto LABEL_42;
            v28 = RegEnumKeyExW(hKey, i, v27, &cchName, 0, 0, 0, 0);
            v22 = v28;
            if ( v28 )
              break;
          }
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_d(1035, 14, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids, v28);
        }
        else
        {
LABEL_42:
          v22 = 14;
        }
        goto LABEL_21;
      }
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_16;
      v29 = 13;
      v30 = v23;
    }
    WPP_SF_d(1035, v29, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids, v30);
    goto LABEL_16;
  }
  v22 = 87;
LABEL_21:
  if ( v4 )
    DnsFreeNrptRuleNamesList(&v32, cSubKeys);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v22;
}

```

## disassembly

```asm
0x1800174b0  mov     [rsp-8+arg_10], rbx
0x1800174b5  push    rbp
0x1800174b6  push    rsi
0x1800174b7  push    rdi
0x1800174b8  push    r12
0x1800174ba  push    r13
0x1800174bc  push    r14
0x1800174be  push    r15
0x1800174c0  lea     rbp, [rsp-1B0h]
0x1800174c8  sub     rsp, 2B0h
0x1800174cf  mov     rax, cs:__security_cookie
0x1800174d6  xor     rax, rsp
0x1800174d9  mov     [rbp+1E0h+var_40], rax
0x1800174e0  xor     r12d, r12d
0x1800174e3  mov     r14, rdx
0x1800174e6  mov     [rsp+2E0h+hKey], r12
0x1800174eb  mov     r15, rcx
0x1800174ee  mov     [rsp+2E0h+var_278], r12
0x1800174f3  mov     edi, r12d
0x1800174f6  mov     [rsp+2E0h+cSubKeys], r12d
0x1800174fb  mov     [rbp+1E0h+cbMaxSubKeyLen], r12d
0x1800174ff  mov     [rsp+2E0h+cchName], r12d
0x180017504  test    rcx, rcx
0x180017507  jz      loc_1800176D5
0x18001750d  test    rdx, rdx
0x180017510  jz      loc_1800176D5
0x180017516  mov     [rcx], r12
0x180017519  mov     ebx, 20Ah
0x18001751e  mov     [rdx], r12d
0x180017521  lea     rcx, [rbp+1E0h+var_250]; void *
0x180017525  mov     r8d, ebx; Size
0x180017528  xor     edx, edx; Val
0x18001752a  call    memset_0
0x18001752f  mov     dword ptr [rsp+2E0h+var_278], r12d
0x180017534  mov     sil, 20h ; ' '
0x180017537  lea     rcx, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x18001753e  test    byte ptr cs:xmmword_1801119E0+3, sil
0x180017545  lea     rdi, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18001754c  lea     r13, aDnscache_1; "Dnscache"
0x180017553  jnz     loc_180017784
0x180017559  lea     rax, [rsp+2E0h+var_278]
0x18001755e  xor     r9d, r9d
0x180017561  mov     [rsp+2E0h+lpcbMaxClassLen], rax
0x180017566  mov     r8, rdi
0x180017569  lea     rax, [rbp+1E0h+var_250]
0x18001756d  mov     dword ptr [rsp+2E0h+lpcbMaxSubKeyLen], ebx
0x180017571  xor     edx, edx
0x180017573  mov     [rsp+2E0h+lpcSubKeys], rax
0x180017578  mov     rcx, r13
0x18001757b  call    cs:__imp_RtlGetPersistedStateLocation
0x180017582  nop     dword ptr [rax+rax+00h]
0x180017587  mov     edi, eax
0x180017589  test    eax, eax
0x18001758b  js      loc_1800177A8
0x180017591  mov     eax, dword ptr [rsp+2E0h+var_278]
0x180017595  lea     rcx, [rbp+1E0h+var_250]
0x180017599  sub     ebx, dword ptr [rsp+2E0h+var_278]
0x18001759d  lea     r10, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x1800175a4  shr     rax, 1
0x1800175a7  mov     r8, r10; pszSrc
0x1800175aa  mov     edx, ebx; cbDest
0x1800175ac  lea     rcx, [rcx+rax*2]; pszDest
0x1800175b0  mov     word ptr [rcx-2], 5Ch ; '\'
0x1800175b6  call    StringCbCopyW
0x1800175bb  mov     ebx, eax
0x1800175bd  test    eax, eax
0x1800175bf  js      loc_1800177E3
0x1800175c5  test    byte ptr cs:xmmword_1801119E0+3, sil
0x1800175cc  jnz     loc_18001780E
0x1800175d2  test    byte ptr cs:xmmword_1801119E0+3, sil
0x1800175d9  mov     r13d, 0Eh
0x1800175df  jnz     loc_180017835
0x1800175e5  test    ebx, ebx
0x1800175e7  jns     loc_1800176A1
0x1800175ed  mov     ecx, ebx
0x1800175ef  call    WX_WIN32_FROM_HR
0x1800175f4  mov     ebx, eax
0x1800175f6  test    eax, eax
0x1800175f8  jnz     loc_18001788D
0x1800175fe  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180017603  lea     rax, [rbp+1E0h+cbMaxSubKeyLen]
0x180017607  mov     [rsp+2E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001760c  xor     r9d, r9d; lpReserved
0x18001760f  mov     [rsp+2E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180017614  xor     r8d, r8d; lpcchClass
0x180017617  mov     [rsp+2E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18001761c  xor     edx, edx; lpClass
0x18001761e  mov     [rsp+2E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180017623  mov     [rsp+2E0h+lpcValues], r12; lpcValues
0x180017628  mov     [rsp+2E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18001762d  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180017632  lea     rax, [rsp+2E0h+cSubKeys]
0x180017637  mov     [rsp+2E0h+lpcSubKeys], rax; lpcSubKeys
0x18001763c  call    cs:__imp_RegQueryInfoKeyW
0x180017643  nop     dword ptr [rax+rax+00h]
0x180017648  mov     ebx, eax
0x18001764a  test    eax, eax
0x18001764c  jnz     loc_18001789D
0x180017652  mov     eax, [rsp+2E0h+cSubKeys]
0x180017656  test    eax, eax
0x180017658  jnz     loc_1800176F6
0x18001765e  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180017663  test    rcx, rcx
0x180017666  jz      short loc_180017674
0x180017668  call    cs:__imp_RegCloseKey
0x18001766f  nop     dword ptr [rax+rax+00h]
0x180017674  mov     eax, ebx
0x180017676  mov     rcx, [rbp+1E0h+var_40]
0x18001767d  xor     rcx, rsp; StackCookie
0x180017680  call    __security_check_cookie
0x180017685  mov     rbx, [rsp+2E0h+arg_10]
0x18001768d  add     rsp, 2B0h
0x180017694  pop     r15
0x180017696  pop     r14
0x180017698  pop     r13
0x18001769a  pop     r12
0x18001769c  pop     rdi
0x18001769d  pop     rsi
0x18001769e  pop     rbp
0x18001769f  retn
0x1800176a1  lea     rax, [rsp+2E0h+hKey]
0x1800176a6  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r12
0x1800176ab  mov     r9d, 9
0x1800176b1  mov     [rsp+2E0h+lpcSubKeys], rax
0x1800176b6  xor     r8d, r8d
0x1800176b9  lea     rdx, [rbp+1E0h+var_250]
0x1800176bd  mov     rcx, 0FFFFFFFF80000002h
0x1800176c4  call    cs:__imp_RegOpenKeyExInternalW
0x1800176cb  nop     dword ptr [rax+rax+00h]
0x1800176d0  jmp     loc_1800175F4
0x1800176d5  mov     ebx, 57h ; 'W'
0x1800176da  test    rdi, rdi
0x1800176dd  jz      loc_18001765E
0x1800176e3  mov     edx, [rsp+2E0h+cSubKeys]
0x1800176e7  lea     rcx, [rsp+2E0h+var_278]
0x1800176ec  call    DnsFreeNrptRuleNamesList
0x1800176f1  jmp     loc_18001765E
0x1800176f6  mov     rcx, rax
0x1800176f9  shl     rcx, 3
0x1800176fd  call    Dns_Allocate
0x180017702  mov     [rsp+2E0h+var_278], rax
0x180017707  mov     rdi, rax
0x18001770a  test    rax, rax
0x18001770d  jz      loc_1800178C8
0x180017713  mov     ebx, r12d
0x180017716  mov     esi, r12d
0x180017719  mov     eax, [rsp+2E0h+cSubKeys]
0x18001771d  cmp     esi, eax
0x18001771f  jnb     loc_180017851
0x180017725  mov     eax, [rbp+1E0h+cbMaxSubKeyLen]
0x180017728  inc     eax
0x18001772a  mov     ecx, eax
0x18001772c  add     rcx, rcx
0x18001772f  mov     [rsp+2E0h+cchName], eax
0x180017733  call    Dns_Allocate
0x180017738  mov     ecx, esi
0x18001773a  mov     [rdi+rcx*8], rax
0x18001773e  test    rax, rax
0x180017741  jz      loc_1800178C8
0x180017747  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001774c  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180017751  mov     [rsp+2E0h+lpcValues], r12; lpftLastWriteTime
0x180017756  mov     r8, rax; lpName
0x180017759  mov     [rsp+2E0h+lpcbMaxClassLen], r12; lpcchClass
0x18001775e  mov     edx, esi; dwIndex
0x180017760  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r12; lpClass
0x180017765  mov     [rsp+2E0h+lpcSubKeys], r12; lpReserved
0x18001776a  call    cs:__imp_RegEnumKeyExW
0x180017771  nop     dword ptr [rax+rax+00h]
0x180017776  mov     ebx, eax
0x180017778  test    eax, eax
0x18001777a  jnz     loc_1800178D0
0x180017780  inc     esi
0x180017782  jmp     short loc_180017719
0x180017784  mov     dword ptr [rsp+2E0h+lpcValues], ebx
0x180017788  lea     rax, [rbp+1E0h+var_250]
0x18001778c  mov     [rsp+2E0h+lpcbMaxClassLen], rax
0x180017791  mov     r9, r13
0x180017794  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rcx
0x180017799  mov     [rsp+2E0h+lpcSubKeys], rdi
0x18001779e  call    WPP_SF_SSSqd
0x1800177a3  jmp     loc_180017559
0x1800177a8  test    byte ptr cs:xmmword_1801119E0+3, sil
0x1800177af  jz      short loc_1800177D5
0x1800177b1  lea     r10, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x1800177b8  mov     dword ptr [rsp+2E0h+lpcbMaxClassLen], edi
0x1800177bc  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800177c3  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r10
0x1800177c8  mov     r9, r13
0x1800177cb  mov     [rsp+2E0h+lpcSubKeys], rax
0x1800177d0  call    WPP_SF_SSSd
0x1800177d5  mov     ecx, edi; int
0x1800177d7  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x1800177dc  mov     ebx, eax
0x1800177de  jmp     loc_1800175D2
0x1800177e3  test    byte ptr cs:xmmword_1801119E0+3, sil
0x1800177ea  jz      loc_1800175D2
0x1800177f0  mov     edx, 0Ch
0x1800177f5  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x1800177fc  mov     ecx, 41Dh
0x180017801  mov     r9d, eax
0x180017804  call    WPP_SF_d
0x180017809  jmp     loc_1800175D2
0x18001780e  lea     rax, [rbp+1E0h+var_250]
0x180017812  mov     r9, r13
0x180017815  mov     [rsp+2E0h+lpcbMaxClassLen], rax
0x18001781a  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180017821  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r10
0x180017826  mov     [rsp+2E0h+lpcSubKeys], rax
0x18001782b  call    WPP_SF_SSSS
0x180017830  jmp     loc_1800175D2
0x180017835  mov     edx, r13d
0x180017838  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18001783f  mov     ecx, 41Dh
0x180017844  mov     r9d, ebx
0x180017847  call    WPP_SF_d
0x18001784c  jmp     loc_1800175E5
0x180017851  mov     [r15], rdi
0x180017854  mov     [r14], eax
0x180017857  jmp     loc_18001765E
0x18001785c  mov     edx, 0Ah
0x180017861  mov     dword ptr [rsp+2E0h+lpcSubKeys], ebx
0x180017865  lea     r9, [rbp+1E0h+var_250]
0x180017869  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x180017870  call    WPP_SF_SD
0x180017875  mov     al, byte ptr cs:xmmword_1801119E0+1
0x18001787b  test    al, 8
0x18001787d  jz      loc_18001765E
0x180017883  mov     edx, 0Ch
0x180017888  mov     r9d, ebx
0x18001788b  jmp     short loc_1800178B2
0x18001788d  mov     al, byte ptr cs:xmmword_1801119E0+1
0x180017893  test    al, 8
0x180017895  jz      loc_18001765E
0x18001789b  jmp     short loc_18001785C
0x18001789d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800178a4  jz      loc_18001765E
0x1800178aa  mov     edx, 0Dh
0x1800178af  mov     r9d, eax
0x1800178b2  mov     ecx, 40Bh
0x1800178b7  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x1800178be  call    WPP_SF_d
0x1800178c3  jmp     loc_18001765E
0x1800178c8  mov     ebx, r13d
0x1800178cb  jmp     loc_1800176DA
0x1800178d0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800178d7  jz      loc_1800176DA
0x1800178dd  mov     edx, r13d
0x1800178e0  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x1800178e7  mov     ecx, 40Bh
0x1800178ec  mov     r9d, eax
0x1800178ef  call    WPP_SF_d
0x1800178f4  jmp     loc_1800176DA
```
