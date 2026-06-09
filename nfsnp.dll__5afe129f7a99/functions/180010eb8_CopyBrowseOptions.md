# CopyBrowseOptions

- ea: `0x180010eb8`
- end: `0x18001136b`
- name: `CopyBrowseOptions`
- size: `1203`
- prototype: `LSTATUS __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000c738`

## callees

- `0x18000190d`
- `0x180010eb8`
- `0x180012e32`
- `0x180012e3e`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001104e`
- `msvcrt!wcscpy_s` at `0x1800110a4`
- `msvcrt!wcscpy_s` at `0x180011258`
- `msvcrt!wcscpy_s` at `0x18001104e`
- `msvcrt!wcscpy_s` at `0x1800110a4`
- `msvcrt!wcscpy_s` at `0x180011258`
- `ADVAPI32!RegEnumKeyExW` at `0x180011322`
- `ADVAPI32!RegEnumKeyExW` at `0x180011322`
- `ADVAPI32!RegEnumValueW` at `0x1800112c2`
- `ADVAPI32!RegEnumValueW` at `0x1800112c2`
- `ADVAPI32!RegCloseKey` at `0x1800112e3`
- `ADVAPI32!RegCloseKey` at `0x18001133b`
- `ADVAPI32!RegCloseKey` at `0x1800112e3`
- `ADVAPI32!RegCloseKey` at `0x18001133b`
- `ADVAPI32!RegQueryValueExW` at `0x180010f5a`
- `ADVAPI32!RegQueryValueExW` at `0x180010fd7`
- `ADVAPI32!RegQueryValueExW` at `0x180011087`
- `ADVAPI32!RegQueryValueExW` at `0x1800110fe`
- `ADVAPI32!RegQueryValueExW` at `0x180011141`
- `ADVAPI32!RegQueryValueExW` at `0x180011184`
- `ADVAPI32!RegQueryValueExW` at `0x1800111d1`
- `ADVAPI32!RegQueryValueExW` at `0x180010f5a`
- `ADVAPI32!RegQueryValueExW` at `0x180010fd7`
- `ADVAPI32!RegQueryValueExW` at `0x180011087`
- `ADVAPI32!RegQueryValueExW` at `0x1800110fe`
- `ADVAPI32!RegQueryValueExW` at `0x180011141`
- `ADVAPI32!RegQueryValueExW` at `0x180011184`
- `ADVAPI32!RegQueryValueExW` at `0x1800111d1`
- `ADVAPI32!RegOpenKeyExW` at `0x180010f1b`
- `ADVAPI32!RegOpenKeyExW` at `0x180010f98`
- `ADVAPI32!RegOpenKeyExW` at `0x180010f1b`
- `ADVAPI32!RegOpenKeyExW` at `0x180010f98`
- `WS2_32!InetPtonW` at `0x1800110bf`
- `WS2_32!InetPtonW` at `0x1800110bf`

## string_xrefs

- `0x180010f14`: `SYSTEM\CurrentControlSet\Services\NfsClnt\NFS LANS`
- `0x180010f53`: `SPUpdateMinutes`
- `0x180010fbb`: `Configure Mode`
- `0x180011219`: `Configure Mode`

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
0x180010eb8  push    rbp
0x180010eba  push    rbx
0x180010ebb  push    rsi
0x180010ebc  push    rdi
0x180010ebd  push    r12
0x180010ebf  push    r13
0x180010ec1  push    r14
0x180010ec3  push    r15
0x180010ec5  lea     rbp, [rsp-5B8h]
0x180010ecd  sub     rsp, 6B8h
0x180010ed4  mov     rax, cs:__security_cookie
0x180010edb  xor     rax, rsp
0x180010ede  mov     [rbp+5F0h+var_50], rax
0x180010ee5  xor     r12d, r12d
0x180010ee8  lea     rax, [rsp+6F0h+hKey]
0x180010eed  mov     rdi, rcx
0x180010ef0  mov     [rsp+6F0h+cbData], r12d
0x180010ef5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010efc  mov     [rsp+6F0h+hKey], r12
0x180010f01  mov     r9d, 0F003Fh; samDesired
0x180010f07  mov     qword ptr [rsp+6F0h+ftLastWriteTime.dwLowDateTime], r12
0x180010f0c  xor     r8d, r8d; ulOptions
0x180010f0f  mov     [rsp+6F0h+phkResult], rax; phkResult
0x180010f14  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x180010f1b  call    cs:__imp_RegOpenKeyExW
0x180010f22  nop     dword ptr [rax+rax+00h]
0x180010f27  test    eax, eax
0x180010f29  jnz     loc_180011347
0x180010f2f  mov     rcx, [rsp+6F0h+hKey]; hKey
0x180010f34  lea     rax, [rsp+6F0h+cbData]
0x180010f39  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x180010f3e  lea     r14d, [r12+4]
0x180010f43  xor     r9d, r9d; lpType
0x180010f46  mov     [rsp+6F0h+phkResult], rdi; lpData
0x180010f4b  xor     r8d, r8d; lpReserved
0x180010f4e  mov     [rsp+6F0h+cbData], r14d
0x180010f53  lea     rdx, aSpupdateminute; "SPUpdateMinutes"
0x180010f5a  call    cs:__imp_RegQueryValueExW
0x180010f61  nop     dword ptr [rax+rax+00h]
0x180010f66  xor     edx, edx
0x180010f68  mov     r15d, r12d
0x180010f6b  mov     r13d, 104h
0x180010f71  jmp     loc_1800112F5
0x180010f76  lea     rax, [rsp+6F0h+var_6A8]
0x180010f7b  mov     dword ptr [rsp+6F0h+Data], r12d
0x180010f80  mov     r9d, 0F003Fh; samDesired
0x180010f86  mov     [rsp+6F0h+phkResult], rax; phkResult
0x180010f8b  xor     r8d, r8d; ulOptions
0x180010f8e  mov     [rsp+6F0h+var_6A8], r12
0x180010f93  lea     rdx, [rsp+6F0h+SubKey]; lpSubKey
0x180010f98  call    cs:__imp_RegOpenKeyExW
0x180010f9f  nop     dword ptr [rax+rax+00h]
0x180010fa4  test    eax, eax
0x180010fa6  jnz     loc_1800112EF
0x180010fac  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x180010fb1  lea     rax, [rsp+6F0h+cbData]
0x180010fb6  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x180010fbb  lea     rdx, aConfigureMode; "Configure Mode"
0x180010fc2  lea     rax, [rsp+6F0h+Data]
0x180010fc7  mov     [rsp+6F0h+cbData], r14d
0x180010fcc  xor     r9d, r9d; lpType
0x180010fcf  mov     [rsp+6F0h+phkResult], rax; lpData
0x180010fd4  xor     r8d, r8d; lpReserved
0x180010fd7  call    cs:__imp_RegQueryValueExW
0x180010fde  nop     dword ptr [rax+rax+00h]
0x180010fe3  test    eax, eax
0x180010fe5  jz      short loc_180010FF0
0x180010fe7  mov     eax, r12d
0x180010fea  mov     dword ptr [rsp+6F0h+Data], eax
0x180010fee  jmp     short loc_180010FF4
0x180010ff0  mov     eax, dword ptr [rsp+6F0h+Data]
0x180010ff4  test    eax, eax
0x180010ff6  jnz     loc_18001120B
0x180010ffc  lea     rcx, [rsp+6F0h+SubKey]
0x180011001  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011005  inc     rax
0x180011008  cmp     [rcx+rax*2], r12w
0x18001100d  jnz     short loc_180011005
0x18001100f  lea     esi, [rax+1]
0x180011012  lea     eax, ds:650h[rsi*2]
0x180011019  movsxd  r14, eax
0x18001101c  mov     rcx, r14; Size
0x18001101f  call    malloc_0
0x180011024  mov     rbx, rax
0x180011027  test    rax, rax
0x18001102a  jz      loc_1800112D8
0x180011030  mov     r8, r14; Size
0x180011033  xor     edx, edx; Val
0x180011035  mov     rcx, rax; void *
0x180011038  call    memset_0
0x18001103d  lea     rcx, [rbx+650h]; Destination
0x180011044  mov     edx, esi; SizeInWords
0x180011046  lea     r8, [rsp+6F0h+SubKey]; Source
0x18001104b  mov     [rbx], rcx
0x18001104e  call    cs:__imp_wcscpy_s
0x180011055  nop     dword ptr [rax+rax+00h]
0x18001105a  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x18001105f  lea     rax, [rsp+6F0h+cbData]
0x180011064  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x180011069  lea     rsi, [rbx+418h]
0x180011070  xor     r9d, r9d; lpType
0x180011073  mov     [rsp+6F0h+phkResult], rsi; lpData
0x180011078  xor     r8d, r8d; lpReserved
0x18001107b  mov     [rsp+6F0h+cbData], r13d
0x180011080  lea     rdx, aSpbroadcastadd; "SPBroadcastAddr"
0x180011087  call    cs:__imp_RegQueryValueExW
0x18001108e  nop     dword ptr [rax+rax+00h]
0x180011093  test    eax, eax
0x180011095  jz      short loc_1800110B0
0x180011097  lea     r8, a255255255255; "255.255.255.255"
0x18001109e  mov     rdx, r13; SizeInWords
0x1800110a1  mov     rcx, rsi; Destination
0x1800110a4  call    cs:__imp_wcscpy_s
0x1800110ab  nop     dword ptr [rax+rax+00h]
0x1800110b0  lea     r8, [rbx+628h]; pAddrBuf
0x1800110b7  mov     rdx, rsi; pszAddrString
0x1800110ba  mov     ecx, 2; Family
0x1800110bf  call    cs:__imp_InetPtonW
0x1800110c6  nop     dword ptr [rax+rax+00h]
0x1800110cb  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x1800110d0  lea     rax, [rsp+6F0h+cbData]
0x1800110d5  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x1800110da  lea     rsi, [rbx+62Ch]
0x1800110e1  mov     r14d, 4
0x1800110e7  mov     [rsp+6F0h+phkResult], rsi; lpData
0x1800110ec  xor     r9d, r9d; lpType
0x1800110ef  mov     [rsp+6F0h+cbData], r14d
0x1800110f4  xor     r8d, r8d; lpReserved
0x1800110f7  lea     rdx, aSpbroadcastret; "SPBroadcastRetry"
0x1800110fe  call    cs:__imp_RegQueryValueExW
0x180011105  nop     dword ptr [rax+rax+00h]
0x18001110a  test    eax, eax
0x18001110c  jz      short loc_180011114
0x18001110e  mov     dword ptr [rsi], 2
0x180011114  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x180011119  lea     rax, [rsp+6F0h+cbData]
0x18001111e  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x180011123  lea     rsi, [rbx+630h]
0x18001112a  xor     r9d, r9d; lpType
0x18001112d  mov     [rsp+6F0h+phkResult], rsi; lpData
0x180011132  xor     r8d, r8d; lpReserved
0x180011135  mov     [rsp+6F0h+cbData], r14d
0x18001113a  lea     rdx, aSptimeoutsecon; "SPTimeoutSeconds"
0x180011141  call    cs:__imp_RegQueryValueExW
0x180011148  nop     dword ptr [rax+rax+00h]
0x18001114d  test    eax, eax
0x18001114f  jz      short loc_180011157
0x180011151  mov     dword ptr [rsi], 5
0x180011157  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x18001115c  lea     rax, [rsp+6F0h+cbData]
0x180011161  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x180011166  lea     rsi, [rbx+634h]
0x18001116d  xor     r9d, r9d; lpType
0x180011170  mov     [rsp+6F0h+phkResult], rsi; lpData
0x180011175  xor     r8d, r8d; lpReserved
0x180011178  mov     [rsp+6F0h+cbData], r14d
0x18001117d  lea     rdx, aSpmaxnodes; "SPMaxNodes"
0x180011184  call    cs:__imp_RegQueryValueExW
0x18001118b  nop     dword ptr [rax+rax+00h]
0x180011190  test    eax, eax
0x180011192  jz      short loc_18001119A
0x180011194  mov     dword ptr [rsi], 400h
0x18001119a  mov     dword ptr [rbx+638h], 2
0x1800111a4  lea     rax, [rsp+6F0h+cbData]
0x1800111a9  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x1800111ae  lea     rsi, [rbx+63Ch]
0x1800111b5  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x1800111ba  lea     rdx, aSpgethostbyadd; "SPGetHostByAddr"
0x1800111c1  xor     r9d, r9d; lpType
0x1800111c4  mov     [rsp+6F0h+phkResult], rsi; lpData
0x1800111c9  xor     r8d, r8d; lpReserved
0x1800111cc  mov     [rsp+6F0h+cbData], r14d
0x1800111d1  call    cs:__imp_RegQueryValueExW
0x1800111d8  nop     dword ptr [rax+rax+00h]
0x1800111dd  test    eax, eax
0x1800111df  jz      short loc_1800111E7
0x1800111e1  mov     dword ptr [rsi], 1
0x1800111e7  mov     rax, [rdi+8]
0x1800111eb  test    rax, rax
0x1800111ee  jz      short loc_180011202
0x1800111f0  mov     [rax+648h], rbx
0x1800111f7  mov     rax, [rdi+8]
0x1800111fb  mov     [rbx+640h], rax
0x180011202  mov     [rdi+8], rbx
0x180011206  jmp     loc_1800112DE
0x18001120b  mov     esi, r12d
0x18001120e  xor     edx, edx
0x180011210  jmp     short loc_180011287
0x180011212  lea     rdx, [rbp+5F0h+String2]; String2
0x180011219  lea     rcx, aConfigureMode; "Configure Mode"
0x180011220  call    wcscmp_0
0x180011225  test    eax, eax
0x180011227  jz      short loc_180011283
0x180011229  mov     ecx, 218h; Size
0x18001122e  call    malloc_0
0x180011233  mov     rbx, rax
0x180011236  test    rax, rax
0x180011239  jz      short loc_180011283
0x18001123b  xor     edx, edx; Val
0x18001123d  mov     r8d, 218h; Size
0x180011243  mov     rcx, rax; void *
0x180011246  call    memset_0
0x18001124b  lea     r8, [rbp+5F0h+Source]; Source
0x180011252  mov     rdx, r13; SizeInWords
0x180011255  mov     rcx, rbx; Destination
0x180011258  call    cs:__imp_wcscpy_s
0x18001125f  nop     dword ptr [rax+rax+00h]
0x180011264  mov     rax, [rdi+10h]
0x180011268  test    rax, rax
0x18001126b  jz      short loc_18001127F
0x18001126d  mov     [rax+210h], rbx
0x180011274  mov     rax, [rdi+10h]
0x180011278  mov     [rbx+208h], rax
0x18001127f  mov     [rdi+10h], rbx
0x180011283  inc     esi
0x180011285  mov     edx, esi; dwIndex
0x180011287  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x18001128c  lea     rax, [rsp+6F0h+var_69C]
0x180011291  mov     [rsp+6F0h+var_6B8], rax; lpcbData
0x180011296  lea     r9, [rsp+6F0h+cchValueName]; lpcchValueName
0x18001129b  lea     rax, [rbp+5F0h+Source]
0x1800112a2  mov     [rsp+6F0h+cchValueName], r13d
0x1800112a7  mov     [rsp+6F0h+lpData], rax; lpData
0x1800112ac  lea     r8, [rbp+5F0h+String2]; lpValueName
0x1800112b3  mov     [rsp+6F0h+lpcbData], r12; lpType
0x1800112b8  mov     [rsp+6F0h+phkResult], r12; lpReserved
0x1800112bd  mov     [rsp+6F0h+var_69C], r13d
0x1800112c2  call    cs:__imp_RegEnumValueW
0x1800112c9  nop     dword ptr [rax+rax+00h]
0x1800112ce  test    eax, eax
0x1800112d0  jz      loc_180011212
0x1800112d6  jmp     short loc_1800112DE
0x1800112d8  mov     r14d, 4
0x1800112de  mov     rcx, [rsp+6F0h+var_6A8]; hKey
0x1800112e3  call    cs:__imp_RegCloseKey
0x1800112ea  nop     dword ptr [rax+rax+00h]
0x1800112ef  inc     r15d
0x1800112f2  mov     edx, r15d; dwIndex
0x1800112f5  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1800112fa  lea     rax, [rsp+6F0h+ftLastWriteTime]
0x1800112ff  mov     [rsp+6F0h+var_6B8], rax; lpftLastWriteTime
0x180011304  lea     r9, [rsp+6F0h+cbData]; lpcchName
0x180011309  mov     [rsp+6F0h+lpData], r12; lpcchClass
0x18001130e  lea     r8, [rsp+6F0h+SubKey]; lpName
0x180011313  mov     [rsp+6F0h+lpcbData], r12; lpClass
0x180011318  mov     [rsp+6F0h+phkResult], r12; lpReserved
0x18001131d  mov     [rsp+6F0h+cbData], r13d
0x180011322  call    cs:__imp_RegEnumKeyExW
0x180011329  nop     dword ptr [rax+rax+00h]
0x18001132e  mov     rcx, [rsp+6F0h+hKey]; hKey
0x180011333  test    eax, eax
0x180011335  jz      loc_180010F76
0x18001133b  call    cs:__imp_RegCloseKey
0x180011342  nop     dword ptr [rax+rax+00h]
0x180011347  mov     rcx, [rbp+5F0h+var_50]
0x18001134e  xor     rcx, rsp; StackCookie
0x180011351  call    __security_check_cookie
0x180011356  add     rsp, 6B8h
0x18001135d  pop     r15
0x18001135f  pop     r14
0x180011361  pop     r13
0x180011363  pop     r12
0x180011365  pop     rdi
0x180011366  pop     rsi
0x180011367  pop     rbx
0x180011368  pop     rbp
0x180011369  retn
```
