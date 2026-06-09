# FNeedToCancel

- ea: `0x14002cf7c`
- end: `0x14002cfc2`
- name: `FNeedToCancel`
- size: `70`
- prototype: `bool __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001760`
- `0x1400343b8`

## callees

- `0x14002cf7c`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x14002cf8e`
- `ntoskrnl!PsIsThreadTerminating` at `0x14002cf8e`

## pseudocode

```c
bool __fastcall FNeedToCancel(__int64 a1)
{
  __int64 v2; // rax

  if ( PsIsThreadTerminating(KeGetCurrentThread()) )
    return 1;
  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 40);
    if ( v2 )
      return *(_BYTE *)(v2 + 68) != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14002cf7c  push    rbx
0x14002cf7e  sub     rsp, 20h
0x14002cf82  mov     rbx, rcx
0x14002cf85  mov     rcx, gs:188h; Thread
0x14002cf8e  call    cs:__imp_PsIsThreadTerminating
0x14002cf95  nop     dword ptr [rax+rax+00h]
0x14002cf9a  test    al, al
0x14002cf9c  jnz     short loc_14002CFB9
0x14002cf9e  test    rbx, rbx
0x14002cfa1  jz      short loc_14002CFB5
0x14002cfa3  mov     rax, [rbx+28h]
0x14002cfa7  test    rax, rax
0x14002cfaa  jz      short loc_14002CFB5
0x14002cfac  cmp     byte ptr [rax+44h], 0
0x14002cfb0  setnz   al
0x14002cfb3  jmp     short loc_14002CFBB
0x14002cfb5  xor     al, al
0x14002cfb7  jmp     short loc_14002CFBB
0x14002cfb9  mov     al, 1
0x14002cfbb  add     rsp, 20h
0x14002cfbf  pop     rbx
0x14002cfc0  retn
```
