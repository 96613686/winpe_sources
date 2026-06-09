# NsiDeregisterChangeNotification

- ea: `0x180002e40`
- end: `0x180002e8c`
- name: `NsiDeregisterChangeNotification`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiDeregisterChangeNotification(__int64 a1, int a2, __int64 a3)
{
  _QWORD v4[2]; // [rsp+30h] [rbp-38h] BYREF
  int v5; // [rsp+40h] [rbp-28h]
  int v6; // [rsp+44h] [rbp-24h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  __int64 v8; // [rsp+50h] [rbp-18h]
  DWORD v9; // [rsp+78h] [rbp+10h] BYREF

  v4[0] = 0;
  v6 = 0;
  v8 = 0;
  v4[1] = a1;
  v5 = a2;
  v7 = a3;
  v9 = 40;
  return NsiIoctl(0x120023u, v4, 0x28u, v4, &v9, 0);
}

```

## disassembly

```asm
0x180002e40  mov     r11, rsp
0x180002e43  sub     rsp, 68h
0x180002e47  xor     eax, eax
0x180002e49  lea     r9, [r11-38h]; lpOutBuffer
0x180002e4d  mov     [r11-38h], rax
0x180002e51  mov     [rsp+68h+var_24], eax
0x180002e55  mov     [r11-18h], rax
0x180002e59  mov     [r11-30h], rcx
0x180002e5d  mov     ecx, 120023h; dwIoControlCode
0x180002e62  mov     [rsp+68h+var_28], edx
0x180002e66  lea     rdx, [r11-38h]; lpInBuffer
0x180002e6a  mov     [r11-40h], rax
0x180002e6e  mov     [r11-20h], r8
0x180002e72  lea     r8d, [rax+28h]; nInBufferSize
0x180002e76  lea     rax, [r11+10h]
0x180002e7a  mov     [r11+10h], r8d
0x180002e7e  mov     [r11-48h], rax
0x180002e82  call    NsiIoctl
0x180002e87  add     rsp, 68h
0x180002e8b  retn
```
