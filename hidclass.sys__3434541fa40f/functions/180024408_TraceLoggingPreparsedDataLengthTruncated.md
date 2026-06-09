# TraceLoggingPreparsedDataLengthTruncated

- ea: `0x180024408`
- end: `0x1800245ac`
- name: `TraceLoggingPreparsedDataLengthTruncated`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18003d250`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x180024408`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingPreparsedDataLengthTruncated(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int16 a5,
        __int16 a6,
        __int16 a7,
        __int16 a8,
        __int16 a9)
{
  NTSTATUS result; // eax
  int v10; // r8d
  __int16 v11; // r9
  __int64 v12; // r10
  __int16 v13; // r11
  __int16 v14; // ax
  __int16 v15; // ax
  __int16 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v17; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v19; // [rsp+3Ch] [rbp-C4h] BYREF
  __int16 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v21; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v23; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+54h] [rbp-ACh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+60h] [rbp-A0h] BYREF
  __int16 *v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  __int16 *v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  __int16 *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  int *v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  __int16 *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  __int16 *v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  __int16 *v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  __int16 *v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  __int16 *v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  __int16 *v45; // [rsp+110h] [rbp+10h]
  __int64 v46; // [rsp+118h] [rbp+18h]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a3);
    if ( (_BYTE)result )
    {
      if ( v12 )
        v14 = *(_WORD *)(v12 + 108);
      else
        v14 = 0;
      v16 = v14;
      v27 = &v16;
      v28 = 2;
      if ( v12 )
        v15 = *(_WORD *)(v12 + 110);
      else
        v15 = 0;
      v17 = v15;
      v25 = v10;
      v29 = &v17;
      v19 = v11;
      v31 = &v18;
      v30 = 2;
      v33 = &v25;
      v18 = v13;
      v35 = &v19;
      v20 = a5;
      v37 = &v20;
      v21 = a6;
      v39 = &v21;
      v22 = a7;
      v41 = &v22;
      v23 = a8;
      v43 = &v23;
      v24 = a9;
      v45 = &v24;
      v32 = 2;
      v34 = 4;
      v36 = 2;
      v38 = 2;
      v40 = 2;
      v42 = 2;
      v44 = 2;
      v46 = 2;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002CD09,
               0,
               0,
               0xCu,
               &v26);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024408  push    rbp
0x18002440a  lea     rbp, [rsp-30h]
0x18002440f  sub     rsp, 130h
0x180024416  mov     rax, cs:__security_cookie
0x18002441d  xor     rax, rsp
0x180024420  mov     [rbp+30h+var_10], rax
0x180024424  mov     eax, cs:dword_1800310D8
0x18002442a  movzx   r11d, dx
0x18002442e  mov     r10, rcx
0x180024431  cmp     eax, 5
0x180024434  jbe     loc_180024596
0x18002443a  mov     rdx, 400000000000h
0x180024444  lea     rcx, dword_1800310D8
0x18002444b  call    _tlgKeywordOn
0x180024450  xor     ecx, ecx
0x180024452  test    al, al
0x180024454  jz      loc_180024596
0x18002445a  test    r10, r10
0x18002445d  jz      short loc_180024466
0x18002445f  movzx   eax, word ptr [r10+6Ch]
0x180024464  jmp     short loc_180024468
0x180024466  mov     eax, ecx
0x180024468  mov     [rsp+130h+var_100], ax
0x18002446d  lea     rax, [rsp+130h+var_100]
0x180024472  mov     [rbp+30h+var_B0], rax
0x180024476  mov     [rbp+30h+var_A8], 2
0x18002447e  test    r10, r10
0x180024481  jz      short loc_18002448A
0x180024483  movzx   eax, word ptr [r10+6Eh]
0x180024488  jmp     short loc_18002448C
0x18002448a  mov     eax, ecx
0x18002448c  mov     [rsp+130h+var_FC], ax
0x180024491  lea     rdx, byte_18002CD09
0x180024498  lea     rax, [rsp+130h+var_FC]
0x18002449d  mov     [rsp+130h+var_DC], r8d
0x1800244a2  mov     [rbp+30h+var_A0], rax
0x1800244a6  lea     rcx, dword_1800310D8
0x1800244ad  lea     rax, [rsp+130h+var_F8]
0x1800244b2  mov     [rsp+130h+var_F4], r9w
0x1800244b8  mov     [rbp+30h+var_90], rax
0x1800244bc  xor     r9d, r9d
0x1800244bf  lea     rax, [rsp+130h+var_DC]
0x1800244c4  mov     [rbp+30h+var_98], 2
0x1800244cc  mov     [rbp+30h+var_80], rax
0x1800244d0  xor     r8d, r8d
0x1800244d3  lea     rax, [rsp+130h+var_F4]
0x1800244d8  mov     [rsp+130h+var_F8], r11w
0x1800244de  mov     [rbp+30h+var_70], rax
0x1800244e2  movzx   eax, [rbp+30h+arg_20]
0x1800244e6  mov     [rsp+130h+var_F0], ax
0x1800244eb  lea     rax, [rsp+130h+var_F0]
0x1800244f0  mov     [rbp+30h+var_60], rax
0x1800244f4  movzx   eax, [rbp+30h+arg_28]
0x1800244f8  mov     [rsp+130h+var_EC], ax
0x1800244fd  lea     rax, [rsp+130h+var_EC]
0x180024502  mov     [rbp+30h+var_50], rax
0x180024506  movzx   eax, [rbp+30h+arg_30]
0x18002450a  mov     [rsp+130h+var_E8], ax
0x18002450f  lea     rax, [rsp+130h+var_E8]
0x180024514  mov     [rbp+30h+var_40], rax
0x180024518  movzx   eax, [rbp+30h+arg_38]
0x18002451c  mov     [rsp+130h+var_E4], ax
0x180024521  lea     rax, [rsp+130h+var_E4]
0x180024526  mov     [rbp+30h+var_30], rax
0x18002452a  movzx   eax, [rbp+30h+arg_40]
0x180024531  mov     [rsp+130h+var_E0], ax
0x180024536  lea     rax, [rsp+130h+var_E0]
0x18002453b  mov     [rbp+30h+var_20], rax
0x18002453f  lea     rax, [rsp+130h+var_D0]
0x180024544  mov     [rsp+130h+var_108], rax
0x180024549  mov     [rsp+130h+var_110], 0Ch
0x180024551  mov     [rbp+30h+var_88], 2
0x180024559  mov     [rbp+30h+var_78], 4
0x180024561  mov     [rbp+30h+var_68], 2
0x180024569  mov     [rbp+30h+var_58], 2
0x180024571  mov     [rbp+30h+var_48], 2
0x180024579  mov     [rbp+30h+var_38], 2
0x180024581  mov     [rbp+30h+var_28], 2
0x180024589  mov     [rbp+30h+var_18], 2
0x180024591  call    _tlgWriteTransfer_EtwWriteTransfer
0x180024596  mov     rcx, [rbp+30h+var_10]
0x18002459a  xor     rcx, rsp; StackCookie
0x18002459d  call    __security_check_cookie
0x1800245a2  add     rsp, 130h
0x1800245a9  pop     rbp
0x1800245aa  retn
```
