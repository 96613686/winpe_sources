# DnsRemoveNrptRule

- ea: `0x1800171c0`
- end: `0x18001749c`
- name: `DnsRemoveNrptRule`
- size: `732`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800171c0`
- `0x180017e00`
- `0x18003de30`
- `0x18007f24c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800cccb0`
- `0x1800dbb48`
- `0x1800dbfe0`
- `0x1800dc4ac`
- `0x1800dc670`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017451`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017451`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180017414`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180017414`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800172a7`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800172a7`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x1800173d4`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x1800173d4`

## string_xrefs

- `0x18001724c`: `Parameters\DnsPolicyConfig`
- `0x1800172c6`: `Parameters\DnsPolicyConfig`
- `0x180017305`: `Parameters\DnsPolicyConfig`
- `0x18001726a`: `Dnscache`
- `0x18001728d`: `Dnscache`
- `0x1800172d9`: `Dnscache`
- `0x180017360`: `Dnscache`
- `0x180017253`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x1800172cd`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x180017367`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsRemoveNrptRule(LPCWSTR lpSubKey)
{
  const WCHAR *v1; // rdi
  unsigned int v2; // ebx
  int v3; // edx
  int v4; // r8d
  int PersistedStateLocation; // eax
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  int v9; // esi
  int v10; // ebx
  size_t v11; // rdx
  wchar_t *v12; // rcx
  HRESULT v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // r10
  unsigned int v18; // eax
  int v19; // ecx
  LSTATUS v20; // eax
  int v21; // ecx
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v25[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  v1 = lpSubKey;
  if ( !lpSubKey )
  {
    v2 = 87;
    goto LABEL_29;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_S(1035, 15, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids, lpSubKey);
  memset_0(v25, 0, 0x20Au);
  hKey = 0;
  v23 = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_SSSqd(
      (unsigned int)L"Parameters\\DnsPolicyConfig",
      v3,
      v4,
      (unsigned int)L"Dnscache",
      (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
      (__int64)L"Parameters\\DnsPolicyConfig",
      (__int64)v25,
      10);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"Dnscache",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                             0,
                             v25,
                             522,
                             &v23);
  v9 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      WPP_SF_SSSd(
        v7,
        v6,
        v8,
        (unsigned int)L"Dnscache",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
        (__int64)L"Parameters\\DnsPolicyConfig",
        PersistedStateLocation);
    v10 = HRESULT_FROM_NTSTATUS(v9);
    goto LABEL_16;
  }
  v11 = 522 - v23;
  v12 = &v25[(unsigned __int64)v23 >> 1];
  *(v12 - 1) = 92;
  v13 = StringCbCopyW(v12, v11, L"Parameters\\DnsPolicyConfig");
  v10 = v13;
  if ( v13 >= 0 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    {
      WPP_SF_SSSS(
        v15,
        v14,
        v16,
        (unsigned int)L"Dnscache",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
        v17,
        (__int64)v25);
LABEL_16:
      if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
        WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v10);
    }
  }
  else if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
  {
    WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v13);
    goto LABEL_16;
  }
  if ( v10 >= 0 )
    v18 = RegOpenKeyExInternalW(-2147483646, v25, 0, 131097, &hKey, 0);
  else
    v18 = WX_WIN32_FROM_HR((unsigned int)v10);
  v2 = v18;
  if ( v18 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_SD(v19, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v25, v18);
  }
  else
  {
    v20 = RegDeleteKeyExW(hKey, v1, 0, 0);
    v2 = v20;
    if ( v20 && (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_SD(v21, 16, (unsigned int)WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids, (_DWORD)v1, v20);
  }
  LODWORD(lpSubKey) = (_DWORD)hKey;
  if ( hKey )
    RegCloseKey(hKey);
LABEL_29:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_SD((_DWORD)lpSubKey, 17, (unsigned int)WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids, (_DWORD)v1, v2);
  return v2;
}

```

## disassembly

```asm
0x1800171c0  push    rbp
0x1800171c2  push    rbx
0x1800171c3  push    rsi
0x1800171c4  push    rdi
0x1800171c5  lea     rbp, [rsp-178h]
0x1800171cd  sub     rsp, 278h
0x1800171d4  mov     rax, cs:__security_cookie
0x1800171db  xor     rax, rsp
0x1800171de  mov     [rbp+190h+var_30], rax
0x1800171e5  mov     [rsp+290h+hKey], 0
0x1800171ee  mov     rdi, rcx
0x1800171f1  test    rcx, rcx
0x1800171f4  jnz     short loc_1800171FE
0x1800171f6  lea     ebx, [rcx+57h]
0x1800171f9  jmp     loc_18001745D
0x1800171fe  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180017205  jz      short loc_180017220
0x180017207  mov     edx, 0Fh
0x18001720c  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x180017213  mov     ecx, 40Bh
0x180017218  mov     r9, rdi
0x18001721b  call    WPP_SF_S
0x180017220  mov     ebx, 20Ah
0x180017225  lea     rcx, [rsp+290h+var_240]; void *
0x18001722a  mov     r8d, ebx; Size
0x18001722d  xor     edx, edx; Val
0x18001722f  call    memset_0
0x180017234  mov     [rsp+290h+hKey], 0
0x18001723d  mov     [rsp+290h+var_250], 0
0x180017245  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18001724c  lea     rcx, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x180017253  lea     rsi, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18001725a  jz      short loc_180017280
0x18001725c  mov     [rsp+290h+var_258], ebx
0x180017260  lea     rax, [rsp+290h+var_240]
0x180017265  mov     [rsp+290h+var_260], rax
0x18001726a  lea     r9, aDnscache_1; "Dnscache"
0x180017271  mov     [rsp+290h+var_268], rcx
0x180017276  mov     [rsp+290h+var_270], rsi
0x18001727b  call    WPP_SF_SSSqd
0x180017280  lea     rax, [rsp+290h+var_250]
0x180017285  xor     r9d, r9d
0x180017288  mov     [rsp+290h+var_260], rax
0x18001728d  lea     rcx, aDnscache_1; "Dnscache"
0x180017294  lea     rax, [rsp+290h+var_240]
0x180017299  mov     dword ptr [rsp+290h+var_268], ebx
0x18001729d  mov     r8, rsi
0x1800172a0  mov     [rsp+290h+var_270], rax
0x1800172a5  xor     edx, edx
0x1800172a7  call    cs:__imp_RtlGetPersistedStateLocation
0x1800172ae  nop     dword ptr [rax+rax+00h]
0x1800172b3  mov     esi, eax
0x1800172b5  test    eax, eax
0x1800172b7  jns     short loc_1800172F8
0x1800172b9  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x1800172c0  jz      short loc_1800172EA
0x1800172c2  mov     dword ptr [rsp+290h+var_260], eax
0x1800172c6  lea     r10, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x1800172cd  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800172d4  mov     [rsp+290h+var_268], r10
0x1800172d9  lea     r9, aDnscache_1; "Dnscache"
0x1800172e0  mov     [rsp+290h+var_270], rax
0x1800172e5  call    WPP_SF_SSSd
0x1800172ea  mov     ecx, esi; int
0x1800172ec  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x1800172f1  mov     ebx, eax
0x1800172f3  jmp     loc_18001737D
0x1800172f8  mov     eax, [rsp+290h+var_250]
0x1800172fc  lea     rcx, [rsp+290h+var_240]
0x180017301  sub     ebx, [rsp+290h+var_250]
0x180017305  lea     r10, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x18001730c  shr     rax, 1
0x18001730f  mov     r8, r10; pszSrc
0x180017312  mov     edx, ebx; cbDest
0x180017314  lea     rcx, [rcx+rax*2]; pszDest
0x180017318  mov     word ptr [rcx-2], 5Ch ; '\'
0x18001731e  call    StringCbCopyW
0x180017323  mov     ebx, eax
0x180017325  test    eax, eax
0x180017327  jns     short loc_18001734D
0x180017329  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180017330  jz      short loc_18001739F
0x180017332  mov     edx, 0Ch
0x180017337  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18001733e  mov     ecx, 41Dh
0x180017343  mov     r9d, eax
0x180017346  call    WPP_SF_d
0x18001734b  jmp     short loc_18001737D
0x18001734d  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180017354  jz      short loc_18001739F
0x180017356  lea     rax, [rsp+290h+var_240]
0x18001735b  mov     [rsp+290h+var_260], rax
0x180017360  lea     r9, aDnscache_1; "Dnscache"
0x180017367  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18001736e  mov     [rsp+290h+var_268], r10
0x180017373  mov     [rsp+290h+var_270], rax
0x180017378  call    WPP_SF_SSSS
0x18001737d  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180017384  jz      short loc_18001739F
0x180017386  mov     edx, 0Eh
0x18001738b  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x180017392  mov     ecx, 41Dh
0x180017397  mov     r9d, ebx
0x18001739a  call    WPP_SF_d
0x18001739f  test    ebx, ebx
0x1800173a1  jns     short loc_1800173AC
0x1800173a3  mov     ecx, ebx
0x1800173a5  call    WX_WIN32_FROM_HR
0x1800173aa  jmp     short loc_1800173E0
0x1800173ac  lea     rax, [rsp+290h+hKey]
0x1800173b1  mov     [rsp+290h+var_268], 0
0x1800173ba  mov     r9d, 20019h
0x1800173c0  mov     [rsp+290h+var_270], rax
0x1800173c5  xor     r8d, r8d
0x1800173c8  lea     rdx, [rsp+290h+var_240]
0x1800173cd  mov     rcx, 0FFFFFFFF80000002h
0x1800173d4  call    cs:__imp_RegOpenKeyExInternalW
0x1800173db  nop     dword ptr [rax+rax+00h]
0x1800173e0  mov     ebx, eax
0x1800173e2  test    eax, eax
0x1800173e4  jz      short loc_180017406
0x1800173e6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800173ed  jz      short loc_180017447
0x1800173ef  mov     edx, 0Ah
0x1800173f4  mov     dword ptr [rsp+290h+var_270], eax
0x1800173f8  lea     r9, [rsp+290h+var_240]
0x1800173fd  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x180017404  jmp     short loc_180017442
0x180017406  mov     rcx, [rsp+290h+hKey]; hKey
0x18001740b  xor     r9d, r9d; Reserved
0x18001740e  xor     r8d, r8d; samDesired
0x180017411  mov     rdx, rdi; lpSubKey
0x180017414  call    cs:__imp_RegDeleteKeyExW
0x18001741b  nop     dword ptr [rax+rax+00h]
0x180017420  mov     ebx, eax
0x180017422  test    eax, eax
0x180017424  jz      short loc_180017447
0x180017426  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001742d  jz      short loc_180017447
0x18001742f  mov     edx, 10h
0x180017434  mov     dword ptr [rsp+290h+var_270], eax
0x180017438  mov     r9, rdi
0x18001743b  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x180017442  call    WPP_SF_SD
0x180017447  mov     rcx, [rsp+290h+hKey]; hKey
0x18001744c  test    rcx, rcx
0x18001744f  jz      short loc_18001745D
0x180017451  call    cs:__imp_RegCloseKey
0x180017458  nop     dword ptr [rax+rax+00h]
0x18001745d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180017464  jz      short loc_18001747E
0x180017466  mov     edx, 11h
0x18001746b  mov     dword ptr [rsp+290h+var_270], ebx
0x18001746f  mov     r9, rdi
0x180017472  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x180017479  call    WPP_SF_SD
0x18001747e  mov     eax, ebx
0x180017480  mov     rcx, [rbp+190h+var_30]
0x180017487  xor     rcx, rsp; StackCookie
0x18001748a  call    __security_check_cookie
0x18001748f  add     rsp, 278h
0x180017496  pop     rdi
0x180017497  pop     rsi
0x180017498  pop     rbx
0x180017499  pop     rbp
0x18001749a  retn
```
