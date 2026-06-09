# RassrvRegSetStr

- ea: `0x180021a5c`
- end: `0x180021aec`
- name: `RassrvRegSetStr`
- size: `144`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180028c40`

## callees

- `0x180021a5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021adb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021adb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021a9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021a9a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021ac9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021ac9`

## pseudocode

```c
__int64 __fastcall RassrvRegSetStr(BYTE *lpData, const WCHAR *a2)
{
  __int64 v3; // rbx
  unsigned int v4; // edi
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20006u, &hKey);
  if ( !v4 )
    v4 = RegSetValueExW(hKey, L"NetworkAdapterGUID", 0, 1u, lpData, 2 * v3 + 2);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180021a5c  mov     [rsp+hKey], r8
0x180021a61  push    rbx
0x180021a62  push    rbp
0x180021a63  push    rsi
0x180021a64  push    rdi
0x180021a65  sub     rsp, 38h
0x180021a69  xor     ebp, ebp
0x180021a6b  mov     rsi, rcx
0x180021a6e  mov     [rsp+58h+hKey], rbp
0x180021a73  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021a77  inc     rbx
0x180021a7a  cmp     [rcx+rbx*2], bp
0x180021a7e  jnz     short loc_180021A77
0x180021a80  lea     rax, [rsp+58h+hKey]
0x180021a85  mov     r9d, 20006h; samDesired
0x180021a8b  xor     r8d, r8d; ulOptions
0x180021a8e  mov     [rsp+58h+phkResult], rax; phkResult
0x180021a93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021a9a  call    cs:__imp_RegOpenKeyExW
0x180021aa0  mov     edi, eax
0x180021aa2  test    eax, eax
0x180021aa4  jnz     short loc_180021AD1
0x180021aa6  mov     rcx, [rsp+58h+hKey]; hKey
0x180021aab  lea     eax, ds:2[rbx*2]
0x180021ab2  mov     [rsp+58h+cbData], eax; cbData
0x180021ab6  lea     r9d, [rdi+1]; dwType
0x180021aba  xor     r8d, r8d; Reserved
0x180021abd  mov     [rsp+58h+phkResult], rsi; lpData
0x180021ac2  lea     rdx, Type; "NetworkAdapterGUID"
0x180021ac9  call    cs:__imp_RegSetValueExW
0x180021acf  mov     edi, eax
0x180021ad1  mov     rcx, [rsp+58h+hKey]; hKey
0x180021ad6  test    rcx, rcx
0x180021ad9  jz      short loc_180021AE1
0x180021adb  call    cs:__imp_RegCloseKey
0x180021ae1  mov     eax, edi
0x180021ae3  add     rsp, 38h
0x180021ae7  pop     rdi
0x180021ae8  pop     rsi
0x180021ae9  pop     rbp
0x180021aea  pop     rbx
0x180021aeb  retn
```
