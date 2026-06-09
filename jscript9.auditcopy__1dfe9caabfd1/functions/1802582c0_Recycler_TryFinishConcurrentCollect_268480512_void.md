# Recycler::TryFinishConcurrentCollect<268480512>(void)

- ea: `0x1802582c0`
- end: `0x180258353`
- name: `??$TryFinishConcurrentCollect@$0BAAALAAA@@Recycler@@AEAAHXZ`
- size: `147`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1801aa1ec`
- `0x1801aa228`

## callees

- `0x180189e0c`
- `0x180257fd8`
- `0x1802582c0`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180258323`
- `KERNEL32!SetThreadPriority` at `0x180258323`
- `KERNEL32!GetTickCount` at `0x1802582ea`
- `KERNEL32!GetTickCount` at `0x1802582ea`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<268480512>(__int64 a1)
{
  DWORD TickCount; // eax
  void *v3; // rcx

  if ( !*(_QWORD *)(a1 + 12952) || (*(_DWORD *)a1 & 0x4000) == 0 )
    return Recycler::FinishConcurrentCollectWrapped(a1, 268480512);
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
  return (unsigned __int8)Recycler::FinishDisposeObjectsWrapped<268480512>(a1);
}

```

## disassembly

```asm
0x1802582c0  mov     [rsp+arg_0], rcx
0x1802582c5  push    rbx
0x1802582c6  sub     rsp, 20h
0x1802582ca  mov     rbx, [rsp+28h+arg_0]
0x1802582cf  cmp     qword ptr [rbx+3298h], 0
0x1802582d7  jz      short loc_180258341
0x1802582d9  test    dword ptr [rbx], 4000h
0x1802582df  jz      short loc_180258341
0x1802582e1  cmp     byte ptr [rbx+326Eh], 0
0x1802582e8  jnz     short loc_18025832F
0x1802582ea  call    cs:__imp_GetTickCount
0x1802582f1  nop     dword ptr [rax+rax+00h]
0x1802582f6  mov     rcx, cs:qword_180442F78
0x1802582fd  cmp     [rbx+1E8h], rcx
0x180258304  ja      short loc_180258313
0x180258306  sub     eax, [rbx+32A0h]
0x18025830c  cmp     eax, 1388h
0x180258311  jbe     short loc_18025832F
0x180258313  mov     rcx, [rbx+3298h]; hThread
0x18025831a  xor     edx, edx; nPriority
0x18025831c  mov     byte ptr [rbx+326Eh], 1
0x180258323  call    cs:__imp_SetThreadPriority
0x18025832a  nop     dword ptr [rax+rax+00h]
0x18025832f  mov     rcx, rbx
0x180258332  call    ??$FinishDisposeObjectsWrapped@$0BAAALAAA@@Recycler@@AEAA_NXZ; Recycler::FinishDisposeObjectsWrapped<268480512>(void)
0x180258337  movzx   eax, al
0x18025833a  add     rsp, 20h
0x18025833e  pop     rbx
0x18025833f  retn
0x180258341  mov     edx, 1000B000h
0x180258346  mov     rcx, rbx
0x180258349  add     rsp, 20h
0x18025834d  pop     rbx
0x18025834e  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
