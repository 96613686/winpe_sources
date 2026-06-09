# hijackStoreRemove

- ea: `0x1800277c0`
- end: `0x1800278f1`
- name: `hijackStoreRemove`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180025728`
- `0x18003064c`

## callees

- `0x180008b00`
- `0x18002039c`
- `0x1800277c0`
- `0x180027900`
- `0x180046ec0`
- `0x180047818`
- `0x180086384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800278d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800278d0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800278b3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800278b3`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18002786c`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18002786c`

## string_xrefs

- `0x180027825`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18002782c`: `Dnscache`

## pseudocode

```c
__int64 __fastcall hijackStoreRemove(__int64 a1)
{
  unsigned int v1; // ebx
  int PersistedRegistryLocation; // eax
  int v3; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-2D8h] BYREF
  WCHAR SubKey[80]; // [rsp+40h] [rbp-2C8h] BYREF
  _BYTE v7[528]; // [rsp+E0h] [rbp-228h] BYREF

  v1 = 0;
  hKey[0] = 0;
  if ( (unsigned int)Dns_GuidToString(a1, SubKey) )
  {
    memset_0(v7, 0, 0x20Au);
    hKey[0] = 0;
    PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                  L"Dnscache",
                                  L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                  L"Parameters\\Probe",
                                  v7,
                                  522);
    if ( PersistedRegistryLocation >= 0 )
      v3 = RegOpenKeyExInternalW(-2147483646, v7, 0, 983103, hKey, 0);
    else
      v3 = WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
    if ( v3 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SD(1035, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v7, v3);
    }
    else if ( (RegDeleteKeyExW(hKey[0], SubKey, 0, 0) & 0xFFFFFFFD) == 0 )
    {
      v1 = 1;
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v1;
}

```

## disassembly

```asm
0x1800277c0  push    rbx
0x1800277c2  sub     rsp, 300h
0x1800277c9  mov     rax, cs:__security_cookie
0x1800277d0  xor     rax, rsp
0x1800277d3  mov     [rsp+308h+var_18], rax
0x1800277db  xor     ebx, ebx
0x1800277dd  lea     rdx, [rsp+308h+SubKey]
0x1800277e2  mov     [rsp+308h+hKey], rbx
0x1800277e7  call    Dns_GuidToString
0x1800277ec  test    eax, eax
0x1800277ee  jz      loc_1800278C6
0x1800277f4  xor     edx, edx; Val
0x1800277f6  lea     rcx, [rsp+308h+var_228]; void *
0x1800277fe  mov     r8d, 20Ah; Size
0x180027804  call    memset_0
0x180027809  lea     r9, [rsp+308h+var_228]
0x180027811  mov     [rsp+308h+hKey], rbx
0x180027816  lea     r8, aParametersProb; "Parameters\\Probe"
0x18002781d  mov     dword ptr [rsp+308h+var_2E8], 20Ah
0x180027825  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18002782c  lea     rcx, aDnscache_0; "Dnscache"
0x180027833  call    WxGetPersistedRegistryLocation
0x180027838  test    eax, eax
0x18002783a  jns     short loc_180027845
0x18002783c  mov     ecx, eax
0x18002783e  call    WX_WIN32_FROM_HR
0x180027843  jmp     short loc_180027872
0x180027845  lea     rax, [rsp+308h+hKey]
0x18002784a  mov     [rsp+308h+var_2E0], rbx
0x18002784f  mov     r9d, 0F003Fh
0x180027855  mov     [rsp+308h+var_2E8], rax
0x18002785a  xor     r8d, r8d
0x18002785d  lea     rdx, [rsp+308h+var_228]
0x180027865  mov     rcx, 0FFFFFFFF80000002h
0x18002786c  call    cs:__imp_RegOpenKeyExInternalW
0x180027872  test    eax, eax
0x180027874  jz      short loc_1800278A3
0x180027876  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002787d  jz      short loc_1800278C6
0x18002787f  mov     edx, 0Ah
0x180027884  mov     dword ptr [rsp+308h+var_2E8], eax
0x180027888  mov     ecx, 40Bh
0x18002788d  lea     r9, [rsp+308h+var_228]
0x180027895  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x18002789c  call    WPP_SF_SD
0x1800278a1  jmp     short loc_1800278C6
0x1800278a3  mov     rcx, [rsp+308h+hKey]; hKey
0x1800278a8  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x1800278ad  xor     r9d, r9d; Reserved
0x1800278b0  xor     r8d, r8d; samDesired
0x1800278b3  call    cs:__imp_RegDeleteKeyExW
0x1800278b9  test    eax, 0FFFFFFFDh
0x1800278be  mov     eax, 1
0x1800278c3  cmovz   ebx, eax
0x1800278c6  mov     rcx, [rsp+308h+hKey]; hKey
0x1800278cb  test    rcx, rcx
0x1800278ce  jz      short loc_1800278D6
0x1800278d0  call    cs:__imp_RegCloseKey
0x1800278d6  mov     eax, ebx
0x1800278d8  mov     rcx, [rsp+308h+var_18]
0x1800278e0  xor     rcx, rsp; StackCookie
0x1800278e3  call    __security_check_cookie
0x1800278e8  add     rsp, 300h
0x1800278ef  pop     rbx
0x1800278f0  retn
```
