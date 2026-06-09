# EventDispatcher_InitializeConfigurableParameters(void)

- ea: `0x18004e080`
- end: `0x18004e2be`
- name: `?EventDispatcher_InitializeConfigurableParameters@@YAJXZ`
- size: `574`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004dfe0`

## callees

- `0x180039610`
- `0x180044554`
- `0x18004e080`
- `0x18004e314`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004e136`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004e136`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004e1f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004e1f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e254`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e254`

## string_xrefs

- `0x18004e0a1`: `Software\Microsoft\Windows\CurrentVersion\NetCache\Service\EventDispatcher`
- `0x18004e15f`: `DispatchThreadQuantumMs`

## pseudocode

```c
__int64 EventDispatcher_InitializeConfigurableParameters(void)
{
  LSTATUS v0; // eax
  int v1; // ebx
  const WCHAR *v2; // r14
  LSTATUS v3; // eax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v9; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpValueName[7]; // [rsp+58h] [rbp-A8h]
  WCHAR SubKey[80]; // [rsp+90h] [rbp-70h] BYREF

  wcscpy(SubKey, L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache\\Service\\EventDispather");
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
  if ( !v0 )
  {
    *(_DWORD *)Data = 0;
    v9 = &g_dwDispatchThreadQuantumMs;
    Type = 0;
    lpValueName[0] = L"DispatchThreadQuantumMs";
    v1 = 0;
    lpValueName[1] = (LPCWSTR)&g_dwDispatchMaxEventRetries;
    lpValueName[2] = L"DispatchMaxEventRetries";
    lpValueName[3] = (LPCWSTR)&g_dwDispatchQueuePacketLimitLower;
    lpValueName[4] = L"DispatchQueuePacketLimitLower";
    lpValueName[5] = (LPCWSTR)&g_dwDispatchQueuePacketLimitUpper;
    lpValueName[6] = L"DispatchQueuePacketLimitUpper";
    while ( 1 )
    {
      cbData = 4;
      v2 = lpValueName[2 * v1];
      v3 = RegQueryValueExW(hKey, v2, 0, &Type, Data, &cbData);
      if ( v3 )
        goto LABEL_7;
      if ( Type != 4 )
        break;
      *(_DWORD *)lpValueName[2 * v1 - 1] = *(_DWORD *)Data;
LABEL_10:
      if ( (unsigned int)++v1 >= 4 )
      {
        RegCloseKey(hKey);
        goto LABEL_15;
      }
    }
    v3 = 13;
LABEL_7:
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids,
        v3,
        (__int64)v2);
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids,
      v0,
      (__int64)SubKey);
LABEL_15:
  EventDispatcher_ReadSetting_NoEvents(&g_bEventDispatcherDisabled);
  return 0;
}

```

## disassembly

```asm
0x18004e080  push    rbp
0x18004e082  push    rbx
0x18004e083  push    rsi
0x18004e084  push    rdi
0x18004e085  push    r14
0x18004e087  lea     rbp, [rsp-40h]
0x18004e08c  sub     rsp, 140h
0x18004e093  mov     rax, cs:__security_cookie
0x18004e09a  xor     rax, rsp
0x18004e09d  mov     [rbp+60h+var_30], rax
0x18004e0a1  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004e0a8  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x18004e0ac  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Windows\\CurrentVersion\\N"...
0x18004e0b3  mov     r9d, 1; samDesired
0x18004e0b9  mov     rax, qword ptr cs:aSoftwareMicros+8Eh; "her"
0x18004e0c0  xor     r8d, r8d; ulOptions
0x18004e0c3  movups  xmmword ptr [rbp+60h+SubKey], xmm0
0x18004e0c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004e0ce  mov     [rsp+160h+hKey], 0
0x18004e0d7  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Windows\\CurrentVersion\\NetCache\\"...
0x18004e0de  movups  [rbp+60h+var_B0], xmm0
0x18004e0e2  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "ntVersion\\NetCache\\Service\\EventDisp"...
0x18004e0e9  movups  [rbp+60h+var_C0], xmm1
0x18004e0ed  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ws\\CurrentVersion\\NetCache\\Service\\"...
0x18004e0f4  movups  [rbp+60h+var_90], xmm0
0x18004e0f8  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+60h; "he\\Service\\EventDispatcher"
0x18004e0ff  movups  [rbp+60h+var_A0], xmm1
0x18004e103  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "n\\NetCache\\Service\\EventDispatcher"
0x18004e10a  movups  [rbp+60h+var_70], xmm0
0x18004e10e  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+80h; "Dispatcher"
0x18004e115  movups  [rbp+60h+var_50], xmm0
0x18004e119  mov     qword ptr [rbp+60h+var_50+0Eh], rax
0x18004e11d  lea     rax, [rsp+160h+hKey]
0x18004e122  movups  [rbp+60h+var_80], xmm1
0x18004e126  mov     [rsp+160h+phkResult], rax; phkResult
0x18004e12b  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+70h; "ce\\EventDispatcher"
0x18004e132  movups  [rbp+60h+var_60], xmm1
0x18004e136  call    cs:__imp_RegOpenKeyExW
0x18004e13c  test    eax, eax
0x18004e13e  jnz     loc_18004E25C
0x18004e144  lea     rax, ?g_dwDispatchThreadQuantumMs@@3KA; ulong g_dwDispatchThreadQuantumMs
0x18004e14b  mov     dword ptr [rsp+160h+Data], 0
0x18004e153  mov     [rsp+160h+var_110], rax
0x18004e158  lea     rdi, WPP_GLOBAL_Control
0x18004e15f  lea     rax, aDispatchthread; "DispatchThreadQuantumMs"
0x18004e166  mov     [rsp+160h+Type], 0
0x18004e16e  mov     [rsp+160h+lpValueName], rax
0x18004e173  xor     ebx, ebx
0x18004e175  lea     rax, ?g_dwDispatchMaxEventRetries@@3KA; ulong g_dwDispatchMaxEventRetries
0x18004e17c  mov     [rsp+160h+var_100], rax
0x18004e181  lea     rax, aDispatchmaxeve; "DispatchMaxEventRetries"
0x18004e188  mov     [rsp+160h+var_F8], rax
0x18004e18d  lea     rax, ?g_dwDispatchQueuePacketLimitLower@@3KA; ulong g_dwDispatchQueuePacketLimitLower
0x18004e194  mov     [rsp+160h+var_F0], rax
0x18004e199  lea     rax, aDispatchqueuep; "DispatchQueuePacketLimitLower"
0x18004e1a0  mov     [rsp+160h+var_E8], rax
0x18004e1a5  lea     rax, ?g_dwDispatchQueuePacketLimitUpper@@3KA; ulong g_dwDispatchQueuePacketLimitUpper
0x18004e1ac  mov     [rbp+60h+var_E0], rax
0x18004e1b0  lea     rax, aDispatchqueuep_0; "DispatchQueuePacketLimitUpper"
0x18004e1b7  mov     [rbp+60h+var_D8], rax
0x18004e1bb  mov     rcx, [rsp+160h+hKey]; hKey
0x18004e1c0  lea     rax, [rsp+160h+cbData]
0x18004e1c5  mov     [rsp+160h+lpcbData], rax; lpcbData
0x18004e1ca  lea     r9, [rsp+160h+Type]; lpType
0x18004e1cf  lea     rax, [rsp+160h+Data]
0x18004e1d4  movsxd  rsi, ebx
0x18004e1d7  add     rsi, rsi
0x18004e1da  mov     [rsp+160h+cbData], 4
0x18004e1e2  xor     r8d, r8d; lpReserved
0x18004e1e5  mov     [rsp+160h+phkResult], rax; lpData
0x18004e1ea  mov     r14, [rsp+rsi*8+160h+lpValueName]
0x18004e1ef  mov     rdx, r14; lpValueName
0x18004e1f2  call    cs:__imp_RegQueryValueExW
0x18004e1f8  test    eax, eax
0x18004e1fa  jnz     short loc_18004E215
0x18004e1fc  cmp     [rsp+160h+Type], 4
0x18004e201  jnz     short loc_18004E210
0x18004e203  mov     rcx, [rsp+rsi*8+160h+var_110]
0x18004e208  mov     eax, dword ptr [rsp+160h+Data]
0x18004e20c  mov     [rcx], eax
0x18004e20e  jmp     short loc_18004E244
0x18004e210  mov     eax, 0Dh
0x18004e215  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e21c  cmp     rcx, rdi
0x18004e21f  jz      short loc_18004E244
0x18004e221  test    byte ptr [rcx+1Ch], 2
0x18004e225  jz      short loc_18004E244
0x18004e227  mov     rcx, [rcx+10h]
0x18004e22b  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18004e232  mov     edx, 28h ; '('
0x18004e237  mov     [rsp+160h+phkResult], r14
0x18004e23c  mov     r9d, eax
0x18004e23f  call    WPP_SF_dS
0x18004e244  inc     ebx
0x18004e246  cmp     ebx, 4
0x18004e249  jb      loc_18004E1BB
0x18004e24f  mov     rcx, [rsp+160h+hKey]; hKey
0x18004e254  call    cs:__imp_RegCloseKey
0x18004e25a  jmp     short loc_18004E296
0x18004e25c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e263  lea     rdi, WPP_GLOBAL_Control
0x18004e26a  cmp     rcx, rdi
0x18004e26d  jz      short loc_18004E296
0x18004e26f  test    byte ptr [rcx+1Ch], 2
0x18004e273  jz      short loc_18004E296
0x18004e275  mov     rcx, [rcx+10h]
0x18004e279  lea     r8, [rbp+60h+SubKey]
0x18004e27d  mov     [rsp+160h+phkResult], r8
0x18004e282  mov     edx, 29h ; ')'
0x18004e287  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18004e28e  mov     r9d, eax
0x18004e291  call    WPP_SF_dS
0x18004e296  lea     rcx, ?g_bEventDispatcherDisabled@@3HA; int *
0x18004e29d  call    ?EventDispatcher_ReadSetting_NoEvents@@YAJPEAH@Z; EventDispatcher_ReadSetting_NoEvents(int *)
0x18004e2a2  xor     eax, eax
0x18004e2a4  mov     rcx, [rbp+60h+var_30]
0x18004e2a8  xor     rcx, rsp; StackCookie
0x18004e2ab  call    __security_check_cookie
0x18004e2b0  add     rsp, 140h
0x18004e2b7  pop     r14
0x18004e2b9  pop     rdi
0x18004e2ba  pop     rsi
0x18004e2bb  pop     rbx
0x18004e2bc  pop     rbp
0x18004e2bd  retn
```
