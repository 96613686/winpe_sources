# OaDeleteCriticalSection

- ea: `0x180022838`
- end: `0x180022866`
- name: `OaDeleteCriticalSection`
- size: `46`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18002214c`
- `0x180022770`
- `0x1800227dc`
- `0x180022bc0`
- `0x180023560`
- `0x18002394c`
- `0x180023f54`
- `0x180024000`

## callees

- `0x180022838`
- `0x18009a618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002285a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002285a`

## pseudocode

```c
void __fastcall OaDeleteCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  if ( memcmp_0(lpCriticalSection, `IsCriticalSectionZeroed'::`2'::z, 0x28u) )
    DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180022838  push    rbx
0x18002283a  sub     rsp, 20h
0x18002283e  mov     r8d, 28h ; '('; Size
0x180022844  lea     rdx, ?z@?1??IsCriticalSectionZeroed@@YAHPEAU_RTL_CRITICAL_SECTION@@@Z@4U2@A; Buf2
0x18002284b  mov     rbx, rcx
0x18002284e  call    memcmp_0
0x180022853  test    eax, eax
0x180022855  jz      short loc_180022860
0x180022857  mov     rcx, rbx; lpCriticalSection
0x18002285a  call    cs:__imp_DeleteCriticalSection
0x180022860  add     rsp, 20h
0x180022864  pop     rbx
0x180022865  retn
```
