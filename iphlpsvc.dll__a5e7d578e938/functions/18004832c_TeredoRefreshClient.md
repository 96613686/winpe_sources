# TeredoRefreshClient

- ea: `0x18004832c`
- end: `0x180048522`
- name: `TeredoRefreshClient`
- size: `502`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180069480`

## callees

- `0x180004de0`
- `0x18000d7c0`
- `0x1800190f0`
- `0x18002dcc0`
- `0x18002e160`
- `0x180033978`
- `0x18004832c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800483bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800483bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048470`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800483e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180048429`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800483e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180048429`

## string_xrefs

- `0x180048370`: `System\CurrentControlSet\Services\iphlpsvc\Teredo`
- `0x1800484f0`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x1800484cb`: `TeredoRefreshClientPerCompartment returned 0x%x`
- `0x180048404`: `TeredoRefreshClient: failed to delete Type 0x%x`
- `0x18004840d`: `TeredoRefreshClient: Failed to read Teredo Type 0x%x`
- `0x18004845a`: `TeredoRefreshClient: failed to delete ServerName 0x%x`
- `0x180048481`: `TeredoRefreshClient: failed to open reg key 0x%x`

## pseudocode

```c
__int64 __fastcall TeredoRefreshClient(unsigned int a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int64 result; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  __int64 v8; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF

  v8 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Data = 0;
  Type = 0;
  cbData = 0;
  if ( !RunningOnXboxOne )
  {
    v2 = TeredoOpenRegKey(&hKey);
    if ( v2 || hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      EventWriteError0(0x100000, L"TeredoRefreshClient: failed to open reg key 0x%x", v2);
    }
    else
    {
      cbData = 4;
      v3 = RegQueryValueExW(hKey, L"Type", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( v3 )
      {
        EventWriteError0(0x100000, L"TeredoRefreshClient: Failed to read Teredo Type 0x%x", v3);
      }
      else if ( Type != 4 || Data == 4 )
      {
        v4 = RegDeleteValueW(hKey, L"Type");
        if ( v4 )
          EventWriteError0(0x100000, L"TeredoRefreshClient: failed to delete Type 0x%x", v4);
        else
          EventWrite0(0x100000, L"TeredoRefreshClient: Successfully cleared client Type");
      }
      v5 = RegDeleteValueW(hKey, L"ServerName");
      if ( v5 )
      {
        if ( v5 == 2 )
          EventWrite0(0x100000, L"TeredoRefreshClient: No ServerName to clear");
        else
          EventWriteError0(0x100000, L"TeredoRefreshClient: failed to delete ServerName 0x%x", v5);
      }
      else
      {
        EventWrite0(0x100000, L"TeredoRefreshClient: Successfully cleared ServerName");
      }
      if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        RegCloseKey(hKey);
    }
  }
  if ( !dword_1800CA0A0 || g_StopServiceEventSet )
    return 2147942421LL;
  v8 = a1;
  ForEachCompartment(TeredoRefreshClientPerCompartment, &v8, &g_ProtocolStateTeredo);
  if ( HIDWORD(v8) )
  {
    EventWriteError0(0x100000, L"TeredoRefreshClientPerCompartment returned 0x%x");
    result = HIDWORD(v8);
    if ( SHIDWORD(v8) > 0 )
      return WORD2(v8) | 0x80070000;
  }
  else
  {
    if ( (unsigned int)ReferenceServiceEx(
                         "TeredoRefreshClient",
                         L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
                         9474) )
      TeredoConfigurationChangeNotification(0, 0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004832c  push    rbp
0x18004832e  push    rbx
0x18004832f  push    rsi
0x180048330  mov     rbp, rsp
0x180048333  sub     rsp, 40h
0x180048337  cmp     cs:RunningOnXboxOne, 0
0x18004833e  mov     ebx, ecx
0x180048340  mov     [rbp+var_8], 0
0x180048348  mov     esi, 100000h
0x18004834d  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x180048355  mov     [rbp+Data], 0
0x18004835c  mov     [rbp+Type], 0
0x180048363  mov     [rbp+cbData], 0
0x18004836a  jnz     loc_18004848F
0x180048370  lea     rdx, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\ip"...
0x180048377  lea     rcx, [rbp+hKey]; phkResult
0x18004837b  call    TeredoOpenRegKey
0x180048380  test    eax, eax
0x180048382  jnz     loc_18004847E
0x180048388  mov     rcx, [rbp+hKey]; hKey
0x18004838c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180048390  jz      loc_18004847E
0x180048396  lea     rax, [rbp+cbData]
0x18004839a  mov     [rbp+cbData], 4
0x1800483a1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800483a6  lea     r9, [rbp+Type]; lpType
0x1800483aa  lea     rax, [rbp+Data]
0x1800483ae  xor     r8d, r8d; lpReserved
0x1800483b1  lea     rdx, aType; "Type"
0x1800483b8  mov     [rsp+40h+lpData], rax; lpData
0x1800483bd  call    cs:__imp_RegQueryValueExW
0x1800483c4  nop     dword ptr [rax+rax+00h]
0x1800483c9  test    eax, eax
0x1800483cb  jnz     short loc_18004840D
0x1800483cd  cmp     [rbp+Type], 4
0x1800483d1  jnz     short loc_1800483D9
0x1800483d3  cmp     [rbp+Data], 4
0x1800483d7  jnz     short loc_18004841E
0x1800483d9  mov     rcx, [rbp+hKey]; hKey
0x1800483dd  lea     rdx, aType; "Type"
0x1800483e4  call    cs:__imp_RegDeleteValueW
0x1800483eb  nop     dword ptr [rax+rax+00h]
0x1800483f0  mov     ecx, esi
0x1800483f2  test    eax, eax
0x1800483f4  jnz     short loc_180048404
0x1800483f6  lea     rdx, aTeredorefreshc_7; "TeredoRefreshClient: Successfully clear"...
0x1800483fd  call    EventWrite0
0x180048402  jmp     short loc_18004841E
0x180048404  lea     rdx, aTeredorefreshc_6; "TeredoRefreshClient: failed to delete T"...
0x18004840b  jmp     short loc_180048416
0x18004840d  lea     rdx, aTeredorefreshc_5; "TeredoRefreshClient: Failed to read Ter"...
0x180048414  mov     ecx, esi
0x180048416  mov     r8d, eax
0x180048419  call    EventWriteError0
0x18004841e  mov     rcx, [rbp+hKey]; hKey
0x180048422  lea     rdx, aServername; "ServerName"
0x180048429  call    cs:__imp_RegDeleteValueW
0x180048430  nop     dword ptr [rax+rax+00h]
0x180048435  mov     ecx, esi
0x180048437  test    eax, eax
0x180048439  jnz     short loc_180048444
0x18004843b  lea     rdx, aTeredorefreshc_3; "TeredoRefreshClient: Successfully clear"...
0x180048442  jmp     short loc_180048450
0x180048444  cmp     eax, 2
0x180048447  jnz     short loc_180048457
0x180048449  lea     rdx, aTeredorefreshc_9; "TeredoRefreshClient: No ServerName to c"...
0x180048450  call    EventWrite0
0x180048455  jmp     short loc_180048466
0x180048457  mov     r8d, eax
0x18004845a  lea     rdx, aTeredorefreshc_2; "TeredoRefreshClient: failed to delete S"...
0x180048461  call    EventWriteError0
0x180048466  mov     rcx, [rbp+hKey]; hKey
0x18004846a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004846e  jz      short loc_18004848F
0x180048470  call    cs:__imp_RegCloseKey
0x180048477  nop     dword ptr [rax+rax+00h]
0x18004847c  jmp     short loc_18004848F
0x18004847e  mov     r8d, eax
0x180048481  lea     rdx, aTeredorefreshc_1; "TeredoRefreshClient: failed to open reg"...
0x180048488  mov     ecx, esi
0x18004848a  call    EventWriteError0
0x18004848f  cmp     cs:dword_1800CA0A0, 0
0x180048496  jz      short loc_180048514
0x180048498  cmp     cs:g_StopServiceEventSet, 0
0x18004849f  jnz     short loc_180048514
0x1800484a1  lea     r8, g_ProtocolStateTeredo
0x1800484a8  mov     dword ptr [rbp+var_8], ebx
0x1800484ab  lea     rdx, [rbp+var_8]
0x1800484af  mov     dword ptr [rbp+var_8+4], 0
0x1800484b6  lea     rcx, TeredoRefreshClientPerCompartment
0x1800484bd  call    ForEachCompartment
0x1800484c2  mov     r8d, dword ptr [rbp+var_8+4]
0x1800484c6  test    r8d, r8d
0x1800484c9  jz      short loc_1800484EA
0x1800484cb  lea     rdx, aTeredorefreshc_0; "TeredoRefreshClientPerCompartment retur"...
0x1800484d2  mov     ecx, esi
0x1800484d4  call    EventWriteError0
0x1800484d9  mov     eax, dword ptr [rbp+var_8+4]
0x1800484dc  test    eax, eax
0x1800484de  jle     short loc_180048519
0x1800484e0  movzx   eax, ax
0x1800484e3  or      eax, 80070000h
0x1800484e8  jmp     short loc_180048519
0x1800484ea  mov     r8d, 2502h
0x1800484f0  lea     rdx, aOnecoreuapNetN_27; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800484f7  lea     rcx, aTeredorefreshc_8; "TeredoRefreshClient"
0x1800484fe  call    ReferenceServiceEx
0x180048503  test    eax, eax
0x180048505  jz      short loc_180048510
0x180048507  xor     edx, edx; Context
0x180048509  xor     ecx, ecx; Instance
0x18004850b  call    TeredoConfigurationChangeNotification
0x180048510  xor     eax, eax
0x180048512  jmp     short loc_180048519
0x180048514  mov     eax, 80070015h
0x180048519  add     rsp, 40h
0x18004851d  pop     rsi
0x18004851e  pop     rbx
0x18004851f  pop     rbp
0x180048520  retn
```
