# Recycler::TryFinishConcurrentCollect<1879576576>(void)

- ea: `0x180253dfc`
- end: `0x180253e87`
- name: `??$TryFinishConcurrentCollect@$0HAAIBAAA@@Recycler@@AEAAHXZ`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801a7c0c`
- `0x1801a7ffc`

## callees

- `0x1801892d8`
- `0x180253dfc`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180253e67`
- `KERNEL32!SetThreadPriority` at `0x180253e67`
- `KERNEL32!GetTickCount` at `0x180253e34`
- `KERNEL32!GetTickCount` at `0x180253e34`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<1879576576>(__int64 a1)
{
  bool v2; // zf
  DWORD TickCount; // eax
  void *v4; // rcx

  v2 = *(_QWORD *)(a1 + 12952) == 0;
  *(_BYTE *)(a1 + 12894) = 1;
  *(_BYTE *)(a1 + 12891) = 1;
  if ( v2 || (*(_DWORD *)a1 & 0x4000) == 0 )
    return Recycler::FinishConcurrentCollectWrapped(a1, 1879576576);
  if ( !*(_BYTE *)(a1 + 12910) )
  {
    TickCount = GetTickCount();
    if ( *(_QWORD *)(a1 + 488) > (unsigned __int64)qword_18043CF78 || TickCount - *(_DWORD *)(a1 + 12960) > 0x1388 )
    {
      v4 = *(void **)(a1 + 12952);
      *(_BYTE *)(a1 + 12910) = 1;
      SetThreadPriority(v4, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180253dfc  mov     [rsp+arg_0], rcx
0x180253e01  push    rbx
0x180253e02  sub     rsp, 20h
0x180253e06  mov     rbx, [rsp+28h+arg_0]
0x180253e0b  cmp     qword ptr [rbx+3298h], 0
0x180253e13  mov     byte ptr [rbx+325Eh], 1
0x180253e1a  mov     byte ptr [rbx+325Bh], 1
0x180253e21  jz      short loc_180253E75
0x180253e23  test    dword ptr [rbx], 4000h
0x180253e29  jz      short loc_180253E75
0x180253e2b  cmp     byte ptr [rbx+326Eh], 0
0x180253e32  jnz     short loc_180253E6D
0x180253e34  call    cs:__imp_GetTickCount
0x180253e3a  mov     rcx, cs:qword_18043CF78
0x180253e41  cmp     [rbx+1E8h], rcx
0x180253e48  ja      short loc_180253E57
0x180253e4a  sub     eax, [rbx+32A0h]
0x180253e50  cmp     eax, 1388h
0x180253e55  jbe     short loc_180253E6D
0x180253e57  mov     rcx, [rbx+3298h]; hThread
0x180253e5e  xor     edx, edx; nPriority
0x180253e60  mov     byte ptr [rbx+326Eh], 1
0x180253e67  call    cs:__imp_SetThreadPriority
0x180253e6d  xor     eax, eax
0x180253e6f  add     rsp, 20h
0x180253e73  pop     rbx
0x180253e74  retn
0x180253e75  mov     edx, 70081000h
0x180253e7a  mov     rcx, rbx
0x180253e7d  add     rsp, 20h
0x180253e81  pop     rbx
0x180253e82  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
