# KerbHandleOfflineDomainJoin(void)

- ea: `0x18007d200`
- end: `0x18007d2c5`
- name: `?KerbHandleOfflineDomainJoin@@YAXXZ`
- size: `197`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18007e200`

## callees

- `0x18007d200`
- `0x1800917d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d2a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d2a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d24a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d280`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d24a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d280`
- `ntdll!RtlReleaseResource` at `0x18007d2ae`
- `ntdll!RtlReleaseResource` at `0x18007d2ae`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007d21a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007d21a`

## pseudocode

```c
void KerbHandleOfflineDomainJoin(void)
{
  char v0; // bl
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = 0;
  RtlAcquireResourceExclusive(&KerberosGlobalResource, 1u);
  if ( KerbGlobalODJState == 2
    && !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\LSA\\OfflineJoinFinalized",
          0,
          0x20019u,
          &hKey) )
  {
    RegCloseKey(hKey);
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\LSA\\OfflineJoin", 0, 0x20019u, &hKey) == 2 )
    {
      KerbGlobalODJState = 0;
      v0 = 1;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  RtlReleaseResource(&KerberosGlobalResource);
  if ( v0 )
    KerbSetKdcData(1u);
}

```

## disassembly

```asm
0x18007d200  push    rbx
0x18007d202  sub     rsp, 30h
0x18007d206  mov     dl, 1; Wait
0x18007d208  mov     [rsp+38h+hKey], 0
0x18007d211  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x18007d218  xor     bl, bl
0x18007d21a  call    cs:__imp_RtlAcquireResourceExclusive
0x18007d220  cmp     cs:?KerbGlobalODJState@@3KA, 2; ulong KerbGlobalODJState
0x18007d227  jnz     short loc_18007D297
0x18007d229  lea     rax, [rsp+38h+hKey]
0x18007d22e  mov     r9d, 20019h; samDesired
0x18007d234  xor     r8d, r8d; ulOptions
0x18007d237  mov     [rsp+38h+phkResult], rax; phkResult
0x18007d23c  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\LSA"...
0x18007d243  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d24a  call    cs:__imp_RegOpenKeyExW
0x18007d250  test    eax, eax
0x18007d252  jnz     short loc_18007D297
0x18007d254  mov     rcx, [rsp+38h+hKey]; hKey
0x18007d259  call    cs:__imp_RegCloseKey
0x18007d25f  lea     rax, [rsp+38h+hKey]
0x18007d264  mov     r9d, 20019h; samDesired
0x18007d26a  xor     r8d, r8d; ulOptions
0x18007d26d  mov     [rsp+38h+phkResult], rax; phkResult
0x18007d272  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Control\\LSA"...
0x18007d279  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d280  call    cs:__imp_RegOpenKeyExW
0x18007d286  cmp     eax, 2
0x18007d289  jnz     short loc_18007D297
0x18007d28b  mov     cs:?KerbGlobalODJState@@3KA, 0; ulong KerbGlobalODJState
0x18007d295  mov     bl, 1
0x18007d297  mov     rcx, [rsp+38h+hKey]; hKey
0x18007d29c  test    rcx, rcx
0x18007d29f  jz      short loc_18007D2A7
0x18007d2a1  call    cs:__imp_RegCloseKey
0x18007d2a7  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x18007d2ae  call    cs:__imp_RtlReleaseResource
0x18007d2b4  test    bl, bl
0x18007d2b6  jz      short loc_18007D2BF
0x18007d2b8  mov     cl, 1; unsigned __int8
0x18007d2ba  call    ?KerbSetKdcData@@YAXE@Z; KerbSetKdcData(uchar)
0x18007d2bf  add     rsp, 30h
0x18007d2c3  pop     rbx
0x18007d2c4  retn
```
