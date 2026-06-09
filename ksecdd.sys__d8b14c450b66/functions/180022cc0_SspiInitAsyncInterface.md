# SspiInitAsyncInterface

- ea: `0x180022cc0`
- end: `0x180022d31`
- name: `SspiInitAsyncInterface`
- size: `113`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002b078`

## callees

- `0x180007ba8`
- `0x180022cc0`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x180022d1f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x180022d1f`

## pseudocode

```c
NTSTATUS SspiInitAsyncInterface()
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, WPP_2a384669bb243b9a28be691c859cfe55_Traceguids);
  return ExInitializeLookasideListEx(&stru_180019690, 0, 0, PagedPool, 0, 0xF0u, 0x69707373u, 0);
}

```

## disassembly

```asm
0x180022cc0  sub     rsp, 48h
0x180022cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ccb  lea     rax, WPP_GLOBAL_Control
0x180022cd2  cmp     rcx, rax
0x180022cd5  jz      short loc_180022CF3
0x180022cd7  mov     eax, [rcx+2Ch]
0x180022cda  test    al, 4
0x180022cdc  jz      short loc_180022CF3
0x180022cde  mov     rcx, [rcx+18h]
0x180022ce2  lea     r8, WPP_2a384669bb243b9a28be691c859cfe55_Traceguids
0x180022ce9  mov     edx, 0Ah
0x180022cee  call    WPP_SF_
0x180022cf3  xor     eax, eax
0x180022cf5  lea     rcx, stru_180019690; Lookaside
0x180022cfc  mov     [rsp+48h+Depth], ax; Depth
0x180022d01  xor     r8d, r8d; Free
0x180022d04  mov     [rsp+48h+Tag], 69707373h; Tag
0x180022d0c  xor     edx, edx; Allocate
0x180022d0e  mov     [rsp+48h+Size], 0F0h; Size
0x180022d17  lea     r9d, [rax+1]; PoolType
0x180022d1b  mov     [rsp+48h+Flags], eax; Flags
0x180022d1f  call    cs:__imp_ExInitializeLookasideListEx
0x180022d26  nop     dword ptr [rax+rax+00h]
0x180022d2b  add     rsp, 48h
0x180022d2f  retn
```
