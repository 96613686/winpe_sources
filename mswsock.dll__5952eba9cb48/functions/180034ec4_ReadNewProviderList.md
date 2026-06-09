# ReadNewProviderList

- ea: `0x180034ec4`
- end: `0x180034fe8`
- name: `ReadNewProviderList`
- size: `292`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800328c0`

## callees

- `0x1800327a8`
- `0x180034da4`
- `0x180034ec4`
- `0x180038118`
- `0x18003a0d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034fc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034fc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034f29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034f29`

## string_xrefs

- `0x180034f3b`: `Failed to open parameters subkey`
- `0x180034fb0`: `Failed to read Transports value`

## pseudocode

```c
__int64 __fastcall ReadNewProviderList(HKEY hKey)
{
  unsigned int MultiSz; // eax
  unsigned int v3; // ebx
  const wchar_t *v4; // rdx
  char v5; // al
  HKEY hKeya; // [rsp+50h] [rbp+18h] BYREF

  hKeya = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qS(
      1025,
      33,
      (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids,
      (_DWORD)hKey,
      (__int64)L"Parameters");
  MultiSz = RegOpenKeyExW(hKey, L"Parameters", 0, 0xF003Fu, &hKeya);
  v3 = MultiSz;
  if ( MultiSz )
  {
    v4 = L"Failed to open parameters subkey";
LABEL_11:
    LogError(MultiSz, v4);
    goto LABEL_12;
  }
  v5 = xmmword_180063D60;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_q(1025, 34, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, hKeya);
    v5 = xmmword_180063D60;
  }
  if ( (v5 & 2) != 0 )
    WPP_SF_qS(
      1025,
      35,
      (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids,
      (_DWORD)hKeya,
      (__int64)L"Transports");
  MultiSz = ReadMultiSz(hKeya, L"Transports");
  v3 = MultiSz;
  if ( MultiSz )
  {
    v4 = L"Failed to read Transports value";
    goto LABEL_11;
  }
LABEL_12:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v3;
}

```

## disassembly

```asm
0x180034ec4  mov     rax, rsp
0x180034ec7  mov     [rax+8], rbx
0x180034ecb  mov     [rax+10h], rdi
0x180034ecf  push    r12
0x180034ed1  sub     rsp, 30h
0x180034ed5  mov     rdi, rdx
0x180034ed8  mov     qword ptr [rax+18h], 0
0x180034ee0  mov     rbx, rcx
0x180034ee3  test    byte ptr cs:xmmword_180063D60, 2
0x180034eea  lea     r12, aParameters; "Parameters"
0x180034ef1  jz      short loc_180034F10
0x180034ef3  mov     edx, 21h ; '!'
0x180034ef8  mov     [rax-18h], r12
0x180034efc  mov     ecx, 401h
0x180034f01  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034f08  mov     r9, rbx
0x180034f0b  call    WPP_SF_qS
0x180034f10  lea     rax, [rsp+38h+hKey]
0x180034f15  mov     r9d, 0F003Fh; samDesired
0x180034f1b  xor     r8d, r8d; ulOptions
0x180034f1e  mov     [rsp+38h+phkResult], rax; phkResult
0x180034f23  mov     rdx, r12; lpSubKey
0x180034f26  mov     rcx, rbx; hKey
0x180034f29  call    cs:__imp_RegOpenKeyExW
0x180034f30  nop     dword ptr [rax+rax+00h]
0x180034f35  mov     ebx, eax
0x180034f37  test    eax, eax
0x180034f39  jz      short loc_180034F44
0x180034f3b  lea     rdx, aFailedToOpenPa; "Failed to open parameters subkey"
0x180034f42  jmp     short loc_180034FB7
0x180034f44  mov     al, byte ptr cs:xmmword_180063D60
0x180034f4a  test    al, 2
0x180034f4c  jz      short loc_180034F6F
0x180034f4e  mov     r9, [rsp+38h+hKey]
0x180034f53  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034f5a  mov     edx, 22h ; '"'
0x180034f5f  mov     ecx, 401h
0x180034f64  call    WPP_SF_q
0x180034f69  mov     al, byte ptr cs:xmmword_180063D60
0x180034f6f  lea     rbx, ValueName; "Transports"
0x180034f76  test    al, 2
0x180034f78  jz      short loc_180034F9A
0x180034f7a  mov     r9, [rsp+38h+hKey]
0x180034f7f  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034f86  mov     edx, 23h ; '#'
0x180034f8b  mov     [rsp+38h+phkResult], rbx
0x180034f90  mov     ecx, 401h
0x180034f95  call    WPP_SF_qS
0x180034f9a  mov     rcx, [rsp+38h+hKey]; hKey
0x180034f9f  mov     r8, rdi
0x180034fa2  mov     rdx, rbx; lpValueName
0x180034fa5  call    ReadMultiSz
0x180034faa  mov     ebx, eax
0x180034fac  test    eax, eax
0x180034fae  jz      short loc_180034FBE
0x180034fb0  lea     rdx, aFailedToReadTr; "Failed to read Transports value"
0x180034fb7  mov     ecx, eax
0x180034fb9  call    LogError
0x180034fbe  mov     rcx, [rsp+38h+hKey]; hKey
0x180034fc3  test    rcx, rcx
0x180034fc6  jz      short loc_180034FD4
0x180034fc8  call    cs:__imp_RegCloseKey
0x180034fcf  nop     dword ptr [rax+rax+00h]
0x180034fd4  mov     rdi, [rsp+38h+arg_8]
0x180034fd9  mov     eax, ebx
0x180034fdb  mov     rbx, [rsp+38h+arg_0]
0x180034fe0  add     rsp, 30h
0x180034fe4  pop     r12
0x180034fe6  retn
```
