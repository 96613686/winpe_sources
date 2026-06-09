# EDL_AddNewDomain(_GUID const &,ushort const *)

- ea: `0x180063ad0`
- end: `0x180063c00`
- name: `?EDL_AddNewDomain@@YAJAEBU_GUID@@PEBG@Z`
- size: `304`
- prototype: `__int64 __fastcall(const struct _GUID *, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064070`

## callees

- `0x18004aec0`
- `0x180063ad0`
- `0x180063e00`
- `0x1800641f0`
- `0x1800642d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180063bc3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180063bc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063bcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063be8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063bcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063be8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180063b91`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180063b91`

## string_xrefs

- `0x180063bb0`: `AddedDuringPrivateBrowsing`

## pseudocode

```c
__int64 __fastcall EDL_AddNewDomain(const struct _GUID *a1, LPCWSTR lpSubKey)
{
  int v2; // eax
  int v5; // r8d
  signed int IsDomainAllowed; // ebx
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+38h] BYREF

  v2 = *lpSubKey;
  v5 = 42 - v2;
  if ( v2 == 42 )
    v5 = -lpSubKey[1];
  if ( !v5 )
    EDL_DeleteAllowedDomainsList(a1);
  hKey = 0;
  dwDisposition = 0;
  IsDomainAllowed = EDL_IsDomainAllowed(a1, lpSubKey, (int *)&dwDisposition);
  if ( IsDomainAllowed >= 0 && !dwDisposition )
  {
    IsDomainAllowed = CreateAllowedDomainsKey(a1, &hKey);
    if ( !IsDomainAllowed )
    {
      dwDisposition = 0;
      phkResult = 0;
      v7 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
      if ( v7 )
      {
        if ( v7 > 0 )
          IsDomainAllowed = (unsigned __int16)v7 | 0x80070000;
        else
          IsDomainAllowed = v7;
      }
      else
      {
        if ( LCIEIsCurrentProcessInPrivate() )
          RegSetValueExW(phkResult, L"AddedDuringPrivateBrowsing", 0, 4u, 0, 0);
        RegCloseKey(phkResult);
      }
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)IsDomainAllowed;
}

```

## disassembly

```asm
0x180063ad0  mov     [rsp-18h+arg_0], rbx
0x180063ad5  push    rbp
0x180063ad6  push    rsi
0x180063ad7  push    rdi
0x180063ad8  mov     rbp, rsp
0x180063adb  sub     rsp, 60h
0x180063adf  movzx   eax, word ptr [rdx]
0x180063ae2  mov     r8d, 2Ah ; '*'
0x180063ae8  mov     rsi, rdx
0x180063aeb  mov     rdi, rcx
0x180063aee  sub     r8d, eax
0x180063af1  jnz     short loc_180063B00
0x180063af3  xor     eax, eax
0x180063af5  movzx   r8d, ax
0x180063af9  movzx   eax, word ptr [rdx+2]
0x180063afd  sub     r8d, eax
0x180063b00  test    r8d, r8d
0x180063b03  jnz     short loc_180063B0A
0x180063b05  call    ?EDL_DeleteAllowedDomainsList@@YAJAEBU_GUID@@@Z; EDL_DeleteAllowedDomainsList(_GUID const &)
0x180063b0a  lea     r8, [rbp+dwDisposition]; int *
0x180063b0e  mov     [rbp+hKey], 0
0x180063b16  mov     rdx, rsi; lpSubKey
0x180063b19  mov     [rbp+dwDisposition], 0
0x180063b20  mov     rcx, rdi; struct _GUID *
0x180063b23  call    ?EDL_IsDomainAllowed@@YAJAEBU_GUID@@PEBGPEAH@Z; EDL_IsDomainAllowed(_GUID const &,ushort const *,int *)
0x180063b28  mov     ebx, eax
0x180063b2a  test    eax, eax
0x180063b2c  js      loc_180063BEE
0x180063b32  cmp     [rbp+dwDisposition], 0
0x180063b36  jnz     loc_180063BEE
0x180063b3c  lea     rdx, [rbp+hKey]; HKEY *
0x180063b40  mov     rcx, rdi; struct _GUID *
0x180063b43  call    ?CreateAllowedDomainsKey@@YAJAEBU_GUID@@PEAPEAUHKEY__@@@Z; CreateAllowedDomainsKey(_GUID const &,HKEY__ * *)
0x180063b48  mov     ebx, eax
0x180063b4a  test    eax, eax
0x180063b4c  jnz     loc_180063BEE
0x180063b52  mov     rcx, [rbp+hKey]; hKey
0x180063b56  xor     r9d, r9d; lpClass
0x180063b59  mov     [rbp+dwDisposition], eax
0x180063b5c  xor     r8d, r8d; Reserved
0x180063b5f  lea     rax, [rbp+dwDisposition]
0x180063b63  mov     [rbp+arg_18], 0
0x180063b6b  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180063b70  mov     rdx, rsi; lpSubKey
0x180063b73  lea     rax, [rbp+arg_18]
0x180063b77  mov     [rsp+60h+phkResult], rax; phkResult
0x180063b7c  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180063b85  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180063b8d  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x180063b91  call    cs:__imp_RegCreateKeyExW
0x180063b97  test    eax, eax
0x180063b99  jnz     short loc_180063BD5
0x180063b9b  call    ?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180063ba0  test    al, al
0x180063ba2  jz      short loc_180063BC9
0x180063ba4  mov     rcx, [rbp+arg_18]; hKey
0x180063ba8  lea     r9d, [rbx+4]; dwType
0x180063bac  mov     [rsp+60h+samDesired], ebx; cbData
0x180063bb0  lea     rdx, aAddedduringpri; "AddedDuringPrivateBrowsing"
0x180063bb7  xor     r8d, r8d; Reserved
0x180063bba  mov     qword ptr [rsp+60h+dwOptions], 0; lpData
0x180063bc3  call    cs:__imp_RegSetValueExW
0x180063bc9  mov     rcx, [rbp+arg_18]; hKey
0x180063bcd  call    cs:__imp_RegCloseKey
0x180063bd3  jmp     short loc_180063BE4
0x180063bd5  jg      short loc_180063BDB
0x180063bd7  mov     ebx, eax
0x180063bd9  jmp     short loc_180063BE4
0x180063bdb  movzx   ebx, ax
0x180063bde  or      ebx, 80070000h
0x180063be4  mov     rcx, [rbp+hKey]; hKey
0x180063be8  call    cs:__imp_RegCloseKey
0x180063bee  mov     eax, ebx
0x180063bf0  mov     rbx, [rsp+60h+arg_0]
0x180063bf8  add     rsp, 60h
0x180063bfc  pop     rdi
0x180063bfd  pop     rsi
0x180063bfe  pop     rbp
0x180063bff  retn
```
