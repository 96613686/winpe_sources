# Recycler::TryFinishConcurrentCollect<-1862266880>(void)

- ea: `0x1802580dc`
- end: `0x18025816d`
- name: `??$TryFinishConcurrentCollect@$0?GOPPPAAA@@Recycler@@AEAAHXZ`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801aa294`
- `0x1801aa62c`

## callees

- `0x180189e0c`
- `0x1802580dc`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180258146`
- `KERNEL32!SetThreadPriority` at `0x180258146`
- `KERNEL32!GetTickCount` at `0x18025810d`
- `KERNEL32!GetTickCount` at `0x18025810d`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<-1862266880>(__int64 a1)
{
  bool v2; // zf
  DWORD TickCount; // eax
  void *v4; // rcx

  v2 = *(_QWORD *)(a1 + 12952) == 0;
  *(_BYTE *)(a1 + 12893) = 1;
  if ( v2 || (*(_DWORD *)a1 & 0x4000) == 0 )
    return Recycler::FinishConcurrentCollectWrapped(a1, 2432700416LL);
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

```

## disassembly

```asm
0x1802580dc  mov     [rsp+arg_0], rcx
0x1802580e1  push    rbx
0x1802580e2  sub     rsp, 20h
0x1802580e6  mov     rbx, [rsp+28h+arg_0]
0x1802580eb  cmp     qword ptr [rbx+3298h], 0
0x1802580f3  mov     byte ptr [rbx+325Dh], 1
0x1802580fa  jz      short loc_18025815B
0x1802580fc  test    dword ptr [rbx], 4000h
0x180258102  jz      short loc_18025815B
0x180258104  cmp     byte ptr [rbx+326Eh], 0
0x18025810b  jnz     short loc_180258152
0x18025810d  call    cs:__imp_GetTickCount
0x180258114  nop     dword ptr [rax+rax+00h]
0x180258119  mov     rcx, cs:qword_180442F78
0x180258120  cmp     [rbx+1E8h], rcx
0x180258127  ja      short loc_180258136
0x180258129  sub     eax, [rbx+32A0h]
0x18025812f  cmp     eax, 1388h
0x180258134  jbe     short loc_180258152
0x180258136  mov     rcx, [rbx+3298h]; hThread
0x18025813d  xor     edx, edx; nPriority
0x18025813f  mov     byte ptr [rbx+326Eh], 1
0x180258146  call    cs:__imp_SetThreadPriority
0x18025814d  nop     dword ptr [rax+rax+00h]
0x180258152  xor     eax, eax
0x180258154  add     rsp, 20h
0x180258158  pop     rbx
0x180258159  retn
0x18025815b  mov     edx, 91001000h
0x180258160  mov     rcx, rbx
0x180258163  add     rsp, 20h
0x180258167  pop     rbx
0x180258168  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
