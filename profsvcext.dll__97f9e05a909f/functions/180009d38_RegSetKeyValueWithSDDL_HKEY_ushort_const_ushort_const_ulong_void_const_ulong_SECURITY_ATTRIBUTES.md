# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180009d38`
- end: `0x180009df3`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d08`

## callees

- `0x180009d38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ddb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ddb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009dc5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009dc5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009d88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009d88`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x180009d38  mov     r11, rsp
0x180009d3b  mov     [r11+10h], rbp
0x180009d3f  mov     [r11+18h], rsi
0x180009d43  mov     [r11+8], rcx
0x180009d47  push    rdi
0x180009d48  sub     rsp, 50h
0x180009d4c  xor     ebp, ebp
0x180009d4e  mov     rsi, r8
0x180009d51  mov     [r11+8], rbp
0x180009d55  test    rdx, rdx
0x180009d58  jz      short loc_180009D9B
0x180009d5a  cmp     [rdx], bp
0x180009d5d  jz      short loc_180009D9B
0x180009d5f  mov     [r11-18h], rbp
0x180009d63  lea     rax, [r11+8]
0x180009d67  mov     [r11-20h], rax
0x180009d6b  xor     r9d, r9d; lpClass
0x180009d6e  mov     [r11-28h], rbp
0x180009d72  xor     r8d, r8d; Reserved
0x180009d75  mov     [rsp+58h+samDesired], 2; samDesired
0x180009d7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009d84  mov     [rsp+58h+dwOptions], ebp; dwOptions
0x180009d88  call    cs:__imp_RegCreateKeyExW
0x180009d8e  mov     edi, eax
0x180009d90  test    eax, eax
0x180009d92  jnz     short loc_180009DE1
0x180009d94  mov     rcx, [rsp+58h+hKey]
0x180009d99  jmp     short loc_180009DA7
0x180009d9b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009da2  mov     [rsp+58h+hKey], rcx
0x180009da7  mov     rax, [rsp+58h+lpData]
0x180009daf  mov     r9d, 4; dwType
0x180009db5  mov     [rsp+58h+samDesired], r9d; cbData
0x180009dba  xor     r8d, r8d; Reserved
0x180009dbd  mov     rdx, rsi; lpValueName
0x180009dc0  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180009dc5  call    cs:__imp_RegSetValueExW
0x180009dcb  mov     rcx, [rsp+58h+hKey]; hKey
0x180009dd0  mov     edi, eax
0x180009dd2  cmp     rcx, 0FFFFFFFF80000002h
0x180009dd9  jz      short loc_180009DE1
0x180009ddb  call    cs:__imp_RegCloseKey
0x180009de1  mov     rbp, [rsp+58h+arg_8]
0x180009de6  mov     eax, edi
0x180009de8  mov     rsi, [rsp+58h+arg_10]
0x180009ded  add     rsp, 50h
0x180009df1  pop     rdi
0x180009df2  retn
```
