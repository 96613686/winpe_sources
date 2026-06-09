# DhcpRegistryFillParamsList

- ea: `0x180009584`
- end: `0x180009918`
- name: `DhcpRegistryFillParamsList`
- size: `916`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH psz)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180009920`

## callees

- `0x180001f90`
- `0x180002160`
- `0x180002c00`
- `0x180003110`
- `0x180003210`
- `0x180009584`
- `0x18000d3cc`
- `0x18000d440`
- `0x18000d4a4`
- `0x18000faac`
- `0x180011598`
- `0x180012a00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009608`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009608`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000989b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000989b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800098af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800098af`

## string_xrefs

- `0x1800095dd`: `System\CurrentControlSet\Services\Dhcp\Parameters\Options`

## pseudocode

```c
__int64 __fastcall DhcpRegistryFillParamsList(STRSAFE_PCNZWCH psz, unsigned int a2, int a3)
{
  int v3; // esi
  int IsWCOSSystem; // eax
  const WCHAR *v7; // rdx
  unsigned int v8; // ebx
  size_t v9; // rdx
  const wchar_t *v10; // r15
  int v11; // r14d
  HRESULT v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // esi
  size_t v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  wchar_t *v19; // r12
  unsigned int v20; // esi
  BYTE *v21; // r14
  unsigned int v22; // eax
  unsigned int v23; // r12d
  unsigned int v24; // r13d
  wchar_t *v25; // rdi
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // r11d
  HRESULT v29; // eax
  unsigned int v30; // r14d
  __int64 v31; // rax
  bool v32; // zf
  HRESULT v33; // eax
  unsigned int v34; // eax
  const wchar_t *v35; // r15
  unsigned int v36; // esi
  PHKEY phkResult; // [rsp+20h] [rbp-50h]
  unsigned int v39; // [rsp+30h] [rbp-40h]
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v41; // [rsp+40h] [rbp-30h] BYREF
  __int64 v42; // [rsp+48h] [rbp-28h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-20h] BYREF
  size_t pcbLength; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int64 v45; // [rsp+60h] [rbp-10h]
  int v47; // [rsp+C0h] [rbp+50h]

  v3 = 0;
  hKey = 0;
  v47 = 0;
  v41 = 0;
  lpData = 0;
  v42 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Sd((_DWORD)psz, a2, a3, (_DWORD)psz, a2);
  IsWCOSSystem = DhcpIsWCOSSystem();
  v7 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
  if ( !IsWCOSSystem )
    v7 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0xFu, &hKey);
  if ( !v8 )
  {
    if ( (unsigned int)GetRegistryString(hKey) )
    {
      v10 = L"1";
      v41 = L"1";
      v11 = 84;
    }
    else
    {
      v10 = v41;
      v11 = 0;
      v47 = 1;
    }
    pcbLength = 0;
    v39 = v11;
    if ( psz )
    {
      v12 = StringCbLengthW(psz, v9, &pcbLength);
      if ( v12 >= 0 )
        v3 = pcbLength;
      else
        HIDWORD(pcbLength) = 108;
    }
    else
    {
      v12 = -2147024809;
      HIDWORD(pcbLength) = 104;
    }
    v8 = WX_WIN32_FROM_HR((unsigned int)v12);
    if ( !v8 )
    {
      v15 = v3 + 14;
      v16 = v15;
      v42 = DhcpAlloc(v15, v13, v14);
      v19 = (wchar_t *)v42;
      if ( !v42 || (v20 = v11 + a2 * v15, lpData = (BYTE *)DhcpAlloc(v20, v17, v18), (v21 = lpData) == 0) )
      {
        v8 = 8;
        goto LABEL_45;
      }
      v22 = StringCbPrintfW(v19, v16, L"%s\\", psz);
      v8 = WX_WIN32_FROM_HR(v22);
      if ( !v8 )
      {
        v23 = v20;
        v24 = 0;
        v25 = (wchar_t *)v21;
        while ( v24 < a2 )
        {
          v45 = v23;
          LODWORD(phkResult) = v24;
          v26 = StringCbPrintfW(v25, v23, L"%s%5x", v42, phkResult);
          v27 = WX_WIN32_FROM_HR(v26);
          v28 = 0;
          v8 = v27;
          if ( v27 )
            goto LABEL_45;
          pcbLength = 0;
          if ( !v25 )
          {
            v29 = -2147024809;
            HIDWORD(pcbLength) = 77;
LABEL_24:
            v30 = v28;
            goto LABEL_28;
          }
          v29 = StringCchLengthW(v25, (unsigned __int64)v20 >> 1, &pcbLength);
          if ( v29 < 0 )
          {
            HIDWORD(pcbLength) = 81;
            goto LABEL_24;
          }
          v30 = pcbLength;
LABEL_28:
          v8 = WX_WIN32_FROM_HR((unsigned int)v29);
          if ( v8 )
            goto LABEL_45;
          v31 = 2LL * v30;
          v25 = (wchar_t *)((char *)v25 + v31 + 2);
          if ( v45 - v31 - 2 > v45 )
          {
            v8 = 87;
            goto LABEL_45;
          }
          v23 += -2 - 2 * v30;
          ++v24;
        }
        v32 = v10 == 0;
        while ( 1 )
        {
          pcbLength = 0;
          if ( v32 )
            break;
          v33 = StringCchLengthW(v10, (unsigned __int64)v39 >> 1, &pcbLength);
          if ( v33 < 0 )
          {
            HIDWORD(pcbLength) = 81;
LABEL_40:
            v36 = 0;
            goto LABEL_42;
          }
          v36 = pcbLength;
LABEL_42:
          v8 = WX_WIN32_FROM_HR((unsigned int)v33);
          if ( v8 )
            goto LABEL_45;
          if ( !v36 )
          {
            *v25 = 0;
            v8 = RegSetValueExW(hKey, L"DhcpOptionLocationList", 0, 7u, lpData, (_DWORD)v25 - (_DWORD)lpData + 2);
            goto LABEL_45;
          }
          v34 = StringCbCopyW(v25, v23, v10);
          v8 = WX_WIN32_FROM_HR(v34);
          if ( v8 )
            goto LABEL_45;
          v35 = &v10[v36];
          v25 += v36 + 1;
          v23 = v23 - 2 * v36 - 2;
          v32 = v35 + 1 == 0;
          v10 = v35 + 1;
        }
        v33 = -2147024809;
        HIDWORD(pcbLength) = 77;
        goto LABEL_40;
      }
    }
LABEL_45:
    v3 = v47;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  DhcpFree(&v42);
  if ( v3 )
    DhcpFree(&v41);
  DhcpFree(&lpData);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 92, WPP_e15037783097355a5233924022d92169_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180009584  mov     [rsp-38h+arg_0], rbx
0x180009589  mov     [rsp-38h+arg_8], edx
0x18000958d  push    rbp
0x18000958e  push    rsi
0x18000958f  push    rdi
0x180009590  push    r12
0x180009592  push    r13
0x180009594  push    r14
0x180009596  push    r15
0x180009598  mov     rbp, rsp
0x18000959b  sub     rsp, 70h
0x18000959f  xor     esi, esi
0x1800095a1  mov     [rbp+hKey], 0
0x1800095a9  mov     [rbp+arg_10], esi
0x1800095ac  mov     r13d, edx
0x1800095af  mov     [rbp+var_30], rsi
0x1800095b3  mov     rdi, rcx
0x1800095b6  mov     [rbp+lpData], rsi
0x1800095ba  mov     [rbp+var_28], rsi
0x1800095be  mov     [rbp+arg_18], esi
0x1800095c1  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800095c8  jz      short loc_1800095D6
0x1800095ca  mov     r9, rcx
0x1800095cd  mov     dword ptr [rsp+70h+phkResult], edx
0x1800095d1  call    WPP_SF_Sd
0x1800095d6  call    DhcpIsWCOSSystem
0x1800095db  test    eax, eax
0x1800095dd  lea     rcx, psz; "System\\CurrentControlSet\\Services\\Dh"...
0x1800095e4  lea     rax, [rbp+hKey]
0x1800095e8  mov     r9d, 0Fh; samDesired
0x1800095ee  lea     rdx, aOsdataNetworki_1; "OSDATA\\Networking\\Dhcp\\Client4\\Para"...
0x1800095f5  mov     [rsp+70h+phkResult], rax; phkResult
0x1800095fa  cmovz   rdx, rcx; lpSubKey
0x1800095fe  xor     r8d, r8d; ulOptions
0x180009601  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009608  call    cs:__imp_RegOpenKeyExW
0x18000960e  mov     ebx, eax
0x180009610  test    eax, eax
0x180009612  jnz     loc_1800098A6
0x180009618  mov     rcx, [rbp+hKey]; hKey
0x18000961c  lea     r9, [rbp+arg_18]
0x180009620  lea     r8, [rbp+var_30]
0x180009624  call    GetRegistryString
0x180009629  test    eax, eax
0x18000962b  jz      short loc_18000963E
0x18000962d  lea     r15, a1; "1"
0x180009634  mov     [rbp+var_30], r15
0x180009638  lea     r14d, [rbx+54h]
0x18000963c  jmp     short loc_18000964D
0x18000963e  mov     r15, [rbp+var_30]
0x180009642  mov     r14d, [rbp+arg_18]
0x180009646  mov     [rbp+arg_10], 1
0x18000964d  mov     dword ptr [rbp+pcbLength+4], esi
0x180009650  mov     [rbp-18h], rsi
0x180009654  mov     [rbp+arg_18], esi
0x180009657  mov     [rbp+var_40], r14d
0x18000965b  test    rdi, rdi
0x18000965e  jnz     short loc_18000966E
0x180009660  mov     eax, 80070057h
0x180009665  mov     dword ptr [rbp+pcbLength+4], 68h ; 'h'
0x18000966c  jmp     short loc_18000968A
0x18000966e  lea     r8, [rbp+pcbLength]; pcbLength
0x180009672  mov     rcx, rdi; psz
0x180009675  call    StringCbLengthW
0x18000967a  test    eax, eax
0x18000967c  jns     short loc_180009687
0x18000967e  mov     dword ptr [rbp+pcbLength+4], 6Ch ; 'l'
0x180009685  jmp     short loc_18000966C
0x180009687  mov     esi, dword ptr [rbp+pcbLength]
0x18000968a  mov     ecx, eax
0x18000968c  call    WX_WIN32_FROM_HR
0x180009691  mov     ebx, eax
0x180009693  test    eax, eax
0x180009695  jnz     loc_1800098A3
0x18000969b  add     esi, 0Eh
0x18000969e  mov     ecx, esi
0x1800096a0  mov     ebx, esi
0x1800096a2  call    DhcpAlloc
0x1800096a7  mov     [rbp+var_28], rax
0x1800096ab  mov     r12, rax
0x1800096ae  test    rax, rax
0x1800096b1  jnz     short loc_1800096BD
0x1800096b3  mov     ebx, 8
0x1800096b8  jmp     loc_1800098A3
0x1800096bd  imul    esi, r13d
0x1800096c1  add     esi, r14d
0x1800096c4  mov     ecx, esi
0x1800096c6  call    DhcpAlloc
0x1800096cb  mov     [rbp+lpData], rax
0x1800096cf  mov     r14, rax
0x1800096d2  test    rax, rax
0x1800096d5  jz      short loc_1800096B3
0x1800096d7  mov     r9, rdi
0x1800096da  lea     r8, aS; "%s\\"
0x1800096e1  mov     rdx, rbx; cbDest
0x1800096e4  mov     rcx, r12; pszDest
0x1800096e7  call    StringCbPrintfW
0x1800096ec  mov     ecx, eax
0x1800096ee  call    WX_WIN32_FROM_HR
0x1800096f3  mov     ebx, eax
0x1800096f5  test    eax, eax
0x1800096f7  jnz     loc_1800098A3
0x1800096fd  mov     r12d, esi
0x180009700  xor     r13d, r13d
0x180009703  mov     rdi, r14
0x180009706  cmp     r13d, [rbp+arg_8]
0x18000970a  jnb     loc_1800097D9
0x180009710  mov     r9, [rbp+var_28]
0x180009714  lea     r8, aS5x; "%s%5x"
0x18000971b  mov     eax, r12d
0x18000971e  mov     rcx, rdi; pszDest
0x180009721  mov     edx, r12d; cbDest
0x180009724  mov     [rbp+var_10], rax
0x180009728  mov     dword ptr [rsp+70h+phkResult], r13d
0x18000972d  call    StringCbPrintfW
0x180009732  mov     ecx, eax
0x180009734  call    WX_WIN32_FROM_HR
0x180009739  xor     r11d, r11d
0x18000973c  mov     ebx, eax
0x18000973e  test    eax, eax
0x180009740  jnz     loc_1800098A3
0x180009746  mov     dword ptr [rbp+pcbLength+4], r11d
0x18000974a  mov     [rbp+pcbLength], r11
0x18000974e  mov     [rbp+arg_18], r11d
0x180009752  test    rdi, rdi
0x180009755  jnz     short loc_180009768
0x180009757  mov     eax, 80070057h
0x18000975c  mov     dword ptr [rbp+pcbLength+4], 4Dh ; 'M'
0x180009763  mov     r14d, r11d
0x180009766  jmp     short loc_18000978A
0x180009768  mov     edx, esi
0x18000976a  lea     r8, [rbp+pcbLength]; pcchLength
0x18000976e  shr     rdx, 1; cchMax
0x180009771  mov     rcx, rdi; psz
0x180009774  call    StringCchLengthW
0x180009779  test    eax, eax
0x18000977b  jns     short loc_180009786
0x18000977d  mov     dword ptr [rbp+pcbLength+4], 51h ; 'Q'
0x180009784  jmp     short loc_180009763
0x180009786  mov     r14d, dword ptr [rbp+pcbLength]
0x18000978a  mov     ecx, eax
0x18000978c  call    WX_WIN32_FROM_HR
0x180009791  mov     ebx, eax
0x180009793  test    eax, eax
0x180009795  jnz     loc_1800098A3
0x18000979b  mov     rcx, [rbp+var_10]
0x18000979f  add     rdi, 2
0x1800097a3  mov     eax, r14d
0x1800097a6  add     rax, rax
0x1800097a9  sub     rcx, rax
0x1800097ac  add     rdi, rax
0x1800097af  sub     rcx, 2
0x1800097b3  cmp     rcx, [rbp+var_10]
0x1800097b7  ja      short loc_1800097CF
0x1800097b9  lea     eax, [r14+r14]
0x1800097bd  mov     ecx, 0FFFFFFFEh
0x1800097c2  sub     ecx, eax
0x1800097c4  add     r12d, ecx
0x1800097c7  inc     r13d
0x1800097ca  jmp     loc_180009706
0x1800097cf  mov     ebx, 57h ; 'W'
0x1800097d4  jmp     loc_1800098A3
0x1800097d9  mov     r14d, [rbp+var_40]
0x1800097dd  xor     r13d, r13d
0x1800097e0  shr     r14, 1
0x1800097e3  test    r15, r15
0x1800097e6  mov     dword ptr [rbp+pcbLength+4], r13d
0x1800097ea  mov     [rbp+arg_18], r13d
0x1800097ee  mov     [rbp+pcbLength], r13
0x1800097f2  jz      short loc_18000984D
0x1800097f4  lea     r8, [rbp+pcbLength]; pcchLength
0x1800097f8  mov     rdx, r14; cchMax
0x1800097fb  mov     rcx, r15; psz
0x1800097fe  call    StringCchLengthW
0x180009803  test    eax, eax
0x180009805  jns     short loc_18000985E
0x180009807  mov     dword ptr [rbp+pcbLength+4], 51h ; 'Q'
0x18000980e  jmp     short loc_180009859
0x180009810  test    esi, esi
0x180009812  jz      short loc_180009870
0x180009814  mov     edx, r12d; cbDest
0x180009817  mov     r8, r15; pszSrc
0x18000981a  mov     rcx, rdi; pszDest
0x18000981d  call    StringCbCopyW
0x180009822  mov     ecx, eax
0x180009824  call    WX_WIN32_FROM_HR
0x180009829  mov     ebx, eax
0x18000982b  test    eax, eax
0x18000982d  jnz     short loc_1800098A3
0x18000982f  mov     eax, esi
0x180009831  lea     rdi, [rdi+rax*2]
0x180009835  lea     r15, [r15+rax*2]
0x180009839  add     rdi, 2
0x18000983d  lea     eax, [rsi+rsi]
0x180009840  sub     r12d, eax
0x180009843  sub     r12d, 2
0x180009847  add     r15, 2
0x18000984b  jmp     short loc_1800097E6
0x18000984d  mov     eax, 80070057h
0x180009852  mov     dword ptr [rbp+pcbLength+4], 4Dh ; 'M'
0x180009859  mov     esi, r13d
0x18000985c  jmp     short loc_180009861
0x18000985e  mov     esi, dword ptr [rbp+pcbLength]
0x180009861  mov     ecx, eax
0x180009863  call    WX_WIN32_FROM_HR
0x180009868  mov     ebx, eax
0x18000986a  test    eax, eax
0x18000986c  jz      short loc_180009810
0x18000986e  jmp     short loc_1800098A3
0x180009870  xor     eax, eax
0x180009872  lea     rdx, aDhcpoptionloca; "DhcpOptionLocationList"
0x180009879  mov     [rdi], ax
0x18000987c  mov     r9d, 7; dwType
0x180009882  mov     rax, [rbp+lpData]
0x180009886  xor     r8d, r8d; Reserved
0x180009889  mov     rcx, [rbp+hKey]; hKey
0x18000988d  sub     edi, eax
0x18000988f  add     edi, 2
0x180009892  mov     [rsp+70h+cbData], edi; cbData
0x180009896  mov     [rsp+70h+phkResult], rax; lpData
0x18000989b  call    cs:__imp_RegSetValueExW
0x1800098a1  mov     ebx, eax
0x1800098a3  mov     esi, [rbp+arg_10]
0x1800098a6  mov     rcx, [rbp+hKey]; hKey
0x1800098aa  test    rcx, rcx
0x1800098ad  jz      short loc_1800098BD
0x1800098af  call    cs:__imp_RegCloseKey
0x1800098b5  mov     [rbp+hKey], 0
0x1800098bd  lea     rcx, [rbp+var_28]
0x1800098c1  call    DhcpFree
0x1800098c6  test    esi, esi
0x1800098c8  jz      short loc_1800098D3
0x1800098ca  lea     rcx, [rbp+var_30]
0x1800098ce  call    DhcpFree
0x1800098d3  lea     rcx, [rbp+lpData]
0x1800098d7  call    DhcpFree
0x1800098dc  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800098e3  jz      short loc_1800098FE
0x1800098e5  mov     edx, 5Ch ; '\'
0x1800098ea  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800098f1  mov     ecx, 404h
0x1800098f6  mov     r9d, ebx
0x1800098f9  call    WPP_SF_d
0x1800098fe  mov     eax, ebx
0x180009900  mov     rbx, [rsp+70h+arg_0]
0x180009908  add     rsp, 70h
0x18000990c  pop     r15
0x18000990e  pop     r14
0x180009910  pop     r13
0x180009912  pop     r12
0x180009914  pop     rdi
0x180009915  pop     rsi
0x180009916  pop     rbp
0x180009917  retn
```
