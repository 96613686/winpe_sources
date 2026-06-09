# PrjfTelemetryPostDirectoryExpansionComplete

- ea: `0x1400370c0`
- end: `0x140037249`
- name: `PrjfTelemetryPostDirectoryExpansionComplete`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140037418`

## callees

- `0x14000af84`
- `0x14000ba20`
- `0x1400370c0`

## pseudocode

```c
NTSTATUS __fastcall PrjfTelemetryPostDirectoryExpansionComplete(
        unsigned __int8 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  NTSTATUS result; // eax
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v18; // [rsp+A0h] [rbp-60h]
  __int64 v19; // [rsp+A8h] [rbp-58h]
  __int64 *v20; // [rsp+B0h] [rbp-50h]
  __int64 v21; // [rsp+B8h] [rbp-48h]
  __int64 *v22; // [rsp+C0h] [rbp-40h]
  __int64 v23; // [rsp+C8h] [rbp-38h]
  __int64 *v24; // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+D8h] [rbp-28h]
  __int64 *v26; // [rsp+E0h] [rbp-20h]
  __int64 v27; // [rsp+E8h] [rbp-18h]
  __int64 *v28; // [rsp+F0h] [rbp-10h]
  __int64 v29; // [rsp+F8h] [rbp-8h]
  __int64 *v30; // [rsp+100h] [rbp+0h]
  __int64 v31; // [rsp+108h] [rbp+8h]
  int *v32; // [rsp+110h] [rbp+10h]
  __int64 v33; // [rsp+118h] [rbp+18h]
  int *v34; // [rsp+120h] [rbp+20h]
  __int64 v35; // [rsp+128h] [rbp+28h]
  __int64 *v36; // [rsp+130h] [rbp+30h]
  __int64 v37; // [rsp+138h] [rbp+38h]

  result = dword_14001A068;
  if ( (unsigned int)dword_14001A068 > 5 )
  {
    result = qword_14001A078;
    if ( (qword_14001A078 & 0x400000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
      {
        v18 = &v9;
        v15 = a4;
        v20 = &v10;
        v9 = 1;
        v19 = 8;
        v11 = a6 * a6;
        v22 = &v11;
        v24 = &v12;
        v26 = &v13;
        v14 = a5;
        v28 = &v14;
        v30 = &v15;
        v32 = &v7;
        v34 = &v8;
        v36 = &v16;
        v10 = a6;
        v21 = 8;
        v23 = 8;
        v12 = a6;
        v25 = 8;
        v13 = a6;
        v27 = 8;
        v29 = 8;
        v31 = 8;
        v7 = a3;
        v33 = 4;
        v8 = a1;
        v35 = 4;
        v16 = 0x1000000;
        v37 = 8;
        return tlgWriteAgg(a6, byte_140016CE7, a3, 0xCu, &v17);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400370c0  push    rbp
0x1400370c2  lea     rbp, [rsp-50h]
0x1400370c7  sub     rsp, 150h
0x1400370ce  mov     rax, cs:__security_cookie
0x1400370d5  xor     rax, rsp
0x1400370d8  mov     [rbp+50h+var_10], rax
0x1400370dc  mov     eax, cs:dword_14001A068
0x1400370e2  movzx   r10d, cl
0x1400370e6  cmp     eax, 5
0x1400370e9  jbe     loc_140037233
0x1400370ef  mov     rdx, cs:qword_14001A080
0x1400370f6  mov     rcx, 400000000000h
0x140037100  mov     rax, cs:qword_14001A078
0x140037107  test    rcx, rax
0x14003710a  jz      loc_140037233
0x140037110  mov     rax, rdx
0x140037113  and     rax, rcx
0x140037116  cmp     rax, rdx
0x140037119  jnz     loc_140037233
0x14003711f  mov     rcx, [rbp+50h+arg_28]
0x140037126  lea     rax, [rsp+150h+var_118]
0x14003712b  mov     [rbp+50h+var_B0], rax
0x14003712f  lea     rdx, byte_140016CE7
0x140037136  lea     rax, [rsp+150h+var_110]
0x14003713b  mov     [rsp+150h+var_E8], r9
0x140037140  mov     [rbp+50h+var_A0], rax
0x140037144  mov     r9d, 0Ch
0x14003714a  mov     rax, rcx
0x14003714d  mov     [rsp+150h+var_118], 1
0x140037156  imul    rax, rcx
0x14003715a  mov     [rbp+50h+var_A8], 8
0x140037162  mov     [rsp+150h+var_108], rax
0x140037167  lea     rax, [rsp+150h+var_108]
0x14003716c  mov     [rbp+50h+var_90], rax
0x140037170  lea     rax, [rsp+150h+var_100]
0x140037175  mov     [rbp+50h+var_80], rax
0x140037179  lea     rax, [rsp+150h+var_F8]
0x14003717e  mov     [rbp+50h+var_70], rax
0x140037182  mov     rax, [rbp+50h+arg_20]
0x140037189  mov     [rsp+150h+var_F0], rax
0x14003718e  lea     rax, [rsp+150h+var_F0]
0x140037193  mov     [rbp+50h+var_60], rax
0x140037197  lea     rax, [rsp+150h+var_E8]
0x14003719c  mov     [rbp+50h+var_50], rax
0x1400371a0  lea     rax, [rsp+150h+var_120]
0x1400371a5  mov     [rbp+50h+var_40], rax
0x1400371a9  lea     rax, [rsp+150h+var_11C]
0x1400371ae  mov     [rbp+50h+var_30], rax
0x1400371b2  lea     rax, [rsp+150h+var_E0]
0x1400371b7  mov     [rbp+50h+var_20], rax
0x1400371bb  lea     rax, [rbp+50h+var_D0]
0x1400371bf  mov     [rsp+150h+var_130], rax
0x1400371c4  mov     [rsp+150h+var_110], rcx
0x1400371c9  mov     [rbp+50h+var_98], 8
0x1400371d1  mov     [rbp+50h+var_88], 8
0x1400371d9  mov     [rsp+150h+var_100], rcx
0x1400371de  mov     [rbp+50h+var_78], 8
0x1400371e6  mov     [rsp+150h+var_F8], rcx
0x1400371eb  mov     [rbp+50h+var_68], 8
0x1400371f3  mov     [rbp+50h+var_58], 8
0x1400371fb  mov     [rbp+50h+var_48], 8
0x140037203  mov     [rsp+150h+var_120], r8d
0x140037208  mov     [rbp+50h+var_38], 4
0x140037210  mov     [rsp+150h+var_11C], r10d
0x140037215  mov     [rbp+50h+var_28], 4
0x14003721d  mov     [rsp+150h+var_E0], 1000000h
0x140037226  mov     [rbp+50h+var_18], 8
0x14003722e  call    _tlgWriteAgg
0x140037233  mov     rcx, [rbp+50h+var_10]
0x140037237  xor     rcx, rsp; StackCookie
0x14003723a  call    __security_check_cookie
0x14003723f  add     rsp, 150h
0x140037246  pop     rbp
0x140037247  retn
```
