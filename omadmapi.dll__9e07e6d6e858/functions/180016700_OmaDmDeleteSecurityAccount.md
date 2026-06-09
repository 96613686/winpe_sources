# OmaDmDeleteSecurityAccount

- ea: `0x180016700`
- end: `0x180016a05`
- name: `OmaDmDeleteSecurityAccount`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d76c`

## callees

- `0x180003db8`
- `0x1800075f0`
- `0x180007930`
- `0x180009bc0`
- `0x180009bf4`
- `0x18000b26c`
- `0x18000c920`
- `0x18000f47c`
- `0x180015120`
- `0x180016700`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016875`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016875`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800168ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001695f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800168ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001695f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001690d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180016982`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001690d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180016982`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800168b9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001692f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800168b9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001692f`
- `DMCmnUtils!CopyString` at `0x18001679c`
- `DMCmnUtils!CopyString` at `0x18001679c`

## string_xrefs

- `0x180016855`: `policy:/REGISTRY/HKLM/SECURITY/PROVISIONING/OMADM/ACCOUNTS`

## pseudocode

```c
__int64 __fastcall OmaDmDeleteSecurityAccount(const unsigned __int16 *a1, unsigned int a2)
{
  signed int AccountIDFromLookupID; // edi
  __int64 v5; // rdx
  __int64 v6; // rax
  signed int v7; // eax
  LPCWSTR v8; // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  HKEY *phkResult; // rbx
  char IsStateSeparationEnabled; // al
  const WCHAR *v14; // rdx
  LSTATUS v15; // eax
  bool v16; // cc
  HKEY *v17; // rbx
  char v18; // al
  const WCHAR *v19; // rdx
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v23; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v24; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v27; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v28[128]; // [rsp+70h] [rbp-90h] BYREF

  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v24 = 0;
  v23 = 0;
  hKey = 0;
  lpSubKey = 0;
  if ( !a1 )
    goto LABEL_2;
  AccountIDFromLookupID = AcquireOmaDmMutex(&v27);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_38;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
LABEL_2:
      AccountIDFromLookupID = -2147024809;
      goto LABEL_38;
    }
    AccountIDFromLookupID = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&lpSubKey);
    if ( AccountIDFromLookupID >= 0 )
      goto LABEL_10;
  }
  else
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, &lpSubKey);
  }
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_38;
LABEL_10:
  v28[0] = 512;
  v5 = 0;
  v28[30] = -1;
  v28[46] = -1;
  do
  {
    v6 = 9 * v5++;
    v28[2 * v6 + 64] = -1;
  }
  while ( v5 != 2 );
  v28[90] = -1;
  v7 = OmaDmClearAcctInfo(a1, a2, v28);
  AccountIDFromLookupID = 0;
  if ( v7 != -2147024894 )
    AccountIDFromLookupID = v7;
  if ( AccountIDFromLookupID >= 0 )
  {
    v8 = lpSubKey;
    hObject = 0;
    if ( lpSubKey )
    {
      AccountIDFromLookupID = AcquireOmaDmMutex(&hObject);
      if ( AccountIDFromLookupID >= 0 )
      {
        hMem = 0;
        v9 = ipx::replace<ipx::detail::_HandleTraits<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>>(&hMem);
        v10 = BuildCanonicalFileOrRegPolicyName(L"policy:/REGISTRY/HKLM/SECURITY/PROVISIONING/OMADM/ACCOUNTS", v8, v9);
        AccountIDFromLookupID = 0;
        if ( v10 < 0 )
          AccountIDFromLookupID = v10;
        if ( hMem )
          LocalFree(hMem);
      }
    }
    else
    {
      AccountIDFromLookupID = -2147024809;
    }
    ReleaseOmaDmMutex(hObject);
    if ( AccountIDFromLookupID >= 0 )
    {
      AccountIDFromLookupID = GetAccountRootKey(lpSubKey, v11, &hKey);
      if ( AccountIDFromLookupID >= 0 )
      {
        phkResult = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
        IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
        v14 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
        if ( !IsStateSeparationEnabled )
          v14 = L"Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
        v15 = RegOpenKeyExW(hKey, v14, 0, 0x3010Eu, phkResult);
        v16 = v15 <= 0;
        if ( !v15 )
        {
          v15 = RegDeleteTreeW(v24, lpSubKey);
          if ( (v15 & 0xFFFFFFFD) == 0 )
          {
            v17 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v23);
            v18 = RtlIsStateSeparationEnabled();
            v19 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
            if ( !v18 )
              v19 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
            v15 = RegOpenKeyExW(hKey, v19, 0, 0x3010Eu, v17);
            if ( v15 )
            {
              if ( v15 == 2 )
              {
                AccountIDFromLookupID = 0;
                goto LABEL_38;
              }
            }
            else
            {
              v15 = RegDeleteTreeW(v23, lpSubKey);
              if ( (v15 & 0xFFFFFFFD) == 0 )
                goto LABEL_38;
            }
          }
          v16 = v15 <= 0;
        }
        if ( v16 )
          AccountIDFromLookupID = v15;
        else
          AccountIDFromLookupID = (unsigned __int16)v15 | 0x80070000;
      }
    }
  }
LABEL_38:
  LocalFree((HLOCAL)lpSubKey);
  ReleaseOmaDmMutex(v27);
  if ( v23 )
    RegCloseKey(v23);
  if ( v24 )
    RegCloseKey(v24);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x180016700  mov     [rsp-8+arg_8], rbx
0x180016705  mov     [rsp-8+arg_10], rsi
0x18001670a  push    rbp
0x18001670b  push    rdi
0x18001670c  push    r15
0x18001670e  lea     rbp, [rsp-170h]
0x180016716  sub     rsp, 270h
0x18001671d  mov     esi, edx
0x18001671f  mov     [rsp+280h+var_220], 0
0x180016728  mov     rbx, rcx
0x18001672b  xor     edx, edx; Val
0x18001672d  lea     rcx, [rsp+280h+var_210]; void *
0x180016732  mov     r8d, 200h; Size
0x180016738  call    memset_0
0x18001673d  mov     [rsp+280h+var_238], 0
0x180016746  mov     [rsp+280h+var_240], 0
0x18001674f  mov     [rsp+280h+hKey], 0
0x180016758  mov     [rsp+280h+lpSubKey], 0
0x180016761  test    rbx, rbx
0x180016764  jnz     short loc_180016770
0x180016766  mov     edi, 80070057h
0x18001676b  jmp     loc_1800169A3
0x180016770  lea     rcx, [rsp+280h+var_220]; void **
0x180016775  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x18001677a  mov     edi, eax
0x18001677c  test    eax, eax
0x18001677e  js      loc_1800169A3
0x180016784  or      r15d, 0FFFFFFFFh
0x180016788  test    esi, esi
0x18001678a  jz      short loc_1800167B0
0x18001678c  cmp     esi, 1
0x18001678f  jnz     short loc_180016766
0x180016791  lea     r8, [rsp+280h+lpSubKey]
0x180016796  mov     edx, r15d
0x180016799  mov     rcx, rbx
0x18001679c  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800167a3  nop     dword ptr [rax+rax+00h]
0x1800167a8  mov     edi, eax
0x1800167aa  test    eax, eax
0x1800167ac  js      short loc_1800167C1
0x1800167ae  jmp     short loc_1800167C9
0x1800167b0  lea     r8, [rsp+280h+lpSubKey]
0x1800167b5  xor     edx, edx
0x1800167b7  mov     rcx, rbx
0x1800167ba  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x1800167bf  mov     edi, eax
0x1800167c1  test    edi, edi
0x1800167c3  js      loc_1800169A3
0x1800167c9  mov     [rsp+280h+var_210], 200h
0x1800167d1  xor     edx, edx
0x1800167d3  mov     [rbp+180h+var_198], r15d
0x1800167d7  mov     [rbp+180h+var_158], r15d
0x1800167db  lea     rax, [rdx+rdx*8]
0x1800167df  inc     rdx
0x1800167e2  mov     [rbp+rax*8+180h+var_110], r15d
0x1800167e7  cmp     rdx, 2
0x1800167eb  jnz     short loc_1800167DB
0x1800167ed  lea     r8, [rsp+280h+var_210]
0x1800167f2  mov     [rbp+180h+var_A8], r15d
0x1800167f9  mov     edx, esi
0x1800167fb  mov     rcx, rbx
0x1800167fe  call    OmaDmClearAcctInfo
0x180016803  xor     edi, edi
0x180016805  cmp     eax, 80070002h
0x18001680a  cmovnz  edi, eax
0x18001680d  test    edi, edi
0x18001680f  js      loc_1800169A3
0x180016815  mov     rbx, [rsp+280h+lpSubKey]
0x18001681a  mov     [rsp+280h+hObject], 0
0x180016823  test    rbx, rbx
0x180016826  jnz     short loc_18001682F
0x180016828  mov     edi, 80070057h
0x18001682d  jmp     short loc_180016881
0x18001682f  lea     rcx, [rsp+280h+hObject]; void **
0x180016834  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x180016839  mov     edi, eax
0x18001683b  test    eax, eax
0x18001683d  js      short loc_180016881
0x18001683f  lea     rcx, [rsp+280h+hMem]
0x180016844  mov     [rsp+280h+hMem], 0
0x18001684d  call    ??$replace@U?$_HandleTraits@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAGAEAV?$unique_any@U?$_HandleTraits@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<ushort *,void * (*)(void *),&LocalFree(void *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<ushort *,void * (*)(void *),&LocalFree(void *),0>> &)
0x180016852  mov     r8, rax
0x180016855  lea     rcx, aPolicyRegistry; "policy:/REGISTRY/HKLM/SECURITY/PROVISIO"...
0x18001685c  mov     rdx, rbx
0x18001685f  call    BuildCanonicalFileOrRegPolicyName
0x180016864  mov     rcx, [rsp+280h+hMem]; hMem
0x180016869  xor     edi, edi
0x18001686b  test    eax, eax
0x18001686d  cmovs   edi, eax
0x180016870  test    rcx, rcx
0x180016873  jz      short loc_180016881
0x180016875  call    cs:__imp_LocalFree
0x18001687c  nop     dword ptr [rax+rax+00h]
0x180016881  mov     rcx, [rsp+280h+hObject]; hObject
0x180016886  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18001688b  test    edi, edi
0x18001688d  js      loc_1800169A3
0x180016893  mov     rcx, [rsp+280h+lpSubKey]
0x180016898  lea     r8, [rsp+280h+hKey]
0x18001689d  call    GetAccountRootKey
0x1800168a2  mov     edi, eax
0x1800168a4  test    eax, eax
0x1800168a6  js      loc_1800169A3
0x1800168ac  lea     rcx, [rsp+280h+var_238]
0x1800168b1  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800168b6  mov     rbx, rax
0x1800168b9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800168c0  nop     dword ptr [rax+rax+00h]
0x1800168c5  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x1800168cc  mov     [rsp+280h+phkResult], rbx; phkResult
0x1800168d1  test    al, al
0x1800168d3  lea     rdx, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x1800168da  mov     r15d, 3010Eh
0x1800168e0  cmovz   rdx, rcx; lpSubKey
0x1800168e4  mov     r9d, r15d; samDesired
0x1800168e7  mov     rcx, [rsp+280h+hKey]; hKey
0x1800168ec  xor     r8d, r8d; ulOptions
0x1800168ef  call    cs:__imp_RegOpenKeyExW
0x1800168f6  nop     dword ptr [rax+rax+00h]
0x1800168fb  test    eax, eax
0x1800168fd  jnz     loc_180016994
0x180016903  mov     rdx, [rsp+280h+lpSubKey]; lpSubKey
0x180016908  mov     rcx, [rsp+280h+var_238]; hKey
0x18001690d  call    cs:__imp_RegDeleteTreeW
0x180016914  nop     dword ptr [rax+rax+00h]
0x180016919  mov     esi, 0FFFFFFFDh
0x18001691e  test    esi, eax
0x180016920  jnz     short loc_180016992
0x180016922  lea     rcx, [rsp+280h+var_240]
0x180016927  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001692c  mov     rbx, rax
0x18001692f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180016936  nop     dword ptr [rax+rax+00h]
0x18001693b  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x180016942  mov     [rsp+280h+phkResult], rbx; phkResult
0x180016947  test    al, al
0x180016949  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180016950  mov     r9d, r15d; samDesired
0x180016953  cmovz   rdx, rcx; lpSubKey
0x180016957  mov     rcx, [rsp+280h+hKey]; hKey
0x18001695c  xor     r8d, r8d; ulOptions
0x18001695f  call    cs:__imp_RegOpenKeyExW
0x180016966  nop     dword ptr [rax+rax+00h]
0x18001696b  test    eax, eax
0x18001696d  jz      short loc_180016978
0x18001696f  cmp     eax, 2
0x180016972  jnz     short loc_180016992
0x180016974  xor     edi, edi
0x180016976  jmp     short loc_1800169A3
0x180016978  mov     rdx, [rsp+280h+lpSubKey]; lpSubKey
0x18001697d  mov     rcx, [rsp+280h+var_240]; hKey
0x180016982  call    cs:__imp_RegDeleteTreeW
0x180016989  nop     dword ptr [rax+rax+00h]
0x18001698e  test    esi, eax
0x180016990  jz      short loc_1800169A3
0x180016992  test    eax, eax
0x180016994  jg      short loc_18001699A
0x180016996  mov     edi, eax
0x180016998  jmp     short loc_1800169A3
0x18001699a  movzx   edi, ax
0x18001699d  or      edi, 80070000h
0x1800169a3  mov     rcx, [rsp+280h+lpSubKey]; hMem
0x1800169a8  call    cs:__imp_LocalFree
0x1800169af  nop     dword ptr [rax+rax+00h]
0x1800169b4  mov     rcx, [rsp+280h+var_220]; hObject
0x1800169b9  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x1800169be  mov     rcx, [rsp+280h+var_240]; hKey
0x1800169c3  test    rcx, rcx
0x1800169c6  jz      short loc_1800169D4
0x1800169c8  call    cs:__imp_RegCloseKey
0x1800169cf  nop     dword ptr [rax+rax+00h]
0x1800169d4  mov     rcx, [rsp+280h+var_238]; hKey
0x1800169d9  test    rcx, rcx
0x1800169dc  jz      short loc_1800169EA
0x1800169de  call    cs:__imp_RegCloseKey
0x1800169e5  nop     dword ptr [rax+rax+00h]
0x1800169ea  lea     r11, [rsp+280h+var_10]
0x1800169f2  mov     eax, edi
0x1800169f4  mov     rbx, [r11+28h]
0x1800169f8  mov     rsi, [r11+30h]
0x1800169fc  mov     rsp, r11
0x1800169ff  pop     r15
0x180016a01  pop     rdi
0x180016a02  pop     rbp
0x180016a03  retn
```
