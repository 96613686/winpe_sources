# CNonClusterTmInstance::SetRegistryValue(char const *,char const *,ulong,uchar *,ulong)

- ea: `0x1800530b0`
- end: `0x1800531fa`
- name: `?SetRegistryValue@CNonClusterTmInstance@@UEAAJPEBD0KPEAEK@Z`
- size: `330`
- prototype: `int(CNonClusterTmInstance *__hidden this, const char *, const char *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800530b0`
- `0x1800709bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800531df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800531df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005316f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180053187`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800531b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005316f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180053187`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800531b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053114`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053132`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053114`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053132`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::SetRegistryValue(
        CNonClusterTmInstance *this,
        const char *a2,
        const char *a3,
        DWORD a4,
        unsigned __int8 *lpData,
        DWORD cbData)
{
  const unsigned __int16 *v6; // rcx
  int v10; // eax
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
  v10 = RegConnectHostnameW(v6, HKEY_LOCAL_MACHINE, &v15);
  v11 = v10;
  v12 = v10 <= 0;
  if ( v10 )
  {
LABEL_2:
    if ( v12 )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( a2 )
  {
    v10 = RegOpenKeyExA(v15, "Software\\Microsoft\\MSDTC", 0, 0x20100u, &hKey);
    v11 = v10;
    v12 = v10 <= 0;
    if ( v10 )
      goto LABEL_2;
    v10 = RegOpenKeyExA(hKey, a2, 0, 0x102u, &phkResult);
    v11 = v10;
    v12 = v10 <= 0;
    if ( v10 )
      goto LABEL_2;
    v14 = phkResult;
  }
  else
  {
    v10 = RegOpenKeyExA(v15, "Software\\Microsoft\\MSDTC", 0, 0x102u, &hKey);
    v11 = v10;
    v12 = v10 <= 0;
    if ( v10 )
      goto LABEL_2;
    v14 = hKey;
  }
  v11 = 0;
  v10 = RegSetValueExA(v14, a3, 0, a4, lpData, cbData);
  if ( v10 )
  {
    if ( v10 > 0 )
    {
LABEL_3:
      v11 = (unsigned __int16)v10 | 0x80070000;
      goto LABEL_4;
    }
    v11 = v10;
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
0x1800530b0  mov     [rsp-18h+arg_8], rbx
0x1800530b5  mov     [rsp-18h+arg_10], rsi
0x1800530ba  push    rbp
0x1800530bb  push    rdi
0x1800530bc  push    r14
0x1800530be  mov     rbp, rsp
0x1800530c1  sub     rsp, 40h
0x1800530c5  mov     rcx, [rcx+28h]; unsigned __int16 *
0x1800530c9  mov     r14, r8
0x1800530cc  mov     rdi, rdx
0x1800530cf  mov     [rbp+var_10], 0
0x1800530d7  lea     r8, [rbp+var_10]; HKEY *
0x1800530db  mov     [rbp+hKey], 0
0x1800530e3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800530ea  mov     [rbp+var_8], 0
0x1800530f2  mov     esi, r9d
0x1800530f5  call    ?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z; RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)
0x1800530fa  mov     ebx, eax
0x1800530fc  test    eax, eax
0x1800530fe  jz      short loc_18005314D
0x180053100  jle     short loc_18005310B
0x180053102  movzx   ebx, ax
0x180053105  or      ebx, 80070000h
0x18005310b  mov     rcx, [rbp+hKey]; hKey
0x18005310f  test    rcx, rcx
0x180053112  jz      short loc_18005311A
0x180053114  call    cs:__imp_RegCloseKey
0x18005311a  mov     rcx, [rbp+var_8]; hKey
0x18005311e  test    rcx, rcx
0x180053121  jz      short loc_180053129
0x180053123  call    cs:__imp_RegCloseKey
0x180053129  mov     rcx, [rbp+var_10]; hKey
0x18005312d  test    rcx, rcx
0x180053130  jz      short loc_180053138
0x180053132  call    cs:__imp_RegCloseKey
0x180053138  mov     rsi, [rsp+40h+arg_10]
0x18005313d  mov     eax, ebx
0x18005313f  mov     rbx, [rsp+40h+arg_8]
0x180053144  add     rsp, 40h
0x180053148  pop     r14
0x18005314a  pop     rdi
0x18005314b  pop     rbp
0x18005314c  retn
0x18005314d  mov     rcx, [rbp+var_10]; hKey
0x180053151  lea     rax, [rbp+hKey]
0x180053155  xor     r8d, r8d; ulOptions
0x180053158  mov     [rsp+40h+phkResult], rax; phkResult
0x18005315d  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\MSDTC"
0x180053164  test    rdi, rdi
0x180053167  jnz     short loc_180053181
0x180053169  mov     r9d, 102h; samDesired
0x18005316f  call    cs:__imp_RegOpenKeyExA
0x180053175  mov     ebx, eax
0x180053177  test    eax, eax
0x180053179  jnz     short loc_180053100
0x18005317b  mov     rcx, [rbp+hKey]
0x18005317f  jmp     short loc_1800531C4
0x180053181  mov     r9d, 20100h; samDesired
0x180053187  call    cs:__imp_RegOpenKeyExA
0x18005318d  mov     ebx, eax
0x18005318f  test    eax, eax
0x180053191  jnz     loc_180053100
0x180053197  mov     rcx, [rbp+hKey]; hKey
0x18005319b  lea     rax, [rbp+var_8]
0x18005319f  mov     r9d, 102h; samDesired
0x1800531a5  mov     [rsp+40h+phkResult], rax; phkResult
0x1800531aa  xor     r8d, r8d; ulOptions
0x1800531ad  mov     rdx, rdi; lpSubKey
0x1800531b0  call    cs:__imp_RegOpenKeyExA
0x1800531b6  mov     ebx, eax
0x1800531b8  test    eax, eax
0x1800531ba  jnz     loc_180053100
0x1800531c0  mov     rcx, [rbp+var_8]; hKey
0x1800531c4  mov     eax, [rbp+arg_28]
0x1800531c7  mov     r9d, esi; dwType
0x1800531ca  mov     [rsp+40h+cbData], eax; cbData
0x1800531ce  xor     r8d, r8d; Reserved
0x1800531d1  mov     rax, [rbp+lpData]
0x1800531d5  mov     rdx, r14; lpValueName
0x1800531d8  mov     [rsp+40h+phkResult], rax; lpData
0x1800531dd  xor     ebx, ebx
0x1800531df  call    cs:__imp_RegSetValueExA
0x1800531e5  test    eax, eax
0x1800531e7  jz      loc_18005310B
0x1800531ed  jg      loc_180053102
0x1800531f3  mov     ebx, eax
0x1800531f5  jmp     loc_18005310B
```
