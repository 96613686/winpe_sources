# WPP_INIT_CONTROL_ARRAY

- ea: `0x180001290`
- end: `0x18000142c`
- name: `WPP_INIT_CONTROL_ARRAY`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001150`

## pseudocode

```c
__int64 *WPP_INIT_CONTROL_ARRAY()
{
  __int64 *result; // rax

  qword_18000A2C8 = 1;
  qword_18000A2C0 = 0;
  WPP_MAIN_CB = (__int64)&qword_18000A2D8;
  qword_18000A2D8 = (__int64)&qword_18000A300;
  qword_18000A300 = (__int64)&qword_18000A328;
  qword_18000A328 = (__int64)&qword_18000A350;
  qword_18000A350 = (__int64)&qword_18000A378;
  qword_18000A378 = (__int64)&qword_18000A3A0;
  qword_18000A3A0 = (__int64)&qword_18000A3C8;
  qword_18000A3C8 = (__int64)&qword_18000A3F0;
  qword_18000A3F0 = (__int64)&qword_18000A418;
  qword_18000A418 = (__int64)&qword_18000A440;
  qword_18000A440 = (__int64)&qword_18000A468;
  result = &qword_18000A490;
  qword_18000A468 = (__int64)&qword_18000A490;
  qword_18000A2E8 = 0;
  qword_18000A2F0 = 1;
  qword_18000A310 = 0;
  qword_18000A318 = 1;
  qword_18000A338 = 0;
  qword_18000A340 = 1;
  qword_18000A360 = 0;
  qword_18000A368 = 1;
  qword_18000A388 = 0;
  qword_18000A390 = 1;
  qword_18000A3B0 = 0;
  qword_18000A3B8 = 1;
  qword_18000A3D8 = 0;
  qword_18000A3E0 = 1;
  qword_18000A400 = 0;
  qword_18000A408 = 1;
  qword_18000A428 = 0;
  qword_18000A430 = 1;
  qword_18000A450 = 0;
  qword_18000A458 = 1;
  qword_18000A478 = 0;
  qword_18000A480 = 1;
  qword_18000A4A0 = 0;
  qword_18000A490 = 0;
  qword_18000A4A8 = 1;
  return result;
}

```

## disassembly

```asm
0x180001290  xor     ecx, ecx
0x180001292  mov     cs:qword_18000A2C8, 1
0x18000129d  lea     rax, qword_18000A2D8
0x1800012a4  mov     cs:qword_18000A2C0, rcx
0x1800012ab  mov     cs:WPP_MAIN_CB, rax
0x1800012b2  lea     rax, qword_18000A300
0x1800012b9  mov     cs:qword_18000A2D8, rax
0x1800012c0  lea     rax, qword_18000A328
0x1800012c7  mov     cs:qword_18000A300, rax
0x1800012ce  lea     rax, qword_18000A350
0x1800012d5  mov     cs:qword_18000A328, rax
0x1800012dc  lea     rax, qword_18000A378
0x1800012e3  mov     cs:qword_18000A350, rax
0x1800012ea  lea     rax, qword_18000A3A0
0x1800012f1  mov     cs:qword_18000A378, rax
0x1800012f8  lea     rax, qword_18000A3C8
0x1800012ff  mov     cs:qword_18000A3A0, rax
0x180001306  lea     rax, qword_18000A3F0
0x18000130d  mov     cs:qword_18000A3C8, rax
0x180001314  lea     rax, qword_18000A418
0x18000131b  mov     cs:qword_18000A3F0, rax
0x180001322  lea     rax, qword_18000A440
0x180001329  mov     cs:qword_18000A418, rax
0x180001330  lea     rax, qword_18000A468
0x180001337  mov     cs:qword_18000A440, rax
0x18000133e  lea     rax, qword_18000A490
0x180001345  mov     cs:qword_18000A468, rax
0x18000134c  mov     cs:qword_18000A2E8, rcx
0x180001353  mov     cs:qword_18000A2F0, 1
0x18000135e  mov     cs:qword_18000A310, rcx
0x180001365  mov     cs:qword_18000A318, 1
0x180001370  mov     cs:qword_18000A338, rcx
0x180001377  mov     cs:qword_18000A340, 1
0x180001382  mov     cs:qword_18000A360, rcx
0x180001389  mov     cs:qword_18000A368, 1
0x180001394  mov     cs:qword_18000A388, rcx
0x18000139b  mov     cs:qword_18000A390, 1
0x1800013a6  mov     cs:qword_18000A3B0, rcx
0x1800013ad  mov     cs:qword_18000A3B8, 1
0x1800013b8  mov     cs:qword_18000A3D8, rcx
0x1800013bf  mov     cs:qword_18000A3E0, 1
0x1800013ca  mov     cs:qword_18000A400, rcx
0x1800013d1  mov     cs:qword_18000A408, 1
0x1800013dc  mov     cs:qword_18000A428, rcx
0x1800013e3  mov     cs:qword_18000A430, 1
0x1800013ee  mov     cs:qword_18000A450, rcx
0x1800013f5  mov     cs:qword_18000A458, 1
0x180001400  mov     cs:qword_18000A478, rcx
0x180001407  mov     cs:qword_18000A480, 1
0x180001412  mov     cs:qword_18000A4A0, rcx
0x180001419  mov     cs:qword_18000A490, rcx
0x180001420  mov     cs:qword_18000A4A8, 1
0x18000142b  retn
```
