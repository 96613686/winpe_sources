# CCriticalSection::Lock(void)

- ea: `0x140006458`
- end: `0x14000646f`
- name: `?Lock@CCriticalSection@@AEAAXXZ`
- size: `23`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1400043c0`
- `0x1400061d4`
- `0x140006268`
- `0x140006418`
- `0x140008f50`
- `0x14000ac9c`
- `0x14000aee8`
- `0x14000afa0`
- `0x14000b69c`
- `0x14000c490`
- `0x14000c8c0`

## callees

- `0x140006458`
- `0x140006960`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000645c`
- `KERNEL32!EnterCriticalSection` at `0x14000645c`

## pseudocode

```c
void __fastcall CCriticalSection::Lock(struct _RTL_CRITICAL_SECTION *this)
{
  EnterCriticalSection(this);
}

```

## disassembly

```asm
0x140006458  sub     rsp, 28h
0x14000645c  call    cs:__imp_EnterCriticalSection
0x140006462  jmp     short loc_14000646A
0x140006464  call    ?ThrowBadAlloc@CCriticalSection@@CAXXZ; CCriticalSection::ThrowBadAlloc(void)
0x14000646a  add     rsp, 28h
0x14000646e  retn
0x14001d4f6  push    rbp
0x14001d4f8  sub     rsp, 20h
0x14001d4fc  mov     rbp, rdx
0x14001d4ff  mov     rax, [rcx]
0x14001d502  xor     ecx, ecx
0x14001d504  cmp     dword ptr [rax], 0C0000008h
0x14001d50a  setz    cl
0x14001d50d  mov     eax, ecx
0x14001d50f  add     rsp, 20h
0x14001d513  pop     rbp
0x14001d514  retn
```
