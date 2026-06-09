# IsCompatibleHostingModelEnabled(ushort const *,int &)

- ea: `0x180085530`
- end: `0x1800857d4`
- name: `?IsCompatibleHostingModelEnabled@@YAJPEBGAEAH@Z`
- size: `676`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180085820`

## callees

- `0x180085530`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800855b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008561b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008568e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800856f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085778`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800855b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008561b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008568e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800856f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085778`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008557b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800855ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085660`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800856c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008573a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008557b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800855ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085660`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800856c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008573a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800855be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008569a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085703`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085784`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800855be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008569a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085703`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085784`

## string_xrefs

- `0x180085656`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`
- `0x1800856bf`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`

## pseudocode

```c
__int64 __fastcall IsCompatibleHostingModelEnabled(const unsigned __int16 *a1, int *a2)
{
  BOOL v3; // edi
  LSTATUS v4; // ebx
  LSTATUS v5; // ebx
  LSTATUS v7; // ebx
  LSTATUS v8; // ebx
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  LSTATUS v11; // esi
  int v12; // ebx
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  int v15; // [rsp+84h] [rbp+44h]
  DWORD Type; // [rsp+90h] [rbp+50h] BYREF
  int Data; // [rsp+98h] [rbp+58h] BYREF

  v15 = HIDWORD(a1);
  Type = 0;
  hKey[0] = 0;
  cbData = 0;
  v3 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20019u, hKey)
    && ((cbData = 0, v4 = RegQueryValueExW(hKey[0], L"WMIRefresher", 0, &Type, 0, &cbData), RegCloseKey(hKey[0]), !v4)
     || v4 == 234)
    && Type == 1
    || !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20219u, hKey)
    && ((cbData = 0, v5 = RegQueryValueExW(hKey[0], L"WMIRefresher", 0, &Type, 0, &cbData), RegCloseKey(hKey[0]), !v5)
     || v5 == 234)
    && Type == 1 )
  {
    *a2 = 0;
    return 0;
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20019u,
          hKey)
    && ((cbData = 0, v7 = RegQueryValueExW(hKey[0], L"WMIRefresher", 0, &Type, 0, &cbData), RegCloseKey(hKey[0]), !v7)
     || v7 == 234)
    && Type == 1
    || !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20219u,
          hKey)
    && ((cbData = 0, v8 = RegQueryValueExW(hKey[0], L"WMIRefresher", 0, &Type, 0, &cbData), RegCloseKey(hKey[0]), !v8)
     || v8 == 234)
    && Type == 1 )
  {
    *a2 = 1;
    return 0;
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, hKey);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 <= 0 )
      return v10;
    v12 = (unsigned __int16)v9;
    return v12 | 0x80070000;
  }
  Data = 0;
  cbData = 4;
  v10 = 0;
  v11 = RegQueryValueExW(hKey[0], L"DefaultSecuredHost", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey[0]);
  if ( !v11 )
  {
    if ( Type == 4 )
      v3 = Data == 0;
    goto LABEL_25;
  }
  if ( v11 != 2 )
  {
    if ( v11 <= 0 )
      return (unsigned int)v11;
    v12 = (unsigned __int16)v11;
    return v12 | 0x80070000;
  }
LABEL_25:
  *a2 = v3;
  return v10;
}

```

## disassembly

```asm
0x180085530  mov     qword ptr [rsp-38h+cbData], rcx
0x180085535  push    rbp
0x180085536  push    rbx
0x180085537  push    rsi
0x180085538  push    rdi
0x180085539  push    r12
0x18008553b  push    r14
0x18008553d  push    r15
0x18008553f  mov     rbp, rsp
0x180085542  sub     rsp, 40h
0x180085546  xor     r15d, r15d
0x180085549  lea     rax, [rbp+hKey]
0x18008554d  mov     r14, rdx
0x180085550  mov     [rbp+Type], r15d
0x180085554  mov     r12, 0FFFFFFFF80000002h
0x18008555b  mov     [rbp+hKey], r15
0x18008555f  mov     rcx, r12; hKey
0x180085562  mov     [rbp+cbData], r15d
0x180085566  mov     r9d, 20019h; samDesired
0x18008556c  mov     [rsp+40h+phkResult], rax; phkResult
0x180085571  xor     r8d, r8d; ulOptions
0x180085574  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x18008557b  call    cs:__imp_RegOpenKeyExW
0x180085581  lea     edi, [r15+1]
0x180085585  mov     esi, 0EAh
0x18008558a  test    eax, eax
0x18008558c  jnz     short loc_1800855D1
0x18008558e  mov     rcx, [rbp+hKey]; hKey
0x180085592  lea     rax, [rbp+cbData]
0x180085596  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18008559b  lea     r9, [rbp+Type]; lpType
0x18008559f  xor     r8d, r8d; lpReserved
0x1800855a2  mov     [rsp+40h+phkResult], r15; lpData
0x1800855a7  lea     rdx, aWmirefresher; "WMIRefresher"
0x1800855ae  mov     [rbp+cbData], r15d
0x1800855b2  call    cs:__imp_RegQueryValueExW
0x1800855b8  mov     rcx, [rbp+hKey]; hKey
0x1800855bc  mov     ebx, eax
0x1800855be  call    cs:__imp_RegCloseKey
0x1800855c4  test    ebx, ebx
0x1800855c6  jz      short loc_1800855CC
0x1800855c8  cmp     ebx, esi
0x1800855ca  jnz     short loc_1800855D1
0x1800855cc  cmp     [rbp+Type], edi
0x1800855cf  jz      short loc_18008563A
0x1800855d1  lea     rax, [rbp+hKey]
0x1800855d5  mov     r9d, 20219h; samDesired
0x1800855db  xor     r8d, r8d; ulOptions
0x1800855de  mov     [rsp+40h+phkResult], rax; phkResult
0x1800855e3  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x1800855ea  mov     rcx, r12; hKey
0x1800855ed  call    cs:__imp_RegOpenKeyExW
0x1800855f3  test    eax, eax
0x1800855f5  jnz     short loc_180085644
0x1800855f7  mov     rcx, [rbp+hKey]; hKey
0x1800855fb  lea     rax, [rbp+cbData]
0x1800855ff  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180085604  lea     r9, [rbp+Type]; lpType
0x180085608  xor     r8d, r8d; lpReserved
0x18008560b  mov     [rsp+40h+phkResult], r15; lpData
0x180085610  lea     rdx, aWmirefresher; "WMIRefresher"
0x180085617  mov     [rbp+cbData], r15d
0x18008561b  call    cs:__imp_RegQueryValueExW
0x180085621  mov     rcx, [rbp+hKey]; hKey
0x180085625  mov     ebx, eax
0x180085627  call    cs:__imp_RegCloseKey
0x18008562d  test    ebx, ebx
0x18008562f  jz      short loc_180085635
0x180085631  cmp     ebx, esi
0x180085633  jnz     short loc_180085644
0x180085635  cmp     [rbp+Type], edi
0x180085638  jnz     short loc_180085644
0x18008563a  mov     [r14], r15d
0x18008563d  xor     eax, eax
0x18008563f  jmp     loc_1800857C5
0x180085644  lea     rax, [rbp+hKey]
0x180085648  mov     r9d, 20019h; samDesired
0x18008564e  xor     r8d, r8d; ulOptions
0x180085651  mov     [rsp+40h+phkResult], rax; phkResult
0x180085656  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x18008565d  mov     rcx, r12; hKey
0x180085660  call    cs:__imp_RegOpenKeyExW
0x180085666  test    eax, eax
0x180085668  jnz     short loc_1800856AD
0x18008566a  mov     rcx, [rbp+hKey]; hKey
0x18008566e  lea     rax, [rbp+cbData]
0x180085672  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180085677  lea     r9, [rbp+Type]; lpType
0x18008567b  xor     r8d, r8d; lpReserved
0x18008567e  mov     [rsp+40h+phkResult], r15; lpData
0x180085683  lea     rdx, aWmirefresher; "WMIRefresher"
0x18008568a  mov     [rbp+cbData], r15d
0x18008568e  call    cs:__imp_RegQueryValueExW
0x180085694  mov     rcx, [rbp+hKey]; hKey
0x180085698  mov     ebx, eax
0x18008569a  call    cs:__imp_RegCloseKey
0x1800856a0  test    ebx, ebx
0x1800856a2  jz      short loc_1800856A8
0x1800856a4  cmp     ebx, esi
0x1800856a6  jnz     short loc_1800856AD
0x1800856a8  cmp     [rbp+Type], edi
0x1800856ab  jz      short loc_180085716
0x1800856ad  lea     rax, [rbp+hKey]
0x1800856b1  mov     r9d, 20219h; samDesired
0x1800856b7  xor     r8d, r8d; ulOptions
0x1800856ba  mov     [rsp+40h+phkResult], rax; phkResult
0x1800856bf  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x1800856c6  mov     rcx, r12; hKey
0x1800856c9  call    cs:__imp_RegOpenKeyExW
0x1800856cf  test    eax, eax
0x1800856d1  jnz     short loc_18008571E
0x1800856d3  mov     rcx, [rbp+hKey]; hKey
0x1800856d7  lea     rax, [rbp+cbData]
0x1800856db  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800856e0  lea     r9, [rbp+Type]; lpType
0x1800856e4  xor     r8d, r8d; lpReserved
0x1800856e7  mov     [rsp+40h+phkResult], r15; lpData
0x1800856ec  lea     rdx, aWmirefresher; "WMIRefresher"
0x1800856f3  mov     [rbp+cbData], r15d
0x1800856f7  call    cs:__imp_RegQueryValueExW
0x1800856fd  mov     rcx, [rbp+hKey]; hKey
0x180085701  mov     ebx, eax
0x180085703  call    cs:__imp_RegCloseKey
0x180085709  test    ebx, ebx
0x18008570b  jz      short loc_180085711
0x18008570d  cmp     ebx, esi
0x18008570f  jnz     short loc_18008571E
0x180085711  cmp     [rbp+Type], edi
0x180085714  jnz     short loc_18008571E
0x180085716  mov     [r14], edi
0x180085719  jmp     loc_18008563D
0x18008571e  lea     rax, [rbp+hKey]
0x180085722  mov     r9d, 20019h; samDesired
0x180085728  xor     r8d, r8d; ulOptions
0x18008572b  mov     [rsp+40h+phkResult], rax; phkResult
0x180085730  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180085737  mov     rcx, r12; hKey
0x18008573a  call    cs:__imp_RegOpenKeyExW
0x180085740  mov     ebx, eax
0x180085742  test    eax, eax
0x180085744  jnz     short loc_1800857B8
0x180085746  mov     rcx, [rbp+hKey]; hKey
0x18008574a  lea     rax, [rbp+cbData]
0x18008574e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180085753  lea     r9, [rbp+Type]; lpType
0x180085757  lea     rax, [rbp+Data]
0x18008575b  mov     [rbp+Data], r15d
0x18008575f  xor     r8d, r8d; lpReserved
0x180085762  mov     [rsp+40h+phkResult], rax; lpData
0x180085767  lea     rdx, aDefaultsecured; "DefaultSecuredHost"
0x18008576e  mov     [rbp+cbData], 4
0x180085775  mov     ebx, r15d
0x180085778  call    cs:__imp_RegQueryValueExW
0x18008577e  mov     rcx, [rbp+hKey]; hKey
0x180085782  mov     esi, eax
0x180085784  call    cs:__imp_RegCloseKey
0x18008578a  test    esi, esi
0x18008578c  jnz     short loc_1800857A1
0x18008578e  cmp     [rbp+Type], 4
0x180085792  jnz     short loc_1800857A6
0x180085794  cmp     [rbp+Data], r15d
0x180085798  mov     edi, r15d
0x18008579b  setz    dil
0x18008579f  jmp     short loc_1800857A6
0x1800857a1  cmp     esi, 2
0x1800857a4  jnz     short loc_1800857AB
0x1800857a6  mov     [r14], edi
0x1800857a9  jmp     short loc_1800857C3
0x1800857ab  test    esi, esi
0x1800857ad  jg      short loc_1800857B3
0x1800857af  mov     ebx, esi
0x1800857b1  jmp     short loc_1800857C3
0x1800857b3  movzx   ebx, si
0x1800857b6  jmp     short loc_1800857BD
0x1800857b8  jle     short loc_1800857C3
0x1800857ba  movzx   ebx, ax
0x1800857bd  or      ebx, 80070000h
0x1800857c3  mov     eax, ebx
0x1800857c5  add     rsp, 40h
0x1800857c9  pop     r15
0x1800857cb  pop     r14
0x1800857cd  pop     r12
0x1800857cf  pop     rdi
0x1800857d0  pop     rsi
0x1800857d1  pop     rbx
0x1800857d2  pop     rbp
0x1800857d3  retn
```
