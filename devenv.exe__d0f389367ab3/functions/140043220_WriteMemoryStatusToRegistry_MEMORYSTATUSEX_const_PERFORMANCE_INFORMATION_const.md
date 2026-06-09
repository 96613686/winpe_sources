# WriteMemoryStatusToRegistry(_MEMORYSTATUSEX const &,_PERFORMANCE_INFORMATION const &)

- ea: `0x140043220`
- end: `0x140043570`
- name: `?WriteMemoryStatusToRegistry@@YAXAEBU_MEMORYSTATUSEX@@AEBU_PERFORMANCE_INFORMATION@@@Z`
- size: `848`
- prototype: `void __fastcall(const struct _MEMORYSTATUSEX *, const struct _PERFORMANCE_INFORMATION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140043800`

## callees

- `0x140001020`
- `0x14001e9e0`
- `0x140043220`
- `0x14006a8ec`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140043543`
- `ADVAPI32!RegCloseKey` at `0x140043543`
- `ADVAPI32!RegCreateKeyExW` at `0x14004330b`
- `ADVAPI32!RegCreateKeyExW` at `0x14004330b`
- `ADVAPI32!RegSetValueExW` at `0x140043351`
- `ADVAPI32!RegSetValueExW` at `0x140043395`
- `ADVAPI32!RegSetValueExW` at `0x1400433c6`
- `ADVAPI32!RegSetValueExW` at `0x1400433f7`
- `ADVAPI32!RegSetValueExW` at `0x140043428`
- `ADVAPI32!RegSetValueExW` at `0x140043459`
- `ADVAPI32!RegSetValueExW` at `0x1400434ec`
- `ADVAPI32!RegSetValueExW` at `0x140043528`
- `ADVAPI32!RegSetValueExW` at `0x140043351`
- `ADVAPI32!RegSetValueExW` at `0x140043395`
- `ADVAPI32!RegSetValueExW` at `0x1400433c6`
- `ADVAPI32!RegSetValueExW` at `0x1400433f7`
- `ADVAPI32!RegSetValueExW` at `0x140043428`
- `ADVAPI32!RegSetValueExW` at `0x140043459`
- `ADVAPI32!RegSetValueExW` at `0x1400434ec`
- `ADVAPI32!RegSetValueExW` at `0x140043528`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400434fd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400434fd`
- `KERNEL32!GetCurrentProcessId` at `0x14004328a`
- `KERNEL32!GetCurrentProcessId` at `0x14004328a`
- `OLEAUT32!__imp_SysFreeString` at `0x140043534`
- `OLEAUT32!__imp_SysFreeString` at `0x140043534`
- `OLEAUT32!__imp_SysStringLen` at `0x140043323`
- `OLEAUT32!__imp_SysStringLen` at `0x140043323`

## string_xrefs

- `0x1400432ac`: `Software\Microsoft\VSCommon`
- `0x14004338b`: `PeakPageFileCommitMB`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WriteMemoryStatusToRegistry(const struct _MEMORYSTATUSEX *a1, struct _PERFORMANCE_INFORMATION *a2)
{
  HKEY v4; // rbx
  UINT v5; // eax
  SIZE_T v6; // rdx
  double v7; // xmm0_8
  SIZE_T v8; // rcx
  double v9; // xmm1_8
  DWORD lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  v4 = 0;
  pbstr = 0;
  if ( (int)TelemetryHelper::GetSessionId((TelemetryHelper *)&pbstr, (unsigned __int16 **)a2) >= 0 )
  {
    lpSecurityAttributes = GetCurrentProcessId();
    if ( (int)StringCchPrintfW(
                SubKey,
                0x104u,
                L"%s\\%s\\%s\\%d",
                L"Software\\Microsoft\\VSCommon",
                L"17.0",
                L"VSMEMDATA\\PIDS",
                lpSecurityAttributes) >= 0 )
    {
      hKey = 0;
      if ( !RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition) )
      {
        v4 = hKey;
        v5 = SysStringLen(pbstr);
        if ( !RegSetValueExW(v4, L"VSInstanceId", 0, 1u, (const BYTE *)pbstr, 2 * v5 + 2) )
        {
          dwDisposition = (a2->PageSize * a2->CommitPeak) >> 20;
          RegSetValueExW(v4, L"PeakPageFileCommitMB", 0, 4u, (const BYTE *)&dwDisposition, 4u);
          dwDisposition = a1->ullAvailPageFile >> 20;
          RegSetValueExW(v4, L"AvailablePageFileMB", 0, 4u, (const BYTE *)&dwDisposition, 4u);
          dwDisposition = a1->ullTotalPageFile >> 20;
          RegSetValueExW(v4, L"TotalPageFileMB", 0, 4u, (const BYTE *)&dwDisposition, 4u);
          dwDisposition = a1->ullAvailPhys >> 20;
          RegSetValueExW(v4, L"AvailablePhysicalMemoryMB", 0, 4u, (const BYTE *)&dwDisposition, 4u);
          dwDisposition = a1->ullTotalPhys >> 20;
          RegSetValueExW(v4, L"TotalPhysicalMemoryMB", 0, 4u, (const BYTE *)&dwDisposition, 4u);
          v6 = a2->CommitPeak * a2->PageSize;
          if ( (v6 & 0x8000000000000000uLL) != 0LL )
            v7 = (double)(int)(v6 & 1 | (v6 >> 1)) + (double)(int)(v6 & 1 | (v6 >> 1));
          else
            v7 = (double)(int)v6;
          v8 = a2->CommitLimit * a2->PageSize;
          if ( (v8 & 0x8000000000000000uLL) != 0LL )
            v9 = (double)(int)(v8 & 1 | (v8 >> 1)) + (double)(int)(v8 & 1 | (v8 >> 1));
          else
            v9 = (double)(int)v8;
          dwDisposition = (int)(v7 / v9 * 100.0);
          RegSetValueExW(v4, L"ResourceUsagePercent", 0, 4u, (const BYTE *)&dwDisposition, 4u);
          hKey = 0;
          GetSystemTimeAsFileTime((LPFILETIME)&hKey);
          RegSetValueExW(v4, L"CollectionTime", 0, 0xBu, (const BYTE *)&hKey, 8u);
        }
      }
    }
  }
  SysFreeString(pbstr);
  if ( v4 )
    RegCloseKey(v4);
}

```

## disassembly

```asm
0x140043220  mov     [rsp-8+arg_10], rbx
0x140043225  mov     [rsp-8+arg_18], rsi
0x14004322a  push    rbp
0x14004322b  push    rdi
0x14004322c  push    r15
0x14004322e  lea     rbp, [rsp-1A0h]
0x140043236  sub     rsp, 2A0h
0x14004323d  mov     rax, cs:__security_cookie
0x140043244  xor     rax, rsp
0x140043247  mov     [rbp+1B0h+var_20], rax
0x14004324e  mov     rdi, rdx
0x140043251  mov     rsi, rcx
0x140043254  xorps   xmm0, xmm0
0x140043257  xor     eax, eax
0x140043259  movups  [rsp+2B0h+var_260], xmm0
0x14004325e  mov     [rsp+2B0h+var_250], rax
0x140043263  xor     ebx, ebx
0x140043265  mov     qword ptr [rsp+2B0h+var_260], rbx
0x14004326a  and     dword ptr [rsp+2B0h+var_260+8], eax
0x14004326e  and     [rsp+2B0h+var_250], rax
0x140043273  and     [rsp+2B0h+pbstr], rbx
0x140043278  lea     rcx, [rsp+2B0h+pbstr]; this
0x14004327d  call    ?GetSessionId@TelemetryHelper@@YAJPEAPEAG@Z; TelemetryHelper::GetSessionId(ushort * *)
0x140043282  test    eax, eax
0x140043284  js      loc_14004352F
0x14004328a  call    cs:__imp_GetCurrentProcessId
0x140043290  mov     dword ptr [rsp+2B0h+lpSecurityAttributes], eax; lpSecurityAttributes
0x140043294  lea     rax, aVsmemdataPids; "VSMEMDATA\\PIDS"
0x14004329b  mov     qword ptr [rsp+2B0h+samDesired], rax
0x1400432a0  lea     rax, dwOptions; "17.0"
0x1400432a7  mov     qword ptr [rsp+2B0h+dwOptions], rax; dwOptions
0x1400432ac  lea     r9, aSoftwareMicros_18; "Software\\Microsoft\\VSCommon"
0x1400432b3  lea     r8, aSSSD; "%s\\%s\\%s\\%d"
0x1400432ba  mov     edx, 104h; unsigned __int64
0x1400432bf  lea     rcx, [rbp+1B0h+SubKey]; Buffer
0x1400432c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400432c8  test    eax, eax
0x1400432ca  js      loc_14004352F
0x1400432d0  and     [rsp+2B0h+hKey], rbx
0x1400432d5  lea     rax, [rsp+2B0h+dwDisposition]
0x1400432da  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x1400432df  lea     rax, [rsp+2B0h+hKey]
0x1400432e4  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1400432e9  and     [rsp+2B0h+lpSecurityAttributes], rbx
0x1400432ee  mov     [rsp+2B0h+samDesired], 2001Fh; samDesired
0x1400432f6  and     [rsp+2B0h+dwOptions], ebx
0x1400432fa  xor     r9d, r9d; lpClass
0x1400432fd  xor     r8d, r8d; Reserved
0x140043300  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x140043304  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004330b  call    cs:__imp_RegCreateKeyExW
0x140043311  test    eax, eax
0x140043313  jnz     loc_14004352F
0x140043319  mov     rbx, [rsp+2B0h+hKey]
0x14004331e  mov     rcx, [rsp+2B0h+pbstr]; pbstr
0x140043323  call    cs:__imp_SysStringLen
0x140043329  lea     eax, ds:2[rax*2]
0x140043330  mov     [rsp+2B0h+samDesired], eax; cbData
0x140043334  mov     rax, [rsp+2B0h+pbstr]
0x140043339  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x14004333e  mov     r9d, 1; dwType
0x140043344  xor     r8d, r8d; Reserved
0x140043347  lea     rdx, aVsinstanceid; "VSInstanceId"
0x14004334e  mov     rcx, rbx; hKey
0x140043351  call    cs:__imp_RegSetValueExW
0x140043357  test    eax, eax
0x140043359  jnz     loc_14004352F
0x14004335f  mov     rax, [rdi+18h]
0x140043363  imul    rax, [rdi+50h]
0x140043368  shr     rax, 14h
0x14004336c  mov     [rsp+2B0h+dwDisposition], eax
0x140043370  mov     r15d, 4
0x140043376  mov     [rsp+2B0h+samDesired], r15d; cbData
0x14004337b  lea     rax, [rsp+2B0h+dwDisposition]
0x140043380  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x140043385  mov     r9d, r15d; dwType
0x140043388  xor     r8d, r8d; Reserved
0x14004338b  lea     rdx, aPeakpagefileco; "PeakPageFileCommitMB"
0x140043392  mov     rcx, rbx; hKey
0x140043395  call    cs:__imp_RegSetValueExW
0x14004339b  mov     rax, [rsi+20h]
0x14004339f  shr     rax, 14h
0x1400433a3  mov     [rsp+2B0h+dwDisposition], eax
0x1400433a7  mov     [rsp+2B0h+samDesired], r15d; cbData
0x1400433ac  lea     rax, [rsp+2B0h+dwDisposition]
0x1400433b1  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1400433b6  mov     r9d, r15d; dwType
0x1400433b9  xor     r8d, r8d; Reserved
0x1400433bc  lea     rdx, aAvailablepagef; "AvailablePageFileMB"
0x1400433c3  mov     rcx, rbx; hKey
0x1400433c6  call    cs:__imp_RegSetValueExW
0x1400433cc  mov     rax, [rsi+18h]
0x1400433d0  shr     rax, 14h
0x1400433d4  mov     [rsp+2B0h+dwDisposition], eax
0x1400433d8  mov     [rsp+2B0h+samDesired], r15d; cbData
0x1400433dd  lea     rax, [rsp+2B0h+dwDisposition]
0x1400433e2  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1400433e7  mov     r9d, r15d; dwType
0x1400433ea  xor     r8d, r8d; Reserved
0x1400433ed  lea     rdx, aTotalpagefilem; "TotalPageFileMB"
0x1400433f4  mov     rcx, rbx; hKey
0x1400433f7  call    cs:__imp_RegSetValueExW
0x1400433fd  mov     rax, [rsi+10h]
0x140043401  shr     rax, 14h
0x140043405  mov     [rsp+2B0h+dwDisposition], eax
0x140043409  mov     [rsp+2B0h+samDesired], r15d; cbData
0x14004340e  lea     rax, [rsp+2B0h+dwDisposition]
0x140043413  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x140043418  mov     r9d, r15d; dwType
0x14004341b  xor     r8d, r8d; Reserved
0x14004341e  lea     rdx, aAvailablephysi; "AvailablePhysicalMemoryMB"
0x140043425  mov     rcx, rbx; hKey
0x140043428  call    cs:__imp_RegSetValueExW
0x14004342e  mov     rax, [rsi+8]
0x140043432  shr     rax, 14h
0x140043436  mov     [rsp+2B0h+dwDisposition], eax
0x14004343a  mov     [rsp+2B0h+samDesired], r15d; cbData
0x14004343f  lea     rax, [rsp+2B0h+dwDisposition]
0x140043444  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x140043449  mov     r9d, r15d; dwType
0x14004344c  xor     r8d, r8d; Reserved
0x14004344f  lea     rdx, aTotalphysicalm; "TotalPhysicalMemoryMB"
0x140043456  mov     rcx, rbx; hKey
0x140043459  call    cs:__imp_RegSetValueExW
0x14004345f  mov     rcx, [rdi+50h]
0x140043463  mov     rdx, rcx
0x140043466  imul    rdx, [rdi+18h]
0x14004346b  xorps   xmm0, xmm0
0x14004346e  test    rdx, rdx
0x140043471  js      short loc_14004347A
0x140043473  cvtsi2sd xmm0, rdx
0x140043478  jmp     short loc_14004348F
0x14004347a  mov     rax, rdx
0x14004347d  shr     rax, 1
0x140043480  and     edx, 1
0x140043483  or      rax, rdx
0x140043486  cvtsi2sd xmm0, rax
0x14004348b  addsd   xmm0, xmm0
0x14004348f  imul    rcx, [rdi+10h]
0x140043494  xorps   xmm1, xmm1
0x140043497  test    rcx, rcx
0x14004349a  js      short loc_1400434A3
0x14004349c  cvtsi2sd xmm1, rcx
0x1400434a1  jmp     short loc_1400434B8
0x1400434a3  mov     rax, rcx
0x1400434a6  shr     rax, 1
0x1400434a9  and     ecx, 1
0x1400434ac  or      rax, rcx
0x1400434af  cvtsi2sd xmm1, rax
0x1400434b4  addsd   xmm1, xmm1
0x1400434b8  divsd   xmm0, xmm1
0x1400434bc  mulsd   xmm0, cs:__real@4059000000000000
0x1400434c4  cvttsd2si rax, xmm0
0x1400434c9  mov     [rsp+2B0h+dwDisposition], eax
0x1400434cd  mov     [rsp+2B0h+samDesired], r15d; cbData
0x1400434d2  lea     rax, [rsp+2B0h+dwDisposition]
0x1400434d7  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1400434dc  mov     r9d, r15d; dwType
0x1400434df  xor     r8d, r8d; Reserved
0x1400434e2  lea     rdx, aResourceusagep; "ResourceUsagePercent"
0x1400434e9  mov     rcx, rbx; hKey
0x1400434ec  call    cs:__imp_RegSetValueExW
0x1400434f2  and     [rsp+2B0h+hKey], 0
0x1400434f8  lea     rcx, [rsp+2B0h+hKey]; lpSystemTimeAsFileTime
0x1400434fd  call    cs:__imp_GetSystemTimeAsFileTime
0x140043503  mov     [rsp+2B0h+samDesired], 8; cbData
0x14004350b  lea     rax, [rsp+2B0h+hKey]
0x140043510  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x140043515  mov     r9d, 0Bh; dwType
0x14004351b  xor     r8d, r8d; Reserved
0x14004351e  lea     rdx, aCollectiontime; "CollectionTime"
0x140043525  mov     rcx, rbx; hKey
0x140043528  call    cs:__imp_RegSetValueExW
0x14004352e  nop
0x14004352f  mov     rcx, [rsp+2B0h+pbstr]; bstrString
0x140043534  call    cs:__imp_SysFreeString
0x14004353a  test    rbx, rbx
0x14004353d  jz      short loc_140043549
0x14004353f  nop
0x140043540  mov     rcx, rbx; hKey
0x140043543  call    cs:__imp_RegCloseKey
0x140043549  mov     rcx, [rbp+1B0h+var_20]
0x140043550  xor     rcx, rsp; StackCookie
0x140043553  call    __security_check_cookie
0x140043558  lea     r11, [rsp+2B0h+var_10]
0x140043560  mov     rbx, [r11+30h]
0x140043564  mov     rsi, [r11+38h]
0x140043568  mov     rsp, r11
0x14004356b  pop     r15
0x14004356d  pop     rdi
0x14004356e  pop     rbp
0x14004356f  retn
```
