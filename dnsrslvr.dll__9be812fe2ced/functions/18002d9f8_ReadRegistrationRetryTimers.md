# ReadRegistrationRetryTimers

- ea: `0x18002d9f8`
- end: `0x18002dbe5`
- name: `ReadRegistrationRetryTimers`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002c120`

## callees

- `0x180008870`
- `0x18000b130`
- `0x18002d9f8`
- `0x180046ec0`
- `0x180062018`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002da9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002dae8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002da9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002dae8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002da66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002da66`

## string_xrefs

- `0x18002da3b`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters`

## pseudocode

```c
__int64 __fastcall ReadRegistrationRetryTimers(__int64 *a1, _DWORD *a2)
{
  char *v4; // rdi
  __int64 v5; // rax
  unsigned int v6; // ebx
  _OWORD *v7; // rax
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  DWORD Type; // [rsp+50h] [rbp-10h] BYREF

  cbData = 0;
  Type = 7;
  hKey = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters", 0, 1u, &hKey)
    && !RegQueryValueExA(hKey, "RegistrationRetryTimer", 0, &Type, 0, &cbData) )
  {
    if ( Type == 7 )
    {
      v4 = (char *)Dns_Allocate(cbData);
      if ( v4 )
      {
        if ( !RegQueryValueExA(hKey, "RegistrationRetryTimer", 0, &Type, (LPBYTE)v4, &cbData) )
          Dns_CreateDwordArrayFromMultiSz(v4);
        MIDL_user_free(v4);
      }
    }
    else if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      WPP_SF_d(1035, 10, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids, 87);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  v5 = Dns_Allocate(32);
  *a1 = v5;
  if ( v5 )
  {
    v6 = 0;
    *a2 = xmmword_1800AB340;
    v7 = (_OWORD *)*a1;
    *v7 = xmmword_1800AB340;
    v7[1] = xmmword_1800AB350;
  }
  else
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 11, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids);
    return GetLastError();
  }
  return v6;
}

```

## disassembly

```asm
0x18002d9f8  mov     [rsp-18h+arg_10], rbx
0x18002d9fd  mov     [rsp-18h+arg_18], rsi
0x18002da02  push    rbp
0x18002da03  push    rdi
0x18002da04  push    r14
0x18002da06  mov     rbp, rsp
0x18002da09  sub     rsp, 60h
0x18002da0d  mov     rax, cs:__security_cookie
0x18002da14  xor     rax, rsp
0x18002da17  mov     [rbp+var_8], rax
0x18002da1b  mov     r14, rdx
0x18002da1e  mov     [rbp+cbData], 0
0x18002da25  mov     rsi, rcx
0x18002da28  mov     [rbp+Type], 7
0x18002da2f  lea     rax, [rbp+hKey]
0x18002da33  mov     [rbp+hKey], 0
0x18002da3b  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18002da42  mov     [rsp+60h+phkResult], rax; phkResult
0x18002da47  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002da4e  mov     [rbp+var_28], 0
0x18002da56  mov     r9d, 1; samDesired
0x18002da5c  mov     [rbp+var_30], 0
0x18002da63  xor     r8d, r8d; ulOptions
0x18002da66  call    cs:__imp_RegOpenKeyExA
0x18002da6c  mov     ebx, eax
0x18002da6e  test    eax, eax
0x18002da70  jnz     loc_18002DB51
0x18002da76  mov     rcx, [rbp+hKey]; hKey
0x18002da7a  lea     rax, [rbp+cbData]
0x18002da7e  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002da83  lea     r9, [rbp+Type]; lpType
0x18002da87  xor     r8d, r8d; lpReserved
0x18002da8a  mov     [rsp+60h+phkResult], 0; lpData
0x18002da93  lea     rdx, aRegistrationre; "RegistrationRetryTimer"
0x18002da9a  call    cs:__imp_RegQueryValueExA
0x18002daa0  mov     ebx, eax
0x18002daa2  test    eax, eax
0x18002daa4  jnz     loc_18002DB51
0x18002daaa  cmp     [rbp+Type], 7
0x18002daae  jnz     short loc_18002DB2C
0x18002dab0  mov     ecx, [rbp+cbData]
0x18002dab3  call    Dns_Allocate
0x18002dab8  mov     rdi, rax
0x18002dabb  test    rax, rax
0x18002dabe  jnz     short loc_18002DAC8
0x18002dac0  lea     ebx, [rax+0Eh]
0x18002dac3  jmp     loc_18002DB51
0x18002dac8  mov     rcx, [rbp+hKey]; hKey
0x18002dacc  lea     rax, [rbp+cbData]
0x18002dad0  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002dad5  lea     r9, [rbp+Type]; lpType
0x18002dad9  xor     r8d, r8d; lpReserved
0x18002dadc  mov     [rsp+60h+phkResult], rdi; lpData
0x18002dae1  lea     rdx, aRegistrationre; "RegistrationRetryTimer"
0x18002dae8  call    cs:__imp_RegQueryValueExA
0x18002daee  mov     ebx, eax
0x18002daf0  test    eax, eax
0x18002daf2  jnz     short loc_18002DB22
0x18002daf4  lea     r9, [rbp+var_30]
0x18002daf8  mov     rcx, rdi; String
0x18002dafb  lea     r8, [rbp+var_28]
0x18002daff  call    Dns_CreateDwordArrayFromMultiSz
0x18002db04  mov     ebx, eax
0x18002db06  test    eax, eax
0x18002db08  jnz     short loc_18002DB22
0x18002db0a  mov     rax, [rbp+var_28]
0x18002db0e  mov     ecx, [rax]
0x18002db10  cmp     [rbp+var_30], ecx
0x18002db13  ja      short loc_18002DB1C
0x18002db15  mov     ebx, 57h ; 'W'
0x18002db1a  jmp     short loc_18002DB22
0x18002db1c  mov     [r14], ecx
0x18002db1f  mov     [rsi], rax
0x18002db22  mov     rcx, rdi; void *
0x18002db25  call    MIDL_user_free
0x18002db2a  jmp     short loc_18002DB51
0x18002db2c  mov     ebx, 57h ; 'W'
0x18002db31  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002db38  jz      short loc_18002DB51
0x18002db3a  lea     edx, [rbx-4Dh]
0x18002db3d  mov     ecx, 40Bh
0x18002db42  mov     r9d, ebx
0x18002db45  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002db4c  call    WPP_SF_d
0x18002db51  mov     rcx, [rbp+hKey]; hKey
0x18002db55  test    rcx, rcx
0x18002db58  jz      short loc_18002DB60
0x18002db5a  call    cs:__imp_RegCloseKey
0x18002db60  test    ebx, ebx
0x18002db62  jz      short loc_18002DBC2
0x18002db64  mov     ecx, 20h ; ' '
0x18002db69  call    Dns_Allocate
0x18002db6e  mov     [rsi], rax
0x18002db71  test    rax, rax
0x18002db74  jz      short loc_18002DB9B
0x18002db76  mov     eax, dword ptr cs:xmmword_1800AB340
0x18002db7c  xor     ebx, ebx
0x18002db7e  mov     [r14], eax
0x18002db81  mov     rax, [rsi]
0x18002db84  movups  xmm0, cs:xmmword_1800AB340
0x18002db8b  movups  xmmword ptr [rax], xmm0
0x18002db8e  movups  xmm1, cs:xmmword_1800AB350
0x18002db95  movups  xmmword ptr [rax+10h], xmm1
0x18002db99  jmp     short loc_18002DBC2
0x18002db9b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002dba2  jz      short loc_18002DBBA
0x18002dba4  mov     edx, 0Bh
0x18002dba9  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002dbb0  mov     ecx, 40Bh
0x18002dbb5  call    WPP_SF_
0x18002dbba  call    cs:__imp_GetLastError
0x18002dbc0  mov     ebx, eax
0x18002dbc2  mov     eax, ebx
0x18002dbc4  mov     rcx, [rbp+var_8]
0x18002dbc8  xor     rcx, rsp; StackCookie
0x18002dbcb  call    __security_check_cookie
0x18002dbd0  lea     r11, [rsp+60h+var_s0]
0x18002dbd5  mov     rbx, [r11+30h]
0x18002dbd9  mov     rsi, [r11+38h]
0x18002dbdd  mov     rsp, r11
0x18002dbe0  pop     r14
0x18002dbe2  pop     rdi
0x18002dbe3  pop     rbp
0x18002dbe4  retn
```
