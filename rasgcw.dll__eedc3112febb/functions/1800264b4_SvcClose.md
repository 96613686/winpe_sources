# SvcClose

- ea: `0x1800264b4`
- end: `0x1800264f4`
- name: `SvcClose`
- size: `64`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001ffac`
- `0x180020098`
- `0x180020240`
- `0x1800209f8`
- `0x180028f8c`
- `0x180029fc0`

## callees

- `0x180021470`
- `0x1800264b4`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800264d0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800264de`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800264d0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800264de`

## pseudocode

```c
__int64 __fastcall SvcClose(SC_HANDLE *lpMem)
{
  SC_HANDLE v3; // rcx

  if ( !lpMem )
    return 87;
  v3 = lpMem[1];
  if ( v3 )
    CloseServiceHandle(v3);
  if ( *lpMem )
    CloseServiceHandle(*lpMem);
  RassrvFree(lpMem);
  return 0;
}

```

## disassembly

```asm
0x1800264b4  push    rbx
0x1800264b6  sub     rsp, 20h
0x1800264ba  mov     rbx, rcx
0x1800264bd  test    rcx, rcx
0x1800264c0  jnz     short loc_1800264C7
0x1800264c2  lea     eax, [rcx+57h]
0x1800264c5  jmp     short loc_1800264EE
0x1800264c7  mov     rcx, [rcx+8]; hSCObject
0x1800264cb  test    rcx, rcx
0x1800264ce  jz      short loc_1800264D6
0x1800264d0  call    cs:__imp_CloseServiceHandle
0x1800264d6  mov     rcx, [rbx]; hSCObject
0x1800264d9  test    rcx, rcx
0x1800264dc  jz      short loc_1800264E4
0x1800264de  call    cs:__imp_CloseServiceHandle
0x1800264e4  mov     rcx, rbx; lpMem
0x1800264e7  call    RassrvFree
0x1800264ec  xor     eax, eax
0x1800264ee  add     rsp, 20h
0x1800264f2  pop     rbx
0x1800264f3  retn
```
