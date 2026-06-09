# TraceLoggingIdleConfiguration

- ea: `0x180024ef0`
- end: `0x1800251ea`
- name: `TraceLoggingIdleConfiguration`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003b748`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x180024ef0`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingIdleConfiguration(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v2; // r8
  __int16 v3; // ax
  __int16 v4; // ax
  int v5; // ecx
  char v6; // [rsp+30h] [rbp-D0h] BYREF
  bool v7; // [rsp+31h] [rbp-CFh] BYREF
  bool v8; // [rsp+32h] [rbp-CEh] BYREF
  bool v9; // [rsp+33h] [rbp-CDh] BYREF
  char v10; // [rsp+34h] [rbp-CCh] BYREF
  bool v11; // [rsp+35h] [rbp-CBh] BYREF
  bool v12; // [rsp+36h] [rbp-CAh] BYREF
  bool v13; // [rsp+37h] [rbp-C9h] BYREF
  char v14; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v15; // [rsp+3Ch] [rbp-C4h] BYREF
  __int16 v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+4Ch] [rbp-B4h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  int v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+5Ch] [rbp-A4h] BYREF
  int v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+64h] [rbp-9Ch] BYREF
  int v26; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+70h] [rbp-90h] BYREF
  __int16 *v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int16 *v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  int *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  int *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  char *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  bool *v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  bool *v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  bool *v42; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h]
  char *v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  bool *v46; // [rsp+120h] [rbp+20h]
  __int64 v47; // [rsp+128h] [rbp+28h]
  bool *v48; // [rsp+130h] [rbp+30h]
  __int64 v49; // [rsp+138h] [rbp+38h]
  bool *v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h]
  char *v52; // [rsp+150h] [rbp+50h]
  __int64 v53; // [rsp+158h] [rbp+58h]
  int *v54; // [rsp+160h] [rbp+60h]
  __int64 v55; // [rsp+168h] [rbp+68h]
  int *v56; // [rsp+170h] [rbp+70h]
  __int64 v57; // [rsp+178h] [rbp+78h]
  int *v58; // [rsp+180h] [rbp+80h]
  __int64 v59; // [rsp+188h] [rbp+88h]
  int *v60; // [rsp+190h] [rbp+90h]
  __int64 v61; // [rsp+198h] [rbp+98h]
  int *v62; // [rsp+1A0h] [rbp+A0h]
  __int64 v63; // [rsp+1A8h] [rbp+A8h]
  int *v64; // [rsp+1B0h] [rbp+B0h]
  __int64 v65; // [rsp+1B8h] [rbp+B8h]
  int *v66; // [rsp+1C0h] [rbp+C0h]
  __int64 v67; // [rsp+1C8h] [rbp+C8h]
  int *v68; // [rsp+1D0h] [rbp+D0h]
  __int64 v69; // [rsp+1D8h] [rbp+D8h]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a1);
    if ( (_BYTE)result )
    {
      if ( v2 )
        v3 = *(_WORD *)(v2 + 108);
      else
        v3 = 0;
      v15 = v3;
      v28 = &v15;
      v29 = 2;
      if ( v2 )
        v4 = *(_WORD *)(v2 + 110);
      else
        v4 = 0;
      v5 = *(_DWORD *)(v2 + 1756);
      v16 = v4;
      v30 = &v16;
      v17 = *(_DWORD *)(v2 + 340);
      v32 = &v17;
      v18 = *(_DWORD *)(v2 + 344);
      v34 = &v18;
      v6 = *(_BYTE *)(v2 + 2056);
      v36 = &v6;
      v31 = 2;
      v7 = (v5 & 2) != 0;
      v33 = 4;
      v38 = &v7;
      v8 = (v5 & 0x30) != 0;
      v35 = 4;
      v40 = &v8;
      v37 = 1;
      v9 = (v5 & 0x40) != 0;
      v42 = &v9;
      v39 = 1;
      v10 = v5 & 1;
      v44 = &v10;
      v41 = 1;
      v11 = (v5 & 4) != 0;
      v46 = &v11;
      v43 = 1;
      v12 = (v5 & 8) != 0;
      v48 = &v12;
      v13 = (v5 & 0x80) != 0;
      v45 = 1;
      v50 = &v13;
      v52 = &v14;
      v19 = *(_DWORD *)(v2 + 1760);
      v54 = &v19;
      v20 = *(_DWORD *)(v2 + 1764);
      v47 = 1;
      v49 = 1;
      v51 = 1;
      v14 = BYTE1(v5) & 1;
      v53 = 1;
      v55 = 4;
      v56 = &v20;
      v21 = *(_DWORD *)(v2 + 1728);
      v57 = 4;
      v58 = &v21;
      v22 = *(_DWORD *)(v2 + 1740);
      v60 = &v22;
      v23 = *(_DWORD *)(v2 + 1736);
      v62 = &v23;
      v24 = *(_DWORD *)(v2 + 1732);
      v64 = &v24;
      v25 = *(_DWORD *)(v2 + 1744);
      v66 = &v25;
      v26 = *(_DWORD *)(v2 + 1748);
      v68 = &v26;
      v59 = 4;
      v61 = 4;
      v63 = 4;
      v65 = 4;
      v67 = 4;
      v69 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)&word_18002D0AE,
               0,
               0,
               0x17u,
               &v27);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024ef0  push    rbp
0x180024ef2  lea     rbp, [rsp-0F0h]
0x180024efa  sub     rsp, 1F0h
0x180024f01  mov     rax, cs:__security_cookie
0x180024f08  xor     rax, rsp
0x180024f0b  mov     [rbp+0F0h+var_10], rax
0x180024f12  mov     eax, cs:dword_1800310D8
0x180024f18  mov     r8, rcx
0x180024f1b  cmp     eax, 5
0x180024f1e  jbe     loc_1800251D1
0x180024f24  mov     rdx, 400000000000h
0x180024f2e  lea     rcx, dword_1800310D8
0x180024f35  call    _tlgKeywordOn
0x180024f3a  xor     r10d, r10d
0x180024f3d  test    al, al
0x180024f3f  jz      loc_1800251D1
0x180024f45  test    r8, r8
0x180024f48  jz      short loc_180024F51
0x180024f4a  movzx   eax, word ptr [r8+6Ch]
0x180024f4f  jmp     short loc_180024F54
0x180024f51  mov     eax, r10d
0x180024f54  mov     [rsp+1F0h+var_1B4], ax
0x180024f59  lea     rax, [rsp+1F0h+var_1B4]
0x180024f5e  mov     [rbp+0F0h+var_160], rax
0x180024f62  mov     [rbp+0F0h+var_158], 2
0x180024f6a  test    r8, r8
0x180024f6d  jz      short loc_180024F76
0x180024f6f  movzx   eax, word ptr [r8+6Eh]
0x180024f74  jmp     short loc_180024F79
0x180024f76  mov     eax, r10d
0x180024f79  mov     ecx, [r8+6DCh]
0x180024f80  mov     edx, 1
0x180024f85  mov     [rsp+1F0h+var_1B0], ax
0x180024f8a  lea     rax, [rsp+1F0h+var_1B0]
0x180024f8f  mov     [rbp+0F0h+var_150], rax
0x180024f93  mov     eax, [r8+154h]
0x180024f9a  mov     [rsp+1F0h+var_1AC], eax
0x180024f9e  lea     rax, [rsp+1F0h+var_1AC]
0x180024fa3  mov     [rbp+0F0h+var_140], rax
0x180024fa7  mov     eax, [r8+158h]
0x180024fae  mov     [rsp+1F0h+var_1A8], eax
0x180024fb2  lea     rax, [rsp+1F0h+var_1A8]
0x180024fb7  mov     [rbp+0F0h+var_130], rax
0x180024fbb  mov     al, [r8+808h]
0x180024fc2  mov     [rsp+1F0h+var_1C0], al
0x180024fc6  lea     rax, [rsp+1F0h+var_1C0]
0x180024fcb  mov     [rbp+0F0h+var_120], rax
0x180024fcf  mov     eax, ecx
0x180024fd1  shr     eax, 1
0x180024fd3  and     al, dl
0x180024fd5  mov     [rbp+0F0h+var_148], 2
0x180024fdd  mov     [rsp+1F0h+var_1BF], al
0x180024fe1  test    cl, 30h
0x180024fe4  lea     rax, [rsp+1F0h+var_1BF]
0x180024fe9  mov     [rbp+0F0h+var_138], 4
0x180024ff1  mov     [rbp+0F0h+var_110], rax
0x180024ff5  setnz   [rsp+1F0h+var_1BE]
0x180024ffa  lea     rax, [rsp+1F0h+var_1BE]
0x180024fff  mov     [rbp+0F0h+var_128], 4
0x180025007  mov     [rbp+0F0h+var_100], rax
0x18002500b  mov     eax, ecx
0x18002500d  shr     eax, 6
0x180025010  and     al, dl
0x180025012  mov     [rbp+0F0h+var_118], rdx
0x180025016  mov     [rsp+1F0h+var_1BD], al
0x18002501a  lea     rax, [rsp+1F0h+var_1BD]
0x18002501f  mov     [rbp+0F0h+var_F0], rax
0x180025023  mov     al, cl
0x180025025  and     al, dl
0x180025027  mov     [rbp+0F0h+var_108], rdx
0x18002502b  mov     [rsp+1F0h+var_1BC], al
0x18002502f  lea     rax, [rsp+1F0h+var_1BC]
0x180025034  mov     [rbp+0F0h+var_E0], rax
0x180025038  mov     eax, ecx
0x18002503a  shr     eax, 2
0x18002503d  and     al, dl
0x18002503f  mov     [rbp+0F0h+var_F8], rdx
0x180025043  mov     [rsp+1F0h+var_1BB], al
0x180025047  lea     rax, [rsp+1F0h+var_1BB]
0x18002504c  mov     [rbp+0F0h+var_D0], rax
0x180025050  mov     eax, ecx
0x180025052  shr     eax, 3
0x180025055  and     al, dl
0x180025057  mov     [rbp+0F0h+var_E8], rdx
0x18002505b  mov     [rsp+1F0h+var_1BA], al
0x18002505f  lea     rax, [rsp+1F0h+var_1BA]
0x180025064  mov     [rbp+0F0h+var_C0], rax
0x180025068  mov     eax, ecx
0x18002506a  shr     eax, 7
0x18002506d  and     al, dl
0x18002506f  shr     ecx, 8
0x180025072  mov     [rsp+1F0h+var_1B9], al
0x180025076  and     cl, dl
0x180025078  lea     rax, [rsp+1F0h+var_1B9]
0x18002507d  mov     [rbp+0F0h+var_D8], rdx
0x180025081  mov     [rbp+0F0h+var_B0], rax
0x180025085  lea     rax, [rsp+1F0h+var_1B8]
0x18002508a  mov     [rbp+0F0h+var_A0], rax
0x18002508e  mov     eax, [r8+6E0h]
0x180025095  mov     [rsp+1F0h+var_1A4], eax
0x180025099  lea     rax, [rsp+1F0h+var_1A4]
0x18002509e  mov     [rbp+0F0h+var_90], rax
0x1800250a2  mov     eax, [r8+6E4h]
0x1800250a9  mov     [rsp+1F0h+var_1A0], eax
0x1800250ad  lea     rax, [rsp+1F0h+var_1A0]
0x1800250b2  mov     [rbp+0F0h+var_C8], rdx
0x1800250b6  mov     [rbp+0F0h+var_B8], rdx
0x1800250ba  mov     [rbp+0F0h+var_A8], rdx
0x1800250be  mov     [rsp+1F0h+var_1B8], cl
0x1800250c2  mov     [rbp+0F0h+var_98], rdx
0x1800250c6  mov     [rbp+0F0h+var_88], 4
0x1800250ce  mov     [rbp+0F0h+var_80], rax
0x1800250d2  lea     rdx, word_18002D0AE
0x1800250d9  mov     eax, [r8+6C0h]
0x1800250e0  lea     rcx, dword_1800310D8
0x1800250e7  mov     [rsp+1F0h+var_19C], eax
0x1800250eb  xor     r9d, r9d
0x1800250ee  lea     rax, [rsp+1F0h+var_19C]
0x1800250f3  mov     [rbp+0F0h+var_78], 4
0x1800250fb  mov     [rbp+0F0h+var_70], rax
0x180025102  mov     eax, [r8+6CCh]
0x180025109  mov     [rsp+1F0h+var_198], eax
0x18002510d  lea     rax, [rsp+1F0h+var_198]
0x180025112  mov     [rbp+0F0h+var_60], rax
0x180025119  mov     eax, [r8+6C8h]
0x180025120  mov     [rsp+1F0h+var_194], eax
0x180025124  lea     rax, [rsp+1F0h+var_194]
0x180025129  mov     [rbp+0F0h+var_50], rax
0x180025130  mov     eax, [r8+6C4h]
0x180025137  mov     [rsp+1F0h+var_190], eax
0x18002513b  lea     rax, [rsp+1F0h+var_190]
0x180025140  mov     [rbp+0F0h+var_40], rax
0x180025147  mov     eax, [r8+6D0h]
0x18002514e  mov     [rsp+1F0h+var_18C], eax
0x180025152  lea     rax, [rsp+1F0h+var_18C]
0x180025157  mov     [rbp+0F0h+var_30], rax
0x18002515e  mov     eax, [r8+6D4h]
0x180025165  xor     r8d, r8d
0x180025168  mov     [rsp+1F0h+var_188], eax
0x18002516c  lea     rax, [rsp+1F0h+var_188]
0x180025171  mov     [rbp+0F0h+var_20], rax
0x180025178  lea     rax, [rsp+1F0h+var_180]
0x18002517d  mov     [rsp+1F0h+var_1C8], rax
0x180025182  mov     [rsp+1F0h+var_1D0], 17h
0x18002518a  mov     [rbp+0F0h+var_68], 4
0x180025195  mov     [rbp+0F0h+var_58], 4
0x1800251a0  mov     [rbp+0F0h+var_48], 4
0x1800251ab  mov     [rbp+0F0h+var_38], 4
0x1800251b6  mov     [rbp+0F0h+var_28], 4
0x1800251c1  mov     [rbp+0F0h+var_18], 4
0x1800251cc  call    _tlgWriteTransfer_EtwWriteTransfer
0x1800251d1  mov     rcx, [rbp+0F0h+var_10]
0x1800251d8  xor     rcx, rsp; StackCookie
0x1800251db  call    __security_check_cookie
0x1800251e0  add     rsp, 1F0h
0x1800251e7  pop     rbp
0x1800251e8  retn
```
