# AEAcquireExclusiveAccess

- ea: `0x1800049d0`
- end: `0x180004acf`
- name: `AEAcquireExclusiveAccess`
- size: `255`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001d90`

## callees

- `0x1800049d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180004a06`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180004a06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ac4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004aa1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004aa1`

## pseudocode

```c
__int64 __fastcall AEAcquireExclusiveAccess(int a1)
{
  unsigned int v2; // edi
  HKEY v4; // rcx
  DWORD dwDisposition; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+18h] BYREF

  phkResult = 0;
  v2 = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( a1 )
  {
    v4 = HKEY_LOCAL_MACHINE;
    hKey = HKEY_LOCAL_MACHINE;
  }
  else
  {
    if ( RegOpenCurrentUser(0x20006u, &hKey) )
    {
      hKey = 0;
      goto LABEL_4;
    }
    v4 = hKey;
  }
  if ( RegCreateKeyExW(
         v4,
         L"SOFTWARE\\Microsoft\\Volatile-AutoEnroll-EXCLUSIVE",
         0,
         0,
         1u,
         0x20006u,
         0,
         &phkResult,
         &dwDisposition) )
  {
    phkResult = 0;
    goto LABEL_6;
  }
  if ( dwDisposition == 1 )
    v2 = 1;
LABEL_4:
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_6:
  if ( !a1 && hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800049d0  mov     rax, rsp
0x1800049d3  mov     [rax+10h], rdx
0x1800049d7  push    rdi
0x1800049d8  sub     rsp, 60h
0x1800049dc  mov     [rax+20h], rbx
0x1800049e0  mov     ebx, ecx
0x1800049e2  mov     [rax-10h], rbp
0x1800049e6  mov     [rax-18h], rsi
0x1800049ea  xor     esi, esi
0x1800049ec  mov     [rax+18h], rsi
0x1800049f0  mov     edi, esi
0x1800049f2  mov     [rax+10h], rsi
0x1800049f6  mov     [rax+8], esi
0x1800049f9  test    ecx, ecx
0x1800049fb  jnz     short loc_180004A5B
0x1800049fd  lea     rdx, [rax+10h]; phkResult
0x180004a01  mov     ecx, 20006h; samDesired
0x180004a06  call    cs:__imp_RegOpenCurrentUser
0x180004a0c  test    eax, eax
0x180004a0e  jz      short loc_180004A54
0x180004a10  mov     [rsp+68h+hKey], rsi
0x180004a15  mov     rcx, [rsp+68h+arg_10]; hKey
0x180004a1d  test    rcx, rcx
0x180004a20  jnz     loc_180004AC4
0x180004a26  mov     rsi, [rsp+68h+var_18]
0x180004a2b  test    ebx, ebx
0x180004a2d  mov     rbx, [rsp+68h+arg_18]
0x180004a35  mov     rbp, [rsp+68h+var_10]
0x180004a3a  jnz     short loc_180004A4C
0x180004a3c  mov     rcx, [rsp+68h+hKey]; hKey
0x180004a41  test    rcx, rcx
0x180004a44  jz      short loc_180004A4C
0x180004a46  call    cs:__imp_RegCloseKey
0x180004a4c  mov     eax, edi
0x180004a4e  add     rsp, 60h
0x180004a52  pop     rdi
0x180004a53  retn
0x180004a54  mov     rcx, [rsp+68h+hKey]
0x180004a59  jmp     short loc_180004A67
0x180004a5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004a62  mov     [rsp+68h+hKey], rcx
0x180004a67  lea     rax, [rsp+68h+dwDisposition]
0x180004a6c  mov     ebp, 1
0x180004a71  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180004a76  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Volatile-AutoEnrol"...
0x180004a7d  lea     rax, [rsp+68h+arg_10]
0x180004a85  xor     r9d, r9d; lpClass
0x180004a88  mov     [rsp+68h+phkResult], rax; phkResult
0x180004a8d  xor     r8d, r8d; Reserved
0x180004a90  mov     [rsp+68h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180004a95  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180004a9d  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x180004aa1  call    cs:__imp_RegCreateKeyExW
0x180004aa7  test    eax, eax
0x180004aa9  jz      short loc_180004AB8
0x180004aab  mov     [rsp+68h+arg_10], rsi
0x180004ab3  jmp     loc_180004A26
0x180004ab8  cmp     [rsp+68h+dwDisposition], ebp
0x180004abc  cmovz   edi, ebp
0x180004abf  jmp     loc_180004A15
0x180004ac4  call    cs:__imp_RegCloseKey
0x180004aca  jmp     loc_180004A26
```
