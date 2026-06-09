# HbpLogHypervisorMsrAccessTelemetryEvent

- ea: `0x140013c34`
- end: `0x140013dbc`
- name: `HbpLogHypervisorMsrAccessTelemetryEvent`
- size: `392`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, unsigned int, unsigned int, const CHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140013dc4`

## callees

- `0x140001008`
- `0x140001040`
- `0x140001070`
- `0x140002ae0`
- `0x140013c34`

## pseudocode

```c
char __fastcall HbpLogHypervisorMsrAccessTelemetryEvent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7,
        unsigned int a8,
        const CHAR *a9)
{
  char result; // al
  __int64 v10; // r8
  __int16 v11; // r9
  char v12; // r10
  int v13; // r11d
  __int64 v14; // r8
  __int64 v15; // r9
  char v16; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v17; // [rsp+34h] [rbp-CCh] BYREF
  int v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+70h] [rbp-90h] BYREF
  int *v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  char *v28; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+A8h] [rbp-58h]
  __int64 *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  __int16 *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  __int64 *v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  __int64 *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  __int64 *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  __int64 *v40; // [rsp+100h] [rbp+0h]
  __int64 v41; // [rsp+108h] [rbp+8h]
  _BYTE v42[16]; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+128h] [rbp+28h]

  result = dword_140009088;
  if ( (unsigned int)dword_140009088 > 5 )
  {
    result = tlgKeywordOn((__int64)&dword_140009088, 0x400000000001LL);
    if ( result )
    {
      v18 = v13;
      v26 = &v18;
      v27 = 4;
      v28 = &v16;
      v16 = v12;
      v30 = &v19;
      v32 = &v17;
      v20 = a5;
      v34 = &v20;
      v21 = a6;
      v36 = &v21;
      v22 = a7;
      v38 = &v22;
      v23 = a8;
      v40 = &v23;
      v29 = 1;
      v19 = v10;
      v31 = 8;
      v17 = v11;
      v33 = 2;
      v35 = 8;
      v37 = 8;
      v39 = 8;
      v41 = 8;
      tlgCreate1Sz_char((__int64)v42, a9);
      v24 = 0x2000000;
      v43 = &v24;
      v44 = 8;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_140009088,
               (unsigned __int8 *)&unk_1400074D8,
               v14,
               v15,
               0xCu,
               &v25);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013c34  mov     [rsp-8+arg_0], rbx
0x140013c39  push    rbp
0x140013c3a  lea     rbp, [rsp-40h]
0x140013c3f  sub     rsp, 140h
0x140013c46  mov     rax, cs:__security_cookie
0x140013c4d  xor     rax, rsp
0x140013c50  mov     [rbp+40h+var_10], rax
0x140013c54  mov     eax, cs:dword_140009088
0x140013c5a  mov     r10b, dl
0x140013c5d  mov     rbx, [rbp+40h+arg_40]
0x140013c64  mov     r11d, ecx
0x140013c67  cmp     eax, 5
0x140013c6a  jbe     loc_140013D9E
0x140013c70  mov     rdx, 400000000001h
0x140013c7a  lea     rcx, dword_140009088
0x140013c81  call    _tlgKeywordOn
0x140013c86  test    al, al
0x140013c88  jz      loc_140013D9E
0x140013c8e  lea     rax, [rsp+140h+var_108]
0x140013c93  mov     [rsp+140h+var_108], r11d
0x140013c98  mov     [rbp+40h+var_B0], rax
0x140013c9c  lea     rcx, [rbp+40h+var_30]
0x140013ca0  lea     rax, [rsp+140h+var_110]
0x140013ca5  mov     [rbp+40h+var_A8], 4
0x140013cad  mov     [rbp+40h+var_A0], rax
0x140013cb1  mov     rdx, rbx
0x140013cb4  lea     rax, [rsp+140h+var_100]
0x140013cb9  mov     [rsp+140h+var_110], r10b
0x140013cbe  mov     [rbp+40h+var_90], rax
0x140013cc2  lea     rax, [rsp+140h+var_10C]
0x140013cc7  mov     [rbp+40h+var_80], rax
0x140013ccb  mov     rax, [rbp+40h+arg_20]
0x140013ccf  mov     [rsp+140h+var_F8], rax
0x140013cd4  lea     rax, [rsp+140h+var_F8]
0x140013cd9  mov     [rbp+40h+var_70], rax
0x140013cdd  mov     rax, [rbp+40h+arg_28]
0x140013ce1  mov     [rsp+140h+var_F0], rax
0x140013ce6  lea     rax, [rsp+140h+var_F0]
0x140013ceb  mov     [rbp+40h+var_60], rax
0x140013cef  mov     eax, [rbp+40h+arg_30]
0x140013cf5  mov     [rsp+140h+var_E8], rax
0x140013cfa  lea     rax, [rsp+140h+var_E8]
0x140013cff  mov     [rbp+40h+var_50], rax
0x140013d03  mov     eax, [rbp+40h+arg_38]
0x140013d09  mov     [rsp+140h+var_E0], rax
0x140013d0e  lea     rax, [rsp+140h+var_E0]
0x140013d13  mov     [rbp+40h+var_40], rax
0x140013d17  mov     [rbp+40h+var_98], 1
0x140013d1f  mov     [rsp+140h+var_100], r8
0x140013d24  mov     [rbp+40h+var_88], 8
0x140013d2c  mov     [rsp+140h+var_10C], r9w
0x140013d32  mov     [rbp+40h+var_78], 2
0x140013d3a  mov     [rbp+40h+var_68], 8
0x140013d42  mov     [rbp+40h+var_58], 8
0x140013d4a  mov     [rbp+40h+var_48], 8
0x140013d52  mov     [rbp+40h+var_38], 8
0x140013d5a  call    _tlgCreate1Sz_char
0x140013d5f  lea     rax, [rsp+140h+var_D8]
0x140013d64  mov     [rsp+140h+var_D8], 2000000h
0x140013d6d  mov     [rbp+40h+var_20], rax
0x140013d71  lea     rdx, unk_1400074D8; int
0x140013d78  lea     rax, [rsp+140h+var_D0]
0x140013d7d  mov     [rbp+40h+var_18], 8
0x140013d85  mov     [rsp+140h+var_118], rax; __int64
0x140013d8a  lea     rcx, dword_140009088; int
0x140013d91  mov     [rsp+140h+var_120], 0Ch; ULONG
0x140013d99  call    _tlgWriteTransfer_EtwWriteTransfer
0x140013d9e  mov     rcx, [rbp+40h+var_10]
0x140013da2  xor     rcx, rsp; StackCookie
0x140013da5  call    __security_check_cookie
0x140013daa  mov     rbx, [rsp+140h+arg_0]
0x140013db2  add     rsp, 140h
0x140013db9  pop     rbp
0x140013dba  retn
```
