# GetExternalSchannelAlgorithms

- ea: `0x180012578`
- end: `0x180012606`
- name: `GetExternalSchannelAlgorithms`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012500`

## callees

- `0x180012578`
- `0x1800126f0`
- `0x180012a7c`
- `0x18001d8e8`
- `0x180023e34`
- `0x180024190`
- `0x180024650`
- `0x180024a3c`

## import_xrefs

- `ntdll!NtClose` at `0x1800125aa`
- `ntdll!NtClose` at `0x1800125aa`

## string_xrefs

- `0x18001258c`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider`

## pseudocode

```c
NTSTATUS GetExternalSchannelAlgorithms()
{
  NTSTATUS result; // eax
  HANDLE Handle; // [rsp+38h] [rbp+10h] BYREF

  Handle = 0;
  result = TlsOpenRegKey(
             L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol Provider",
             0,
             &Handle);
  if ( result >= 0 )
  {
    result = GetSslDWordFromRegistry(Handle);
    if ( result >= 0 )
      result = 1;
  }
  if ( Handle )
    result = NtClose(Handle);
  dword_18003EF90 = 0;
  return result;
}

```

## disassembly

```asm
0x180012578  push    rbx
0x18001257a  sub     rsp, 20h
0x18001257e  xor     ebx, ebx
0x180012580  lea     r8, [rsp+28h+Handle]; KeyHandle
0x180012585  xor     edx, edx; PCWSTR
0x180012587  mov     [rsp+28h+Handle], rbx
0x18001258c  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180012593  mov     [rsp+28h+arg_0], ebx
0x180012597  call    TlsOpenRegKey
0x18001259c  test    eax, eax
0x18001259e  jns     short loc_1800125C0
0x1800125a0  mov     rcx, [rsp+28h+Handle]; Handle
0x1800125a5  test    rcx, rcx
0x1800125a8  jz      short loc_1800125B0
0x1800125aa  call    cs:__imp_NtClose
0x1800125b0  mov     cs:dword_18003EF90, ebx
0x1800125b6  test    ebx, ebx
0x1800125b8  jnz     short loc_1800125E8
0x1800125ba  add     rsp, 20h
0x1800125be  pop     rbx
0x1800125bf  retn
0x1800125c0  mov     rcx, [rsp+28h+Handle]; KeyHandle
0x1800125c5  lea     r8, [rsp+28h+arg_0]
0x1800125ca  lea     rdx, aEnabletlsexter; "EnableTlsExternalAlgorithms"
0x1800125d1  call    GetSslDWordFromRegistry
0x1800125d6  test    eax, eax
0x1800125d8  js      short loc_1800125A0
0x1800125da  mov     eax, 1
0x1800125df  cmp     [rsp+28h+arg_0], eax
0x1800125e3  cmovz   ebx, eax
0x1800125e6  jmp     short loc_1800125A0
0x1800125e8  call    GetExternalHashAlgorithms
0x1800125ed  call    GetExternalSignatureAlgorithms
0x1800125f2  call    GetExternalKeyExchangeAlgorithms
0x1800125f7  call    GetExternalCipherAlgorithms
0x1800125fc  add     rsp, 20h
0x180012600  pop     rbx
0x180012601  jmp     GetExternalCipherSuites
```
