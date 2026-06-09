# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18000b0ec`
- end: `0x18000b1a4`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac18`
- `0x18000ac54`
- `0x1800105f8`

## callees

- `0x18000b0ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b187`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b187`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b175`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b175`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b13c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b13c`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData)
{
  HKEY v8; // rbx
  unsigned int v9; // edi
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  v8 = a1;
  if ( a2 && *a2 )
  {
    v9 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v9 )
      return v9;
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v9 = RegSetValueExW(a1, a3, 0, a4, lpData, cbData);
  if ( hKey != v8 )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18000b0ec  mov     r11, rsp
0x18000b0ef  mov     [r11+8], rbx
0x18000b0f3  mov     [r11+18h], rbp
0x18000b0f7  push    rsi
0x18000b0f8  push    rdi
0x18000b0f9  push    r14
0x18000b0fb  sub     rsp, 50h
0x18000b0ff  xor     r14d, r14d
0x18000b102  mov     esi, r9d
0x18000b105  mov     [r11+10h], r14
0x18000b109  mov     rbp, r8
0x18000b10c  mov     rbx, rcx
0x18000b10f  test    rdx, rdx
0x18000b112  jz      short loc_18000B14F
0x18000b114  cmp     [rdx], r14w
0x18000b118  jz      short loc_18000B14F
0x18000b11a  mov     [r11-28h], r14
0x18000b11e  lea     rax, [r11+10h]
0x18000b122  mov     [r11-30h], rax
0x18000b126  xor     r9d, r9d; lpClass
0x18000b129  mov     [r11-38h], r14
0x18000b12d  xor     r8d, r8d; Reserved
0x18000b130  mov     [rsp+68h+samDesired], 2; samDesired
0x18000b138  mov     [r11-48h], r14d
0x18000b13c  call    cs:__imp_RegCreateKeyExW
0x18000b142  mov     edi, eax
0x18000b144  test    eax, eax
0x18000b146  jnz     short loc_18000B18D
0x18000b148  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b14d  jmp     short loc_18000B154
0x18000b14f  mov     [rsp+68h+hKey], rbx
0x18000b154  mov     eax, [rsp+68h+cbData]
0x18000b15b  mov     r9d, esi; dwType
0x18000b15e  mov     [rsp+68h+samDesired], eax; cbData
0x18000b162  xor     r8d, r8d; Reserved
0x18000b165  mov     rax, [rsp+68h+arg_20]
0x18000b16d  mov     rdx, rbp; lpValueName
0x18000b170  mov     [rsp+68h+lpData], rax; lpData
0x18000b175  call    cs:__imp_RegSetValueExW
0x18000b17b  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b180  mov     edi, eax
0x18000b182  cmp     rcx, rbx
0x18000b185  jz      short loc_18000B18D
0x18000b187  call    cs:__imp_RegCloseKey
0x18000b18d  lea     r11, [rsp+68h+var_18]
0x18000b192  mov     eax, edi
0x18000b194  mov     rbx, [r11+20h]
0x18000b198  mov     rbp, [r11+30h]
0x18000b19c  mov     rsp, r11
0x18000b19f  pop     r14
0x18000b1a1  pop     rdi
0x18000b1a2  pop     rsi
0x18000b1a3  retn
```
