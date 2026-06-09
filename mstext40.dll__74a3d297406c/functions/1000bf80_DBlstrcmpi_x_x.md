# DBlstrcmpi(x,x)

- ea: `0x1000bf80`
- end: `0x1000bfa3`
- name: `_DBlstrcmpi@8`
- size: `35`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1000a470`
- `0x1000f530`
- `0x10010020`
- `0x100108e0`
- `0x10013ff0`
- `0x10014560`
- `0x100146d0`
- `0x10014740`
- `0x100170e0`
- `0x10018200`
- `0x1001f320`
- `0x1001f730`
- `0x1001fcd0`
- `0x10026ec0`
- `0x10026fd0`
- `0x100283b0`

## callees

- `0x1002b674`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x1000bf91`
- `KERNEL32!GetUserDefaultLCID` at `0x1000bf91`

## pseudocode

```c
int __stdcall DBlstrcmpi(int a1, int a2)
{
  LCID UserDefaultLCID; // eax

  UserDefaultLCID = GetUserDefaultLCID();
  return DBCompareStringW(UserDefaultLCID, 196609, a1, -1, a2, -1) - 2;
}

```

## disassembly

```asm
0x1000bf80  push    0FFFFFFFFh
0x1000bf82  push    [esp+4+arg_4]
0x1000bf86  push    0FFFFFFFFh
0x1000bf88  push    [esp+0Ch+arg_0]
0x1000bf8c  push    30001h
0x1000bf91  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1000bf97  push    eax
0x1000bf98  call    _DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1000bf9d  sub     eax, 2
0x1000bfa0  retn    8
```
