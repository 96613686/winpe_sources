# InitializeDCPTMonitoring

- ea: `0x18003ebb8`
- end: `0x18003ed1b`
- name: `InitializeDCPTMonitoring`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002c980`

## callees

- `0x180008b00`
- `0x18002039c`
- `0x18003ebb8`
- `0x180046ec0`
- `0x180047818`
- `0x18004cc80`
- `0x180086384`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eca5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003ecc2`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003ecc2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ec92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ec92`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18003ec52`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18003ec52`

## string_xrefs

- `0x18003ec0e`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18003ec15`: `Dnscache`
- `0x18003ec03`: `Parameters\DnsPolicyConfig`

## pseudocode

```c
__int64 InitializeDCPTMonitoring()
{
  void *v0; // rdi
  int PersistedRegistryLocation; // eax
  int v2; // eax
  DWORD v3; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 result; // rax
  HANDLE v7; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[528]; // [rsp+40h] [rbp-C0h] BYREF

  v0 = 0;
  memset_0(v9, 0, 0x20Au);
  hKey = 0;
  PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                L"Dnscache",
                                L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                L"Parameters\\DnsPolicyConfig",
                                v9,
                                522);
  if ( PersistedRegistryLocation >= 0 )
    v2 = RegOpenKeyExInternalW(-2147483646, v9, 0, 131097, &hKey, 0);
  else
    v2 = WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
  if ( v2 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SD(1035, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v9, v2);
    v3 = 0;
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v7 = EventW;
    v0 = EventW;
    if ( EventW )
      LastError = RegNotifyChangeKeyValue(hKey, 1, 5u, EventW, 1);
    else
      LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      CleanupDCPTMonitoring(&hKey, &v7);
      v0 = v7;
    }
  }
  g_hDCPTKey = hKey;
  result = v3;
  g_hDCPTChange = v0;
  return result;
}

```

## disassembly

```asm
0x18003ebb8  mov     [rsp-8+arg_0], rbx
0x18003ebbd  mov     [rsp-8+arg_8], rdi
0x18003ebc2  push    rbp
0x18003ebc3  lea     rbp, [rsp-160h]
0x18003ebcb  sub     rsp, 260h
0x18003ebd2  mov     rax, cs:__security_cookie
0x18003ebd9  xor     rax, rsp
0x18003ebdc  mov     [rbp+160h+var_10], rax
0x18003ebe3  mov     ebx, 20Ah
0x18003ebe8  lea     rcx, [rsp+260h+var_220]; void *
0x18003ebed  mov     r8d, ebx; Size
0x18003ebf0  xor     edx, edx; Val
0x18003ebf2  xor     edi, edi
0x18003ebf4  call    memset_0
0x18003ebf9  lea     r9, [rsp+260h+var_220]
0x18003ebfe  mov     [rsp+260h+hKey], rdi
0x18003ec03  lea     r8, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x18003ec0a  mov     [rsp+260h+fAsynchronous], ebx
0x18003ec0e  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18003ec15  lea     rcx, aDnscache_0; "Dnscache"
0x18003ec1c  call    WxGetPersistedRegistryLocation
0x18003ec21  test    eax, eax
0x18003ec23  jns     short loc_18003EC2E
0x18003ec25  mov     ecx, eax
0x18003ec27  call    WX_WIN32_FROM_HR
0x18003ec2c  jmp     short loc_18003EC58
0x18003ec2e  lea     rax, [rsp+260h+hKey]
0x18003ec33  mov     [rsp+260h+var_238], rdi
0x18003ec38  mov     r9d, 20019h
0x18003ec3e  mov     qword ptr [rsp+260h+fAsynchronous], rax
0x18003ec43  xor     r8d, r8d
0x18003ec46  lea     rdx, [rsp+260h+var_220]
0x18003ec4b  mov     rcx, 0FFFFFFFF80000002h
0x18003ec52  call    cs:__imp_RegOpenKeyExInternalW
0x18003ec58  test    eax, eax
0x18003ec5a  jz      short loc_18003EC88
0x18003ec5c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003ec63  jz      short loc_18003EC84
0x18003ec65  mov     edx, 0Ah
0x18003ec6a  mov     [rsp+260h+fAsynchronous], eax
0x18003ec6e  mov     ecx, 40Bh
0x18003ec73  lea     r9, [rsp+260h+var_220]
0x18003ec78  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x18003ec7f  call    WPP_SF_SD
0x18003ec84  xor     ebx, ebx
0x18003ec86  jmp     short loc_18003ECE2
0x18003ec88  xor     r9d, r9d; lpName
0x18003ec8b  xor     r8d, r8d; bInitialState
0x18003ec8e  xor     edx, edx; bManualReset
0x18003ec90  xor     ecx, ecx; lpEventAttributes
0x18003ec92  call    cs:__imp_CreateEventW
0x18003ec98  mov     [rsp+260h+var_230], rax
0x18003ec9d  mov     rdi, rax
0x18003eca0  test    rax, rax
0x18003eca3  jnz     short loc_18003ECAD
0x18003eca5  call    cs:__imp_GetLastError
0x18003ecab  jmp     short loc_18003ECC8
0x18003ecad  mov     rcx, [rsp+260h+hKey]; hKey
0x18003ecb2  mov     edx, 1; bWatchSubtree
0x18003ecb7  mov     r9, rax; hEvent
0x18003ecba  mov     [rsp+260h+fAsynchronous], edx; fAsynchronous
0x18003ecbe  lea     r8d, [rdx+4]; dwNotifyFilter
0x18003ecc2  call    cs:__imp_RegNotifyChangeKeyValue
0x18003ecc8  mov     ebx, eax
0x18003ecca  test    eax, eax
0x18003eccc  jz      short loc_18003ECE2
0x18003ecce  lea     rdx, [rsp+260h+var_230]
0x18003ecd3  lea     rcx, [rsp+260h+hKey]
0x18003ecd8  call    CleanupDCPTMonitoring
0x18003ecdd  mov     rdi, [rsp+260h+var_230]
0x18003ece2  mov     rax, [rsp+260h+hKey]
0x18003ece7  mov     cs:g_hDCPTKey, rax
0x18003ecee  mov     eax, ebx
0x18003ecf0  mov     cs:g_hDCPTChange, rdi
0x18003ecf7  mov     rcx, [rbp+160h+var_10]
0x18003ecfe  xor     rcx, rsp; StackCookie
0x18003ed01  call    __security_check_cookie
0x18003ed06  lea     r11, [rsp+260h+var_s0]
0x18003ed0e  mov     rbx, [r11+10h]
0x18003ed12  mov     rdi, [r11+18h]
0x18003ed16  mov     rsp, r11
0x18003ed19  pop     rbp
0x18003ed1a  retn
```
