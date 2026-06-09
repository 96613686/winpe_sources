# ComputeFlushPeriod

- ea: `0x180017664`
- end: `0x1800176f1`
- name: `ComputeFlushPeriod`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800184d0`

## callees

- `0x180018374`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1, int a2)
{
  __int64 v2; // rax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  v2 = *(_QWORD *)(a1 + 328);
  v5 = a1 >> 4;
  v6 = 0;
  v4 = *(_OWORD *)(*(_QWORD *)(v2 + 8) - 16LL);
  RunningHash(&v6, &v4, 16);
  RunningHash(&v6, &v5, 8);
  return 32769 * ((9 * v6) ^ ((unsigned int)(9 * v6) >> 11)) % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x180017664  mov     [rsp+arg_8], edx
0x180017668  sub     rsp, 38h
0x18001766c  mov     rax, [rcx+148h]
0x180017673  mov     r8d, 10h
0x180017679  shr     rcx, 4
0x18001767d  mov     [rsp+38h+arg_0], rcx
0x180017682  lea     rcx, [rsp+38h+arg_8]
0x180017687  mov     [rsp+38h+arg_8], 0
0x18001768f  mov     rdx, [rax+8]
0x180017693  movups  xmm0, xmmword ptr [rdx-10h]
0x180017697  lea     rdx, [rsp+38h+var_18]
0x18001769c  movdqu  [rsp+38h+var_18], xmm0
0x1800176a2  call    RunningHash
0x1800176a7  lea     rcx, [rsp+38h+arg_8]
0x1800176ac  mov     r8d, 8
0x1800176b2  lea     rdx, [rsp+38h+arg_0]
0x1800176b7  call    RunningHash
0x1800176bc  mov     edx, [rsp+38h+arg_8]
0x1800176c0  lea     eax, [rdx+rdx*8]
0x1800176c3  mov     ecx, eax
0x1800176c5  shr     ecx, 0Bh
0x1800176c8  xor     ecx, eax
0x1800176ca  mov     eax, 6FD91D85h
0x1800176cf  imul    r8d, ecx, 8001h
0x1800176d6  mul     r8d
0x1800176d9  shr     edx, 12h
0x1800176dc  imul    ecx, edx, 927C0h
0x1800176e2  sub     r8d, ecx
0x1800176e5  lea     eax, [r8+927C0h]
0x1800176ec  add     rsp, 38h
0x1800176f0  retn
```
