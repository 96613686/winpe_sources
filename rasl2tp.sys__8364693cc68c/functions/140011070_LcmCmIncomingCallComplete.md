# LcmCmIncomingCallComplete

- ea: `0x140011070`
- end: `0x1400110b2`
- name: `LcmCmIncomingCallComplete`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011518`

## callees

- `0x140011070`
- `0x14001ac30`
- `0x14001c050`

## pseudocode

```c
__int64 __fastcall LcmCmIncomingCallComplete(unsigned int a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 result; // rax
  int v4; // [rsp+28h] [rbp-30h]
  int v5; // [rsp+30h] [rbp-28h]

  if ( *(_DWORD *)(a2 + 16) == 861155916 )
  {
    v2 = *(_QWORD *)(a2 + 32);
    ScheduleTunnelWork(v2, a2, (__int64)IncomingCallCompletePassive, a1, 0, v4, v5, 0);
    return DereferenceTunnel(v2);
  }
  return result;
}

```

## disassembly

```asm
0x140011070  push    rbx
0x140011072  sub     rsp, 50h
0x140011076  cmp     dword ptr [rdx+10h], 3354324Ch
0x14001107d  jnz     short loc_1400110AB
0x14001107f  mov     rbx, [rdx+20h]
0x140011083  lea     r8, IncomingCallCompletePassive
0x14001108a  mov     r9d, ecx
0x14001108d  mov     rcx, rbx
0x140011090  mov     [rsp+58h+var_20], 0
0x140011095  mov     [rsp+58h+var_38], 0
0x14001109e  call    ScheduleTunnelWork
0x1400110a3  mov     rcx, rbx
0x1400110a6  call    DereferenceTunnel
0x1400110ab  add     rsp, 50h
0x1400110af  pop     rbx
0x1400110b0  retn
```
