# Utils::RetrieveAndSetOneSettings(void)

- ea: `0x1800d37d0`
- end: `0x1800d3abc`
- name: `?RetrieveAndSetOneSettings@Utils@@SAXXZ`
- size: `748`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2cd0`
- `0x1800a47e0`

## callees

- `0x180008dc0`
- `0x180014f2c`
- `0x180016748`
- `0x1800b98fc`
- `0x1800d37d0`
- `0x18016796c`
- `0x180184b4c`
- `0x180184b58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800d3a06`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800d3a06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3853`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3840`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d38d5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d3a51`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d38d5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d3a51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d384b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d3a93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d384b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d3a93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d382c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d387f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d382c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d387f`

## string_xrefs

- `0x1800d381e`: `OSDATA\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\Census`
- `0x1800d3871`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\Census`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void Utils::RetrieveAndSetOneSettings(void)
{
  HKEY v0; // rdi
  DWORD LastError; // ebx
  int v2; // ebx
  LSTATUS v3; // eax
  __m128i si128; // xmm6
  unsigned __int64 v5; // r8
  __int64 v6; // rdx
  HKEY hKey; // [rsp+48h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+54h] [rbp-B4h] BYREF
  DWORD cchValueName; // [rsp+58h] [rbp-B0h] BYREF
  DWORD cchValueName_8[4]; // [rsp+60h] [rbp-A8h] BYREF
  __m128i v12; // [rsp+70h] [rbp-98h]
  wchar_t Data[264]; // [rsp+88h] [rbp-80h] BYREF
  WCHAR ValueName[264]; // [rsp+298h] [rbp+190h] BYREF

  g_FullSyncIntervalInRuns = 14;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"OSDATA\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\Census",
          0,
          0x20019u,
          &hKey) )
    goto LABEL_5;
  v0 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v0);
    SetLastError(LastError);
  }
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\Census",
          0,
          0x20019u,
          &hKey) )
  {
LABEL_5:
    v2 = 0;
    Type = 0;
    cchValueName = 520;
    cbData = 520;
    v3 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
    if ( !v3 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        if ( Type == 1 )
        {
          if ( !wcsncmp_0(ValueName, L"BLOCKED_", 8u) )
          {
            AslLogCallPrintf(
              3,
              "Utils::RetrieveAndSetOneSettings",
              1646,
              "Census attribute %ls blocked by OneSettings.",
              Data);
            *(_OWORD *)cchValueName_8 = 0;
            v12 = 0;
            v5 = -1;
            do
              ++v5;
            while ( Data[v5] );
            std::wstring::_Construct<1,unsigned short const *>((char **)cchValueName_8, Data, v5);
            v6 = qword_1801FFCC8;
            if ( qword_1801FFCC8 == qword_1801FFCD0 )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(
                &g_CensusAttributesBlocked,
                qword_1801FFCC8,
                cchValueName_8);
            }
            else
            {
              *(_OWORD *)qword_1801FFCC8 = *(_OWORD *)cchValueName_8;
              *(__m128i *)(v6 + 16) = v12;
              v12 = si128;
              LOWORD(cchValueName_8[0]) = 0;
              qword_1801FFCC8 += 32;
            }
            std::wstring::~wstring((char **)cchValueName_8);
          }
          else if ( !wcscmp_0(ValueName, L"FullSyncInterval") )
          {
            AslLogCallPrintf(
              3,
              "Utils::RetrieveAndSetOneSettings",
              1651,
              "Census fullsync inverval set to %ls by OneSettings.",
              Data);
            g_FullSyncIntervalInRuns = _o__wtoi(Data);
          }
        }
        cchValueName = 520;
        cbData = 520;
        v3 = RegEnumValueW(hKey, ++v2, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
      }
      while ( !v3 );
    }
    if ( v3 != 259 )
      AslLogCallPrintf(1, "Utils::RetrieveAndSetOneSettings", 1663, "RegEnumValueW failed with error [%d]", v3);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800d37d0  mov     rax, rsp
0x1800d37d3  push    rbp
0x1800d37d4  push    rbx
0x1800d37d5  push    rsi
0x1800d37d6  push    rdi
0x1800d37d7  lea     rbp, [rax-3E8h]
0x1800d37de  sub     rsp, 4C8h
0x1800d37e5  movaps  xmmword ptr [rax-38h], xmm6
0x1800d37e9  mov     rax, cs:__security_cookie
0x1800d37f0  xor     rax, rsp
0x1800d37f3  mov     [rbp+3E0h+var_40], rax
0x1800d37fa  mov     cs:?g_FullSyncIntervalInRuns@@3KA, 0Eh; ulong g_FullSyncIntervalInRuns
0x1800d3804  xor     esi, esi
0x1800d3806  mov     [rsp+4E0h+hKey], rsi
0x1800d380b  lea     rax, [rsp+4E0h+hKey]
0x1800d3810  mov     [rsp+4E0h+phkResult], rax; phkResult
0x1800d3815  mov     r9d, 20019h; samDesired
0x1800d381b  xor     r8d, r8d; ulOptions
0x1800d381e  lea     rdx, aOsdataSoftware_0; "OSDATA\\SOFTWARE\\Microsoft\\Windows NT"...
0x1800d3825  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d382c  call    cs:__imp_RegOpenKeyExW
0x1800d3832  test    eax, eax
0x1800d3834  jz      short loc_1800D388D
0x1800d3836  mov     rdi, [rsp+4E0h+hKey]
0x1800d383b  test    rdi, rdi
0x1800d383e  jz      short loc_1800D3859
0x1800d3840  call    cs:__imp_GetLastError
0x1800d3846  mov     ebx, eax
0x1800d3848  mov     rcx, rdi; hKey
0x1800d384b  call    cs:__imp_RegCloseKey
0x1800d3851  mov     ecx, ebx; dwErrCode
0x1800d3853  call    cs:__imp_SetLastError
0x1800d3859  mov     [rsp+4E0h+hKey], rsi
0x1800d385e  lea     rax, [rsp+4E0h+hKey]
0x1800d3863  mov     [rsp+4E0h+phkResult], rax; phkResult
0x1800d3868  mov     r9d, 20019h; samDesired
0x1800d386e  xor     r8d, r8d; ulOptions
0x1800d3871  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800d3878  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d387f  call    cs:__imp_RegOpenKeyExW
0x1800d3885  test    eax, eax
0x1800d3887  jnz     loc_1800D3A89
0x1800d388d  mov     ebx, esi
0x1800d388f  mov     [rsp+4E0h+Type], esi
0x1800d3893  mov     edi, 208h
0x1800d3898  mov     [rsp+4E0h+cchValueName], edi
0x1800d389c  mov     [rsp+4E0h+cbData], edi
0x1800d38a0  lea     rax, [rsp+4E0h+cbData]
0x1800d38a5  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x1800d38aa  lea     rax, [rbp+3E0h+Data]
0x1800d38ae  mov     [rsp+4E0h+lpData], rax; lpData
0x1800d38b3  lea     rax, [rsp+4E0h+Type]
0x1800d38b8  mov     [rsp+4E0h+lpType], rax; lpType
0x1800d38bd  mov     [rsp+4E0h+phkResult], rsi; lpReserved
0x1800d38c2  lea     r9, [rsp+4E0h+cchValueName]; lpcchValueName
0x1800d38c7  lea     r8, [rbp+3E0h+ValueName]; lpValueName
0x1800d38ce  xor     edx, edx; dwIndex
0x1800d38d0  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800d38d5  call    cs:__imp_RegEnumValueW
0x1800d38db  test    eax, eax
0x1800d38dd  jnz     loc_1800D3A5F
0x1800d38e3  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800d38eb  cmp     [rsp+4E0h+Type], 1
0x1800d38f0  jnz     loc_1800D3A12
0x1800d38f6  mov     r8d, 8; MaxCount
0x1800d38fc  lea     rdx, aBlocked; "BLOCKED_"
0x1800d3903  lea     rcx, [rbp+3E0h+ValueName]; String1
0x1800d390a  call    wcsncmp_0
0x1800d390f  test    eax, eax
0x1800d3911  jnz     loc_1800D39C4
0x1800d3917  lea     rax, [rbp+3E0h+Data]
0x1800d391b  mov     [rsp+4E0h+phkResult], rax
0x1800d3920  lea     r9, aCensusAttribut; "Census attribute %ls blocked by OneSett"...
0x1800d3927  mov     r8d, 66Eh
0x1800d392d  lea     rdx, aUtilsRetrievea; "Utils::RetrieveAndSetOneSettings"
0x1800d3934  mov     ecx, 3
0x1800d3939  call    AslLogCallPrintf
0x1800d393e  xorps   xmm0, xmm0
0x1800d3941  movups  xmmword ptr [rsp+4E0h+cchValueName+8], xmm0
0x1800d3946  xorps   xmm1, xmm1
0x1800d3949  movdqu  xmmword ptr [rsp+4E0h+var_480+8], xmm1
0x1800d394f  lea     rax, [rbp+3E0h+Data]
0x1800d3953  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d3957  inc     r8
0x1800d395a  cmp     [rax+r8*2], si
0x1800d395f  jnz     short loc_1800D3957
0x1800d3961  lea     rdx, [rbp+3E0h+Data]
0x1800d3965  lea     rcx, [rsp+4E0h+cchValueName+8]
0x1800d396a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d396f  nop
0x1800d3970  mov     rdx, cs:qword_1801FFCC8
0x1800d3977  cmp     rdx, cs:qword_1801FFCD0
0x1800d397e  jz      short loc_1800D39A6
0x1800d3980  movups  xmm0, xmmword ptr [rsp+4E0h+cchValueName+8]
0x1800d3985  movups  xmmword ptr [rdx], xmm0
0x1800d3988  movups  xmm1, xmmword ptr [rsp+4E0h+var_480+8]
0x1800d398d  movups  xmmword ptr [rdx+10h], xmm1
0x1800d3991  movdqu  xmmword ptr [rsp+4E0h+var_480+8], xmm6
0x1800d3997  mov     word ptr [rsp+4E0h+cchValueName+8], si
0x1800d399c  add     cs:qword_1801FFCC8, 20h ; ' '
0x1800d39a4  jmp     short loc_1800D39B8
0x1800d39a6  lea     r8, [rsp+4E0h+cchValueName+8]
0x1800d39ab  lea     rcx, ?g_CensusAttributesBlocked@@3V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> g_CensusAttributesBlocked
0x1800d39b2  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800d39b7  nop
0x1800d39b8  lea     rcx, [rsp+4E0h+cchValueName+8]
0x1800d39bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d39c2  jmp     short loc_1800D3A12
0x1800d39c4  lea     rdx, aFullsyncinterv; "FullSyncInterval"
0x1800d39cb  lea     rcx, [rbp+3E0h+ValueName]; String1
0x1800d39d2  call    wcscmp_0
0x1800d39d7  test    eax, eax
0x1800d39d9  jnz     short loc_1800D3A12
0x1800d39db  lea     rax, [rbp+3E0h+Data]
0x1800d39df  mov     [rsp+4E0h+phkResult], rax
0x1800d39e4  lea     r9, aCensusFullsync; "Census fullsync inverval set to %ls by "...
0x1800d39eb  mov     r8d, 673h
0x1800d39f1  lea     rdx, aUtilsRetrievea; "Utils::RetrieveAndSetOneSettings"
0x1800d39f8  mov     ecx, 3
0x1800d39fd  call    AslLogCallPrintf
0x1800d3a02  lea     rcx, [rbp+3E0h+Data]
0x1800d3a06  call    cs:__imp__o__wtoi
0x1800d3a0c  mov     cs:?g_FullSyncIntervalInRuns@@3KA, eax; ulong g_FullSyncIntervalInRuns
0x1800d3a12  mov     [rsp+4E0h+cchValueName], edi
0x1800d3a16  mov     [rsp+4E0h+cbData], edi
0x1800d3a1a  inc     ebx
0x1800d3a1c  lea     rax, [rsp+4E0h+cbData]
0x1800d3a21  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x1800d3a26  lea     rax, [rbp+3E0h+Data]
0x1800d3a2a  mov     [rsp+4E0h+lpData], rax; lpData
0x1800d3a2f  lea     rax, [rsp+4E0h+Type]
0x1800d3a34  mov     [rsp+4E0h+lpType], rax; lpType
0x1800d3a39  mov     [rsp+4E0h+phkResult], rsi; lpReserved
0x1800d3a3e  lea     r9, [rsp+4E0h+cchValueName]; lpcchValueName
0x1800d3a43  lea     r8, [rbp+3E0h+ValueName]; lpValueName
0x1800d3a4a  mov     edx, ebx; dwIndex
0x1800d3a4c  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800d3a51  call    cs:__imp_RegEnumValueW
0x1800d3a57  test    eax, eax
0x1800d3a59  jz      loc_1800D38EB
0x1800d3a5f  cmp     eax, 103h
0x1800d3a64  jz      short loc_1800D3A89
0x1800d3a66  mov     dword ptr [rsp+4E0h+phkResult], eax
0x1800d3a6a  lea     r9, aRegenumvaluewF; "RegEnumValueW failed with error [%d]"
0x1800d3a71  mov     r8d, 67Fh
0x1800d3a77  lea     rdx, aUtilsRetrievea; "Utils::RetrieveAndSetOneSettings"
0x1800d3a7e  mov     ecx, 1
0x1800d3a83  call    AslLogCallPrintf
0x1800d3a88  nop
0x1800d3a89  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800d3a8e  test    rcx, rcx
0x1800d3a91  jz      short loc_1800D3A99
0x1800d3a93  call    cs:__imp_RegCloseKey
0x1800d3a99  mov     rcx, [rbp+3E0h+var_40]
0x1800d3aa0  xor     rcx, rsp; StackCookie
0x1800d3aa3  call    __security_check_cookie
0x1800d3aa8  movaps  xmm6, [rsp+4E0h+var_38+8]
0x1800d3ab0  add     rsp, 4C8h
0x1800d3ab7  pop     rdi
0x1800d3ab8  pop     rsi
0x1800d3ab9  pop     rbx
0x1800d3aba  pop     rbp
0x1800d3abb  retn
```
