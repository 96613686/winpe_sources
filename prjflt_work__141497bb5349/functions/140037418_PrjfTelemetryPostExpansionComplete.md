# PrjfTelemetryPostExpansionComplete

- ea: `0x140037418`
- end: `0x1400376d7`
- name: `PrjfTelemetryPostExpansionComplete`
- size: `703`
- prototype: `__int64 __fastcall(unsigned __int8, __int64, __int64, int, __int64, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140029f60`

## callees

- `0x14000af84`
- `0x14000ba20`
- `0x14000d754`
- `0x1400115e8`
- `0x1400370c0`
- `0x140037418`

## pseudocode

```c
__int64 __fastcall PrjfTelemetryPostExpansionComplete(
        unsigned __int8 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned __int64 a6,
        __int64 a7)
{
  __int64 v7; // rax
  int v9; // ebx
  int v10; // r15d
  __int64 v11; // rcx
  __int64 result; // rax
  int v13; // ebx
  int v14; // [rsp+70h] [rbp-90h] BYREF
  int v15; // [rsp+74h] [rbp-8Ch] BYREF
  __int128 v16; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+88h] [rbp-78h] BYREF
  __int64 v18; // [rsp+90h] [rbp-70h] BYREF
  __int64 v19; // [rsp+98h] [rbp-68h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v22; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+B8h] [rbp-48h] BYREF
  char v24[32]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v25; // [rsp+E0h] [rbp-20h]
  __int64 v26; // [rsp+E8h] [rbp-18h]
  __int64 *v27; // [rsp+F0h] [rbp-10h]
  __int64 v28; // [rsp+F8h] [rbp-8h]
  __int64 *v29; // [rsp+100h] [rbp+0h]
  __int64 v30; // [rsp+108h] [rbp+8h]
  __int64 *v31; // [rsp+110h] [rbp+10h]
  __int64 v32; // [rsp+118h] [rbp+18h]
  __int64 *v33; // [rsp+120h] [rbp+20h]
  __int64 v34; // [rsp+128h] [rbp+28h]
  int *v35; // [rsp+130h] [rbp+30h]
  __int64 v36; // [rsp+138h] [rbp+38h]
  unsigned __int64 *v37; // [rsp+140h] [rbp+40h]
  __int64 v38; // [rsp+148h] [rbp+48h]
  int *v39; // [rsp+150h] [rbp+50h]
  __int64 v40; // [rsp+158h] [rbp+58h]
  __int64 *v41; // [rsp+160h] [rbp+60h]
  __int64 v42; // [rsp+168h] [rbp+68h]

  v7 = *(_QWORD *)(a3 + 272);
  v9 = a2;
  v10 = a1;
  v16 = 0;
  v11 = *(_QWORD *)(v7 + 72);
  WORD1(v16) = *(_WORD *)(v11 + 288);
  LOWORD(v16) = WORD1(v16);
  *((_QWORD *)&v16 + 1) = v11 + 290;
  if ( a4 < 0 )
  {
    result = (__int64)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 4;
    if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      result = WPP_RECORDER_AND_TRACE_SF_sDdZ(
                 522,
                 a2,
                 a3,
                 *((_QWORD *)WPP_GLOBAL_Control + 8),
                 2,
                 10,
                 14,
                 (__int64)WPP_cead7f9b79fe32a96920046e878d7ba9_Traceguids,
                 (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\telemetry.c",
                 145,
                 a4,
                 (__int64)&v16);
    }
  }
  else
  {
    result = (__int64)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3E0) & 4;
    if ( (BYTE1(xmmword_14001A3E0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      result = WPP_RECORDER_AND_TRACE_SF_sDZLii(v11, a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 8));
    }
  }
  v13 = v9 - 1;
  if ( v13 )
  {
    if ( v13 == 1 )
      return PrjfTelemetryPostDirectoryExpansionComplete(v10, a2, a4, a5, a6, a7);
  }
  else
  {
    result = (unsigned int)dword_14001A068;
    if ( (unsigned int)dword_14001A068 > 5 )
    {
      result = qword_14001A078;
      if ( (qword_14001A078 & 0x400000000000LL) != 0 )
      {
        result = qword_14001A080 & 0x400000000000LL;
        if ( (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
        {
          v17 = 1;
          v25 = &v17;
          v26 = 8;
          v27 = &v18;
          v18 = a7;
          v28 = 8;
          v19 = a7 * a7;
          v29 = &v19;
          v31 = &v20;
          v33 = &v21;
          v35 = &v14;
          v37 = &v22;
          v39 = &v15;
          v41 = &v23;
          v30 = 8;
          v20 = a7;
          v32 = 8;
          v21 = a7;
          v34 = 8;
          v14 = v10;
          v36 = 4;
          v22 = (a6 >> 11) & -(__int64)(a6 != 0);
          v38 = 8;
          v15 = a4;
          v40 = 4;
          v23 = 0x1000000;
          v42 = 8;
          return tlgWriteAgg(a6 != 0 ? a6 >> 11 : 0, (unsigned int)byte_140016DE3, 0, 11, (__int64)v24);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140037418  mov     [rsp-8+arg_8], rbx
0x14003741d  push    rbp
0x14003741e  push    rsi
0x14003741f  push    rdi
0x140037420  push    r14
0x140037422  push    r15
0x140037424  lea     rbp, [rsp-80h]
0x140037429  sub     rsp, 180h
0x140037430  mov     rax, cs:__security_cookie
0x140037437  xor     rax, rsp
0x14003743a  mov     [rbp+0A0h+var_30], rax
0x14003743e  mov     rax, [r8+110h]
0x140037445  xorps   xmm0, xmm0
0x140037448  mov     rsi, [rbp+0A0h+arg_30]
0x14003744f  mov     r14d, r9d
0x140037452  mov     rdi, [rbp+0A0h+arg_28]
0x140037459  mov     ebx, edx
0x14003745b  movzx   r15d, cl
0x14003745f  movups  [rsp+1A0h+var_128], xmm0
0x140037464  mov     rcx, [rax+48h]
0x140037468  movzx   eax, word ptr [rcx+120h]
0x14003746f  mov     word ptr [rsp+1A0h+var_128+2], ax
0x140037474  mov     word ptr [rsp+1A0h+var_128], ax
0x140037479  lea     rax, [rcx+122h]
0x140037480  mov     qword ptr [rbp+0A0h+var_128+8], rax
0x140037484  test    r9d, r9d
0x140037487  js      short loc_1400374D9
0x140037489  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14003748f  lea     rax, WPP_RECORDER_INITIALIZED
0x140037496  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003749d  setnz   r8b
0x1400374a1  and     dl, 4
0x1400374a4  jnz     short loc_1400374AF
0x1400374a6  test    r8b, r8b
0x1400374a9  jz      loc_140037553
0x1400374af  mov     r9, cs:WPP_GLOBAL_Control
0x1400374b6  lea     rax, [rsp+1A0h+var_128]
0x1400374bb  mov     [rsp+1A0h+var_138], rdi
0x1400374c0  mov     [rsp+1A0h+var_140], rsi
0x1400374c5  mov     dword ptr [rsp+1A0h+var_148], ebx
0x1400374c9  mov     r9, [r9+40h]
0x1400374cd  mov     [rsp+1A0h+var_150], rax
0x1400374d2  call    WPP_RECORDER_AND_TRACE_SF_sDZLii
0x1400374d7  jmp     short loc_140037553
0x1400374d9  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400374df  lea     rax, WPP_RECORDER_INITIALIZED
0x1400374e6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400374ed  setnz   r8b
0x1400374f1  and     dl, 4
0x1400374f4  jnz     short loc_1400374FB
0x1400374f6  test    r8b, r8b
0x1400374f9  jz      short loc_140037553
0x1400374fb  mov     r9, cs:WPP_GLOBAL_Control
0x140037502  lea     rax, [rsp+1A0h+var_128]
0x140037507  mov     [rsp+1A0h+var_148], rax
0x14003750c  mov     ecx, 20Ah
0x140037511  mov     dword ptr [rsp+1A0h+var_150], r14d
0x140037516  lea     rax, aOnecoreBaseFsG_4; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003751d  mov     [rsp+1A0h+var_158], 191h
0x140037525  mov     r9, [r9+40h]
0x140037529  mov     [rsp+1A0h+var_160], rax
0x14003752e  lea     rax, WPP_cead7f9b79fe32a96920046e878d7ba9_Traceguids
0x140037535  mov     [rsp+1A0h+var_168], rax
0x14003753a  mov     [rsp+1A0h+var_170], 0Eh
0x140037541  mov     dword ptr [rsp+1A0h+var_178], 0Ah
0x140037549  mov     byte ptr [rsp+1A0h+var_180], 2
0x14003754e  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140037553  sub     ebx, 1
0x140037556  jz      short loc_140037582
0x140037558  cmp     ebx, 1
0x14003755b  jnz     loc_1400376B3
0x140037561  mov     r9, [rbp+0A0h+arg_20]
0x140037568  mov     r8d, r14d
0x14003756b  mov     [rsp+1A0h+var_178], rsi
0x140037570  mov     cl, r15b
0x140037573  mov     [rsp+1A0h+var_180], rdi
0x140037578  call    PrjfTelemetryPostDirectoryExpansionComplete
0x14003757d  jmp     loc_1400376B3
0x140037582  mov     rax, rdi
0x140037585  shr     rax, 0Bh
0x140037589  neg     rdi
0x14003758c  sbb     rcx, rcx
0x14003758f  and     rcx, rax
0x140037592  mov     eax, cs:dword_14001A068
0x140037598  cmp     eax, 5
0x14003759b  jbe     loc_1400376B3
0x1400375a1  mov     rdx, cs:qword_14001A080
0x1400375a8  mov     r8, 400000000000h
0x1400375b2  mov     rax, cs:qword_14001A078
0x1400375b9  test    r8, rax
0x1400375bc  jz      loc_1400376B3
0x1400375c2  mov     rax, rdx
0x1400375c5  and     rax, r8
0x1400375c8  cmp     rax, rdx
0x1400375cb  jnz     loc_1400376B3
0x1400375d1  lea     rax, [rbp+0A0h+var_118]
0x1400375d5  mov     [rbp+0A0h+var_118], 1
0x1400375dd  mov     [rbp+0A0h+var_C0], rax
0x1400375e1  lea     rdx, byte_140016DE3
0x1400375e8  lea     rax, [rbp+0A0h+var_110]
0x1400375ec  mov     [rbp+0A0h+var_B8], 8
0x1400375f4  mov     [rbp+0A0h+var_B0], rax
0x1400375f8  mov     r9d, 0Bh
0x1400375fe  mov     rax, rsi
0x140037601  mov     [rbp+0A0h+var_110], rsi
0x140037605  imul    rax, rsi
0x140037609  mov     [rbp+0A0h+var_A8], 8
0x140037611  mov     [rbp+0A0h+var_108], rax
0x140037615  lea     rax, [rbp+0A0h+var_108]
0x140037619  mov     [rbp+0A0h+var_A0], rax
0x14003761d  lea     rax, [rbp+0A0h+var_100]
0x140037621  mov     [rbp+0A0h+var_90], rax
0x140037625  lea     rax, [rbp+0A0h+var_F8]
0x140037629  mov     [rbp+0A0h+var_80], rax
0x14003762d  lea     rax, [rsp+1A0h+var_130]
0x140037632  mov     [rbp+0A0h+var_70], rax
0x140037636  lea     rax, [rbp+0A0h+var_F0]
0x14003763a  mov     [rbp+0A0h+var_60], rax
0x14003763e  lea     rax, [rsp+1A0h+var_12C]
0x140037643  mov     [rbp+0A0h+var_50], rax
0x140037647  lea     rax, [rbp+0A0h+var_E8]
0x14003764b  mov     [rbp+0A0h+var_40], rax
0x14003764f  lea     rax, [rbp+0A0h+var_E0]
0x140037653  mov     [rsp+1A0h+var_180], rax
0x140037658  mov     [rbp+0A0h+var_98], 8
0x140037660  mov     [rbp+0A0h+var_100], rsi
0x140037664  mov     [rbp+0A0h+var_88], 8
0x14003766c  mov     [rbp+0A0h+var_F8], rsi
0x140037670  mov     [rbp+0A0h+var_78], 8
0x140037678  mov     [rsp+1A0h+var_130], r15d
0x14003767d  mov     [rbp+0A0h+var_68], 4
0x140037685  mov     [rbp+0A0h+var_F0], rcx
0x140037689  mov     [rbp+0A0h+var_58], 8
0x140037691  mov     [rsp+1A0h+var_12C], r14d
0x140037696  mov     [rbp+0A0h+var_48], 4
0x14003769e  mov     [rbp+0A0h+var_E8], 1000000h
0x1400376a6  mov     [rbp+0A0h+var_38], 8
0x1400376ae  call    _tlgWriteAgg
0x1400376b3  mov     rcx, [rbp+0A0h+var_30]
0x1400376b7  xor     rcx, rsp; StackCookie
0x1400376ba  call    __security_check_cookie
0x1400376bf  mov     rbx, [rsp+1A0h+arg_8]
0x1400376c7  add     rsp, 180h
0x1400376ce  pop     r15
0x1400376d0  pop     r14
0x1400376d2  pop     rdi
0x1400376d3  pop     rsi
0x1400376d4  pop     rbp
0x1400376d5  retn
```
