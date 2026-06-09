# TeredoRefreshClient

- ea: `0x18004836c`
- end: `0x180048562`
- name: `TeredoRefreshClient`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180069460`

## callees

- `0x180004dd0`
- `0x18000d7b0`
- `0x1800190e0`
- `0x18002dcb0`
- `0x18002e150`
- `0x180033968`
- `0x18004836c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800483fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800483fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800484b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800484b0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180048424`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180048469`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180048424`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180048469`

## string_xrefs

- `0x1800483b0`: `System\CurrentControlSet\Services\iphlpsvc\Teredo`
- `0x180048530`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x18004850b`: `TeredoRefreshClientPerCompartment returned 0x%x`
- `0x180048444`: `TeredoRefreshClient: failed to delete Type 0x%x`
- `0x18004844d`: `TeredoRefreshClient: Failed to read Teredo Type 0x%x`
- `0x18004849a`: `TeredoRefreshClient: failed to delete ServerName 0x%x`
- `0x1800484c1`: `TeredoRefreshClient: failed to open reg key 0x%x`

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
0x18004836c  push    rbp
0x18004836e  push    rbx
0x18004836f  push    rsi
0x180048370  mov     rbp, rsp
0x180048373  sub     rsp, 40h
0x180048377  cmp     cs:RunningOnXboxOne, 0
0x18004837e  mov     ebx, ecx
0x180048380  mov     [rbp+var_8], 0
0x180048388  mov     esi, 100000h
0x18004838d  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x180048395  mov     [rbp+Data], 0
0x18004839c  mov     [rbp+Type], 0
0x1800483a3  mov     [rbp+cbData], 0
0x1800483aa  jnz     loc_1800484CF
0x1800483b0  lea     rdx, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\ip"...
0x1800483b7  lea     rcx, [rbp+hKey]; phkResult
0x1800483bb  call    TeredoOpenRegKey
0x1800483c0  test    eax, eax
0x1800483c2  jnz     loc_1800484BE
0x1800483c8  mov     rcx, [rbp+hKey]; hKey
0x1800483cc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800483d0  jz      loc_1800484BE
0x1800483d6  lea     rax, [rbp+cbData]
0x1800483da  mov     [rbp+cbData], 4
0x1800483e1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800483e6  lea     r9, [rbp+Type]; lpType
0x1800483ea  lea     rax, [rbp+Data]
0x1800483ee  xor     r8d, r8d; lpReserved
0x1800483f1  lea     rdx, aType; "Type"
0x1800483f8  mov     [rsp+40h+lpData], rax; lpData
0x1800483fd  call    cs:__imp_RegQueryValueExW
0x180048404  nop     dword ptr [rax+rax+00h]
0x180048409  test    eax, eax
0x18004840b  jnz     short loc_18004844D
0x18004840d  cmp     [rbp+Type], 4
0x180048411  jnz     short loc_180048419
0x180048413  cmp     [rbp+Data], 4
0x180048417  jnz     short loc_18004845E
0x180048419  mov     rcx, [rbp+hKey]; hKey
0x18004841d  lea     rdx, aType; "Type"
0x180048424  call    cs:__imp_RegDeleteValueW
0x18004842b  nop     dword ptr [rax+rax+00h]
0x180048430  mov     ecx, esi
0x180048432  test    eax, eax
0x180048434  jnz     short loc_180048444
0x180048436  lea     rdx, aTeredorefreshc_7; "TeredoRefreshClient: Successfully clear"...
0x18004843d  call    EventWrite0
0x180048442  jmp     short loc_18004845E
0x180048444  lea     rdx, aTeredorefreshc_6; "TeredoRefreshClient: failed to delete T"...
0x18004844b  jmp     short loc_180048456
0x18004844d  lea     rdx, aTeredorefreshc_5; "TeredoRefreshClient: Failed to read Ter"...
0x180048454  mov     ecx, esi
0x180048456  mov     r8d, eax
0x180048459  call    EventWriteError0
0x18004845e  mov     rcx, [rbp+hKey]; hKey
0x180048462  lea     rdx, aServername; "ServerName"
0x180048469  call    cs:__imp_RegDeleteValueW
0x180048470  nop     dword ptr [rax+rax+00h]
0x180048475  mov     ecx, esi
0x180048477  test    eax, eax
0x180048479  jnz     short loc_180048484
0x18004847b  lea     rdx, aTeredorefreshc_3; "TeredoRefreshClient: Successfully clear"...
0x180048482  jmp     short loc_180048490
0x180048484  cmp     eax, 2
0x180048487  jnz     short loc_180048497
0x180048489  lea     rdx, aTeredorefreshc_9; "TeredoRefreshClient: No ServerName to c"...
0x180048490  call    EventWrite0
0x180048495  jmp     short loc_1800484A6
0x180048497  mov     r8d, eax
0x18004849a  lea     rdx, aTeredorefreshc_2; "TeredoRefreshClient: failed to delete S"...
0x1800484a1  call    EventWriteError0
0x1800484a6  mov     rcx, [rbp+hKey]; hKey
0x1800484aa  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800484ae  jz      short loc_1800484CF
0x1800484b0  call    cs:__imp_RegCloseKey
0x1800484b7  nop     dword ptr [rax+rax+00h]
0x1800484bc  jmp     short loc_1800484CF
0x1800484be  mov     r8d, eax
0x1800484c1  lea     rdx, aTeredorefreshc_1; "TeredoRefreshClient: failed to open reg"...
0x1800484c8  mov     ecx, esi
0x1800484ca  call    EventWriteError0
0x1800484cf  cmp     cs:dword_1800CA0A0, 0
0x1800484d6  jz      short loc_180048554
0x1800484d8  cmp     cs:g_StopServiceEventSet, 0
0x1800484df  jnz     short loc_180048554
0x1800484e1  lea     r8, g_ProtocolStateTeredo
0x1800484e8  mov     dword ptr [rbp+var_8], ebx
0x1800484eb  lea     rdx, [rbp+var_8]
0x1800484ef  mov     dword ptr [rbp+var_8+4], 0
0x1800484f6  lea     rcx, TeredoRefreshClientPerCompartment
0x1800484fd  call    ForEachCompartment
0x180048502  mov     r8d, dword ptr [rbp+var_8+4]
0x180048506  test    r8d, r8d
0x180048509  jz      short loc_18004852A
0x18004850b  lea     rdx, aTeredorefreshc_0; "TeredoRefreshClientPerCompartment retur"...
0x180048512  mov     ecx, esi
0x180048514  call    EventWriteError0
0x180048519  mov     eax, dword ptr [rbp+var_8+4]
0x18004851c  test    eax, eax
0x18004851e  jle     short loc_180048559
0x180048520  movzx   eax, ax
0x180048523  or      eax, 80070000h
0x180048528  jmp     short loc_180048559
0x18004852a  mov     r8d, 2502h
0x180048530  lea     rdx, aOnecoreuapNetN_27; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180048537  lea     rcx, aTeredorefreshc_8; "TeredoRefreshClient"
0x18004853e  call    ReferenceServiceEx
0x180048543  test    eax, eax
0x180048545  jz      short loc_180048550
0x180048547  xor     edx, edx; Context
0x180048549  xor     ecx, ecx; Instance
0x18004854b  call    TeredoConfigurationChangeNotification
0x180048550  xor     eax, eax
0x180048552  jmp     short loc_180048559
0x180048554  mov     eax, 80070015h
0x180048559  add     rsp, 40h
0x18004855d  pop     rsi
0x18004855e  pop     rbx
0x18004855f  pop     rbp
0x180048560  retn
```
