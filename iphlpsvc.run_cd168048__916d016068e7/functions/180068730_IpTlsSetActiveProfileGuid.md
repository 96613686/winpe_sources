# IpTlsSetActiveProfileGuid

- ea: `0x180068730`
- end: `0x180068851`
- name: `IpTlsSetActiveProfileGuid`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180061498`

## callees

- `0x18000d7b0`
- `0x18004b630`
- `0x180068730`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006881d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006881d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800687ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800687ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068805`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068805`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180068763`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180068763`

## string_xrefs

- `0x1800687c8`: `RegOpenKeyEx: Key = %s: Status = %d`
- `0x18006879e`: `SYSTEM\CurrentControlSet\Services\IPHLPSVC\Parameters`
- `0x1800687c1`: `SYSTEM\CurrentControlSet\Services\IPHLPSVC\Parameters`

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
0x180068730  mov     r11, rsp
0x180068733  mov     [r11+10h], rbx
0x180068737  mov     [r11+18h], rsi
0x18006873b  push    rdi
0x18006873c  sub     rsp, 0A0h
0x180068743  mov     rax, cs:__security_cookie
0x18006874a  xor     rax, rsp
0x18006874d  mov     [rsp+0A8h+var_18], rax
0x180068755  xor     esi, esi
0x180068757  lea     rdx, [r11-68h]
0x18006875b  mov     [r11-78h], rsi
0x18006875f  lea     r8d, [rsi+27h]
0x180068763  call    cs:__imp_ConvertGuidToStringW
0x18006876a  nop     dword ptr [rax+rax+00h]
0x18006876f  mov     ebx, eax
0x180068771  test    eax, eax
0x180068773  jnz     loc_180068813
0x180068779  lea     rax, [rsp+0A8h+Data]
0x18006877e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180068782  inc     rdi
0x180068785  cmp     [rax+rdi*2], si
0x180068789  jnz     short loc_180068782
0x18006878b  lea     rax, [rsp+0A8h+hKey]
0x180068790  mov     r9d, 20006h; samDesired
0x180068796  xor     r8d, r8d; ulOptions
0x180068799  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18006879e  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\IP"...
0x1800687a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800687ac  call    cs:__imp_RegOpenKeyExW
0x1800687b3  nop     dword ptr [rax+rax+00h]
0x1800687b8  mov     ebx, eax
0x1800687ba  test    eax, eax
0x1800687bc  jz      short loc_1800687DB
0x1800687be  mov     r9d, eax
0x1800687c1  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\IP"...
0x1800687c8  lea     rdx, aRegopenkeyexKe; "RegOpenKeyEx: Key = %s: Status = %d"
0x1800687cf  mov     ecx, 10000000h
0x1800687d4  call    EventWrite0
0x1800687d9  jmp     short loc_180068813
0x1800687db  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800687e0  lea     eax, ds:2[rdi*2]
0x1800687e7  mov     [rsp+0A8h+cbData], eax; cbData
0x1800687eb  lea     rdx, aIphttpsactivep; "IPHTTPSActiveProfile"
0x1800687f2  lea     rax, [rsp+0A8h+Data]
0x1800687f7  mov     r9d, 1; dwType
0x1800687fd  xor     r8d, r8d; Reserved
0x180068800  mov     [rsp+0A8h+phkResult], rax; lpData
0x180068805  call    cs:__imp_RegSetValueExW
0x18006880c  nop     dword ptr [rax+rax+00h]
0x180068811  mov     ebx, eax
0x180068813  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180068818  test    rcx, rcx
0x18006881b  jz      short loc_180068829
0x18006881d  call    cs:__imp_RegCloseKey
0x180068824  nop     dword ptr [rax+rax+00h]
0x180068829  mov     eax, ebx
0x18006882b  mov     rcx, [rsp+0A8h+var_18]
0x180068833  xor     rcx, rsp; StackCookie
0x180068836  call    __security_check_cookie
0x18006883b  lea     r11, [rsp+0A8h+var_8]
0x180068843  mov     rbx, [r11+18h]
0x180068847  mov     rsi, [r11+20h]
0x18006884b  mov     rsp, r11
0x18006884e  pop     rdi
0x18006884f  retn
```
