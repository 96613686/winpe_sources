# RfsTimerSet

- ea: `0x14000521c`
- end: `0x140005292`
- name: `RfsTimerSet`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140013370`
- `0x1400136b0`
- `0x1400151c0`
- `0x140016808`

## callees

- `0x14000521c`
- `0x1400052e8`

## import_xrefs

- `ntoskrnl!KeSetCoalescableTimer` at `0x14000524f`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14000524f`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x14000527f`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x14000527f`

## pseudocode

```c
__int64 __fastcall RfsTimerSet(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  ULONG v4; // r10d
  LARGE_INTEGER v5; // r11

  result = RfsTimerpSetFlagsSafe(a1, 2);
  if ( (result & 1) == 0 && (result & 4) == 0 )
  {
    KeSetCoalescableTimer((PKTIMER)v3, v5, 0, v4, (PKDPC)(v3 + 72));
    _m_prefetchw((const void *)(a1 + 64));
    result = (unsigned int)_InterlockedAnd((volatile signed __int32 *)(a1 + 64), 0xFFFFFFFD);
    if ( (result & 1) != 0 || (result & 4) != 0 )
      return ExUnblockOnAddressPushLockEx(a1 + 184, 0);
  }
  return result;
}

```

## disassembly

```asm
0x14000521c  push    rbx
0x14000521e  sub     rsp, 30h
0x140005222  mov     r11, rdx
0x140005225  mov     r10d, r9d
0x140005228  mov     edx, 2
0x14000522d  mov     rbx, rcx
0x140005230  call    RfsTimerpSetFlagsSafe
0x140005235  test    al, 1
0x140005237  jnz     short loc_14000528B
0x140005239  test    al, 4
0x14000523b  jnz     short loc_14000528B
0x14000523d  lea     rax, [rcx+48h]
0x140005241  mov     r9d, r10d; TolerableDelay
0x140005244  xor     r8d, r8d; Period
0x140005247  mov     [rsp+38h+Dpc], rax; Dpc
0x14000524c  mov     rdx, r11; DueTime
0x14000524f  call    cs:__imp_KeSetCoalescableTimer
0x140005256  nop     dword ptr [rax+rax+00h]
0x14000525b  prefetchw byte ptr [rbx+40h]
0x14000525f  mov     eax, [rbx+40h]
0x140005262  mov     ecx, eax
0x140005264  and     ecx, 0FFFFFFFDh
0x140005267  lock cmpxchg [rbx+40h], ecx
0x14000526c  jnz     short loc_140005262
0x14000526e  test    al, 1
0x140005270  jnz     short loc_140005276
0x140005272  test    al, 4
0x140005274  jz      short loc_14000528B
0x140005276  lea     rcx, [rbx+0B8h]
0x14000527d  xor     edx, edx
0x14000527f  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x140005286  nop     dword ptr [rax+rax+00h]
0x14000528b  add     rsp, 30h
0x14000528f  pop     rbx
0x140005290  retn
```
