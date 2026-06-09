# _TraceLoggingThrottleCheck

- ea: `0x180068940`
- end: `0x180068afb`
- name: `_TraceLoggingThrottleCheck`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180067020`

## callees

- `0x180033690`
- `0x1800336b8`
- `0x18005d484`
- `0x180068940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068acd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068acd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180068a85`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180068a85`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800689ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068a42`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800689ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068a42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068adc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068aeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068adc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068aeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180068962`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180068962`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x180068995`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x180068995`

## pseudocode

```c
char TraceLoggingThrottleCheck()
{
  ULONGLONG TickCount64; // rax
  char v1; // bl
  int AppContainerRegistryHandle; // eax
  LSTATUS v3; // edi
  HKEY v5; // [rsp+50h] [rbp-20h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-18h] BYREF
  BYTE v7[16]; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+28h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+38h] BYREF

  phkResult = 0;
  v5 = 0;
  dwDisposition = 0;
  TickCount64 = GetTickCount64();
  hKey = 0;
  *(_QWORD *)v7 = TickCount64;
  v1 = 1;
  phkResult = 0;
  if ( (unsigned int)I_CryptIsAppContainerToken(0) )
    AppContainerRegistryHandle = GetAppContainerRegistryHandle(131097, &hKey);
  else
    AppContainerRegistryHandle = RegOpenHKCUEx(&hKey);
  if ( !AppContainerRegistryHandle )
  {
    v3 = RegCreateKeyExW(hKey, L"Software\\Microsoft", 0, 0, 0, 0x2011Fu, 0, &phkResult, &dwDisposition);
    if ( hKey )
      RegCloseHKCU(hKey);
    if ( !v3 && !RegCreateKeyExW(phkResult, L"CertSelect", 0, 0, 1u, 0x2011Fu, 0, &v5, &dwDisposition) )
    {
      Type = 0;
      LODWORD(hKey) = 8;
      *(_QWORD *)Data = 0;
      if ( !RegQueryValueExW(v5, L"TickCount", 0, &Type, Data, (LPDWORD)&hKey)
        && (_DWORD)hKey == 8
        && Type == 11
        && (unsigned __int64)(*(_QWORD *)Data + 3600000LL) > *(_QWORD *)v7 )
      {
        v1 = 0;
      }
      else
      {
        RegSetValueExW(v5, L"TickCount", 0, 0xBu, v7, 8u);
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
    RegCloseKey(v5);
  return v1;
}

```

## disassembly

```asm
0x180068940  push    rbp
0x180068942  push    rbx
0x180068943  push    rdi
0x180068944  mov     rbp, rsp
0x180068947  sub     rsp, 70h
0x18006894b  mov     [rbp+arg_18], 0
0x180068953  mov     [rbp+var_20], 0
0x18006895b  mov     [rbp+dwDisposition], 0
0x180068962  call    cs:__imp_GetTickCount64
0x180068968  xor     ecx, ecx
0x18006896a  mov     [rbp+hKey], 0
0x180068972  mov     qword ptr [rbp+var_10], rax
0x180068976  mov     ebx, 1
0x18006897b  mov     [rbp+arg_18], 0
0x180068983  call    I_CryptIsAppContainerToken
0x180068988  test    eax, eax
0x18006898a  jz      short loc_18006899D
0x18006898c  lea     rdx, [rbp+hKey]
0x180068990  mov     ecx, 20019h
0x180068995  call    cs:__imp_GetAppContainerRegistryHandle
0x18006899b  jmp     short loc_1800689A8
0x18006899d  xor     edx, edx
0x18006899f  lea     rcx, [rbp+hKey]; phkResult
0x1800689a3  call    RegOpenHKCUEx
0x1800689a8  test    eax, eax
0x1800689aa  jnz     loc_180068AD3
0x1800689b0  mov     rcx, [rbp+hKey]; hKey
0x1800689b4  lea     rax, [rbp+dwDisposition]
0x1800689b8  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1800689bd  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft"
0x1800689c4  lea     rax, [rbp+arg_18]
0x1800689c8  xor     r9d, r9d; lpClass
0x1800689cb  mov     [rsp+70h+phkResult], rax; phkResult
0x1800689d0  xor     r8d, r8d; Reserved
0x1800689d3  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800689dc  mov     [rsp+70h+samDesired], 2011Fh; samDesired
0x1800689e4  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1800689ec  call    cs:__imp_RegCreateKeyExW
0x1800689f2  mov     rcx, [rbp+hKey]
0x1800689f6  mov     edi, eax
0x1800689f8  test    rcx, rcx
0x1800689fb  jz      short loc_180068A02
0x1800689fd  call    RegCloseHKCU
0x180068a02  test    edi, edi
0x180068a04  jnz     loc_180068AD3
0x180068a0a  mov     rcx, [rbp+arg_18]; hKey
0x180068a0e  lea     rax, [rbp+dwDisposition]
0x180068a12  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180068a17  lea     rdx, aCertselect; "CertSelect"
0x180068a1e  lea     rax, [rbp+var_20]
0x180068a22  xor     r9d, r9d; lpClass
0x180068a25  mov     [rsp+70h+phkResult], rax; phkResult
0x180068a2a  xor     r8d, r8d; Reserved
0x180068a2d  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180068a36  mov     [rsp+70h+samDesired], 2011Fh; samDesired
0x180068a3e  mov     [rsp+70h+dwOptions], ebx; dwOptions
0x180068a42  call    cs:__imp_RegCreateKeyExW
0x180068a48  test    eax, eax
0x180068a4a  jnz     loc_180068AD3
0x180068a50  mov     rcx, [rbp+var_20]; hKey
0x180068a54  lea     edi, [rax+8]
0x180068a57  mov     [rbp+Type], eax
0x180068a5a  lea     r9, [rbp+Type]; lpType
0x180068a5e  lea     rax, [rbp+hKey]
0x180068a62  mov     dword ptr [rbp+hKey], edi
0x180068a65  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x180068a6a  lea     rdx, aTickcount; "TickCount"
0x180068a71  lea     rax, [rbp+Data]
0x180068a75  mov     qword ptr [rbp+Data], 0
0x180068a7d  xor     r8d, r8d; lpReserved
0x180068a80  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180068a85  call    cs:__imp_RegQueryValueExW
0x180068a8b  lea     r9d, [rdi+3]; dwType
0x180068a8f  test    eax, eax
0x180068a91  jnz     short loc_180068AB2
0x180068a93  cmp     dword ptr [rbp+hKey], edi
0x180068a96  jnz     short loc_180068AB2
0x180068a98  cmp     [rbp+Type], r9d
0x180068a9c  jnz     short loc_180068AB2
0x180068a9e  mov     rax, qword ptr [rbp+Data]
0x180068aa2  add     rax, 36EE80h
0x180068aa8  cmp     rax, qword ptr [rbp+var_10]
0x180068aac  jbe     short loc_180068AB2
0x180068aae  xor     ebx, ebx
0x180068ab0  jmp     short loc_180068AD3
0x180068ab2  mov     rcx, [rbp+var_20]; hKey
0x180068ab6  lea     rax, [rbp+var_10]
0x180068aba  mov     [rsp+70h+samDesired], edi; cbData
0x180068abe  lea     rdx, aTickcount; "TickCount"
0x180068ac5  xor     r8d, r8d; Reserved
0x180068ac8  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180068acd  call    cs:__imp_RegSetValueExW
0x180068ad3  mov     rcx, [rbp+arg_18]; hKey
0x180068ad7  test    rcx, rcx
0x180068ada  jz      short loc_180068AE2
0x180068adc  call    cs:__imp_RegCloseKey
0x180068ae2  mov     rcx, [rbp+var_20]; hKey
0x180068ae6  test    rcx, rcx
0x180068ae9  jz      short loc_180068AF1
0x180068aeb  call    cs:__imp_RegCloseKey
0x180068af1  mov     al, bl
0x180068af3  add     rsp, 70h
0x180068af7  pop     rdi
0x180068af8  pop     rbx
0x180068af9  pop     rbp
0x180068afa  retn
```
