# Recycler::TryFinishConcurrentCollect<1879576576>(void)

- ea: `0x180258530`
- end: `0x1802585c8`
- name: `??$TryFinishConcurrentCollect@$0HAAIBAAA@@Recycler@@AEAAHXZ`
- size: `152`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801aa3b4`
- `0x1801aa7c0`

## callees

- `0x180189e0c`
- `0x180258530`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x1802585a1`
- `KERNEL32!SetThreadPriority` at `0x1802585a1`
- `KERNEL32!GetTickCount` at `0x180258568`
- `KERNEL32!GetTickCount` at `0x180258568`

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
0x180258530  mov     [rsp+arg_0], rcx
0x180258535  push    rbx
0x180258536  sub     rsp, 20h
0x18025853a  mov     rbx, [rsp+28h+arg_0]
0x18025853f  cmp     qword ptr [rbx+3298h], 0
0x180258547  mov     byte ptr [rbx+325Eh], 1
0x18025854e  mov     byte ptr [rbx+325Bh], 1
0x180258555  jz      short loc_1802585B6
0x180258557  test    dword ptr [rbx], 4000h
0x18025855d  jz      short loc_1802585B6
0x18025855f  cmp     byte ptr [rbx+326Eh], 0
0x180258566  jnz     short loc_1802585AD
0x180258568  call    cs:__imp_GetTickCount
0x18025856f  nop     dword ptr [rax+rax+00h]
0x180258574  mov     rcx, cs:qword_180442F78
0x18025857b  cmp     [rbx+1E8h], rcx
0x180258582  ja      short loc_180258591
0x180258584  sub     eax, [rbx+32A0h]
0x18025858a  cmp     eax, 1388h
0x18025858f  jbe     short loc_1802585AD
0x180258591  mov     rcx, [rbx+3298h]; hThread
0x180258598  xor     edx, edx; nPriority
0x18025859a  mov     byte ptr [rbx+326Eh], 1
0x1802585a1  call    cs:__imp_SetThreadPriority
0x1802585a8  nop     dword ptr [rax+rax+00h]
0x1802585ad  xor     eax, eax
0x1802585af  add     rsp, 20h
0x1802585b3  pop     rbx
0x1802585b4  retn
0x1802585b6  mov     edx, 70081000h
0x1802585bb  mov     rcx, rbx
0x1802585be  add     rsp, 20h
0x1802585c2  pop     rbx
0x1802585c3  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
