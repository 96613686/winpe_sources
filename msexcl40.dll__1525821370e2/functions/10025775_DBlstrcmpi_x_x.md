# DBlstrcmpi(x,x)

- ea: `0x10025775`
- end: `0x10025791`
- name: `_DBlstrcmpi@8`
- size: `28`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `14`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x100255d7`
- `0x10027bb8`
- `0x10027bfb`
- `0x10027e33`
- `0x1002838d`
- `0x100283fc`
- `0x10028701`
- `0x10029648`
- `0x100296d0`
- `0x1002ab9e`
- `0x1002ae15`
- `0x1002aea1`
- `0x1002b580`
- `0x1002fa03`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x10025780`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x10025780`
- `mswstr10!__imp__DBCompareStringW@24` at `0x10025787`
- `mswstr10!__imp__DBCompareStringW@24` at `0x10025787`

## pseudocode

```c
int __fastcall DBlstrcmpi(int a1, int a2)
{
  LCID UserDefaultLCID; // eax

  UserDefaultLCID = GetUserDefaultLCID();
  return DBCompareStringW(UserDefaultLCID, 196609, a1, -1, a2, -1) - 2;
}

```

## disassembly

```asm
0x10025775  push    0FFFFFFFFh
0x10025777  push    edx
0x10025778  push    0FFFFFFFFh
0x1002577a  push    ecx
0x1002577b  push    30001h
0x10025780  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x10025786  push    eax
0x10025787  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1002578d  sub     eax, 2
0x10025790  retn
```
