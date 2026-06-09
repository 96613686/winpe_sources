# DhcpRecreateWcosKeys

- ea: `0x18002a274`
- end: `0x18002a3a2`
- name: `DhcpRecreateWcosKeys`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017438`

## callees

- `0x18002a274`
- `0x1800337d0`
- `0x180033970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a2e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a2e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a374`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a374`

## pseudocode

```c
LSTATUS DhcpRecreateWcosKeys()
{
  __int64 v0; // rdi
  __int64 v1; // rbx
  LSTATUS result; // eax
  HKEY v3; // rcx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v0 = 0;
  dwDisposition = 0;
  v1 = 0;
  hKey = 0;
  do
  {
    result = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               (&off_1800374B0)[v1],
               0,
               0,
               *((_DWORD *)&off_1800374B0 + 2 * v1 + 2) != 0,
               0xF003Fu,
               0,
               &hKey,
               &dwDisposition);
    if ( result && (xmmword_1800423E0 & 2) != 0 )
      result = WPP_SF_SD(
                 1025,
                 60,
                 (unsigned int)WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids,
                 (unsigned int)(&off_1800374B0)[v1],
                 result);
    if ( dwDisposition == 2 && (xmmword_1800423E0 & 0x10) != 0 )
      result = WPP_SF_S(1028, 61, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, (&off_1800374B0)[v1]);
    v3 = hKey;
    if ( hKey )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        WPP_SF_S(1028, 62, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, (&off_1800374B0)[v1]);
        v3 = hKey;
      }
      result = RegCloseKey(v3);
    }
    ++v0;
    v1 += 2;
  }
  while ( v0 != 5 );
  return result;
}

```

## disassembly

```asm
0x18002a274  mov     rax, rsp
0x18002a277  mov     [rax+18h], rbx
0x18002a27b  mov     [rax+20h], rbp
0x18002a27f  push    rdi
0x18002a280  sub     rsp, 50h
0x18002a284  xor     edi, edi
0x18002a286  mov     dword ptr [rax+8], 0
0x18002a28d  xor     ebx, ebx
0x18002a28f  mov     qword ptr [rax+10h], 0
0x18002a297  lea     rbp, off_1800374B0; "System\\CurrentControlSet\\Services\\Tc"...
0x18002a29e  mov     rdx, [rbx+rbp]; lpSubKey
0x18002a2a2  lea     rcx, [rsp+58h+dwDisposition]
0x18002a2a7  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18002a2ac  xor     eax, eax
0x18002a2ae  cmp     [rbx+rbp+8], eax
0x18002a2b2  lea     rcx, [rsp+58h+hKey]
0x18002a2b7  mov     [rsp+58h+phkResult], rcx; phkResult
0x18002a2bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a2c3  setnz   al
0x18002a2c6  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002a2cf  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18002a2d7  xor     r9d, r9d; lpClass
0x18002a2da  xor     r8d, r8d; Reserved
0x18002a2dd  mov     [rsp+58h+dwOptions], eax; dwOptions
0x18002a2e1  call    cs:__imp_RegCreateKeyExW
0x18002a2e8  nop     dword ptr [rax+rax+00h]
0x18002a2ed  test    eax, eax
0x18002a2ef  jz      short loc_18002A318
0x18002a2f1  test    byte ptr cs:xmmword_1800423E0, 2
0x18002a2f8  jz      short loc_18002A318
0x18002a2fa  mov     r9, [rbx+rbp]
0x18002a2fe  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18002a305  mov     edx, 3Ch ; '<'
0x18002a30a  mov     [rsp+58h+dwOptions], eax
0x18002a30e  mov     ecx, 401h
0x18002a313  call    WPP_SF_SD
0x18002a318  cmp     [rsp+58h+dwDisposition], 2
0x18002a31d  jnz     short loc_18002A342
0x18002a31f  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002a326  jz      short loc_18002A342
0x18002a328  mov     r9, [rbx+rbp]
0x18002a32c  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18002a333  mov     edx, 3Dh ; '='
0x18002a338  mov     ecx, 404h
0x18002a33d  call    WPP_SF_S
0x18002a342  mov     rcx, [rsp+58h+hKey]
0x18002a347  test    rcx, rcx
0x18002a34a  jz      short loc_18002A380
0x18002a34c  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002a353  jz      short loc_18002A374
0x18002a355  mov     r9, [rbx+rbp]
0x18002a359  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18002a360  mov     edx, 3Eh ; '>'
0x18002a365  mov     ecx, 404h
0x18002a36a  call    WPP_SF_S
0x18002a36f  mov     rcx, [rsp+58h+hKey]; hKey
0x18002a374  call    cs:__imp_RegCloseKey
0x18002a37b  nop     dword ptr [rax+rax+00h]
0x18002a380  inc     rdi
0x18002a383  add     rbx, 10h
0x18002a387  cmp     rdi, 5
0x18002a38b  jnz     loc_18002A29E
0x18002a391  mov     rbx, [rsp+58h+arg_10]
0x18002a396  mov     rbp, [rsp+58h+arg_18]
0x18002a39b  add     rsp, 50h
0x18002a39f  pop     rdi
0x18002a3a0  retn
```
