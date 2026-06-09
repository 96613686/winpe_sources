# NsippProbeForWrite

- ea: `0x140004c50`
- end: `0x140004c9a`
- name: `NsippProbeForWrite`
- size: `74`
- prototype: `unsigned __int64 __fastcall(volatile void *, SIZE_T, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400043d0`

## callees

- `0x140004c50`

## import_xrefs

- `ntoskrnl!ExRaiseAccessViolation` at `0x140004c8d`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140004c8d`
- `ntoskrnl!ProbeForWrite` at `0x140004c77`
- `ntoskrnl!ProbeForWrite` at `0x140004c77`

## pseudocode

```c
unsigned __int64 __fastcall NsippProbeForWrite(volatile void *a1, SIZE_T a2, __int64 a3, char a4)
{
  if ( a1 )
  {
    if ( a4 )
      ProbeForWrite(a1, a2, 1u);
    return (a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  }
  else
  {
    if ( a2 )
      ExRaiseAccessViolation();
    return 0;
  }
}

```

## disassembly

```asm
0x140004c50  push    rbx
0x140004c52  sub     rsp, 20h
0x140004c56  mov     rbx, rdx
0x140004c59  test    rcx, rcx
0x140004c5c  jnz     short loc_140004C6C
0x140004c5e  test    rdx, rdx
0x140004c61  jnz     short loc_140004C8D
0x140004c63  xor     eax, eax
0x140004c65  add     rsp, 20h
0x140004c69  pop     rbx
0x140004c6a  retn
0x140004c6c  test    r9b, r9b
0x140004c6f  jz      short loc_140004C83
0x140004c71  mov     r8d, 1; Alignment
0x140004c77  call    cs:__imp_ProbeForWrite
0x140004c7e  nop     dword ptr [rax+rax+00h]
0x140004c83  lea     rax, [rbx+7]
0x140004c87  and     rax, 0FFFFFFFFFFFFFFF8h
0x140004c8b  jmp     short loc_140004C65
0x140004c8d  call    cs:__imp_ExRaiseAccessViolation
0x140004c94  nop     dword ptr [rax+rax+00h]
0x140004c99  int     3; Trap to Debugger
```
