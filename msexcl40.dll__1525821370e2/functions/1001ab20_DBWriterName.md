# DBWriterName

- ea: `0x1001ab20`
- end: `0x1001ab5a`
- name: `DBWriterName`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001ab36`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001ab36`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001ab3d`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001ab3d`

## pseudocode

```c
int __stdcall DBWriterName(int a1)
{
  LCID UserDefaultLCID; // eax

  UserDefaultLCID = GetUserDefaultLCID();
  *(_DWORD *)(dword_1003A9BC + 24) = DBCompareStringW(
                                       UserDefaultLCID,
                                       196609,
                                       a1,
                                       -1,
                                       L"A satisfied Microsoft Office user                     ",
                                       -1) == 2;
  return 0;
}

```

## disassembly

```asm
0x1001ab20  mov     edi, edi
0x1001ab22  push    ebp
0x1001ab23  mov     ebp, esp
0x1001ab25  push    0FFFFFFFFh
0x1001ab27  push    offset aASatisfiedMicr; "A satisfied Microsoft Office user      "...
0x1001ab2c  push    0FFFFFFFFh
0x1001ab2e  push    [ebp+arg_0]
0x1001ab31  push    30001h
0x1001ab36  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1001ab3c  push    eax
0x1001ab3d  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1001ab43  mov     ecx, dword_1003A9BC
0x1001ab49  sub     eax, 2
0x1001ab4c  neg     eax
0x1001ab4e  sbb     eax, eax
0x1001ab50  inc     eax
0x1001ab51  mov     [ecx+18h], eax
0x1001ab54  xor     eax, eax
0x1001ab56  pop     ebp
0x1001ab57  retn    4
```
