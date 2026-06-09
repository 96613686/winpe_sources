# IsOOBEInProgress(void)

- ea: `0x180058e50`
- end: `0x180058fb5`
- name: `?IsOOBEInProgress@@YAHXZ`
- size: `357`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18005a838`

## callees

- `0x180011a58`
- `0x180047240`
- `0x180058e50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058eaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058eaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058f60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058f60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058edf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058edf`

## pseudocode

```c
__int64 IsOOBEInProgress(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  unsigned int v2; // eax
  __int64 v3; // r9
  __int64 v4; // rcx
  __int64 v5; // rdx
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-14h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-10h] BYREF

  *(_DWORD *)Data = 0;
  hKey = 0;
  Type = 0;
  cbData = 4;
  v0 = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, &hKey);
  if ( !v1 )
  {
    v2 = RegQueryValueExW(hKey, L"OobeInProgress", 0, &Type, Data, &cbData);
    v3 = v2;
    if ( !v2 && Type == 4 && cbData == 4 )
    {
      v3 = *(unsigned int *)Data;
      LOBYTE(v0) = *(_DWORD *)Data != 0;
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u )
      {
        goto LABEL_14;
      }
      v5 = 11;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u )
      {
        goto LABEL_14;
      }
      v5 = 12;
    }
    WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids, v3);
LABEL_14:
    RegCloseKey(hKey);
    return v0;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids, v1);
  }
  return v0;
}

```

## disassembly

```asm
0x180058e50  mov     [rsp-8+arg_0], rbx
0x180058e55  push    rbp
0x180058e56  mov     rbp, rsp
0x180058e59  sub     rsp, 50h
0x180058e5d  mov     rax, cs:__security_cookie
0x180058e64  xor     rax, rsp
0x180058e67  mov     [rbp+var_8], rax
0x180058e6b  lea     rax, [rbp+hKey]
0x180058e6f  mov     dword ptr [rbp+Data], 0
0x180058e76  mov     r9d, 20019h; samDesired
0x180058e7c  mov     [rsp+50h+phkResult], rax; phkResult
0x180058e81  xor     r8d, r8d; ulOptions
0x180058e84  mov     [rbp+hKey], 0
0x180058e8c  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x180058e93  mov     [rbp+Type], 0
0x180058e9a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058ea1  mov     [rbp+cbData], 4
0x180058ea8  xor     ebx, ebx
0x180058eaa  call    cs:__imp_RegOpenKeyExW
0x180058eb0  mov     r9d, eax
0x180058eb3  test    eax, eax
0x180058eb5  jnz     loc_180058F68
0x180058ebb  mov     rcx, [rbp+hKey]; hKey
0x180058ebf  lea     rax, [rbp+cbData]
0x180058ec3  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180058ec8  lea     r9, [rbp+Type]; lpType
0x180058ecc  lea     rax, [rbp+Data]
0x180058ed0  xor     r8d, r8d; lpReserved
0x180058ed3  lea     rdx, aOobeinprogress; "OobeInProgress"
0x180058eda  mov     [rsp+50h+phkResult], rax; lpData
0x180058edf  call    cs:__imp_RegQueryValueExW
0x180058ee5  mov     r9d, eax
0x180058ee8  test    eax, eax
0x180058eea  jnz     short loc_180058F28
0x180058eec  cmp     [rbp+Type], 4
0x180058ef0  jnz     short loc_180058F28
0x180058ef2  cmp     [rbp+cbData], 4
0x180058ef6  jnz     short loc_180058F28
0x180058ef8  mov     r9d, dword ptr [rbp+Data]
0x180058efc  test    r9d, r9d
0x180058eff  setnz   bl
0x180058f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f09  lea     rax, WPP_GLOBAL_Control
0x180058f10  cmp     rcx, rax
0x180058f13  jz      short loc_180058F5C
0x180058f15  test    byte ptr [rcx+1Ch], 10h
0x180058f19  jz      short loc_180058F5C
0x180058f1b  cmp     byte ptr [rcx+19h], 5
0x180058f1f  jb      short loc_180058F5C
0x180058f21  mov     edx, 0Bh
0x180058f26  jmp     short loc_180058F4C
0x180058f28  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f2f  lea     rax, WPP_GLOBAL_Control
0x180058f36  cmp     rcx, rax
0x180058f39  jz      short loc_180058F5C
0x180058f3b  test    byte ptr [rcx+1Ch], 10h
0x180058f3f  jz      short loc_180058F5C
0x180058f41  cmp     byte ptr [rcx+19h], 5
0x180058f45  jb      short loc_180058F5C
0x180058f47  mov     edx, 0Ch
0x180058f4c  mov     rcx, [rcx+10h]
0x180058f50  lea     r8, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids
0x180058f57  call    WPP_SF_d
0x180058f5c  mov     rcx, [rbp+hKey]; hKey
0x180058f60  call    cs:__imp_RegCloseKey
0x180058f66  jmp     short loc_180058F9C
0x180058f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f6f  lea     rax, WPP_GLOBAL_Control
0x180058f76  cmp     rcx, rax
0x180058f79  jz      short loc_180058F9C
0x180058f7b  test    byte ptr [rcx+1Ch], 10h
0x180058f7f  jz      short loc_180058F9C
0x180058f81  cmp     byte ptr [rcx+19h], 2
0x180058f85  jb      short loc_180058F9C
0x180058f87  mov     rcx, [rcx+10h]
0x180058f8b  lea     r8, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids
0x180058f92  mov     edx, 0Dh
0x180058f97  call    WPP_SF_d
0x180058f9c  mov     eax, ebx
0x180058f9e  mov     rcx, [rbp+var_8]
0x180058fa2  xor     rcx, rsp; StackCookie
0x180058fa5  call    __security_check_cookie
0x180058faa  mov     rbx, [rsp+50h+arg_0]
0x180058faf  add     rsp, 50h
0x180058fb3  pop     rbp
0x180058fb4  retn
```
