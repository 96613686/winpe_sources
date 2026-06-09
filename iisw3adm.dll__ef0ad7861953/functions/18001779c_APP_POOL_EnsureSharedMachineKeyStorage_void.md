# APP_POOL::EnsureSharedMachineKeyStorage(void)

- ea: `0x18001779c`
- end: `0x180017d0a`
- name: `?EnsureSharedMachineKeyStorage@APP_POOL@@AEAAXXZ`
- size: `1390`
- prototype: `void __fastcall(APP_POOL *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017040`

## callees

- `0x18001779c`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180017990`
- `msvcrt!_wcsnicmp` at `0x180017990`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c6a`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180017bb1`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180017bb1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017a60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017ace`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017a60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017ace`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001795a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001795a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800178f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800179fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800178f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800179fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017cbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017cbe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017ccd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017cd7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017ce1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017ccd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017cd7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017ce1`
- `iisutil!PuDbgPrintError` at `0x180017c11`
- `iisutil!PuDbgPrintError` at `0x180017c5a`
- `iisutil!PuDbgPrintError` at `0x180017c11`
- `iisutil!PuDbgPrintError` at `0x180017c5a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800179aa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017b16`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800179aa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017b16`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b3e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b5d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b78`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b3e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b5d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b78`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001780a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001782f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017854`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001780a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001782f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017854`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180017970`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180017970`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800179c2`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800179c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017b98`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017b98`

## string_xrefs

- `0x180017c0a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180017c53`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001790b`: `Opening the 'HKLM\Software\Microsoft\ASP.Net' key failed\n`
- `0x180017a12`: `Failed opening the version specific ASP.Net key.\n`
- `0x180017a77`: `Failed opening the version specific ASP.Net autogen key.\n`
- `0x180017ae5`: `Failed creating the SID key under the ASP.Net autogen key.\n`
- `0x180017bc4`: `Error setting the security for the ASP.Net autogen SID key.\n`
- `0x180017c36`: `Failure in creating or securing the ASP.Net autogen SID key.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall APP_POOL::EnsureSharedMachineKeyStorage(APP_POOL *this)
{
  int v2; // ebx
  __int64 v3; // rcx
  const wchar_t *v4; // rdi
  size_t v5; // rsi
  int v6; // r12d
  const char *v7; // rax
  __int64 v8; // r8
  DWORD i; // r14d
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY v15; // [rsp+70h] [rbp-90h] BYREF
  HKEY v16; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v17[32]; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR lpName; // [rsp+A0h] [rbp-60h]
  unsigned int v19; // [rsp+A8h] [rbp-58h]
  unsigned int v20; // [rsp+B0h] [rbp-50h]
  _BYTE v21[32]; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+D8h] [rbp-28h]
  _BYTE v23[32]; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+110h] [rbp+10h]
  unsigned __int16 v25[256]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v26[256]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v27[256]; // [rsp+530h] [rbp+430h] BYREF

  hKey = 0;
  phkResult = 0;
  v15 = 0;
  v16 = 0;
  v2 = 0;
  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v17, v25, 0x100u);
  memset_0(v26, 0, sizeof(v26));
  STRU::STRU((STRU *)v23, v26, 0x100u);
  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v21, v27, 0x100u);
  v3 = *((_QWORD *)this + 11);
  cchName = 0;
  dwDisposition = 0;
  SecurityDescriptor = 0;
  if ( *(_DWORD *)(v3 + 652) == 4 )
  {
    if ( *(_DWORD *)(v3 + 456) )
    {
      v4 = *(const wchar_t **)(v3 + 440);
      if ( v4 )
      {
        if ( *v4 )
        {
          if ( ((*v4 - 86) & 0xFFDF) == 0 )
            ++v4;
          v5 = -1;
          do
            ++v5;
          while ( v4[v5] );
          v6 = *(_DWORD *)(v3 + 400);
          if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\ASP.NET", 0, v6 != 0 ? 524 : 12, &hKey) )
          {
            for ( i = 0; ; ++i )
            {
              *lpName = 0;
              cchName = v19 >> 1;
              v20 = 0;
              if ( RegEnumKeyExW(hKey, i, lpName, &cchName, 0, 0, 0, 0) )
                break;
              if ( !STRU::SetLen((STRU *)v17, cchName) )
                goto LABEL_42;
              if ( v5 < v20 && !_wcsnicmp(v4, lpName, v5) )
              {
                v2 = STRU::Copy((STRU *)v23, L"SOFTWARE\\Microsoft\\ASP.NET\\");
                if ( v2 >= 0 )
                {
                  v2 = STRU::Append((STRU *)v23, (const struct STRU *)v17);
                  if ( v2 >= 0 )
                  {
                    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, v6 != 0 ? 516 : 4, &phkResult) )
                    {
                      if ( (g_dwDebugFlags & 0xF) != 0 )
                        PuDbgPrintError(
                          g_pDebug,
                          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
                          7007,
                          "APP_POOL::EnsureSharedMachineKeyStorage",
                          v2,
                          "Failed opening the version specific ASP.Net key.\n");
                    }
                    else if ( RegCreateKeyExW(phkResult, L"AutoGenKeys", 0, 0, 0, 0x2001Fu, 0, &v15, 0) )
                    {
                      if ( (g_dwDebugFlags & 0xF) != 0 )
                        PuDbgPrintError(
                          g_pDebug,
                          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
                          7027,
                          "APP_POOL::EnsureSharedMachineKeyStorage",
                          v2,
                          "Failed opening the version specific ASP.Net autogen key.\n");
                    }
                    else if ( RegCreateKeyExW(
                                v15,
                                *(LPCWSTR *)(*((_QWORD *)this + 11) + 192LL),
                                0,
                                0,
                                0,
                                0x40000u,
                                0,
                                &v16,
                                &dwDisposition) )
                    {
                      if ( (g_dwDebugFlags & 0xF) != 0 )
                        PuDbgPrintError(
                          g_pDebug,
                          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
                          7048,
                          "APP_POOL::EnsureSharedMachineKeyStorage",
                          v2,
                          "Failed creating the SID key under the ASP.Net autogen key.\n");
                    }
                    else if ( dwDisposition != 2 )
                    {
                      v2 = STRU::Copy((STRU *)v21, L"D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)");
                      if ( v2 >= 0 )
                      {
                        if ( !*(_QWORD *)(*((_QWORD *)this + 11) + 192LL)
                          || (v2 = STRU::Append((STRU *)v21, L"(A;OICI;GA;;;"), v2 >= 0)
                          && (v2 = STRU::Append(
                                     (STRU *)v21,
                                     *(const unsigned __int16 **)(*((_QWORD *)this + 11) + 192LL)),
                              v2 >= 0) )
                        {
                          v2 = STRU::Append((STRU *)v21, L")");
                          if ( v2 >= 0
                            && ConvertStringSecurityDescriptorToSecurityDescriptorW(
                                 StringSecurityDescriptor,
                                 1u,
                                 &SecurityDescriptor,
                                 0)
                            && RegSetKeySecurity(v16, 4u, SecurityDescriptor)
                            && (g_dwDebugFlags & 0xF) != 0 )
                          {
                            PuDbgPrintError(
                              g_pDebug,
                              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
                              7109,
                              "APP_POOL::EnsureSharedMachineKeyStorage",
                              v2,
                              "Error setting the security for the ASP.Net autogen SID key.\n");
                          }
                        }
                      }
                    }
                  }
                }
                goto LABEL_42;
              }
            }
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_42;
            v7 = "Doing an enum on the 'HKLM\\Software\\Microsoft\\ASP.Net' key failed\n";
            v8 = 6956;
            goto LABEL_41;
          }
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v7 = "Opening the 'HKLM\\Software\\Microsoft\\ASP.Net' key failed\n";
            v8 = 6932;
LABEL_41:
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
              v8,
              "APP_POOL::EnsureSharedMachineKeyStorage",
              0,
              v7);
          }
        }
      }
    }
  }
LABEL_42:
  *((_DWORD *)this + 126) = 1;
  if ( v2 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
      7123,
      "APP_POOL::EnsureSharedMachineKeyStorage",
      v2,
      "Failure in creating or securing the ASP.Net autogen SID key.\n");
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v15 )
  {
    RegCloseKey(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    RegCloseKey(v16);
    v16 = 0;
  }
  STRU::~STRU((STRU *)v21);
  STRU::~STRU((STRU *)v23);
  STRU::~STRU((STRU *)v17);
}

```

## disassembly

```asm
0x18001779c  push    rbp
0x18001779e  push    rbx
0x18001779f  push    rsi
0x1800177a0  push    rdi
0x1800177a1  push    r12
0x1800177a3  push    r13
0x1800177a5  push    r14
0x1800177a7  push    r15
0x1800177a9  lea     rbp, [rsp-648h]
0x1800177b1  sub     rsp, 748h
0x1800177b8  mov     rax, cs:__security_cookie
0x1800177bf  xor     rax, rsp
0x1800177c2  mov     [rbp+680h+var_50], rax
0x1800177c9  xor     r13d, r13d
0x1800177cc  mov     r15, rcx
0x1800177cf  mov     r14d, 200h
0x1800177d5  mov     [rsp+780h+hKey], r13
0x1800177da  mov     r8d, r14d; Size
0x1800177dd  mov     [rsp+780h+var_718], r13
0x1800177e2  xor     edx, edx; Val
0x1800177e4  mov     [rsp+780h+var_710], r13
0x1800177e9  lea     rcx, [rbp+680h+var_650]; void *
0x1800177ed  mov     [rsp+780h+var_708], r13
0x1800177f2  mov     ebx, r13d
0x1800177f5  call    memset_0
0x1800177fa  mov     edi, 100h
0x1800177ff  lea     rdx, [rbp+680h+var_650]
0x180017803  mov     r8d, edi
0x180017806  lea     rcx, [rbp+680h+var_700]
0x18001780a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180017810  mov     r8d, r14d; Size
0x180017813  lea     rcx, [rbp+680h+var_450]; void *
0x18001781a  xor     edx, edx; Val
0x18001781c  call    memset_0
0x180017821  mov     r8d, edi
0x180017824  lea     rdx, [rbp+680h+var_450]
0x18001782b  lea     rcx, [rbp+680h+var_690]
0x18001782f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180017835  mov     r8d, r14d; Size
0x180017838  lea     rcx, [rbp+680h+var_250]; void *
0x18001783f  xor     edx, edx; Val
0x180017841  call    memset_0
0x180017846  mov     r8d, edi
0x180017849  lea     rdx, [rbp+680h+var_250]
0x180017850  lea     rcx, [rbp+680h+var_6C8]
0x180017854  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001785a  mov     rcx, [r15+58h]
0x18001785e  mov     [rsp+780h+cchName], r13d
0x180017863  mov     [rsp+780h+dwDisposition], r13d
0x180017868  mov     [rsp+780h+SecurityDescriptor], r13
0x18001786d  cmp     dword ptr [rcx+28Ch], 4
0x180017874  jnz     loc_180017C17
0x18001787a  cmp     [rcx+1C8h], r13d
0x180017881  jz      loc_180017C17
0x180017887  mov     rdi, [rcx+1B8h]
0x18001788e  test    rdi, rdi
0x180017891  jz      loc_180017C17
0x180017897  movzx   eax, word ptr [rdi]
0x18001789a  test    ax, ax
0x18001789d  jz      loc_180017C17
0x1800178a3  sub     ax, 56h ; 'V'
0x1800178a7  mov     edx, 0FFDFh
0x1800178ac  test    dx, ax
0x1800178af  jnz     short loc_1800178B5
0x1800178b1  add     rdi, 2
0x1800178b5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800178b9  inc     rsi
0x1800178bc  cmp     [rdi+rsi*2], r13w
0x1800178c1  jnz     short loc_1800178B9
0x1800178c3  mov     r12d, [rcx+190h]
0x1800178ca  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\ASP.NET"
0x1800178d1  mov     eax, r12d
0x1800178d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800178db  neg     eax
0x1800178dd  lea     rax, [rsp+780h+hKey]
0x1800178e2  sbb     r9d, r9d
0x1800178e5  mov     [rsp+780h+phkResult], rax; phkResult
0x1800178ea  and     r9d, r14d
0x1800178ed  xor     r8d, r8d; ulOptions
0x1800178f0  add     r9d, 0Ch; samDesired
0x1800178f4  call    cs:__imp_RegOpenKeyExW
0x1800178fa  test    eax, eax
0x1800178fc  jz      short loc_18001791D
0x1800178fe  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017905  jz      loc_180017C17
0x18001790b  lea     rax, aOpeningTheHklm; "Opening the 'HKLM\\Software\\Microsoft"...
0x180017912  mov     r8d, 1B14h
0x180017918  jmp     loc_180017BF2
0x18001791d  mov     r14d, r13d
0x180017920  mov     rax, [rbp+680h+lpName]
0x180017924  lea     r9, [rsp+780h+cchName]; lpcchName
0x180017929  mov     [rsp+780h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18001792e  mov     edx, r14d; dwIndex
0x180017931  mov     [rsp+780h+lpcchClass], r13; lpcchClass
0x180017936  mov     [rsp+780h+lpClass], r13; lpClass
0x18001793b  mov     [rax], r13w
0x18001793f  mov     eax, [rbp+680h+var_6D8]
0x180017942  mov     r8, [rbp+680h+lpName]; lpName
0x180017946  mov     rcx, [rsp+780h+hKey]; hKey
0x18001794b  shr     eax, 1
0x18001794d  mov     [rsp+780h+cchName], eax
0x180017951  mov     [rbp+680h+var_6D0], r13d
0x180017955  mov     [rsp+780h+phkResult], r13; lpReserved
0x18001795a  call    cs:__imp_RegEnumKeyExW
0x180017960  test    eax, eax
0x180017962  jnz     loc_180017BDC
0x180017968  mov     edx, [rsp+780h+cchName]
0x18001796c  lea     rcx, [rbp+680h+var_700]
0x180017970  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180017976  test    al, al
0x180017978  jz      loc_180017C17
0x18001797e  mov     eax, [rbp+680h+var_6D0]
0x180017981  cmp     rsi, rax
0x180017984  jnb     short loc_18001799A
0x180017986  mov     rdx, [rbp+680h+lpName]; String2
0x18001798a  mov     r8, rsi; MaxCount
0x18001798d  mov     rcx, rdi; String1
0x180017990  call    cs:__imp__wcsnicmp
0x180017996  test    eax, eax
0x180017998  jz      short loc_18001799F
0x18001799a  inc     r14d
0x18001799d  jmp     short loc_180017920
0x18001799f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ASP.NET\\"
0x1800179a6  lea     rcx, [rbp+680h+var_690]
0x1800179aa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800179b0  mov     ebx, eax
0x1800179b2  test    eax, eax
0x1800179b4  js      loc_180017C17
0x1800179ba  lea     rdx, [rbp+680h+var_700]
0x1800179be  lea     rcx, [rbp+680h+var_690]
0x1800179c2  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800179c8  mov     ebx, eax
0x1800179ca  test    eax, eax
0x1800179cc  js      loc_180017C17
0x1800179d2  mov     rdx, [rbp+680h+lpSubKey]; lpSubKey
0x1800179d6  lea     rax, [rsp+780h+var_718]
0x1800179db  neg     r12d
0x1800179de  mov     [rsp+780h+phkResult], rax; phkResult
0x1800179e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800179ea  sbb     r9d, r9d
0x1800179ed  xor     r8d, r8d; ulOptions
0x1800179f0  and     r9d, 200h
0x1800179f7  add     r9d, 4; samDesired
0x1800179fb  call    cs:__imp_RegOpenKeyExW
0x180017a01  test    eax, eax
0x180017a03  jz      short loc_180017A2D
0x180017a05  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017a0c  jz      loc_180017C17
0x180017a12  lea     rax, aFailedOpeningT; "Failed opening the version specific ASP"...
0x180017a19  mov     r8d, 1B5Fh
0x180017a1f  mov     [rsp+780h+lpClass], rax
0x180017a24  mov     dword ptr [rsp+780h+phkResult], ebx
0x180017a28  jmp     loc_180017BFC
0x180017a2d  mov     rcx, [rsp+780h+var_718]; hKey
0x180017a32  lea     rax, [rsp+780h+var_710]
0x180017a37  mov     [rsp+780h+lpdwDisposition], r13; lpdwDisposition
0x180017a3c  lea     rdx, aAutogenkeys; "AutoGenKeys"
0x180017a43  mov     [rsp+780h+lpftLastWriteTime], rax; phkResult
0x180017a48  xor     r9d, r9d; lpClass
0x180017a4b  mov     [rsp+780h+lpcchClass], r13; lpSecurityAttributes
0x180017a50  xor     r8d, r8d; Reserved
0x180017a53  mov     dword ptr [rsp+780h+lpClass], 2001Fh; samDesired
0x180017a5b  mov     dword ptr [rsp+780h+phkResult], r13d; dwOptions
0x180017a60  call    cs:__imp_RegCreateKeyExW
0x180017a66  test    eax, eax
0x180017a68  jz      short loc_180017A92
0x180017a6a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017a71  jz      loc_180017C17
0x180017a77  lea     rax, aFailedOpeningT_0; "Failed opening the version specific ASP"...
0x180017a7e  mov     r8d, 1B73h
0x180017a84  mov     [rsp+780h+lpClass], rax
0x180017a89  mov     dword ptr [rsp+780h+phkResult], ebx
0x180017a8d  jmp     loc_180017BFC
0x180017a92  mov     rdx, [r15+58h]
0x180017a96  lea     rax, [rsp+780h+dwDisposition]
0x180017a9b  mov     rcx, [rsp+780h+var_710]; hKey
0x180017aa0  xor     r9d, r9d; lpClass
0x180017aa3  mov     [rsp+780h+lpdwDisposition], rax; lpdwDisposition
0x180017aa8  xor     r8d, r8d; Reserved
0x180017aab  lea     rax, [rsp+780h+var_708]
0x180017ab0  mov     rdx, [rdx+0C0h]; lpSubKey
0x180017ab7  mov     [rsp+780h+lpftLastWriteTime], rax; phkResult
0x180017abc  mov     [rsp+780h+lpcchClass], r13; lpSecurityAttributes
0x180017ac1  mov     dword ptr [rsp+780h+lpClass], 40000h; samDesired
0x180017ac9  mov     dword ptr [rsp+780h+phkResult], r13d; dwOptions
0x180017ace  call    cs:__imp_RegCreateKeyExW
0x180017ad4  test    eax, eax
0x180017ad6  jz      short loc_180017B00
0x180017ad8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017adf  jz      loc_180017C17
0x180017ae5  lea     rax, aFailedCreating; "Failed creating the SID key under the A"...
0x180017aec  mov     r8d, 1B88h
0x180017af2  mov     [rsp+780h+lpClass], rax
0x180017af7  mov     dword ptr [rsp+780h+phkResult], ebx
0x180017afb  jmp     loc_180017BFC
0x180017b00  cmp     [rsp+780h+dwDisposition], 2
0x180017b05  jz      loc_180017C17
0x180017b0b  lea     rdx, aDPAOiciGaSyAOi; "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)"
0x180017b12  lea     rcx, [rbp+680h+var_6C8]
0x180017b16  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017b1c  mov     ebx, eax
0x180017b1e  test    eax, eax
0x180017b20  js      loc_180017C17
0x180017b26  mov     rax, [r15+58h]
0x180017b2a  cmp     [rax+0C0h], r13
0x180017b31  jz      short loc_180017B6D
0x180017b33  lea     rdx, aAOiciGa; "(A;OICI;GA;;;"
0x180017b3a  lea     rcx, [rbp+680h+var_6C8]
0x180017b3e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017b44  mov     ebx, eax
0x180017b46  test    eax, eax
0x180017b48  js      loc_180017C17
0x180017b4e  mov     rdx, [r15+58h]
0x180017b52  lea     rcx, [rbp+680h+var_6C8]
0x180017b56  mov     rdx, [rdx+0C0h]
0x180017b5d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017b63  mov     ebx, eax
0x180017b65  test    eax, eax
0x180017b67  js      loc_180017C17
0x180017b6d  lea     rdx, asc_180067C58; ")"
0x180017b74  lea     rcx, [rbp+680h+var_6C8]
0x180017b78  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017b7e  mov     ebx, eax
0x180017b80  test    eax, eax
0x180017b82  js      loc_180017C17
0x180017b88  mov     rcx, [rbp+680h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180017b8c  lea     r8, [rsp+780h+SecurityDescriptor]; SecurityDescriptor
0x180017b91  xor     r9d, r9d; SecurityDescriptorSize
0x180017b94  lea     edx, [r9+1]; StringSDRevision
0x180017b98  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180017b9e  test    eax, eax
0x180017ba0  jz      short loc_180017C17
0x180017ba2  mov     r8, [rsp+780h+SecurityDescriptor]; pSecurityDescriptor
0x180017ba7  mov     edx, 4; SecurityInformation
0x180017bac  mov     rcx, [rsp+780h+var_708]; hKey
0x180017bb1  call    cs:__imp_RegSetKeySecurity
0x180017bb7  test    eax, eax
0x180017bb9  jz      short loc_180017C17
0x180017bbb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017bc2  jz      short loc_180017C17
0x180017bc4  lea     rax, aErrorSettingTh; "Error setting the security for the ASP."...
0x180017bcb  mov     r8d, 1BC5h
0x180017bd1  mov     [rsp+780h+lpClass], rax
0x180017bd6  mov     dword ptr [rsp+780h+phkResult], ebx
0x180017bda  jmp     short loc_180017BFC
0x180017bdc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017be3  jz      short loc_180017C17
0x180017be5  lea     rax, aDoingAnEnumOnT; "Doing an enum on the 'HKLM\\Software\\M"...
0x180017bec  mov     r8d, 1B2Ch
0x180017bf2  mov     [rsp+780h+lpClass], rax
0x180017bf7  mov     dword ptr [rsp+780h+phkResult], r13d
0x180017bfc  mov     rcx, cs:g_pDebug
0x180017c03  lea     r9, aAppPoolEnsures; "APP_POOL::EnsureSharedMachineKeyStorage"
0x180017c0a  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017c11  call    cs:__imp_PuDbgPrintError
0x180017c17  mov     dword ptr [r15+1F8h], 1
0x180017c22  test    ebx, ebx
0x180017c24  jns     short loc_180017C60
0x180017c26  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017c2d  jz      short loc_180017C60
0x180017c2f  mov     rcx, cs:g_pDebug
0x180017c36  lea     rax, aFailureInCreat; "Failure in creating or securing the ASP"...
0x180017c3d  mov     [rsp+780h+lpClass], rax
0x180017c42  lea     r9, aAppPoolEnsures; "APP_POOL::EnsureSharedMachineKeyStorage"
0x180017c49  mov     r8d, 1BD3h
0x180017c4f  mov     dword ptr [rsp+780h+phkResult], ebx
0x180017c53  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017c5a  call    cs:__imp_PuDbgPrintError
0x180017c60  mov     rcx, [rsp+780h+SecurityDescriptor]; hMem
0x180017c65  test    rcx, rcx
0x180017c68  jz      short loc_180017C75
0x180017c6a  call    cs:__imp_LocalFree
0x180017c70  mov     [rsp+780h+SecurityDescriptor], r13
0x180017c75  mov     rcx, [rsp+780h+hKey]; hKey
0x180017c7a  test    rcx, rcx
0x180017c7d  jz      short loc_180017C8A
0x180017c7f  call    cs:__imp_RegCloseKey
0x180017c85  mov     [rsp+780h+hKey], r13
0x180017c8a  mov     rcx, [rsp+780h+var_718]; hKey
0x180017c8f  test    rcx, rcx
0x180017c92  jz      short loc_180017C9F
0x180017c94  call    cs:__imp_RegCloseKey
0x180017c9a  mov     [rsp+780h+var_718], r13
0x180017c9f  mov     rcx, [rsp+780h+var_710]; hKey
0x180017ca4  test    rcx, rcx
0x180017ca7  jz      short loc_180017CB4
0x180017ca9  call    cs:__imp_RegCloseKey
0x180017caf  mov     [rsp+780h+var_710], r13
0x180017cb4  mov     rcx, [rsp+780h+var_708]; hKey
0x180017cb9  test    rcx, rcx
0x180017cbc  jz      short loc_180017CC9
0x180017cbe  call    cs:__imp_RegCloseKey
0x180017cc4  mov     [rsp+780h+var_708], r13
0x180017cc9  lea     rcx, [rbp+680h+var_6C8]
0x180017ccd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017cd3  lea     rcx, [rbp+680h+var_690]
0x180017cd7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017cdd  lea     rcx, [rbp+680h+var_700]
0x180017ce1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017ce7  mov     rcx, [rbp+680h+var_50]
  ... truncated ...
```
