# DeleteStaticDnsServerAddresses

- ea: `0x18003ee24`
- end: `0x18003eec8`
- name: `DeleteStaticDnsServerAddresses`
- size: `164`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800279a0`
- `0x180027aa0`

## callees

- `0x180002534`
- `0x18000eb7c`
- `0x18003ee24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ee6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ee6e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003ee86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003ee86`

## pseudocode

```c
__int64 __fastcall DeleteStaticDnsServerAddresses(__int64 a1)
{
  unsigned int v1; // eax
  __int64 v2; // rbx
  unsigned int v3; // edi
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  hKey = 0;
  v1 = DhcpFindAndRefContext(a1, &v6);
  v2 = v6;
  v3 = v1;
  if ( !v1 )
  {
    v3 = RegOpenKeyExW(*(HKEY *)(v6 + 728), 0, 0, 0xFu, &hKey);
    if ( !v3 )
    {
      v3 = RegDeleteValueW(hKey, L"NameServer");
      if ( v3 == 2 )
        v3 = 0;
      RegCloseKey(hKey);
    }
  }
  if ( v2 && _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 16), 0xFFFFFFFF) == 1 )
    DhcpDestroyContextEx(v2);
  return v3;
}

```

## disassembly

```asm
0x18003ee24  mov     rax, rsp
0x18003ee27  mov     [rax+8], rbx
0x18003ee2b  push    rdi
0x18003ee2c  sub     rsp, 30h
0x18003ee30  lea     rdx, [rax+18h]
0x18003ee34  mov     qword ptr [rax+18h], 0
0x18003ee3c  mov     qword ptr [rax+10h], 0
0x18003ee44  call    DhcpFindAndRefContext
0x18003ee49  mov     rbx, [rsp+38h+arg_10]
0x18003ee4e  mov     edi, eax
0x18003ee50  test    eax, eax
0x18003ee52  jnz     short loc_18003EEA1
0x18003ee54  mov     rcx, [rbx+2D8h]; hKey
0x18003ee5b  lea     rax, [rsp+38h+hKey]
0x18003ee60  lea     r9d, [rdi+0Fh]; samDesired
0x18003ee64  mov     [rsp+38h+phkResult], rax; phkResult
0x18003ee69  xor     r8d, r8d; ulOptions
0x18003ee6c  xor     edx, edx; lpSubKey
0x18003ee6e  call    cs:__imp_RegOpenKeyExW
0x18003ee74  mov     edi, eax
0x18003ee76  test    eax, eax
0x18003ee78  jnz     short loc_18003EEA1
0x18003ee7a  mov     rcx, [rsp+38h+hKey]; hKey
0x18003ee7f  lea     rdx, aNameserver; "NameServer"
0x18003ee86  call    cs:__imp_RegDeleteValueW
0x18003ee8c  mov     edi, eax
0x18003ee8e  xor     eax, eax
0x18003ee90  cmp     edi, 2
0x18003ee93  cmovz   edi, eax
0x18003ee96  mov     rcx, [rsp+38h+hKey]; hKey
0x18003ee9b  call    cs:__imp_RegCloseKey
0x18003eea1  test    rbx, rbx
0x18003eea4  jz      short loc_18003EEBB
0x18003eea6  or      eax, 0FFFFFFFFh
0x18003eea9  lock xadd [rbx+10h], eax
0x18003eeae  cmp     eax, 1
0x18003eeb1  jnz     short loc_18003EEBB
0x18003eeb3  mov     rcx, rbx
0x18003eeb6  call    DhcpDestroyContextEx
0x18003eebb  mov     rbx, [rsp+38h+arg_0]
0x18003eec0  mov     eax, edi
0x18003eec2  add     rsp, 30h
0x18003eec6  pop     rdi
0x18003eec7  retn
```
