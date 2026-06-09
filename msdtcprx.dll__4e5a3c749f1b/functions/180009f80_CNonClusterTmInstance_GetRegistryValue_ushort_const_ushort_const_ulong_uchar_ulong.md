# CNonClusterTmInstance::GetRegistryValue(ushort const *,ushort const *,ulong *,uchar *,ulong *)

- ea: `0x180009f80`
- end: `0x18000a0cc`
- name: `?GetRegistryValue@CNonClusterTmInstance@@UEAAJPEBG0PEAKPEAE1@Z`
- size: `332`
- prototype: `int(CNonClusterTmInstance *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009f80`
- `0x1800709bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a0b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a0b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a03f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a057`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a080`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a03f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a057`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fe4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ff3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a002`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fe4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ff3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a002`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::GetRegistryValue(
        CNonClusterTmInstance *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int8 *lpData,
        unsigned int *lpcbData)
{
  const unsigned __int16 *v6; // rcx
  int Value; // eax
  unsigned int v11; // ebx
  bool v12; // cc
  HKEY v14; // rcx
  HKEY v15; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF

  v6 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  v15 = 0;
  hKey = 0;
  phkResult = 0;
  Value = RegConnectHostnameW(v6, HKEY_LOCAL_MACHINE, &v15);
  v11 = Value;
  v12 = Value <= 0;
  if ( Value )
  {
LABEL_2:
    if ( v12 )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( a2 )
  {
    Value = RegOpenKeyExW(v15, L"Software\\Microsoft\\MSDTC", 0, 0x20100u, &hKey);
    v11 = Value;
    v12 = Value <= 0;
    if ( Value )
      goto LABEL_2;
    Value = RegOpenKeyExW(hKey, a2, 0, 0x101u, &phkResult);
    v11 = Value;
    v12 = Value <= 0;
    if ( Value )
      goto LABEL_2;
    v14 = phkResult;
  }
  else
  {
    Value = RegOpenKeyExW(v15, L"Software\\Microsoft\\MSDTC", 0, 0x101u, &hKey);
    v11 = Value;
    v12 = Value <= 0;
    if ( Value )
      goto LABEL_2;
    v14 = hKey;
  }
  v11 = 0;
  Value = RegQueryValueExW(v14, a3, 0, a4, lpData, lpcbData);
  if ( Value )
  {
    if ( Value > 0 )
    {
LABEL_3:
      v11 = (unsigned __int16)Value | 0x80070000;
      goto LABEL_4;
    }
    v11 = Value;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v15 )
    RegCloseKey(v15);
  return v11;
}

```

## disassembly

```asm
0x180009f80  mov     [rsp-18h+arg_8], rbx
0x180009f85  mov     [rsp-18h+arg_10], rsi
0x180009f8a  push    rbp
0x180009f8b  push    rdi
0x180009f8c  push    r14
0x180009f8e  mov     rbp, rsp
0x180009f91  sub     rsp, 40h
0x180009f95  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180009f99  mov     r14, r8
0x180009f9c  mov     rdi, rdx
0x180009f9f  mov     [rbp+var_10], 0
0x180009fa7  lea     r8, [rbp+var_10]; HKEY *
0x180009fab  mov     [rbp+hKey], 0
0x180009fb3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180009fba  mov     [rbp+var_8], 0
0x180009fc2  mov     rsi, r9
0x180009fc5  call    ?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z; RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)
0x180009fca  mov     ebx, eax
0x180009fcc  test    eax, eax
0x180009fce  jz      short loc_18000A01D
0x180009fd0  jle     short loc_180009FDB
0x180009fd2  movzx   ebx, ax
0x180009fd5  or      ebx, 80070000h
0x180009fdb  mov     rcx, [rbp+hKey]; hKey
0x180009fdf  test    rcx, rcx
0x180009fe2  jz      short loc_180009FEA
0x180009fe4  call    cs:__imp_RegCloseKey
0x180009fea  mov     rcx, [rbp+var_8]; hKey
0x180009fee  test    rcx, rcx
0x180009ff1  jz      short loc_180009FF9
0x180009ff3  call    cs:__imp_RegCloseKey
0x180009ff9  mov     rcx, [rbp+var_10]; hKey
0x180009ffd  test    rcx, rcx
0x18000a000  jz      short loc_18000A008
0x18000a002  call    cs:__imp_RegCloseKey
0x18000a008  mov     rsi, [rsp+40h+arg_10]
0x18000a00d  mov     eax, ebx
0x18000a00f  mov     rbx, [rsp+40h+arg_8]
0x18000a014  add     rsp, 40h
0x18000a018  pop     r14
0x18000a01a  pop     rdi
0x18000a01b  pop     rbp
0x18000a01c  retn
0x18000a01d  mov     rcx, [rbp+var_10]; hKey
0x18000a021  lea     rax, [rbp+hKey]
0x18000a025  xor     r8d, r8d; ulOptions
0x18000a028  mov     [rsp+40h+phkResult], rax; phkResult
0x18000a02d  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x18000a034  test    rdi, rdi
0x18000a037  jnz     short loc_18000A051
0x18000a039  mov     r9d, 101h; samDesired
0x18000a03f  call    cs:__imp_RegOpenKeyExW
0x18000a045  mov     ebx, eax
0x18000a047  test    eax, eax
0x18000a049  jnz     short loc_180009FD0
0x18000a04b  mov     rcx, [rbp+hKey]
0x18000a04f  jmp     short loc_18000A094
0x18000a051  mov     r9d, 20100h; samDesired
0x18000a057  call    cs:__imp_RegOpenKeyExW
0x18000a05d  mov     ebx, eax
0x18000a05f  test    eax, eax
0x18000a061  jnz     loc_180009FD0
0x18000a067  mov     rcx, [rbp+hKey]; hKey
0x18000a06b  lea     rax, [rbp+var_8]
0x18000a06f  mov     r9d, 101h; samDesired
0x18000a075  mov     [rsp+40h+phkResult], rax; phkResult
0x18000a07a  xor     r8d, r8d; ulOptions
0x18000a07d  mov     rdx, rdi; lpSubKey
0x18000a080  call    cs:__imp_RegOpenKeyExW
0x18000a086  mov     ebx, eax
0x18000a088  test    eax, eax
0x18000a08a  jnz     loc_180009FD0
0x18000a090  mov     rcx, [rbp+var_8]; hKey
0x18000a094  mov     rax, [rbp+arg_28]
0x18000a098  mov     r9, rsi; lpType
0x18000a09b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000a0a0  xor     r8d, r8d; lpReserved
0x18000a0a3  mov     rax, [rbp+lpData]
0x18000a0a7  mov     rdx, r14; lpValueName
0x18000a0aa  mov     [rsp+40h+phkResult], rax; lpData
0x18000a0af  xor     ebx, ebx
0x18000a0b1  call    cs:__imp_RegQueryValueExW
0x18000a0b7  test    eax, eax
0x18000a0b9  jz      loc_180009FDB
0x18000a0bf  jg      loc_180009FD2
0x18000a0c5  mov     ebx, eax
0x18000a0c7  jmp     loc_180009FDB
```
