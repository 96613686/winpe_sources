# HidpFdoCancelWaitWakeIrp

- ea: `0x1800150f4`
- end: `0x18001516e`
- name: `HidpFdoCancelWaitWakeIrp`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800150d0`

## callees

- `0x1800150f4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180015160`
- `ntoskrnl!IofCompleteRequest` at `0x180015160`
- `ntoskrnl!IoCancelIrp` at `0x180015139`
- `ntoskrnl!IoCancelIrp` at `0x180015139`

## pseudocode

```c
void __fastcall HidpFdoCancelWaitWakeIrp(__int64 a1)
{
  _m_prefetchw((const void *)(a1 + 376));
  if ( _InterlockedOr((volatile signed __int32 *)(a1 + 376), 1u) == 4 )
  {
    IoCancelIrp(*(PIRP *)(a1 + 368));
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 376), 4, 5) == 7 )
      IofCompleteRequest(*(PIRP *)(a1 + 368), 0);
  }
}

```

## disassembly

```asm
0x1800150f4  mov     [rsp+arg_0], rbx
0x1800150f9  push    rdi
0x1800150fa  sub     rsp, 20h
0x1800150fe  mov     rbx, rcx
0x180015101  prefetchw byte ptr [rcx+178h]
0x180015108  mov     eax, [rcx+178h]
0x18001510e  mov     edx, eax
0x180015110  or      edx, 1
0x180015113  lock cmpxchg [rcx+178h], edx
0x18001511b  jnz     short loc_18001510E
0x18001511d  mov     edi, 4
0x180015122  cmp     eax, edi
0x180015124  jz      short loc_180015132
0x180015126  mov     rbx, [rsp+28h+arg_0]
0x18001512b  add     rsp, 20h
0x18001512f  pop     rdi
0x180015130  retn
0x180015132  mov     rcx, [rcx+170h]; Irp
0x180015139  call    cs:__imp_IoCancelIrp
0x180015140  nop     dword ptr [rax+rax+00h]
0x180015145  mov     eax, 5
0x18001514a  lock cmpxchg [rbx+178h], edi
0x180015152  cmp     eax, 7
0x180015155  jnz     short loc_180015126
0x180015157  mov     rcx, [rbx+170h]; Irp
0x18001515e  xor     edx, edx; PriorityBoost
0x180015160  call    cs:__imp_IofCompleteRequest
0x180015167  nop     dword ptr [rax+rax+00h]
0x18001516c  jmp     short loc_180015126
```
