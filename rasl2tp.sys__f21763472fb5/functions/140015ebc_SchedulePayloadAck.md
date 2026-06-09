# SchedulePayloadAck

- ea: `0x140015ebc`
- end: `0x140015f4d`
- name: `SchedulePayloadAck`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14001b8a0`

## callees

- `0x140001990`
- `0x140015ebc`
- `0x1400181a8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015ee6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015ee6`

## pseudocode

```c
void __fastcall SchedulePayloadAck(__int64 a1, __int64 a2)
{
  PVOID v4; // rax
  _QWORD *v5; // rax
  unsigned int v6; // edx
  unsigned int v7; // r8d

  if ( !*(_QWORD *)(a2 + 272) )
  {
    v4 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 576LL));
    if ( v4 )
    {
      *(_QWORD *)(a2 + 272) = v4;
      v5 = (_QWORD *)ReferenceVc(a2);
      v5[1] = v5;
      *v5 = v5;
      if ( v6 <= v7 )
        v7 = v6;
      TimerQScheduleItem(*(_QWORD *)(a1 + 304), (_DWORD)v5, v7, (unsigned int)PayloadAckTimerEvent, a2);
    }
  }
}

```

## disassembly

```asm
0x140015ebc  mov     [rsp+arg_0], rbx
0x140015ec1  mov     [rsp+arg_8], rsi
0x140015ec6  push    rdi
0x140015ec7  sub     rsp, 30h
0x140015ecb  cmp     qword ptr [rdx+110h], 0
0x140015ed3  mov     rbx, rdx
0x140015ed6  mov     rsi, rcx
0x140015ed9  jnz     short loc_140015F3C
0x140015edb  mov     rdi, [rdx+18h]
0x140015edf  lea     rcx, [rdi+240h]; Lookaside
0x140015ee6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140015eed  nop     dword ptr [rax+rax+00h]
0x140015ef2  test    rax, rax
0x140015ef5  jz      short loc_140015F3C
0x140015ef7  mov     edx, [rbx+10Ch]
0x140015efd  mov     rcx, rbx
0x140015f00  mov     [rbx+110h], rax
0x140015f07  mov     r8d, [rdi+20h]
0x140015f0b  shr     edx, 2
0x140015f0e  call    ReferenceVc
0x140015f13  cmp     edx, r8d
0x140015f16  mov     [rax+8], rax
0x140015f1a  mov     [rax], rax
0x140015f1d  lea     r9, PayloadAckTimerEvent
0x140015f24  mov     rcx, [rsi+130h]
0x140015f2b  cmovbe  r8d, edx
0x140015f2f  mov     rdx, rax
0x140015f32  mov     [rsp+38h+var_18], rbx
0x140015f37  call    TimerQScheduleItem
0x140015f3c  mov     rbx, [rsp+38h+arg_0]
0x140015f41  mov     rsi, [rsp+38h+arg_8]
0x140015f46  add     rsp, 30h
0x140015f4a  pop     rdi
0x140015f4b  retn
```
