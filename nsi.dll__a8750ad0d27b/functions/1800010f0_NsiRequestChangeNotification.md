# NsiRequestChangeNotification

- ea: `0x1800010f0`
- end: `0x18000112d`
- name: `NsiRequestChangeNotification`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001140`

## pseudocode

```c
__int64 __fastcall NsiRequestChangeNotification(unsigned int a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  _QWORD InBuffer[2]; // [rsp+20h] [rbp-38h] BYREF
  int v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+34h] [rbp-24h]
  __int64 v9; // [rsp+38h] [rbp-20h]
  __int64 v10; // [rsp+40h] [rbp-18h]

  InBuffer[0] = a1;
  v8 = 0;
  v10 = a5;
  InBuffer[1] = a2;
  v7 = a3;
  v9 = a4;
  return NsiRequestChangeNotificationEx(InBuffer);
}

```

## disassembly

```asm
0x1800010f0  sub     rsp, 58h
0x1800010f4  xor     eax, eax
0x1800010f6  mov     [rsp+58h+InBuffer], ecx
0x1800010fa  mov     [rsp+58h+var_34], eax
0x1800010fe  lea     rcx, [rsp+58h+InBuffer]; lpInBuffer
0x180001103  mov     [rsp+58h+var_24], eax
0x180001107  mov     rax, [rsp+58h+arg_20]
0x18000110f  mov     [rsp+58h+var_18], rax
0x180001114  mov     [rsp+58h+var_30], rdx
0x180001119  mov     [rsp+58h+var_28], r8d
0x18000111e  mov     [rsp+58h+var_20], r9
0x180001123  call    NsiRequestChangeNotificationEx
0x180001128  add     rsp, 58h
0x18000112c  retn
```
