# PageAllocator::ZeroQueuedPages(void)

- ea: `0x18017d2c0`
- end: `0x18017d32c`
- name: `?ZeroQueuedPages@PageAllocator@@QEAAXXZ`
- size: `108`
- prototype: `void __fastcall(PageAllocator *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18006a300`
- `0x180199b58`
- `0x1801fd9a0`
- `0x1802538ac`
- `0x180255b20`

## callees

- `0x18017d2c0`
- `0x1801c989b`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x18017d2fd`
- `KERNEL32!InterlockedPushEntrySList` at `0x18017d2fd`
- `KERNEL32!InterlockedPopEntrySList` at `0x18017d30e`
- `KERNEL32!InterlockedPopEntrySList` at `0x18017d30e`

## pseudocode

```c
void __fastcall PageAllocator::ZeroQueuedPages(PageAllocator *this)
{
  int Next; // ebx
  __int64 v3; // rdi
  PSLIST_ENTRY v4; // rax
  PSLIST_ENTRY v5; // rbp

  while ( 1 )
  {
    v4 = InterlockedPopEntrySList((PSLIST_HEADER)(*((_QWORD *)this + 16) + 64LL));
    v5 = v4;
    if ( !v4 )
      break;
    Next = (int)v4[1].Next;
    v3 = *((_QWORD *)&v4->Next + 1);
    memset_0(v4, 0, (unsigned int)(Next << 12));
    *((_QWORD *)&v5->Next + 1) = v3;
    LODWORD(v5[1].Next) = Next;
    InterlockedPushEntrySList(*((PSLIST_HEADER *)this + 16), v5);
  }
  *((_BYTE *)this + 138) = 0;
}

```

## disassembly

```asm
0x18017d2c0  mov     [rsp+arg_0], rcx
0x18017d2c5  push    rbx
0x18017d2c6  push    rbp
0x18017d2c7  push    rsi
0x18017d2c8  push    rdi
0x18017d2c9  sub     rsp, 28h
0x18017d2cd  mov     rsi, [rsp+48h+arg_0]
0x18017d2d2  jmp     short loc_18017D303
0x18017d2d4  mov     ebx, [rbp+10h]
0x18017d2d7  xor     edx, edx; Val
0x18017d2d9  mov     rdi, [rbp+8]
0x18017d2dd  mov     r8d, ebx
0x18017d2e0  shl     r8d, 0Ch; Size
0x18017d2e4  mov     rcx, rbp; void *
0x18017d2e7  call    memset_0
0x18017d2ec  mov     [rbp+8], rdi
0x18017d2f0  mov     rdx, rbp; ListEntry
0x18017d2f3  mov     [rbp+10h], ebx
0x18017d2f6  mov     rcx, [rsi+80h]; ListHead
0x18017d2fd  call    cs:__imp_InterlockedPushEntrySList
0x18017d303  mov     rcx, [rsi+80h]
0x18017d30a  add     rcx, 40h ; '@'; ListHead
0x18017d30e  call    cs:__imp_InterlockedPopEntrySList
0x18017d314  mov     rbp, rax
0x18017d317  test    rax, rax
0x18017d31a  jnz     short loc_18017D2D4
0x18017d31c  mov     byte ptr [rsi+8Ah], 0
0x18017d323  add     rsp, 28h
0x18017d327  pop     rdi
0x18017d328  pop     rsi
0x18017d329  pop     rbp
0x18017d32a  pop     rbx
0x18017d32b  retn
```
