# NTCheckSetCancelRoutine

- ea: `0x14000dccc`
- end: `0x14000dd34`
- name: `NTCheckSetCancelRoutine`
- size: `104`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c28c`
- `0x14000dd3c`
- `0x14001ba80`
- `0x1400299b0`
- `0x14002a64c`
- `0x14003027c`
- `0x1400304c8`
- `0x1400485e8`
- `0x14004f224`
- `0x140050ba0`

## callees

- `0x14000dccc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000dd0b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000dd0b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000dce5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000dce5`

## pseudocode

```c
__int64 __fastcall NTCheckSetCancelRoutine(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi

  IoAcquireCancelSpinLock((PKIRQL)(a1 + 69));
  if ( *(_BYTE *)(a1 + 68) )
  {
    v4 = -1073741536;
    *(_DWORD *)(a1 + 48) = -1073741536;
  }
  else
  {
    *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
    _InterlockedExchange64((volatile __int64 *)(a1 + 104), a2);
    v4 = 0;
  }
  IoReleaseCancelSpinLock(*(_BYTE *)(a1 + 69));
  return v4;
}

```

## disassembly

```asm
0x14000dccc  mov     [rsp+arg_0], rbx
0x14000dcd1  mov     [rsp+arg_8], rsi
0x14000dcd6  push    rdi
0x14000dcd7  sub     rsp, 20h
0x14000dcdb  mov     rbx, rcx
0x14000dcde  mov     rdi, rdx
0x14000dce1  add     rcx, 45h ; 'E'; Irql
0x14000dce5  call    cs:__imp_IoAcquireCancelSpinLock
0x14000dcec  nop     dword ptr [rax+rax+00h]
0x14000dcf1  cmp     byte ptr [rbx+44h], 0
0x14000dcf5  jnz     short loc_14000DD2A
0x14000dcf7  mov     rax, [rbx+0B8h]
0x14000dcfe  or      byte ptr [rax+3], 1
0x14000dd02  xchg    rdi, [rbx+68h]
0x14000dd06  xor     edi, edi
0x14000dd08  mov     cl, [rbx+45h]; Irql
0x14000dd0b  call    cs:__imp_IoReleaseCancelSpinLock
0x14000dd12  nop     dword ptr [rax+rax+00h]
0x14000dd17  mov     rbx, [rsp+28h+arg_0]
0x14000dd1c  mov     eax, edi
0x14000dd1e  mov     rsi, [rsp+28h+arg_8]
0x14000dd23  add     rsp, 20h
0x14000dd27  pop     rdi
0x14000dd28  retn
0x14000dd2a  mov     edi, 0C0000120h
0x14000dd2f  mov     [rbx+30h], edi
0x14000dd32  jmp     short loc_14000DD08
```
