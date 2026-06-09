# Smb2ValidateNegotiateInfo

- ea: `0x140029668`
- end: `0x14002972a`
- name: `Smb2ValidateNegotiateInfo`
- size: `194`
- prototype: `char __fastcall(__int64, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140029190`
- `0x140029250`

## callees

- `0x140028fa8`
- `0x140029668`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400296ad`
- `ntoskrnl!RtlCompareMemory` at `0x1400296ad`

## pseudocode

```c
char __fastcall Smb2ValidateNegotiateInfo(__int64 a1, __int64 a2, int a3)
{
  if ( *(_WORD *)(a1 + 20) == *(_WORD *)(a2 + 672)
    && *(_DWORD *)a1 == *(_DWORD *)(a2 + 676)
    && *(_WORD *)(a1 + 22) == *(_WORD *)(a2 + 674)
    && RtlCompareMemory((const void *)(a1 + 4), (const void *)(a2 + 656), 0x10u) == 16 )
  {
    return 1;
  }
  if ( (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 2) != 0 )
    McTemplateK0hhqjhhqj_EtwWriteTransfer(
      a2 + 656,
      a2,
      a3,
      *(unsigned __int16 *)(a2 + 674),
      *(_WORD *)(a2 + 672),
      *(_DWORD *)(a2 + 676),
      a2 + 656,
      *(_WORD *)(a1 + 22),
      *(_WORD *)(a1 + 20),
      *(_DWORD *)a1,
      a1 + 4);
  return 0;
}

```

## disassembly

```asm
0x140029668  mov     [rsp+arg_0], rbx
0x14002966d  push    rdi
0x14002966e  sub     rsp, 60h
0x140029672  movzx   eax, word ptr [rdx+2A0h]
0x140029679  mov     rbx, rdx
0x14002967c  mov     rdi, rcx
0x14002967f  cmp     [rcx+14h], ax
0x140029683  jnz     short loc_1400296C3
0x140029685  mov     eax, [rdx+2A4h]
0x14002968b  cmp     [rcx], eax
0x14002968d  jnz     short loc_1400296C3
0x14002968f  movzx   eax, word ptr [rdx+2A2h]
0x140029696  cmp     [rcx+16h], ax
0x14002969a  jnz     short loc_1400296C3
0x14002969c  add     rdx, 290h; Source2
0x1400296a3  add     rcx, 4; Source1
0x1400296a7  mov     r8d, 10h; Length
0x1400296ad  call    cs:__imp_RtlCompareMemory
0x1400296b4  nop     dword ptr [rax+rax+00h]
0x1400296b9  cmp     rax, 10h
0x1400296bd  jnz     short loc_1400296C3
0x1400296bf  mov     al, 1
0x1400296c1  jmp     short loc_14002971E
0x1400296c3  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 2
0x1400296ca  jz      short loc_14002971C
0x1400296cc  movzx   r9d, word ptr [rbx+2A2h]
0x1400296d4  lea     rax, [rdi+4]
0x1400296d8  mov     [rsp+68h+var_18], rax
0x1400296dd  lea     rcx, [rbx+290h]
0x1400296e4  mov     eax, [rdi]
0x1400296e6  mov     [rsp+68h+var_20], eax
0x1400296ea  movzx   eax, word ptr [rdi+14h]
0x1400296ee  mov     [rsp+68h+var_28], ax
0x1400296f3  movzx   eax, word ptr [rdi+16h]
0x1400296f7  mov     [rsp+68h+var_30], ax
0x1400296fc  mov     eax, [rbx+2A4h]
0x140029702  mov     [rsp+68h+var_38], rcx
0x140029707  mov     [rsp+68h+var_40], eax
0x14002970b  movzx   eax, word ptr [rbx+2A0h]
0x140029712  mov     [rsp+68h+var_48], ax
0x140029717  call    McTemplateK0hhqjhhqj_EtwWriteTransfer
0x14002971c  xor     al, al
0x14002971e  mov     rbx, [rsp+68h+arg_0]
0x140029723  add     rsp, 60h
0x140029727  pop     rdi
0x140029728  retn
```
