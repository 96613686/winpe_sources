# GetExternalSchannelAlgorithms

- ea: `0x14000bff0`
- end: `0x14000c06b`
- name: `GetExternalSchannelAlgorithms`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003e30`

## callees

- `0x14000bff0`
- `0x14000c63c`
- `0x14000c7f0`
- `0x14000c86c`
- `0x14000ca84`
- `0x14000ce40`
- `0x14000d200`
- `0x14000d5d8`

## string_xrefs

- `0x14000c004`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider`

## pseudocode

```c
__int64 GetExternalSchannelAlgorithms()
{
  __int64 result; // rax
  HANDLE KeyHandle; // [rsp+38h] [rbp+10h] BYREF

  KeyHandle = 0;
  if ( (int)TlsOpenRegKey(
              L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol Provider",
              0,
              &KeyHandle) >= 0 )
    GetSslDWordFromRegistry(KeyHandle);
  result = TlsCloseRegKey(&KeyHandle);
  dword_140019530 = 0;
  return result;
}

```

## disassembly

```asm
0x14000bff0  push    rbx
0x14000bff2  sub     rsp, 20h
0x14000bff6  xor     ebx, ebx
0x14000bff8  lea     r8, [rsp+28h+KeyHandle]; KeyHandle
0x14000bffd  xor     edx, edx; PCWSTR
0x14000bfff  mov     [rsp+28h+KeyHandle], rbx
0x14000c004  lea     rcx, aRegistryMachin_5; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000c00b  mov     [rsp+28h+arg_0], ebx
0x14000c00f  call    TlsOpenRegKey
0x14000c014  test    eax, eax
0x14000c016  js      short loc_14000C03C
0x14000c018  mov     rcx, [rsp+28h+KeyHandle]; KeyHandle
0x14000c01d  lea     r8, [rsp+28h+arg_0]
0x14000c022  lea     rdx, aEnabletlsexter; "EnableTlsExternalAlgorithms"
0x14000c029  call    GetSslDWordFromRegistry
0x14000c02e  test    eax, eax
0x14000c030  js      short loc_14000C03C
0x14000c032  lea     eax, [rbx+1]
0x14000c035  cmp     [rsp+28h+arg_0], eax
0x14000c039  cmovz   ebx, eax
0x14000c03c  lea     rcx, [rsp+28h+KeyHandle]
0x14000c041  call    TlsCloseRegKey
0x14000c046  mov     cs:dword_140019530, ebx
0x14000c04c  test    ebx, ebx
0x14000c04e  jz      short loc_14000C064
0x14000c050  call    GetExternalHashAlgorithms
0x14000c055  call    GetExternalSignatureAlgorithms
0x14000c05a  call    GetExternalKeyExchangeAlgorithms
0x14000c05f  call    GetExternalCipherAlgorithms
0x14000c064  add     rsp, 20h
0x14000c068  pop     rbx
0x14000c069  retn
```
