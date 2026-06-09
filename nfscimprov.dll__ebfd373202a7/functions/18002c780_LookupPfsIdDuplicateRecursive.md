# LookupPfsIdDuplicateRecursive

- ea: `0x18002c780`
- end: `0x18002c80d`
- name: `LookupPfsIdDuplicateRecursive`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002c5d4`

## callees

- `0x18002c5d4`
- `0x18002c780`
- `0x18002c964`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002c7d0`
- `ADVAPI32!RegOpenKeyExW` at `0x18002c7d0`
- `CLUSAPI!ClusterRegOpenKey` at `0x18002c7b2`
- `CLUSAPI!ClusterRegOpenKey` at `0x18002c7b2`

## pseudocode

```c
__int64 __fastcall LookupPfsIdDuplicateRecursive(HKEY a1, char a2, const WCHAR *a3)
{
  LONG v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  HKEY hKey[3]; // [rsp+30h] [rbp-18h] BYREF

  hKey[0] = 0;
  if ( a2 )
    v4 = ClusterRegOpenKey(a1, a3, 0x20019u, hKey);
  else
    v4 = RegOpenKeyExW(a1, a3, 0, 0x20019u, hKey);
  v5 = v4;
  if ( !v4 )
  {
    v6 = LookupPfsIdDuplicate(hKey[0]);
    LOBYTE(v7) = a2;
    v5 = v6;
    NfsPFsCloseKey(hKey[0], v7);
  }
  return v5;
}

```

## disassembly

```asm
0x18002c780  mov     r11, rsp
0x18002c783  mov     [r11+8], rbx
0x18002c787  mov     [r11+10h], rsi
0x18002c78b  push    rdi
0x18002c78c  sub     rsp, 40h
0x18002c790  mov     qword ptr [r11-18h], 0
0x18002c798  mov     esi, r9d
0x18002c79b  mov     rax, r8
0x18002c79e  mov     dil, dl
0x18002c7a1  test    dl, dl
0x18002c7a3  jz      short loc_18002C7BA
0x18002c7a5  lea     r9, [r11-18h]; phkResult
0x18002c7a9  mov     r8d, 20019h; samDesired
0x18002c7af  mov     rdx, rax; lpszSubKey
0x18002c7b2  call    cs:__imp_ClusterRegOpenKey
0x18002c7b8  jmp     short loc_18002C7D6
0x18002c7ba  lea     rdx, [rsp+48h+hKey]
0x18002c7bf  mov     r9d, 20019h; samDesired
0x18002c7c5  mov     [rsp+48h+phkResult], rdx; phkResult
0x18002c7ca  xor     r8d, r8d; ulOptions
0x18002c7cd  mov     rdx, rax; lpSubKey
0x18002c7d0  call    cs:__imp_RegOpenKeyExW
0x18002c7d6  mov     ebx, eax
0x18002c7d8  test    eax, eax
0x18002c7da  jnz     short loc_18002C7FB
0x18002c7dc  mov     rcx, [rsp+48h+hKey]; hKey
0x18002c7e1  mov     r8d, esi
0x18002c7e4  mov     dl, dil
0x18002c7e7  call    LookupPfsIdDuplicate
0x18002c7ec  mov     rcx, [rsp+48h+hKey]
0x18002c7f1  mov     dl, dil
0x18002c7f4  mov     ebx, eax
0x18002c7f6  call    NfsPFsCloseKey
0x18002c7fb  mov     rsi, [rsp+48h+arg_8]
0x18002c800  mov     eax, ebx
0x18002c802  mov     rbx, [rsp+48h+arg_0]
0x18002c807  add     rsp, 40h
0x18002c80b  pop     rdi
0x18002c80c  retn
```
