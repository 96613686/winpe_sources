# ctRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x180010070`
- end: `0x18001013d`
- name: `?ctRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `205`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, __int64, unsigned __int16 *, unsigned int, REGSAM samDesired, struct _SECURITY_ATTRIBUTES *, PHKEY phkResult, LPDWORD lpdwDisposition)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fc24`
- `0x180031a2c`
- `0x180031ddc`

## callees

- `0x180008400`
- `0x180008610`
- `0x180010070`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001012a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001012a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18001009e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18001009e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800100fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800100fd`

## string_xrefs

- `0x1800100d1`: `Software\Microsoft\Cryptography\CertificateTemplateCache`
- `0x18001010c`: `Software\Microsoft\Cryptography\CertificateTemplateCache`

## pseudocode

```c
__int64 __fastcall ctRegCreateKeyEx(
        HKEY a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *a7,
        PHKEY phkResult,
        LPDWORD lpdwDisposition)
{
  REGSAM v9; // edi
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  LSTATUS Key; // eax
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v9 = samDesired;
  hKey = 0;
  if ( a1 == HKEY_CURRENT_USER )
  {
    v10 = RegOpenCurrentUser(samDesired, &hKey);
    v11 = v10;
    if ( v10 )
    {
      CSPrintErrorLineFile(0x13F0328u, v10);
      goto LABEL_7;
    }
    a1 = hKey;
  }
  Key = RegCreateKeyExW(
          a1,
          L"Software\\Microsoft\\Cryptography\\CertificateTemplateCache",
          0,
          (LPWSTR)&Class,
          0,
          v9,
          0,
          phkResult,
          lpdwDisposition);
  v11 = Key;
  if ( Key )
    CSPrintErrorLineFileData2(L"Software\\Microsoft\\Cryptography\\CertificateTemplateCache", 0x14E0328u, Key, 0);
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return v11;
}

```

## disassembly

```asm
0x180010070  mov     rax, rsp
0x180010073  mov     [rax+8], rbx
0x180010077  mov     [rax+20h], r9
0x18001007b  push    rdi
0x18001007c  sub     rsp, 50h
0x180010080  mov     edi, [rsp+58h+samDesired]
0x180010087  mov     qword ptr [rax+20h], 0
0x18001008f  cmp     rcx, 0FFFFFFFF80000001h
0x180010096  jnz     short loc_1800100BD
0x180010098  lea     rdx, [rax+20h]; phkResult
0x18001009c  mov     ecx, edi; samDesired
0x18001009e  call    cs:__imp_RegOpenCurrentUser
0x1800100a4  mov     ebx, eax
0x1800100a6  test    eax, eax
0x1800100a8  jz      short loc_1800100B8
0x1800100aa  mov     edx, eax; int
0x1800100ac  mov     ecx, 13F0328h; unsigned int
0x1800100b1  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800100b6  jmp     short loc_180010120
0x1800100b8  mov     rcx, [rsp+58h+hKey]; hKey
0x1800100bd  mov     rax, [rsp+58h+arg_40]
0x1800100c5  lea     r9, Class; lpClass
0x1800100cc  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800100d1  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\Cert"...
0x1800100d8  mov     rax, [rsp+58h+arg_38]
0x1800100e0  xor     r8d, r8d; Reserved
0x1800100e3  mov     [rsp+58h+phkResult], rax; phkResult
0x1800100e8  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800100f1  mov     [rsp+58h+var_30], edi; samDesired
0x1800100f5  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800100fd  call    cs:__imp_RegCreateKeyExW
0x180010103  mov     ebx, eax
0x180010105  test    eax, eax
0x180010107  jz      short loc_180010120
0x180010109  xor     r9d, r9d; int
0x18001010c  lea     rcx, SubKey; "Software\\Microsoft\\Cryptography\\Cert"...
0x180010113  mov     r8d, eax; int
0x180010116  mov     edx, 14E0328h; unsigned int
0x18001011b  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180010120  mov     rcx, [rsp+58h+hKey]; hKey
0x180010125  test    rcx, rcx
0x180010128  jz      short loc_180010130
0x18001012a  call    cs:__imp_RegCloseKey
0x180010130  mov     eax, ebx
0x180010132  mov     rbx, [rsp+58h+arg_0]
0x180010137  add     rsp, 50h
0x18001013b  pop     rdi
0x18001013c  retn
```
