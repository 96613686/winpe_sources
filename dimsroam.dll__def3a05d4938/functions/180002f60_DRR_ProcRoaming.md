# DRR_ProcRoaming

- ea: `0x180002f60`
- end: `0x1800032eb`
- name: `DRR_ProcRoaming`
- size: `907`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003300`

## callees

- `0x180002f60`
- `0x1800035cc`
- `0x1800035f4`
- `0x180005c00`
- `0x180006230`
- `0x1800071d0`
- `0x18000d8d0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ff6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ff6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002fbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002fbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003002`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003002`
- `ntdll!EtwEventWrite` at `0x18000324c`
- `ntdll!EtwEventWrite` at `0x18000324c`
- `ntdll!EtwEventEnabled` at `0x1800031a8`
- `ntdll!EtwEventEnabled` at `0x180003221`
- `ntdll!EtwEventEnabled` at `0x1800031a8`
- `ntdll!EtwEventEnabled` at `0x180003221`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003078`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003114`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003078`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003114`

## pseudocode

```c
__int64 DRR_ProcRoaming()
{
  LSTATUS v0; // ebx
  unsigned int v1; // ebx
  unsigned int v2; // eax
  __int64 v3; // r9
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 *v8; // rdx
  BYTE Data[8]; // [rsp+30h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-38h] BYREF
  LPVOID v12; // [rsp+40h] [rbp-30h] BYREF
  int v13; // [rsp+48h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-24h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  __int64 v16; // [rsp+58h] [rbp-18h] BYREF
  int v17; // [rsp+60h] [rbp-10h]

  hKey = 0;
  v16 = 0;
  v17 = 0;
  ppv = 0;
  v12 = 0;
  *(_DWORD *)Data = 0;
  v13 = 0;
  if ( RegOpenKeyExW(::hKey, L"Software\\Microsoft\\Cryptography\\DIMS\\KeyRoaming", 0, 1u, &hKey) )
  {
LABEL_8:
    v1 = 0;
    if ( CoCreateInstance(
           &GUID_ff8a71c2_7eb8_418b_950d_3b49f43f024f,
           0,
           1u,
           &GUID_435eb1b8_b681_4569_b862_551e13764315,
           &ppv) )
    {
      goto LABEL_40;
    }
    FilterPolicyUpdateCheck(StringSid, *(&xmmword_180013840 + 1), &v13, &v16);
    (*(void (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 96LL))(ppv, &v16);
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, 0);
    v3 = v2;
    if ( v2 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_40;
      v5 = 30;
      goto LABEL_39;
    }
    if ( CoCreateInstance(
           &GUID_f91b9abc_985b_4c04_b5e7_9c7099fc2cda,
           0,
           1u,
           &GUID_062c7f3f_5d6c_426b_95d9_69dddcf524ad,
           &v12) )
    {
      goto LABEL_40;
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(*(_QWORD *)v12 + 64LL))(v12, L"WinCredStore", 0);
    v3 = v6;
    if ( v6 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_40;
      v5 = 31;
LABEL_39:
      WPP_SF_D(v4[2], v5, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids, v3);
      goto LABEL_40;
    }
    if ( *(_DWORD *)Data )
    {
      v1 = DRR_ForceDownload(ppv, v12, 0, v6);
      if ( !v1 )
      {
        if ( !qword_1800138C8 )
          goto LABEL_40;
        if ( !(unsigned __int8)EtwEventEnabled(qword_1800138C8, DRR_LOG_SUCCESS_HEAL) )
          goto LABEL_40;
        if ( g_dwLoglevel <= v1 )
          goto LABEL_40;
        v7 = qword_1800138C8;
        if ( !qword_1800138C8 )
          goto LABEL_40;
        v8 = DRR_LOG_SUCCESS_HEAL;
LABEL_34:
        EtwEventWrite(v7, v8, 0, 0);
        goto LABEL_40;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_40;
      v5 = 33;
    }
    else
    {
      v1 = DRR_SyncLocAndNetStores((struct IUnknown *)ppv);
      if ( !v1 )
      {
        if ( !qword_1800138C8 )
          goto LABEL_40;
        if ( !(unsigned __int8)EtwEventEnabled(qword_1800138C8, DRR_LOG_SUCCESS) )
          goto LABEL_40;
        if ( g_dwLoglevel <= v1 )
          goto LABEL_40;
        v7 = qword_1800138C8;
        if ( !qword_1800138C8 )
          goto LABEL_40;
        v8 = DRR_LOG_SUCCESS;
        goto LABEL_34;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_40;
      v5 = 32;
    }
    v3 = v1;
    goto LABEL_39;
  }
  cbData = 4;
  v0 = RegQueryValueExW(hKey, L"Disabled", 0, 0, Data, &cbData);
  RegCloseKey(hKey);
  if ( v0 )
  {
    *(_DWORD *)Data = 0;
    goto LABEL_8;
  }
  if ( *(_DWORD *)Data != -1 )
    goto LABEL_8;
  v1 = 1058;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids);
LABEL_40:
  if ( v12 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 72LL))(v12);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 72LL))(ppv);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return v1;
}

```

## disassembly

```asm
0x180002f60  mov     [rsp-8+arg_0], rbx
0x180002f65  push    rbp
0x180002f66  mov     rbp, rsp
0x180002f69  sub     rsp, 70h
0x180002f6d  mov     rax, cs:__security_cookie
0x180002f74  xor     rax, rsp
0x180002f77  mov     [rbp+var_8], rax
0x180002f7b  mov     rcx, cs:hKey; hKey
0x180002f82  lea     rdx, DRR_REG_SUBKEY; "Software\\Microsoft\\Cryptography\\DIMS"...
0x180002f89  xor     eax, eax
0x180002f8b  mov     [rbp+hKey], 0
0x180002f93  mov     [rbp+var_18], rax
0x180002f97  mov     r9d, 1; samDesired
0x180002f9d  mov     [rbp+var_10], eax
0x180002fa0  xor     r8d, r8d; ulOptions
0x180002fa3  mov     [rbp+ppv], rax
0x180002fa7  mov     [rbp+var_30], rax
0x180002fab  mov     dword ptr [rbp+Data], eax
0x180002fae  lea     rax, [rbp+hKey]
0x180002fb2  mov     [rsp+70h+phkResult], rax; phkResult
0x180002fb7  mov     [rbp+var_28], 0
0x180002fbe  call    cs:__imp_RegOpenKeyExW
0x180002fc4  test    eax, eax
0x180002fc6  jnz     loc_180003059
0x180002fcc  mov     rcx, [rbp+hKey]; hKey
0x180002fd0  lea     rax, [rbp+cbData]
0x180002fd4  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180002fd9  lea     rdx, DRR_REG_VALUE_DISABLED; "Disabled"
0x180002fe0  lea     rax, [rbp+Data]
0x180002fe4  mov     [rbp+cbData], 4
0x180002feb  xor     r9d, r9d; lpType
0x180002fee  mov     [rsp+70h+phkResult], rax; lpData
0x180002ff3  xor     r8d, r8d; lpReserved
0x180002ff6  call    cs:__imp_RegQueryValueExW
0x180002ffc  mov     rcx, [rbp+hKey]; hKey
0x180003000  mov     ebx, eax
0x180003002  call    cs:__imp_RegCloseKey
0x180003008  test    ebx, ebx
0x18000300a  jnz     short loc_180003052
0x18000300c  cmp     dword ptr [rbp+Data], 0FFFFFFFFh
0x180003010  jnz     short loc_180003059
0x180003012  mov     ebx, 422h
0x180003017  mov     rcx, cs:WPP_GLOBAL_Control
0x18000301e  lea     rax, WPP_GLOBAL_Control
0x180003025  cmp     rcx, rax
0x180003028  jz      loc_180003285
0x18000302e  test    byte ptr [rcx+1Ch], 2
0x180003032  jz      loc_180003285
0x180003038  mov     rcx, [rcx+10h]
0x18000303c  lea     r8, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids
0x180003043  mov     edx, 1Dh
0x180003048  call    WPP_SF_
0x18000304d  jmp     loc_180003285
0x180003052  mov     dword ptr [rbp+Data], 0
0x180003059  lea     rax, [rbp+ppv]
0x18000305d  xor     ebx, ebx
0x18000305f  lea     r9, _GUID_435eb1b8_b681_4569_b862_551e13764315; riid
0x180003066  mov     [rsp+70h+phkResult], rax; ppv
0x18000306b  xor     edx, edx; pUnkOuter
0x18000306d  lea     rcx, _GUID_ff8a71c2_7eb8_418b_950d_3b49f43f024f; rclsid
0x180003074  lea     r8d, [rbx+1]; dwClsContext
0x180003078  call    cs:__imp_CoCreateInstance
0x18000307e  test    eax, eax
0x180003080  jnz     loc_180003285
0x180003086  mov     rdx, qword ptr cs:xmmword_180013840+8
0x18000308d  lea     r9, [rbp+var_18]
0x180003091  mov     rcx, cs:StringSid
0x180003098  lea     r8, [rbp+var_28]
0x18000309c  call    FilterPolicyUpdateCheck
0x1800030a1  mov     rcx, [rbp+ppv]
0x1800030a5  lea     rdx, [rbp+var_18]
0x1800030a9  mov     rax, [rcx]
0x1800030ac  mov     rax, [rax+60h]
0x1800030b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b5  mov     rcx, [rbp+ppv]
0x1800030b9  xor     edx, edx
0x1800030bb  mov     rax, [rcx]
0x1800030be  mov     rax, [rax+40h]
0x1800030c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c7  mov     r9d, eax
0x1800030ca  test    eax, eax
0x1800030cc  jz      short loc_1800030F7
0x1800030ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030d5  lea     rax, WPP_GLOBAL_Control
0x1800030dc  cmp     rcx, rax
0x1800030df  jz      loc_180003285
0x1800030e5  test    byte ptr [rcx+1Ch], 2
0x1800030e9  jz      loc_180003285
0x1800030ef  lea     edx, [rbx+1Eh]
0x1800030f2  jmp     loc_180003275
0x1800030f7  xor     edx, edx; pUnkOuter
0x1800030f9  lea     rax, [rbp+var_30]
0x1800030fd  lea     r9, _GUID_062c7f3f_5d6c_426b_95d9_69dddcf524ad; riid
0x180003104  mov     [rsp+70h+phkResult], rax; ppv
0x180003109  lea     rcx, _GUID_f91b9abc_985b_4c04_b5e7_9c7099fc2cda; rclsid
0x180003110  lea     r8d, [rdx+1]; dwClsContext
0x180003114  call    cs:__imp_CoCreateInstance
0x18000311a  test    eax, eax
0x18000311c  jnz     loc_180003285
0x180003122  mov     rcx, [rbp+var_30]
0x180003126  lea     rdx, aWincredstore; "WinCredStore"
0x18000312d  xor     r8d, r8d
0x180003130  mov     rax, [rcx]
0x180003133  mov     rax, [rax+40h]
0x180003137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313c  mov     r9d, eax
0x18000313f  test    eax, eax
0x180003141  jz      short loc_18000316E
0x180003143  mov     rcx, cs:WPP_GLOBAL_Control
0x18000314a  lea     rax, WPP_GLOBAL_Control
0x180003151  cmp     rcx, rax
0x180003154  jz      loc_180003285
0x18000315a  test    byte ptr [rcx+1Ch], 2
0x18000315e  jz      loc_180003285
0x180003164  mov     edx, 1Fh
0x180003169  jmp     loc_180003275
0x18000316e  mov     rdx, [rbp+var_30]
0x180003172  xor     r8d, r8d
0x180003175  mov     rcx, [rbp+ppv]; struct IUnknown *
0x180003179  cmp     dword ptr [rbp+Data], ebx
0x18000317c  jnz     loc_180003203
0x180003182  mov     r9d, [rbp+var_28]
0x180003186  call    DRR_SyncLocAndNetStores
0x18000318b  mov     ebx, eax
0x18000318d  test    eax, eax
0x18000318f  jnz     short loc_1800031DB
0x180003191  mov     rcx, cs:qword_1800138C8
0x180003198  test    rcx, rcx
0x18000319b  jz      loc_180003285
0x1800031a1  lea     rdx, DRR_LOG_SUCCESS
0x1800031a8  call    cs:__imp_EtwEventEnabled
0x1800031ae  test    al, al
0x1800031b0  jz      loc_180003285
0x1800031b6  cmp     cs:g_dwLoglevel, ebx
0x1800031bc  jbe     loc_180003285
0x1800031c2  mov     rcx, cs:qword_1800138C8
0x1800031c9  test    rcx, rcx
0x1800031cc  jz      loc_180003285
0x1800031d2  lea     rdx, DRR_LOG_SUCCESS
0x1800031d9  jmp     short loc_180003246
0x1800031db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031e2  lea     rax, WPP_GLOBAL_Control
0x1800031e9  cmp     rcx, rax
0x1800031ec  jz      loc_180003285
0x1800031f2  test    byte ptr [rcx+1Ch], 2
0x1800031f6  jz      loc_180003285
0x1800031fc  mov     edx, 20h ; ' '
0x180003201  jmp     short loc_180003272
0x180003203  call    DRR_ForceDownload
0x180003208  mov     ebx, eax
0x18000320a  test    eax, eax
0x18000320c  jnz     short loc_180003254
0x18000320e  mov     rcx, cs:qword_1800138C8
0x180003215  test    rcx, rcx
0x180003218  jz      short loc_180003285
0x18000321a  lea     rdx, DRR_LOG_SUCCESS_HEAL
0x180003221  call    cs:__imp_EtwEventEnabled
0x180003227  test    al, al
0x180003229  jz      short loc_180003285
0x18000322b  cmp     cs:g_dwLoglevel, ebx
0x180003231  jbe     short loc_180003285
0x180003233  mov     rcx, cs:qword_1800138C8
0x18000323a  test    rcx, rcx
0x18000323d  jz      short loc_180003285
0x18000323f  lea     rdx, DRR_LOG_SUCCESS_HEAL
0x180003246  xor     r9d, r9d
0x180003249  xor     r8d, r8d
0x18000324c  call    cs:__imp_EtwEventWrite
0x180003252  jmp     short loc_180003285
0x180003254  mov     rcx, cs:WPP_GLOBAL_Control
0x18000325b  lea     rax, WPP_GLOBAL_Control
0x180003262  cmp     rcx, rax
0x180003265  jz      short loc_180003285
0x180003267  test    byte ptr [rcx+1Ch], 2
0x18000326b  jz      short loc_180003285
0x18000326d  mov     edx, 21h ; '!'
0x180003272  mov     r9d, ebx
0x180003275  mov     rcx, [rcx+10h]
0x180003279  lea     r8, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids
0x180003280  call    WPP_SF_D
0x180003285  mov     rcx, [rbp+var_30]
0x180003289  test    rcx, rcx
0x18000328c  jz      short loc_1800032AA
0x18000328e  mov     rax, [rcx]
0x180003291  mov     rax, [rax+48h]
0x180003295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000329a  mov     rcx, [rbp+var_30]
0x18000329e  mov     rax, [rcx]
0x1800032a1  mov     rax, [rax+10h]
0x1800032a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032aa  mov     rcx, [rbp+ppv]
0x1800032ae  test    rcx, rcx
0x1800032b1  jz      short loc_1800032CF
0x1800032b3  mov     rax, [rcx]
0x1800032b6  mov     rax, [rax+48h]
0x1800032ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032bf  mov     rcx, [rbp+ppv]
0x1800032c3  mov     rax, [rcx]
0x1800032c6  mov     rax, [rax+10h]
0x1800032ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032cf  mov     eax, ebx
0x1800032d1  mov     rcx, [rbp+var_8]
0x1800032d5  xor     rcx, rsp; StackCookie
0x1800032d8  call    __security_check_cookie
0x1800032dd  mov     rbx, [rsp+70h+arg_0]
0x1800032e5  add     rsp, 70h
0x1800032e9  pop     rbp
0x1800032ea  retn
```
