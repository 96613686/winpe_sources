# Recycler::TryFinishConcurrentCollect<-1879044095>(void)

- ea: `0x180258174`
- end: `0x180258205`
- name: `??$TryFinishConcurrentCollect@$0?GPPPOPPP@@Recycler@@AEAAHXZ`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801aa8b0`
- `0x180257e7c`

## callees

- `0x180189e0c`
- `0x180258174`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x1802581de`
- `KERNEL32!SetThreadPriority` at `0x1802581de`
- `KERNEL32!GetTickCount` at `0x1802581a5`
- `KERNEL32!GetTickCount` at `0x1802581a5`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<-1879044095>(__int64 a1)
{
  bool v2; // zf
  DWORD TickCount; // eax
  void *v4; // rcx

  v2 = *(_QWORD *)(a1 + 12952) == 0;
  *(_BYTE *)(a1 + 12893) = 1;
  if ( v2 || (*(_DWORD *)a1 & 0x4000) == 0 )
    return Recycler::FinishConcurrentCollectWrapped(a1, 2415923201LL);
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
0x180258174  mov     [rsp+arg_0], rcx
0x180258179  push    rbx
0x18025817a  sub     rsp, 20h
0x18025817e  mov     rbx, [rsp+28h+arg_0]
0x180258183  cmp     qword ptr [rbx+3298h], 0
0x18025818b  mov     byte ptr [rbx+325Dh], 1
0x180258192  jz      short loc_1802581F3
0x180258194  test    dword ptr [rbx], 4000h
0x18025819a  jz      short loc_1802581F3
0x18025819c  cmp     byte ptr [rbx+326Eh], 0
0x1802581a3  jnz     short loc_1802581EA
0x1802581a5  call    cs:__imp_GetTickCount
0x1802581ac  nop     dword ptr [rax+rax+00h]
0x1802581b1  mov     rcx, cs:qword_180442F78
0x1802581b8  cmp     [rbx+1E8h], rcx
0x1802581bf  ja      short loc_1802581CE
0x1802581c1  sub     eax, [rbx+32A0h]
0x1802581c7  cmp     eax, 1388h
0x1802581cc  jbe     short loc_1802581EA
0x1802581ce  mov     rcx, [rbx+3298h]; hThread
0x1802581d5  xor     edx, edx; nPriority
0x1802581d7  mov     byte ptr [rbx+326Eh], 1
0x1802581de  call    cs:__imp_SetThreadPriority
0x1802581e5  nop     dword ptr [rax+rax+00h]
0x1802581ea  xor     eax, eax
0x1802581ec  add     rsp, 20h
0x1802581f0  pop     rbx
0x1802581f1  retn
0x1802581f3  mov     edx, 90001001h
0x1802581f8  mov     rcx, rbx
0x1802581fb  add     rsp, 20h
0x1802581ff  pop     rbx
0x180258200  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
