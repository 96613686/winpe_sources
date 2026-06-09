# DiscpRemoveTargetPortalsByTag

- ea: `0x180007b20`
- end: `0x180007bac`
- name: `DiscpRemoveTargetPortalsByTag`
- size: `140`
- prototype: `NTSTATUS __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000bfc4`
- `0x18000c03c`

## callees

- `0x1800068cc`
- `0x180007a94`
- `0x180007b20`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180007ba5`
- `ntdll!RtlEnterCriticalSection` at `0x180007b36`
- `ntdll!RtlEnterCriticalSection` at `0x180007b36`

## pseudocode

```c
NTSTATUS __fastcall DiscpRemoveTargetPortalsByTag(int a1)
{
  _UNKNOWN **v2; // rdi
  _UNKNOWN **v3; // r14
  _QWORD **v4; // r14
  _QWORD *v5; // rbx
  __int64 v6; // rsi

  RtlEnterCriticalSection(&DiscpCritSection);
  v2 = (_UNKNOWN **)DiscpTargetAddressList;
  while ( v2 != &DiscpTargetAddressList )
  {
    v3 = v2;
    v2 = (_UNKNOWN **)*v2;
    v4 = (_QWORD **)(v3 + 4);
    v5 = *v4;
    while ( v5 != v4 )
    {
      v6 = (__int64)v5;
      v5 = (_QWORD *)*v5;
      if ( a1 == 1 || a1 == *(_DWORD *)(v6 + 24) )
      {
        DiscpRemoveTargetPortalFromList((__int64 *)v6);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 16), 0xFFFFFFFF) == 1 )
          DiscpFreeTargetPortal(v6);
      }
    }
  }
  return RtlLeaveCriticalSection(&DiscpCritSection);
}

```

## disassembly

```asm
0x180007b20  push    rbx
0x180007b22  push    rbp
0x180007b23  push    rsi
0x180007b24  push    rdi
0x180007b25  push    r14
0x180007b27  push    r15
0x180007b29  sub     rsp, 28h
0x180007b2d  mov     ebp, ecx
0x180007b2f  lea     rcx, DiscpCritSection; CriticalSection
0x180007b36  call    cs:__imp_RtlEnterCriticalSection
0x180007b3c  mov     rdi, cs:DiscpTargetAddressList
0x180007b43  lea     r15, DiscpTargetAddressList
0x180007b4a  jmp     short loc_180007B8D
0x180007b4c  mov     r14, rdi
0x180007b4f  mov     rdi, [rdi]
0x180007b52  add     r14, 20h ; ' '
0x180007b56  mov     rbx, [r14]
0x180007b59  jmp     short loc_180007B88
0x180007b5b  mov     rsi, rbx
0x180007b5e  mov     rbx, [rbx]
0x180007b61  cmp     ebp, 1
0x180007b64  jz      short loc_180007B6B
0x180007b66  cmp     ebp, [rsi+18h]
0x180007b69  jnz     short loc_180007B88
0x180007b6b  mov     rcx, rsi
0x180007b6e  call    DiscpRemoveTargetPortalFromList
0x180007b73  or      eax, 0FFFFFFFFh
0x180007b76  lock xadd [rsi+10h], eax
0x180007b7b  cmp     eax, 1
0x180007b7e  jnz     short loc_180007B88
0x180007b80  mov     rcx, rsi
0x180007b83  call    DiscpFreeTargetPortal
0x180007b88  cmp     rbx, r14
0x180007b8b  jnz     short loc_180007B5B
0x180007b8d  cmp     rdi, r15
0x180007b90  jnz     short loc_180007B4C
0x180007b92  lea     rcx, DiscpCritSection
0x180007b99  add     rsp, 28h
0x180007b9d  pop     r15
0x180007b9f  pop     r14
0x180007ba1  pop     rdi
0x180007ba2  pop     rsi
0x180007ba3  pop     rbp
0x180007ba4  pop     rbx
0x180007ba5  jmp     cs:__imp_RtlLeaveCriticalSection
```
