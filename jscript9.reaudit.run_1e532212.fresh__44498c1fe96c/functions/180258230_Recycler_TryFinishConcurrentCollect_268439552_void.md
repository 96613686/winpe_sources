# Recycler::TryFinishConcurrentCollect<268439552>(void)

- ea: `0x180258230`
- end: `0x1802582ba`
- name: `??$TryFinishConcurrentCollect@$0BAAABAAA@@Recycler@@AEAAHXZ`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801aa30c`
- `0x1801aa348`

## callees

- `0x180189e0c`
- `0x180258230`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180258293`
- `KERNEL32!SetThreadPriority` at `0x180258293`
- `KERNEL32!GetTickCount` at `0x18025825a`
- `KERNEL32!GetTickCount` at `0x18025825a`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<268439552>(__int64 a1)
{
  DWORD TickCount; // eax
  void *v3; // rcx

  if ( !*(_QWORD *)(a1 + 12952) || (*(_DWORD *)a1 & 0x4000) == 0 )
    return Recycler::FinishConcurrentCollectWrapped(a1, 268439552);
  if ( !*(_BYTE *)(a1 + 12910) )
  {
    TickCount = GetTickCount();
    if ( *(_QWORD *)(a1 + 488) > (unsigned __int64)qword_180442F78 || TickCount - *(_DWORD *)(a1 + 12960) > 0x1388 )
    {
      v3 = *(void **)(a1 + 12952);
      *(_BYTE *)(a1 + 12910) = 1;
      SetThreadPriority(v3, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180258230  mov     [rsp+arg_0], rcx
0x180258235  push    rbx
0x180258236  sub     rsp, 20h
0x18025823a  mov     rbx, [rsp+28h+arg_0]
0x18025823f  cmp     qword ptr [rbx+3298h], 0
0x180258247  jz      short loc_1802582A8
0x180258249  test    dword ptr [rbx], 4000h
0x18025824f  jz      short loc_1802582A8
0x180258251  cmp     byte ptr [rbx+326Eh], 0
0x180258258  jnz     short loc_18025829F
0x18025825a  call    cs:__imp_GetTickCount
0x180258261  nop     dword ptr [rax+rax+00h]
0x180258266  mov     rcx, cs:qword_180442F78
0x18025826d  cmp     [rbx+1E8h], rcx
0x180258274  ja      short loc_180258283
0x180258276  sub     eax, [rbx+32A0h]
0x18025827c  cmp     eax, 1388h
0x180258281  jbe     short loc_18025829F
0x180258283  mov     rcx, [rbx+3298h]; hThread
0x18025828a  xor     edx, edx; nPriority
0x18025828c  mov     byte ptr [rbx+326Eh], 1
0x180258293  call    cs:__imp_SetThreadPriority
0x18025829a  nop     dword ptr [rax+rax+00h]
0x18025829f  xor     eax, eax
0x1802582a1  add     rsp, 20h
0x1802582a5  pop     rbx
0x1802582a6  retn
0x1802582a8  mov     edx, 10001000h
0x1802582ad  mov     rcx, rbx
0x1802582b0  add     rsp, 20h
0x1802582b4  pop     rbx
0x1802582b5  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
