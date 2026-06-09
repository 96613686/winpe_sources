# IpTlsSetActiveProfileGuid

- ea: `0x180068750`
- end: `0x180068871`
- name: `IpTlsSetActiveProfileGuid`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800614b8`

## callees

- `0x18000d7c0`
- `0x18004b5f0`
- `0x180068750`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006883d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006883d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800687cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800687cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068825`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068825`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180068783`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180068783`

## string_xrefs

- `0x1800687e8`: `RegOpenKeyEx: Key = %s: Status = %d`
- `0x1800687be`: `SYSTEM\CurrentControlSet\Services\IPHLPSVC\Parameters`
- `0x1800687e1`: `SYSTEM\CurrentControlSet\Services\IPHLPSVC\Parameters`

## pseudocode

```c
__int64 __fastcall IpTlsSetActiveProfileGuid(__int64 a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdi
  unsigned int v3; // eax
  HKEY hKey; // [rsp+30h] [rbp-78h] BYREF
  _WORD Data[40]; // [rsp+40h] [rbp-68h] BYREF

  hKey = 0;
  v1 = ConvertGuidToStringW(a1, Data, 39);
  if ( !v1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( Data[v2] );
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\IPHLPSVC\\Parameters",
           0,
           0x20006u,
           &hKey);
    v1 = v3;
    if ( v3 )
      EventWrite0(
        0x10000000,
        L"RegOpenKeyEx: Key = %s: Status = %d",
        L"SYSTEM\\CurrentControlSet\\Services\\IPHLPSVC\\Parameters",
        v3);
    else
      v1 = RegSetValueExW(hKey, L"IPHTTPSActiveProfile", 0, 1u, (const BYTE *)Data, 2 * v2 + 2);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180068750  mov     r11, rsp
0x180068753  mov     [r11+10h], rbx
0x180068757  mov     [r11+18h], rsi
0x18006875b  push    rdi
0x18006875c  sub     rsp, 0A0h
0x180068763  mov     rax, cs:__security_cookie
0x18006876a  xor     rax, rsp
0x18006876d  mov     [rsp+0A8h+var_18], rax
0x180068775  xor     esi, esi
0x180068777  lea     rdx, [r11-68h]
0x18006877b  mov     [r11-78h], rsi
0x18006877f  lea     r8d, [rsi+27h]
0x180068783  call    cs:__imp_ConvertGuidToStringW
0x18006878a  nop     dword ptr [rax+rax+00h]
0x18006878f  mov     ebx, eax
0x180068791  test    eax, eax
0x180068793  jnz     loc_180068833
0x180068799  lea     rax, [rsp+0A8h+Data]
0x18006879e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800687a2  inc     rdi
0x1800687a5  cmp     [rax+rdi*2], si
0x1800687a9  jnz     short loc_1800687A2
0x1800687ab  lea     rax, [rsp+0A8h+hKey]
0x1800687b0  mov     r9d, 20006h; samDesired
0x1800687b6  xor     r8d, r8d; ulOptions
0x1800687b9  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800687be  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\IP"...
0x1800687c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800687cc  call    cs:__imp_RegOpenKeyExW
0x1800687d3  nop     dword ptr [rax+rax+00h]
0x1800687d8  mov     ebx, eax
0x1800687da  test    eax, eax
0x1800687dc  jz      short loc_1800687FB
0x1800687de  mov     r9d, eax
0x1800687e1  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\IP"...
0x1800687e8  lea     rdx, aRegopenkeyexKe; "RegOpenKeyEx: Key = %s: Status = %d"
0x1800687ef  mov     ecx, 10000000h
0x1800687f4  call    EventWrite0
0x1800687f9  jmp     short loc_180068833
0x1800687fb  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180068800  lea     eax, ds:2[rdi*2]
0x180068807  mov     [rsp+0A8h+cbData], eax; cbData
0x18006880b  lea     rdx, aIphttpsactivep; "IPHTTPSActiveProfile"
0x180068812  lea     rax, [rsp+0A8h+Data]
0x180068817  mov     r9d, 1; dwType
0x18006881d  xor     r8d, r8d; Reserved
0x180068820  mov     [rsp+0A8h+phkResult], rax; lpData
0x180068825  call    cs:__imp_RegSetValueExW
0x18006882c  nop     dword ptr [rax+rax+00h]
0x180068831  mov     ebx, eax
0x180068833  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180068838  test    rcx, rcx
0x18006883b  jz      short loc_180068849
0x18006883d  call    cs:__imp_RegCloseKey
0x180068844  nop     dword ptr [rax+rax+00h]
0x180068849  mov     eax, ebx
0x18006884b  mov     rcx, [rsp+0A8h+var_18]
0x180068853  xor     rcx, rsp; StackCookie
0x180068856  call    __security_check_cookie
0x18006885b  lea     r11, [rsp+0A8h+var_8]
0x180068863  mov     rbx, [r11+18h]
0x180068867  mov     rsi, [r11+20h]
0x18006886b  mov     rsp, r11
0x18006886e  pop     rdi
0x18006886f  retn
```
