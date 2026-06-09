# Recycler::TryFinishConcurrentCollect<270635011>(void)

- ea: `0x180258404`
- end: `0x1802584ab`
- name: `??$TryFinishConcurrentCollect@$0BACBJAAD@@Recycler@@AEAAHXZ`
- size: `167`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801aab9c`

## callees

- `0x180189e0c`
- `0x180258044`
- `0x180258404`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180258467`
- `KERNEL32!SetThreadPriority` at `0x180258467`
- `KERNEL32!GetTickCount` at `0x18025842e`
- `KERNEL32!GetTickCount` at `0x180258485`
- `KERNEL32!GetTickCount` at `0x18025842e`
- `KERNEL32!GetTickCount` at `0x180258485`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<270635011>(__int64 a1)
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
        if ( *(_QWORD *)(a1 + 488) > (unsigned __int64)qword_180442F78 || TickCount - *(_DWORD *)(a1 + 12960) > 0x1388 )
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
  return Recycler::FinishConcurrentCollectWrapped(a1, 270635011);
}

```

## disassembly

```asm
0x180258404  mov     [rsp+arg_0], rcx
0x180258409  push    rbx
0x18025840a  sub     rsp, 20h
0x18025840e  mov     rbx, [rsp+28h+arg_0]
0x180258413  cmp     qword ptr [rbx+3298h], 0
0x18025841b  jz      short loc_180258499
0x18025841d  test    dword ptr [rbx], 4000h
0x180258423  jz      short loc_180258485
0x180258425  cmp     byte ptr [rbx+326Eh], 0
0x18025842c  jnz     short loc_180258473
0x18025842e  call    cs:__imp_GetTickCount
0x180258435  nop     dword ptr [rax+rax+00h]
0x18025843a  mov     rcx, cs:qword_180442F78
0x180258441  cmp     [rbx+1E8h], rcx
0x180258448  ja      short loc_180258457
0x18025844a  sub     eax, [rbx+32A0h]
0x180258450  cmp     eax, 1388h
0x180258455  jbe     short loc_180258473
0x180258457  mov     rcx, [rbx+3298h]; hThread
0x18025845e  xor     edx, edx; nPriority
0x180258460  mov     byte ptr [rbx+326Eh], 1
0x180258467  call    cs:__imp_SetThreadPriority
0x18025846e  nop     dword ptr [rax+rax+00h]
0x180258473  mov     rcx, rbx
0x180258476  call    ??$FinishDisposeObjectsWrapped@$0BACBJAAD@@Recycler@@AEAA_NXZ; Recycler::FinishDisposeObjectsWrapped<270635011>(void)
0x18025847b  movzx   eax, al
0x18025847e  add     rsp, 20h
0x180258482  pop     rbx
0x180258483  retn
0x180258485  call    cs:__imp_GetTickCount
0x18025848c  nop     dword ptr [rax+rax+00h]
0x180258491  cmp     eax, [rbx+3FA4h]
0x180258497  jbe     short loc_180258473
0x180258499  mov     edx, 10219003h
0x18025849e  mov     rcx, rbx
0x1802584a1  add     rsp, 20h
0x1802584a5  pop     rbx
0x1802584a6  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
