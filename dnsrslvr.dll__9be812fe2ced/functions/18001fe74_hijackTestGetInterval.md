# hijackTestGetInterval

- ea: `0x18001fe74`
- end: `0x18001ffef`
- name: `hijackTestGetInterval`
- size: `379`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18003064c`
- `0x18003fe3c`

## callees

- `0x180008b00`
- `0x18001fe74`
- `0x18002039c`
- `0x180046ec0`
- `0x180047818`
- `0x180086384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff75`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ff61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ff61`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18001ff2f`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18001ff2f`

## string_xrefs

- `0x18001fef0`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18001fef7`: `Dnscache`
- `0x18001ff55`: `HijackingProbeCacheSeconds`

## pseudocode

```c
__int64 __fastcall hijackTestGetInterval(_DWORD *a1)
{
  unsigned int v2; // edi
  int PersistedRegistryLocation; // eax
  int v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[528]; // [rsp+50h] [rbp-B0h] BYREF

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData[0] = 4;
  if ( !a1 )
    return 0;
  v2 = 0;
  memset_0(v10, 0, 0x20Au);
  hKey = 0;
  PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                L"Dnscache",
                                L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                L"Parameters",
                                v10,
                                522);
  if ( PersistedRegistryLocation < 0 )
    v4 = WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
  else
    v4 = RegOpenKeyExInternalW(-2147483646, v10, 0, 131097, &hKey, 0);
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SD(1035, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v10, v4);
  }
  else if ( !RegQueryValueExW(hKey, L"HijackingProbeCacheSeconds", 0, &Type, Data, cbData) && Type == 4 )
  {
    v2 = 1;
    *a1 = *(_DWORD *)Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18001fe74  mov     [rsp-8+arg_8], rbx
0x18001fe79  mov     [rsp-8+arg_10], rdi
0x18001fe7e  push    rbp
0x18001fe7f  lea     rbp, [rsp-170h]
0x18001fe87  sub     rsp, 270h
0x18001fe8e  mov     rax, cs:__security_cookie
0x18001fe95  xor     rax, rsp
0x18001fe98  mov     [rbp+170h+var_10], rax
0x18001fe9f  mov     [rsp+270h+Type], 0
0x18001fea7  mov     rbx, rcx
0x18001feaa  mov     dword ptr [rsp+270h+Data], 0
0x18001feb2  mov     [rsp+270h+cbData], 4
0x18001feba  test    rcx, rcx
0x18001febd  jz      loc_18001FFA1
0x18001fec3  xor     edx, edx; Val
0x18001fec5  lea     rcx, [rsp+270h+var_220]; void *
0x18001feca  mov     r8d, 20Ah; Size
0x18001fed0  xor     edi, edi
0x18001fed2  call    memset_0
0x18001fed7  lea     r9, [rsp+270h+var_220]
0x18001fedc  mov     [rsp+270h+hKey], rdi
0x18001fee1  lea     r8, aParameters; "Parameters"
0x18001fee8  mov     dword ptr [rsp+270h+lpData], 20Ah
0x18001fef0  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18001fef7  lea     rcx, aDnscache_0; "Dnscache"
0x18001fefe  call    WxGetPersistedRegistryLocation
0x18001ff03  test    eax, eax
0x18001ff05  js      loc_18001FFA5
0x18001ff0b  lea     rax, [rsp+270h+hKey]
0x18001ff10  mov     [rsp+270h+lpcbData], rdi
0x18001ff15  mov     r9d, 20019h
0x18001ff1b  mov     [rsp+270h+lpData], rax
0x18001ff20  xor     r8d, r8d
0x18001ff23  lea     rdx, [rsp+270h+var_220]
0x18001ff28  mov     rcx, 0FFFFFFFF80000002h
0x18001ff2f  call    cs:__imp_RegOpenKeyExInternalW
0x18001ff35  test    eax, eax
0x18001ff37  jnz     short loc_18001FFAE
0x18001ff39  mov     rcx, [rsp+270h+hKey]; hKey
0x18001ff3e  lea     rax, [rsp+270h+cbData]
0x18001ff43  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18001ff48  lea     r9, [rsp+270h+Type]; lpType
0x18001ff4d  lea     rax, [rsp+270h+Data]
0x18001ff52  xor     r8d, r8d; lpReserved
0x18001ff55  lea     rdx, aHijackingprobe_0; "HijackingProbeCacheSeconds"
0x18001ff5c  mov     [rsp+270h+lpData], rax; lpData
0x18001ff61  call    cs:__imp_RegQueryValueExW
0x18001ff67  test    eax, eax
0x18001ff69  jz      short loc_18001FFD8
0x18001ff6b  mov     rcx, [rsp+270h+hKey]; hKey
0x18001ff70  test    rcx, rcx
0x18001ff73  jz      short loc_18001FF7B
0x18001ff75  call    cs:__imp_RegCloseKey
0x18001ff7b  mov     eax, edi
0x18001ff7d  mov     rcx, [rbp+170h+var_10]
0x18001ff84  xor     rcx, rsp; StackCookie
0x18001ff87  call    __security_check_cookie
0x18001ff8c  lea     r11, [rsp+270h+var_s0]
0x18001ff94  mov     rbx, [r11+18h]
0x18001ff98  mov     rdi, [r11+20h]
0x18001ff9c  mov     rsp, r11
0x18001ff9f  pop     rbp
0x18001ffa0  retn
0x18001ffa1  xor     eax, eax
0x18001ffa3  jmp     short loc_18001FF7D
0x18001ffa5  mov     ecx, eax
0x18001ffa7  call    WX_WIN32_FROM_HR
0x18001ffac  jmp     short loc_18001FF35
0x18001ffae  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001ffb5  jz      short loc_18001FF6B
0x18001ffb7  mov     edx, 0Ah
0x18001ffbc  mov     dword ptr [rsp+270h+lpData], eax
0x18001ffc0  mov     ecx, 40Bh
0x18001ffc5  lea     r9, [rsp+270h+var_220]
0x18001ffca  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x18001ffd1  call    WPP_SF_SD
0x18001ffd6  jmp     short loc_18001FF6B
0x18001ffd8  cmp     [rsp+270h+Type], 4
0x18001ffdd  jnz     short loc_18001FF6B
0x18001ffdf  mov     eax, dword ptr [rsp+270h+Data]
0x18001ffe3  mov     edi, 1
0x18001ffe8  mov     [rbx], eax
0x18001ffea  jmp     loc_18001FF6B
```
