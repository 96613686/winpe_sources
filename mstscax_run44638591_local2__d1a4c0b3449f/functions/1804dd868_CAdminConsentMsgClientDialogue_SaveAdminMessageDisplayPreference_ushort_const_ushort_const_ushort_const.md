# CAdminConsentMsgClientDialogue::SaveAdminMessageDisplayPreference(ushort const *,ushort const *,ushort const *)

- ea: `0x1804dd868`
- end: `0x1804ddc10`
- name: `?SaveAdminMessageDisplayPreference@CAdminConsentMsgClientDialogue@@SAJPEBG00@Z`
- size: `936`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR, BYTE *lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1804b9340`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x180085e50`
- `0x1800fb4ec`
- `0x1804dd868`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1804dd942`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dda28`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dda93`
- `ADVAPI32!RegOpenKeyExW` at `0x1804ddaf7`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd942`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dda28`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dda93`
- `ADVAPI32!RegOpenKeyExW` at `0x1804ddaf7`
- `ADVAPI32!RegCloseKey` at `0x1804ddbb5`
- `ADVAPI32!RegCloseKey` at `0x1804ddbc4`
- `ADVAPI32!RegCloseKey` at `0x1804ddbd3`
- `ADVAPI32!RegCloseKey` at `0x1804ddbe2`
- `ADVAPI32!RegCloseKey` at `0x1804ddbb5`
- `ADVAPI32!RegCloseKey` at `0x1804ddbc4`
- `ADVAPI32!RegCloseKey` at `0x1804ddbd3`
- `ADVAPI32!RegCloseKey` at `0x1804ddbe2`
- `ADVAPI32!RegCreateKeyExW` at `0x1804dd9cc`
- `ADVAPI32!RegCreateKeyExW` at `0x1804dda6d`
- `ADVAPI32!RegCreateKeyExW` at `0x1804ddad1`
- `ADVAPI32!RegCreateKeyExW` at `0x1804ddb35`
- `ADVAPI32!RegCreateKeyExW` at `0x1804dd9cc`
- `ADVAPI32!RegCreateKeyExW` at `0x1804dda6d`
- `ADVAPI32!RegCreateKeyExW` at `0x1804ddad1`
- `ADVAPI32!RegCreateKeyExW` at `0x1804ddb35`
- `ADVAPI32!RegSetValueExW` at `0x1804ddb69`
- `ADVAPI32!RegSetValueExW` at `0x1804ddba4`
- `ADVAPI32!RegSetValueExW` at `0x1804ddb69`
- `ADVAPI32!RegSetValueExW` at `0x1804ddba4`

## pseudocode

```c
__int64 __fastcall CAdminConsentMsgClientDialogue::SaveAdminMessageDisplayPreference(
        LPCWSTR lpSubKey,
        LPCWSTR a2,
        BYTE *lpData)
{
  LSTATUS v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  LSTATUS v9; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HKEY v11; // rcx
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // rax
  HKEY v17; // [rsp+50h] [rbp-20h] BYREF
  HKEY v18; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  int Data; // [rsp+A0h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+B8h] [rbp+48h] BYREF

  phkResult = 0;
  v17 = 0;
  v18 = 0;
  v6 = 0;
  hKey = 0;
  if ( !lpSubKey || !a2 )
    return (unsigned int)v6;
  if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
  {
    if ( (int)CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey) >= 0 )
    {
      v9 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\Terminal Server Gateway\\Messages", 0, 0x20019u, &phkResult);
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_8a63958bf7f03e22b31d297bf1b8c2bd_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        if ( v9 == 2
          && RegCreateKeyExW(
               hKey,
               L"Software\\Microsoft\\Terminal Server Gateway\\Messages",
               0,
               0,
               0,
               0x20006u,
               0,
               &phkResult,
               0)
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 15;
          goto LABEL_9;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 13;
LABEL_9:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_8a63958bf7f03e22b31d297bf1b8c2bd_Traceguids, v7);
    }
  }
  v11 = phkResult;
  if ( phkResult )
    goto LABEL_26;
  v12 = RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Terminal Server Gateway\\Messages",
          0,
          0x20006u,
          &phkResult);
  v6 = v12;
  if ( !v12
    || v12 == 2
    && (v6 = RegCreateKeyExW(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Terminal Server Gateway\\Messages",
               0,
               0,
               0,
               0x20006u,
               0,
               &phkResult,
               0)) == 0 )
  {
    v11 = phkResult;
LABEL_26:
    v13 = RegOpenKeyExW(v11, a2, 0, 0x20006u, &v17);
    v6 = v13;
    if ( !v13 || v13 == 2 && (v6 = RegCreateKeyExW(phkResult, a2, 0, 0, 0, 0x20006u, 0, &v17, 0)) == 0 )
    {
      v14 = RegOpenKeyExW(v17, lpSubKey, 0, 0x20006u, &v18);
      v6 = v14;
      if ( !v14 || v14 == 2 && (v6 = RegCreateKeyExW(v17, lpSubKey, 0, 0, 0, 0x20006u, 0, &v18, 0)) == 0 )
      {
        Data = 1;
        v6 = RegSetValueExW(v18, L"UserPreferenceOption", 0, 4u, (const BYTE *)&Data, 4u);
        if ( !v6 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)&lpData[2 * v15] );
          v6 = RegSetValueExW(v18, L"ConsentHash", 0, 1u, lpData, 2 * v15 + 2);
        }
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v17 )
    RegCloseKey(v17);
  if ( v18 )
    RegCloseKey(v18);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1804dd868  mov     [rsp-28h+arg_8], rbx
0x1804dd86d  mov     [rsp-28h+arg_10], rsi
0x1804dd872  push    rbp
0x1804dd873  push    rdi
0x1804dd874  push    r12
0x1804dd876  push    r14
0x1804dd878  push    r15
0x1804dd87a  mov     rbp, rsp
0x1804dd87d  sub     rsp, 70h
0x1804dd881  xor     r12d, r12d
0x1804dd884  mov     r15, r8
0x1804dd887  mov     [rbp+arg_18], r12
0x1804dd88b  mov     rsi, rdx
0x1804dd88e  mov     [rbp+var_20], r12
0x1804dd892  mov     r14, rcx
0x1804dd895  mov     [rbp+var_18], r12
0x1804dd899  mov     ebx, r12d
0x1804dd89c  mov     [rbp+hKey], r12
0x1804dd8a0  test    rcx, rcx
0x1804dd8a3  jz      loc_1804DDBF5
0x1804dd8a9  test    rdx, rdx
0x1804dd8ac  jz      loc_1804DDBF5
0x1804dd8b2  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1804dd8b7  mov     edi, 20006h
0x1804dd8bc  test    eax, eax
0x1804dd8be  jz      loc_1804DDA02
0x1804dd8c4  lea     rcx, [rbp+hKey]; HKEY *
0x1804dd8c8  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1804dd8cd  test    eax, eax
0x1804dd8cf  jns     short loc_1804DD925
0x1804dd8d1  mov     rax, cs:WPP_GLOBAL_Control
0x1804dd8d8  lea     rbx, WPP_GLOBAL_Control
0x1804dd8df  cmp     rax, rbx
0x1804dd8e2  jz      loc_1804DDA02
0x1804dd8e8  test    byte ptr [rax+1Ch], 1
0x1804dd8ec  jz      loc_1804DDA02
0x1804dd8f2  cmp     byte ptr [rax+19h], 2
0x1804dd8f6  jb      loc_1804DDA02
0x1804dd8fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804dd901  lea     edx, [r12+0Dh]
0x1804dd906  mov     rcx, cs:WPP_GLOBAL_Control
0x1804dd90d  lea     r8, WPP_8a63958bf7f03e22b31d297bf1b8c2bd_Traceguids
0x1804dd914  mov     r9d, eax
0x1804dd917  mov     rcx, [rcx+10h]
0x1804dd91b  call    WPP_SF_d
0x1804dd920  jmp     loc_1804DDA02
0x1804dd925  mov     rcx, [rbp+hKey]; hKey
0x1804dd929  lea     rax, [rbp+arg_18]
0x1804dd92d  mov     r9d, 20019h; samDesired
0x1804dd933  mov     [rsp+70h+phkResult], rax; phkResult
0x1804dd938  xor     r8d, r8d; ulOptions
0x1804dd93b  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Terminal Server Ga"...
0x1804dd942  call    cs:__imp_RegOpenKeyExW
0x1804dd948  mov     edi, eax
0x1804dd94a  test    eax, eax
0x1804dd94c  jz      loc_1804DD9FD
0x1804dd952  mov     rcx, cs:WPP_GLOBAL_Control
0x1804dd959  lea     rbx, WPP_GLOBAL_Control
0x1804dd960  cmp     rcx, rbx
0x1804dd963  jz      short loc_1804DD995
0x1804dd965  test    byte ptr [rcx+1Ch], 1
0x1804dd969  jz      short loc_1804DD995
0x1804dd96b  cmp     byte ptr [rcx+19h], 2
0x1804dd96f  jb      short loc_1804DD995
0x1804dd971  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804dd976  mov     rcx, cs:WPP_GLOBAL_Control
0x1804dd97d  lea     r8, WPP_8a63958bf7f03e22b31d297bf1b8c2bd_Traceguids
0x1804dd984  mov     edx, 0Eh
0x1804dd989  mov     r9d, eax
0x1804dd98c  mov     rcx, [rcx+10h]
0x1804dd990  call    WPP_SF_d
0x1804dd995  cmp     edi, 2
0x1804dd998  mov     edi, 20006h
0x1804dd99d  jnz     short loc_1804DDA02
0x1804dd99f  mov     rcx, [rbp+hKey]; hKey
0x1804dd9a3  lea     rax, [rbp+arg_18]
0x1804dd9a7  mov     [rsp+70h+lpdwDisposition], r12; lpdwDisposition
0x1804dd9ac  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Terminal Server Ga"...
0x1804dd9b3  mov     [rsp+70h+var_38], rax; phkResult
0x1804dd9b8  xor     r9d, r9d; lpClass
0x1804dd9bb  mov     [rsp+70h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1804dd9c0  xor     r8d, r8d; Reserved
0x1804dd9c3  mov     [rsp+70h+samDesired], edi; samDesired
0x1804dd9c7  mov     dword ptr [rsp+70h+phkResult], r12d; dwOptions
0x1804dd9cc  call    cs:__imp_RegCreateKeyExW
0x1804dd9d2  test    eax, eax
0x1804dd9d4  jz      short loc_1804DDA02
0x1804dd9d6  mov     rax, cs:WPP_GLOBAL_Control
0x1804dd9dd  cmp     rax, rbx
0x1804dd9e0  jz      short loc_1804DDA02
0x1804dd9e2  test    byte ptr [rax+1Ch], 1
0x1804dd9e6  jz      short loc_1804DDA02
0x1804dd9e8  cmp     byte ptr [rax+19h], 2
0x1804dd9ec  jb      short loc_1804DDA02
0x1804dd9ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804dd9f3  mov     edx, 0Fh
0x1804dd9f8  jmp     loc_1804DD906
0x1804dd9fd  mov     edi, 20006h
0x1804dda02  mov     rcx, [rbp+arg_18]
0x1804dda06  test    rcx, rcx
0x1804dda09  jnz     short loc_1804DDA81
0x1804dda0b  lea     rax, [rbp+arg_18]
0x1804dda0f  mov     r9d, edi; samDesired
0x1804dda12  xor     r8d, r8d; ulOptions
0x1804dda15  mov     [rsp+70h+phkResult], rax; phkResult
0x1804dda1a  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Terminal Server Ga"...
0x1804dda21  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1804dda28  call    cs:__imp_RegOpenKeyExW
0x1804dda2e  mov     ebx, eax
0x1804dda30  test    eax, eax
0x1804dda32  jz      short loc_1804DDA7D
0x1804dda34  cmp     eax, 2
0x1804dda37  jnz     loc_1804DDBAC
0x1804dda3d  mov     [rsp+70h+lpdwDisposition], r12; lpdwDisposition
0x1804dda42  lea     rax, [rbp+arg_18]
0x1804dda46  mov     [rsp+70h+var_38], rax; phkResult
0x1804dda4b  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Terminal Server Ga"...
0x1804dda52  mov     [rsp+70h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1804dda57  xor     r9d, r9d; lpClass
0x1804dda5a  mov     [rsp+70h+samDesired], edi; samDesired
0x1804dda5e  xor     r8d, r8d; Reserved
0x1804dda61  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1804dda68  mov     dword ptr [rsp+70h+phkResult], r12d; dwOptions
0x1804dda6d  call    cs:__imp_RegCreateKeyExW
0x1804dda73  mov     ebx, eax
0x1804dda75  test    eax, eax
0x1804dda77  jnz     loc_1804DDBAC
0x1804dda7d  mov     rcx, [rbp+arg_18]; hKey
0x1804dda81  lea     rax, [rbp+var_20]
0x1804dda85  mov     r9d, edi; samDesired
0x1804dda88  xor     r8d, r8d; ulOptions
0x1804dda8b  mov     [rsp+70h+phkResult], rax; phkResult
0x1804dda90  mov     rdx, rsi; lpSubKey
0x1804dda93  call    cs:__imp_RegOpenKeyExW
0x1804dda99  mov     ebx, eax
0x1804dda9b  test    eax, eax
0x1804dda9d  jz      short loc_1804DDAE1
0x1804dda9f  cmp     eax, 2
0x1804ddaa2  jnz     loc_1804DDBAC
0x1804ddaa8  mov     rcx, [rbp+arg_18]; hKey
0x1804ddaac  lea     rax, [rbp+var_20]
0x1804ddab0  mov     [rsp+70h+lpdwDisposition], r12; lpdwDisposition
0x1804ddab5  xor     r9d, r9d; lpClass
0x1804ddab8  mov     [rsp+70h+var_38], rax; phkResult
0x1804ddabd  xor     r8d, r8d; Reserved
0x1804ddac0  mov     [rsp+70h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1804ddac5  mov     rdx, rsi; lpSubKey
0x1804ddac8  mov     [rsp+70h+samDesired], edi; samDesired
0x1804ddacc  mov     dword ptr [rsp+70h+phkResult], r12d; dwOptions
0x1804ddad1  call    cs:__imp_RegCreateKeyExW
0x1804ddad7  mov     ebx, eax
0x1804ddad9  test    eax, eax
0x1804ddadb  jnz     loc_1804DDBAC
0x1804ddae1  mov     rcx, [rbp+var_20]; hKey
0x1804ddae5  lea     rax, [rbp+var_18]
0x1804ddae9  mov     r9d, edi; samDesired
0x1804ddaec  mov     [rsp+70h+phkResult], rax; phkResult
0x1804ddaf1  xor     r8d, r8d; ulOptions
0x1804ddaf4  mov     rdx, r14; lpSubKey
0x1804ddaf7  call    cs:__imp_RegOpenKeyExW
0x1804ddafd  mov     ebx, eax
0x1804ddaff  test    eax, eax
0x1804ddb01  jz      short loc_1804DDB41
0x1804ddb03  cmp     eax, 2
0x1804ddb06  jnz     loc_1804DDBAC
0x1804ddb0c  mov     rcx, [rbp+var_20]; hKey
0x1804ddb10  lea     rax, [rbp+var_18]
0x1804ddb14  mov     [rsp+70h+lpdwDisposition], r12; lpdwDisposition
0x1804ddb19  xor     r9d, r9d; lpClass
0x1804ddb1c  mov     [rsp+70h+var_38], rax; phkResult
0x1804ddb21  xor     r8d, r8d; Reserved
0x1804ddb24  mov     [rsp+70h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1804ddb29  mov     rdx, r14; lpSubKey
0x1804ddb2c  mov     [rsp+70h+samDesired], edi; samDesired
0x1804ddb30  mov     dword ptr [rsp+70h+phkResult], r12d; dwOptions
0x1804ddb35  call    cs:__imp_RegCreateKeyExW
0x1804ddb3b  mov     ebx, eax
0x1804ddb3d  test    eax, eax
0x1804ddb3f  jnz     short loc_1804DDBAC
0x1804ddb41  mov     rcx, [rbp+var_18]; hKey
0x1804ddb45  lea     rax, [rbp+Data]
0x1804ddb49  mov     edi, 1
0x1804ddb4e  lea     rdx, aUserpreference; "UserPreferenceOption"
0x1804ddb55  xor     r8d, r8d; Reserved
0x1804ddb58  mov     [rbp+Data], edi
0x1804ddb5b  lea     r9d, [rdi+3]; dwType
0x1804ddb5f  mov     [rsp+70h+samDesired], r9d; cbData
0x1804ddb64  mov     [rsp+70h+phkResult], rax; lpData
0x1804ddb69  call    cs:__imp_RegSetValueExW
0x1804ddb6f  mov     ebx, eax
0x1804ddb71  test    eax, eax
0x1804ddb73  jnz     short loc_1804DDBAC
0x1804ddb75  or      rax, 0FFFFFFFFFFFFFFFFh
0x1804ddb79  inc     rax
0x1804ddb7c  cmp     [r15+rax*2], r12w
0x1804ddb81  jnz     short loc_1804DDB79
0x1804ddb83  mov     rcx, [rbp+var_18]; hKey
0x1804ddb87  lea     eax, ds:2[rax*2]
0x1804ddb8e  mov     [rsp+70h+samDesired], eax; cbData
0x1804ddb92  lea     rdx, aConsenthash; "ConsentHash"
0x1804ddb99  mov     r9d, edi; dwType
0x1804ddb9c  mov     [rsp+70h+phkResult], r15; lpData
0x1804ddba1  xor     r8d, r8d; Reserved
0x1804ddba4  call    cs:__imp_RegSetValueExW
0x1804ddbaa  mov     ebx, eax
0x1804ddbac  mov     rcx, [rbp+arg_18]; hKey
0x1804ddbb0  test    rcx, rcx
0x1804ddbb3  jz      short loc_1804DDBBB
0x1804ddbb5  call    cs:__imp_RegCloseKey
0x1804ddbbb  mov     rcx, [rbp+var_20]; hKey
0x1804ddbbf  test    rcx, rcx
0x1804ddbc2  jz      short loc_1804DDBCA
0x1804ddbc4  call    cs:__imp_RegCloseKey
0x1804ddbca  mov     rcx, [rbp+var_18]; hKey
0x1804ddbce  test    rcx, rcx
0x1804ddbd1  jz      short loc_1804DDBD9
0x1804ddbd3  call    cs:__imp_RegCloseKey
0x1804ddbd9  mov     rcx, [rbp+hKey]; hKey
0x1804ddbdd  test    rcx, rcx
0x1804ddbe0  jz      short loc_1804DDBE8
0x1804ddbe2  call    cs:__imp_RegCloseKey
0x1804ddbe8  test    ebx, ebx
0x1804ddbea  jle     short loc_1804DDBF5
0x1804ddbec  movzx   ebx, bx
0x1804ddbef  or      ebx, 80070000h
0x1804ddbf5  lea     r11, [rsp+70h+var_s0]
0x1804ddbfa  mov     eax, ebx
0x1804ddbfc  mov     rbx, [r11+38h]
0x1804ddc00  mov     rsi, [r11+40h]
0x1804ddc04  mov     rsp, r11
0x1804ddc07  pop     r15
0x1804ddc09  pop     r14
0x1804ddc0b  pop     r12
0x1804ddc0d  pop     rdi
0x1804ddc0e  pop     rbp
0x1804ddc0f  retn
```
