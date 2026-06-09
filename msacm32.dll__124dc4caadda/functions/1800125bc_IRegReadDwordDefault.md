# IRegReadDwordDefault

- ea: `0x1800125bc`
- end: `0x180012618`
- name: `IRegReadDwordDefault`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005e70`

## callees

- `0x1800125bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012601`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012601`

## pseudocode

```c
__int64 __fastcall IRegReadDwordDefault(HKEY a1, __int64 a2)
{
  DWORD v3; // [rsp+48h] [rbp+10h] BYREF
  int v4; // [rsp+4Ch] [rbp+14h]
  unsigned int v5; // [rsp+50h] [rbp+18h] BYREF
  DWORD v6; // [rsp+58h] [rbp+20h] BYREF

  v4 = HIDWORD(a2);
  v6 = -5;
  v3 = 4;
  v5 = 0;
  if ( RegQueryValueExW(a1, L"NoPCMConverter", 0, &v6, (LPBYTE)&v5, &v3) )
    return 0;
  else
    return v5;
}

```

## disassembly

```asm
0x1800125bc  mov     r11, rsp
0x1800125bf  mov     [r11+18h], r8d
0x1800125c3  mov     [r11+10h], rdx
0x1800125c7  sub     rsp, 38h
0x1800125cb  lea     rax, [r11+10h]
0x1800125cf  mov     [rsp+38h+arg_18], 0FFFFFFFBh
0x1800125d7  mov     [r11-10h], rax
0x1800125db  lea     r9, [r11+20h]; lpType
0x1800125df  lea     rax, [r11+18h]
0x1800125e3  mov     [rsp+38h+arg_8], 4
0x1800125eb  xor     r8d, r8d; lpReserved
0x1800125ee  mov     [r11-18h], rax
0x1800125f2  lea     rdx, gszKeyNoPCMConverter; "NoPCMConverter"
0x1800125f9  mov     [rsp+38h+arg_10], 0
0x180012601  call    cs:__imp_RegQueryValueExW
0x180012607  test    eax, eax
0x180012609  jz      short loc_18001260F
0x18001260b  xor     eax, eax
0x18001260d  jmp     short loc_180012613
0x18001260f  mov     eax, [rsp+38h+arg_10]
0x180012613  add     rsp, 38h
0x180012617  retn
```
