# DevAuthFinishHash

- ea: `0x1800026a0`
- end: `0x1800026e1`
- name: `DevAuthFinishHash`
- size: `65`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e4`
- `0x180002740`

## callees

- `0x180002e00`

## import_xrefs

- `cng!BCryptFinishHash` at `0x1800026b8`
- `cng!BCryptFinishHash` at `0x1800026b8`

## pseudocode

```c
_BOOL8 __fastcall DevAuthFinishHash(BCRYPT_HASH_HANDLE *P, UCHAR *a2)
{
  BOOL v3; // ebx

  v3 = BCryptFinishHash(P[1], a2, 0x20u, 0) >= 0;
  DevAuthHashCleanup(P);
  return v3;
}

```

## disassembly

```asm
0x1800026a0  mov     [rsp+arg_0], rbx
0x1800026a5  push    rdi
0x1800026a6  sub     rsp, 20h
0x1800026aa  xor     r9d, r9d; dwFlags
0x1800026ad  mov     rdi, rcx
0x1800026b0  mov     rcx, [rcx+8]; hHash
0x1800026b4  lea     r8d, [r9+20h]; cbOutput
0x1800026b8  call    cs:__imp_BCryptFinishHash
0x1800026bf  nop     dword ptr [rax+rax+00h]
0x1800026c4  mov     ebx, eax
0x1800026c6  mov     rcx, rdi; P
0x1800026c9  not     ebx
0x1800026cb  shr     ebx, 1Fh
0x1800026ce  call    _DevAuthHashCleanup
0x1800026d3  mov     eax, ebx
0x1800026d5  mov     rbx, [rsp+28h+arg_0]
0x1800026da  add     rsp, 20h
0x1800026de  pop     rdi
0x1800026df  retn
```
