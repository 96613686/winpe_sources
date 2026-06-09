# Cac::TestGetDecNumberCores(ulong &)

- ea: `0x180156718`
- end: `0x1801567be`
- name: `?TestGetDecNumberCores@Cac@@YAJAEAK@Z`
- size: `166`
- prototype: `__int64 __fastcall(Cac *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801571b8`

## callees

- `0x180156718`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18015678e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18015678e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801567ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801567ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180156753`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180156753`

## string_xrefs

- `0x180156768`: `CacDecCpuMaxThreads`

## pseudocode

```c
__int64 __fastcall Cac::TestGetDecNumberCores(Cac *this, unsigned int *a2)
{
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  v3 = -2147467259;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Terminal Server Client", 0, 1u, &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"CacDecCpuMaxThreads", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      v3 = 0;
      *(_DWORD *)this = Data;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180156718  push    rbp
0x18015671a  push    rbx
0x18015671b  push    rdi
0x18015671c  mov     rbp, rsp
0x18015671f  sub     rsp, 40h
0x180156723  mov     rdi, rcx
0x180156726  mov     [rbp+hKey], 0
0x18015672e  lea     rax, [rbp+hKey]
0x180156732  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180156739  mov     r9d, 1; samDesired
0x18015673f  mov     [rsp+40h+phkResult], rax; phkResult
0x180156744  xor     r8d, r8d; ulOptions
0x180156747  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Terminal Server Cl"...
0x18015674e  mov     ebx, 80004005h
0x180156753  call    cs:__imp_RegOpenKeyExW
0x180156759  test    eax, eax
0x18015675b  jnz     short loc_1801567A5
0x18015675d  mov     rcx, [rbp+hKey]; hKey
0x180156761  lea     r9, [rbp+Type]; lpType
0x180156765  mov     [rbp+Type], eax
0x180156768  lea     rdx, aCacdeccpumaxth; "CacDecCpuMaxThreads"
0x18015676f  mov     [rbp+Data], eax
0x180156772  xor     r8d, r8d; lpReserved
0x180156775  lea     rax, [rbp+cbData]
0x180156779  mov     [rbp+cbData], 4
0x180156780  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180156785  lea     rax, [rbp+Data]
0x180156789  mov     [rsp+40h+phkResult], rax; lpData
0x18015678e  call    cs:__imp_RegQueryValueExW
0x180156794  test    eax, eax
0x180156796  jnz     short loc_1801567A5
0x180156798  cmp     [rbp+Type], 4
0x18015679c  jnz     short loc_1801567A5
0x18015679e  mov     eax, [rbp+Data]
0x1801567a1  xor     ebx, ebx
0x1801567a3  mov     [rdi], eax
0x1801567a5  mov     rcx, [rbp+hKey]; hKey
0x1801567a9  test    rcx, rcx
0x1801567ac  jz      short loc_1801567B4
0x1801567ae  call    cs:__imp_RegCloseKey
0x1801567b4  mov     eax, ebx
0x1801567b6  add     rsp, 40h
0x1801567ba  pop     rdi
0x1801567bb  pop     rbx
0x1801567bc  pop     rbp
0x1801567bd  retn
```
