# UpdateGlobals(int)

- ea: `0x18000b680`
- end: `0x18000bc5d`
- name: `?UpdateGlobals@@YAKH@Z`
- size: `1501`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `14`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a7a0`
- `0x18000b5cc`
- `0x18000b638`
- `0x180014c80`
- `0x180016370`
- `0x180019f40`
- `0x18001ab70`
- `0x180024f38`
- `0x18002a794`
- `0x18002d330`
- `0x180035dd4`
- `0x1800362c0`
- `0x180036778`
- `0x1800367f4`

## callees

- `0x18000b680`
- `0x18001c3a8`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b71d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b75f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b7a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b7f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b865`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b8af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b8fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b947`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b981`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b9cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ba07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ba4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b71d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b75f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b7a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b7f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b865`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b8af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b8fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b947`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b981`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b9cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ba07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ba4f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000ba8c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000ba8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b6b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b6b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc41`
- `ntdll!RtlEnterCriticalSection` at `0x18000b6ea`
- `ntdll!RtlEnterCriticalSection` at `0x18000b6ea`
- `ntdll!RtlLeaveCriticalSection` at `0x18000baa9`
- `ntdll!RtlLeaveCriticalSection` at `0x18000baa9`

## string_xrefs

- `0x18000b758`: `MasterKeyLegacyCompliance`

## pseudocode

```c
__int64 __fastcall UpdateGlobals(DWORD a1)
{
  unsigned int v1; // ebx
  BOOL v3; // eax
  BOOL v4; // eax
  int v5; // edx
  __int64 v6; // rcx
  BOOL v7; // eax
  BOOL v8; // eax
  bool v9; // zf
  __int64 v10; // rdx
  __int64 v11; // rcx
  const char *v12; // r9
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+20h] BYREF

  cbData = a1;
  if ( dword_18004CCB4 && hKey && hObject )
  {
    v1 = 0;
    if ( WaitForSingleObject(hObject, 0) )
      return v1;
    Data = 0;
    cbData = 4;
    Type = 0;
    RtlEnterCriticalSection(&stru_18004C978);
    if ( !RegQueryValueExW(hKey, L"MasterKeyIterationCount", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && Data > dword_18004CCA4 )
    {
      dword_18004CCA4 = Data;
    }
    cbData = 4;
    v3 = !RegQueryValueExW(hKey, L"MasterKeyLegacyCompliance", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data;
    dword_18004CC88 = v3;
    cbData = 4;
    v4 = !RegQueryValueExW(hKey, L"MasterKeyLegacyNt4Domain", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data;
    dword_18004CC9C = v4;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DistributeBackupKey", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    {
      v5 = (*((unsigned __int8 (**)(void))g_pDPAPILsasrvIfTable + 9))();
      dword_18004CCAC = v5;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      {
        v9 = v5 == 0;
        v10 = 14;
        goto LABEL_44;
      }
    }
    else
    {
      dword_18004CCAC = Data != 0;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      {
        v9 = Data == 0;
        v10 = 13;
LABEL_44:
        v11 = *(_QWORD *)(v6 + 16);
        v12 = "TRUE";
        if ( v9 )
          v12 = "FALSE";
        WPP_SF_s(v11, v10, WPP_c311ca3328b03ff90a5c1865b7fbbc75_Traceguids, v12);
      }
    }
    cbData = 4;
    v7 = !RegQueryValueExW(hKey, L"ProtectionPolicy", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1;
    dword_18004CCA0 = v7;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Recovery Version", 0, &Type, (LPBYTE)&Data, &cbData)
      || Type != 4
      || (dword_18004C54C = Data, Data - 2 > 1) )
    {
      dword_18004C54C = 3;
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Encr Alg", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      dword_18004C548 = -1;
    else
      dword_18004C548 = Data;
    cbData = 4;
    RegQueryValueExW(hKey, L"Encr Alg Key Size", 0, &Type, (LPBYTE)&Data, &cbData);
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"MAC Alg", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      dword_18004C550 = -1;
    else
      dword_18004C550 = Data;
    cbData = 4;
    RegQueryValueExW(hKey, L"MAC Alg Key Size", 0, &Type, (LPBYTE)&Data, &cbData);
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Disable DC Recovery", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      dword_18004CCB0 = 0;
    else
      dword_18004CCB0 = Data;
    cbData = 4;
    v8 = !RegQueryValueExW(hKey, L"EnableWeakCryptography", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1;
    dword_18004CC98 = v8;
    v1 = RegNotifyChangeKeyValue(hKey, 1, 5u, hObject, 1);
    if ( v1 )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    RtlLeaveCriticalSection(&stru_18004C978);
    return v1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b680  mov     [rsp-8+cbData], ecx
0x18000b684  push    rbp
0x18000b685  mov     rbp, rsp
0x18000b688  sub     rsp, 30h
0x18000b68c  cmp     cs:dword_18004CCB4, 0
0x18000b693  jz      short loc_18000B6D2
0x18000b695  cmp     cs:hKey, 0
0x18000b69d  jz      short loc_18000B6D2
0x18000b69f  mov     rcx, cs:hObject; hHandle
0x18000b6a6  test    rcx, rcx
0x18000b6a9  jz      short loc_18000B6D2
0x18000b6ab  mov     [rsp+30h+arg_18], rbx
0x18000b6b0  xor     edx, edx; dwMilliseconds
0x18000b6b2  xor     ebx, ebx
0x18000b6b4  call    cs:__imp_WaitForSingleObject
0x18000b6bb  nop     dword ptr [rax+rax+00h]
0x18000b6c0  test    eax, eax
0x18000b6c2  jz      short loc_18000B6D6
0x18000b6c4  mov     eax, ebx
0x18000b6c6  mov     rbx, [rsp+30h+arg_18]
0x18000b6cb  add     rsp, 30h
0x18000b6cf  pop     rbp
0x18000b6d0  retn
0x18000b6d2  xor     eax, eax
0x18000b6d4  jmp     short loc_18000B6CB
0x18000b6d6  lea     rcx, stru_18004C978; CriticalSection
0x18000b6dd  mov     [rbp+Data], ebx
0x18000b6e0  mov     [rbp+cbData], 4
0x18000b6e7  mov     [rbp+Type], ebx
0x18000b6ea  call    cs:__imp_RtlEnterCriticalSection
0x18000b6f1  nop     dword ptr [rax+rax+00h]
0x18000b6f6  mov     rcx, cs:hKey; hKey
0x18000b6fd  lea     rax, [rbp+cbData]
0x18000b701  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b706  lea     r9, [rbp+Type]; lpType
0x18000b70a  lea     rax, [rbp+Data]
0x18000b70e  xor     r8d, r8d; lpReserved
0x18000b711  lea     rdx, ValueName; "MasterKeyIterationCount"
0x18000b718  mov     [rsp+30h+lpData], rax; lpData
0x18000b71d  call    cs:__imp_RegQueryValueExW
0x18000b724  nop     dword ptr [rax+rax+00h]
0x18000b729  test    eax, eax
0x18000b72b  jz      loc_18000BABA
0x18000b731  mov     rcx, cs:hKey; hKey
0x18000b738  lea     rax, [rbp+cbData]
0x18000b73c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b741  lea     r9, [rbp+Type]; lpType
0x18000b745  lea     rax, [rbp+Data]
0x18000b749  mov     [rbp+cbData], 4
0x18000b750  xor     r8d, r8d; lpReserved
0x18000b753  mov     [rsp+30h+lpData], rax; lpData
0x18000b758  lea     rdx, aMasterkeylegac; "MasterKeyLegacyCompliance"
0x18000b75f  call    cs:__imp_RegQueryValueExW
0x18000b766  nop     dword ptr [rax+rax+00h]
0x18000b76b  test    eax, eax
0x18000b76d  jz      loc_18000BADE
0x18000b773  xor     eax, eax
0x18000b775  mov     rcx, cs:hKey; hKey
0x18000b77c  lea     r9, [rbp+Type]; lpType
0x18000b780  mov     cs:dword_18004CC88, eax
0x18000b786  lea     rdx, aMasterkeylegac_0; "MasterKeyLegacyNt4Domain"
0x18000b78d  lea     rax, [rbp+cbData]
0x18000b791  mov     [rbp+cbData], 4
0x18000b798  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b79d  xor     r8d, r8d; lpReserved
0x18000b7a0  lea     rax, [rbp+Data]
0x18000b7a4  mov     [rsp+30h+lpData], rax; lpData
0x18000b7a9  call    cs:__imp_RegQueryValueExW
0x18000b7b0  nop     dword ptr [rax+rax+00h]
0x18000b7b5  test    eax, eax
0x18000b7b7  jz      loc_18000BAFB
0x18000b7bd  xor     eax, eax
0x18000b7bf  mov     rcx, cs:hKey; hKey
0x18000b7c6  lea     r9, [rbp+Type]; lpType
0x18000b7ca  mov     cs:dword_18004CC9C, eax
0x18000b7d0  lea     rdx, aDistributeback; "DistributeBackupKey"
0x18000b7d7  lea     rax, [rbp+cbData]
0x18000b7db  mov     [rbp+cbData], 4
0x18000b7e2  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b7e7  xor     r8d, r8d; lpReserved
0x18000b7ea  lea     rax, [rbp+Data]
0x18000b7ee  mov     [rsp+30h+lpData], rax; lpData
0x18000b7f3  call    cs:__imp_RegQueryValueExW
0x18000b7fa  nop     dword ptr [rax+rax+00h]
0x18000b7ff  test    eax, eax
0x18000b801  jz      loc_18000BB18
0x18000b807  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x18000b80e  mov     rax, [rax+48h]
0x18000b812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b817  movzx   edx, al
0x18000b81a  mov     cs:dword_18004CCAC, edx
0x18000b820  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b827  lea     rax, WPP_GLOBAL_Control
0x18000b82e  cmp     rcx, rax
0x18000b831  jnz     loc_18000BB5A
0x18000b837  mov     rcx, cs:hKey; hKey
0x18000b83e  lea     rax, [rbp+cbData]
0x18000b842  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b847  lea     r9, [rbp+Type]; lpType
0x18000b84b  lea     rax, [rbp+Data]
0x18000b84f  mov     [rbp+cbData], 4
0x18000b856  xor     r8d, r8d; lpReserved
0x18000b859  mov     [rsp+30h+lpData], rax; lpData
0x18000b85e  lea     rdx, aProtectionpoli; "ProtectionPolicy"
0x18000b865  call    cs:__imp_RegQueryValueExW
0x18000b86c  nop     dword ptr [rax+rax+00h]
0x18000b871  test    eax, eax
0x18000b873  jz      loc_18000BB92
0x18000b879  xor     eax, eax
0x18000b87b  mov     rcx, cs:hKey; hKey
0x18000b882  lea     r9, [rbp+Type]; lpType
0x18000b886  mov     cs:dword_18004CCA0, eax
0x18000b88c  lea     rdx, aRecoveryVersio; "Recovery Version"
0x18000b893  lea     rax, [rbp+cbData]
0x18000b897  mov     [rbp+cbData], 4
0x18000b89e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b8a3  xor     r8d, r8d; lpReserved
0x18000b8a6  lea     rax, [rbp+Data]
0x18000b8aa  mov     [rsp+30h+lpData], rax; lpData
0x18000b8af  call    cs:__imp_RegQueryValueExW
0x18000b8b6  nop     dword ptr [rax+rax+00h]
0x18000b8bb  test    eax, eax
0x18000b8bd  jz      loc_18000BBB0
0x18000b8c3  mov     cs:dword_18004C54C, 3
0x18000b8cd  mov     rcx, cs:hKey; hKey
0x18000b8d4  lea     rax, [rbp+cbData]
0x18000b8d8  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b8dd  lea     r9, [rbp+Type]; lpType
0x18000b8e1  lea     rax, [rbp+Data]
0x18000b8e5  mov     [rbp+cbData], 4
0x18000b8ec  xor     r8d, r8d; lpReserved
0x18000b8ef  mov     [rsp+30h+lpData], rax; lpData
0x18000b8f4  lea     rdx, aEncrAlg; "Encr Alg"
0x18000b8fb  call    cs:__imp_RegQueryValueExW
0x18000b902  nop     dword ptr [rax+rax+00h]
0x18000b907  test    eax, eax
0x18000b909  jz      loc_18000BBD4
0x18000b90f  mov     cs:dword_18004C548, 0FFFFFFFFh
0x18000b919  mov     rcx, cs:hKey; hKey
0x18000b920  lea     rax, [rbp+cbData]
0x18000b924  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b929  lea     r9, [rbp+Type]; lpType
0x18000b92d  lea     rax, [rbp+Data]
0x18000b931  mov     [rbp+cbData], 4
0x18000b938  xor     r8d, r8d; lpReserved
0x18000b93b  mov     [rsp+30h+lpData], rax; lpData
0x18000b940  lea     rdx, aEncrAlgKeySize; "Encr Alg Key Size"
0x18000b947  call    cs:__imp_RegQueryValueExW
0x18000b94e  nop     dword ptr [rax+rax+00h]
0x18000b953  mov     rcx, cs:hKey; hKey
0x18000b95a  lea     rax, [rbp+cbData]
0x18000b95e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b963  lea     r9, [rbp+Type]; lpType
0x18000b967  lea     rax, [rbp+Data]
0x18000b96b  mov     [rbp+cbData], 4
0x18000b972  xor     r8d, r8d; lpReserved
0x18000b975  mov     [rsp+30h+lpData], rax; lpData
0x18000b97a  lea     rdx, aMacAlg; "MAC Alg"
0x18000b981  call    cs:__imp_RegQueryValueExW
0x18000b988  nop     dword ptr [rax+rax+00h]
0x18000b98d  test    eax, eax
0x18000b98f  jz      loc_18000BBEC
0x18000b995  mov     cs:dword_18004C550, 0FFFFFFFFh
0x18000b99f  mov     rcx, cs:hKey; hKey
0x18000b9a6  lea     rax, [rbp+cbData]
0x18000b9aa  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b9af  lea     r9, [rbp+Type]; lpType
0x18000b9b3  lea     rax, [rbp+Data]
0x18000b9b7  mov     [rbp+cbData], 4
0x18000b9be  xor     r8d, r8d; lpReserved
0x18000b9c1  mov     [rsp+30h+lpData], rax; lpData
0x18000b9c6  lea     rdx, aMacAlgKeySize; "MAC Alg Key Size"
0x18000b9cd  call    cs:__imp_RegQueryValueExW
0x18000b9d4  nop     dword ptr [rax+rax+00h]
0x18000b9d9  mov     rcx, cs:hKey; hKey
0x18000b9e0  lea     rax, [rbp+cbData]
0x18000b9e4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000b9e9  lea     r9, [rbp+Type]; lpType
0x18000b9ed  lea     rax, [rbp+Data]
0x18000b9f1  mov     [rbp+cbData], 4
0x18000b9f8  xor     r8d, r8d; lpReserved
0x18000b9fb  mov     [rsp+30h+lpData], rax; lpData
0x18000ba00  lea     rdx, aDisableDcRecov; "Disable DC Recovery"
0x18000ba07  call    cs:__imp_RegQueryValueExW
0x18000ba0e  nop     dword ptr [rax+rax+00h]
0x18000ba13  test    eax, eax
0x18000ba15  jz      loc_18000BC04
0x18000ba1b  mov     cs:dword_18004CCB0, ebx
0x18000ba21  mov     rcx, cs:hKey; hKey
0x18000ba28  lea     rax, [rbp+cbData]
0x18000ba2c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000ba31  lea     r9, [rbp+Type]; lpType
0x18000ba35  lea     rax, [rbp+Data]
0x18000ba39  mov     [rbp+cbData], 4
0x18000ba40  xor     r8d, r8d; lpReserved
0x18000ba43  mov     [rsp+30h+lpData], rax; lpData
0x18000ba48  lea     rdx, aEnableweakcryp; "EnableWeakCryptography"
0x18000ba4f  call    cs:__imp_RegQueryValueExW
0x18000ba56  nop     dword ptr [rax+rax+00h]
0x18000ba5b  test    eax, eax
0x18000ba5d  jz      loc_18000BC1C
0x18000ba63  xor     eax, eax
0x18000ba65  mov     r9, cs:hObject; hEvent
0x18000ba6c  mov     edx, 1; bWatchSubtree
0x18000ba71  mov     rcx, cs:hKey; hKey
0x18000ba78  mov     r8d, 5; dwNotifyFilter
0x18000ba7e  mov     cs:dword_18004CC98, eax
0x18000ba84  mov     dword ptr [rsp+30h+lpData], 1; fAsynchronous
0x18000ba8c  call    cs:__imp_RegNotifyChangeKeyValue
0x18000ba93  nop     dword ptr [rax+rax+00h]
0x18000ba98  mov     ebx, eax
0x18000ba9a  test    eax, eax
0x18000ba9c  jnz     loc_18000BC3A
0x18000baa2  lea     rcx, stru_18004C978; CriticalSection
0x18000baa9  call    cs:__imp_RtlLeaveCriticalSection
0x18000bab0  nop     dword ptr [rax+rax+00h]
0x18000bab5  jmp     loc_18000B6C4
0x18000baba  cmp     [rbp+Type], 4
0x18000babe  jnz     loc_18000B731
0x18000bac4  mov     eax, [rbp+Data]
0x18000bac7  cmp     eax, cs:dword_18004CCA4
0x18000bacd  jbe     loc_18000B731
0x18000bad3  mov     cs:dword_18004CCA4, eax
0x18000bad9  jmp     loc_18000B731
0x18000bade  cmp     [rbp+Type], 4
0x18000bae2  jnz     loc_18000B773
0x18000bae8  cmp     [rbp+Data], ebx
0x18000baeb  jz      loc_18000B773
0x18000baf1  mov     eax, 1
0x18000baf6  jmp     loc_18000B775
0x18000bafb  cmp     [rbp+Type], 4
0x18000baff  jnz     loc_18000B7BD
0x18000bb05  cmp     [rbp+Data], ebx
0x18000bb08  jz      loc_18000B7BD
0x18000bb0e  mov     eax, 1
0x18000bb13  jmp     loc_18000B7BF
0x18000bb18  cmp     [rbp+Type], 4
0x18000bb1c  jnz     loc_18000B807
0x18000bb22  xor     edx, edx
0x18000bb24  cmp     [rbp+Data], edx
0x18000bb27  setnz   dl
0x18000bb2a  mov     cs:dword_18004CCAC, edx
0x18000bb30  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb37  lea     rax, WPP_GLOBAL_Control
0x18000bb3e  cmp     rcx, rax
0x18000bb41  jz      loc_18000B837
0x18000bb47  test    byte ptr [rcx+1Ch], 8
0x18000bb4b  jz      loc_18000B837
0x18000bb51  test    edx, edx
0x18000bb53  mov     edx, 0Dh
0x18000bb58  jmp     short loc_18000BB6B
0x18000bb5a  test    byte ptr [rcx+1Ch], 8
0x18000bb5e  jz      loc_18000B837
0x18000bb64  test    edx, edx
0x18000bb66  mov     edx, 0Eh
0x18000bb6b  mov     rcx, [rcx+10h]
0x18000bb6f  lea     rax, aFalse; "FALSE"
0x18000bb76  lea     r9, aTrue; "TRUE"
0x18000bb7d  cmovz   r9, rax
0x18000bb81  lea     r8, WPP_c311ca3328b03ff90a5c1865b7fbbc75_Traceguids
0x18000bb88  call    WPP_SF_s
0x18000bb8d  jmp     loc_18000B837
0x18000bb92  cmp     [rbp+Type], 4
0x18000bb96  jnz     loc_18000B879
0x18000bb9c  cmp     [rbp+Data], 1
0x18000bba0  jnz     loc_18000B879
0x18000bba6  mov     eax, 1
0x18000bbab  jmp     loc_18000B87B
0x18000bbb0  cmp     [rbp+Type], 4
0x18000bbb4  jnz     loc_18000B8C3
0x18000bbba  mov     ecx, [rbp+Data]
0x18000bbbd  mov     cs:dword_18004C54C, ecx
0x18000bbc3  lea     eax, [rcx-2]
0x18000bbc6  cmp     eax, 1
0x18000bbc9  jbe     loc_18000B8CD
0x18000bbcf  jmp     loc_18000B8C3
0x18000bbd4  cmp     [rbp+Type], 4
0x18000bbd8  jnz     loc_18000B90F
0x18000bbde  mov     eax, [rbp+Data]
0x18000bbe1  mov     cs:dword_18004C548, eax
0x18000bbe7  jmp     loc_18000B919
0x18000bbec  cmp     [rbp+Type], 4
0x18000bbf0  jnz     loc_18000B995
0x18000bbf6  mov     eax, [rbp+Data]
0x18000bbf9  mov     cs:dword_18004C550, eax
0x18000bbff  jmp     loc_18000B99F
0x18000bc04  cmp     [rbp+Type], 4
0x18000bc08  jnz     loc_18000BA1B
0x18000bc0e  mov     eax, [rbp+Data]
0x18000bc11  mov     cs:dword_18004CCB0, eax
0x18000bc17  jmp     loc_18000BA21
0x18000bc1c  cmp     [rbp+Type], 4
0x18000bc20  jnz     loc_18000BA63
0x18000bc26  cmp     [rbp+Data], 1
0x18000bc2a  jnz     loc_18000BA63
0x18000bc30  mov     eax, 1
0x18000bc35  jmp     loc_18000BA65
0x18000bc3a  mov     rcx, cs:hObject; hObject
0x18000bc41  call    cs:__imp_CloseHandle
0x18000bc48  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
