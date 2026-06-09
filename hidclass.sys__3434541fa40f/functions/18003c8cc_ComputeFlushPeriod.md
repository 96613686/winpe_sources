# ComputeFlushPeriod

- ea: `0x18003c8cc`
- end: `0x18003c954`
- name: `ComputeFlushPeriod`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003d128`

## callees

- `0x18002744c`
- `0x18002796c`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1, unsigned int a2)
{
  __int64 v2; // rax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  v2 = *(_QWORD *)(a1 + 344);
  v5 = a1 >> 4;
  v6 = 0;
  v4 = *(_OWORD *)(*(_QWORD *)(v2 + 8) - 16LL);
  RunningHash(&v6, &v4, 16);
  RunningHash(&v6, &v5, 8);
  FinishHash(&v6);
  return v6 % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x18003c8cc  mov     [rsp+arg_8], edx
0x18003c8d0  sub     rsp, 38h
0x18003c8d4  mov     rax, [rcx+158h]
0x18003c8db  mov     r8d, 10h
0x18003c8e1  shr     rcx, 4
0x18003c8e5  mov     [rsp+38h+arg_0], rcx
0x18003c8ea  lea     rcx, [rsp+38h+arg_8]
0x18003c8ef  mov     [rsp+38h+arg_8], 0
0x18003c8f7  mov     rdx, [rax+8]
0x18003c8fb  movups  xmm0, xmmword ptr [rdx-10h]
0x18003c8ff  lea     rdx, [rsp+38h+var_18]
0x18003c904  movdqu  [rsp+38h+var_18], xmm0
0x18003c90a  call    RunningHash
0x18003c90f  lea     rcx, [rsp+38h+arg_8]
0x18003c914  mov     r8d, 8
0x18003c91a  lea     rdx, [rsp+38h+arg_0]
0x18003c91f  call    RunningHash
0x18003c924  lea     rcx, [rsp+38h+arg_8]
0x18003c929  call    FinishHash
0x18003c92e  mov     r8d, [rsp+38h+arg_8]
0x18003c933  mov     eax, 6FD91D85h
0x18003c938  mul     r8d
0x18003c93b  shr     edx, 12h
0x18003c93e  imul    ecx, edx, 927C0h
0x18003c944  sub     r8d, ecx
0x18003c947  lea     eax, [r8+927C0h]
0x18003c94e  add     rsp, 38h
0x18003c952  retn
```
