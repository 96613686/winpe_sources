# ZtRegOpen

- ea: `0x1800689f4`
- end: `0x180068b99`
- name: `ZtRegOpen`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180055ac4`

## callees

- `0x18002025c`
- `0x180046ec0`
- `0x1800689f4`
- `0x18007dfa4`
- `0x180086b1c`

## import_xrefs

- `ntdll!NtClose` at `0x180068b70`
- `ntdll!NtClose` at `0x180068b70`
- `ntdll!NtCreateRegistryTransaction` at `0x180068a80`
- `ntdll!NtCreateRegistryTransaction` at `0x180068a80`
- `ntdll!RtlNtStatusToDosError` at `0x180068a88`
- `ntdll!RtlNtStatusToDosError` at `0x180068a88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068b59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068b59`

## string_xrefs

- `0x180068aa5`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x180068ab4`: `Dnscache`
- `0x180068a6b`: `Parameters\ZTDNS\ZTStagingConfig`

## pseudocode

```c
__int64 __fastcall ZtRegOpen(unsigned int a1, __int64 a2, __int64 a3, HKEY *a4, HANDLE *a5)
{
  const wchar_t *v7; // r14
  NTSTATUS v8; // eax
  ULONG v9; // ebx
  __int64 v10; // r9
  ULONG v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-18h] BYREF

  Handle = 0;
  hKey = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_dqq(a1, 10, (unsigned int)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, a1, (__int64)a4, (__int64)a5);
  if ( a1 > 1 )
  {
    v9 = 87;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_16;
    v12 = 11;
    v13 = 87;
  }
  else
  {
    v7 = L"Parameters\\ZTDNS\\ZTStagingConfig";
    if ( a1 != 1 )
      v7 = L"Parameters\\ZTDNS";
    v8 = NtCreateRegistryTransaction(&Handle, 2031679, 0, 0);
    v9 = RtlNtStatusToDosError(v8);
    if ( v9 )
      goto LABEL_14;
    v11 = CreatePersistedRegistryKeyHelper(
            (__int64)L"Dnscache",
            (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
            (__int64)v7,
            v10,
            0x20019u,
            (__int64)Handle,
            1,
            &hKey);
    v9 = v11;
    if ( !v11 )
    {
      *a4 = hKey;
      *a5 = Handle;
      hKey = 0;
      Handle = 0;
      goto LABEL_14;
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_16;
    v12 = 12;
    v13 = v11;
  }
  WPP_SF_d(1035, v12, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, v13);
LABEL_14:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 13, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, v9);
LABEL_16:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( Handle )
    NtClose(Handle);
  return v9;
}

```

## disassembly

```asm
0x1800689f4  mov     r11, rsp
0x1800689f7  mov     [r11+10h], rbx
0x1800689fb  mov     [r11+18h], rsi
0x1800689ff  push    rbp
0x180068a00  push    rdi
0x180068a01  push    r14
0x180068a03  mov     rbp, rsp
0x180068a06  sub     rsp, 60h
0x180068a0a  mov     rax, cs:__security_cookie
0x180068a11  xor     rax, rsp
0x180068a14  mov     [rbp+var_10], rax
0x180068a18  mov     rsi, [rbp+arg_20]
0x180068a1c  mov     rdi, r9
0x180068a1f  mov     ebx, ecx
0x180068a21  mov     [rbp+Handle], 0
0x180068a29  mov     [rbp+hKey], 0
0x180068a31  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180068a38  jz      short loc_180068A56
0x180068a3a  mov     [r11-50h], rsi
0x180068a3e  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x180068a45  mov     [r11-58h], r9
0x180068a49  mov     edx, 0Ah
0x180068a4e  mov     r9d, ecx
0x180068a51  call    WPP_SF_dqq
0x180068a56  cmp     ebx, 1
0x180068a59  ja      loc_180068B09
0x180068a5f  lea     rax, aParametersZtdn; "Parameters\\ZTDNS"
0x180068a66  mov     edx, 1F003Fh
0x180068a6b  lea     r14, aParametersZtdn_0; "Parameters\\ZTDNS\\ZTStagingConfig"
0x180068a72  cmovnz  r14, rax
0x180068a76  lea     rcx, [rbp+Handle]
0x180068a7a  xor     r9d, r9d
0x180068a7d  xor     r8d, r8d
0x180068a80  call    cs:__imp_NtCreateRegistryTransaction
0x180068a86  mov     ecx, eax; Status
0x180068a88  call    cs:__imp_RtlNtStatusToDosError
0x180068a8e  mov     ebx, eax
0x180068a90  test    eax, eax
0x180068a92  jnz     loc_180068B2E
0x180068a98  mov     rax, [rbp+Handle]
0x180068a9c  lea     rcx, [rbp+hKey]
0x180068aa0  mov     [rsp+60h+var_28], rcx
0x180068aa5  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180068aac  mov     [rsp+60h+var_30], 1
0x180068ab4  lea     rcx, aDnscache_0; "Dnscache"
0x180068abb  mov     [rsp+60h+var_38], rax
0x180068ac0  mov     r8, r14
0x180068ac3  mov     [rsp+60h+var_40], 20019h
0x180068acb  call    CreatePersistedRegistryKeyHelper
0x180068ad0  mov     ebx, eax
0x180068ad2  test    eax, eax
0x180068ad4  jnz     short loc_180068AF6
0x180068ad6  mov     rax, [rbp+hKey]
0x180068ada  mov     [rdi], rax
0x180068add  mov     rax, [rbp+Handle]
0x180068ae1  mov     [rsi], rax
0x180068ae4  mov     [rbp+hKey], 0
0x180068aec  mov     [rbp+Handle], 0
0x180068af4  jmp     short loc_180068B2E
0x180068af6  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180068afd  jz      short loc_180068B50
0x180068aff  mov     edx, 0Ch
0x180068b04  mov     r9d, eax
0x180068b07  jmp     short loc_180068B1D
0x180068b09  mov     ebx, 57h ; 'W'
0x180068b0e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180068b15  jz      short loc_180068B50
0x180068b17  lea     edx, [rbx-4Ch]
0x180068b1a  mov     r9d, ebx
0x180068b1d  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x180068b24  mov     ecx, 40Bh
0x180068b29  call    WPP_SF_d
0x180068b2e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180068b35  jz      short loc_180068B50
0x180068b37  mov     edx, 0Dh
0x180068b3c  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x180068b43  mov     ecx, 40Bh
0x180068b48  mov     r9d, ebx
0x180068b4b  call    WPP_SF_d
0x180068b50  mov     rcx, [rbp+hKey]; hKey
0x180068b54  test    rcx, rcx
0x180068b57  jz      short loc_180068B67
0x180068b59  call    cs:__imp_RegCloseKey
0x180068b5f  mov     [rbp+hKey], 0
0x180068b67  mov     rcx, [rbp+Handle]; Handle
0x180068b6b  test    rcx, rcx
0x180068b6e  jz      short loc_180068B76
0x180068b70  call    cs:__imp_NtClose
0x180068b76  mov     eax, ebx
0x180068b78  mov     rcx, [rbp+var_10]
0x180068b7c  xor     rcx, rsp; StackCookie
0x180068b7f  call    __security_check_cookie
0x180068b84  lea     r11, [rsp+60h+var_s0]
0x180068b89  mov     rbx, [r11+28h]
0x180068b8d  mov     rsi, [r11+30h]
0x180068b91  mov     rsp, r11
0x180068b94  pop     r14
0x180068b96  pop     rdi
0x180068b97  pop     rbp
0x180068b98  retn
```
