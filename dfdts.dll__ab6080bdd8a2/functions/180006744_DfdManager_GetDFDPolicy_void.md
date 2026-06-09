# DfdManager::GetDFDPolicy(void)

- ea: `0x180006744`
- end: `0x1800069ef`
- name: `?GetDFDPolicy@DfdManager@@AEAAKXZ`
- size: `683`
- prototype: `__int64 __fastcall(DfdManager *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006b10`

## callees

- `0x180002c68`
- `0x180002c90`
- `0x180006744`
- `0x1800069f8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000678c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000678c`
- `ADVAPI32!RegCloseKey` at `0x1800069cf`
- `ADVAPI32!RegCloseKey` at `0x1800069cf`
- `ADVAPI32!RegQueryValueExW` at `0x1800067f9`
- `ADVAPI32!RegQueryValueExW` at `0x1800068af`
- `ADVAPI32!RegQueryValueExW` at `0x1800067f9`
- `ADVAPI32!RegQueryValueExW` at `0x1800068af`

## pseudocode

```c
__int64 __fastcall DfdManager::GetDFDPolicy(DfdManager *this)
{
  unsigned int v1; // eax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // r9d
  char v5; // bl
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DfdManager *v8; // rcx
  unsigned int Data; // [rsp+50h] [rbp+20h] BYREF
  int v11; // [rsp+54h] [rbp+24h]
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v11 = HIDWORD(this);
  hKey = 0;
  Data = 5;
  cbData = 4;
  Type = 4;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\WDI\\{29689E29-2CE9-4751-B4FC-8EFF5066E3FD}",
         0,
         0x20019u,
         &hKey);
  if ( v1 )
  {
    Data = 5;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v3 = 36;
    goto LABEL_5;
  }
  v1 = RegQueryValueExW(hKey, L"ScenarioExecutionEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v1 )
  {
    Data = 6;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v3 = 37;
LABEL_5:
    WPP_SF_d(v2[2], v3, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, v1);
LABEL_35:
    v5 = 1;
    goto LABEL_36;
  }
  v4 = Data;
  v5 = 0;
  if ( !Data )
  {
    Data = 3;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v7 = v4 + 38;
LABEL_14:
      WPP_SF_(v6[2], v7, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  if ( Data != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, Data);
    goto LABEL_34;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"EnabledScenarioExecutionLevel", 0, &Type, (LPBYTE)&Data, &cbData) )
  {
    Data = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids);
    goto LABEL_35;
  }
  if ( Data != 1 )
  {
    if ( Data == 2 )
    {
      Data = 9;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v7 = 41;
        goto LABEL_14;
      }
      goto LABEL_36;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids);
LABEL_34:
    Data = 10;
    goto LABEL_35;
  }
  Data = 4;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v7 = 40;
    goto LABEL_14;
  }
LABEL_36:
  v8 = (DfdManager *)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    return DfdManager::GetFallbackPolicy(v8, Data);
  return Data;
}

```

## disassembly

```asm
0x180006744  mov     qword ptr [rsp-18h+Data], rcx
0x180006749  push    rbp
0x18000674a  push    rbx
0x18000674b  push    rdi
0x18000674c  mov     rbp, rsp
0x18000674f  sub     rsp, 30h
0x180006753  mov     ebx, 5
0x180006758  mov     [rbp+hKey], 0
0x180006760  lea     rax, [rbp+hKey]
0x180006764  mov     [rbp+Data], ebx
0x180006767  mov     r9d, 20019h; samDesired
0x18000676d  mov     [rsp+30h+phkResult], rax; phkResult
0x180006772  xor     r8d, r8d; ulOptions
0x180006775  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000677c  lea     edi, [rbx-1]
0x18000677f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006786  mov     [rbp+cbData], edi
0x180006789  mov     [rbp+Type], edi
0x18000678c  call    cs:__imp_RegOpenKeyExW
0x180006792  test    eax, eax
0x180006794  jz      short loc_1800067D5
0x180006796  mov     [rbp+Data], ebx
0x180006799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067a0  lea     rdx, WPP_GLOBAL_Control
0x1800067a7  cmp     rcx, rdx
0x1800067aa  jz      loc_1800069C4
0x1800067b0  test    byte ptr [rcx+1Ch], 1
0x1800067b4  jz      loc_1800069C4
0x1800067ba  lea     edx, [rbx+1Fh]
0x1800067bd  mov     rcx, [rcx+10h]
0x1800067c1  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x1800067c8  mov     r9d, eax
0x1800067cb  call    WPP_SF_d
0x1800067d0  jmp     loc_1800069C4
0x1800067d5  mov     rcx, [rbp+hKey]; hKey
0x1800067d9  lea     rax, [rbp+cbData]
0x1800067dd  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800067e2  lea     r9, [rbp+Type]; lpType
0x1800067e6  lea     rax, [rbp+Data]
0x1800067ea  xor     r8d, r8d; lpReserved
0x1800067ed  lea     rdx, aScenarioexecut; "ScenarioExecutionEnabled"
0x1800067f4  mov     [rsp+30h+phkResult], rax; lpData
0x1800067f9  call    cs:__imp_RegQueryValueExW
0x1800067ff  test    eax, eax
0x180006801  jz      short loc_180006832
0x180006803  mov     [rbp+Data], 6
0x18000680a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006811  lea     rdx, WPP_GLOBAL_Control
0x180006818  cmp     rcx, rdx
0x18000681b  jz      loc_1800069C4
0x180006821  test    byte ptr [rcx+1Ch], 1
0x180006825  jz      loc_1800069C4
0x18000682b  mov     edx, 25h ; '%'
0x180006830  jmp     short loc_1800067BD
0x180006832  mov     r9d, [rbp+Data]
0x180006836  xor     bl, bl
0x180006838  test    r9d, r9d
0x18000683b  jnz     short loc_18000687E
0x18000683d  mov     [rbp+Data], 3
0x180006844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000684b  lea     rdx, WPP_GLOBAL_Control
0x180006852  cmp     rcx, rdx
0x180006855  jz      loc_1800069C6
0x18000685b  test    [rcx+1Ch], dil
0x18000685f  jz      loc_1800069C6
0x180006865  lea     edx, [r9+26h]
0x180006869  mov     rcx, [rcx+10h]
0x18000686d  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006874  call    WPP_SF_
0x180006879  jmp     loc_1800069C6
0x18000687e  cmp     r9d, 1
0x180006882  jnz     loc_18000698F
0x180006888  mov     rcx, [rbp+hKey]; hKey
0x18000688c  lea     rax, [rbp+cbData]
0x180006890  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180006895  lea     r9, [rbp+Type]; lpType
0x180006899  lea     rax, [rbp+Data]
0x18000689d  mov     [rbp+cbData], edi
0x1800068a0  xor     r8d, r8d; lpReserved
0x1800068a3  mov     [rsp+30h+phkResult], rax; lpData
0x1800068a8  lea     rdx, aEnabledscenari; "EnabledScenarioExecutionLevel"
0x1800068af  call    cs:__imp_RegQueryValueExW
0x1800068b5  test    eax, eax
0x1800068b7  jz      short loc_1800068FB
0x1800068b9  mov     [rbp+Data], 8
0x1800068c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068c7  lea     rdx, WPP_GLOBAL_Control
0x1800068ce  cmp     rcx, rdx
0x1800068d1  jz      loc_1800069C4
0x1800068d7  test    [rcx+1Ch], dil
0x1800068db  jz      loc_1800069C4
0x1800068e1  mov     rcx, [rcx+10h]
0x1800068e5  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x1800068ec  mov     edx, 27h ; '''
0x1800068f1  call    WPP_SF_
0x1800068f6  jmp     loc_1800069C4
0x1800068fb  cmp     [rbp+Data], 1
0x1800068ff  jnz     short loc_18000692F
0x180006901  mov     [rbp+Data], edi
0x180006904  mov     rcx, cs:WPP_GLOBAL_Control
0x18000690b  lea     rdx, WPP_GLOBAL_Control
0x180006912  cmp     rcx, rdx
0x180006915  jz      loc_1800069C6
0x18000691b  test    [rcx+1Ch], dil
0x18000691f  jz      loc_1800069C6
0x180006925  mov     edx, 28h ; '('
0x18000692a  jmp     loc_180006869
0x18000692f  cmp     [rbp+Data], 2
0x180006933  jnz     short loc_18000695F
0x180006935  mov     [rbp+Data], 9
0x18000693c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006943  lea     rdx, WPP_GLOBAL_Control
0x18000694a  cmp     rcx, rdx
0x18000694d  jz      short loc_1800069C6
0x18000694f  test    [rcx+1Ch], dil
0x180006953  jz      short loc_1800069C6
0x180006955  mov     edx, 29h ; ')'
0x18000695a  jmp     loc_180006869
0x18000695f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006966  lea     rdx, WPP_GLOBAL_Control
0x18000696d  cmp     rcx, rdx
0x180006970  jz      short loc_1800069BD
0x180006972  test    [rcx+1Ch], dil
0x180006976  jz      short loc_1800069BD
0x180006978  mov     rcx, [rcx+10h]
0x18000697c  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006983  mov     edx, 2Ah ; '*'
0x180006988  call    WPP_SF_
0x18000698d  jmp     short loc_1800069BD
0x18000698f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006996  lea     rdx, WPP_GLOBAL_Control
0x18000699d  cmp     rcx, rdx
0x1800069a0  jz      short loc_1800069BD
0x1800069a2  test    byte ptr [rcx+1Ch], 1
0x1800069a6  jz      short loc_1800069BD
0x1800069a8  mov     rcx, [rcx+10h]
0x1800069ac  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x1800069b3  mov     edx, 2Bh ; '+'
0x1800069b8  call    WPP_SF_d
0x1800069bd  mov     [rbp+Data], 0Ah
0x1800069c4  mov     bl, 1
0x1800069c6  mov     rcx, [rbp+hKey]; hKey
0x1800069ca  test    rcx, rcx
0x1800069cd  jz      short loc_1800069D5
0x1800069cf  call    cs:__imp_RegCloseKey
0x1800069d5  test    bl, bl
0x1800069d7  jz      short loc_1800069E4
0x1800069d9  mov     edx, [rbp+Data]; unsigned int
0x1800069dc  call    ?GetFallbackPolicy@DfdManager@@AEAAKK@Z; DfdManager::GetFallbackPolicy(ulong)
0x1800069e1  mov     [rbp+Data], eax
0x1800069e4  mov     eax, [rbp+Data]
0x1800069e7  add     rsp, 30h
0x1800069eb  pop     rdi
0x1800069ec  pop     rbx
0x1800069ed  pop     rbp
0x1800069ee  retn
```
