# Recycler::TryFinishConcurrentCollect<404852739>(void)

- ea: `0x1801a847c`
- end: `0x1801a8510`
- name: `??$TryFinishConcurrentCollect@$0BICBJAAD@@Recycler@@AEAAHXZ`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1801a82fc`
- `0x1801a8388`

## callees

- `0x1801892d8`
- `0x1801a847c`
- `0x18025396c`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x1801a84d9`
- `KERNEL32!SetThreadPriority` at `0x1801a84d9`
- `KERNEL32!GetTickCount` at `0x1801a84a6`
- `KERNEL32!GetTickCount` at `0x1801a84f0`
- `KERNEL32!GetTickCount` at `0x1801a84a6`
- `KERNEL32!GetTickCount` at `0x1801a84f0`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<404852739>(__int64 a1)
{
  DWORD TickCount; // eax
  void *v3; // rcx

  if ( *(_QWORD *)(a1 + 12952) )
  {
    if ( (*(_DWORD *)a1 & 0x4000) != 0 )
    {
      if ( !*(_BYTE *)(a1 + 12910) )
      {
        TickCount = GetTickCount();
        if ( *(_QWORD *)(a1 + 488) > (unsigned __int64)qword_18043CF78 || TickCount - *(_DWORD *)(a1 + 12960) > 0x1388 )
        {
          v3 = *(void **)(a1 + 12952);
          *(_BYTE *)(a1 + 12910) = 1;
          SetThreadPriority(v3, 0);
        }
      }
      return (unsigned __int8)Recycler::FinishDisposeObjectsWrapped<270635011>(a1);
    }
    if ( GetTickCount() <= *(_DWORD *)(a1 + 16292) )
      return (unsigned __int8)Recycler::FinishDisposeObjectsWrapped<270635011>(a1);
  }
  return Recycler::FinishConcurrentCollectWrapped(a1, 404852739);
}

```

## disassembly

```asm
0x1801a847c  mov     [rsp+arg_0], rcx
0x1801a8481  push    rbx
0x1801a8482  sub     rsp, 20h
0x1801a8486  mov     rbx, [rsp+28h+arg_0]
0x1801a848b  cmp     qword ptr [rbx+3298h], 0
0x1801a8493  jz      short loc_1801A84FE
0x1801a8495  test    dword ptr [rbx], 4000h
0x1801a849b  jz      short loc_1801A84F0
0x1801a849d  cmp     byte ptr [rbx+326Eh], 0
0x1801a84a4  jnz     short loc_1801A84DF
0x1801a84a6  call    cs:__imp_GetTickCount
0x1801a84ac  mov     rcx, cs:qword_18043CF78
0x1801a84b3  cmp     [rbx+1E8h], rcx
0x1801a84ba  ja      short loc_1801A84C9
0x1801a84bc  sub     eax, [rbx+32A0h]
0x1801a84c2  cmp     eax, 1388h
0x1801a84c7  jbe     short loc_1801A84DF
0x1801a84c9  mov     rcx, [rbx+3298h]; hThread
0x1801a84d0  xor     edx, edx; nPriority
0x1801a84d2  mov     byte ptr [rbx+326Eh], 1
0x1801a84d9  call    cs:__imp_SetThreadPriority
0x1801a84df  mov     rcx, rbx
0x1801a84e2  call    ??$FinishDisposeObjectsWrapped@$0BACBJAAD@@Recycler@@AEAA_NXZ; Recycler::FinishDisposeObjectsWrapped<270635011>(void)
0x1801a84e7  movzx   eax, al
0x1801a84ea  add     rsp, 20h
0x1801a84ee  pop     rbx
0x1801a84ef  retn
0x1801a84f0  call    cs:__imp_GetTickCount
0x1801a84f6  cmp     eax, [rbx+3FA4h]
0x1801a84fc  jbe     short loc_1801A84DF
0x1801a84fe  mov     edx, 18219003h
0x1801a8503  mov     rcx, rbx
0x1801a8506  add     rsp, 20h
0x1801a850a  pop     rbx
0x1801a850b  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
