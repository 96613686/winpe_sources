# GetRegistryKey(HKEY__ *,ushort *,HKEY__ * *,VERSION_ARCHITECTURE)

- ea: `0x18000abd0`
- end: `0x18000ac25`
- name: `?GetRegistryKey@@YAJPEAUHKEY__@@PEAGPEAPEAU1@W4VERSION_ARCHITECTURE@@@Z`
- size: `85`
- prototype: `LSTATUS __fastcall(HKEY, __int64, __int64, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000aa50`
- `0x18000ac2c`
- `0x18000af8c`
- `0x180032c00`

## callees

- `0x1800067d0`
- `0x18000abd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000abfd`
- `ADVAPI32!RegOpenKeyExW` at `0x18000abfd`

## pseudocode

```c
LSTATUS __fastcall GetRegistryKey(HKEY a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int RegFlags; // eax
  PHKEY phkResult; // r10
  LPCWSTR v7; // r11
  LSTATUS result; // eax

  RegFlags = GetRegFlags(a4);
  result = RegOpenKeyExW(a1, v7, 0, RegFlags | 0x20019, phkResult);
  if ( result )
  {
    if ( result == 2 )
    {
      return 1;
    }
    else if ( result > 0 )
    {
      return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000abd0  push    rbx
0x18000abd2  sub     rsp, 30h
0x18000abd6  mov     rbx, rcx
0x18000abd9  mov     r10, r8
0x18000abdc  mov     ecx, r9d
0x18000abdf  mov     r11, rdx
0x18000abe2  call    ?GetRegFlags@@YAKW4VERSION_ARCHITECTURE@@@Z; GetRegFlags(VERSION_ARCHITECTURE)
0x18000abe7  or      eax, 20019h
0x18000abec  mov     [rsp+38h+phkResult], r10; phkResult
0x18000abf1  mov     r9d, eax; samDesired
0x18000abf4  xor     r8d, r8d; ulOptions
0x18000abf7  mov     rdx, r11; lpSubKey
0x18000abfa  mov     rcx, rbx; hKey
0x18000abfd  call    cs:__imp_RegOpenKeyExW
0x18000ac03  test    eax, eax
0x18000ac05  jz      short loc_18000AC1F
0x18000ac07  cmp     eax, 2
0x18000ac0a  jnz     short loc_18000AC13
0x18000ac0c  mov     eax, 1
0x18000ac11  jmp     short loc_18000AC1F
0x18000ac13  test    eax, eax
0x18000ac15  jle     short loc_18000AC1F
0x18000ac17  movzx   eax, ax
0x18000ac1a  or      eax, 80070000h
0x18000ac1f  add     rsp, 30h
0x18000ac23  pop     rbx
0x18000ac24  retn
```
