# NpEventsDisconnectCompleted

- ea: `0x1400101d0`
- end: `0x140010282`
- name: `NpEventsDisconnectCompleted`
- size: `178`
- prototype: `int __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000f8c0`
- `0x14000fdc4`

## callees

- `0x1400101d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010225`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010225`
- `ntoskrnl!ObfDereferenceObject` at `0x140010214`
- `ntoskrnl!ObfDereferenceObject` at `0x140010214`
- `ntoskrnl!KeSetEvent` at `0x140010274`
- `ntoskrnl!KeSetEvent` at `0x140010274`

## pseudocode

```c
int __fastcall NpEventsDisconnectCompleted(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  PVOID *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  struct _KEVENT *v8; // rcx

  v2 = a2;
  v4 = *(PVOID **)(a1 + 8LL * a2 + 432);
  if ( v4 )
  {
    if ( *v4 )
      ObfDereferenceObject(*v4);
    ExFreePoolWithTag(v4, 0);
    *(_QWORD *)(a1 + 8 * v2 + 432) = 0;
  }
  v5 = 432;
  if ( (_DWORD)v2 != 1 )
    v5 = 440;
  v6 = *(_QWORD *)(v5 + a1);
  if ( v6 )
  {
    LODWORD(v5) = *(_DWORD *)(v6 + 8);
    if ( (v5 & 8) != 0 )
    {
      v7 = 48;
      if ( (_DWORD)v2 != 1 )
        v7 = 56;
      v5 = *(_QWORD *)(v7 + a1);
      if ( v5 )
      {
        v5 = *(_QWORD *)(v5 + 32);
        if ( (v5 & 1) != 0 )
        {
          v8 = *(struct _KEVENT **)v6;
          if ( v8 )
            LODWORD(v5) = KeSetEvent(v8, 2, 0);
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400101d0  push    rbx
0x1400101d2  push    rbp
0x1400101d3  push    rsi
0x1400101d4  push    rdi
0x1400101d5  sub     rsp, 28h
0x1400101d9  mov     esi, edx
0x1400101db  mov     rbx, rcx
0x1400101de  mov     rdi, [rcx+rsi*8+1B0h]
0x1400101e6  test    rdi, rdi
0x1400101e9  jnz     short loc_14001020C
0x1400101eb  mov     eax, 1B0h
0x1400101f0  cmp     esi, 1
0x1400101f3  lea     ecx, [rax+8]
0x1400101f6  cmovnz  eax, ecx
0x1400101f9  mov     rcx, [rax+rbx]
0x1400101fd  test    rcx, rcx
0x140010200  jnz     short loc_14001023F
0x140010202  add     rsp, 28h
0x140010206  pop     rdi
0x140010207  pop     rsi
0x140010208  pop     rbp
0x140010209  pop     rbx
0x14001020a  retn
0x14001020c  mov     rcx, [rdi]; Object
0x14001020f  test    rcx, rcx
0x140010212  jz      short loc_140010220
0x140010214  call    cs:__imp_ObfDereferenceObject
0x14001021b  nop     dword ptr [rax+rax+00h]
0x140010220  xor     edx, edx; Tag
0x140010222  mov     rcx, rdi; P
0x140010225  call    cs:__imp_ExFreePoolWithTag
0x14001022c  nop     dword ptr [rax+rax+00h]
0x140010231  mov     qword ptr [rbx+rsi*8+1B0h], 0
0x14001023d  jmp     short loc_1400101EB
0x14001023f  mov     eax, [rcx+8]
0x140010242  test    al, 8
0x140010244  jz      short loc_140010202
0x140010246  mov     eax, 30h ; '0'
0x14001024b  cmp     esi, 1
0x14001024e  lea     edx, [rax+8]
0x140010251  cmovnz  eax, edx
0x140010254  mov     rax, [rax+rbx]
0x140010258  test    rax, rax
0x14001025b  jz      short loc_140010202
0x14001025d  mov     rax, [rax+20h]
0x140010261  test    al, 1
0x140010263  jz      short loc_140010202
0x140010265  mov     rcx, [rcx]; Event
0x140010268  test    rcx, rcx
0x14001026b  jz      short loc_140010202
0x14001026d  xor     r8d, r8d; Wait
0x140010270  lea     edx, [r8+2]; Increment
0x140010274  call    cs:__imp_KeSetEvent
0x14001027b  nop     dword ptr [rax+rax+00h]
0x140010280  jmp     short loc_140010202
```
