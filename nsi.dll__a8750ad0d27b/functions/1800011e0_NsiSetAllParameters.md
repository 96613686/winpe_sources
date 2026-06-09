# NsiSetAllParameters

- ea: `0x1800011e0`
- end: `0x180001273`
- name: `NsiSetAllParameters`
- size: `147`
- prototype: `__int64 __fastcall(int, int, __int64, int, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800013b0`

## pseudocode

```c
__int64 __fastcall NsiSetAllParameters(int a1, int a2, __int64 a3, int a4, __int64 a5, int a6, __int64 a7, int a8)
{
  _QWORD v9[3]; // [rsp+30h] [rbp-58h] BYREF
  int v10; // [rsp+48h] [rbp-40h]
  int v11; // [rsp+4Ch] [rbp-3Ch]
  int v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+54h] [rbp-34h]
  __int64 v14; // [rsp+58h] [rbp-30h]
  int v15; // [rsp+60h] [rbp-28h]
  int v16; // [rsp+64h] [rbp-24h]
  __int64 v17; // [rsp+68h] [rbp-20h]
  int v18; // [rsp+70h] [rbp-18h]
  int v19; // [rsp+74h] [rbp-14h]

  v9[2] = a3;
  v10 = a4;
  v9[0] = 0;
  v9[1] = 0;
  v11 = 0;
  v16 = 0;
  v19 = 0;
  v12 = a1;
  v13 = a2;
  v14 = a5;
  v15 = a6;
  v17 = a7;
  v18 = a8;
  a6 = 72;
  return NsiIoctl(0x120013u, v9, 0x48u, v9, (LPDWORD)&a6, 0);
}

```

## disassembly

```asm
0x1800011e0  mov     r11, rsp
0x1800011e3  sub     rsp, 88h
0x1800011ea  mov     rax, [rsp+88h+arg_20]
0x1800011f2  xor     r10d, r10d
0x1800011f5  mov     [r11-48h], r8
0x1800011f9  mov     r8d, 48h ; 'H'; nInBufferSize
0x1800011ff  mov     [r11-40h], r9d
0x180001203  lea     r9, [r11-58h]; lpOutBuffer
0x180001207  mov     [r11-58h], r10
0x18000120b  mov     [r11-50h], r10
0x18000120f  mov     [r11-3Ch], r10d
0x180001213  mov     [r11-24h], r10d
0x180001217  mov     [r11-14h], r10d
0x18000121b  mov     [rsp+88h+var_38], ecx
0x18000121f  mov     ecx, 120013h; dwIoControlCode
0x180001224  mov     [rsp+88h+var_34], edx
0x180001228  lea     rdx, [r11-58h]; lpInBuffer
0x18000122c  mov     [r11-30h], rax
0x180001230  mov     eax, [rsp+88h+arg_28]
0x180001237  mov     [rsp+88h+var_28], eax
0x18000123b  mov     rax, [rsp+88h+arg_30]
0x180001243  mov     [r11-20h], rax
0x180001247  mov     eax, [rsp+88h+arg_38]
0x18000124e  mov     [rsp+88h+var_18], eax
0x180001252  lea     rax, [r11+30h]
0x180001256  mov     [r11-60h], r10
0x18000125a  mov     [r11-68h], rax
0x18000125e  mov     dword ptr [r11+30h], 48h ; 'H'
0x180001266  call    NsiIoctl
0x18000126b  add     rsp, 88h
0x180001272  retn
```
