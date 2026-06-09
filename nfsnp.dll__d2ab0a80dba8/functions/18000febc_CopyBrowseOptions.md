# CopyBrowseOptions

- ea: `0x18000febc`
- end: `0x180010308`
- name: `CopyBrowseOptions`
- size: `1100`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000be24`

## callees

- `0x18000190d`
- `0x18000febc`
- `0x180011b62`
- `0x180011b6e`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001003a`
- `msvcrt!wcscpy_s` at `0x180010084`
- `msvcrt!wcscpy_s` at `0x180010214`
- `msvcrt!wcscpy_s` at `0x18001003a`
- `msvcrt!wcscpy_s` at `0x180010084`
- `msvcrt!wcscpy_s` at `0x180010214`
- `ADVAPI32!RegEnumKeyExW` at `0x1800102cc`
- `ADVAPI32!RegEnumKeyExW` at `0x1800102cc`
- `ADVAPI32!RegEnumValueW` at `0x180010278`
- `ADVAPI32!RegEnumValueW` at `0x180010278`
- `ADVAPI32!RegCloseKey` at `0x180010293`
- `ADVAPI32!RegCloseKey` at `0x1800102df`
- `ADVAPI32!RegCloseKey` at `0x180010293`
- `ADVAPI32!RegCloseKey` at `0x1800102df`
- `ADVAPI32!RegQueryValueExW` at `0x18000ff58`
- `ADVAPI32!RegQueryValueExW` at `0x18000ffc9`
- `ADVAPI32!RegQueryValueExW` at `0x18001006d`
- `ADVAPI32!RegQueryValueExW` at `0x1800100d2`
- `ADVAPI32!RegQueryValueExW` at `0x18001010f`
- `ADVAPI32!RegQueryValueExW` at `0x18001014c`
- `ADVAPI32!RegQueryValueExW` at `0x180010193`
- `ADVAPI32!RegQueryValueExW` at `0x18000ff58`
- `ADVAPI32!RegQueryValueExW` at `0x18000ffc9`
- `ADVAPI32!RegQueryValueExW` at `0x18001006d`
- `ADVAPI32!RegQueryValueExW` at `0x1800100d2`
- `ADVAPI32!RegQueryValueExW` at `0x18001010f`
- `ADVAPI32!RegQueryValueExW` at `0x18001014c`
- `ADVAPI32!RegQueryValueExW` at `0x180010193`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ff1f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ff90`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ff1f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ff90`
- `WS2_32!InetPtonW` at `0x180010099`
- `WS2_32!InetPtonW` at `0x180010099`

## string_xrefs

- `0x18000ff18`: `SYSTEM\CurrentControlSet\Services\NfsClnt\NFS LANS`
- `0x18000ff51`: `SPUpdateMinutes`
- `0x18000ffad`: `Configure Mode`
- `0x1800101d5`: `Configure Mode`

## pseudocode

```c
LSTATUS __fastcall CopyBrowseOptions(LPBYTE lpData)
{
  LSTATUS result; // eax
  DWORD v3; // edx
  DWORD i; // r15d
  int v5; // eax
  __int64 v6; // rax
  unsigned int v7; // esi
  size_t v8; // r14
  char *v9; // rax
  char *v10; // rbx
  __int64 v11; // rax
  DWORD v12; // esi
  DWORD j; // edx
  wchar_t *v14; // rax
  wchar_t *v15; // rbx
  __int64 v16; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v20; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchValueName; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  wchar_t SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Source[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t String2[264]; // [rsp+490h] [rbp+390h] BYREF

  cbData = 0;
  hKey = 0;
  ftLastWriteTime = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\NfsClnt\\NFS LANS",
             0,
             0xF003Fu,
             &hKey);
  if ( !result )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"SPUpdateMinutes", 0, 0, lpData, &cbData);
    v3 = 0;
    for ( i = 0; ; v3 = i )
    {
      cbData = 260;
      if ( RegEnumKeyExW(hKey, v3, SubKey, &cbData, 0, 0, 0, &ftLastWriteTime) )
        break;
      *(_DWORD *)Data = 0;
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, SubKey, 0, 0xF003Fu, &phkResult) )
      {
        cbData = 4;
        if ( RegQueryValueExW(phkResult, L"Configure Mode", 0, 0, Data, &cbData) )
        {
          v5 = 0;
          *(_DWORD *)Data = 0;
        }
        else
        {
          v5 = *(_DWORD *)Data;
        }
        if ( v5 )
        {
          v12 = 0;
          for ( j = 0; ; j = v12 )
          {
            cchValueName = 260;
            v20 = 260;
            if ( RegEnumValueW(phkResult, j, String2, &cchValueName, 0, 0, (LPBYTE)Source, &v20) )
              break;
            if ( wcscmp_0(L"Configure Mode", String2) )
            {
              v14 = (wchar_t *)malloc_0(0x218u);
              v15 = v14;
              if ( v14 )
              {
                memset_0(v14, 0, 0x218u);
                wcscpy_s(v15, 0x104u, Source);
                v16 = *((_QWORD *)lpData + 2);
                if ( v16 )
                {
                  *(_QWORD *)(v16 + 528) = v15;
                  *((_QWORD *)v15 + 65) = *((_QWORD *)lpData + 2);
                }
                *((_QWORD *)lpData + 2) = v15;
              }
            }
            ++v12;
          }
        }
        else
        {
          v6 = -1;
          do
            ++v6;
          while ( SubKey[v6] );
          v7 = v6 + 1;
          v8 = 2 * ((int)v6 + 1) + 1616;
          v9 = (char *)malloc_0(v8);
          v10 = v9;
          if ( v9 )
          {
            memset_0(v9, 0, v8);
            *(_QWORD *)v10 = v10 + 1616;
            wcscpy_s((wchar_t *)v10 + 808, v7, SubKey);
            cbData = 260;
            if ( RegQueryValueExW(phkResult, L"SPBroadcastAddr", 0, 0, (LPBYTE)v10 + 1048, &cbData) )
              wcscpy_s((wchar_t *)v10 + 524, 0x104u, L"255.255.255.255");
            InetPtonW(2, (PCWSTR)v10 + 524, v10 + 1576);
            cbData = 4;
            if ( RegQueryValueExW(phkResult, L"SPBroadcastRetry", 0, 0, (LPBYTE)v10 + 1580, &cbData) )
              *((_DWORD *)v10 + 395) = 2;
            cbData = 4;
            if ( RegQueryValueExW(phkResult, L"SPTimeoutSeconds", 0, 0, (LPBYTE)v10 + 1584, &cbData) )
              *((_DWORD *)v10 + 396) = 5;
            cbData = 4;
            if ( RegQueryValueExW(phkResult, L"SPMaxNodes", 0, 0, (LPBYTE)v10 + 1588, &cbData) )
              *((_DWORD *)v10 + 397) = 1024;
            *((_DWORD *)v10 + 398) = 2;
            cbData = 4;
            if ( RegQueryValueExW(phkResult, L"SPGetHostByAddr", 0, 0, (LPBYTE)v10 + 1596, &cbData) )
              *((_DWORD *)v10 + 399) = 1;
            v11 = *((_QWORD *)lpData + 1);
            if ( v11 )
            {
              *(_QWORD *)(v11 + 1608) = v10;
              *((_QWORD *)v10 + 200) = *((_QWORD *)lpData + 1);
            }
            *((_QWORD *)lpData + 1) = v10;
          }
        }
        RegCloseKey(phkResult);
      }
      ++i;
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18000febc  push    rbp
0x18000febe  push    rbx
0x18000febf  push    rsi
0x18000fec0  push    rdi
0x18000fec1  push    r12
0x18000fec3  push    r13
0x18000fec5  push    r14
0x18000fec7  push    r15
0x18000fec9  lea     rbp, [rsp-5B8h]
0x18000fed1  sub     rsp, 6B8h
0x18000fed8  mov     rax, cs:__security_cookie
0x18000fedf  xor     rax, rsp
0x18000fee2  mov     [rbp+5F0h+var_50], rax
0x18000fee9  xor     r12d, r12d
0x18000feec  lea     rax, [rsp+6F0h+hKey]
0x18000fef1  mov     rdi, rcx
0x18000fef4  mov     [rsp+6F0h+cbData], r12d
0x18000fef9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ff00  mov     [rsp+6F0h+hKey], r12
0x18000ff05  mov     r9d, 0F003Fh; samDesired
0x18000ff0b  mov     qword ptr [rsp+6F0h+ftLastWriteTime.dwLowDateTime], r12
0x18000ff10  xor     r8d, r8d; ulOptions
0x18000ff13  mov     [rsp+6F0h+phkResult], rax; phkResult
0x18000ff18  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x18000ff1f  call    cs:__imp_RegOpenKeyExW
0x18000ff25  test    eax, eax
0x18000ff27  jnz     loc_1800102E5
0x18000ff2d  mov     rcx, [rsp+6F0h+hKey]; hKey
0x18000ff32  lea     rax, [rsp+6F0h+cbData]
0x18000ff37  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x18000ff3c  lea     r14d, [r12+4]
0x18000ff41  xor     r9d, r9d; lpType
0x18000ff44  mov     [rsp+6F0h+phkResult], rdi; lpData
0x18000ff49  xor     r8d, r8d; lpReserved
0x18000ff4c  mov     [rsp+6F0h+cbData], r14d
0x18000ff51  lea     rdx, aSpupdateminute; "SPUpdateMinutes"
0x18000ff58  call    cs:__imp_RegQueryValueExW
0x18000ff5e  xor     edx, edx
0x18000ff60  mov     r15d, r12d
0x18000ff63  mov     r13d, 104h
0x18000ff69  jmp     loc_18001029F
0x18000ff6e  lea     rax, [rsp+6F0h+var_6A8]
0x18000ff73  mov     dword ptr [rsp+6F0h+Data], r12d
0x18000ff78  mov     r9d, 0F003Fh; samDesired
0x18000ff7e  mov     [rsp+6F0h+phkResult], rax; phkResult
0x18000ff83  xor     r8d, r8d; ulOptions
0x18000ff86  mov     [rsp+6F0h+var_6A8], r12
0x18000ff8b  lea     rdx, [rsp+6F0h+SubKey]; lpSubKey
0x18000ff90  call    cs:__imp_RegOpenKeyExW
0x18000ff96  test    eax, eax
0x18000ff98  jnz     loc_180010299
0x18000ff9e  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x18000ffa3  lea     rax, [rsp+6F0h+cbData]
0x18000ffa8  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x18000ffad  lea     rdx, aConfigureMode; "Configure Mode"
0x18000ffb4  lea     rax, [rsp+6F0h+Data]
0x18000ffb9  mov     [rsp+6F0h+cbData], r14d
0x18000ffbe  xor     r9d, r9d; lpType
0x18000ffc1  mov     [rsp+6F0h+phkResult], rax; lpData
0x18000ffc6  xor     r8d, r8d; lpReserved
0x18000ffc9  call    cs:__imp_RegQueryValueExW
0x18000ffcf  test    eax, eax
0x18000ffd1  jz      short loc_18000FFDC
0x18000ffd3  mov     eax, r12d
0x18000ffd6  mov     dword ptr [rsp+6F0h+Data], eax
0x18000ffda  jmp     short loc_18000FFE0
0x18000ffdc  mov     eax, dword ptr [rsp+6F0h+Data]
0x18000ffe0  test    eax, eax
0x18000ffe2  jnz     loc_1800101C7
0x18000ffe8  lea     rcx, [rsp+6F0h+SubKey]
0x18000ffed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fff1  inc     rax
0x18000fff4  cmp     [rcx+rax*2], r12w
0x18000fff9  jnz     short loc_18000FFF1
0x18000fffb  lea     esi, [rax+1]
0x18000fffe  lea     eax, ds:650h[rsi*2]
0x180010005  movsxd  r14, eax
0x180010008  mov     rcx, r14; Size
0x18001000b  call    malloc_0
0x180010010  mov     rbx, rax
0x180010013  test    rax, rax
0x180010016  jz      loc_180010288
0x18001001c  mov     r8, r14; Size
0x18001001f  xor     edx, edx; Val
0x180010021  mov     rcx, rax; void *
0x180010024  call    memset_0
0x180010029  lea     rcx, [rbx+650h]; Destination
0x180010030  mov     edx, esi; SizeInWords
0x180010032  lea     r8, [rsp+6F0h+SubKey]; Source
0x180010037  mov     [rbx], rcx
0x18001003a  call    cs:__imp_wcscpy_s
0x180010040  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x180010045  lea     rax, [rsp+6F0h+cbData]
0x18001004a  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x18001004f  lea     rsi, [rbx+418h]
0x180010056  xor     r9d, r9d; lpType
0x180010059  mov     [rsp+6F0h+phkResult], rsi; lpData
0x18001005e  xor     r8d, r8d; lpReserved
0x180010061  mov     [rsp+6F0h+cbData], r13d
0x180010066  lea     rdx, aSpbroadcastadd; "SPBroadcastAddr"
0x18001006d  call    cs:__imp_RegQueryValueExW
0x180010073  test    eax, eax
0x180010075  jz      short loc_18001008A
0x180010077  lea     r8, a255255255255; "255.255.255.255"
0x18001007e  mov     rdx, r13; SizeInWords
0x180010081  mov     rcx, rsi; Destination
0x180010084  call    cs:__imp_wcscpy_s
0x18001008a  lea     r8, [rbx+628h]; pAddrBuf
0x180010091  mov     rdx, rsi; pszAddrString
0x180010094  mov     ecx, 2; Family
0x180010099  call    cs:__imp_InetPtonW
0x18001009f  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x1800100a4  lea     rax, [rsp+6F0h+cbData]
0x1800100a9  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x1800100ae  lea     rsi, [rbx+62Ch]
0x1800100b5  mov     r14d, 4
0x1800100bb  mov     [rsp+6F0h+phkResult], rsi; lpData
0x1800100c0  xor     r9d, r9d; lpType
0x1800100c3  mov     [rsp+6F0h+cbData], r14d
0x1800100c8  xor     r8d, r8d; lpReserved
0x1800100cb  lea     rdx, aSpbroadcastret; "SPBroadcastRetry"
0x1800100d2  call    cs:__imp_RegQueryValueExW
0x1800100d8  test    eax, eax
0x1800100da  jz      short loc_1800100E2
0x1800100dc  mov     dword ptr [rsi], 2
0x1800100e2  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x1800100e7  lea     rax, [rsp+6F0h+cbData]
0x1800100ec  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x1800100f1  lea     rsi, [rbx+630h]
0x1800100f8  xor     r9d, r9d; lpType
0x1800100fb  mov     [rsp+6F0h+phkResult], rsi; lpData
0x180010100  xor     r8d, r8d; lpReserved
0x180010103  mov     [rsp+6F0h+cbData], r14d
0x180010108  lea     rdx, aSptimeoutsecon; "SPTimeoutSeconds"
0x18001010f  call    cs:__imp_RegQueryValueExW
0x180010115  test    eax, eax
0x180010117  jz      short loc_18001011F
0x180010119  mov     dword ptr [rsi], 5
0x18001011f  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x180010124  lea     rax, [rsp+6F0h+cbData]
0x180010129  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x18001012e  lea     rsi, [rbx+634h]
0x180010135  xor     r9d, r9d; lpType
0x180010138  mov     [rsp+6F0h+phkResult], rsi; lpData
0x18001013d  xor     r8d, r8d; lpReserved
0x180010140  mov     [rsp+6F0h+cbData], r14d
0x180010145  lea     rdx, aSpmaxnodes; "SPMaxNodes"
0x18001014c  call    cs:__imp_RegQueryValueExW
0x180010152  test    eax, eax
0x180010154  jz      short loc_18001015C
0x180010156  mov     dword ptr [rsi], 400h
0x18001015c  mov     dword ptr [rbx+638h], 2
0x180010166  lea     rax, [rsp+6F0h+cbData]
0x18001016b  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x180010170  lea     rsi, [rbx+63Ch]
0x180010177  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x18001017c  lea     rdx, aSpgethostbyadd; "SPGetHostByAddr"
0x180010183  xor     r9d, r9d; lpType
0x180010186  mov     [rsp+6F0h+phkResult], rsi; lpData
0x18001018b  xor     r8d, r8d; lpReserved
0x18001018e  mov     [rsp+6F0h+cbData], r14d
0x180010193  call    cs:__imp_RegQueryValueExW
0x180010199  test    eax, eax
0x18001019b  jz      short loc_1800101A3
0x18001019d  mov     dword ptr [rsi], 1
0x1800101a3  mov     rax, [rdi+8]
0x1800101a7  test    rax, rax
0x1800101aa  jz      short loc_1800101BE
0x1800101ac  mov     [rax+648h], rbx
0x1800101b3  mov     rax, [rdi+8]
0x1800101b7  mov     [rbx+640h], rax
0x1800101be  mov     [rdi+8], rbx
0x1800101c2  jmp     loc_18001028E
0x1800101c7  mov     esi, r12d
0x1800101ca  xor     edx, edx
0x1800101cc  jmp     short loc_18001023D
0x1800101ce  lea     rdx, [rbp+5F0h+String2]; String2
0x1800101d5  lea     rcx, aConfigureMode; "Configure Mode"
0x1800101dc  call    wcscmp_0
0x1800101e1  test    eax, eax
0x1800101e3  jz      short loc_180010239
0x1800101e5  mov     ecx, 218h; Size
0x1800101ea  call    malloc_0
0x1800101ef  mov     rbx, rax
0x1800101f2  test    rax, rax
0x1800101f5  jz      short loc_180010239
0x1800101f7  xor     edx, edx; Val
0x1800101f9  mov     r8d, 218h; Size
0x1800101ff  mov     rcx, rax; void *
0x180010202  call    memset_0
0x180010207  lea     r8, [rbp+5F0h+Source]; Source
0x18001020e  mov     rdx, r13; SizeInWords
0x180010211  mov     rcx, rbx; Destination
0x180010214  call    cs:__imp_wcscpy_s
0x18001021a  mov     rax, [rdi+10h]
0x18001021e  test    rax, rax
0x180010221  jz      short loc_180010235
0x180010223  mov     [rax+210h], rbx
0x18001022a  mov     rax, [rdi+10h]
0x18001022e  mov     [rbx+208h], rax
0x180010235  mov     [rdi+10h], rbx
0x180010239  inc     esi
0x18001023b  mov     edx, esi; dwIndex
0x18001023d  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x180010242  lea     rax, [rsp+6F0h+var_69C]
0x180010247  mov     [rsp+6F0h+var_6B8], rax; lpcbData
0x18001024c  lea     r9, [rsp+6F0h+cchValueName]; lpcchValueName
0x180010251  lea     rax, [rbp+5F0h+Source]
0x180010258  mov     [rsp+6F0h+cchValueName], r13d
0x18001025d  mov     [rsp+6F0h+lpData], rax; lpData
0x180010262  lea     r8, [rbp+5F0h+String2]; lpValueName
0x180010269  mov     [rsp+6F0h+lpcbData], r12; lpType
0x18001026e  mov     [rsp+6F0h+phkResult], r12; lpReserved
0x180010273  mov     [rsp+6F0h+var_69C], r13d
0x180010278  call    cs:__imp_RegEnumValueW
0x18001027e  test    eax, eax
0x180010280  jz      loc_1800101CE
0x180010286  jmp     short loc_18001028E
0x180010288  mov     r14d, 4
0x18001028e  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x180010293  call    cs:__imp_RegCloseKey
0x180010299  inc     r15d
0x18001029c  mov     edx, r15d; dwIndex
0x18001029f  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1800102a4  lea     rax, [rsp+6F0h+ftLastWriteTime]
0x1800102a9  mov     [rsp+6F0h+var_6B8], rax; lpftLastWriteTime
0x1800102ae  lea     r9, [rsp+6F0h+cbData]; lpcchName
0x1800102b3  mov     [rsp+6F0h+lpData], r12; lpcchClass
0x1800102b8  lea     r8, [rsp+6F0h+SubKey]; lpName
0x1800102bd  mov     [rsp+6F0h+lpcbData], r12; lpClass
0x1800102c2  mov     [rsp+6F0h+phkResult], r12; lpReserved
0x1800102c7  mov     [rsp+6F0h+cbData], r13d
0x1800102cc  call    cs:__imp_RegEnumKeyExW
0x1800102d2  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1800102d7  test    eax, eax
0x1800102d9  jz      loc_18000FF6E
0x1800102df  call    cs:__imp_RegCloseKey
0x1800102e5  mov     rcx, [rbp+5F0h+var_50]
0x1800102ec  xor     rcx, rsp; StackCookie
0x1800102ef  call    __security_check_cookie
0x1800102f4  add     rsp, 6B8h
0x1800102fb  pop     r15
0x1800102fd  pop     r14
0x1800102ff  pop     r13
0x180010301  pop     r12
0x180010303  pop     rdi
0x180010304  pop     rsi
0x180010305  pop     rbx
0x180010306  pop     rbp
0x180010307  retn
```
