# ExpireInDays(ushort const *,ulong *)

- ea: `0x180042b3c`
- end: `0x180042c01`
- name: `?ExpireInDays@@YAKPEBGPEAK@Z`
- size: `197`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042c80`

## callees

- `0x180042b3c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180042b83`
- `ADVAPI32!RegOpenKeyExW` at `0x180042b83`
- `ADVAPI32!RegCloseKey` at `0x180042be7`
- `ADVAPI32!RegCloseKey` at `0x180042be7`
- `ADVAPI32!RegGetValueW` at `0x180042bc5`
- `ADVAPI32!RegGetValueW` at `0x180042bc5`

## pseudocode

```c
__int64 __fastcall ExpireInDays(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int ValueW; // ebx
  HKEY hkey; // [rsp+40h] [rbp-18h] BYREF
  unsigned int pvData; // [rsp+60h] [rbp+8h] BYREF
  int v7; // [rsp+64h] [rbp+Ch]
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD pdwType; // [rsp+78h] [rbp+20h] BYREF

  v7 = HIDWORD(a1);
  pdwType = 0;
  pvData = 0;
  hkey = 0;
  pcbData = 4;
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\TermServLicensing", 0, 0xF003Fu, &hkey);
  if ( !ValueW )
  {
    ValueW = RegGetValueW(hkey, 0, L"ExpireInDays", 0x10u, &pdwType, &pvData, &pcbData);
    if ( !ValueW )
      *a2 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return ValueW;
}

```

## disassembly

```asm
0x180042b3c  mov     rax, rsp
0x180042b3f  mov     [rax+10h], rbx
0x180042b43  mov     [rax+8], rcx
0x180042b47  push    rdi
0x180042b48  sub     rsp, 50h
0x180042b4c  and     dword ptr [rax+20h], 0
0x180042b50  mov     rdi, rdx
0x180042b53  and     dword ptr [rax+8], 0
0x180042b57  mov     r9d, 0F003Fh; samDesired
0x180042b5d  and     qword ptr [rax-18h], 0
0x180042b62  xor     r8d, r8d; ulOptions
0x180042b65  mov     dword ptr [rax+18h], 4
0x180042b6c  lea     rax, [rax-18h]
0x180042b70  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\TermServLicensing"
0x180042b77  mov     [rsp+58h+phkResult], rax; phkResult
0x180042b7c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042b83  call    cs:__imp_RegOpenKeyExW
0x180042b8a  nop     dword ptr [rax+rax+00h]
0x180042b8f  mov     ebx, eax
0x180042b91  test    eax, eax
0x180042b93  jnz     short loc_180042BDD
0x180042b95  mov     rcx, [rsp+58h+hkey]; hkey
0x180042b9a  lea     rax, [rsp+58h+arg_10]
0x180042b9f  mov     [rsp+58h+pcbData], rax; pcbData
0x180042ba4  lea     r9d, [rbx+10h]; dwFlags
0x180042ba8  lea     rax, [rsp+58h+arg_0]
0x180042bad  xor     edx, edx; lpSubKey
0x180042baf  mov     [rsp+58h+pvData], rax; pvData
0x180042bb4  lea     r8, aExpireindays; "ExpireInDays"
0x180042bbb  lea     rax, [rsp+58h+pdwType]
0x180042bc0  mov     [rsp+58h+phkResult], rax; pdwType
0x180042bc5  call    cs:__imp_RegGetValueW
0x180042bcc  nop     dword ptr [rax+rax+00h]
0x180042bd1  mov     ebx, eax
0x180042bd3  test    eax, eax
0x180042bd5  jnz     short loc_180042BDD
0x180042bd7  mov     eax, [rsp+58h+arg_0]
0x180042bdb  mov     [rdi], eax
0x180042bdd  mov     rcx, [rsp+58h+hkey]; hKey
0x180042be2  test    rcx, rcx
0x180042be5  jz      short loc_180042BF3
0x180042be7  call    cs:__imp_RegCloseKey
0x180042bee  nop     dword ptr [rax+rax+00h]
0x180042bf3  mov     eax, ebx
0x180042bf5  mov     rbx, [rsp+58h+arg_8]
0x180042bfa  add     rsp, 50h
0x180042bfe  pop     rdi
0x180042bff  retn
```
