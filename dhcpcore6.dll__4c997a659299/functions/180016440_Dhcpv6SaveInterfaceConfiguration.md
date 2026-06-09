# Dhcpv6SaveInterfaceConfiguration

- ea: `0x180016440`
- end: `0x180016651`
- name: `Dhcpv6SaveInterfaceConfiguration`
- size: `529`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180010088`
- `0x180011e04`

## callees

- `0x1800062e8`
- `0x18000e950`
- `0x180016440`
- `0x1800337d0`
- `0x180033900`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800164be`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800164be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016549`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016549`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800165fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800165fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016630`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016630`

## pseudocode

```c
__int64 __fastcall Dhcpv6SaveInterfaceConfiguration(__int64 a1)
{
  _DWORD *v2; // rdi
  int v3; // ecx
  int v4; // eax
  int v5; // eax
  int v6; // ecx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // edi
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  dwDisposition = 0;
  if ( a1 && *(_QWORD *)(a1 + 8952) )
  {
    v2 = (_DWORD *)(a1 + 8860);
    v3 = g_fVelocityDhcpv6ContextBitfieldUpdate;
    if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
    {
      v4 = *(_DWORD *)(a1 + 8876);
      v3 = g_fVelocityDhcpv6ContextBitfieldUpdate;
    }
    else
    {
      v4 = (*v2 >> 4) & 1;
    }
    if ( v4 )
    {
      v5 = v3 ? *(_DWORD *)(a1 + 8880) : (*v2 >> 5) & 1;
      if ( v5
        || _time64(0) <= *(_QWORD *)(a1 + 512)
        && ((v6 = g_fVelocityDhcpv6ContextBitfieldUpdate) == 0
          ? (v7 = (*v2 >> 4) & 1)
          : (v7 = *(_DWORD *)(a1 + 8876), v6 = g_fVelocityDhcpv6ContextBitfieldUpdate),
            v7
         && (!v6 ? (v8 = (*v2 >> 5) & 1) : (v8 = *(_DWORD *)(a1 + 8880)), !v8 && *(_QWORD *)(a1 + 104) != a1 + 104)) )
      {
        v9 = RegOpenKeyExW(*(HKEY *)(a1 + 648), *(LPCWSTR *)(a1 + 8952), 0, 0xFu, &hKey);
        if ( !v9 )
          goto LABEL_28;
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_S(1028, 97, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, *(_QWORD *)(a1 + 8952));
        v9 = DhcpCacheScavanger(a1, 1);
        if ( v9 )
        {
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_(1028, 98, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
          goto LABEL_30;
        }
        v9 = RegCreateKeyExW(*(HKEY *)(a1 + 648), *(LPCWSTR *)(a1 + 8952), 0, 0, 0, 0xFu, 0, &hKey, &dwDisposition);
        if ( !v9 )
        {
LABEL_28:
          if ( !hKey )
            return v9;
          DhcpRegCopy(*(HKEY *)(a1 + 648), hKey);
        }
LABEL_30:
        if ( hKey )
          RegCloseKey(hKey);
        return v9;
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180016440  mov     [rsp+arg_10], rbx
0x180016445  push    rdi
0x180016446  sub     rsp, 50h
0x18001644a  mov     [rsp+58h+hKey], 0
0x180016453  mov     rbx, rcx
0x180016456  mov     [rsp+58h+dwDisposition], 0
0x18001645e  test    rcx, rcx
0x180016461  jz      loc_180016640
0x180016467  cmp     qword ptr [rcx+22F8h], 0
0x18001646f  jz      loc_180016640
0x180016475  lea     rdi, [rcx+229Ch]
0x18001647c  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x180016482  test    ecx, ecx
0x180016484  jz      short loc_180016494
0x180016486  mov     eax, [rbx+22ACh]
0x18001648c  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x180016492  jmp     short loc_18001649C
0x180016494  mov     eax, [rdi]
0x180016496  shr     eax, 4
0x180016499  and     eax, 1
0x18001649c  test    eax, eax
0x18001649e  jz      loc_180016640
0x1800164a4  test    ecx, ecx
0x1800164a6  jz      short loc_1800164B0
0x1800164a8  mov     eax, [rbx+22B0h]
0x1800164ae  jmp     short loc_1800164B8
0x1800164b0  mov     eax, [rdi]
0x1800164b2  shr     eax, 5
0x1800164b5  and     eax, 1
0x1800164b8  test    eax, eax
0x1800164ba  jnz     short loc_180016528
0x1800164bc  xor     ecx, ecx; Time
0x1800164be  call    cs:__imp__time64
0x1800164c5  nop     dword ptr [rax+rax+00h]
0x1800164ca  cmp     rax, [rbx+200h]
0x1800164d1  jg      loc_180016640
0x1800164d7  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x1800164dd  test    ecx, ecx
0x1800164df  jz      short loc_1800164EF
0x1800164e1  mov     eax, [rbx+22ACh]
0x1800164e7  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x1800164ed  jmp     short loc_1800164F7
0x1800164ef  mov     eax, [rdi]
0x1800164f1  shr     eax, 4
0x1800164f4  and     eax, 1
0x1800164f7  test    eax, eax
0x1800164f9  jz      loc_180016640
0x1800164ff  test    ecx, ecx
0x180016501  jz      short loc_18001650B
0x180016503  mov     eax, [rbx+22B0h]
0x180016509  jmp     short loc_180016513
0x18001650b  mov     eax, [rdi]
0x18001650d  shr     eax, 5
0x180016510  and     eax, 1
0x180016513  test    eax, eax
0x180016515  jnz     loc_180016640
0x18001651b  lea     rax, [rbx+68h]
0x18001651f  cmp     [rax], rax
0x180016522  jz      loc_180016640
0x180016528  mov     rdx, [rbx+22F8h]; lpSubKey
0x18001652f  lea     rax, [rsp+58h+hKey]
0x180016534  mov     rcx, [rbx+288h]; hKey
0x18001653b  mov     r9d, 0Fh; samDesired
0x180016541  xor     r8d, r8d; ulOptions
0x180016544  mov     [rsp+58h+phkResult], rax; phkResult
0x180016549  call    cs:__imp_RegOpenKeyExW
0x180016550  nop     dword ptr [rax+rax+00h]
0x180016555  mov     edi, eax
0x180016557  test    eax, eax
0x180016559  jz      loc_180016610
0x18001655f  test    byte ptr cs:xmmword_1800423E0, 10h
0x180016566  jz      short loc_180016585
0x180016568  mov     r9, [rbx+22F8h]
0x18001656f  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180016576  mov     edx, 61h ; 'a'
0x18001657b  mov     ecx, 404h
0x180016580  call    WPP_SF_S
0x180016585  mov     edx, 1
0x18001658a  mov     rcx, rbx
0x18001658d  call    DhcpCacheScavanger
0x180016592  mov     edi, eax
0x180016594  test    eax, eax
0x180016596  jz      short loc_1800165BD
0x180016598  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001659f  jz      loc_180016626
0x1800165a5  mov     edx, 62h ; 'b'
0x1800165aa  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x1800165b1  mov     ecx, 404h
0x1800165b6  call    WPP_SF_
0x1800165bb  jmp     short loc_180016626
0x1800165bd  mov     rdx, [rbx+22F8h]; lpSubKey
0x1800165c4  lea     rax, [rsp+58h+dwDisposition]
0x1800165c9  mov     rcx, [rbx+288h]; hKey
0x1800165d0  xor     r9d, r9d; lpClass
0x1800165d3  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800165d8  xor     r8d, r8d; Reserved
0x1800165db  lea     rax, [rsp+58h+hKey]
0x1800165e0  mov     [rsp+58h+var_20], rax; phkResult
0x1800165e5  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800165ee  mov     [rsp+58h+samDesired], 0Fh; samDesired
0x1800165f6  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x1800165fe  call    cs:__imp_RegCreateKeyExW
0x180016605  nop     dword ptr [rax+rax+00h]
0x18001660a  mov     edi, eax
0x18001660c  test    eax, eax
0x18001660e  jnz     short loc_180016626
0x180016610  mov     rdx, [rsp+58h+hKey]; HKEY
0x180016615  test    rdx, rdx
0x180016618  jz      short loc_18001663C
0x18001661a  mov     rcx, [rbx+288h]; hKey
0x180016621  call    DhcpRegCopy
0x180016626  mov     rcx, [rsp+58h+hKey]; hKey
0x18001662b  test    rcx, rcx
0x18001662e  jz      short loc_18001663C
0x180016630  call    cs:__imp_RegCloseKey
0x180016637  nop     dword ptr [rax+rax+00h]
0x18001663c  mov     eax, edi
0x18001663e  jmp     short loc_180016645
0x180016640  mov     eax, 57h ; 'W'
0x180016645  mov     rbx, [rsp+58h+arg_10]
0x18001664a  add     rsp, 50h
0x18001664e  pop     rdi
0x18001664f  retn
```
