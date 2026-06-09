# LsaDbRegistryWatch(void *)

- ea: `0x180035280`
- end: `0x180035353`
- name: `?LsaDbRegistryWatch@@YAKPEAX@Z`
- size: `211`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003535c`

## callees

- `0x180035280`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035319`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035319`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800352b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800352b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800352f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800352f0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180035340`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180035340`

## pseudocode

```c
__int64 __fastcall LsaDbRegistryWatch(void *a1)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"EnablePDCTrustScanner", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      LsaDbEnablePDCTrustScanner = 1;
    else
      LsaDbEnablePDCTrustScanner = Data;
    RegCloseKey(hKey);
  }
  RegNotifyChangeKeyValue(LsaDbRegistryWatchKey, 1, 0x10000005u, LsaDbRegistryWatchEvent, 1);
  return 0;
}

```

## disassembly

```asm
0x180035280  mov     [rsp-8+arg_0], rsi
0x180035285  push    rbp
0x180035286  mov     rbp, rsp
0x180035289  sub     rsp, 40h
0x18003528d  lea     rax, [rbp+hKey]
0x180035291  mov     [rbp+hKey], 0
0x180035299  mov     r9d, 20019h; samDesired
0x18003529f  mov     [rsp+40h+phkResult], rax; phkResult
0x1800352a4  xor     r8d, r8d; ulOptions
0x1800352a7  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"
0x1800352ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800352b5  call    cs:__imp_RegOpenKeyExW
0x1800352bb  test    eax, eax
0x1800352bd  jnz     short loc_18003531F
0x1800352bf  mov     rcx, [rbp+hKey]; hKey
0x1800352c3  lea     r9, [rbp+Type]; lpType
0x1800352c7  mov     [rbp+Type], eax
0x1800352ca  lea     rdx, ValueName; "EnablePDCTrustScanner"
0x1800352d1  mov     [rbp+Data], eax
0x1800352d4  xor     r8d, r8d; lpReserved
0x1800352d7  lea     rax, [rbp+cbData]
0x1800352db  mov     [rbp+cbData], 4
0x1800352e2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800352e7  lea     rax, [rbp+Data]
0x1800352eb  mov     [rsp+40h+phkResult], rax; lpData
0x1800352f0  call    cs:__imp_RegQueryValueExW
0x1800352f6  test    eax, eax
0x1800352f8  jnz     short loc_18003530B
0x1800352fa  cmp     [rbp+Type], 4
0x1800352fe  jnz     short loc_18003530B
0x180035300  mov     eax, [rbp+Data]
0x180035303  mov     cs:?LsaDbEnablePDCTrustScanner@@3KA, eax; ulong LsaDbEnablePDCTrustScanner
0x180035309  jmp     short loc_180035315
0x18003530b  mov     cs:?LsaDbEnablePDCTrustScanner@@3KA, 1; ulong LsaDbEnablePDCTrustScanner
0x180035315  mov     rcx, [rbp+hKey]; hKey
0x180035319  call    cs:__imp_RegCloseKey
0x18003531f  mov     r9, cs:?LsaDbRegistryWatchEvent@@3PEAXEA; hEvent
0x180035326  mov     edx, 1; bWatchSubtree
0x18003532b  mov     rcx, cs:?LsaDbRegistryWatchKey@@3PEAUHKEY__@@EA; hKey
0x180035332  mov     r8d, 10000005h; dwNotifyFilter
0x180035338  mov     dword ptr [rsp+40h+phkResult], 1; fAsynchronous
0x180035340  call    cs:__imp_RegNotifyChangeKeyValue
0x180035346  mov     rsi, [rsp+40h+arg_0]
0x18003534b  xor     eax, eax
0x18003534d  add     rsp, 40h
0x180035351  pop     rbp
0x180035352  retn
```
