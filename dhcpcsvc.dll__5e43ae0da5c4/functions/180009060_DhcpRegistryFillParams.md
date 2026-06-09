# DhcpRegistryFillParams

- ea: `0x180009060`
- end: `0x18000957b`
- name: `DhcpRegistryFillParams`
- size: `1307`
- prototype: `__int64 __usercall@<rax>(STRSAFE_PCNZWCH psz@<rcx>, __int64, __int64, STRSAFE_PCNZWCH)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180009920`

## callees

- `0x180001f90`
- `0x180002160`
- `0x180002c00`
- `0x180003110`
- `0x180003210`
- `0x1800048c0`
- `0x180009060`
- `0x18000d3cc`
- `0x18000d440`
- `0x18000d4a4`
- `0x18000d510`
- `0x18001190c`
- `0x180012850`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009306`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009306`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009337`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000935b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009388`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800093f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000941b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000950b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009337`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000935b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009388`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800093f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000941b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000950b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009425`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000951c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009425`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000951c`

## string_xrefs

- `0x1800091ce`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x180009281`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x180009444`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x180009219`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180009291`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180009466`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180009374`: `ClassId`

## pseudocode

```c
__int64 __fastcall DhcpRegistryFillParams(
        STRSAFE_PCNZWCH psz,
        BYTE *a2,
        DWORD a3,
        unsigned int a4,
        HKEY a5,
        __int64 a6,
        STRSAFE_PCNZWCH psza)
{
  int v7; // esi
  DWORD v9; // r14d
  unsigned int v11; // eax
  size_t v12; // rdx
  unsigned int v13; // ebx
  DWORD v14; // eax
  HRESULT v15; // eax
  size_t v16; // rdx
  const WCHAR *v17; // r12
  HRESULT v18; // eax
  int v19; // r14d
  int IsWCOSSystem; // eax
  size_t v21; // rdx
  const wchar_t *v22; // rcx
  HRESULT v23; // eax
  int v24; // edi
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // edi
  HRESULT v28; // eax
  size_t v29; // rcx
  size_t v30; // rsi
  wchar_t *v31; // rdi
  int v32; // eax
  const wchar_t *v33; // r8
  const WCHAR *v34; // r9
  unsigned int v35; // eax
  HRESULT v36; // eax
  unsigned int v37; // r14d
  unsigned int v38; // eax
  unsigned int v39; // eax
  size_t pcbLength; // [rsp+50h] [rbp-71h] BYREF
  int v42; // [rsp+58h] [rbp-69h]
  HKEY phkResult; // [rsp+60h] [rbp-61h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-59h]
  BYTE Data[4]; // [rsp+6Ch] [rbp-55h] BYREF
  BYTE v46[4]; // [rsp+70h] [rbp-51h] BYREF
  BYTE v47[4]; // [rsp+74h] [rbp-4Dh] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-49h] BYREF
  DWORD v49; // [rsp+7Ch] [rbp-45h]
  BYTE *lpData; // [rsp+80h] [rbp-41h]
  __int64 v51; // [rsp+88h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-31h]
  BYTE *v53; // [rsp+98h] [rbp-29h]
  wchar_t pszDest[8]; // [rsp+A0h] [rbp-21h] BYREF

  v7 = 0;
  v9 = a3;
  hKey = a5;
  phkResult = 0;
  v51 = 0;
  dwDisposition = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v46 = 0;
  *(_DWORD *)v47 = 0;
  cbData = a3;
  lpData = a2;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SqddqqS((_DWORD)psz, (_DWORD)a2, a3, (_DWORD)psz, (char)a2, a3, a4, (char)a5, a6, (__int64)psza);
  v11 = StringCchPrintfW(pszDest, 7u, L"%5x", a4);
  v13 = WX_WIN32_FROM_HR(v11);
  if ( !v13 )
  {
    *(_DWORD *)Data = *(_DWORD *)(a6 + 4);
    *(_DWORD *)v46 = *(_DWORD *)(a6 + 8);
    v53 = *(BYTE **)(a6 + 16);
    v14 = *(_DWORD *)(a6 + 24);
    pcbLength = 0;
    v42 = 0;
    v49 = v14;
    if ( psza )
    {
      v15 = StringCbLengthW(psza, v12, &pcbLength);
      if ( v15 >= 0 )
        v7 = pcbLength;
      else
        HIDWORD(pcbLength) = 108;
    }
    else
    {
      v15 = -2147024809;
      HIDWORD(pcbLength) = 104;
    }
    v13 = WX_WIN32_FROM_HR((unsigned int)v15);
    if ( !v13 )
    {
      v17 = L"OSDATA\\Networking\\Dhcp\\Client4";
      pcbLength = 0;
      if ( !psz )
      {
        cbData = 0;
        v28 = StringCbLengthW(L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters", v16, &pcbLength);
        if ( v28 >= 0 )
        {
          v27 = pcbLength;
        }
        else
        {
          HIDWORD(pcbLength) = 108;
          v27 = cbData;
        }
        v13 = WX_WIN32_FROM_HR((unsigned int)v28);
        if ( v13 )
          goto LABEL_50;
        goto LABEL_26;
      }
      v42 = 0;
      v18 = StringCbLengthW(psz, v16, &pcbLength);
      if ( v18 >= 0 )
      {
        v19 = pcbLength;
      }
      else
      {
        v19 = v42;
        HIDWORD(pcbLength) = 108;
      }
      v13 = WX_WIN32_FROM_HR((unsigned int)v18);
      if ( !v13 )
      {
        IsWCOSSystem = DhcpIsWCOSSystem();
        pcbLength = 0;
        v22 = L"OSDATA\\Networking\\Dhcp\\Client4";
        v42 = 0;
        if ( !IsWCOSSystem )
          v22 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces";
        v23 = StringCbLengthW(v22, v21, &pcbLength);
        if ( v23 >= 0 )
        {
          v24 = pcbLength;
        }
        else
        {
          HIDWORD(pcbLength) = 108;
          v24 = v42;
        }
        v13 = WX_WIN32_FROM_HR((unsigned int)v23);
        if ( !v13 )
        {
          v27 = v19 + v24;
          v9 = cbData;
LABEL_26:
          v29 = (unsigned int)(v7 + v27 + 22);
          v30 = v29;
          v51 = DhcpAlloc(v29, v25, v26);
          v31 = (wchar_t *)v51;
          if ( v51 )
          {
            if ( psz )
            {
              v32 = DhcpIsWCOSSystem();
              v33 = L"%s\\?\\%s%s";
              v34 = L"OSDATA\\Networking\\Dhcp\\Client4";
              if ( !v32 )
                v34 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces";
            }
            else
            {
              v34 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
              v33 = L"%s\\%s%s";
            }
            v35 = StringCbPrintfW(v31, v30, v33, v34, psza, pszDest);
            v13 = WX_WIN32_FROM_HR(v35);
            if ( !v13 )
            {
              v13 = RegCreateKeyExW(
                      hKey,
                      pszDest,
                      0,
                      (LPWSTR)L"DhcpClientClass",
                      0,
                      0xF003Fu,
                      0,
                      &phkResult,
                      &dwDisposition);
              if ( !v13 )
              {
                RegSetValueExW(phkResult, L"OptionId", 0, 4u, Data, 4u);
                RegSetValueExW(phkResult, L"VendorType", 0, 4u, v46, 4u);
                if ( v9 )
                  RegSetValueExW(phkResult, L"ClassId", 0, 3u, lpData, v9);
                HIDWORD(lpData) = 0;
                cbData = 0;
                pcbLength = 0;
                v36 = StringCchLengthW(v31, 0x7FFFFFFFu, &pcbLength);
                if ( v36 >= 0 )
                {
                  v37 = pcbLength;
                }
                else
                {
                  HIDWORD(lpData) = 81;
                  v37 = 0;
                }
                v13 = WX_WIN32_FROM_HR((unsigned int)v36);
                if ( !v13 )
                {
                  RegSetValueExW(phkResult, L"RegSendLocation", 0, 1u, (const BYTE *)v31, 2 * v37 + 2);
                  *(_DWORD *)v47 = 4;
                  RegSetValueExW(phkResult, L"KeyType", 0, 4u, v47, 4u);
                  RegCloseKey(phkResult);
                  phkResult = 0;
                  if ( psz )
                  {
                    if ( !(unsigned int)DhcpIsWCOSSystem() )
                      v17 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces";
                    v38 = StringCbPrintfW(v31, v30, L"%s\\%s", v17, psz);
                  }
                  else
                  {
                    v38 = StringCbCopyW(v31, v30, L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters");
                  }
                  v13 = WX_WIN32_FROM_HR(v38);
                  if ( !v13 )
                  {
                    v39 = StringCbPrintfW(&v31[v37 + 1], v30 - 2LL * v37, L"%s%s", psza, pszDest);
                    v13 = WX_WIN32_FROM_HR(v39);
                    if ( !v13 )
                    {
                      v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v31, 0, 0xF003Fu, &phkResult);
                      if ( !v13 )
                        v13 = RegSetValueExW(phkResult, &v31[v37 + 1], 0, 3u, v53, v49);
                    }
                  }
                }
              }
            }
          }
          else
          {
            v13 = 8;
          }
        }
      }
    }
  }
LABEL_50:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  DhcpFree(&v51);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 94, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, (_DWORD)psz, v13);
  return v13;
}

```

## disassembly

```asm
0x180009060  push    rbp
0x180009062  push    rbx
0x180009063  push    rsi
0x180009064  push    rdi
0x180009065  push    r12
0x180009067  push    r13
0x180009069  push    r14
0x18000906b  push    r15
0x18000906d  lea     rbp, [rsp-7]
0x180009072  sub     rsp, 0C8h
0x180009079  mov     rax, cs:__security_cookie
0x180009080  xor     rax, rsp
0x180009083  mov     [rbp+3Fh+var_50], rax
0x180009087  mov     rax, [rbp+3Fh+arg_20]
0x18000908b  xor     esi, esi
0x18000908d  mov     rdi, [rbp+3Fh+arg_28]
0x180009091  mov     ebx, r9d
0x180009094  mov     r13, [rbp+3Fh+psz]
0x180009098  mov     r14d, r8d
0x18000909b  mov     [rbp+3Fh+hKey], rax
0x18000909f  mov     r15, rcx
0x1800090a2  mov     [rbp+3Fh+var_A0], rsi
0x1800090a6  mov     [rbp+3Fh+var_78], rsi
0x1800090aa  mov     [rbp+3Fh+dwDisposition], esi
0x1800090ad  mov     dword ptr [rbp+3Fh+Data], esi
0x1800090b0  mov     dword ptr [rbp+3Fh+var_90], esi
0x1800090b3  mov     dword ptr [rbp+3Fh+var_8C], esi
0x1800090b6  mov     [rbp+3Fh+cbData], r8d
0x1800090ba  mov     [rbp+3Fh+lpData], rdx
0x1800090be  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800090c5  jz      short loc_1800090EC
0x1800090c7  mov     [rsp+100h+var_B8], r13
0x1800090cc  mov     r9, rcx
0x1800090cf  mov     [rsp+100h+lpdwDisposition], rdi
0x1800090d4  mov     [rsp+100h+phkResult], rax
0x1800090d9  mov     dword ptr [rsp+100h+lpSecurityAttributes], ebx
0x1800090dd  mov     [rsp+100h+samDesired], r8d
0x1800090e2  mov     qword ptr [rsp+100h+dwOptions], rdx
0x1800090e7  call    WPP_SF_SqddqqS
0x1800090ec  mov     r9d, ebx
0x1800090ef  lea     r8, a5x; "%5x"
0x1800090f6  mov     edx, 7; cchDest
0x1800090fb  lea     rcx, [rbp+3Fh+pszDest]; pszDest
0x1800090ff  call    StringCchPrintfW
0x180009104  mov     ecx, eax
0x180009106  call    WX_WIN32_FROM_HR
0x18000910b  mov     ebx, eax
0x18000910d  test    eax, eax
0x18000910f  jnz     loc_180009513
0x180009115  mov     eax, [rdi+4]
0x180009118  mov     dword ptr [rbp+3Fh+Data], eax
0x18000911b  mov     eax, [rdi+8]
0x18000911e  mov     dword ptr [rbp+3Fh+var_90], eax
0x180009121  mov     rax, [rdi+10h]
0x180009125  mov     [rbp+3Fh+var_68], rax
0x180009129  mov     eax, [rdi+18h]
0x18000912c  lea     edi, [rbx+6Ch]
0x18000912f  mov     dword ptr [rbp+3Fh+pcbLength+4], esi
0x180009132  mov     [rbp-71h], rsi
0x180009136  mov     [rbp+3Fh+var_A8], esi
0x180009139  mov     [rbp+3Fh+var_84], eax
0x18000913c  test    r13, r13
0x18000913f  jnz     short loc_18000914F
0x180009141  mov     eax, 80070057h
0x180009146  mov     dword ptr [rbp+3Fh+pcbLength+4], 68h ; 'h'
0x18000914d  jmp     short loc_180009167
0x18000914f  lea     r8, [rbp+3Fh+pcbLength]; pcbLength
0x180009153  mov     rcx, r13; psz
0x180009156  call    StringCbLengthW
0x18000915b  test    eax, eax
0x18000915d  jns     short loc_180009164
0x18000915f  mov     dword ptr [rbp+3Fh+pcbLength+4], edi
0x180009162  jmp     short loc_18000914D
0x180009164  mov     esi, dword ptr [rbp+3Fh+pcbLength]
0x180009167  mov     ecx, eax
0x180009169  call    WX_WIN32_FROM_HR
0x18000916e  mov     ebx, eax
0x180009170  test    eax, eax
0x180009172  jnz     loc_180009513
0x180009178  mov     dword ptr [rbp+3Fh+pcbLength+4], eax
0x18000917b  lea     r12, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client4"
0x180009182  mov     [rbp+3Fh+pcbLength], 0
0x18000918a  lea     r8, [rbp+3Fh+pcbLength]; pcbLength
0x18000918e  test    r15, r15
0x180009191  jz      loc_180009219
0x180009197  mov     rcx, r15; psz
0x18000919a  mov     [rbp+3Fh+var_A8], eax
0x18000919d  call    StringCbLengthW
0x1800091a2  test    eax, eax
0x1800091a4  jns     short loc_1800091AF
0x1800091a6  mov     r14d, [rbp+3Fh+var_A8]
0x1800091aa  mov     dword ptr [rbp+3Fh+pcbLength+4], edi
0x1800091ad  jmp     short loc_1800091B3
0x1800091af  mov     r14d, dword ptr [rbp+3Fh+pcbLength]
0x1800091b3  mov     ecx, eax
0x1800091b5  call    WX_WIN32_FROM_HR
0x1800091ba  mov     ebx, eax
0x1800091bc  test    eax, eax
0x1800091be  jnz     loc_180009513
0x1800091c4  call    DhcpIsWCOSSystem
0x1800091c9  test    eax, eax
0x1800091cb  mov     dword ptr [rbp+3Fh+pcbLength+4], ebx
0x1800091ce  lea     rax, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x1800091d5  mov     [rbp+3Fh+pcbLength], 0
0x1800091dd  mov     rcx, r12
0x1800091e0  mov     [rbp+3Fh+var_A8], ebx
0x1800091e3  cmovz   rcx, rax; psz
0x1800091e7  lea     r8, [rbp+3Fh+pcbLength]; pcbLength
0x1800091eb  call    StringCbLengthW
0x1800091f0  test    eax, eax
0x1800091f2  jns     short loc_1800091FC
0x1800091f4  mov     dword ptr [rbp+3Fh+pcbLength+4], edi
0x1800091f7  mov     edi, [rbp+3Fh+var_A8]
0x1800091fa  jmp     short loc_1800091FF
0x1800091fc  mov     edi, dword ptr [rbp+3Fh+pcbLength]
0x1800091ff  mov     ecx, eax
0x180009201  call    WX_WIN32_FROM_HR
0x180009206  mov     ebx, eax
0x180009208  test    eax, eax
0x18000920a  jnz     loc_180009513
0x180009210  add     edi, r14d
0x180009213  mov     r14d, [rbp+3Fh+cbData]
0x180009217  jmp     short loc_18000924C
0x180009219  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x180009220  mov     [rbp+3Fh+cbData], 0
0x180009227  call    StringCbLengthW
0x18000922c  test    eax, eax
0x18000922e  jns     short loc_180009238
0x180009230  mov     dword ptr [rbp+3Fh+pcbLength+4], edi
0x180009233  mov     edi, [rbp+3Fh+cbData]
0x180009236  jmp     short loc_18000923B
0x180009238  mov     edi, dword ptr [rbp+3Fh+pcbLength]
0x18000923b  mov     ecx, eax
0x18000923d  call    WX_WIN32_FROM_HR
0x180009242  mov     ebx, eax
0x180009244  test    eax, eax
0x180009246  jnz     loc_180009513
0x18000924c  lea     eax, [rdi+16h]
0x18000924f  add     eax, esi
0x180009251  mov     ecx, eax
0x180009253  mov     esi, eax
0x180009255  call    DhcpAlloc
0x18000925a  mov     [rbp+3Fh+var_78], rax
0x18000925e  mov     rdi, rax
0x180009261  test    rax, rax
0x180009264  jnz     short loc_18000926E
0x180009266  lea     ebx, [rax+8]
0x180009269  jmp     loc_180009513
0x18000926e  test    r15, r15
0x180009271  jz      short loc_180009291
0x180009273  call    DhcpIsWCOSSystem
0x180009278  test    eax, eax
0x18000927a  lea     r8, aSSS; "%s\\?\\%s%s"
0x180009281  lea     rax, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x180009288  mov     r9, r12
0x18000928b  cmovz   r9, rax
0x18000928f  jmp     short loc_18000929F
0x180009291  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x180009298  lea     r8, aSSS_0; "%s\\%s%s"
0x18000929f  lea     rax, [rbp+3Fh+pszDest]
0x1800092a3  mov     rdx, rsi; cbDest
0x1800092a6  mov     qword ptr [rsp+100h+samDesired], rax
0x1800092ab  mov     rcx, rdi; pszDest
0x1800092ae  mov     qword ptr [rsp+100h+dwOptions], r13
0x1800092b3  call    StringCbPrintfW
0x1800092b8  mov     ecx, eax
0x1800092ba  call    WX_WIN32_FROM_HR
0x1800092bf  mov     ebx, eax
0x1800092c1  test    eax, eax
0x1800092c3  jnz     loc_180009513
0x1800092c9  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800092cd  lea     rax, [rbp+3Fh+dwDisposition]
0x1800092d1  mov     [rsp+100h+lpdwDisposition], rax; lpdwDisposition
0x1800092d6  lea     r9, Class; "DhcpClientClass"
0x1800092dd  lea     rax, [rbp+3Fh+var_A0]
0x1800092e1  xor     r8d, r8d; Reserved
0x1800092e4  mov     [rsp+100h+phkResult], rax; phkResult
0x1800092e9  lea     rdx, [rbp+3Fh+pszDest]; lpSubKey
0x1800092ed  mov     [rsp+100h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800092f6  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x1800092fe  mov     [rsp+100h+dwOptions], 0; dwOptions
0x180009306  call    cs:__imp_RegCreateKeyExW
0x18000930c  mov     ebx, eax
0x18000930e  test    eax, eax
0x180009310  jnz     loc_180009513
0x180009316  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x18000931a  lea     ebx, [rax+4]
0x18000931d  lea     rax, [rbp+3Fh+Data]
0x180009321  mov     [rsp+100h+samDesired], ebx; cbData
0x180009325  mov     r9d, ebx; dwType
0x180009328  mov     qword ptr [rsp+100h+dwOptions], rax; lpData
0x18000932d  xor     r8d, r8d; Reserved
0x180009330  lea     rdx, aOptionid; "OptionId"
0x180009337  call    cs:__imp_RegSetValueExW
0x18000933d  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x180009341  lea     rax, [rbp+3Fh+var_90]
0x180009345  mov     [rsp+100h+samDesired], ebx; cbData
0x180009349  lea     rdx, aVendortype; "VendorType"
0x180009350  mov     r9d, ebx; dwType
0x180009353  mov     qword ptr [rsp+100h+dwOptions], rax; lpData
0x180009358  xor     r8d, r8d; Reserved
0x18000935b  call    cs:__imp_RegSetValueExW
0x180009361  xor     ebx, ebx
0x180009363  test    r14d, r14d
0x180009366  jz      short loc_18000938E
0x180009368  mov     rax, [rbp+3Fh+lpData]
0x18000936c  lea     r9d, [rbx+3]; dwType
0x180009370  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x180009374  lea     rdx, aClassid; "ClassId"
0x18000937b  mov     [rsp+100h+samDesired], r14d; cbData
0x180009380  xor     r8d, r8d; Reserved
0x180009383  mov     qword ptr [rsp+100h+dwOptions], rax; lpData
0x180009388  call    cs:__imp_RegSetValueExW
0x18000938e  mov     dword ptr [rbp+3Fh+lpData+4], ebx
0x180009391  lea     r8, [rbp+3Fh+pcbLength]; pcchLength
0x180009395  mov     edx, 7FFFFFFFh; cchMax
0x18000939a  mov     [rbp+3Fh+cbData], ebx
0x18000939d  mov     rcx, rdi; psz
0x1800093a0  mov     [rbp+3Fh+pcbLength], rbx
0x1800093a4  call    StringCchLengthW
0x1800093a9  test    eax, eax
0x1800093ab  jns     short loc_1800093B9
0x1800093ad  mov     dword ptr [rbp+3Fh+lpData+4], 51h ; 'Q'
0x1800093b4  mov     r14d, ebx
0x1800093b7  jmp     short loc_1800093BD
0x1800093b9  mov     r14d, dword ptr [rbp+3Fh+pcbLength]
0x1800093bd  mov     ecx, eax
0x1800093bf  call    WX_WIN32_FROM_HR
0x1800093c4  mov     ebx, eax
0x1800093c6  test    eax, eax
0x1800093c8  jnz     loc_180009513
0x1800093ce  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x1800093d2  lea     eax, ds:2[r14*2]
0x1800093da  mov     [rsp+100h+samDesired], eax; cbData
0x1800093de  lea     r9d, [rbx+1]; dwType
0x1800093e2  xor     r8d, r8d; Reserved
0x1800093e5  mov     qword ptr [rsp+100h+dwOptions], rdi; lpData
0x1800093ea  lea     rdx, aRegsendlocatio; "RegSendLocation"
0x1800093f1  call    cs:__imp_RegSetValueExW
0x1800093f7  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x1800093fb  lea     r9d, [rbx+4]; dwType
0x1800093ff  lea     rax, [rbp+3Fh+var_8C]
0x180009403  mov     [rsp+100h+samDesired], r9d; cbData
0x180009408  xor     r8d, r8d; Reserved
0x18000940b  mov     qword ptr [rsp+100h+dwOptions], rax; lpData
0x180009410  lea     rdx, aKeytype; "KeyType"
0x180009417  mov     dword ptr [rbp+3Fh+var_8C], r9d
0x18000941b  call    cs:__imp_RegSetValueExW
0x180009421  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x180009425  call    cs:__imp_RegCloseKey
0x18000942b  mov     [rbp+3Fh+var_A0], 0
0x180009433  test    r15, r15
0x180009436  jz      short loc_180009466
0x180009438  call    DhcpIsWCOSSystem
0x18000943d  test    eax, eax
0x18000943f  mov     qword ptr [rsp+100h+dwOptions], r15
0x180009444  lea     rax, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18000944b  mov     rdx, rsi; cbDest
0x18000944e  cmovz   r12, rax
0x180009452  lea     r8, aSS_0; "%s\\%s"
0x180009459  mov     r9, r12
0x18000945c  mov     rcx, rdi; pszDest
0x18000945f  call    StringCbPrintfW
0x180009464  jmp     short loc_180009478
0x180009466  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18000946d  mov     rdx, rsi; cbDest
0x180009470  mov     rcx, rdi; pszDest
0x180009473  call    StringCbCopyW
0x180009478  mov     ecx, eax
0x18000947a  call    WX_WIN32_FROM_HR
0x18000947f  mov     ebx, eax
0x180009481  test    eax, eax
0x180009483  jnz     loc_180009513
0x180009489  lea     eax, [r14+1]
0x18000948d  mov     r9, r13
0x180009490  lea     r12, [rdi+rax*2]
0x180009494  mov     eax, r14d
0x180009497  add     rax, rax
0x18000949a  lea     r8, aSS; "%s%s"
0x1800094a1  sub     rsi, rax
0x1800094a4  mov     rcx, r12; pszDest
0x1800094a7  lea     rax, [rbp+3Fh+pszDest]
0x1800094ab  mov     rdx, rsi; cbDest
0x1800094ae  mov     qword ptr [rsp+100h+dwOptions], rax
0x1800094b3  call    StringCbPrintfW
0x1800094b8  mov     ecx, eax
0x1800094ba  call    WX_WIN32_FROM_HR
0x1800094bf  mov     ebx, eax
0x1800094c1  test    eax, eax
0x1800094c3  jnz     short loc_180009513
0x1800094c5  lea     rax, [rbp+3Fh+var_A0]
0x1800094c9  mov     r9d, 0F003Fh; samDesired
0x1800094cf  xor     r8d, r8d; ulOptions
0x1800094d2  mov     qword ptr [rsp+100h+dwOptions], rax; phkResult
0x1800094d7  mov     rdx, rdi; lpSubKey
0x1800094da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800094e1  call    cs:__imp_RegOpenKeyExW
0x1800094e7  mov     ebx, eax
0x1800094e9  test    eax, eax
0x1800094eb  jnz     short loc_180009513
  ... truncated ...
```
