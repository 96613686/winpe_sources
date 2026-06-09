# FveHwAccelCleanup

- ea: `0x1400cb170`
- end: `0x1400cb215`
- name: `FveHwAccelCleanup`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14006f658`

## callees

- `0x1400cb170`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400cb1cc`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400cb1cc`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cb202`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cb202`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb1e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb1e4`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyOffloadWorkspace` at `0x1400cb1a9`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyOffloadWorkspace` at `0x1400cb1a9`
- `ext-ms-win-accel-api-km-l1-1-1!AccelCloseResource` at `0x1400cb191`
- `ext-ms-win-accel-api-km-l1-1-1!AccelCloseResource` at `0x1400cb191`

## pseudocode

```c

```

## disassembly

```asm
0x1400cb170  push    rbx
0x1400cb172  sub     rsp, 20h
0x1400cb176  test    dword ptr [rcx+25D0h], 800000h
0x1400cb180  mov     rbx, rcx
0x1400cb183  jnz     short loc_1400CB19D
0x1400cb185  mov     rcx, [rcx+28E8h]
0x1400cb18c  test    rcx, rcx
0x1400cb18f  jz      short loc_1400CB19D
0x1400cb191  call    cs:__imp_AccelCloseResource
0x1400cb198  nop     dword ptr [rax+rax+00h]
0x1400cb19d  mov     rcx, [rbx+28E0h]
0x1400cb1a4  test    rcx, rcx
0x1400cb1a7  jz      short loc_1400CB1C0
0x1400cb1a9  call    cs:__imp_AccelDestroyOffloadWorkspace
0x1400cb1b0  nop     dword ptr [rax+rax+00h]
0x1400cb1b5  mov     qword ptr [rbx+28E0h], 0
0x1400cb1c0  mov     rcx, [rbx+28D8h]; Lookaside
0x1400cb1c7  test    rcx, rcx
0x1400cb1ca  jz      short loc_1400CB1FB
0x1400cb1cc  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400cb1d3  nop     dword ptr [rax+rax+00h]
0x1400cb1d8  mov     rcx, [rbx+28D8h]; P
0x1400cb1df  mov     edx, 30455646h; Tag
0x1400cb1e4  call    cs:__imp_ExFreePoolWithTag
0x1400cb1eb  nop     dword ptr [rax+rax+00h]
0x1400cb1f0  mov     qword ptr [rbx+28D8h], 0
0x1400cb1fb  lea     rcx, [rbx+2870h]; Resource
0x1400cb202  call    cs:__imp_ExDeleteResourceLite
0x1400cb209  nop     dword ptr [rax+rax+00h]
0x1400cb20e  add     rsp, 20h
0x1400cb212  pop     rbx
0x1400cb213  retn
```
