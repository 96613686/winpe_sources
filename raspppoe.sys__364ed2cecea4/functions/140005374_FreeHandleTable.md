# FreeHandleTable

- ea: `0x140005374`
- end: `0x1400053be`
- name: `FreeHandleTable`
- size: `74`
- prototype: `__int64 __fastcall(PVOID VirtualAddress)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c44`
- `0x14000e3d8`

## callees

- `0x140005374`

## import_xrefs

- `NDIS!NdisFreeMemory` at `0x140005395`
- `NDIS!NdisFreeMemory` at `0x1400053ab`
- `NDIS!NdisFreeMemory` at `0x140005395`
- `NDIS!NdisFreeMemory` at `0x1400053ab`

## pseudocode

```c
void __fastcall FreeHandleTable(_DWORD *VirtualAddress)
{
  void *v2; // rcx

  if ( VirtualAddress )
  {
    v2 = *(void **)VirtualAddress;
    if ( v2 )
      NdisFreeMemory(v2, 24 * VirtualAddress[2], 0);
    NdisFreeMemory(VirtualAddress, 0x18u, 0);
  }
}

```

## disassembly

```asm
0x140005374  test    rcx, rcx
0x140005377  jz      short locret_1400053BC
0x140005379  push    rbx
0x14000537a  sub     rsp, 20h
0x14000537e  mov     rbx, rcx
0x140005381  mov     rcx, [rcx]; VirtualAddress
0x140005384  test    rcx, rcx
0x140005387  jz      short loc_1400053A1
0x140005389  mov     eax, [rbx+8]
0x14000538c  xor     r8d, r8d; MemoryFlags
0x14000538f  lea     edx, [rax+rax*2]
0x140005392  shl     edx, 3; Length
0x140005395  call    cs:__imp_NdisFreeMemory
0x14000539c  nop     dword ptr [rax+rax+00h]
0x1400053a1  xor     r8d, r8d; MemoryFlags
0x1400053a4  mov     rcx, rbx; VirtualAddress
0x1400053a7  lea     edx, [r8+18h]; Length
0x1400053ab  call    cs:__imp_NdisFreeMemory
0x1400053b2  nop     dword ptr [rax+rax+00h]
0x1400053b7  add     rsp, 20h
0x1400053bb  pop     rbx
0x1400053bc  retn
```
