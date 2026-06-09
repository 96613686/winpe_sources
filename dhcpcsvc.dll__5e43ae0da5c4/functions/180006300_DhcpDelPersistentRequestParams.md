# DhcpDelPersistentRequestParams

- ea: `0x180006300`
- end: `0x180006780`
- name: `DhcpDelPersistentRequestParams`
- size: `1152`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x18000beb0`

## callees

- `0x180001f90`
- `0x180002160`
- `0x180002760`
- `0x180002c00`
- `0x180003110`
- `0x180003210`
- `0x180006300`
- `0x18000d3cc`
- `0x18000d440`
- `0x18000d4a4`
- `0x18000e000`
- `0x18000faac`
- `0x180010a94`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800066db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800066db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800066fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800066fa`

## string_xrefs

- `0x18000639f`: `System\CurrentControlSet\Services\Dhcp\Parameters\Options`

## pseudocode

```c
__int64 __fastcall DhcpDelPersistentRequestParams(int a1, const wchar_t *a2)
{
  int v3; // edi
  unsigned int v4; // ebx
  int IsWCOSSystem; // eax
  size_t v6; // rdx
  const WCHAR *v7; // r14
  const wchar_t *v8; // rcx
  HRESULT v9; // eax
  int v10; // esi
  size_t v11; // rdx
  HRESULT v12; // eax
  int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // r8
  size_t v16; // rbx
  wchar_t *v17; // rdi
  int v18; // eax
  const wchar_t *v19; // r9
  unsigned int v20; // eax
  wchar_t *v21; // r13
  wchar_t *v22; // rsi
  __int64 v23; // rax
  unsigned int v24; // r15d
  wchar_t *v25; // rdi
  int v26; // r14d
  __int64 v27; // rbx
  unsigned int v28; // eax
  size_t v29; // rdx
  __int64 v30; // rax
  HRESULT v31; // eax
  __int64 v32; // r15
  unsigned int v33; // eax
  size_t v34; // rdx
  __int64 v35; // rax
  HRESULT v36; // eax
  __int64 v37; // rax
  __int64 v38; // rax
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  wchar_t *String2; // [rsp+38h] [rbp-18h] BYREF
  size_t pcbLength; // [rsp+40h] [rbp-10h] BYREF
  __int64 v43; // [rsp+48h] [rbp-8h] BYREF
  size_t pcchLength; // [rsp+A0h] [rbp+50h] BYREF
  size_t cbDest; // [rsp+A8h] [rbp+58h] BYREF

  hKey = 0;
  v3 = a1;
  LODWORD(cbDest) = 0;
  v43 = 0;
  String2 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SS(a1, 105, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)a2);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v4 = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 106, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_68;
  }
  if ( StringCchLengthW(a2, 0x100u, &pcchLength) < 0 )
  {
    v4 = 111;
    goto LABEL_68;
  }
  IsWCOSSystem = DhcpIsWCOSSystem();
  v7 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
  pcbLength = 0;
  v8 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
  LODWORD(pcchLength) = 0;
  if ( !IsWCOSSystem )
    v8 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
  v9 = StringCbLengthW(v8, v6, &pcbLength);
  if ( v9 >= 0 )
  {
    v10 = pcbLength;
  }
  else
  {
    HIDWORD(pcbLength) = 108;
    v10 = 0;
  }
  v4 = WX_WIN32_FROM_HR((unsigned int)v9);
  if ( !v4 )
  {
    pcbLength = 0;
    LODWORD(pcchLength) = 0;
    if ( a2 )
    {
      v12 = StringCbLengthW(a2, v11, &pcbLength);
      if ( v12 >= 0 )
      {
        v13 = pcbLength;
        goto LABEL_18;
      }
      HIDWORD(pcbLength) = 108;
    }
    else
    {
      v12 = -2147024809;
      HIDWORD(pcbLength) = 104;
    }
    v13 = 0;
LABEL_18:
    v4 = WX_WIN32_FROM_HR((unsigned int)v12);
    if ( v4 )
      goto LABEL_67;
    v16 = (unsigned int)(v10 + v13 + 4);
    v43 = DhcpAlloc(v16, v14, v15);
    v17 = (wchar_t *)v43;
    if ( !v43 )
    {
      v4 = 8;
      goto LABEL_67;
    }
    v18 = DhcpIsWCOSSystem();
    v19 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
    if ( !v18 )
      v19 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
    v20 = StringCbPrintfW(v17, v16, L"%s\\%s", v19, a2);
    v4 = WX_WIN32_FROM_HR(v20);
    if ( !v4 )
    {
      DhcpRegRecurseDelete(HKEY_LOCAL_MACHINE, v17);
      if ( !(unsigned int)DhcpIsWCOSSystem() )
        v7 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
      v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0xFu, &hKey);
      if ( !v4 )
      {
        DhcpRegRecurseDelete(hKey, a2);
        GetRegistryString(hKey);
        v21 = String2;
        if ( !String2 )
        {
          v4 = 2;
          goto LABEL_67;
        }
        v22 = String2;
        v23 = -1;
        do
          ++v23;
        while ( String2[v23] );
        if ( !v23 )
        {
LABEL_65:
          *v22 = 0;
          v4 = RegSetValueExW(hKey, L"DhcpOptionLocationList", 0, 7u, (const BYTE *)v21, (_DWORD)v22 - (_DWORD)v21 + 2);
          goto LABEL_67;
        }
        v24 = cbDest;
        v25 = String2;
        v26 = 0;
        while ( 1 )
        {
          v27 = -1;
          do
            ++v27;
          while ( a2[v27] );
          if ( !wcsncmp_0(a2, v25, (unsigned int)v27) )
          {
            if ( v25[v27] == 92 )
            {
              v37 = -1;
              do
                ++v37;
              while ( v25[v37] );
              v25 += v37 + 1;
              goto LABEL_62;
            }
            v33 = StringCbCopyW(v22, v24, v25);
            v4 = WX_WIN32_FROM_HR(v33);
            if ( v4 )
              break;
            v35 = -1;
            do
              ++v35;
            while ( v25[v35] );
            v22 += v35 + 1;
            cbDest = 0;
            LODWORD(pcchLength) = 0;
            v25 += v35 + 1;
            if ( v25 )
            {
              v36 = StringCbLengthW(v25, v34, &cbDest);
              if ( v36 >= 0 )
                v26 = cbDest;
              else
                HIDWORD(cbDest) = 108;
            }
            else
            {
              v36 = -2147024809;
              HIDWORD(cbDest) = 104;
            }
            v4 = WX_WIN32_FROM_HR((unsigned int)v36);
            if ( v4 )
              break;
            v24 += -2 - v26;
          }
          else
          {
            pcbLength = v24;
            v28 = StringCbCopyW(v22, v24, v25);
            v4 = WX_WIN32_FROM_HR(v28);
            if ( v4 )
              break;
            v30 = -1;
            do
              ++v30;
            while ( v25[v30] );
            v22 += v30 + 1;
            cbDest = 0;
            LODWORD(pcchLength) = 0;
            v25 += v30 + 1;
            if ( v25 )
            {
              v31 = StringCbLengthW(v25, v29, &cbDest);
              if ( v31 >= 0 )
                v26 = cbDest;
              else
                HIDWORD(cbDest) = 108;
            }
            else
            {
              v31 = -2147024809;
              HIDWORD(cbDest) = 104;
            }
            v4 = WX_WIN32_FROM_HR((unsigned int)v31);
            if ( v4 )
              break;
            v32 = v24 - v26;
            if ( v32 - 2 > pcbLength )
            {
              v4 = 87;
              break;
            }
            v24 = v32 - 2;
          }
          v26 = 0;
LABEL_62:
          v38 = -1;
          do
            ++v38;
          while ( v25[v38] );
          if ( !v38 )
            goto LABEL_65;
        }
      }
    }
LABEL_67:
    v3 = a1;
  }
LABEL_68:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  DhcpFree(&v43);
  DhcpFree(&String2);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 107, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v3, v4);
  return v4;
}

```

## disassembly

```asm
0x180006300  mov     [rsp-38h+arg_8], rbx
0x180006305  mov     [rsp-38h+arg_0], rcx
0x18000630a  push    rbp
0x18000630b  push    rsi
0x18000630c  push    rdi
0x18000630d  push    r12
0x18000630f  push    r13
0x180006311  push    r14
0x180006313  push    r15
0x180006315  mov     rbp, rsp
0x180006318  sub     rsp, 50h
0x18000631c  xor     r15d, r15d
0x18000631f  mov     r12, rdx
0x180006322  mov     [rbp+hKey], r15
0x180006326  mov     rdi, rcx
0x180006329  mov     dword ptr [rbp+cbDest], r15d
0x18000632d  mov     [rbp+var_8], r15
0x180006331  mov     [rbp+String2], r15
0x180006335  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000633c  jz      short loc_180006356
0x18000633e  lea     edx, [r15+69h]
0x180006342  mov     [rsp+50h+phkResult], r12
0x180006347  mov     r9, rcx
0x18000634a  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006351  call    WPP_SF_SS
0x180006356  call    DhcpIsFSEGuestSystem
0x18000635b  test    eax, eax
0x18000635d  jnz     loc_180006756
0x180006363  lea     r8, [rbp+pcchLength]; pcchLength
0x180006367  mov     edx, 100h; cchMax
0x18000636c  mov     rcx, r12; psz
0x18000636f  call    StringCchLengthW
0x180006374  test    eax, eax
0x180006376  jns     short loc_180006382
0x180006378  mov     ebx, 6Fh ; 'o'
0x18000637d  jmp     loc_1800066F1
0x180006382  call    DhcpIsWCOSSystem
0x180006387  mov     dword ptr [rbp+pcbLength+4], r15d
0x18000638b  lea     r14, aOsdataNetworki_1; "OSDATA\\Networking\\Dhcp\\Client4\\Para"...
0x180006392  test    eax, eax
0x180006394  mov     [rbp-10h], r15
0x180006398  mov     rcx, r14
0x18000639b  mov     dword ptr [rbp+pcchLength], r15d
0x18000639f  lea     r13, psz; "System\\CurrentControlSet\\Services\\Dh"...
0x1800063a6  cmovz   rcx, r13; psz
0x1800063aa  lea     r8, [rbp+pcbLength]; pcbLength
0x1800063ae  call    StringCbLengthW
0x1800063b3  test    eax, eax
0x1800063b5  jns     short loc_1800063C3
0x1800063b7  mov     dword ptr [rbp+pcbLength+4], 6Ch ; 'l'
0x1800063be  mov     esi, r15d
0x1800063c1  jmp     short loc_1800063C6
0x1800063c3  mov     esi, dword ptr [rbp+pcbLength]
0x1800063c6  mov     ecx, eax
0x1800063c8  call    WX_WIN32_FROM_HR
0x1800063cd  mov     ebx, eax
0x1800063cf  test    eax, eax
0x1800063d1  jnz     loc_1800066F1
0x1800063d7  mov     dword ptr [rbp+pcbLength+4], r15d
0x1800063db  mov     [rbp+pcbLength], r15
0x1800063df  mov     dword ptr [rbp+pcchLength], r15d
0x1800063e3  test    r12, r12
0x1800063e6  jnz     short loc_1800063F9
0x1800063e8  mov     eax, 80070057h
0x1800063ed  mov     dword ptr [rbp+pcbLength+4], 68h ; 'h'
0x1800063f4  mov     edi, r15d
0x1800063f7  jmp     short loc_180006415
0x1800063f9  lea     r8, [rbp+pcbLength]; pcbLength
0x1800063fd  mov     rcx, r12; psz
0x180006400  call    StringCbLengthW
0x180006405  test    eax, eax
0x180006407  jns     short loc_180006412
0x180006409  mov     dword ptr [rbp+pcbLength+4], 6Ch ; 'l'
0x180006410  jmp     short loc_1800063F4
0x180006412  mov     edi, dword ptr [rbp+pcbLength]
0x180006415  mov     ecx, eax
0x180006417  call    WX_WIN32_FROM_HR
0x18000641c  mov     ebx, eax
0x18000641e  test    eax, eax
0x180006420  jnz     loc_1800066ED
0x180006426  lea     eax, [rdi+4]
0x180006429  add     eax, esi
0x18000642b  mov     ecx, eax
0x18000642d  mov     ebx, eax
0x18000642f  call    DhcpAlloc
0x180006434  mov     [rbp+var_8], rax
0x180006438  mov     rdi, rax
0x18000643b  test    rax, rax
0x18000643e  jnz     short loc_180006448
0x180006440  lea     ebx, [rax+8]
0x180006443  jmp     loc_1800066ED
0x180006448  call    DhcpIsWCOSSystem
0x18000644d  test    eax, eax
0x18000644f  mov     [rsp+50h+phkResult], r12
0x180006454  mov     r9, r14
0x180006457  lea     r8, aSS_0; "%s\\%s"
0x18000645e  cmovz   r9, r13
0x180006462  mov     rdx, rbx; cbDest
0x180006465  mov     rcx, rdi; pszDest
0x180006468  call    StringCbPrintfW
0x18000646d  mov     ecx, eax
0x18000646f  call    WX_WIN32_FROM_HR
0x180006474  mov     ebx, eax
0x180006476  test    eax, eax
0x180006478  jnz     loc_1800066ED
0x18000647e  mov     rbx, 0FFFFFFFF80000002h
0x180006485  mov     rdx, rdi; lpSubKey
0x180006488  mov     rcx, rbx; hKey
0x18000648b  call    DhcpRegRecurseDelete
0x180006490  call    DhcpIsWCOSSystem
0x180006495  test    eax, eax
0x180006497  mov     r9d, 0Fh; samDesired
0x18000649d  lea     rax, [rbp+hKey]
0x1800064a1  mov     rcx, rbx; hKey
0x1800064a4  cmovz   r14, r13
0x1800064a8  mov     [rsp+50h+phkResult], rax; phkResult
0x1800064ad  mov     rdx, r14; lpSubKey
0x1800064b0  xor     r8d, r8d; ulOptions
0x1800064b3  call    cs:__imp_RegOpenKeyExW
0x1800064b9  mov     ebx, eax
0x1800064bb  test    eax, eax
0x1800064bd  jnz     loc_1800066ED
0x1800064c3  mov     rcx, [rbp+hKey]; hKey
0x1800064c7  mov     rdx, r12; lpSubKey
0x1800064ca  call    DhcpRegRecurseDelete
0x1800064cf  mov     rcx, [rbp+hKey]; hKey
0x1800064d3  lea     r9, [rbp+cbDest]
0x1800064d7  lea     r8, [rbp+String2]
0x1800064db  call    GetRegistryString
0x1800064e0  mov     r13, [rbp+String2]
0x1800064e4  test    r13, r13
0x1800064e7  jnz     short loc_1800064F2
0x1800064e9  lea     ebx, [r13+2]
0x1800064ed  jmp     loc_1800066ED
0x1800064f2  mov     rsi, r13
0x1800064f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800064f9  inc     rax
0x1800064fc  cmp     [r13+rax*2+0], r15w
0x180006502  jnz     short loc_1800064F9
0x180006504  test    rax, rax
0x180006507  jz      loc_1800066B4
0x18000650d  mov     r15d, dword ptr [rbp+cbDest]
0x180006511  mov     rdi, r13
0x180006514  xor     r14d, r14d
0x180006517  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000651b  inc     rbx
0x18000651e  cmp     [r12+rbx*2], r14w
0x180006523  jnz     short loc_18000651B
0x180006525  mov     r8d, ebx; MaxCount
0x180006528  mov     rdx, rdi; String2
0x18000652b  mov     rcx, r12; String1
0x18000652e  call    wcsncmp_0
0x180006533  test    eax, eax
0x180006535  jz      loc_1800065E6
0x18000653b  mov     eax, r15d
0x18000653e  mov     r8, rdi; pszSrc
0x180006541  mov     edx, r15d; cbDest
0x180006544  mov     rcx, rsi; pszDest
0x180006547  mov     [rbp+pcbLength], rax
0x18000654b  call    StringCbCopyW
0x180006550  mov     ecx, eax
0x180006552  call    WX_WIN32_FROM_HR
0x180006557  mov     ebx, eax
0x180006559  test    eax, eax
0x18000655b  jnz     loc_1800066EA
0x180006561  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006565  inc     rax
0x180006568  cmp     [rdi+rax*2], r14w
0x18000656d  jnz     short loc_180006565
0x18000656f  mov     dword ptr [rbp+cbDest+4], r14d
0x180006573  lea     rsi, [rsi+rax*2]
0x180006577  add     rsi, 2
0x18000657b  mov     [rbp+cbDest], r14
0x18000657f  lea     rdi, [rdi+rax*2]
0x180006583  mov     dword ptr [rbp+pcchLength], r14d
0x180006587  add     rdi, 2
0x18000658b  jnz     short loc_18000659B
0x18000658d  mov     eax, 80070057h
0x180006592  mov     dword ptr [rbp+cbDest+4], 68h ; 'h'
0x180006599  jmp     short loc_1800065B8
0x18000659b  lea     r8, [rbp+cbDest]; pcbLength
0x18000659f  mov     rcx, rdi; psz
0x1800065a2  call    StringCbLengthW
0x1800065a7  test    eax, eax
0x1800065a9  jns     short loc_1800065B4
0x1800065ab  mov     dword ptr [rbp+cbDest+4], 6Ch ; 'l'
0x1800065b2  jmp     short loc_180006599
0x1800065b4  mov     r14d, dword ptr [rbp+cbDest]
0x1800065b8  mov     ecx, eax
0x1800065ba  call    WX_WIN32_FROM_HR
0x1800065bf  mov     ebx, eax
0x1800065c1  test    eax, eax
0x1800065c3  jnz     loc_1800066EA
0x1800065c9  sub     r15d, r14d
0x1800065cc  lea     rax, [r15-2]
0x1800065d0  cmp     rax, [rbp+pcbLength]
0x1800065d4  ja      loc_1800066E5
0x1800065da  add     r15d, 0FFFFFFFEh
0x1800065de  xor     r14d, r14d
0x1800065e1  jmp     loc_18000669A
0x1800065e6  cmp     word ptr [rdi+rbx*2], 5Ch ; '\'
0x1800065eb  jz      loc_180006684
0x1800065f1  mov     edx, r15d; cbDest
0x1800065f4  mov     r8, rdi; pszSrc
0x1800065f7  mov     rcx, rsi; pszDest
0x1800065fa  call    StringCbCopyW
0x1800065ff  mov     ecx, eax
0x180006601  call    WX_WIN32_FROM_HR
0x180006606  mov     ebx, eax
0x180006608  test    eax, eax
0x18000660a  jnz     loc_1800066EA
0x180006610  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006614  inc     rax
0x180006617  cmp     [rdi+rax*2], r14w
0x18000661c  jnz     short loc_180006614
0x18000661e  mov     dword ptr [rbp+cbDest+4], r14d
0x180006622  lea     rsi, [rsi+rax*2]
0x180006626  add     rsi, 2
0x18000662a  mov     [rbp+cbDest], r14
0x18000662e  lea     rdi, [rdi+rax*2]
0x180006632  mov     dword ptr [rbp+pcchLength], r14d
0x180006636  add     rdi, 2
0x18000663a  jnz     short loc_18000664A
0x18000663c  mov     eax, 80070057h
0x180006641  mov     dword ptr [rbp+cbDest+4], 68h ; 'h'
0x180006648  jmp     short loc_180006667
0x18000664a  lea     r8, [rbp+cbDest]; pcbLength
0x18000664e  mov     rcx, rdi; psz
0x180006651  call    StringCbLengthW
0x180006656  test    eax, eax
0x180006658  jns     short loc_180006663
0x18000665a  mov     dword ptr [rbp+cbDest+4], 6Ch ; 'l'
0x180006661  jmp     short loc_180006648
0x180006663  mov     r14d, dword ptr [rbp+cbDest]
0x180006667  mov     ecx, eax
0x180006669  call    WX_WIN32_FROM_HR
0x18000666e  mov     ebx, eax
0x180006670  test    eax, eax
0x180006672  jnz     short loc_1800066EA
0x180006674  mov     eax, 0FFFFFFFEh
0x180006679  sub     eax, r14d
0x18000667c  add     r15d, eax
0x18000667f  jmp     loc_1800065DE
0x180006684  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006688  inc     rax
0x18000668b  cmp     [rdi+rax*2], r14w
0x180006690  jnz     short loc_180006688
0x180006692  lea     rdi, [rdi+rax*2]
0x180006696  add     rdi, 2
0x18000669a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000669e  inc     rax
0x1800066a1  cmp     [rdi+rax*2], r14w
0x1800066a6  jnz     short loc_18000669E
0x1800066a8  test    rax, rax
0x1800066ab  jnz     loc_180006517
0x1800066b1  xor     r15d, r15d
0x1800066b4  mov     [rsi], r15w
0x1800066b8  lea     rdx, aDhcpoptionloca; "DhcpOptionLocationList"
0x1800066bf  mov     rcx, [rbp+hKey]; hKey
0x1800066c3  sub     esi, r13d
0x1800066c6  add     esi, 2
0x1800066c9  mov     r9d, 7; dwType
0x1800066cf  mov     [rsp+50h+cbData], esi; cbData
0x1800066d3  xor     r8d, r8d; Reserved
0x1800066d6  mov     [rsp+50h+phkResult], r13; lpData
0x1800066db  call    cs:__imp_RegSetValueExW
0x1800066e1  mov     ebx, eax
0x1800066e3  jmp     short loc_1800066ED
0x1800066e5  mov     ebx, 57h ; 'W'
0x1800066ea  xor     r15d, r15d
0x1800066ed  mov     rdi, [rbp+arg_0]
0x1800066f1  mov     rcx, [rbp+hKey]; hKey
0x1800066f5  test    rcx, rcx
0x1800066f8  jz      short loc_180006704
0x1800066fa  call    cs:__imp_RegCloseKey
0x180006700  mov     [rbp+hKey], r15
0x180006704  lea     rcx, [rbp+var_8]
0x180006708  call    DhcpFree
0x18000670d  lea     rcx, [rbp+String2]
0x180006711  call    DhcpFree
0x180006716  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000671d  jz      short loc_18000673C
0x18000671f  mov     edx, 6Bh ; 'k'
0x180006724  mov     dword ptr [rsp+50h+phkResult], ebx
0x180006728  mov     ecx, 404h
0x18000672d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006734  mov     r9, rdi
0x180006737  call    WPP_SF_SD
0x18000673c  mov     eax, ebx
0x18000673e  mov     rbx, [rsp+50h+arg_8]
0x180006746  add     rsp, 50h
0x18000674a  pop     r15
0x18000674c  pop     r14
0x18000674e  pop     r13
0x180006750  pop     r12
0x180006752  pop     rdi
0x180006753  pop     rsi
0x180006754  pop     rbp
0x180006755  retn
0x180006756  mov     ebx, 32h ; '2'
  ... truncated ...
```
