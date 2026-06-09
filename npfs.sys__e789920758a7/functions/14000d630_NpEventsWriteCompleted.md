# NpEventsWriteCompleted

- ea: `0x14000d630`
- end: `0x14000d6d3`
- name: `NpEventsWriteCompleted`
- size: `163`
- prototype: `void __fastcall(__int64, unsigned int, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000cff8`

## callees

- `0x14000d630`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000d6a1`
- `ntoskrnl!KeSetEvent` at `0x14000d6a1`

## pseudocode

```c
void __fastcall NpEventsWriteCompleted(__int64 a1, unsigned int a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // r9d

  if ( *(_DWORD *)(a3 + 16) == 1 )
  {
    v5 = *(_QWORD *)(a1 + 8LL * a2 + 432);
    if ( v5 )
    {
      if ( !a5 && a4 >= 0 )
      {
        v10 = *(_DWORD *)(v5 + 8);
        if ( (v10 & 1) == 0 )
          *(_DWORD *)(v5 + 8) = v10 | 1;
      }
    }
    v6 = 432;
    if ( a2 != 1 )
      v6 = 440;
    v7 = *(_QWORD *)(v6 + a1);
    if ( v7 && (*(_DWORD *)(v7 + 8) & 2) != 0 )
    {
      v8 = 48;
      if ( a2 != 1 )
        v8 = 56;
      v9 = *(_QWORD *)(v8 + a1);
      if ( v9 )
      {
        if ( (*(_QWORD *)(v9 + 32) & 1) != 0 )
          KeSetEvent(*(PRKEVENT *)v7, 2, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x14000d630  sub     rsp, 28h
0x14000d634  cmp     dword ptr [r8+10h], 1
0x14000d639  jnz     short loc_14000D665
0x14000d63b  mov     eax, edx
0x14000d63d  mov     r8, [rcx+rax*8+1B0h]
0x14000d645  test    r8, r8
0x14000d648  jnz     short loc_14000D6AF
0x14000d64a  cmp     edx, 1
0x14000d64d  mov     eax, 1B0h
0x14000d652  mov     r8d, 1B8h
0x14000d658  cmovnz  eax, r8d
0x14000d65c  mov     r9, [rax+rcx]
0x14000d660  test    r9, r9
0x14000d663  jnz     short loc_14000D66B
0x14000d665  add     rsp, 28h
0x14000d669  retn
0x14000d66b  mov     eax, [r9+8]
0x14000d66f  test    al, 2
0x14000d671  jz      short loc_14000D665
0x14000d673  cmp     edx, 1
0x14000d676  mov     eax, 30h ; '0'
0x14000d67b  mov     r8d, 38h ; '8'
0x14000d681  cmovnz  eax, r8d
0x14000d685  mov     rax, [rax+rcx]
0x14000d689  test    rax, rax
0x14000d68c  jz      short loc_14000D665
0x14000d68e  mov     rax, [rax+20h]
0x14000d692  test    al, 1
0x14000d694  jz      short loc_14000D665
0x14000d696  mov     rcx, [r9]; Event
0x14000d699  xor     r8d, r8d; Wait
0x14000d69c  mov     edx, 2; Increment
0x14000d6a1  call    cs:__imp_KeSetEvent
0x14000d6a8  nop     dword ptr [rax+rax+00h]
0x14000d6ad  jmp     short loc_14000D665
0x14000d6af  cmp     [rsp+28h+arg_20], 0
0x14000d6b5  jnz     short loc_14000D64A
0x14000d6b7  test    r9d, r9d
0x14000d6ba  js      short loc_14000D64A
0x14000d6bc  mov     r9d, [r8+8]
0x14000d6c0  test    r9b, 1
0x14000d6c4  jnz     short loc_14000D64A
0x14000d6c6  or      r9d, 1
0x14000d6ca  mov     [r8+8], r9d
0x14000d6ce  jmp     loc_14000D64A
```
