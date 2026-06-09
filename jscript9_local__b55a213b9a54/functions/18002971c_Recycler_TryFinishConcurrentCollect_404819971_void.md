# Recycler::TryFinishConcurrentCollect<404819971>(void)

- ea: `0x18002971c`
- end: `0x1800297bc`
- name: `??$TryFinishConcurrentCollect@$0BICBBAAD@@Recycler@@AEAAHXZ`
- size: `160`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18002893c`
- `0x180028c80`
- `0x180029a38`
- `0x18002a240`
- `0x180036b00`
- `0x180068450`
- `0x1801aa9cc`

## callees

- `0x18002971c`
- `0x180189e0c`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x1800297ae`
- `KERNEL32!SetThreadPriority` at `0x1800297ae`
- `KERNEL32!GetTickCount` at `0x180029746`
- `KERNEL32!GetTickCount` at `0x180029778`
- `KERNEL32!GetTickCount` at `0x180029746`
- `KERNEL32!GetTickCount` at `0x180029778`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<404819971>(__int64 a1)
{
  DWORD TickCount; // eax
  void *v4; // rcx

  if ( *(_QWORD *)(a1 + 12952) )
  {
    if ( (*(_DWORD *)a1 & 0x4000) != 0 )
    {
      if ( !*(_BYTE *)(a1 + 12910) )
      {
        TickCount = GetTickCount();
        if ( *(_QWORD *)(a1 + 488) > (unsigned __int64)qword_180442F78 || TickCount - *(_DWORD *)(a1 + 12960) > 0x1388 )
        {
          v4 = *(void **)(a1 + 12952);
          *(_BYTE *)(a1 + 12910) = 1;
          SetThreadPriority(v4, 0);
        }
      }
      return 0;
    }
    if ( GetTickCount() <= *(_DWORD *)(a1 + 16292) )
      return 0;
  }
  return Recycler::FinishConcurrentCollectWrapped(a1, 404819971);
}

```

## disassembly

```asm
0x18002971c  mov     [rsp+arg_0], rcx
0x180029721  push    rbx
0x180029722  sub     rsp, 20h
0x180029726  mov     rbx, [rsp+28h+arg_0]
0x18002972b  cmp     qword ptr [rbx+3298h], 0
0x180029733  jz      short loc_18002978C
0x180029735  test    dword ptr [rbx], 4000h
0x18002973b  jz      short loc_180029778
0x18002973d  cmp     byte ptr [rbx+326Eh], 0
0x180029744  jnz     short loc_18002976F
0x180029746  call    cs:__imp_GetTickCount
0x18002974d  nop     dword ptr [rax+rax+00h]
0x180029752  mov     rcx, cs:qword_180442F78
0x180029759  cmp     [rbx+1E8h], rcx
0x180029760  ja      short loc_18002979E
0x180029762  sub     eax, [rbx+32A0h]
0x180029768  cmp     eax, 1388h
0x18002976d  ja      short loc_18002979E
0x18002976f  xor     eax, eax
0x180029771  add     rsp, 20h
0x180029775  pop     rbx
0x180029776  retn
0x180029778  call    cs:__imp_GetTickCount
0x18002977f  nop     dword ptr [rax+rax+00h]
0x180029784  cmp     eax, [rbx+3FA4h]
0x18002978a  jbe     short loc_18002976F
0x18002978c  mov     edx, 18211003h
0x180029791  mov     rcx, rbx
0x180029794  add     rsp, 20h
0x180029798  pop     rbx
0x180029799  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
0x18002979e  mov     rcx, [rbx+3298h]; hThread
0x1800297a5  xor     edx, edx; nPriority
0x1800297a7  mov     byte ptr [rbx+326Eh], 1
0x1800297ae  call    cs:__imp_SetThreadPriority
0x1800297b5  nop     dword ptr [rax+rax+00h]
0x1800297ba  jmp     short loc_18002976F
```
