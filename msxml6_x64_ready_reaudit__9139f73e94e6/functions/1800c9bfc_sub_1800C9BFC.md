# sub_1800C9BFC

- ea: `0x1800c9bfc`
- end: `0x1800c9c3e`
- name: `sub_1800C9BFC`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c98fc`
- `0x1800c99cc`

## callees

- `0x18000e120`
- `0x180096fb8`
- `0x1800c9bfc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800c9c0d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800c9c0d`

## pseudocode

```c

```

## disassembly

```asm
0x1800c9bfc  push    rbx
0x1800c9bfe  sub     rsp, 20h
0x1800c9c02  mov     rbx, rcx
0x1800c9c05  mov     rcx, [rcx+78h]
0x1800c9c09  mov     rcx, [rcx+18h]; lpszProgID
0x1800c9c0d  call    cs:CLSIDFromProgID
0x1800c9c14  nop     dword ptr [rax+rax+00h]
0x1800c9c19  test    eax, eax
0x1800c9c1b  jns     short loc_1800C9C37
0x1800c9c1d  mov     rdx, [rbx+78h]
0x1800c9c21  xor     r9d, r9d
0x1800c9c24  xor     r8d, r8d
0x1800c9c27  mov     ecx, 0C00CE305h
0x1800c9c2c  call    sub_180096FB8
0x1800c9c31  call    sub_18000E120
0x1800c9c36  int     3; Trap to Debugger
0x1800c9c37  add     rsp, 20h
0x1800c9c3b  pop     rbx
0x1800c9c3c  retn
```
