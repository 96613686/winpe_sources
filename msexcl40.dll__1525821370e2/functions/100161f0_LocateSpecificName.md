# LocateSpecificName

- ea: `0x100161f0`
- end: `0x10016231`
- name: `LocateSpecificName`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100161f0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001620a`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001620a`
- `mswstr10!__imp__DBCompareStringW@24` at `0x10016211`
- `mswstr10!__imp__DBCompareStringW@24` at `0x10016211`

## pseudocode

```c
BOOL __stdcall LocateSpecificName(int a1, int a2, int a3, int a4, int a5)
{
  LCID UserDefaultLCID; // eax

  UserDefaultLCID = GetUserDefaultLCID();
  return DBCompareStringW(UserDefaultLCID, 196609, dword_1003A7A0, -1, a3, -1) == 2 && dword_1003A788 == a4;
}

```

## disassembly

```asm
0x100161f0  mov     edi, edi
0x100161f2  push    ebp
0x100161f3  mov     ebp, esp
0x100161f5  push    esi
0x100161f6  mov     esi, [ebp+arg_C]
0x100161f9  push    0FFFFFFFFh
0x100161fb  push    [ebp+arg_8]
0x100161fe  push    0FFFFFFFFh
0x10016200  push    offset dword_1003A7A0
0x10016205  push    30001h
0x1001620a  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x10016210  push    eax
0x10016211  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x10016217  sub     eax, 2
0x1001621a  jnz     short loc_1001622A
0x1001621c  cmp     dword_1003A788, esi
0x10016222  pop     esi
0x10016223  setz    al
0x10016226  pop     ebp
0x10016227  retn    14h
0x1001622a  xor     eax, eax
0x1001622c  pop     esi
0x1001622d  pop     ebp
0x1001622e  retn    14h
```
