# GetAutoTriggerProfileInfoInternal

- ea: `0x1800367c4`
- end: `0x180036cb2`
- name: `GetAutoTriggerProfileInfoInternal`
- size: `1262`
- prototype: `__int64 __usercall@<rax>(PVOID pvData@<rcx>, PVOID, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180036330`
- `0x18006a1d0`

## callees

- `0x1800367c4`
- `0x18004e580`
- `0x18004e984`
- `0x18004eab4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036885`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036885`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003696b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036a5c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036b70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036c1e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003696b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036a5c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036b70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036c1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036999`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036999`
- `rtutils!TracePrintfExA` at `0x1800368cb`
- `rtutils!TracePrintfExA` at `0x180036ac5`
- `rtutils!TracePrintfExA` at `0x180036b30`
- `rtutils!TracePrintfExA` at `0x180036bd1`
- `rtutils!TracePrintfExA` at `0x1800368cb`
- `rtutils!TracePrintfExA` at `0x180036ac5`
- `rtutils!TracePrintfExA` at `0x180036b30`
- `rtutils!TracePrintfExA` at `0x180036bd1`

## string_xrefs

- `0x180036857`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800368b8`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180036868`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180036a3a`: `AutoTriggerProfilePhonebookPath`
- `0x180036c76`: `GetAutoTriggerProfileInfoInternal: Could not read connection GUID 0x%.8x`
- `0x180036ab9`: `GetAutoTriggerProfileInfoInternal: Could not read phonebookpath 0x%.8x`
- `0x180036b1f`: `GetAutoTriggerProfileInfoInternal: Could not read EntryName 0x%.8x`
- `0x180036bc3`: `GetAutoTriggerProfileInfoInternal: Could not read EntryName 0x%.8x`
- `0x1800368ab`: `GetAutoTriggerProfileInfoInternal: Could not open regkey %S 0x%.8x`

## pseudocode

```c
__int64 __fastcall GetAutoTriggerProfileInfoInternal(_WORD *pvData, int a2, _WORD *a3, int a4, _OWORD *a5, _DWORD *a6)
{
  _QWORD *v10; // rcx
  _DWORD *v11; // rsi
  int v12; // eax
  const wchar_t *v13; // rdi
  const WCHAR *v14; // rdx
  unsigned int ValueW; // ebx
  __int64 v16; // rdx
  unsigned int v18; // eax
  unsigned int v19; // ebx
  unsigned int v20; // eax
  HKEY v21; // rcx
  unsigned int v22; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-38h]
  PVOID pvDataa; // [rsp+28h] [rbp-30h]
  int v25; // [rsp+40h] [rbp-18h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+48h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  hkey = 0;
  pcbData = 0;
  if ( pvData && a3 )
  {
    v11 = a6;
    if ( a6 )
      *a6 = 0;
    *pvData = 0;
    *a3 = 0;
    v12 = StateSepEnabled();
    v13 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    v14 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !v12 )
      v14 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0x20019u, &hkey);
    if ( ValueW )
    {
      if ( g_dwTraceId != -1 )
      {
        LODWORD(phkResult) = ValueW;
        if ( !(unsigned int)StateSepEnabled() )
          v13 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "GetAutoTriggerProfileInfoInternal: Could not open regkey %S 0x%.8x",
          v13,
          phkResult);
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v16 = 79;
      goto LABEL_20;
    }
    if ( v11 )
    {
      v25 = 0;
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"AutoTriggeringDisabled", 0x10u, 0, &v25, &pcbData);
      if ( !ValueW )
      {
        *v11 = v25 != 0;
        goto LABEL_24;
      }
      if ( ValueW != 2 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, ValueW);
          v10 = WPP_GLOBAL_Control;
        }
        if ( g_dwTraceId == -1 )
          goto LABEL_25;
        TracePrintfExA(g_dwTraceId, 0xCu, "GetAutoTriggerProfileInfoInternal: Could not read EntryName 0x%.8x", ValueW);
        goto LABEL_24;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 2);
      }
    }
    pcbData = 2 * a2;
    v18 = RegGetValueW(hkey, 0, L"AutoTriggerProfilePhonebookPath", 2u, 0, pvData, &pcbData);
    v19 = v18;
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v18);
      }
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "GetAutoTriggerProfileInfoInternal: Could not read phonebookpath 0x%.8x", v19);
    }
    pcbData = 2 * a4;
    v20 = RegGetValueW(hkey, 0, L"AutoTriggerProfileEntryName", 2u, 0, a3, &pcbData);
    ValueW = v20;
    if ( v20 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v20);
        v10 = WPP_GLOBAL_Control;
      }
      if ( g_dwTraceId == -1 )
        goto LABEL_58;
      TracePrintfExA(g_dwTraceId, 0xCu, "GetAutoTriggerProfileInfoInternal: Could not read EntryName 0x%.8x", ValueW);
    }
    v10 = WPP_GLOBAL_Control;
LABEL_58:
    if ( !a5 )
    {
LABEL_25:
      if ( hkey )
      {
        RegCloseKey(hkey);
        v10 = WPP_GLOBAL_Control;
        hkey = 0;
      }
      goto LABEL_27;
    }
    pcbData = 16;
    v21 = hkey;
    pvDataa = a5;
    *a5 = 0;
    v22 = RegGetValueW(v21, 0, L"AutoTriggerProfileGUID", 8u, 0, pvDataa, &pcbData);
    ValueW = v22;
    if ( v22 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v22);
        v10 = WPP_GLOBAL_Control;
      }
      if ( g_dwTraceId == -1 )
        goto LABEL_25;
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "GetAutoTriggerProfileInfoInternal: Could not read connection GUID 0x%.8x",
        ValueW);
    }
LABEL_24:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  ValueW = 87;
  if ( v10 == &WPP_GLOBAL_Control )
    return ValueW;
  if ( (*((_DWORD *)v10 + 7) & 0x1000) != 0 && *((_BYTE *)v10 + 25) >= 2u )
  {
    v16 = 78;
LABEL_20:
    WPP_SF_d(v10[2], v16, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, ValueW);
    v10 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
LABEL_27:
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x1000) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 85, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, ValueW);
  return ValueW;
}

```

## disassembly

```asm
0x1800367c4  push    rbp
0x1800367c6  push    rbx
0x1800367c7  push    rsi
0x1800367c8  push    rdi
0x1800367c9  push    r12
0x1800367cb  push    r13
0x1800367cd  push    r14
0x1800367cf  push    r15
0x1800367d1  mov     rbp, rsp
0x1800367d4  sub     rsp, 58h
0x1800367d8  mov     r13d, r9d
0x1800367db  mov     r15, r8
0x1800367de  mov     r12d, edx
0x1800367e1  mov     r14, rcx
0x1800367e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367eb  lea     rsi, WPP_GLOBAL_Control
0x1800367f2  cmp     rcx, rsi
0x1800367f5  jz      short loc_180036822
0x1800367f7  test    dword ptr [rcx+1Ch], 1000h
0x1800367fe  jz      short loc_180036822
0x180036800  cmp     byte ptr [rcx+19h], 6
0x180036804  jb      short loc_180036822
0x180036806  mov     rcx, [rcx+10h]
0x18003680a  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180036811  mov     edx, 4Dh ; 'M'
0x180036816  call    WPP_SF_
0x18003681b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036822  xor     ebx, ebx
0x180036824  mov     [rbp+hkey], rbx
0x180036828  mov     [rbp+arg_0], ebx
0x18003682b  test    r14, r14
0x18003682e  jz      loc_180036C82
0x180036834  test    r15, r15
0x180036837  jz      loc_180036C82
0x18003683d  mov     rsi, [rbp+arg_28]
0x180036841  test    rsi, rsi
0x180036844  jz      short loc_180036848
0x180036846  mov     [rsi], ebx
0x180036848  mov     [r14], bx
0x18003684c  mov     [r15], bx
0x180036850  call    StateSepEnabled
0x180036855  test    eax, eax
0x180036857  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18003685e  lea     rax, [rbp+hkey]
0x180036862  mov     r9d, 20019h; samDesired
0x180036868  lea     rdi, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x18003686f  mov     [rsp+58h+phkResult], rax; phkResult
0x180036874  mov     rdx, rdi
0x180036877  cmovz   rdx, rcx; lpSubKey
0x18003687b  xor     r8d, r8d; ulOptions
0x18003687e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036885  call    cs:__imp_RegOpenKeyExW
0x18003688b  mov     ebx, eax
0x18003688d  test    eax, eax
0x18003688f  jz      loc_180036923
0x180036895  or      esi, 0FFFFFFFFh
0x180036898  cmp     cs:g_dwTraceId, esi
0x18003689e  jz      short loc_1800368D1
0x1800368a0  call    StateSepEnabled
0x1800368a5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800368ab  lea     r8, aGetautotrigger_3; "GetAutoTriggerProfileInfoInternal: Coul"...
0x1800368b2  test    eax, eax
0x1800368b4  mov     dword ptr [rsp+58h+phkResult], ebx
0x1800368b8  lea     rax, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800368bf  mov     edx, 0Ch; dwFlags
0x1800368c4  cmovz   rdi, rax
0x1800368c8  mov     r9, rdi
0x1800368cb  call    cs:__imp_TracePrintfExA
0x1800368d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368d8  lea     rsi, WPP_GLOBAL_Control
0x1800368df  cmp     rcx, rsi
0x1800368e2  jz      loc_18003698D
0x1800368e8  test    dword ptr [rcx+1Ch], 1000h
0x1800368ef  jz      loc_18003698D
0x1800368f5  mov     edi, 2
0x1800368fa  cmp     [rcx+19h], dil
0x1800368fe  jb      loc_18003698D
0x180036904  lea     edx, [rdi+4Dh]
0x180036907  mov     rcx, [rcx+10h]
0x18003690b  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180036912  mov     r9d, ebx
0x180036915  call    WPP_SF_d
0x18003691a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036921  jmp     short loc_18003698D
0x180036923  mov     edi, 2
0x180036928  test    rsi, rsi
0x18003692b  jz      loc_180036A2F
0x180036931  mov     rcx, [rbp+hkey]; hkey
0x180036935  lea     rax, [rbp+arg_0]
0x180036939  mov     [rsp+58h+pcbData], rax; pcbData
0x18003693e  lea     r9d, [rdi+0Eh]; dwFlags
0x180036942  lea     rax, [rbp+var_18]
0x180036946  mov     [rbp+var_18], 0
0x18003694d  mov     [rsp+58h+pvData], rax; pvData
0x180036952  lea     r8, Value; "AutoTriggeringDisabled"
0x180036959  xor     edx, edx; lpSubKey
0x18003695b  mov     [rsp+58h+phkResult], 0; pdwType
0x180036964  mov     [rbp+arg_0], 4
0x18003696b  call    cs:__imp_RegGetValueW
0x180036971  mov     ebx, eax
0x180036973  test    eax, eax
0x180036975  jnz     short loc_1800369ED
0x180036977  cmp     [rbp+var_18], eax
0x18003697a  setnz   al
0x18003697d  mov     [rsi], eax
0x18003697f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036986  lea     rsi, WPP_GLOBAL_Control
0x18003698d  mov     rax, [rbp+hkey]
0x180036991  test    rax, rax
0x180036994  jz      short loc_1800369AE
0x180036996  mov     rcx, rax; hKey
0x180036999  call    cs:__imp_RegCloseKey
0x18003699f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369a6  mov     [rbp+hkey], 0
0x1800369ae  cmp     rcx, rsi
0x1800369b1  jz      short loc_1800369DA
0x1800369b3  test    dword ptr [rcx+1Ch], 1000h
0x1800369ba  jz      short loc_1800369DA
0x1800369bc  cmp     byte ptr [rcx+19h], 6
0x1800369c0  jb      short loc_1800369DA
0x1800369c2  mov     rcx, [rcx+10h]
0x1800369c6  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800369cd  mov     edx, 55h ; 'U'
0x1800369d2  mov     r9d, ebx
0x1800369d5  call    WPP_SF_d
0x1800369da  mov     eax, ebx
0x1800369dc  add     rsp, 58h
0x1800369e0  pop     r15
0x1800369e2  pop     r14
0x1800369e4  pop     r13
0x1800369e6  pop     r12
0x1800369e8  pop     rdi
0x1800369e9  pop     rsi
0x1800369ea  pop     rbx
0x1800369eb  pop     rbp
0x1800369ec  retn
0x1800369ed  cmp     ebx, edi
0x1800369ef  jnz     loc_180036ACD
0x1800369f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369fc  lea     rax, WPP_GLOBAL_Control
0x180036a03  cmp     rcx, rax
0x180036a06  jz      short loc_180036A2F
0x180036a08  test    dword ptr [rcx+1Ch], 1000h
0x180036a0f  jz      short loc_180036A2F
0x180036a11  cmp     [rcx+19h], dil
0x180036a15  jb      short loc_180036A2F
0x180036a17  mov     rcx, [rcx+10h]
0x180036a1b  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180036a22  mov     edx, 50h ; 'P'
0x180036a27  mov     r9d, edi
0x180036a2a  call    WPP_SF_d
0x180036a2f  mov     rcx, [rbp+hkey]; hkey
0x180036a33  lea     eax, [r12+r12]
0x180036a37  mov     [rbp+arg_0], eax
0x180036a3a  lea     r8, aAutotriggerpro_1; "AutoTriggerProfilePhonebookPath"
0x180036a41  lea     rax, [rbp+arg_0]
0x180036a45  mov     r9d, edi; dwFlags
0x180036a48  mov     [rsp+58h+pcbData], rax; pcbData
0x180036a4d  xor     edx, edx; lpSubKey
0x180036a4f  mov     [rsp+58h+pvData], r14; pvData
0x180036a54  xor     r14d, r14d
0x180036a57  mov     [rsp+58h+phkResult], r14; pdwType
0x180036a5c  call    cs:__imp_RegGetValueW
0x180036a62  or      esi, 0FFFFFFFFh
0x180036a65  mov     ebx, eax
0x180036a67  test    eax, eax
0x180036a69  jz      loc_180036B3B
0x180036a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a76  lea     r12, WPP_GLOBAL_Control
0x180036a7d  cmp     rcx, r12
0x180036a80  jz      short loc_180036AA8
0x180036a82  test    dword ptr [rcx+1Ch], 1000h
0x180036a89  jz      short loc_180036AA8
0x180036a8b  cmp     [rcx+19h], dil
0x180036a8f  jb      short loc_180036AA8
0x180036a91  mov     rcx, [rcx+10h]
0x180036a95  lea     edx, [r14+52h]
0x180036a99  mov     r9d, eax
0x180036a9c  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180036aa3  call    WPP_SF_d
0x180036aa8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180036aae  cmp     ecx, esi
0x180036ab0  jz      loc_180036B42
0x180036ab6  mov     r9d, ebx
0x180036ab9  lea     r8, aGetautotrigger_0; "GetAutoTriggerProfileInfoInternal: Coul"...
0x180036ac0  mov     edx, 0Ch; dwFlags
0x180036ac5  call    cs:__imp_TracePrintfExA
0x180036acb  jmp     short loc_180036B42
0x180036acd  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ad4  lea     rax, WPP_GLOBAL_Control
0x180036adb  cmp     rcx, rax
0x180036ade  jz      short loc_180036B0E
0x180036ae0  test    dword ptr [rcx+1Ch], 1000h
0x180036ae7  jz      short loc_180036B0E
0x180036ae9  cmp     [rcx+19h], dil
0x180036aed  jb      short loc_180036B0E
0x180036aef  mov     rcx, [rcx+10h]
0x180036af3  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180036afa  mov     edx, 51h ; 'Q'
0x180036aff  mov     r9d, ebx
0x180036b02  call    WPP_SF_d
0x180036b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b0e  mov     eax, cs:g_dwTraceId
0x180036b14  or      esi, 0FFFFFFFFh
0x180036b17  cmp     eax, esi
0x180036b19  jz      loc_180036986
0x180036b1f  lea     r8, aGetautotrigger_2; "GetAutoTriggerProfileInfoInternal: Coul"...
0x180036b26  mov     r9d, ebx
0x180036b29  mov     edx, 0Ch; dwFlags
0x180036b2e  mov     ecx, eax; dwTraceID
0x180036b30  call    cs:__imp_TracePrintfExA
0x180036b36  jmp     loc_18003697F
0x180036b3b  lea     r12, WPP_GLOBAL_Control
0x180036b42  mov     rcx, [rbp+hkey]; hkey
0x180036b46  lea     eax, ds:0[r13*2]
0x180036b4e  mov     [rbp+arg_0], eax
0x180036b51  lea     r8, aAutotriggerpro_2; "AutoTriggerProfileEntryName"
0x180036b58  lea     rax, [rbp+arg_0]
0x180036b5c  mov     r9d, edi; dwFlags
0x180036b5f  mov     [rsp+58h+pcbData], rax; pcbData
0x180036b64  xor     edx, edx; lpSubKey
0x180036b66  mov     [rsp+58h+pvData], r15; pvData
0x180036b6b  mov     [rsp+58h+phkResult], r14; pdwType
0x180036b70  call    cs:__imp_RegGetValueW
0x180036b76  mov     ebx, eax
0x180036b78  test    eax, eax
0x180036b7a  jz      short loc_180036BD7
0x180036b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b83  cmp     rcx, r12
0x180036b86  jz      short loc_180036BB6
0x180036b88  test    dword ptr [rcx+1Ch], 1000h
0x180036b8f  jz      short loc_180036BB6
0x180036b91  cmp     [rcx+19h], dil
0x180036b95  jb      short loc_180036BB6
0x180036b97  mov     rcx, [rcx+10h]
0x180036b9b  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180036ba2  mov     edx, 53h ; 'S'
0x180036ba7  mov     r9d, eax
0x180036baa  call    WPP_SF_d
0x180036baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bb6  mov     eax, cs:g_dwTraceId
0x180036bbc  cmp     eax, esi
0x180036bbe  jz      short loc_180036BDE
0x180036bc0  mov     r9d, ebx
0x180036bc3  lea     r8, aGetautotrigger_2; "GetAutoTriggerProfileInfoInternal: Coul"...
0x180036bca  mov     edx, 0Ch; dwFlags
0x180036bcf  mov     ecx, eax; dwTraceID
0x180036bd1  call    cs:__imp_TracePrintfExA
0x180036bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bde  mov     rax, [rbp+arg_20]
0x180036be2  test    rax, rax
0x180036be5  jz      loc_180036986
0x180036beb  lea     rcx, [rbp+arg_0]
0x180036bef  mov     [rbp+arg_0], 10h
0x180036bf6  mov     [rsp+58h+pcbData], rcx; pcbData
0x180036bfb  lea     r8, aAutotriggerpro_3; "AutoTriggerProfileGUID"
0x180036c02  mov     rcx, [rbp+hkey]; hkey
0x180036c06  xorps   xmm0, xmm0
0x180036c09  mov     [rsp+58h+pvData], rax; pvData
0x180036c0e  mov     r9d, 8; dwFlags
0x180036c14  xor     edx, edx; lpSubKey
0x180036c16  mov     [rsp+58h+phkResult], r14; pdwType
0x180036c1b  movups  xmmword ptr [rax], xmm0
0x180036c1e  call    cs:__imp_RegGetValueW
0x180036c24  mov     ebx, eax
0x180036c26  test    eax, eax
0x180036c28  jz      loc_18003697F
0x180036c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c35  cmp     rcx, r12
0x180036c38  jz      short loc_180036C68
0x180036c3a  test    dword ptr [rcx+1Ch], 1000h
0x180036c41  jz      short loc_180036C68
0x180036c43  cmp     [rcx+19h], dil
0x180036c47  jb      short loc_180036C68
0x180036c49  mov     rcx, [rcx+10h]
0x180036c4d  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180036c54  mov     edx, 54h ; 'T'
0x180036c59  mov     r9d, eax
0x180036c5c  call    WPP_SF_d
0x180036c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c68  mov     eax, cs:g_dwTraceId
0x180036c6e  cmp     eax, esi
0x180036c70  jz      loc_180036986
0x180036c76  lea     r8, aGetautotrigger_1; "GetAutoTriggerProfileInfoInternal: Coul"...
0x180036c7d  jmp     loc_180036B26
0x180036c82  mov     ebx, 57h ; 'W'
0x180036c87  cmp     rcx, rsi
0x180036c8a  jz      loc_1800369DA
0x180036c90  test    dword ptr [rcx+1Ch], 1000h
0x180036c97  jz      loc_1800369AE
0x180036c9d  lea     edi, [rbx-55h]
0x180036ca0  cmp     [rcx+19h], dil
0x180036ca4  jb      loc_1800369AE
0x180036caa  lea     edx, [rbx-9]
0x180036cad  jmp     loc_180036907
```
