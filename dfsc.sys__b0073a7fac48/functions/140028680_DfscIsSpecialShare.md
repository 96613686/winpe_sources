# DfscIsSpecialShare

- ea: `0x140028680`
- end: `0x1400286d3`
- name: `DfscIsSpecialShare`
- size: `83`
- prototype: `char __fastcall(UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011494`
- `0x140016070`
- `0x14001abc0`
- `0x14001fb50`
- `0x140023120`

## callees

- `0x1400238c0`
- `0x140028680`

## pseudocode

```c
char __fastcall DfscIsSpecialShare(UNICODE_STRING *a1)
{
  char v1; // di
  unsigned int i; // ebx

  v1 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( (unsigned int)DfscCompareStringsIgnoreTrailingChars((UNICODE_STRING *)&qword_14000C0C0[2 * i], a1) )
      return 1;
  }
  return v1;
}

```

## disassembly

```asm
0x140028680  mov     [rsp+arg_0], rbx
0x140028685  mov     [rsp+arg_8], rsi
0x14002868a  push    rdi
0x14002868b  sub     rsp, 20h
0x14002868f  xor     dil, dil
0x140028692  mov     rsi, rcx
0x140028695  xor     ebx, ebx
0x140028697  cmp     ebx, 2
0x14002869a  jnb     short loc_1400286BF
0x14002869c  lea     rax, qword_14000C0C0
0x1400286a3  mov     ecx, ebx
0x1400286a5  shl     rcx, 4
0x1400286a9  mov     rdx, rsi
0x1400286ac  add     rcx, rax
0x1400286af  call    DfscCompareStringsIgnoreTrailingChars
0x1400286b4  test    eax, eax
0x1400286b6  jnz     short loc_1400286BC
0x1400286b8  inc     ebx
0x1400286ba  jmp     short loc_140028697
0x1400286bc  mov     dil, 1
0x1400286bf  mov     rbx, [rsp+28h+arg_0]
0x1400286c4  mov     al, dil
0x1400286c7  mov     rsi, [rsp+28h+arg_8]
0x1400286cc  add     rsp, 20h
0x1400286d0  pop     rdi
0x1400286d1  retn
```
