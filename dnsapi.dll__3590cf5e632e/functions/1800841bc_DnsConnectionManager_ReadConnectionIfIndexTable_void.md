# DnsConnectionManager::ReadConnectionIfIndexTable(void)

- ea: `0x1800841bc`
- end: `0x180084513`
- name: `?ReadConnectionIfIndexTable@DnsConnectionManager@@AEAAJXZ`
- size: `855`
- prototype: `__int64 __fastcall(DnsConnectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x180086bf8`

## callees

- `0x1800097e0`
- `0x18004148c`
- `0x1800414fc`
- `0x18005a60c`
- `0x180065520`
- `0x180067dc4`
- `0x1800841bc`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800acce0`
- `0x1800acfdc`
- `0x1800ad4ac`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800843aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800843aa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008440b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008440b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084304`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800844c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800844dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084304`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800844c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800844dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084331`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084331`

## string_xrefs

- `0x180084285`: `Dnscache`
- `0x18008427e`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsConnectionManager::ReadConnectionIfIndexTable(DnsConnectionManager *this)
{
  __int64 v2; // r9
  int v3; // eax
  signed int RegistryString; // ebx
  DWORD v5; // esi
  DWORD v6; // edx
  LSTATUS v7; // eax
  DnsConnectionInterfaceIndexTable *v8; // rcx
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  char *v11; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h]
  _DNS_CONNECTION_IFINDEX_ENTRY v13; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v16; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *String; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  cchName = 261;
  v16 = 0;
  hKey = 0;
  memset_0(SubKey, 0, 0x20Au);
  v18 = 0;
  String = (wchar_t *)&word_1800F66E0;
  v12 = 0;
  v11 = (char *)this + 8;
  v13 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 62, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, this);
  AutoSrw::LockExclusive((AutoSrw *)&v11);
  v3 = CreatePersistedRegistryKeyHelper(
         (__int64)L"Dnscache",
         (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
         (__int64)L"Parameters\\DnsActiveIfs",
         v2,
         0x20019u,
         (__int64)lpClass,
         0,
         &v16);
  RegistryString = v3;
  if ( v3 == 1168 || v3 == 2 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
      WPP_SF_(1054, 63, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids);
    RegistryString = 0;
  }
  else
  {
    if ( v3 > 0 )
      RegistryString = (unsigned __int16)v3 | 0x80070000;
    if ( RegistryString >= 0 )
    {
      v5 = 0;
      v6 = 0;
      while ( !RegEnumKeyExW(v16, v6, SubKey, &cchName, 0, 0, 0, 0) )
      {
        if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
          WPP_SF_S(1054, 64, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, SubKey);
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        v7 = RegOpenKeyExW(v16, SubKey, 0, 0x20019u, &hKey);
        RegistryString = v7;
        if ( v7 > 0 )
          RegistryString = (unsigned __int16)v7 | 0x80070000;
        if ( RegistryString < 0 )
          break;
        CWxString::Empty((CWxString *)&String);
        RegistryString = GetRegistryString(hKey, L"Connection", (struct CWxString *)&String);
        if ( RegistryString < 0 )
          break;
        RegistryString = GetRegistryDword(hKey, L"ActiveInterfaces", &v13.dwIfIndex);
        if ( RegistryString < 0 )
          break;
        if ( (_DWORD)v18 )
          _wcslwr_s(String, (unsigned int)(v18 + 1));
        v8 = (DnsConnectionInterfaceIndexTable *)*((_QWORD *)this + 3);
        v13.pwszConnectionName = String;
        RegistryString = DnsConnectionInterfaceIndexTable::AddConnectionIfIndexEntry(v8, &v13);
        if ( RegistryString < 0 )
          break;
        ++v5;
        v13.pwszConnectionName = 0;
        v6 = v5;
        v13.dwIfIndex = 0;
        cchName = 261;
      }
    }
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 65, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, (unsigned int)RegistryString);
  if ( (_DWORD)v12 )
    AutoSrw::UnlockShared((AutoSrw *)&v11);
  if ( HIDWORD(v12) )
    AutoSrw::UnlockExclusive((AutoSrw *)&v11);
  CWxString::_Release((CWxString *)&String);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v16 )
    RegCloseKey(v16);
  return (unsigned int)RegistryString;
}

```

## disassembly

```asm
0x1800841bc  mov     [rsp-8+arg_8], rbx
0x1800841c1  mov     [rsp-8+arg_10], rsi
0x1800841c6  push    rbp
0x1800841c7  push    rdi
0x1800841c8  push    r14
0x1800841ca  lea     rbp, [rsp-1B0h]
0x1800841d2  sub     rsp, 2B0h
0x1800841d9  mov     rax, cs:__security_cookie
0x1800841e0  xor     rax, rsp
0x1800841e3  mov     [rbp+1C0h+var_20], rax
0x1800841ea  xor     r14d, r14d
0x1800841ed  mov     [rsp+2C0h+cchName], 105h
0x1800841f5  mov     rdi, rcx
0x1800841f8  mov     [rsp+2C0h+var_27C], r14d
0x1800841fd  lea     rcx, [rbp+1C0h+SubKey]; void *
0x180084201  mov     [rsp+2C0h+var_248], r14
0x180084206  xor     edx, edx; Val
0x180084208  mov     [rsp+2C0h+hKey], r14
0x18008420d  mov     r8d, 20Ah; Size
0x180084213  call    memset_0
0x180084218  lea     rax, word_1800F66E0
0x18008421f  mov     [rbp+1C0h+var_238], r14
0x180084223  mov     [rbp+1C0h+String], rax
0x180084227  xorps   xmm0, xmm0
0x18008422a  lea     rax, [rdi+8]
0x18008422e  mov     [rsp+2C0h+var_270], r14
0x180084233  mov     [rsp+2C0h+var_278], rax
0x180084238  movups  xmmword ptr [rsp+2C0h+var_268.pwszConnectionName], xmm0
0x18008423d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180084244  jz      short loc_18008425E
0x180084246  lea     edx, [r14+3Eh]
0x18008424a  mov     ecx, 40Bh
0x18008424f  mov     r9, rdi
0x180084252  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x180084259  call    WPP_SF_q
0x18008425e  lea     rcx, [rsp+2C0h+var_278]; this
0x180084263  call    ?LockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::LockExclusive(void)
0x180084268  lea     rax, [rsp+2C0h+var_248]
0x18008426d  mov     [rsp+2C0h+lpftLastWriteTime], rax
0x180084272  lea     r8, aParametersDnsa; "Parameters\\DnsActiveIfs"
0x180084279  mov     dword ptr [rsp+2C0h+lpcchClass], r14d
0x18008427e  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180084285  lea     rcx, aDnscache_1; "Dnscache"
0x18008428c  mov     dword ptr [rsp+2C0h+phkResult], 20019h
0x180084294  call    CreatePersistedRegistryKeyHelper
0x180084299  mov     ebx, eax
0x18008429b  cmp     eax, 490h
0x1800842a0  jz      loc_180084449
0x1800842a6  cmp     eax, 2
0x1800842a9  jz      loc_180084449
0x1800842af  test    eax, eax
0x1800842b1  jle     short loc_1800842BC
0x1800842b3  movzx   ebx, ax
0x1800842b6  or      ebx, 80070000h
0x1800842bc  test    ebx, ebx
0x1800842be  jns     short loc_1800842CD
0x1800842c0  mov     [rsp+2C0h+var_27C], 59Eh
0x1800842c8  jmp     loc_18008446B
0x1800842cd  mov     esi, r14d
0x1800842d0  xor     edx, edx
0x1800842d2  jmp     loc_1800843E9
0x1800842d7  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800842de  jz      short loc_1800842FA
0x1800842e0  mov     edx, 40h ; '@'
0x1800842e5  lea     r9, [rbp+1C0h+SubKey]
0x1800842e9  mov     ecx, 41Eh
0x1800842ee  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800842f5  call    WPP_SF_S
0x1800842fa  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800842ff  test    rcx, rcx
0x180084302  jz      short loc_180084315
0x180084304  call    cs:__imp_RegCloseKey
0x18008430b  nop     dword ptr [rax+rax+00h]
0x180084310  mov     [rsp+2C0h+hKey], r14
0x180084315  mov     rcx, [rsp+2C0h+var_248]; hKey
0x18008431a  lea     rax, [rsp+2C0h+hKey]
0x18008431f  mov     r9d, 20019h; samDesired
0x180084325  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18008432a  xor     r8d, r8d; ulOptions
0x18008432d  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x180084331  call    cs:__imp_RegOpenKeyExW
0x180084338  nop     dword ptr [rax+rax+00h]
0x18008433d  mov     ebx, eax
0x18008433f  test    eax, eax
0x180084341  jle     short loc_18008434C
0x180084343  movzx   ebx, ax
0x180084346  or      ebx, 80070000h
0x18008434c  test    ebx, ebx
0x18008434e  js      loc_18008443F
0x180084354  lea     rcx, [rbp+1C0h+String]; this
0x180084358  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x18008435d  mov     rcx, [rsp+2C0h+hKey]; hkey
0x180084362  lea     r8, [rbp+1C0h+String]; struct CWxString *
0x180084366  lea     rdx, aConnection; "Connection"
0x18008436d  call    ?GetRegistryString@@YAJPEAUHKEY__@@PEBGPEAVCWxString@@@Z; GetRegistryString(HKEY__ *,ushort const *,CWxString *)
0x180084372  mov     ebx, eax
0x180084374  test    eax, eax
0x180084376  js      loc_180084435
0x18008437c  mov     rcx, [rsp+2C0h+hKey]; hkey
0x180084381  lea     r8, [rsp+2C0h+var_268.dwIfIndex]; unsigned int *
0x180084386  lea     rdx, aActiveinterfac; "ActiveInterfaces"
0x18008438d  call    ?GetRegistryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegistryDword(HKEY__ *,ushort const *,ulong *)
0x180084392  mov     ebx, eax
0x180084394  test    eax, eax
0x180084396  js      loc_18008442B
0x18008439c  mov     eax, dword ptr [rbp+1C0h+var_238]
0x18008439f  test    eax, eax
0x1800843a1  jz      short loc_1800843B6
0x1800843a3  mov     rcx, [rbp+1C0h+String]; String
0x1800843a7  lea     edx, [rax+1]; SizeInWords
0x1800843aa  call    cs:__imp__wcslwr_s
0x1800843b1  nop     dword ptr [rax+rax+00h]
0x1800843b6  mov     rax, [rbp+1C0h+String]
0x1800843ba  lea     rdx, [rsp+2C0h+var_268]; struct _DNS_CONNECTION_IFINDEX_ENTRY *
0x1800843bf  mov     rcx, [rdi+18h]; this
0x1800843c3  mov     [rsp+2C0h+var_268.pwszConnectionName], rax
0x1800843c8  call    ?AddConnectionIfIndexEntry@DnsConnectionInterfaceIndexTable@@QEAAJPEAU_DNS_CONNECTION_IFINDEX_ENTRY@@@Z; DnsConnectionInterfaceIndexTable::AddConnectionIfIndexEntry(_DNS_CONNECTION_IFINDEX_ENTRY *)
0x1800843cd  mov     ebx, eax
0x1800843cf  test    eax, eax
0x1800843d1  js      short loc_180084421
0x1800843d3  inc     esi
0x1800843d5  mov     [rsp+2C0h+var_268.pwszConnectionName], r14
0x1800843da  mov     edx, esi; dwIndex
0x1800843dc  mov     [rsp+2C0h+var_268.dwIfIndex], r14d
0x1800843e1  mov     [rsp+2C0h+cchName], 105h
0x1800843e9  mov     rcx, [rsp+2C0h+var_248]; hKey
0x1800843ee  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x1800843f3  mov     [rsp+2C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800843f8  lea     r8, [rbp+1C0h+SubKey]; lpName
0x1800843fc  mov     [rsp+2C0h+lpcchClass], r14; lpcchClass
0x180084401  mov     [rsp+2C0h+lpClass], r14; lpClass
0x180084406  mov     [rsp+2C0h+phkResult], r14; lpReserved
0x18008440b  call    cs:__imp_RegEnumKeyExW
0x180084412  nop     dword ptr [rax+rax+00h]
0x180084417  test    eax, eax
0x180084419  jz      loc_1800842D7
0x18008441f  jmp     short loc_18008446B
0x180084421  mov     [rsp+2C0h+var_27C], 5CCh
0x180084429  jmp     short loc_18008446B
0x18008442b  mov     [rsp+2C0h+var_27C], 5C2h
0x180084433  jmp     short loc_18008446B
0x180084435  mov     [rsp+2C0h+var_27C], 5BEh
0x18008443d  jmp     short loc_18008446B
0x18008443f  mov     [rsp+2C0h+var_27C], 5B8h
0x180084447  jmp     short loc_18008446B
0x180084449  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x180084450  jz      short loc_180084468
0x180084452  mov     edx, 3Fh ; '?'
0x180084457  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x18008445e  mov     ecx, 41Eh
0x180084463  call    WPP_SF_
0x180084468  mov     ebx, r14d
0x18008446b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180084472  jz      short loc_18008448D
0x180084474  mov     edx, 41h ; 'A'
0x180084479  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x180084480  mov     ecx, 40Bh
0x180084485  mov     r9d, ebx
0x180084488  call    WPP_SF_d
0x18008448d  cmp     dword ptr [rsp+2C0h+var_270], r14d
0x180084492  jz      short loc_18008449E
0x180084494  lea     rcx, [rsp+2C0h+var_278]; this
0x180084499  call    ?UnlockShared@AutoSrw@@QEAAXXZ; AutoSrw::UnlockShared(void)
0x18008449e  cmp     dword ptr [rsp+2C0h+var_270+4], r14d
0x1800844a3  jz      short loc_1800844AF
0x1800844a5  lea     rcx, [rsp+2C0h+var_278]; this
0x1800844aa  call    ?UnlockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::UnlockExclusive(void)
0x1800844af  lea     rcx, [rbp+1C0h+String]; this
0x1800844b3  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800844b8  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800844bd  test    rcx, rcx
0x1800844c0  jz      short loc_1800844D3
0x1800844c2  call    cs:__imp_RegCloseKey
0x1800844c9  nop     dword ptr [rax+rax+00h]
0x1800844ce  mov     [rsp+2C0h+hKey], r14
0x1800844d3  mov     rcx, [rsp+2C0h+var_248]; hKey
0x1800844d8  test    rcx, rcx
0x1800844db  jz      short loc_1800844E9
0x1800844dd  call    cs:__imp_RegCloseKey
0x1800844e4  nop     dword ptr [rax+rax+00h]
0x1800844e9  mov     eax, ebx
0x1800844eb  mov     rcx, [rbp+1C0h+var_20]
0x1800844f2  xor     rcx, rsp; StackCookie
0x1800844f5  call    __security_check_cookie
0x1800844fa  lea     r11, [rsp+2C0h+var_10]
0x180084502  mov     rbx, [r11+28h]
0x180084506  mov     rsi, [r11+30h]
0x18008450a  mov     rsp, r11
0x18008450d  pop     r14
0x18008450f  pop     rdi
0x180084510  pop     rbp
0x180084511  retn
```
