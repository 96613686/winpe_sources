# CopyDeviceRelations

- ea: `0x18003fa00`
- end: `0x18003fa49`
- name: `CopyDeviceRelations`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019694`

## callees

- `0x1800140ec`
- `0x180021940`
- `0x18003fa00`

## pseudocode

```c
__int64 __fastcall CopyDeviceRelations(unsigned int *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  unsigned __int64 v4; // rax

  v3 = 0;
  if ( !a1
    || (a2 = 0xFFFFFFFFLL, v4 = 8LL * *a1, v4 > 0xFFFFFFFF)
    || (a3 = (unsigned int)(v4 + 16), (unsigned int)a3 < (unsigned int)v4)
    || (v3 = MemDup(a1, a1)) == 0 )
  {
    TraceLoggingCopyDeviceRelationsFailed((__int64)a1, a2, a3);
  }
  return v3;
}

```

## disassembly

```asm
0x18003fa00  push    rbx
0x18003fa02  sub     rsp, 20h
0x18003fa06  xor     ebx, ebx
0x18003fa08  test    rcx, rcx
0x18003fa0b  jz      short loc_18003FA1D
0x18003fa0d  mov     eax, [rcx]
0x18003fa0f  mov     edx, 0FFFFFFFFh
0x18003fa14  shl     rax, 3
0x18003fa18  cmp     rax, rdx
0x18003fa1b  jbe     short loc_18003FA3E
0x18003fa1d  call    TraceLoggingCopyDeviceRelationsFailed
0x18003fa22  jmp     short loc_18003FA34
0x18003fa24  mov     rdx, rcx
0x18003fa27  call    MemDup
0x18003fa2c  mov     rbx, rax
0x18003fa2f  test    rax, rax
0x18003fa32  jz      short loc_18003FA1D
0x18003fa34  mov     rax, rbx
0x18003fa37  add     rsp, 20h
0x18003fa3b  pop     rbx
0x18003fa3c  retn
0x18003fa3e  lea     r8d, [rax+10h]
0x18003fa42  cmp     r8d, eax
0x18003fa45  jb      short loc_18003FA1D
0x18003fa47  jmp     short loc_18003FA24
```
