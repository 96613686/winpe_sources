# GetPhysicalNodeNameW(ushort * *)

- ea: `0x1800092f4`
- end: `0x18000964b`
- name: `?GetPhysicalNodeNameW@@YAJPEAPEAG@Z`
- size: `855`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008940`
- `0x180013694`
- `0x180015414`
- `0x180018188`
- `0x18001b5b0`
- `0x18004f994`
- `0x180052ad0`
- `0x180071fc8`
- `0x180072174`
- `0x1800761a0`
- `0x180076de0`

## callees

- `0x180003cf0`
- `0x1800092f4`
- `0x18000d5f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000952b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000952b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800094d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800095e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800094d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800095e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009613`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800095ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180009605`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800095ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180009605`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800093a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800093d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009404`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009439`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800094c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009513`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800093a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800093d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009404`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009439`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800094c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009513`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009371`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009371`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000953a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000953a`

## string_xrefs

- `0x1800094e7`: `(LPWSTR) CoTaskMemAlloc(CustomHostNameSize)`
- `0x18000963e`: `GetPhysicalNodeNameW (com\complus\dtc\shared\util\physnode.cpp@32): GetPhysicalNodeNameW - NULL != ppwszPhysicalNodeName`
- `0x180009465`: `Unsupported configuration: Custom hostname cannot be enabled with Mutual Authentication without schannel Mutual Authentication`
- `0x18000947c`: `com\complus\dtc\shared\util\physnode.cpp`
- `0x18000956c`: `com\complus\dtc\shared\util\physnode.cpp`
- `0x180009631`: `GetPhysicalNodeNameW (com\complus\dtc\shared\util\physnode.cpp@140): GetPhysicalNodeNameW - Unexpected - call to GetComputerNameExW with NULL pointer succeeded`

## pseudocode

```c
__int64 __fastcall GetPhysicalNodeNameW(BYTE **a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  BYTE *v4; // rdi
  const wchar_t *v5; // rax
  __int64 v6; // r9
  LSTATUS v7; // eax
  bool v9; // cf
  int v10; // esi
  signed int LastError; // eax
  WCHAR *v12; // rax
  signed int v13; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-40h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-40h]
  BYTE Data[4]; // [rsp+40h] [rbp-28h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-24h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-20h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-1Ch] BYREF
  DWORD v20; // [rsp+50h] [rbp-18h] BYREF
  DWORD v21; // [rsp+54h] [rbp-14h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-10h] BYREF
  int v23; // [rsp+A0h] [rbp+38h] BYREF
  int v24; // [rsp+A8h] [rbp+40h] BYREF
  int v25; // [rsp+B0h] [rbp+48h] BYREF
  DWORD v26; // [rsp+B8h] [rbp+50h] BYREF

  cbData = 4;
  nSize = 0;
  *(_DWORD *)Data = 0;
  v24 = 0;
  v19 = 4;
  v25 = 0;
  v20 = 4;
  v23 = 0;
  v21 = 4;
  v26 = 0;
  hKey = 0;
  if ( !a1 )
    DtcInternalErrorW(
      L"GetPhysicalNodeNameW (com\\complus\\dtc\\shared\\util\\physnode.cpp@32): GetPhysicalNodeNameW - NULL != ppwszPhysicalNodeName");
  *a1 = 0;
  v2 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSDTC", 0, 0x20119u, &hKey) )
  {
    if ( RegQueryValueExW(hKey, L"useFQDN", 0, 0, Data, &cbData) )
      *(_DWORD *)Data = 0;
    if ( RegQueryValueExW(hKey, L"useCustomHostName", 0, 0, (LPBYTE)&v24, &v19) )
      v24 = 0;
    if ( RegQueryValueExW(hKey, L"AllowOnlySecureRpcCalls", 0, 0, (LPBYTE)&v25, &v20) )
      v25 = 1;
    if ( RegQueryValueExW(hKey, L"AllowOnlySchannelSecureRpcCalls", 0, 0, (LPBYTE)&v23, &v21) )
    {
      v3 = 0;
      v23 = 0;
    }
    else
    {
      v3 = v23;
    }
    if ( v24 )
    {
      if ( v25 && !v3 )
      {
        v4 = 0;
        v5 = L"Unsupported configuration: Custom hostname cannot be enabled with Mutual Authentication without schannel Mu"
              "tual Authentication";
        v2 = -2147467263;
        v6 = 66;
LABEL_16:
        LODWORD(lpcbData) = v2;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\physnode.cpp",
          v6,
          L"GetPhysicalNodeNameW",
          lpcbData,
          v5);
        goto LABEL_24;
      }
      if ( !RegQueryValueExW(hKey, L"CustomHostName", 0, 0, 0, &v26) )
      {
        v4 = (BYTE *)CoTaskMemAlloc(v26);
        if ( !v4 )
        {
          v2 = -2147024882;
          v5 = L"(LPWSTR) CoTaskMemAlloc(CustomHostNameSize)";
          v6 = 82;
          goto LABEL_16;
        }
        v7 = RegQueryValueExW(hKey, L"CustomHostName", 0, 0, v4, &v26);
        v2 = v7;
        if ( !v7 )
        {
          v2 = 0;
LABEL_22:
          *a1 = v4;
LABEL_23:
          v4 = 0;
          goto LABEL_24;
        }
        if ( v7 > 0 )
          v2 = (unsigned __int16)v7 | 0x80070000;
        LODWORD(lpcbDataa) = v2;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\physnode.cpp",
          98,
          L"GetPhysicalNodeNameW",
          lpcbDataa,
          L"RegQueryValueExW(hkey, CustomHostNameKey, NULL, NULL, (LPBYTE)wszNodeName, &CustomHostNameSize)");
        CoTaskMemFree(v4);
      }
    }
  }
  v9 = *(_DWORD *)Data != 0;
  *a1 = 0;
  v10 = v9 ? 3 : 0;
  if ( GetComputerNameExW((COMPUTER_NAME_FORMAT)(v10 + 4), 0, &nSize) )
    DtcInternalErrorW(
      L"GetPhysicalNodeNameW (com\\complus\\dtc\\shared\\util\\physnode.cpp@140): GetPhysicalNodeNameW - Unexpected - call"
       " to GetComputerNameExW with NULL pointer succeeded");
  LastError = GetLastError();
  if ( LastError != 234 )
  {
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    else
      v2 = LastError;
    goto LABEL_23;
  }
  v12 = (WCHAR *)CoTaskMemAlloc(2LL * nSize);
  v4 = (BYTE *)v12;
  if ( v12 )
  {
    if ( GetComputerNameExW((COMPUTER_NAME_FORMAT)(v10 + 4), v12, &nSize) )
      goto LABEL_22;
    v13 = GetLastError();
    v2 = v13;
    if ( v13 > 0 )
      v2 = (unsigned __int16)v13 | 0x80070000;
  }
  else
  {
    v2 = -2147024882;
  }
LABEL_24:
  CoTaskMemFree(v4);
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800092f4  push    rbp
0x1800092f6  push    rbx
0x1800092f7  push    rsi
0x1800092f8  push    rdi
0x1800092f9  push    r14
0x1800092fb  push    r15
0x1800092fd  mov     rbp, rsp
0x180009300  sub     rsp, 68h
0x180009304  xor     r15d, r15d
0x180009307  mov     [rbp+cbData], 4
0x18000930e  mov     [rbp+nSize], r15d
0x180009312  mov     r14, rcx
0x180009315  mov     dword ptr [rbp+Data], r15d
0x180009319  mov     [rbp+arg_8], r15d
0x18000931d  mov     [rbp+var_1C], 4
0x180009324  mov     [rbp+arg_10], r15d
0x180009328  mov     [rbp+var_18], 4
0x18000932f  mov     [rbp+arg_0], r15d
0x180009333  mov     [rbp+var_14], 4
0x18000933a  mov     [rbp+arg_18], r15d
0x18000933e  mov     [rbp+hKey], r15
0x180009342  test    rcx, rcx
0x180009345  jz      loc_18000963E
0x18000934b  mov     [rcx], r15
0x18000934e  lea     rax, [rbp+hKey]
0x180009352  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009359  mov     [rsp+68h+phkResult], rax; phkResult
0x18000935e  mov     r9d, 20119h; samDesired
0x180009364  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\MSDTC"
0x18000936b  xor     r8d, r8d; ulOptions
0x18000936e  mov     ebx, r15d
0x180009371  call    cs:__imp_RegOpenKeyExW
0x180009377  test    eax, eax
0x180009379  jnz     loc_180009597
0x18000937f  mov     rcx, [rbp+hKey]; hKey
0x180009383  lea     rax, [rbp+cbData]
0x180009387  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000938c  lea     rdx, aUsefqdn; "useFQDN"
0x180009393  lea     rax, [rbp+Data]
0x180009397  xor     r9d, r9d; lpType
0x18000939a  xor     r8d, r8d; lpReserved
0x18000939d  mov     [rsp+68h+phkResult], rax; lpData
0x1800093a2  call    cs:__imp_RegQueryValueExW
0x1800093a8  test    eax, eax
0x1800093aa  jz      short loc_1800093B0
0x1800093ac  mov     dword ptr [rbp+Data], r15d
0x1800093b0  mov     rcx, [rbp+hKey]; hKey
0x1800093b4  lea     rax, [rbp+var_1C]
0x1800093b8  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800093bd  lea     rdx, aUsecustomhostn; "useCustomHostName"
0x1800093c4  lea     rax, [rbp+arg_8]
0x1800093c8  xor     r9d, r9d; lpType
0x1800093cb  xor     r8d, r8d; lpReserved
0x1800093ce  mov     [rsp+68h+phkResult], rax; lpData
0x1800093d3  call    cs:__imp_RegQueryValueExW
0x1800093d9  test    eax, eax
0x1800093db  jz      short loc_1800093E1
0x1800093dd  mov     [rbp+arg_8], r15d
0x1800093e1  mov     rcx, [rbp+hKey]; hKey
0x1800093e5  lea     rax, [rbp+var_18]
0x1800093e9  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800093ee  lea     rdx, aAllowonlysecur; "AllowOnlySecureRpcCalls"
0x1800093f5  lea     rax, [rbp+arg_10]
0x1800093f9  xor     r9d, r9d; lpType
0x1800093fc  xor     r8d, r8d; lpReserved
0x1800093ff  mov     [rsp+68h+phkResult], rax; lpData
0x180009404  call    cs:__imp_RegQueryValueExW
0x18000940a  mov     esi, 1
0x18000940f  test    eax, eax
0x180009411  jz      short loc_180009416
0x180009413  mov     [rbp+arg_10], esi
0x180009416  mov     rcx, [rbp+hKey]; hKey
0x18000941a  lea     rax, [rbp+var_14]
0x18000941e  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180009423  lea     rdx, aAllowonlyschan; "AllowOnlySchannelSecureRpcCalls"
0x18000942a  lea     rax, [rbp+arg_0]
0x18000942e  xor     r9d, r9d; lpType
0x180009431  xor     r8d, r8d; lpReserved
0x180009434  mov     [rsp+68h+phkResult], rax; lpData
0x180009439  call    cs:__imp_RegQueryValueExW
0x18000943f  test    eax, eax
0x180009441  jz      short loc_18000944B
0x180009443  mov     eax, r15d
0x180009446  mov     [rbp+arg_0], eax
0x180009449  jmp     short loc_18000944E
0x18000944b  mov     eax, [rbp+arg_0]
0x18000944e  cmp     [rbp+arg_8], r15d
0x180009452  jz      loc_180009597
0x180009458  cmp     [rbp+arg_10], r15d
0x18000945c  jz      short loc_1800094A4
0x18000945e  test    eax, eax
0x180009460  jnz     short loc_1800094A4
0x180009462  mov     rdi, r15
0x180009465  lea     rax, aUnsupportedCon; "Unsupported configuration: Custom hostn"...
0x18000946c  mov     ebx, 80004001h
0x180009471  mov     r9d, 42h ; 'B'
0x180009477  mov     [rsp+68h+var_38], rax
0x18000947c  lea     r8, aComComplusDtcS_11; "com\\complus\\dtc\\shared\\util\\physno"...
0x180009483  lea     rax, aGetphysicalnod_1; "GetPhysicalNodeNameW"
0x18000948a  mov     dword ptr [rsp+68h+lpcbData], ebx
0x18000948e  mov     edx, esi
0x180009490  mov     [rsp+68h+phkResult], rax
0x180009495  mov     ecx, 7
0x18000949a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000949f  jmp     loc_180009528
0x1800094a4  mov     rcx, [rbp+hKey]; hKey
0x1800094a8  lea     rax, [rbp+arg_18]
0x1800094ac  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800094b1  lea     rdx, aCustomhostname; "CustomHostName"
0x1800094b8  xor     r9d, r9d; lpType
0x1800094bb  mov     [rsp+68h+phkResult], r15; lpData
0x1800094c0  xor     r8d, r8d; lpReserved
0x1800094c3  call    cs:__imp_RegQueryValueExW
0x1800094c9  test    eax, eax
0x1800094cb  jnz     loc_180009597
0x1800094d1  mov     ecx, [rbp+arg_18]; cb
0x1800094d4  call    cs:__imp_CoTaskMemAlloc
0x1800094da  mov     rdi, rax
0x1800094dd  test    rax, rax
0x1800094e0  jnz     short loc_1800094F4
0x1800094e2  mov     ebx, 8007000Eh
0x1800094e7  lea     rax, aLpwstrCotaskme; "(LPWSTR) CoTaskMemAlloc(CustomHostNameS"...
0x1800094ee  lea     r9d, [rdi+52h]
0x1800094f2  jmp     short loc_180009477
0x1800094f4  mov     rcx, [rbp+hKey]; hKey
0x1800094f8  lea     rax, [rbp+arg_18]
0x1800094fc  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180009501  lea     rdx, aCustomhostname; "CustomHostName"
0x180009508  xor     r9d, r9d; lpType
0x18000950b  mov     [rsp+68h+phkResult], rdi; lpData
0x180009510  xor     r8d, r8d; lpReserved
0x180009513  call    cs:__imp_RegQueryValueExW
0x180009519  mov     ebx, eax
0x18000951b  test    eax, eax
0x18000951d  jnz     short loc_18000954F
0x18000951f  mov     ebx, r15d
0x180009522  mov     [r14], rdi
0x180009525  mov     rdi, r15
0x180009528  mov     rcx, rdi; pv
0x18000952b  call    cs:__imp_CoTaskMemFree
0x180009531  mov     rcx, [rbp+hKey]; hKey
0x180009535  test    rcx, rcx
0x180009538  jz      short loc_180009540
0x18000953a  call    cs:__imp_RegCloseKey
0x180009540  mov     eax, ebx
0x180009542  add     rsp, 68h
0x180009546  pop     r15
0x180009548  pop     r14
0x18000954a  pop     rdi
0x18000954b  pop     rsi
0x18000954c  pop     rbx
0x18000954d  pop     rbp
0x18000954e  retn
0x18000954f  jle     short loc_18000955A
0x180009551  movzx   ebx, ax
0x180009554  or      ebx, 80070000h
0x18000955a  mov     r9d, 62h ; 'b'
0x180009560  lea     rax, aRegqueryvaluee_0; "RegQueryValueExW(hkey, CustomHostNameKe"...
0x180009567  mov     [rsp+68h+var_38], rax
0x18000956c  lea     r8, aComComplusDtcS_11; "com\\complus\\dtc\\shared\\util\\physno"...
0x180009573  lea     rax, aGetphysicalnod_1; "GetPhysicalNodeNameW"
0x18000957a  mov     dword ptr [rsp+68h+lpcbData], ebx
0x18000957e  mov     edx, esi
0x180009580  mov     [rsp+68h+phkResult], rax
0x180009585  lea     ecx, [r9-5Bh]
0x180009589  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000958e  mov     rcx, rdi; pv
0x180009591  call    cs:__imp_CoTaskMemFree
0x180009597  mov     eax, dword ptr [rbp+Data]
0x18000959a  lea     r8, [rbp+nSize]; nSize
0x18000959e  neg     eax
0x1800095a0  mov     [r14], r15
0x1800095a3  sbb     esi, esi
0x1800095a5  xor     edx, edx; lpBuffer
0x1800095a7  and     esi, 3
0x1800095aa  lea     ecx, [rsi+4]; NameType
0x1800095ad  call    cs:__imp_GetComputerNameExW
0x1800095b3  test    eax, eax
0x1800095b5  jnz     short loc_180009631
0x1800095b7  call    cs:__imp_GetLastError
0x1800095bd  cmp     eax, 0EAh
0x1800095c2  jz      short loc_1800095DD
0x1800095c4  test    eax, eax
0x1800095c6  jg      short loc_1800095CF
0x1800095c8  mov     ebx, eax
0x1800095ca  jmp     loc_180009525
0x1800095cf  movzx   ebx, ax
0x1800095d2  or      ebx, 80070000h
0x1800095d8  jmp     loc_180009525
0x1800095dd  mov     ecx, [rbp+nSize]
0x1800095e0  add     rcx, rcx; cb
0x1800095e3  call    cs:__imp_CoTaskMemAlloc
0x1800095e9  mov     rdi, rax
0x1800095ec  test    rax, rax
0x1800095ef  jnz     short loc_1800095FB
0x1800095f1  mov     ebx, 8007000Eh
0x1800095f6  jmp     loc_180009528
0x1800095fb  lea     r8, [rbp+nSize]; nSize
0x1800095ff  mov     rdx, rdi; lpBuffer
0x180009602  lea     ecx, [rsi+4]; NameType
0x180009605  call    cs:__imp_GetComputerNameExW
0x18000960b  test    eax, eax
0x18000960d  jnz     loc_180009522
0x180009613  call    cs:__imp_GetLastError
0x180009619  mov     ebx, eax
0x18000961b  test    eax, eax
0x18000961d  jle     loc_180009528
0x180009623  movzx   ebx, ax
0x180009626  or      ebx, 80070000h
0x18000962c  jmp     loc_180009528
0x180009631  lea     rcx, aGetphysicalnod_3; "GetPhysicalNodeNameW (com\\complus\\dtc"...
0x180009638  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000963e  lea     rcx, aGetphysicalnod_2; "GetPhysicalNodeNameW (com\\complus\\dtc"...
0x180009645  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
