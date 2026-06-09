# I8xServiceDebugEnable

- ea: `0x14001908c`
- end: `0x140019488`
- name: `I8xServiceDebugEnable`
- size: `1020`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400198e0`

## callees

- `0x140006950`
- `0x140007b10`
- `0x14000a67c`
- `0x14000daa0`
- `0x14001908c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400191c2`
- `ntoskrnl!ExAllocatePool2` at `0x140019220`
- `ntoskrnl!ExAllocatePool2` at `0x1400191c2`
- `ntoskrnl!ExAllocatePool2` at `0x140019220`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019453`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019469`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019453`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019469`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400191fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019356`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400191fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019356`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140019385`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140019366`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140019366`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140019280`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140019297`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140019280`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140019297`

## string_xrefs

- `0x14001931c`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void __fastcall I8xServiceDebugEnable(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  const WCHAR *v4; // rbx
  int v7; // edx
  __int64 Pool2; // r15
  int v9; // r9d
  __int64 v10; // r9
  int v11; // edx
  PWSTR Buffer; // rbx
  PVOID SystemRoutineAddress; // rax
  int v14; // eax
  char v15; // cl
  int v16; // edx
  __int64 v17; // [rsp+28h] [rbp-A1h]
  _DWORD v18[16]; // [rsp+40h] [rbp-89h]
  __int64 v19; // [rsp+80h] [rbp-49h]
  int v20; // [rsp+88h] [rbp-41h]
  int v21; // [rsp+8Ch] [rbp-3Dh]
  int v22; // [rsp+90h] [rbp-39h]
  int v23; // [rsp+94h] [rbp-35h]
  int v24; // [rsp+98h] [rbp-31h]
  int v25; // [rsp+9Ch] [rbp-2Dh]
  _DWORD v26[4]; // [rsp+A0h] [rbp-29h] BYREF
  _WORD v27[8]; // [rsp+B0h] [rbp-19h] BYREF
  int v28; // [rsp+C0h] [rbp-9h]
  __int16 v29; // [rsp+C4h] [rbp-5h]
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp+7h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+E0h] [rbp+17h] BYREF
  int v32; // [rsp+130h] [rbp+67h] BYREF
  int v33; // [rsp+138h] [rbp+6Fh] BYREF
  int v34; // [rsp+140h] [rbp+77h] BYREF
  int v35; // [rsp+148h] [rbp+7Fh] BYREF

  v4 = *(const WCHAR **)(a2 + 8);
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  v18[0] = 50473216;
  v18[1] = 117835012;
  v18[2] = 185207048;
  v18[3] = 243076364;
  v18[4] = 303108111;
  v18[5] = 370480147;
  v18[6] = 437852183;
  v18[7] = 507117595;
  v18[8] = 572596255;
  v18[9] = 639968291;
  v18[10] = 472590375;
  v18[11] = 757858346;
  v18[12] = 825241390;
  v18[13] = 892613426;
  v18[14] = 1914483;
  v18[15] = 12073272;
  v19 = 157;
  v20 = -771751936;
  v21 = -889192237;
  v22 = -939470905;
  v23 = 13748688;
  v24 = 1195756800;
  v25 = -1258270901;
  strcpy((char *)v26, "HLPR7IMQSJN");
  v26[3] = 65692;
  strcpy((char *)v27, ";<=>?@ABCDWX");
  HIBYTE(v27[6]) = 70;
  v27[7] = 0;
  v28 = 2063597568;
  v29 = 28793;
  DestinationString = 0;
  Pool2 = ExAllocatePool2(256, 168, 842281016, a4);
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 73;
LABEL_7:
      WPP_RECORDER_SF_S(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        17,
        v9,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        (__int64)v4);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  RtlInitUnicodeString(&DestinationString, 0);
  DestinationString.MaximumLength = *(_WORD *)a2 + 26;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, DestinationString.MaximumLength, 842281016, v10);
  if ( !DestinationString.Buffer )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 74;
      goto LABEL_7;
    }
LABEL_13:
    v14 = v32;
    goto LABEL_15;
  }
  RtlAppendUnicodeToString(&DestinationString, v4);
  RtlAppendUnicodeToString(&DestinationString, L"\\DebugEnable");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_S(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      16,
      75,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      (__int64)DestinationString.Buffer);
  *(_QWORD *)(Pool2 + 16) = L"Debug1Keys";
  *(_DWORD *)(Pool2 + 8) = 288;
  *(_DWORD *)(Pool2 + 32) = 67108868;
  *(_QWORD *)(Pool2 + 24) = &v33;
  *(_DWORD *)(Pool2 + 64) = 288;
  *(_QWORD *)(Pool2 + 40) = &v32;
  *(_DWORD *)(Pool2 + 88) = 67108868;
  *(_QWORD *)(Pool2 + 72) = L"Debug2Key";
  *(_DWORD *)(Pool2 + 48) = 4;
  *(_QWORD *)(Pool2 + 80) = &v34;
  *(_QWORD *)(Pool2 + 96) = &v35;
  *(_DWORD *)(Pool2 + 104) = 4;
  Buffer = DestinationString.Buffer;
  SystemRoutineName = 0;
  RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  if ( ((int (__fastcall *)(__int64, PWSTR, __int64, _QWORD, _QWORD))SystemRoutineAddress)(
         0x80000000LL,
         Buffer,
         Pool2,
         0,
         0) < 0 )
    goto LABEL_13;
  v14 = v33;
LABEL_15:
  *(_DWORD *)(a1 + 956) = v14;
  if ( v14 )
  {
    if ( v34 == 124 )
    {
      *(_WORD *)(a1 + 960) = 21687;
    }
    else
    {
      if ( v34 > 133 )
        v15 = 0;
      else
        v15 = *((_BYTE *)v18 + v34);
      *(_BYTE *)(a1 + 960) = v15;
      *(_BYTE *)(a1 + 961) = 0;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v17) = v14;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      14,
      76,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      v17);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        14,
        77,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        *(_BYTE *)(a1 + 960),
        *(_BYTE *)(a1 + 961));
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0);
}

```

## disassembly

```asm
0x14001908c  push    rbp
0x14001908e  push    rbx
0x14001908f  push    rsi
0x140019090  push    rdi
0x140019091  push    r12
0x140019093  push    r14
0x140019095  push    r15
0x140019097  lea     rbp, [rsp-27h]
0x14001909c  sub     rsp, 0F0h
0x1400190a3  mov     rbx, [rdx+8]
0x1400190a7  xor     r12d, r12d
0x1400190aa  mov     rsi, rdx
0x1400190ad  mov     [rbp+57h+arg_0], r12d
0x1400190b1  mov     edx, 0A8h
0x1400190b6  mov     [rbp+57h+arg_8], r12d
0x1400190ba  mov     rdi, rcx
0x1400190bd  mov     [rbp+57h+arg_18], r12d
0x1400190c1  xorps   xmm0, xmm0
0x1400190c4  mov     [rbp+57h+arg_10], r12d
0x1400190c8  mov     r14d, 32343038h
0x1400190ce  mov     [rsp+120h+var_E0], 3022900h
0x1400190d6  lea     ecx, [rdx+58h]
0x1400190d9  mov     [rsp+120h+var_DC], 7060504h
0x1400190e1  mov     r8d, r14d
0x1400190e4  mov     [rsp+120h+var_D8], 0B0A0908h
0x1400190ec  mov     [rbp+57h+var_D4], 0E7D0D0Ch
0x1400190f3  mov     [rbp+57h+var_D0], 1211100Fh
0x1400190fa  mov     [rbp+57h+var_CC], 16151413h
0x140019101  mov     [rbp+57h+var_C8], 1A191817h
0x140019108  mov     [rbp+57h+var_C4], 1E3A001Bh
0x14001910f  mov     [rbp+57h+var_C0], 2221201Fh
0x140019116  mov     [rbp+57h+var_BC], 26252423h
0x14001911d  mov     [rbp+57h+var_B8], 1C2B2827h
0x140019124  mov     [rbp+57h+var_B4], 2D2C002Ah
0x14001912b  mov     [rbp+57h+var_B0], 31302F2Eh
0x140019132  mov     [rbp+57h+var_AC], 35343332h
0x140019139  mov     [rbp+57h+var_A8], 1D3673h
0x140019140  mov     [rbp+57h+var_A4], 0B83938h
0x140019147  mov     [rbp+57h+var_A0], 9Dh
0x14001914f  mov     [rbp+57h+var_98], 0D2000000h
0x140019156  mov     [rbp+57h+var_94], 0CB0000D3h
0x14001915d  mov     [rbp+57h+var_90], 0C800CFC7h
0x140019164  mov     [rbp+57h+var_8C], 0D1C9D0h
0x14001916b  mov     [rbp+57h+var_88], 4745CD00h
0x140019172  mov     [rbp+57h+var_84], 0B5004F4Bh
0x140019179  mov     dword ptr [rbp+57h+var_80], 52504C48h
0x140019180  mov     dword ptr [rbp+57h+var_80+4], 514D4937h
0x140019187  mov     dword ptr [rbp+57h+var_80+8], 4E4A53h
0x14001918e  mov     dword ptr [rbp+57h+var_80+0Ch], 1009Ch
0x140019195  mov     dword ptr [rbp+57h+var_70], 3E3D3C3Bh
0x14001919c  mov     dword ptr [rbp+57h+var_70+4], 4241403Fh
0x1400191a3  mov     dword ptr [rbp+57h+var_70+8], 58574443h
0x1400191aa  mov     dword ptr [rbp+57h+var_70+0Ch], 4600h
0x1400191b1  mov     [rbp+57h+var_60], 7B000000h
0x1400191b8  mov     [rbp+57h+var_5C], 7079h
0x1400191be  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400191c2  call    cs:__imp_ExAllocatePool2
0x1400191c9  nop     dword ptr [rax+rax+00h]
0x1400191ce  mov     r15, rax
0x1400191d1  test    rax, rax
0x1400191d4  jnz     short loc_1400191F8
0x1400191d6  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400191dd  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400191e4  lea     r14, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x1400191eb  jz      loc_140019399
0x1400191f1  lea     r9d, [r12+49h]
0x1400191f6  jmp     short loc_140019254
0x1400191f8  xor     edx, edx; SourceString
0x1400191fa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400191fe  call    cs:__imp_RtlInitUnicodeString
0x140019205  nop     dword ptr [rax+rax+00h]
0x14001920a  movzx   eax, word ptr [rsi]
0x14001920d  mov     r8d, r14d
0x140019210  add     ax, 1Ah
0x140019214  mov     ecx, 100h
0x140019219  movzx   edx, ax
0x14001921c  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x140019220  call    cs:__imp_ExAllocatePool2
0x140019227  nop     dword ptr [rax+rax+00h]
0x14001922c  mov     [rbp+57h+DestinationString.Buffer], rax
0x140019230  test    rax, rax
0x140019233  jnz     short loc_140019279
0x140019235  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001923c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140019243  lea     r14, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001924a  jz      loc_140019399
0x140019250  lea     r9d, [rax+4Ah]
0x140019254  mov     rcx, cs:WPP_GLOBAL_Control
0x14001925b  mov     r8d, 11h
0x140019261  mov     [rsp+120h+var_F8], rbx
0x140019266  mov     [rsp+120h+var_100], r14
0x14001926b  mov     rcx, [rcx+40h]
0x14001926f  call    WPP_RECORDER_SF_S
0x140019274  jmp     loc_140019399
0x140019279  mov     rdx, rbx; Source
0x14001927c  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140019280  call    cs:__imp_RtlAppendUnicodeToString
0x140019287  nop     dword ptr [rax+rax+00h]
0x14001928c  lea     rdx, aDebugenable; "\\DebugEnable"
0x140019293  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140019297  call    cs:__imp_RtlAppendUnicodeToString
0x14001929e  nop     dword ptr [rax+rax+00h]
0x1400192a3  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400192aa  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400192b1  lea     r14, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x1400192b8  jz      short loc_1400192E2
0x1400192ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400192c1  mov     r9d, 4Bh ; 'K'
0x1400192c7  mov     rax, [rbp+57h+DestinationString.Buffer]
0x1400192cb  mov     [rsp+120h+var_F8], rax
0x1400192d0  mov     [rsp+120h+var_100], r14
0x1400192d5  mov     rcx, [rcx+40h]
0x1400192d9  lea     r8d, [r9-3Bh]
0x1400192dd  call    WPP_RECORDER_SF_S
0x1400192e2  mov     edx, 120h
0x1400192e7  lea     rax, aDebug1keys; "Debug1Keys"
0x1400192ee  mov     [r15+10h], rax
0x1400192f2  mov     ecx, 4000004h
0x1400192f7  mov     r8d, 4
0x1400192fd  mov     [r15+8], edx
0x140019301  mov     [r15+20h], ecx
0x140019305  lea     rax, [rbp+57h+arg_8]
0x140019309  mov     [r15+18h], rax
0x14001930d  xorps   xmm0, xmm0
0x140019310  mov     [r15+40h], edx
0x140019314  lea     rax, [rbp+57h+arg_0]
0x140019318  mov     [r15+28h], rax
0x14001931c  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140019323  mov     [r15+58h], ecx
0x140019327  lea     rax, aDebug2key; "Debug2Key"
0x14001932e  mov     [r15+48h], rax
0x140019332  lea     rcx, [rbp+57h+SystemRoutineName]; DestinationString
0x140019336  lea     rax, [rbp+57h+arg_10]
0x14001933a  mov     [r15+30h], r8d
0x14001933e  mov     [r15+50h], rax
0x140019342  lea     rax, [rbp+57h+arg_18]
0x140019346  mov     [r15+60h], rax
0x14001934a  mov     [r15+68h], r8d
0x14001934e  mov     rbx, [rbp+57h+DestinationString.Buffer]
0x140019352  movups  xmmword ptr [rbp+57h+SystemRoutineName.Length], xmm0
0x140019356  call    cs:__imp_RtlInitUnicodeString
0x14001935d  nop     dword ptr [rax+rax+00h]
0x140019362  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x140019366  call    cs:__imp_MmGetSystemRoutineAddress
0x14001936d  nop     dword ptr [rax+rax+00h]
0x140019372  mov     r8, r15
0x140019375  mov     [rsp+120h+var_100], r12
0x14001937a  test    rax, rax
0x14001937d  mov     rdx, rbx
0x140019380  mov     ecx, 80000000h
0x140019385  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14001938d  xor     r9d, r9d
0x140019390  call    _guard_dispatch_icall
0x140019395  test    eax, eax
0x140019397  jns     short loc_14001939E
0x140019399  mov     eax, [rbp+57h+arg_0]
0x14001939c  jmp     short loc_1400193A1
0x14001939e  mov     eax, [rbp+57h+arg_8]
0x1400193a1  mov     [rdi+3BCh], eax
0x1400193a7  mov     edx, eax
0x1400193a9  test    eax, eax
0x1400193ab  jz      short loc_1400193DE
0x1400193ad  movsxd  rax, [rbp+57h+arg_10]
0x1400193b1  cmp     eax, 7Ch ; '|'
0x1400193b4  jnz     short loc_1400193C1
0x1400193b6  mov     word ptr [rdi+3C0h], 54B7h
0x1400193bf  jmp     short loc_1400193DE
0x1400193c1  cmp     eax, 85h
0x1400193c6  jg      short loc_1400193CE
0x1400193c8  mov     cl, byte ptr [rsp+rax+120h+var_E0]
0x1400193cc  jmp     short loc_1400193D1
0x1400193ce  mov     cl, r12b
0x1400193d1  mov     [rdi+3C0h], cl
0x1400193d7  mov     [rdi+3C1h], r12b
0x1400193de  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400193e5  jz      short loc_140019448
0x1400193e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400193ee  mov     r9d, 4Ch ; 'L'
0x1400193f4  mov     dword ptr [rsp+120h+var_F8], edx
0x1400193f8  mov     [rsp+120h+var_100], r14
0x1400193fd  mov     rcx, [rcx+40h]
0x140019401  lea     ebx, [r9-3Eh]
0x140019405  mov     r8d, ebx
0x140019408  call    WPP_RECORDER_SF_D
0x14001940d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140019414  jz      short loc_140019448
0x140019416  movzx   ecx, byte ptr [rdi+3C0h]
0x14001941d  lea     r9d, [rbx+3Fh]
0x140019421  movzx   eax, byte ptr [rdi+3C1h]
0x140019428  mov     r8d, ebx
0x14001942b  mov     [rsp+120h+var_F0], eax
0x14001942f  mov     dword ptr [rsp+120h+var_F8], ecx
0x140019433  mov     rcx, cs:WPP_GLOBAL_Control
0x14001943a  mov     [rsp+120h+var_100], r14
0x14001943f  mov     rcx, [rcx+40h]
0x140019443  call    WPP_RECORDER_SF_dD
0x140019448  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x14001944c  test    rcx, rcx
0x14001944f  jz      short loc_14001945F
0x140019451  xor     edx, edx; Tag
0x140019453  call    cs:__imp_ExFreePoolWithTag
0x14001945a  nop     dword ptr [rax+rax+00h]
0x14001945f  test    r15, r15
0x140019462  jz      short loc_140019475
0x140019464  xor     edx, edx; Tag
0x140019466  mov     rcx, r15; P
0x140019469  call    cs:__imp_ExFreePoolWithTag
0x140019470  nop     dword ptr [rax+rax+00h]
0x140019475  add     rsp, 0F0h
0x14001947c  pop     r15
0x14001947e  pop     r14
0x140019480  pop     r12
0x140019482  pop     rdi
0x140019483  pop     rsi
0x140019484  pop     rbx
0x140019485  pop     rbp
0x140019486  retn
```
