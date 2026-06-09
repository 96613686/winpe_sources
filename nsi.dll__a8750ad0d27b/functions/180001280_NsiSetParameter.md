# NsiSetParameter

- ea: `0x180001280`
- end: `0x180001321`
- name: `NsiSetParameter`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800013b0`

## pseudocode

```c
DWORD __fastcall NsiSetParameter(
        int a1,
        int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        DWORD a9,
        DWORD a10)
{
  _QWORD v11[3]; // [rsp+30h] [rbp-58h] BYREF
  int v12; // [rsp+48h] [rbp-40h]
  int v13; // [rsp+4Ch] [rbp-3Ch]
  int v14; // [rsp+50h] [rbp-38h]
  int v15; // [rsp+54h] [rbp-34h]
  __int64 v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+60h] [rbp-28h]
  int v18; // [rsp+64h] [rbp-24h]
  int v19; // [rsp+68h] [rbp-20h]
  int v20; // [rsp+6Ch] [rbp-1Ch]
  __int64 v21; // [rsp+70h] [rbp-18h]
  DWORD v22[4]; // [rsp+78h] [rbp-10h] BYREF

  v11[2] = a3;
  v12 = a4;
  v11[0] = 0;
  v11[1] = 0;
  v13 = 0;
  v18 = 0;
  v20 = 0;
  v14 = a1;
  v15 = a2;
  v16 = a5;
  v17 = a6;
  v19 = a7;
  v21 = a8;
  v22[0] = a9;
  v22[1] = a10;
  return NsiIoctl(0x12000Bu, v11, 0x50u, v11, v22, 0);
}

```

## disassembly

```asm
0x180001280  mov     r11, rsp
0x180001283  sub     rsp, 88h
0x18000128a  mov     rax, [rsp+88h+arg_20]
0x180001292  xor     r10d, r10d
0x180001295  mov     [r11-48h], r8
0x180001299  mov     r8d, 50h ; 'P'; nInBufferSize
0x18000129f  mov     [r11-40h], r9d
0x1800012a3  lea     r9, [r11-58h]; lpOutBuffer
0x1800012a7  mov     [r11-58h], r10
0x1800012ab  mov     [r11-50h], r10
0x1800012af  mov     [r11-3Ch], r10d
0x1800012b3  mov     [r11-24h], r10d
0x1800012b7  mov     [r11-1Ch], r10d
0x1800012bb  mov     [rsp+88h+var_38], ecx
0x1800012bf  mov     ecx, 12000Bh; dwIoControlCode
0x1800012c4  mov     [rsp+88h+var_34], edx
0x1800012c8  lea     rdx, [r11-58h]; lpInBuffer
0x1800012cc  mov     [r11-30h], rax
0x1800012d0  mov     eax, [rsp+88h+arg_28]
0x1800012d7  mov     [rsp+88h+var_28], eax
0x1800012db  mov     eax, [rsp+88h+arg_30]
0x1800012e2  mov     [rsp+88h+var_20], eax
0x1800012e6  mov     rax, [rsp+88h+arg_38]
0x1800012ee  mov     [r11-18h], rax
0x1800012f2  mov     eax, [rsp+88h+arg_40]
0x1800012f9  mov     [rsp+88h+var_10], eax
0x1800012fd  mov     eax, [rsp+88h+arg_48]
0x180001304  mov     [rsp+88h+var_C], eax
0x180001308  lea     rax, [r11-10h]
0x18000130c  mov     [r11-60h], r10
0x180001310  mov     [r11-68h], rax
0x180001314  call    NsiIoctl
0x180001319  add     rsp, 88h
0x180001320  retn
```
