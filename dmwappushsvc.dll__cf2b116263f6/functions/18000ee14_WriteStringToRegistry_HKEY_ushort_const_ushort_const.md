# WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18000ee14`
- end: `0x18000eec5`
- name: `?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `177`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ffa0`

## callees

- `0x18000bcf8`
- `0x18000ec68`
- `0x18000ee14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ee93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ee93`

## pseudocode

```c
__int64 __fastcall WriteStringToRegistry(HKEY hKey, LPCWSTR lpValueName, const unsigned __int16 *a3)
{
  int v6; // ebx
  unsigned __int64 v7; // rcx
  const BYTE *lpData; // r11
  LSTATUS v9; // eax
  unsigned __int64 cbData; // [rsp+50h] [rbp+18h] BYREF

  cbData = 0;
  if ( !a3 )
    return 0;
  v6 = StringCbLengthW(a3, (unsigned __int64)lpValueName, &cbData);
  if ( v6 >= 0 )
  {
    v7 = cbData + 2;
    if ( cbData + 2 < cbData )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      LODWORD(cbData) = 0;
      v6 = ULongLongToULong(v7, (unsigned int *)&cbData);
      if ( v6 >= 0 )
      {
        v9 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, cbData);
        if ( v9 )
        {
          if ( v9 > 0 )
            return (unsigned __int16)v9 | 0x80070000;
          else
            return (unsigned int)v9;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ee14  mov     [rsp+arg_0], rbx
0x18000ee19  mov     [rsp+arg_8], rsi
0x18000ee1e  push    rdi
0x18000ee1f  sub     rsp, 30h
0x18000ee23  mov     [rsp+38h+arg_10], 0
0x18000ee2c  mov     r11, r8
0x18000ee2f  mov     rdi, rdx
0x18000ee32  mov     rsi, rcx
0x18000ee35  test    r8, r8
0x18000ee38  jnz     short loc_18000EE3E
0x18000ee3a  xor     eax, eax
0x18000ee3c  jmp     short loc_18000EEB5
0x18000ee3e  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x18000ee43  mov     rcx, r11; unsigned __int16 *
0x18000ee46  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ee4b  mov     ebx, eax
0x18000ee4d  test    eax, eax
0x18000ee4f  js      short loc_18000EEB3
0x18000ee51  mov     rax, [rsp+38h+arg_10]
0x18000ee56  lea     rcx, [rax+2]; unsigned __int64
0x18000ee5a  cmp     rcx, rax
0x18000ee5d  jb      short loc_18000EEAE
0x18000ee5f  lea     rdx, [rsp+38h+arg_10]; unsigned int *
0x18000ee64  mov     dword ptr [rsp+38h+arg_10], 0
0x18000ee6c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000ee71  mov     ebx, eax
0x18000ee73  test    eax, eax
0x18000ee75  js      short loc_18000EEB3
0x18000ee77  mov     eax, dword ptr [rsp+38h+arg_10]
0x18000ee7b  mov     r9d, 1; dwType
0x18000ee81  mov     [rsp+38h+cbData], eax; cbData
0x18000ee85  xor     r8d, r8d; Reserved
0x18000ee88  mov     rdx, rdi; lpValueName
0x18000ee8b  mov     [rsp+38h+lpData], r11; lpData
0x18000ee90  mov     rcx, rsi; hKey
0x18000ee93  call    cs:__imp_RegSetValueExW
0x18000ee99  test    eax, eax
0x18000ee9b  jz      short loc_18000EEB3
0x18000ee9d  jg      short loc_18000EEA3
0x18000ee9f  mov     ebx, eax
0x18000eea1  jmp     short loc_18000EEB3
0x18000eea3  movzx   ebx, ax
0x18000eea6  or      ebx, 80070000h
0x18000eeac  jmp     short loc_18000EEB3
0x18000eeae  mov     ebx, 80070216h
0x18000eeb3  mov     eax, ebx
0x18000eeb5  mov     rbx, [rsp+38h+arg_0]
0x18000eeba  mov     rsi, [rsp+38h+arg_8]
0x18000eebf  add     rsp, 30h
0x18000eec3  pop     rdi
0x18000eec4  retn
```
