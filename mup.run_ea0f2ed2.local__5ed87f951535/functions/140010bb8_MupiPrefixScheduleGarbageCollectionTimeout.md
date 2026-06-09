# MupiPrefixScheduleGarbageCollectionTimeout

- ea: `0x140010bb8`
- end: `0x140010c8c`
- name: `MupiPrefixScheduleGarbageCollectionTimeout`
- size: `212`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140010950`
- `0x140010a80`
- `0x14001d6f4`

## callees

- `0x140010bb8`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140010c08`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140010c08`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140010c74`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140010c74`

## pseudocode

```c
char MupiPrefixScheduleGarbageCollectionTimeout()
{
  __int64 v0; // rax
  __int64 v1; // rdx
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rbx

  v0 = qword_14000A9E0;
  if ( (__int64 *)qword_14000A9E0 != &qword_14000A9E0 )
  {
    v1 = qword_14000A9F0;
    while ( (__int64 *)v0 != &qword_14000A9E0 )
    {
      if ( !*(_DWORD *)(v0 + 16) )
      {
        v2 = *(_QWORD *)(v0 - 24);
        v3 = 0;
        v4 = MEMORY[0xFFFFF78000000320];
        if ( v2 > MEMORY[0xFFFFF78000000320] )
          v3 = 100 * (v2 - v4) * KeQueryTimeIncrement();
        v1 = v3 / 100;
        if ( v3 / 100 > qword_14000A9F0 )
          v1 = qword_14000A9F0;
        break;
      }
      v0 = *(_QWORD *)v0;
    }
    WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)-v1;
    LOBYTE(v0) = KeSetCoalescableTimer(
                   &MupiPrefixGarbageCollectionTimer,
                   (LARGE_INTEGER)-v1,
                   0,
                   0x3E8u,
                   &MupiPrefixGarbageCollectionDpc);
  }
  return v0;
}

```

## disassembly

```asm
0x140010bb8  mov     [rsp+arg_0], rbx
0x140010bbd  push    rdi
0x140010bbe  sub     rsp, 30h
0x140010bc2  mov     rax, cs:qword_14000A9E0
0x140010bc9  lea     rcx, qword_14000A9E0
0x140010bd0  cmp     rax, rcx
0x140010bd3  jz      loc_140010C80
0x140010bd9  mov     rdx, cs:qword_14000A9F0
0x140010be0  cmp     rax, rcx
0x140010be3  jz      short loc_140010C4E
0x140010be5  cmp     dword ptr [rax+10h], 0
0x140010be9  jz      short loc_140010BF0
0x140010beb  mov     rax, [rax]
0x140010bee  jmp     short loc_140010BE0
0x140010bf0  mov     rdi, [rax-18h]
0x140010bf4  mov     rbx, 0FFFFF78000000320h
0x140010bfe  xor     ecx, ecx
0x140010c00  mov     rbx, [rbx]
0x140010c03  cmp     rdi, rbx
0x140010c06  jle     short loc_140010C21
0x140010c08  call    cs:__imp_KeQueryTimeIncrement
0x140010c0f  nop     dword ptr [rax+rax+00h]
0x140010c14  sub     rdi, rbx
0x140010c17  mov     eax, eax
0x140010c19  imul    rax, rdi
0x140010c1d  imul    rcx, rax, 64h ; 'd'
0x140010c21  mov     rax, 0A3D70A3D70A3D70Bh
0x140010c2b  imul    rcx
0x140010c2e  add     rdx, rcx
0x140010c31  sar     rdx, 6
0x140010c35  mov     rax, rdx
0x140010c38  shr     rax, 3Fh
0x140010c3c  add     rdx, rax
0x140010c3f  cmp     rdx, cs:qword_14000A9F0
0x140010c46  cmovg   rdx, cs:qword_14000A9F0
0x140010c4e  neg     rdx; DueTime
0x140010c51  lea     rax, MupiPrefixGarbageCollectionDpc
0x140010c58  mov     r9d, 3E8h; TolerableDelay
0x140010c5e  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, rdx
0x140010c65  xor     r8d, r8d; Period
0x140010c68  mov     [rsp+38h+Dpc], rax; Dpc
0x140010c6d  lea     rcx, MupiPrefixGarbageCollectionTimer; Timer
0x140010c74  call    cs:__imp_KeSetCoalescableTimer
0x140010c7b  nop     dword ptr [rax+rax+00h]
0x140010c80  mov     rbx, [rsp+38h+arg_0]
0x140010c85  add     rsp, 30h
0x140010c89  pop     rdi
0x140010c8a  retn
```
