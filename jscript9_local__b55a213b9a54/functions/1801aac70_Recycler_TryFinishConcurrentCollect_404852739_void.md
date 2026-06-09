# Recycler::TryFinishConcurrentCollect<404852739>(void)

- ea: `0x1801aac70`
- end: `0x1801aad17`
- name: `??$TryFinishConcurrentCollect@$0BICBJAAD@@Recycler@@AEAAHXZ`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1801aaadc`
- `0x1801aab70`

## callees

- `0x180189e0c`
- `0x1801aac70`
- `0x180258044`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x1801aacd3`
- `KERNEL32!SetThreadPriority` at `0x1801aacd3`
- `KERNEL32!GetTickCount` at `0x1801aac9a`
- `KERNEL32!GetTickCount` at `0x1801aacf1`
- `KERNEL32!GetTickCount` at `0x1801aac9a`
- `KERNEL32!GetTickCount` at `0x1801aacf1`

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
  return Recycler::FinishConcurrentCollectWrapped(a1, 404852739);
}

```

## disassembly

```asm
0x1801aac70  mov     [rsp+arg_0], rcx
0x1801aac75  push    rbx
0x1801aac76  sub     rsp, 20h
0x1801aac7a  mov     rbx, [rsp+28h+arg_0]
0x1801aac7f  cmp     qword ptr [rbx+3298h], 0
0x1801aac87  jz      short loc_1801AAD05
0x1801aac89  test    dword ptr [rbx], 4000h
0x1801aac8f  jz      short loc_1801AACF1
0x1801aac91  cmp     byte ptr [rbx+326Eh], 0
0x1801aac98  jnz     short loc_1801AACDF
0x1801aac9a  call    cs:__imp_GetTickCount
0x1801aaca1  nop     dword ptr [rax+rax+00h]
0x1801aaca6  mov     rcx, cs:qword_180442F78
0x1801aacad  cmp     [rbx+1E8h], rcx
0x1801aacb4  ja      short loc_1801AACC3
0x1801aacb6  sub     eax, [rbx+32A0h]
0x1801aacbc  cmp     eax, 1388h
0x1801aacc1  jbe     short loc_1801AACDF
0x1801aacc3  mov     rcx, [rbx+3298h]; hThread
0x1801aacca  xor     edx, edx; nPriority
0x1801aaccc  mov     byte ptr [rbx+326Eh], 1
0x1801aacd3  call    cs:__imp_SetThreadPriority
0x1801aacda  nop     dword ptr [rax+rax+00h]
0x1801aacdf  mov     rcx, rbx
0x1801aace2  call    ??$FinishDisposeObjectsWrapped@$0BACBJAAD@@Recycler@@AEAA_NXZ; Recycler::FinishDisposeObjectsWrapped<270635011>(void)
0x1801aace7  movzx   eax, al
0x1801aacea  add     rsp, 20h
0x1801aacee  pop     rbx
0x1801aacef  retn
0x1801aacf1  call    cs:__imp_GetTickCount
0x1801aacf8  nop     dword ptr [rax+rax+00h]
0x1801aacfd  cmp     eax, [rbx+3FA4h]
0x1801aad03  jbe     short loc_1801AACDF
0x1801aad05  mov     edx, 18219003h
0x1801aad0a  mov     rcx, rbx
0x1801aad0d  add     rsp, 20h
0x1801aad11  pop     rbx
0x1801aad12  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
