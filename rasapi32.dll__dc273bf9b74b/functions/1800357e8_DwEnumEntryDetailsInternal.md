# DwEnumEntryDetailsInternal

- ea: `0x1800357e8`
- end: `0x18003604e`
- name: `DwEnumEntryDetailsInternal`
- size: `2150`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800356f0`
- `0x180097890`

## callees

- `0x180007b98`
- `0x180009dd0`
- `0x18000b0f4`
- `0x18000ced8`
- `0x180010d10`
- `0x1800357e8`
- `0x1800430dc`
- `0x18004e580`
- `0x18004e984`
- `0x1800c5520`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035db9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035db9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035b50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035be4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035b50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035be4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180035cb0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180035cb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fc4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180035b1d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180035bae`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180035b1d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180035bae`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180035c70`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180035c70`

## string_xrefs

- `0x180035b32`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`
- `0x180035bcc`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`
- `0x180035b23`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`
- `0x180035bb4`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`

## pseudocode

```c
__int64 __fastcall DwEnumEntryDetailsInternal(unsigned int a1, wchar_t *a2, _DWORD *a3, _DWORD *a4, int *a5)
{
  _DWORD *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  int *v12; // r15
  LPCWSTR v13; // rsi
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // esi
  unsigned int v17; // edx
  unsigned int v18; // r8d
  unsigned int v19; // esi
  unsigned int v20; // eax
  unsigned int v21; // ecx
  unsigned int v22; // esi
  unsigned int v23; // edx
  unsigned int v24; // eax
  _DWORD *v25; // r12
  char IsStateSeparationEnabled; // al
  const WCHAR *v27; // rdx
  unsigned int v28; // eax
  bool v29; // zf
  const WCHAR *v30; // rax
  unsigned int v31; // eax
  WCHAR *v32; // rax
  unsigned int v33; // edx
  unsigned int v34; // r8d
  LSTATUS v35; // eax
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r9
  unsigned int v39; // eax
  unsigned int RasTlsDll; // eax
  _DWORD *v41; // rsi
  unsigned int v42; // eax
  unsigned int v44; // [rsp+40h] [rbp-30h] BYREF
  int v45; // [rsp+44h] [rbp-2Ch]
  DWORD cchValueName; // [rsp+48h] [rbp-28h] BYREF
  int v47; // [rsp+4Ch] [rbp-24h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR lpValueName; // [rsp+58h] [rbp-18h]
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  _DWORD *v51; // [rsp+68h] [rbp-8h]
  unsigned int v52; // [rsp+C0h] [rbp+50h] BYREF
  _DWORD *dwIndex; // [rsp+C8h] [rbp+58h]

  dwIndex = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1099, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, a1);
  }
  cchValueName = 0x3FFF;
  v47 = 0;
  hKey = 0;
  cbData = 0;
  DebugInit();
  if ( !a4 )
  {
    v9 = WPP_GLOBAL_Control;
    v10 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1100, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 87);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != (_DWORD *)&WPP_GLOBAL_Control && (v9[7] & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 6u )
      {
        v11 = 1101;
        goto LABEL_139;
      }
    }
    return v10;
  }
  if ( a3 && *a3 == 3672 )
  {
    v12 = &v47;
    lpValueName = 0;
    v13 = 0;
    if ( a5 )
      v12 = a5;
    if ( a2 )
    {
      v14 = IsPublicPhonebook(a2);
      v15 = DwEnumEntriesFromPhonebook(a2, a3, a4, v12, 3672, v14 != 0, 1);
      v10 = v15;
      if ( v15 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1103, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v15);
          v9 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
      }
      goto LABEL_127;
    }
    v16 = *a4;
    *a4 = 0;
    *v12 = 0;
    v44 = 0;
    v52 = v16;
    v10 = DwEnumEntriesForPbkMode(a1 | 1, (_DWORD)a3, (unsigned int)&v52, (unsigned int)&v44, 3672, 1);
    if ( v10 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1104, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v10);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v10 != 603 )
      {
LABEL_126:
        v13 = lpValueName;
        goto LABEL_127;
      }
    }
    v17 = v52;
    v18 = v44;
    v51 = a3;
    if ( v10 == 603 )
    {
      v45 = 1;
      v19 = 0;
    }
    else
    {
      v20 = 0;
      v45 = 0;
      a3 += 918 * v44;
      if ( v16 >= v52 )
        v20 = v52;
      v19 = v16 - v20;
    }
    v52 = v19;
    v44 = 0;
    *dwIndex += v17;
    *v12 = v18;
    v10 = DwEnumEntriesForPbkMode(a1, (_DWORD)a3, (unsigned int)&v52, (unsigned int)&v44, 3672, 1);
    if ( v10 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1105, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v10);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v10 != 603 )
        goto LABEL_96;
      v21 = v52;
      v22 = 0;
      v23 = v44;
      v45 = 1;
    }
    else
    {
      v23 = v44;
      v24 = 0;
      a3 += 918 * v44;
      v21 = v52;
      if ( v19 >= v52 )
        v24 = v52;
      v22 = v19 - v24;
    }
    v25 = dwIndex;
    v52 = v22;
    *dwIndex += v21;
    *v12 += v23;
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v27 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
    if ( !IsStateSeparationEnabled )
      v27 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
    v28 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v27, 0, 0x2001Fu, &hKey);
    LODWORD(dwIndex) = v28;
    if ( v28 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1106, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v28);
        v9 = WPP_GLOBAL_Control;
        v28 = (unsigned int)dwIndex;
      }
      if ( v28 != 5 )
      {
LABEL_98:
        v39 = 0;
        if ( v10 != 259 )
          v39 = v10;
        v10 = v39;
        if ( v45 )
        {
          RasTlsDll = 603;
          v10 = 603;
          if ( v9 == (_DWORD *)&WPP_GLOBAL_Control || (v9[7] & 0x800) == 0 || *((_BYTE *)v9 + 25) < 2u )
            goto LABEL_96;
          v37 = 1111;
          goto LABEL_105;
        }
        v41 = v51;
        if ( !v39 )
        {
          v42 = DwMarkDefaultInternetConnnection(v51, (unsigned int)*v12);
          if ( v42 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_113;
            }
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1112, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v42);
          }
          v9 = WPP_GLOBAL_Control;
        }
LABEL_113:
        if ( (unsigned int)*v12 <= 1 )
          goto LABEL_96;
        RasTlsDll = LoadRasTlsDll();
        if ( !RasTlsDll )
        {
          if ( !(unsigned __int8)((__int64 (__fastcall *)(_DWORD *, _QWORD))g_pRasEapSortRasEntries)(
                                   v41,
                                   (unsigned int)*v12) )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_96;
            }
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1113, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
          }
          goto LABEL_95;
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_96;
        }
        v37 = 1114;
LABEL_105:
        v38 = RasTlsDll;
LABEL_94:
        WPP_SF_d(*((_QWORD *)v9 + 2), v37, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v38);
LABEL_95:
        v9 = WPP_GLOBAL_Control;
LABEL_96:
        v13 = lpValueName;
        goto LABEL_127;
      }
      v29 = (unsigned __int8)RtlIsStateSeparationEnabled() == 0;
      v30 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
      if ( v29 )
        v30 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
      v31 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v30, 0, 0x20019u, &hKey);
      if ( v31 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1107, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v31);
          v9 = WPP_GLOBAL_Control;
        }
        goto LABEL_98;
      }
    }
    for ( LODWORD(dwIndex) = 0; ; LODWORD(dwIndex) = (_DWORD)dwIndex + 1 )
    {
      if ( lpValueName )
        Free0(lpValueName);
      v32 = (WCHAR *)GlobalAlloc(0x40u, 0x8000u);
      lpValueName = v32;
      if ( !v32 )
      {
        v10 = 8;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v37 = 1108;
          v38 = 8;
          goto LABEL_94;
        }
        v13 = 0;
LABEL_127:
        if ( hKey )
        {
          RegCloseKey(hKey);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v13 )
        {
          Free0(v13);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != (_DWORD *)&WPP_GLOBAL_Control && (v9[7] & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 6u )
        {
          v11 = 1115;
          goto LABEL_139;
        }
        return v10;
      }
      cchValueName = 0x3FFF;
      v10 = RegEnumValueW(hKey, (DWORD)dwIndex, v32, &cchValueName, 0, 0, 0, &cbData);
      if ( v10 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1109, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v10);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v10 != 234 )
        {
          if ( v10 != 259 )
            goto LABEL_96;
          goto LABEL_98;
        }
      }
      v10 = DwEnumEntriesFromPhonebook(lpValueName, a3, &v52, &v44, 3672, 0, 1);
      if ( v10 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1110, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v10);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v10 == 603 )
        {
          v34 = v52;
          v22 = 0;
          v33 = v44;
          v45 = 1;
          goto LABEL_86;
        }
        if ( v10 != 621 )
          goto LABEL_126;
      }
      v33 = v44;
      if ( !v44 || v10 == 621 )
      {
        v35 = RegDeleteValueW(hKey, lpValueName);
        v34 = 0;
        v10 = v35;
        v33 = 0;
        v44 = 0;
      }
      else
      {
        v34 = v52;
      }
      v36 = 0;
      a3 += 918 * v33;
      if ( v22 >= v34 )
        v36 = v34;
      v22 -= v36;
LABEL_86:
      *v25 += v34;
      *v12 += v33;
      v52 = v22;
      if ( v10 == 259 )
      {
        v9 = WPP_GLOBAL_Control;
        goto LABEL_98;
      }
    }
  }
  v9 = WPP_GLOBAL_Control;
  v10 = 632;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v11 = 1102;
LABEL_139:
    WPP_SF_d(*((_QWORD *)v9 + 2), v11, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x1800357e8  mov     [rsp-38h+arg_0], rbx
0x1800357ed  mov     [rsp-38h+dwIndex], r9
0x1800357f2  push    rbp
0x1800357f3  push    rsi
0x1800357f4  push    rdi
0x1800357f5  push    r12
0x1800357f7  push    r13
0x1800357f9  push    r14
0x1800357fb  push    r15
0x1800357fd  mov     rbp, rsp
0x180035800  sub     rsp, 70h
0x180035804  mov     rdi, r9
0x180035807  mov     r14, r8
0x18003580a  mov     rbx, rdx
0x18003580d  mov     r12d, ecx
0x180035810  mov     rcx, cs:WPP_GLOBAL_Control
0x180035817  lea     r15, WPP_GLOBAL_Control
0x18003581e  mov     esi, 800h
0x180035823  cmp     rcx, r15
0x180035826  jz      short loc_18003584B
0x180035828  test    [rcx+1Ch], esi
0x18003582b  jz      short loc_18003584B
0x18003582d  cmp     byte ptr [rcx+19h], 6
0x180035831  jb      short loc_18003584B
0x180035833  mov     rcx, [rcx+10h]
0x180035837  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x18003583e  mov     edx, 44Bh
0x180035843  mov     r9d, r12d
0x180035846  call    WPP_SF_d
0x18003584b  xor     r13d, r13d
0x18003584e  mov     [rbp+cchValueName], 3FFFh
0x180035855  mov     [rbp+var_24], r13d
0x180035859  mov     [rbp+hKey], r13
0x18003585d  mov     [rbp+cbData], r13d
0x180035861  call    DebugInit
0x180035866  test    rdi, rdi
0x180035869  jnz     short loc_1800358D1
0x18003586b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035872  lea     ebx, [rdi+57h]
0x180035875  cmp     rcx, r15
0x180035878  jz      loc_180036034
0x18003587e  test    [rcx+1Ch], esi
0x180035881  jz      short loc_1800358AB
0x180035883  mov     dil, 2
0x180035886  cmp     [rcx+19h], dil
0x18003588a  jb      short loc_1800358AB
0x18003588c  mov     rcx, [rcx+10h]
0x180035890  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180035897  mov     edx, 44Ch
0x18003589c  mov     r9d, ebx
0x18003589f  call    WPP_SF_d
0x1800358a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358ab  cmp     rcx, r15
0x1800358ae  jz      loc_180036034
0x1800358b4  test    [rcx+1Ch], esi
0x1800358b7  jz      loc_180036034
0x1800358bd  cmp     byte ptr [rcx+19h], 6
0x1800358c1  jb      loc_180036034
0x1800358c7  mov     edx, 44Dh
0x1800358cc  jmp     loc_180036021
0x1800358d1  test    r14, r14
0x1800358d4  jz      loc_180036000
0x1800358da  mov     edx, 0E58h
0x1800358df  cmp     [r14], edx
0x1800358e2  jnz     loc_180036000
0x1800358e8  mov     rax, [rbp+arg_20]
0x1800358ec  lea     r15, [rbp+var_24]
0x1800358f0  test    rax, rax
0x1800358f3  mov     [rbp+lpValueName], r13
0x1800358f7  mov     rsi, r13
0x1800358fa  cmovnz  r15, rax
0x1800358fe  test    rbx, rbx
0x180035901  jz      loc_1800359A3
0x180035907  mov     rcx, rbx
0x18003590a  call    IsPublicPhonebook
0x18003590f  mov     ecx, r13d
0x180035912  mov     dword ptr [rsp+70h+lpData], 1
0x18003591a  test    eax, eax
0x18003591c  mov     r9, r15
0x18003591f  mov     r8, rdi
0x180035922  mov     rdx, r14
0x180035925  setnz   cl
0x180035928  mov     dword ptr [rsp+70h+lpType], ecx
0x18003592c  mov     rcx, rbx
0x18003592f  mov     dword ptr [rsp+70h+phkResult], 0E58h
0x180035937  call    DwEnumEntriesFromPhonebook
0x18003593c  mov     ebx, eax
0x18003593e  test    eax, eax
0x180035940  jz      short loc_180035997
0x180035942  mov     rcx, cs:WPP_GLOBAL_Control
0x180035949  lea     r14, WPP_GLOBAL_Control
0x180035950  cmp     rcx, r14
0x180035953  jz      loc_180035FB8
0x180035959  test    dword ptr [rcx+1Ch], 800h
0x180035960  jz      loc_180035FB8
0x180035966  mov     dil, 2
0x180035969  cmp     [rcx+19h], dil
0x18003596d  jb      loc_180035FB8
0x180035973  mov     rcx, [rcx+10h]
0x180035977  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x18003597e  mov     edx, 44Fh
0x180035983  mov     r9d, eax
0x180035986  call    WPP_SF_d
0x18003598b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035992  jmp     loc_180035FB8
0x180035997  mov     rcx, cs:WPP_GLOBAL_Control
0x18003599e  jmp     loc_180035FB1
0x1800359a3  mov     esi, [rdi]
0x1800359a5  lea     r9, [rbp+var_30]
0x1800359a9  mov     [rdi], r13d
0x1800359ac  lea     r8, [rbp+arg_10]
0x1800359b0  mov     [r15], r13d
0x1800359b3  mov     ecx, r12d
0x1800359b6  mov     [rbp+var_30], r13d
0x1800359ba  mov     r13d, 1
0x1800359c0  mov     dword ptr [rsp+70h+lpType], r13d
0x1800359c5  or      ecx, r13d
0x1800359c8  mov     dword ptr [rsp+70h+phkResult], edx
0x1800359cc  mov     rdx, r14
0x1800359cf  mov     [rbp+arg_10], esi
0x1800359d2  call    DwEnumEntriesForPbkMode
0x1800359d7  mov     ebx, eax
0x1800359d9  mov     dil, 2
0x1800359dc  test    eax, eax
0x1800359de  jz      short loc_180035A2D
0x1800359e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800359e7  lea     rax, WPP_GLOBAL_Control
0x1800359ee  cmp     rcx, rax
0x1800359f1  jz      short loc_180035A21
0x1800359f3  test    dword ptr [rcx+1Ch], 800h
0x1800359fa  jz      short loc_180035A21
0x1800359fc  cmp     [rcx+19h], dil
0x180035a00  jb      short loc_180035A21
0x180035a02  mov     rcx, [rcx+10h]
0x180035a06  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180035a0d  mov     edx, 450h
0x180035a12  mov     r9d, ebx
0x180035a15  call    WPP_SF_d
0x180035a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a21  cmp     ebx, 25Bh
0x180035a27  jnz     loc_180035FAD
0x180035a2d  mov     edx, [rbp+arg_10]
0x180035a30  mov     r8d, [rbp+var_30]
0x180035a34  mov     [rbp+var_8], r14
0x180035a38  cmp     ebx, 25Bh
0x180035a3e  jnz     short loc_180035A48
0x180035a40  mov     [rbp+var_2C], r13d
0x180035a44  xor     esi, esi
0x180035a46  jmp     short loc_180035A62
0x180035a48  imul    rcx, r8, 0E58h
0x180035a4f  xor     eax, eax
0x180035a51  mov     [rbp+var_2C], 0
0x180035a58  add     r14, rcx
0x180035a5b  cmp     esi, edx
0x180035a5d  cmovnb  eax, edx
0x180035a60  sub     esi, eax
0x180035a62  mov     rax, [rbp+dwIndex]
0x180035a66  lea     r9, [rbp+var_30]
0x180035a6a  mov     dword ptr [rsp+70h+lpType], r13d
0x180035a6f  mov     ecx, r12d
0x180035a72  mov     [rbp+arg_10], esi
0x180035a75  mov     [rbp+var_30], 0
0x180035a7c  add     [rax], edx
0x180035a7e  mov     rdx, r14
0x180035a81  mov     [r15], r8d
0x180035a84  lea     r8, [rbp+arg_10]
0x180035a88  mov     dword ptr [rsp+70h+phkResult], 0E58h
0x180035a90  call    DwEnumEntriesForPbkMode
0x180035a95  mov     ebx, eax
0x180035a97  test    eax, eax
0x180035a99  jz      short loc_180035AF6
0x180035a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035aa2  lea     rax, WPP_GLOBAL_Control
0x180035aa9  cmp     rcx, rax
0x180035aac  jz      short loc_180035ADC
0x180035aae  test    dword ptr [rcx+1Ch], 800h
0x180035ab5  jz      short loc_180035ADC
0x180035ab7  cmp     [rcx+19h], dil
0x180035abb  jb      short loc_180035ADC
0x180035abd  mov     rcx, [rcx+10h]
0x180035ac1  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180035ac8  mov     edx, 451h
0x180035acd  mov     r9d, ebx
0x180035ad0  call    WPP_SF_d
0x180035ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180035adc  cmp     ebx, 25Bh
0x180035ae2  jnz     loc_180035FA1
0x180035ae8  mov     ecx, [rbp+arg_10]
0x180035aeb  xor     esi, esi
0x180035aed  mov     edx, [rbp+var_30]
0x180035af0  mov     [rbp+var_2C], r13d
0x180035af4  jmp     short loc_180035B0F
0x180035af6  mov     edx, [rbp+var_30]
0x180035af9  xor     eax, eax
0x180035afb  imul    rcx, rdx, 0E58h
0x180035b02  add     r14, rcx
0x180035b05  mov     ecx, [rbp+arg_10]
0x180035b08  cmp     esi, ecx
0x180035b0a  cmovnb  eax, ecx
0x180035b0d  sub     esi, eax
0x180035b0f  mov     r12, [rbp+dwIndex]
0x180035b13  mov     [rbp+arg_10], esi
0x180035b16  add     [r12], ecx
0x180035b1a  add     [r15], edx
0x180035b1d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180035b23  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180035b2a  mov     r9d, 2001Fh; samDesired
0x180035b30  test    al, al
0x180035b32  lea     rdx, aOsdataSystemCu; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180035b39  lea     rax, [rbp+hKey]
0x180035b3d  cmovz   rdx, rcx; lpSubKey
0x180035b41  mov     [rsp+70h+phkResult], rax; phkResult
0x180035b46  xor     r8d, r8d; ulOptions
0x180035b49  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035b50  call    cs:__imp_RegOpenKeyExW
0x180035b56  mov     dword ptr [rbp+dwIndex], eax
0x180035b59  test    eax, eax
0x180035b5b  jz      loc_180035C40
0x180035b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b68  lea     rdx, WPP_GLOBAL_Control
0x180035b6f  cmp     rcx, rdx
0x180035b72  jz      short loc_180035BA5
0x180035b74  test    dword ptr [rcx+1Ch], 800h
0x180035b7b  jz      short loc_180035BA5
0x180035b7d  cmp     [rcx+19h], dil
0x180035b81  jb      short loc_180035BA5
0x180035b83  mov     rcx, [rcx+10h]
0x180035b87  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180035b8e  mov     edx, 452h
0x180035b93  mov     r9d, eax
0x180035b96  call    WPP_SF_d
0x180035b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ba2  mov     eax, dword ptr [rbp+dwIndex]
0x180035ba5  cmp     eax, 5
0x180035ba8  jnz     loc_180035E6E
0x180035bae  call    cs:__imp_RtlIsStateSeparationEnabled
0x180035bb4  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180035bbb  mov     r9d, 20019h; samDesired
0x180035bc1  test    al, al
0x180035bc3  lea     rdx, [rbp+hKey]
0x180035bc7  mov     [rsp+70h+phkResult], rdx; phkResult
0x180035bcc  lea     rax, aOsdataSystemCu; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180035bd3  cmovz   rax, rcx
0x180035bd7  xor     r8d, r8d; ulOptions
0x180035bda  mov     rdx, rax; lpSubKey
0x180035bdd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035be4  call    cs:__imp_RegOpenKeyExW
0x180035bea  test    eax, eax
0x180035bec  jz      short loc_180035C40
0x180035bee  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bf5  lea     r14, WPP_GLOBAL_Control
0x180035bfc  cmp     rcx, r14
0x180035bff  jz      loc_180035E75
0x180035c05  test    dword ptr [rcx+1Ch], 800h
0x180035c0c  jz      loc_180035E75
0x180035c12  cmp     [rcx+19h], dil
0x180035c16  jb      loc_180035E75
0x180035c1c  mov     rcx, [rcx+10h]
0x180035c20  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180035c27  mov     edx, 453h
0x180035c2c  mov     r9d, eax
0x180035c2f  call    WPP_SF_d
0x180035c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c3b  jmp     loc_180035E75
0x180035c40  mov     dword ptr [rbp+dwIndex], 0
0x180035c47  cmp     ebx, 103h
0x180035c4d  jz      loc_180035E67
0x180035c53  mov     rax, [rbp+lpValueName]
0x180035c57  xor     ebx, ebx
0x180035c59  test    rax, rax
0x180035c5c  jz      short loc_180035C66
0x180035c5e  mov     rcx, rax
0x180035c61  call    Free0
0x180035c66  mov     edx, 8000h; dwBytes
0x180035c6b  mov     ecx, 40h ; '@'; uFlags
0x180035c70  call    cs:__imp_GlobalAlloc
0x180035c76  mov     [rbp+lpValueName], rax
0x180035c7a  test    rax, rax
0x180035c7d  jz      loc_180035E0C
0x180035c83  mov     edx, dword ptr [rbp+dwIndex]; dwIndex
0x180035c86  lea     rcx, [rbp+cbData]
0x180035c8a  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x180035c8f  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180035c93  mov     rcx, [rbp+hKey]; hKey
0x180035c97  mov     r8, rax; lpValueName
0x180035c9a  mov     [rsp+70h+lpData], rbx; lpData
0x180035c9f  mov     [rsp+70h+lpType], rbx; lpType
0x180035ca4  mov     [rsp+70h+phkResult], rbx; lpReserved
0x180035ca9  mov     [rbp+cchValueName], 3FFFh
0x180035cb0  call    cs:__imp_RegEnumValueW
0x180035cb6  mov     ebx, eax
0x180035cb8  test    eax, eax
0x180035cba  jz      short loc_180035D09
0x180035cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cc3  lea     rax, WPP_GLOBAL_Control
0x180035cca  cmp     rcx, rax
0x180035ccd  jz      short loc_180035CFD
0x180035ccf  test    dword ptr [rcx+1Ch], 800h
0x180035cd6  jz      short loc_180035CFD
0x180035cd8  cmp     [rcx+19h], dil
  ... truncated ...
```
