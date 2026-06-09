# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180014e6c`
- end: `0x180014f27`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `187`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013654`
- `0x18001510c`

## callees

- `0x180014e6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f0f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014ebc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014ebc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014ef9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014ef9`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData)
{
  unsigned int v6; // edi
  HKEY v7; // rcx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v6 )
      return v6;
    v7 = hKey;
  }
  else
  {
    v7 = HKEY_LOCAL_MACHINE;
    hKey = HKEY_LOCAL_MACHINE;
  }
  v6 = RegSetValueExW(v7, a3, 0, 4u, lpData, 4u);
  if ( hKey != HKEY_LOCAL_MACHINE )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180014e6c  mov     r11, rsp
0x180014e6f  mov     [r11+10h], rbp
0x180014e73  mov     [r11+18h], rsi
0x180014e77  mov     [r11+8], rcx
0x180014e7b  push    rdi
0x180014e7c  sub     rsp, 50h
0x180014e80  xor     ebp, ebp
0x180014e82  mov     rsi, r8
0x180014e85  mov     [r11+8], rbp
0x180014e89  test    rdx, rdx
0x180014e8c  jz      short loc_180014ECF
0x180014e8e  cmp     [rdx], bp
0x180014e91  jz      short loc_180014ECF
0x180014e93  mov     [r11-18h], rbp
0x180014e97  lea     rax, [r11+8]
0x180014e9b  mov     [r11-20h], rax
0x180014e9f  xor     r9d, r9d; lpClass
0x180014ea2  mov     [r11-28h], rbp
0x180014ea6  xor     r8d, r8d; Reserved
0x180014ea9  mov     [rsp+58h+samDesired], 2; samDesired
0x180014eb1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014eb8  mov     [rsp+58h+dwOptions], ebp; dwOptions
0x180014ebc  call    cs:__imp_RegCreateKeyExW
0x180014ec2  mov     edi, eax
0x180014ec4  test    eax, eax
0x180014ec6  jnz     short loc_180014F15
0x180014ec8  mov     rcx, [rsp+58h+hKey]
0x180014ecd  jmp     short loc_180014EDB
0x180014ecf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014ed6  mov     [rsp+58h+hKey], rcx
0x180014edb  mov     rax, [rsp+58h+lpData]
0x180014ee3  mov     r9d, 4; dwType
0x180014ee9  mov     [rsp+58h+samDesired], r9d; cbData
0x180014eee  xor     r8d, r8d; Reserved
0x180014ef1  mov     rdx, rsi; lpValueName
0x180014ef4  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180014ef9  call    cs:__imp_RegSetValueExW
0x180014eff  mov     rcx, [rsp+58h+hKey]; hKey
0x180014f04  mov     edi, eax
0x180014f06  cmp     rcx, 0FFFFFFFF80000002h
0x180014f0d  jz      short loc_180014F15
0x180014f0f  call    cs:__imp_RegCloseKey
0x180014f15  mov     rbp, [rsp+58h+arg_8]
0x180014f1a  mov     eax, edi
0x180014f1c  mov     rsi, [rsp+58h+arg_10]
0x180014f21  add     rsp, 50h
0x180014f25  pop     rdi
0x180014f26  retn
```
