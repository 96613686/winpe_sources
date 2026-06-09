# VarFind

- ea: `0x14000dfd8`
- end: `0x14000e021`
- name: `VarFind`
- size: `73`
- prototype: ``
- caller_count: `28`
- callee_count: `3`
- tags: ``

## callers

- `0x140003a30`
- `0x140003d28`
- `0x140003f68`
- `0x140004398`
- `0x1400045ac`
- `0x14000488c`
- `0x1400054b0`
- `0x1400062e0`
- `0x140006590`
- `0x140006834`
- `0x1400068d8`
- `0x140006a34`
- `0x140007120`
- `0x1400072bc`
- `0x140007934`
- `0x140008190`
- `0x140008244`
- `0x14000836c`
- `0x1400084d8`
- `0x14000aa6c`
- `0x14000ae78`
- `0x14000b128`
- `0x14000b2d8`
- `0x14000b7b0`
- `0x14000b890`
- `0x14000c2bc`
- `0x14000c6d4`
- `0x14000cb80`

## callees

- `0x14000dfd8`
- `0x14000e138`
- `0x14000e1a4`

## pseudocode

```c
__int64 __fastcall VarFind(__int64 a1, __int64 a2, __int64 a3)
{
  if ( (unsigned int)isValidVarName(a2, a3) )
    return findVar(a1, a2, a3);
  else
    return 0;
}

```

## disassembly

```asm
0x14000dfd8  mov     [rsp+arg_0], rbx
0x14000dfdd  mov     [rsp+arg_8], rsi
0x14000dfe2  push    rdi
0x14000dfe3  sub     rsp, 20h
0x14000dfe7  mov     rdi, rdx
0x14000dfea  mov     rsi, rcx
0x14000dfed  mov     rcx, rdi
0x14000dff0  mov     rdx, r8
0x14000dff3  mov     rbx, r8
0x14000dff6  call    isValidVarName
0x14000dffb  test    eax, eax
0x14000dffd  jnz     short loc_14000E003
0x14000dfff  xor     eax, eax
0x14000e001  jmp     short loc_14000E011
0x14000e003  mov     r8, rbx
0x14000e006  mov     rdx, rdi
0x14000e009  mov     rcx, rsi
0x14000e00c  call    findVar
0x14000e011  mov     rbx, [rsp+28h+arg_0]
0x14000e016  mov     rsi, [rsp+28h+arg_8]
0x14000e01b  add     rsp, 20h
0x14000e01f  pop     rdi
0x14000e020  retn
```
