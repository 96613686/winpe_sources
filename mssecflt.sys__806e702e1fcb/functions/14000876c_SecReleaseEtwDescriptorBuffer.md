# SecReleaseEtwDescriptorBuffer

- ea: `0x14000876c`
- end: `0x1400087e4`
- name: `SecReleaseEtwDescriptorBuffer`
- size: `120`
- prototype: `__int64 __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `41`
- callee_count: `2`
- tags: ``

## callers

- `0x140004e08`
- `0x140004fb0`
- `0x140005230`
- `0x140005418`
- `0x140005638`
- `0x140007870`
- `0x140007a30`
- `0x140007bb0`
- `0x14000c1f0`
- `0x14000c2a4`
- `0x14000c514`
- `0x140025b78`
- `0x140025cf8`
- `0x140025f00`
- `0x1400260b8`
- `0x1400262c8`
- `0x14002643c`
- `0x140026630`
- `0x14002685c`
- `0x14002b490`
- `0x14002b5ec`
- `0x14002b76c`
- `0x14002e97c`
- `0x140030ca8`
- `0x140031300`
- `0x140031598`
- `0x140031924`
- `0x140035b7c`
- `0x140035cfc`
- `0x140035e7c`
- `0x140036098`
- `0x140036258`
- `0x140036418`
- `0x1400365d8`
- `0x14003e4bc`
- `0x140043150`
- `0x1400434bc`
- `0x14004377c`
- `0x140043840`
- `0x140043bf4`
- `0x140043cc8`

## callees

- `0x14000876c`
- `0x140011610`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400087c7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400087c7`
- `ntoskrnl!ExQueryDepthSList` at `0x14000879b`
- `ntoskrnl!ExQueryDepthSList` at `0x14000879b`

## pseudocode

```c
void __fastcall SecReleaseEtwDescriptorBuffer(PSLIST_ENTRY ListEntry)
{
  char *v2; // rdi
  USHORT v3; // bx

  if ( ListEntry )
  {
    v2 = (char *)SecData + 896;
    ++*((_DWORD *)SecData + 231);
    v3 = *((_WORD *)v2 + 8);
    if ( ExQueryDepthSList((PSLIST_HEADER)v2) < v3 )
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v2, ListEntry);
    }
    else
    {
      ++*((_DWORD *)v2 + 8);
      (*((void (__fastcall **)(PSLIST_ENTRY))v2 + 7))(ListEntry);
    }
  }
}

```

## disassembly

```asm
0x14000876c  test    rcx, rcx
0x14000876f  jz      short locret_1400087E2
0x140008771  mov     [rsp+arg_0], rbx
0x140008776  mov     [rsp+arg_8], rsi
0x14000877b  push    rdi
0x14000877c  sub     rsp, 20h
0x140008780  mov     rdi, cs:SecData
0x140008787  mov     rsi, rcx
0x14000878a  add     rdi, 380h
0x140008791  mov     rcx, rdi; SListHead
0x140008794  inc     dword ptr [rdi+1Ch]
0x140008797  movzx   ebx, word ptr [rdi+10h]
0x14000879b  call    cs:__imp_ExQueryDepthSList
0x1400087a2  nop     dword ptr [rax+rax+00h]
0x1400087a7  cmp     ax, bx
0x1400087aa  jb      short loc_1400087BE
0x1400087ac  inc     dword ptr [rdi+20h]
0x1400087af  mov     rcx, rsi
0x1400087b2  mov     rax, [rdi+38h]
0x1400087b6  call    cs:__guard_dispatch_icall_fptr
0x1400087bc  jmp     short loc_1400087D3
0x1400087be  lfence
0x1400087c1  mov     rdx, rsi; ListEntry
0x1400087c4  mov     rcx, rdi; ListHead
0x1400087c7  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400087ce  nop     dword ptr [rax+rax+00h]
0x1400087d3  mov     rbx, [rsp+28h+arg_0]
0x1400087d8  mov     rsi, [rsp+28h+arg_8]
0x1400087dd  add     rsp, 20h
0x1400087e1  pop     rdi
0x1400087e2  retn
```
