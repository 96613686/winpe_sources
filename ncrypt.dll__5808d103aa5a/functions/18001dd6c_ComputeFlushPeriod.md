# ComputeFlushPeriod

- ea: `0x18001dd6c`
- end: `0x18001ddf9`
- name: `ComputeFlushPeriod`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018e90`

## callees

- `0x18001881c`

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
0x18001dd6c  mov     [rsp+arg_8], edx
0x18001dd70  sub     rsp, 38h
0x18001dd74  mov     rax, [rcx+148h]
0x18001dd7b  mov     r8d, 10h
0x18001dd81  shr     rcx, 4
0x18001dd85  mov     [rsp+38h+arg_0], rcx
0x18001dd8a  lea     rcx, [rsp+38h+arg_8]
0x18001dd8f  mov     [rsp+38h+arg_8], 0
0x18001dd97  mov     rdx, [rax+8]
0x18001dd9b  movups  xmm0, xmmword ptr [rdx-10h]
0x18001dd9f  lea     rdx, [rsp+38h+var_18]
0x18001dda4  movdqu  [rsp+38h+var_18], xmm0
0x18001ddaa  call    RunningHash
0x18001ddaf  lea     rcx, [rsp+38h+arg_8]
0x18001ddb4  mov     r8d, 8
0x18001ddba  lea     rdx, [rsp+38h+arg_0]
0x18001ddbf  call    RunningHash
0x18001ddc4  mov     edx, [rsp+38h+arg_8]
0x18001ddc8  lea     eax, [rdx+rdx*8]
0x18001ddcb  mov     ecx, eax
0x18001ddcd  shr     ecx, 0Bh
0x18001ddd0  xor     ecx, eax
0x18001ddd2  mov     eax, 6FD91D85h
0x18001ddd7  imul    r8d, ecx, 8001h
0x18001ddde  mul     r8d
0x18001dde1  shr     edx, 12h
0x18001dde4  imul    ecx, edx, 927C0h
0x18001ddea  sub     r8d, ecx
0x18001dded  lea     eax, [r8+927C0h]
0x18001ddf4  add     rsp, 38h
0x18001ddf8  retn
```
