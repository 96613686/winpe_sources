# PsmpCompleteQuiescing

- ea: `0x180015f38`
- end: `0x180015f95`
- name: `PsmpCompleteQuiescing`
- size: `93`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015e70`
- `0x180015f10`

## callees

- `0x18000e93c`
- `0x180015b50`
- `0x180015f38`

## import_xrefs

- `ntdll!NtSetEvent` at `0x180015f8d`
- `ntdll!NtSetEvent` at `0x180015f8d`

## pseudocode

```c
__int64 __fastcall PsmpCompleteQuiescing(__int64 a1, _DWORD *a2)
{
  void *v4; // rcx

  if ( _interlockedbittestandreset((volatile signed __int32 *)(a1 + 128), 0x17u) )
  {
    PsmpHaltApplication();
  }
  else if ( (*(_DWORD *)(a1 + 132) & 0x1000) != 0 )
  {
    *a2 = *(_DWORD *)(a1 + 344);
  }
  else
  {
    *a2 = 7;
    PsmpSetApplicationQuiesceCompleteEvents();
    v4 = *(void **)(a1 + 216);
    if ( v4 )
      NtSetEvent(v4, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180015f38  push    rbx
0x180015f3a  sub     rsp, 20h
0x180015f3e  lock btr dword ptr [rcx+80h], 17h
0x180015f47  mov     rbx, rcx
0x180015f4a  setb    al
0x180015f4d  test    al, al
0x180015f4f  jnz     short loc_180015F6D
0x180015f51  test    dword ptr [rcx+84h], 1000h
0x180015f5b  jz      short loc_180015F74
0x180015f5d  mov     eax, [rcx+158h]
0x180015f63  mov     [rdx], eax
0x180015f65  xor     eax, eax
0x180015f67  add     rsp, 20h
0x180015f6b  pop     rbx
0x180015f6c  retn
0x180015f6d  call    PsmpHaltApplication
0x180015f72  jmp     short loc_180015F65
0x180015f74  mov     dword ptr [rdx], 7
0x180015f7a  call    PsmpSetApplicationQuiesceCompleteEvents
0x180015f7f  mov     rcx, [rbx+0D8h]; EventHandle
0x180015f86  test    rcx, rcx
0x180015f89  jz      short loc_180015F65
0x180015f8b  xor     edx, edx; PreviousState
0x180015f8d  call    cs:__imp_NtSetEvent
0x180015f93  jmp     short loc_180015F65
```
