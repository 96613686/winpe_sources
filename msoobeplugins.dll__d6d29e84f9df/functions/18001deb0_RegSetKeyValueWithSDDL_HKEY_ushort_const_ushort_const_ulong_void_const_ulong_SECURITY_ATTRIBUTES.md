# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18001deb0`
- end: `0x18001df68`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001de58`
- `0x18002d0e0`
- `0x180046c9c`
- `0x18006b8fc`
- `0x1800aecd4`

## callees

- `0x18001deb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001df39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001df39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df4b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001df00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001df00`

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
0x18001deb0  mov     r11, rsp
0x18001deb3  mov     [r11+8], rbx
0x18001deb7  mov     [r11+18h], rbp
0x18001debb  push    rsi
0x18001debc  push    rdi
0x18001debd  push    r14
0x18001debf  sub     rsp, 50h
0x18001dec3  xor     r14d, r14d
0x18001dec6  mov     esi, r9d
0x18001dec9  mov     [r11+10h], r14
0x18001decd  mov     rbp, r8
0x18001ded0  mov     rbx, rcx
0x18001ded3  test    rdx, rdx
0x18001ded6  jz      short loc_18001DF13
0x18001ded8  cmp     [rdx], r14w
0x18001dedc  jz      short loc_18001DF13
0x18001dede  mov     [r11-28h], r14
0x18001dee2  lea     rax, [r11+10h]
0x18001dee6  mov     [r11-30h], rax
0x18001deea  xor     r9d, r9d; lpClass
0x18001deed  mov     [r11-38h], r14
0x18001def1  xor     r8d, r8d; Reserved
0x18001def4  mov     [rsp+68h+samDesired], 2; samDesired
0x18001defc  mov     [r11-48h], r14d
0x18001df00  call    cs:__imp_RegCreateKeyExW
0x18001df06  mov     edi, eax
0x18001df08  test    eax, eax
0x18001df0a  jnz     short loc_18001DF51
0x18001df0c  mov     rcx, [rsp+68h+hKey]; hKey
0x18001df11  jmp     short loc_18001DF18
0x18001df13  mov     [rsp+68h+hKey], rbx
0x18001df18  mov     eax, [rsp+68h+cbData]
0x18001df1f  mov     r9d, esi; dwType
0x18001df22  mov     [rsp+68h+samDesired], eax; cbData
0x18001df26  xor     r8d, r8d; Reserved
0x18001df29  mov     rax, [rsp+68h+arg_20]
0x18001df31  mov     rdx, rbp; lpValueName
0x18001df34  mov     [rsp+68h+lpData], rax; lpData
0x18001df39  call    cs:__imp_RegSetValueExW
0x18001df3f  mov     rcx, [rsp+68h+hKey]; hKey
0x18001df44  mov     edi, eax
0x18001df46  cmp     rcx, rbx
0x18001df49  jz      short loc_18001DF51
0x18001df4b  call    cs:__imp_RegCloseKey
0x18001df51  lea     r11, [rsp+68h+var_18]
0x18001df56  mov     eax, edi
0x18001df58  mov     rbx, [r11+20h]
0x18001df5c  mov     rbp, [r11+30h]
0x18001df60  mov     rsp, r11
0x18001df63  pop     r14
0x18001df65  pop     rdi
0x18001df66  pop     rsi
0x18001df67  retn
```
