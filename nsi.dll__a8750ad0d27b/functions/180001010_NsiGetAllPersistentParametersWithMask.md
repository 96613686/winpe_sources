# NsiGetAllPersistentParametersWithMask

- ea: `0x180001010`
- end: `0x180001098`
- name: `NsiGetAllPersistentParametersWithMask`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiGetAllPersistentParametersWithMask(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  _QWORD v8[3]; // [rsp+30h] [rbp-58h] BYREF
  int v9; // [rsp+48h] [rbp-40h]
  int v10; // [rsp+4Ch] [rbp-3Ch]
  __int64 v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+5Ch] [rbp-2Ch]
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]
  int v16; // [rsp+70h] [rbp-18h]
  int v17; // [rsp+74h] [rbp-14h]

  v8[2] = a1;
  v8[0] = 0;
  v8[1] = 0;
  v10 = 0;
  v13 = 0;
  v17 = 0;
  v9 = a2;
  v15 = a6;
  v14 = a5;
  v11 = a3;
  v12 = a4;
  v16 = a7;
  a7 = 72;
  return NsiIoctl(0x12004Bu, v8, 0x48u, v8, (LPDWORD)&a7, 0);
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  sub     rsp, 88h
0x18000101a  mov     rax, [rsp+88h+arg_28]
0x180001022  xor     r10d, r10d
0x180001025  mov     [r11-48h], rcx
0x180001029  mov     ecx, 12004Bh; dwIoControlCode
0x18000102e  mov     [r11-58h], r10
0x180001032  mov     [r11-50h], r10
0x180001036  mov     [r11-3Ch], r10d
0x18000103a  mov     [r11-2Ch], r10d
0x18000103e  mov     [r11-14h], r10d
0x180001042  mov     [rsp+88h+var_40], edx
0x180001046  lea     rdx, [r11-58h]; lpInBuffer
0x18000104a  mov     [r11-20h], rax
0x18000104e  mov     rax, [rsp+88h+arg_20]
0x180001056  mov     [r11-28h], rax
0x18000105a  mov     eax, [rsp+88h+arg_30]
0x180001061  mov     [r11-38h], r8
0x180001065  mov     r8d, 48h ; 'H'; nInBufferSize
0x18000106b  mov     [r11-30h], r9d
0x18000106f  lea     r9, [r11-58h]; lpOutBuffer
0x180001073  mov     [rsp+88h+var_18], eax
0x180001077  lea     rax, [r11+38h]
0x18000107b  mov     [r11-60h], r10
0x18000107f  mov     [r11-68h], rax
0x180001083  mov     dword ptr [r11+38h], 48h ; 'H'
0x18000108b  call    NsiIoctl
0x180001090  add     rsp, 88h
0x180001097  retn
```
