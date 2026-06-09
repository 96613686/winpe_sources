# PageAllocator::ZeroQueuedPages(void)

- ea: `0x18017e034`
- end: `0x18017e0ad`
- name: `?ZeroQueuedPages@PageAllocator@@QEAAXXZ`
- size: `121`
- prototype: `void __fastcall(PageAllocator *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800212b4`
- `0x18019ba90`
- `0x180200c60`
- `0x180257f80`
- `0x18025a2e8`

## callees

- `0x18017e034`
- `0x1801cc26b`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x18017e071`
- `KERNEL32!InterlockedPushEntrySList` at `0x18017e071`
- `KERNEL32!InterlockedPopEntrySList` at `0x18017e088`
- `KERNEL32!InterlockedPopEntrySList` at `0x18017e088`

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
0x18017e034  mov     [rsp+arg_0], rcx
0x18017e039  push    rbx
0x18017e03a  push    rbp
0x18017e03b  push    rsi
0x18017e03c  push    rdi
0x18017e03d  sub     rsp, 28h
0x18017e041  mov     rsi, [rsp+48h+arg_0]
0x18017e046  jmp     short loc_18017E07D
0x18017e048  mov     ebx, [rbp+10h]
0x18017e04b  xor     edx, edx; Val
0x18017e04d  mov     rdi, [rbp+8]
0x18017e051  mov     r8d, ebx
0x18017e054  shl     r8d, 0Ch; Size
0x18017e058  mov     rcx, rbp; void *
0x18017e05b  call    memset_0
0x18017e060  mov     [rbp+8], rdi
0x18017e064  mov     rdx, rbp; ListEntry
0x18017e067  mov     [rbp+10h], ebx
0x18017e06a  mov     rcx, [rsi+80h]; ListHead
0x18017e071  call    cs:__imp_InterlockedPushEntrySList
0x18017e078  nop     dword ptr [rax+rax+00h]
0x18017e07d  mov     rcx, [rsi+80h]
0x18017e084  add     rcx, 40h ; '@'; ListHead
0x18017e088  call    cs:__imp_InterlockedPopEntrySList
0x18017e08f  nop     dword ptr [rax+rax+00h]
0x18017e094  mov     rbp, rax
0x18017e097  test    rax, rax
0x18017e09a  jnz     short loc_18017E048
0x18017e09c  mov     byte ptr [rsi+8Ah], 0
0x18017e0a3  add     rsp, 28h
0x18017e0a7  pop     rdi
0x18017e0a8  pop     rsi
0x18017e0a9  pop     rbp
0x18017e0aa  pop     rbx
0x18017e0ab  retn
```
