# buildInfAndRpt

- ea: `0x140003f68`
- end: `0x140004391`
- name: `buildInfAndRpt`
- size: `1065`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007934`

## callees

- `0x14000328c`
- `0x140003f68`
- `0x1400078ac`
- `0x140008620`
- `0x14000caac`
- `0x14000cb80`
- `0x14000ce88`
- `0x14000dfd8`

## import_xrefs

- `msvcrt!ctime` at `0x14000411a`
- `msvcrt!ctime` at `0x14000411a`
- `msvcrt!time` at `0x140003fde`
- `msvcrt!time` at `0x140003fde`
- `msvcrt!fprintf` at `0x140004159`
- `msvcrt!fprintf` at `0x1400041a4`
- `msvcrt!fprintf` at `0x1400041e8`
- `msvcrt!fprintf` at `0x14000422f`
- `msvcrt!fprintf` at `0x1400042a0`
- `msvcrt!fprintf` at `0x140004309`
- `msvcrt!fprintf` at `0x14000434b`
- `msvcrt!fprintf` at `0x140004159`
- `msvcrt!fprintf` at `0x1400041a4`
- `msvcrt!fprintf` at `0x1400041e8`
- `msvcrt!fprintf` at `0x14000422f`
- `msvcrt!fprintf` at `0x1400042a0`
- `msvcrt!fprintf` at `0x140004309`
- `msvcrt!fprintf` at `0x14000434b`
- `msvcrt!fclose` at `0x140004354`
- `msvcrt!fclose` at `0x140004354`
- `msvcrt!fopen` at `0x1400040c3`
- `msvcrt!fopen` at `0x1400040c3`

## string_xrefs

- `0x1400040db`: `Cannot create report file: %1`
- `0x140004270`: `After/Before:           %1%% compression`

## pseudocode

```c
__int64 __fastcall buildInfAndRpt(__int64 a1, __int64 a2)
{
  double v3; // xmm6_8
  double v5; // xmm7_8
  int v6; // esi
  __int64 v7; // rax
  const char *v8; // rdx
  __int64 v9; // rcx
  double v10; // xmm9_8
  double v11; // xmm8_8
  __int64 v12; // rax
  const char *v13; // rbp
  FILE *v14; // rsi
  char *v15; // rax
  __int64 v17; // [rsp+20h] [rbp-88h]
  __int64 v18; // [rsp+20h] [rbp-88h]
  __int64 v19; // [rsp+20h] [rbp-88h]
  time_t Time; // [rsp+B0h] [rbp+8h] BYREF

  v3 = 0.0;
  Time = 0;
  v5 = (float)((float)(*(_DWORD *)(a1 + 156) - *(_DWORD *)(a1 + 152)) / 1000.0);
  if ( v5 == 0.0 )
    v5 = DOUBLE_1_0;
  v6 = *(_DWORD *)(a1 + 124);
  time(&Time);
  v7 = VarFind(*(_QWORD *)(a1 + 16), "InfFileName", a2);
  v8 = "setup.inf";
  if ( v7 )
    v8 = *(const char **)(v7 + 8);
  if ( !(unsigned int)infGenerate(a1, v8, &Time) || !(unsigned int)infDestroy(*(void **)(a1 + 144)) )
    return 0;
  v9 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 144) = 0;
  v10 = (double)v6 / v5 * 0.0009765625;
  v12 = VarFind(v9, "RptFileName", a2);
  v13 = "setup.rpt";
  if ( v12 )
    v13 = *(const char **)(v12 + 8);
  v14 = fopen(v13, "wt");
  if ( !v14 )
  {
    ErrSet(a2, "Cannot create report file: %1", "%s", v13);
    printError(a1, a2);
    *(_DWORD *)(a2 + 512) = 0;
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 544) = 0;
    *(_QWORD *)(a2 + 552) = 0;
  }
  v15 = ctime(&Time);
  MsgSet(a1 + 484, 2048, "MakeCAB Report: %1", "%s", v15);
  if ( v14 )
    fprintf(v14, "%s\n", (const char *)(a1 + 484));
  LODWORD(v17) = *(_DWORD *)(a1 + 132);
  MsgSet(a1 + 484, 2048, "Total files:  %1", "%,13ld", v17);
  lineOut(a1, a1 + 484, 1);
  if ( v14 )
    fprintf(v14, "%s\n", (const char *)(a1 + 484));
  LODWORD(v18) = *(_DWORD *)(a1 + 124);
  MsgSet(a1 + 484, 2048, "Bytes before: %1", "%,13ld", v18);
  lineOut(a1, a1 + 484, 1);
  if ( v14 )
    fprintf(v14, "%s\n", (const char *)(a1 + 484));
  LODWORD(v19) = *(_DWORD *)(a1 + 128);
  MsgSet(a1 + 484, 2048, "Bytes after:  %1", "%,13ld", v19);
  lineOut(a1, a1 + 484, 1);
  if ( v14 )
    fprintf(v14, "%s\n", (const char *)(a1 + 484));
  if ( *(_DWORD *)(a1 + 124) )
    v3 = (float)((float)*(int *)(a1 + 128) / (float)*(int *)(a1 + 124)) * 100.0;
  MsgSet(a1 + 484, 2048, "After/Before:           %1%% compression", "%6.2f", v3);
  lineOut(a1, a1 + 484, 1);
  if ( v14 )
    fprintf(v14, "%s\n", (const char *)(a1 + 484));
  v11 = v5 - (double)(3600 * (int)(v5 / 3600.0));
  MsgSet(
    a1 + 484,
    2048,
    "Time:                %1 seconds (%2 hr %3 min %4 sec)",
    "%9.2f%2d%2d%5.2f",
    v5,
    (int)(v5 / 3600.0),
    (int)(v11 / 60.0),
    v11 - (double)(60 * (int)(v11 / 60.0)));
  lineOut(a1, a1 + 484, 1);
  if ( v14 )
    fprintf(v14, "%s\n", (const char *)(a1 + 484));
  MsgSet(a1 + 484, 2048, "Throughput:          %1 Kb/second", "%9.2f", v10);
  lineOut(a1, a1 + 484, 1);
  if ( v14 )
  {
    fprintf(v14, "%s\n", (const char *)(a1 + 484));
    fclose(v14);
  }
  return 1;
}

```

## disassembly

```asm
0x140003f68  mov     rax, rsp
0x140003f6b  mov     [rax+10h], rbx
0x140003f6f  mov     [rax+18h], rbp
0x140003f73  push    rsi
0x140003f74  push    rdi
0x140003f75  push    r13
0x140003f77  push    r14
0x140003f79  push    r15
0x140003f7b  sub     rsp, 80h
0x140003f82  movaps  xmmword ptr [rax-38h], xmm6
0x140003f86  mov     rbx, rdx
0x140003f89  movaps  xmmword ptr [rax-48h], xmm7
0x140003f8d  xorps   xmm6, xmm6
0x140003f90  movaps  xmmword ptr [rax-58h], xmm8
0x140003f95  mov     rdi, rcx
0x140003f98  movaps  xmmword ptr [rax-68h], xmm9
0x140003f9d  mov     qword ptr [rax+8], 0
0x140003fa5  mov     eax, [rcx+9Ch]
0x140003fab  sub     eax, [rcx+98h]
0x140003fb1  movd    xmm0, eax
0x140003fb5  cvtdq2ps xmm0, xmm0
0x140003fb8  divss   xmm0, cs:__real@447a0000
0x140003fc0  cvtps2pd xmm7, xmm0
0x140003fc3  ucomisd xmm7, xmm6
0x140003fc7  jp      short loc_140003FD3
0x140003fc9  jnz     short loc_140003FD3
0x140003fcb  movsd   xmm7, cs:__real@3ff0000000000000
0x140003fd3  mov     esi, [rcx+7Ch]
0x140003fd6  lea     rcx, [rsp+0A8h+Time]; Time
0x140003fde  call    cs:__imp_time
0x140003fe4  mov     rcx, [rdi+10h]
0x140003fe8  lea     rdx, aInffilename; "InfFileName"
0x140003fef  mov     r8, rbx
0x140003ff2  call    VarFind
0x140003ff7  lea     rdx, aSetupInf; "setup.inf"
0x140003ffe  test    rax, rax
0x140004001  jz      short loc_140004007
0x140004003  mov     rdx, [rax+8]
0x140004007  lea     r8, [rsp+0A8h+Time]
0x14000400f  mov     [rsp+0A8h+var_88], rbx
0x140004014  mov     rcx, rdi
0x140004017  call    infGenerate
0x14000401c  test    eax, eax
0x14000401e  jz      loc_14000435F
0x140004024  mov     rcx, [rdi+90h]; Block
0x14000402b  mov     rdx, rbx
0x14000402e  call    infDestroy
0x140004033  test    eax, eax
0x140004035  jz      loc_14000435F
0x14000403b  mov     rcx, [rdi+10h]
0x14000403f  lea     rdx, aRptfilename; "RptFileName"
0x140004046  movaps  xmm0, xmm7
0x140004049  mov     qword ptr [rdi+90h], 0
0x140004054  divsd   xmm0, cs:__real@40ac200000000000
0x14000405c  mov     r8, rbx
0x14000405f  xorps   xmm9, xmm9
0x140004063  movaps  xmm8, xmm7
0x140004067  cvttsd2si r15d, xmm0
0x14000406c  cvtsi2sd xmm9, rsi
0x140004071  imul    eax, r15d, 0E10h
0x140004078  divsd   xmm9, xmm7
0x14000407d  movd    xmm0, eax
0x140004081  mulsd   xmm9, cs:__real@3f50000000000000
0x14000408a  cvtdq2pd xmm0, xmm0
0x14000408e  subsd   xmm8, xmm0
0x140004093  movaps  xmm1, xmm8
0x140004097  divsd   xmm1, cs:__real@404e000000000000
0x14000409f  cvttsd2si r14d, xmm1
0x1400040a4  call    VarFind
0x1400040a9  lea     rbp, FileName; "setup.rpt"
0x1400040b0  test    rax, rax
0x1400040b3  jz      short loc_1400040B9
0x1400040b5  mov     rbp, [rax+8]
0x1400040b9  lea     rdx, Mode; "wt"
0x1400040c0  mov     rcx, rbp; FileName
0x1400040c3  call    cs:__imp_fopen
0x1400040c9  mov     rsi, rax
0x1400040cc  test    rax, rax
0x1400040cf  jnz     short loc_14000410B
0x1400040d1  mov     r9, rbp
0x1400040d4  lea     r8, aS_4; "%s"
0x1400040db  lea     rdx, aCannotCreateRe; "Cannot create report file: %1"
0x1400040e2  mov     rcx, rbx
0x1400040e5  call    ErrSet
0x1400040ea  mov     rdx, rbx
0x1400040ed  mov     rcx, rdi
0x1400040f0  call    printError
0x1400040f5  mov     [rbx+200h], esi
0x1400040fb  mov     [rbx], sil
0x1400040fe  mov     [rbx+220h], esi
0x140004104  mov     [rbx+228h], rsi
0x14000410b  lea     rcx, [rsp+0A8h+Time]; Time
0x140004113  lea     rbx, [rdi+1E4h]
0x14000411a  call    cs:__imp_ctime
0x140004120  mov     r13d, 800h
0x140004126  lea     r9, aS_4; "%s"
0x14000412d  lea     r8, aMakecabReport1; "MakeCAB Report: %1"
0x140004134  mov     [rsp+0A8h+var_88], rax
0x140004139  mov     edx, r13d
0x14000413c  mov     rcx, rbx
0x14000413f  call    MsgSet
0x140004144  lea     rbp, aS_2; "%s\n"
0x14000414b  test    rsi, rsi
0x14000414e  jz      short loc_14000415F
0x140004150  mov     r8, rbx
0x140004153  mov     rdx, rbp; Format
0x140004156  mov     rcx, rsi; Stream
0x140004159  call    cs:__imp_fprintf
0x14000415f  mov     eax, [rdi+84h]
0x140004165  lea     r9, a13ld; "%,13ld"
0x14000416c  lea     r8, aTotalFiles1; "Total files:  %1"
0x140004173  mov     dword ptr [rsp+0A8h+var_88], eax
0x140004177  mov     edx, r13d
0x14000417a  mov     rcx, rbx
0x14000417d  call    MsgSet
0x140004182  mov     r13d, 1
0x140004188  mov     rdx, rbx
0x14000418b  mov     r8d, r13d
0x14000418e  mov     rcx, rdi
0x140004191  call    lineOut
0x140004196  test    rsi, rsi
0x140004199  jz      short loc_1400041AA
0x14000419b  mov     r8, rbx
0x14000419e  mov     rdx, rbp; Format
0x1400041a1  mov     rcx, rsi; Stream
0x1400041a4  call    cs:__imp_fprintf
0x1400041aa  mov     eax, [rdi+7Ch]
0x1400041ad  lea     r9, a13ld; "%,13ld"
0x1400041b4  lea     r8, aBytesBefore1; "Bytes before: %1"
0x1400041bb  mov     dword ptr [rsp+0A8h+var_88], eax
0x1400041bf  mov     edx, 800h
0x1400041c4  mov     rcx, rbx
0x1400041c7  call    MsgSet
0x1400041cc  mov     r8d, r13d
0x1400041cf  mov     rdx, rbx
0x1400041d2  mov     rcx, rdi
0x1400041d5  call    lineOut
0x1400041da  test    rsi, rsi
0x1400041dd  jz      short loc_1400041EE
0x1400041df  mov     r8, rbx
0x1400041e2  mov     rdx, rbp; Format
0x1400041e5  mov     rcx, rsi; Stream
0x1400041e8  call    cs:__imp_fprintf
0x1400041ee  mov     eax, [rdi+80h]
0x1400041f4  lea     r9, a13ld; "%,13ld"
0x1400041fb  lea     r8, aBytesAfter1; "Bytes after:  %1"
0x140004202  mov     dword ptr [rsp+0A8h+var_88], eax
0x140004206  mov     edx, 800h
0x14000420b  mov     rcx, rbx
0x14000420e  call    MsgSet
0x140004213  mov     r8d, r13d
0x140004216  mov     rdx, rbx
0x140004219  mov     rcx, rdi
0x14000421c  call    lineOut
0x140004221  test    rsi, rsi
0x140004224  jz      short loc_140004235
0x140004226  mov     r8, rbx
0x140004229  mov     rdx, rbp; Format
0x14000422c  mov     rcx, rsi; Stream
0x14000422f  call    cs:__imp_fprintf
0x140004235  cmp     dword ptr [rdi+7Ch], 0
0x140004239  jbe     short loc_140004263
0x14000423b  mov     eax, [rdi+80h]
0x140004241  xorps   xmm1, xmm1
0x140004244  xorps   xmm0, xmm0
0x140004247  cvtsi2ss xmm1, rax
0x14000424c  mov     eax, [rdi+7Ch]
0x14000424f  cvtsi2ss xmm0, rax
0x140004254  divss   xmm1, xmm0
0x140004258  cvtps2pd xmm6, xmm1
0x14000425b  mulsd   xmm6, cs:__real@4059000000000000
0x140004263  lea     r9, a62f; "%6.2f"
0x14000426a  movsd   [rsp+0A8h+var_88], xmm6
0x140004270  lea     r8, aAfterBefore1Co; "After/Before:           %1%% compressio"...
0x140004277  mov     edx, 800h
0x14000427c  mov     rcx, rbx
0x14000427f  call    MsgSet
0x140004284  mov     r8d, r13d
0x140004287  mov     rdx, rbx
0x14000428a  mov     rcx, rdi
0x14000428d  call    lineOut
0x140004292  test    rsi, rsi
0x140004295  jz      short loc_1400042A6
0x140004297  mov     r8, rbx
0x14000429a  mov     rdx, rbp; Format
0x14000429d  mov     rcx, rsi; Stream
0x1400042a0  call    cs:__imp_fprintf
0x1400042a6  imul    eax, r14d, 3Ch ; '<'
0x1400042aa  lea     r9, a92f2d2d52f; "%9.2f%2d%2d%5.2f"
0x1400042b1  lea     r8, aTime1Seconds2H; "Time:                %1 seconds (%2 hr "...
0x1400042b8  mov     rcx, rbx
0x1400042bb  movd    xmm0, eax
0x1400042bf  cvtdq2pd xmm0, xmm0
0x1400042c3  subsd   xmm8, xmm0
0x1400042c8  movsd   [rsp+0A8h+var_70], xmm8
0x1400042cf  mov     [rsp+0A8h+var_78], r14d
0x1400042d4  mov     r14d, 800h
0x1400042da  mov     edx, r14d
0x1400042dd  mov     [rsp+0A8h+var_80], r15d
0x1400042e2  movsd   [rsp+0A8h+var_88], xmm7
0x1400042e8  call    MsgSet
0x1400042ed  mov     r8d, r13d
0x1400042f0  mov     rdx, rbx
0x1400042f3  mov     rcx, rdi
0x1400042f6  call    lineOut
0x1400042fb  test    rsi, rsi
0x1400042fe  jz      short loc_14000430F
0x140004300  mov     r8, rbx
0x140004303  mov     rdx, rbp; Format
0x140004306  mov     rcx, rsi; Stream
0x140004309  call    cs:__imp_fprintf
0x14000430f  lea     r9, a92f; "%9.2f"
0x140004316  movsd   [rsp+0A8h+var_88], xmm9
0x14000431d  lea     r8, aThroughput1KbS; "Throughput:          %1 Kb/second"
0x140004324  mov     edx, r14d
0x140004327  mov     rcx, rbx
0x14000432a  call    MsgSet
0x14000432f  mov     r8d, r13d
0x140004332  mov     rdx, rbx
0x140004335  mov     rcx, rdi
0x140004338  call    lineOut
0x14000433d  test    rsi, rsi
0x140004340  jz      short loc_14000435A
0x140004342  mov     r8, rbx
0x140004345  mov     rdx, rbp; Format
0x140004348  mov     rcx, rsi; Stream
0x14000434b  call    cs:__imp_fprintf
0x140004351  mov     rcx, rsi; Stream
0x140004354  call    cs:__imp_fclose
0x14000435a  mov     eax, r13d
0x14000435d  jmp     short loc_140004361
0x14000435f  xor     eax, eax
0x140004361  movaps  xmm6, [rsp+0A8h+var_38]
0x140004366  lea     r11, [rsp+0A8h+var_28]
0x14000436e  mov     rbx, [r11+38h]
0x140004372  mov     rbp, [r11+40h]
0x140004376  movaps  xmm8, xmmword ptr [r11-30h]
0x14000437b  movaps  xmm9, xmmword ptr [r11-40h]
0x140004380  movaps  xmm7, [rsp+0A8h+var_48]
0x140004385  mov     rsp, r11
0x140004388  pop     r15
0x14000438a  pop     r14
0x14000438c  pop     r13
0x14000438e  pop     rdi
0x14000438f  pop     rsi
0x140004390  retn
```
