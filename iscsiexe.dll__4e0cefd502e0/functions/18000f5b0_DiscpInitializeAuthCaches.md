# DiscpInitializeAuthCaches

- ea: `0x18000f5b0`
- end: `0x18000f7f1`
- name: `DiscpInitializeAuthCaches`
- size: `577`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f7f8`

## callees

- `0x180001cfe`
- `0x18000f5b0`
- `0x18000fe70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f74c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f74c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000f738`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000f738`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f683`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f6b9`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f683`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f6b9`
- `ISCSIUM!DiscpDecryptBuffer` at `0x18000f725`
- `ISCSIUM!DiscpDecryptBuffer` at `0x18000f725`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x18000f616`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x18000f616`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f790`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f7a4`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f7ad`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f790`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f7a4`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f7ad`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000f70d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000f70d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f777`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f777`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f666`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f7bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f7d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f7bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f7d5`

## string_xrefs

- `0x18000f60b`: `Software\Microsoft\Windows NT\CurrentVersion\iSCSI\Discovery\Authentication Cache`

## pseudocode

```c
__int64 __fastcall DiscpInitializeAuthCaches(__int64 a1)
{
  __int64 v1; // r15
  __int64 v2; // rsi
  unsigned int v4; // ebx
  BYTE *v5; // r14
  DWORD v6; // eax
  unsigned __int64 v7; // rcx
  WCHAR *v8; // rbx
  DWORD i; // edi
  size_t Size; // [rsp+60h] [rbp-9h] BYREF
  DWORD Type; // [rsp+68h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+7h] BYREF
  void *v14; // [rsp+78h] [rbp+Fh] BYREF
  DWORD cbMaxValueNameLen; // [rsp+D0h] [rbp+67h] BYREF
  DWORD cValues; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cbMaxValueLen; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = *(_QWORD *)(a1 + 40);
  cValues = 0;
  v2 = -1;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v14 = 0;
  hKey = 0;
  Size = 0;
  Type = 0;
  cbData = 0;
  do
    ++v2;
  while ( *(_WORD *)(v1 + 2 * v2) );
  v4 = DiscpOpenRegistryKey(
         &hKey,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Authentication Cache",
         983103);
  if ( !v4 )
  {
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    if ( !v4 && cValues )
    {
      v5 = (BYTE *)DiscpAllocMemory(cbMaxValueLen);
      if ( v5 )
      {
        v6 = cbMaxValueNameLen + 1;
        if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen || (v7 = 2LL * v6, v7 > 0xFFFFFFFF) )
        {
          cbMaxValueNameLen = -1;
          RegCloseKey(hKey);
          return 534;
        }
        cbMaxValueNameLen = 2 * v6;
        v8 = (WCHAR *)DiscpAllocMemory(v7);
        if ( v8 )
        {
          for ( i = 0; i < cValues; ++i )
          {
            cbData = cbMaxValueLen;
            HIDWORD(Size) = cbMaxValueNameLen;
            if ( !RegEnumValueW(hKey, i, v8, (LPDWORD)&Size + 1, 0, &Type, v5, &cbData)
              && !(unsigned int)DiscpDecryptBuffer(cbData, v5, &Size, &v14) )
            {
              if ( (!(unsigned int)_o__wcsnicmp(v8, v1, (unsigned int)v2) || !(unsigned int)_o__wcsicmp(v8, L"All"))
                && (unsigned int)DiscpRebuildInitiatorAuthCache(a1, v8, v14, (unsigned int)Size) == -268500938 )
              {
                RegDeleteValueW(hKey, v8);
              }
              memset_0(v14, 0, (unsigned int)Size);
              DiscpFreeMemory(v14);
            }
          }
          DiscpFreeMemory(v8);
        }
        DiscpFreeMemory(v5);
        v4 = 0;
      }
      else
      {
        v4 = 8;
      }
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x18000f5b0  push    rbp
0x18000f5b2  push    rbx
0x18000f5b3  push    rsi
0x18000f5b4  push    rdi
0x18000f5b5  push    r12
0x18000f5b7  push    r13
0x18000f5b9  push    r14
0x18000f5bb  push    r15
0x18000f5bd  lea     rbp, [rsp-1Fh]
0x18000f5c2  sub     rsp, 88h
0x18000f5c9  mov     r15, [rcx+28h]
0x18000f5cd  xor     r12d, r12d
0x18000f5d0  mov     [rbp+57h+cValues], r12d
0x18000f5d4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f5d8  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x18000f5dc  mov     r13, rcx
0x18000f5df  mov     [rbp+57h+cbMaxValueLen], r12d
0x18000f5e3  mov     [rbp+57h+var_48], r12
0x18000f5e7  mov     [rbp+57h+hKey], r12
0x18000f5eb  mov     dword ptr [rbp+57h+Size], r12d
0x18000f5ef  mov     dword ptr [rbp+57h+Size+4], r12d
0x18000f5f3  mov     [rbp+57h+Type], r12d
0x18000f5f7  mov     [rbp+57h+cbData], r12d
0x18000f5fb  inc     rsi
0x18000f5fe  cmp     [r15+rsi*2], r12w
0x18000f603  jnz     short loc_18000F5FB
0x18000f605  mov     r8d, 0F003Fh
0x18000f60b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000f612  lea     rcx, [rbp+57h+hKey]
0x18000f616  call    cs:__imp_DiscpOpenRegistryKey
0x18000f61c  mov     ebx, eax
0x18000f61e  test    eax, eax
0x18000f620  jnz     loc_18000F7DB
0x18000f626  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f62a  lea     rax, [rbp+57h+cbMaxValueLen]
0x18000f62e  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000f633  xor     r9d, r9d; lpReserved
0x18000f636  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000f63b  xor     r8d, r8d; lpcchClass
0x18000f63e  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000f643  xor     edx, edx; lpClass
0x18000f645  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18000f649  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000f64e  lea     rax, [rbp+57h+cValues]
0x18000f652  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x18000f657  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000f65c  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18000f661  mov     [rsp+0C0h+lpcSubKeys], r12; lpcSubKeys
0x18000f666  call    cs:__imp_RegQueryInfoKeyW
0x18000f66c  mov     ebx, eax
0x18000f66e  test    eax, eax
0x18000f670  jnz     loc_18000F7D1
0x18000f676  cmp     [rbp+57h+cValues], r12d
0x18000f67a  jbe     loc_18000F7D1
0x18000f680  mov     ecx, [rbp+57h+cbMaxValueLen]
0x18000f683  call    cs:__imp_DiscpAllocMemory
0x18000f689  mov     r14, rax
0x18000f68c  test    rax, rax
0x18000f68f  jz      loc_18000F7CC
0x18000f695  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18000f698  mov     edx, 0FFFFFFFFh
0x18000f69d  lea     eax, [rcx+1]
0x18000f6a0  cmp     eax, ecx
0x18000f6a2  jb      loc_18000F7B8
0x18000f6a8  mov     ecx, eax
0x18000f6aa  add     rcx, rcx
0x18000f6ad  cmp     rcx, rdx
0x18000f6b0  ja      loc_18000F7B8
0x18000f6b6  mov     [rbp+57h+cbMaxValueNameLen], ecx
0x18000f6b9  call    cs:__imp_DiscpAllocMemory
0x18000f6bf  mov     rbx, rax
0x18000f6c2  test    rax, rax
0x18000f6c5  jz      loc_18000F7AA
0x18000f6cb  mov     edi, r12d
0x18000f6ce  cmp     [rbp+57h+cValues], r12d
0x18000f6d2  jbe     loc_18000F7A1
0x18000f6d8  mov     ecx, [rbp+57h+cbMaxValueLen]
0x18000f6db  lea     rax, [rbp+57h+cbData]
0x18000f6df  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x18000f6e4  lea     r9, [rbp+57h+Size+4]; lpcchValueName
0x18000f6e8  mov     [rbp+57h+cbData], ecx
0x18000f6eb  lea     rax, [rbp+57h+Type]
0x18000f6ef  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18000f6f2  mov     r8, rbx; lpValueName
0x18000f6f5  mov     dword ptr [rbp+57h+Size+4], ecx
0x18000f6f8  mov     edx, edi; dwIndex
0x18000f6fa  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f6fe  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpData
0x18000f703  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x18000f708  mov     [rsp+0C0h+lpcSubKeys], r12; lpReserved
0x18000f70d  call    cs:__imp_RegEnumValueW
0x18000f713  test    eax, eax
0x18000f715  jnz     short loc_18000F796
0x18000f717  mov     ecx, [rbp+57h+cbData]
0x18000f71a  lea     r9, [rbp+57h+var_48]
0x18000f71e  lea     r8, [rbp+57h+Size]
0x18000f722  mov     rdx, r14
0x18000f725  call    cs:__imp_DiscpDecryptBuffer
0x18000f72b  test    eax, eax
0x18000f72d  jnz     short loc_18000F796
0x18000f72f  mov     r8d, esi
0x18000f732  mov     rdx, r15
0x18000f735  mov     rcx, rbx
0x18000f738  call    cs:__imp__o__wcsnicmp
0x18000f73e  test    eax, eax
0x18000f740  jz      short loc_18000F756
0x18000f742  lea     rdx, aAll; "All"
0x18000f749  mov     rcx, rbx
0x18000f74c  call    cs:__imp__o__wcsicmp
0x18000f752  test    eax, eax
0x18000f754  jnz     short loc_18000F77D
0x18000f756  mov     r9d, dword ptr [rbp+57h+Size]
0x18000f75a  mov     rdx, rbx
0x18000f75d  mov     r8, [rbp+57h+var_48]
0x18000f761  mov     rcx, r13
0x18000f764  call    DiscpRebuildInitiatorAuthCache
0x18000f769  cmp     eax, 0EFFF0036h
0x18000f76e  jnz     short loc_18000F77D
0x18000f770  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f774  mov     rdx, rbx; lpValueName
0x18000f777  call    cs:__imp_RegDeleteValueW
0x18000f77d  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18000f781  xor     edx, edx; Val
0x18000f783  mov     rcx, [rbp+57h+var_48]; void *
0x18000f787  call    memset_0
0x18000f78c  mov     rcx, [rbp+57h+var_48]
0x18000f790  call    cs:__imp_DiscpFreeMemory
0x18000f796  inc     edi
0x18000f798  cmp     edi, [rbp+57h+cValues]
0x18000f79b  jb      loc_18000F6D8
0x18000f7a1  mov     rcx, rbx
0x18000f7a4  call    cs:__imp_DiscpFreeMemory
0x18000f7aa  mov     rcx, r14
0x18000f7ad  call    cs:__imp_DiscpFreeMemory
0x18000f7b3  mov     ebx, r12d
0x18000f7b6  jmp     short loc_18000F7D1
0x18000f7b8  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f7bc  mov     [rbp+57h+cbMaxValueNameLen], edx
0x18000f7bf  call    cs:__imp_RegCloseKey
0x18000f7c5  mov     eax, 216h
0x18000f7ca  jmp     short loc_18000F7DD
0x18000f7cc  mov     ebx, 8
0x18000f7d1  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f7d5  call    cs:__imp_RegCloseKey
0x18000f7db  mov     eax, ebx
0x18000f7dd  add     rsp, 88h
0x18000f7e4  pop     r15
0x18000f7e6  pop     r14
0x18000f7e8  pop     r13
0x18000f7ea  pop     r12
0x18000f7ec  pop     rdi
0x18000f7ed  pop     rsi
0x18000f7ee  pop     rbx
0x18000f7ef  pop     rbp
0x18000f7f0  retn
```
