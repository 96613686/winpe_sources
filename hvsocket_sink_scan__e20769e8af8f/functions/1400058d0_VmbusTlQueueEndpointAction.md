# VmbusTlQueueEndpointAction

- ea: `0x1400058d0`
- end: `0x1400059af`
- name: `VmbusTlQueueEndpointAction`
- size: `223`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e90`
- `0x1400020c4`
- `0x1400023b0`
- `0x140002d08`
- `0x140002e48`
- `0x140003034`
- `0x14000309c`
- `0x140003ee8`
- `0x140003fe0`
- `0x140004750`
- `0x1400049a0`
- `0x140004e9c`
- `0x1400051b0`
- `0x140005d74`
- `0x140007130`
- `0x140007794`
- `0x140007b00`
- `0x140008200`
- `0x1400083f0`
- `0x140019290`
- `0x140019fc0`
- `0x14001b800`
- `0x14001c2d0`
- `0x1400209c0`
- `0x140020b80`
- `0x140021550`

## callees

- `0x1400058d0`
- `0x140009834`
- `0x14000a048`

## import_xrefs

- `NETIO!NetioInsertWorkQueue` at `0x140005998`
- `NETIO!NetioInsertWorkQueue` at `0x140005998`

## pseudocode

```c
__int64 __fastcall VmbusTlQueueEndpointAction(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // ebx
  int v8; // ebx

  v5 = a3;
  if ( (unsigned int)dword_140013058 > 4 )
    HvsocketTraceEndpointEvent("VmbusTlQueueEndpointAction", a1, a3);
  *(_DWORD *)(a2 + 8) = v5;
  *(_QWORD *)(a2 + 16) = a1;
  if ( a4 )
  {
    v8 = v5 - 2;
    if ( v8 )
    {
      if ( v8 == 1 )
        *(_BYTE *)(a2 + 24) = *(_BYTE *)a4;
    }
    else
    {
      *(_OWORD *)(a2 + 24) = *(_OWORD *)a4;
      *(_QWORD *)(a2 + 40) = *(_QWORD *)(a4 + 16);
    }
  }
  else
  {
    *(_OWORD *)(a2 + 24) = 0;
    *(_QWORD *)(a2 + 40) = 0;
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlQueueEndpointAction",
      128,
      a1,
      *(_QWORD *)(a1 + 8),
      (const int *)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8)) <= 1 )
    __fastfail(0xEu);
  return NetioInsertWorkQueue(*(_QWORD *)(a1 + 192) + 8LL, a2);
}

```

## disassembly

```asm
0x1400058d0  push    rbx
0x1400058d2  push    rsi
0x1400058d3  push    rdi
0x1400058d4  push    r14
0x1400058d6  sub     rsp, 38h
0x1400058da  mov     eax, cs:dword_140013058
0x1400058e0  mov     r14, r9
0x1400058e3  mov     ebx, r8d
0x1400058e6  mov     rdi, rdx
0x1400058e9  mov     rsi, rcx
0x1400058ec  cmp     eax, 4
0x1400058ef  jbe     short loc_140005900
0x1400058f1  mov     rdx, rcx
0x1400058f4  lea     rcx, aVmbustlqueueen; "VmbusTlQueueEndpointAction"
0x1400058fb  call    HvsocketTraceEndpointEvent
0x140005900  mov     [rdi+8], ebx
0x140005903  mov     [rdi+10h], rsi
0x140005907  test    r14, r14
0x14000590a  jz      short loc_140005933
0x14000590c  sub     ebx, 2
0x14000590f  jz      short loc_14000591E
0x140005911  cmp     ebx, 1
0x140005914  jnz     short loc_140005940
0x140005916  mov     al, [r14]
0x140005919  mov     [rdi+18h], al
0x14000591c  jmp     short loc_140005940
0x14000591e  movups  xmm0, xmmword ptr [r14]
0x140005922  movups  xmmword ptr [rdi+18h], xmm0
0x140005926  movsd   xmm1, qword ptr [r14+10h]
0x14000592c  movsd   qword ptr [rdi+28h], xmm1
0x140005931  jmp     short loc_140005940
0x140005933  xorps   xmm0, xmm0
0x140005936  xor     eax, eax
0x140005938  movups  xmmword ptr [rdi+18h], xmm0
0x14000593c  mov     [rdi+28h], rax
0x140005940  mov     eax, cs:dword_140013058
0x140005946  cmp     eax, 5
0x140005949  jbe     short loc_14000596F
0x14000594b  mov     r9, [rsi+8]
0x14000594f  lea     rax, aReferenceObjec; "Reference object"
0x140005956  mov     r8, rsi
0x140005959  mov     [rsp+58h+var_38], rax
0x14000595e  mov     edx, 80h
0x140005963  lea     rcx, aVmbustlqueueen; "VmbusTlQueueEndpointAction"
0x14000596a  call    HvsocketTraceReferenceCount
0x14000596f  mov     eax, 1
0x140005974  lock xadd [rsi+8], rax
0x14000597a  inc     rax
0x14000597d  cmp     rax, 1
0x140005981  jg      short loc_14000598A
0x140005983  mov     ecx, 0Eh
0x140005988  int     29h; Win8: RtlFailFast(ecx)
0x14000598a  mov     rcx, [rsi+0C0h]
0x140005991  mov     rdx, rdi
0x140005994  add     rcx, 8
0x140005998  call    cs:__imp_NetioInsertWorkQueue
0x14000599f  nop     dword ptr [rax+rax+00h]
0x1400059a4  add     rsp, 38h
0x1400059a8  pop     r14
0x1400059aa  pop     rdi
0x1400059ab  pop     rsi
0x1400059ac  pop     rbx
0x1400059ad  retn
```
