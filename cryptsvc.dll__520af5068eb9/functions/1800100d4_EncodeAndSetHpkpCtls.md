# _EncodeAndSetHpkpCtls

- ea: `0x1800100d4`
- end: `0x1800101ca`
- name: `_EncodeAndSetHpkpCtls`
- size: `246`
- prototype: `__int64 __fastcall(int, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180001868`

## callees

- `0x1800068b0`
- `0x1800100d4`
- `0x1800101d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001019f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001019f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010165`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010165`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010193`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010193`

## string_xrefs

- `0x180010132`: `Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

## pseudocode

```c
__int64 __fastcall EncodeAndSetHpkpCtls(int a1, int a2, int a3, int a4, __int64 a5)
{
  __int64 result; // rax
  LSTATUS v6; // eax
  BYTE *v7; // rbx
  DWORD cbData; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-10h] BYREF

  lpData = 0;
  cbData = 0;
  hKey = 0;
  dwDisposition = 0;
  result = EncodeDomainCtl(a1, a2, a3, a4, a5, (__int64)&lpData, (__int64)&cbData);
  if ( (_DWORD)result )
  {
    v6 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
           0,
           0,
           0,
           0x2011Fu,
           0,
           &hKey,
           &dwDisposition);
    v7 = lpData;
    if ( v6 || (v6 = RegSetValueExW(hKey, L"HpkpEncodedCtl", 0, 3u, lpData, cbData)) != 0 )
      SetLastError(v6);
    if ( hKey )
      RegCloseKey(hKey);
    return PkiFree(v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800100d4  mov     r11, rsp
0x1800100d7  mov     [r11+8], rbx
0x1800100db  push    rbp
0x1800100dc  mov     rbp, rsp
0x1800100df  sub     rsp, 70h
0x1800100e3  lea     rax, [rbp+cbData]
0x1800100e7  mov     [rbp+lpData], 0
0x1800100ef  mov     [r11-48h], rax
0x1800100f3  lea     rax, [rbp+lpData]
0x1800100f7  mov     [r11-50h], rax
0x1800100fb  mov     rax, [rbp+arg_20]
0x1800100ff  mov     [r11-58h], rax
0x180010103  mov     [rbp+cbData], 0
0x18001010a  mov     [rbp+hKey], 0
0x180010112  mov     [rbp+dwDisposition], 0
0x180010119  call    _EncodeDomainCtl
0x18001011e  test    eax, eax
0x180010120  jz      loc_1800101BC
0x180010126  lea     rax, [rbp+dwDisposition]
0x18001012a  xor     r9d, r9d; lpClass
0x18001012d  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180010132  lea     rdx, SubKey; "Software\\Microsoft\\SystemCertificates"...
0x180010139  lea     rax, [rbp+hKey]
0x18001013d  xor     r8d, r8d; Reserved
0x180010140  mov     [rsp+70h+phkResult], rax; phkResult
0x180010145  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001014c  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010155  mov     [rsp+70h+samDesired], 2011Fh; samDesired
0x18001015d  mov     [rsp+70h+dwOptions], 0; dwOptions
0x180010165  call    cs:__imp_RegCreateKeyExW
0x18001016b  mov     rbx, [rbp+lpData]
0x18001016f  test    eax, eax
0x180010171  jnz     short loc_18001019D
0x180010173  mov     eax, [rbp+cbData]
0x180010176  lea     rdx, ValueName; "HpkpEncodedCtl"
0x18001017d  mov     rcx, [rbp+hKey]; hKey
0x180010181  mov     r9d, 3; dwType
0x180010187  mov     [rsp+70h+samDesired], eax; cbData
0x18001018b  xor     r8d, r8d; Reserved
0x18001018e  mov     qword ptr [rsp+70h+dwOptions], rbx; lpData
0x180010193  call    cs:__imp_RegSetValueExW
0x180010199  test    eax, eax
0x18001019b  jz      short loc_1800101A5
0x18001019d  mov     ecx, eax; dwErrCode
0x18001019f  call    cs:__imp_SetLastError
0x1800101a5  mov     rcx, [rbp+hKey]; hKey
0x1800101a9  test    rcx, rcx
0x1800101ac  jz      short loc_1800101B4
0x1800101ae  call    cs:__imp_RegCloseKey
0x1800101b4  mov     rcx, rbx; hMem
0x1800101b7  call    PkiFree
0x1800101bc  mov     rbx, [rsp+70h+arg_0]
0x1800101c4  add     rsp, 70h
0x1800101c8  pop     rbp
0x1800101c9  retn
```
