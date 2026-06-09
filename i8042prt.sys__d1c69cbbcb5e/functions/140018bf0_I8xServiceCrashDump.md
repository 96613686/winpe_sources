# I8xServiceCrashDump

- ea: `0x140018bf0`
- end: `0x140019084`
- name: `I8xServiceCrashDump`
- size: `1172`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400198e0`

## callees

- `0x140006950`
- `0x140007b10`
- `0x14000a340`
- `0x14000a67c`
- `0x14000da60`
- `0x14000daa0`
- `0x14000de80`
- `0x140018bf0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140018d9d`
- `ntoskrnl!ExAllocatePool2` at `0x140018dfa`
- `ntoskrnl!ExAllocatePool2` at `0x140018d9d`
- `ntoskrnl!ExAllocatePool2` at `0x140018dfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019036`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001904c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019036`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001904c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018dd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018f30`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018dd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018f30`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140018f5f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018f40`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018f40`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140018e5a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140018e71`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140018e5a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140018e71`
- `ntoskrnl!RtlGetVersion` at `0x140018d5a`
- `ntoskrnl!RtlGetVersion` at `0x140018d5a`

## string_xrefs

- `0x140018ef6`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void __fastcall I8xServiceCrashDump(__int64 a1, __int64 a2)
{
  __int64 v4; // r9
  const WCHAR *v5; // rbx
  int v6; // edx
  __int64 Pool2; // r15
  int v8; // r9d
  __int64 v9; // r9
  int v10; // edx
  PWSTR Buffer; // rbx
  PVOID SystemRoutineAddress; // rax
  int v13; // ecx
  int v14; // eax
  char v15; // cl
  int v16; // edx
  __int64 v17; // [rsp+28h] [rbp-D8h]
  _DWORD v18[16]; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+80h] [rbp-80h]
  int v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+8Ch] [rbp-74h]
  int v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+94h] [rbp-6Ch]
  int v24; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+9Ch] [rbp-64h]
  _DWORD v26[4]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v27[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v28; // [rsp+C0h] [rbp-40h]
  __int16 v29; // [rsp+C4h] [rbp-3Ch]
  int v30; // [rsp+D0h] [rbp-30h] BYREF
  int v31; // [rsp+D4h] [rbp-2Ch] BYREF
  int v32; // [rsp+D8h] [rbp-28h] BYREF
  int v33; // [rsp+DCh] [rbp-24h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD VersionInformation[72]; // [rsp+100h] [rbp+0h] BYREF

  v18[0] = 50473216;
  v30 = 0;
  DestinationString = 0;
  v33 = 0;
  v31 = 0;
  v32 = 0;
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
  Feature_DefaultCrashHotKey__private_ReportDeviceUsage();
  VersionInformation[0] = 284;
  memset(&VersionInformation[1], 0, 0x118u);
  if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0 && BYTE2(VersionInformation[70]) == 1 )
  {
    v30 = 17;
    v31 = 1;
  }
  v5 = *(const WCHAR **)(a2 + 8);
  DestinationString = 0;
  Pool2 = ExAllocatePool2(256, 168, 842281016, v4);
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = 68;
LABEL_10:
      WPP_RECORDER_SF_S(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        17,
        v8,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        (__int64)v5);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  RtlInitUnicodeString(&DestinationString, 0);
  DestinationString.MaximumLength = *(_WORD *)a2 + 22;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, DestinationString.MaximumLength, 842281016, v9);
  if ( !DestinationString.Buffer )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = 69;
      goto LABEL_10;
    }
LABEL_16:
    v13 = v31;
    v14 = v30;
    v32 = v31;
    goto LABEL_18;
  }
  RtlAppendUnicodeToString(&DestinationString, v5);
  RtlAppendUnicodeToString(&DestinationString, L"\\Crashdump");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_S(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      16,
      70,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      (__int64)DestinationString.Buffer);
  *(_QWORD *)(Pool2 + 16) = L"Dump1Keys";
  *(_DWORD *)(Pool2 + 8) = 288;
  *(_DWORD *)(Pool2 + 32) = 67108868;
  *(_QWORD *)(Pool2 + 24) = &v33;
  *(_DWORD *)(Pool2 + 64) = 288;
  *(_QWORD *)(Pool2 + 40) = &v30;
  *(_DWORD *)(Pool2 + 88) = 67108868;
  *(_QWORD *)(Pool2 + 72) = L"Dump2Key";
  *(_DWORD *)(Pool2 + 48) = 4;
  *(_QWORD *)(Pool2 + 80) = &v32;
  *(_QWORD *)(Pool2 + 96) = &v31;
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
    goto LABEL_16;
  v14 = v33;
  v13 = v32;
LABEL_18:
  *(_DWORD *)(a1 + 944) = v14;
  if ( v14 )
  {
    if ( v13 == 124 )
    {
      *(_WORD *)(a1 + 952) = 21687;
    }
    else
    {
      if ( v13 > 133 )
        v15 = 0;
      else
        v15 = *((_BYTE *)v18 + v13);
      *(_BYTE *)(a1 + 952) = v15;
      *(_BYTE *)(a1 + 953) = 0;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v17) = v14;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      14,
      71,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      v17);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        14,
        72,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        *(_BYTE *)(a1 + 952),
        *(_BYTE *)(a1 + 953));
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0);
}

```

## disassembly

```asm
0x140018bf0  mov     [rsp-8+arg_10], rbx
0x140018bf5  mov     [rsp-8+arg_18], rsi
0x140018bfa  push    rbp
0x140018bfb  push    rdi
0x140018bfc  push    r12
0x140018bfe  push    r14
0x140018c00  push    r15
0x140018c02  lea     rbp, [rsp-130h]
0x140018c0a  sub     rsp, 230h
0x140018c11  mov     rax, cs:__security_cookie
0x140018c18  xor     rax, rsp
0x140018c1b  mov     [rbp+150h+var_30], rax
0x140018c22  xor     r12d, r12d
0x140018c25  mov     [rsp+250h+var_210], 3022900h
0x140018c2d  xorps   xmm0, xmm0
0x140018c30  mov     [rbp+150h+var_180], r12d
0x140018c34  movups  xmmword ptr [rbp+150h+DestinationString.Length], xmm0
0x140018c38  mov     [rbp+150h+var_174], r12d
0x140018c3c  mov     rsi, rdx
0x140018c3f  mov     [rbp+150h+var_17C], r12d
0x140018c43  mov     rdi, rcx
0x140018c46  mov     [rbp+150h+var_178], r12d
0x140018c4a  mov     [rsp+250h+var_20C], 7060504h
0x140018c52  mov     [rsp+250h+var_208], 0B0A0908h
0x140018c5a  mov     [rsp+250h+var_204], 0E7D0D0Ch
0x140018c62  mov     [rsp+250h+var_200], 1211100Fh
0x140018c6a  mov     [rsp+250h+var_1FC], 16151413h
0x140018c72  mov     [rsp+250h+var_1F8], 1A191817h
0x140018c7a  mov     [rsp+250h+var_1F4], 1E3A001Bh
0x140018c82  mov     [rsp+250h+var_1F0], 2221201Fh
0x140018c8a  mov     [rsp+250h+var_1EC], 26252423h
0x140018c92  mov     [rsp+250h+var_1E8], 1C2B2827h
0x140018c9a  mov     [rsp+250h+var_1E4], 2D2C002Ah
0x140018ca2  mov     [rsp+250h+var_1E0], 31302F2Eh
0x140018caa  mov     [rsp+250h+var_1DC], 35343332h
0x140018cb2  mov     [rsp+250h+var_1D8], 1D3673h
0x140018cba  mov     [rsp+250h+var_1D4], 0B83938h
0x140018cc2  mov     [rbp+150h+var_1D0], 9Dh
0x140018cca  mov     [rbp+150h+var_1C8], 0D2000000h
0x140018cd1  mov     [rbp+150h+var_1C4], 0CB0000D3h
0x140018cd8  mov     [rbp+150h+var_1C0], 0C800CFC7h
0x140018cdf  mov     [rbp+150h+var_1BC], 0D1C9D0h
0x140018ce6  mov     [rbp+150h+var_1B8], 4745CD00h
0x140018ced  mov     [rbp+150h+var_1B4], 0B5004F4Bh
0x140018cf4  mov     dword ptr [rbp+150h+var_1B0], 52504C48h
0x140018cfb  mov     dword ptr [rbp+150h+var_1B0+4], 514D4937h
0x140018d02  mov     dword ptr [rbp+150h+var_1B0+8], 4E4A53h
0x140018d09  mov     dword ptr [rbp+150h+var_1B0+0Ch], 1009Ch
0x140018d10  mov     dword ptr [rbp+150h+var_1A0], 3E3D3C3Bh
0x140018d17  mov     dword ptr [rbp+150h+var_1A0+4], 4241403Fh
0x140018d1e  mov     dword ptr [rbp+150h+var_1A0+8], 58574443h
0x140018d25  mov     dword ptr [rbp+150h+var_1A0+0Ch], 4600h
0x140018d2c  mov     [rbp+150h+var_190], 7B000000h
0x140018d33  mov     [rbp+150h+var_18C], 7079h
0x140018d39  call    Feature_DefaultCrashHotKey__private_ReportDeviceUsage
0x140018d3e  xor     edx, edx; Val
0x140018d40  mov     [rbp+150h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140018d47  mov     r8d, 118h; Size
0x140018d4d  lea     rcx, [rbp+150h+VersionInformation.dwMajorVersion]; void *
0x140018d51  call    memset
0x140018d56  lea     rcx, [rbp+150h+VersionInformation]; lpVersionInformation
0x140018d5a  call    cs:__imp_RtlGetVersion
0x140018d61  nop     dword ptr [rax+rax+00h]
0x140018d66  test    eax, eax
0x140018d68  js      short loc_140018D81
0x140018d6a  cmp     [rbp+150h+var_36], 1
0x140018d71  jnz     short loc_140018D81
0x140018d73  mov     [rbp+150h+var_180], 11h
0x140018d7a  mov     [rbp+150h+var_17C], 1
0x140018d81  mov     rbx, [rsi+8]
0x140018d85  mov     edx, 0A8h
0x140018d8a  xorps   xmm0, xmm0
0x140018d8d  mov     r14d, 32343038h
0x140018d93  mov     r8d, r14d
0x140018d96  movups  xmmword ptr [rbp+150h+DestinationString.Length], xmm0
0x140018d9a  lea     ecx, [rdx+58h]
0x140018d9d  call    cs:__imp_ExAllocatePool2
0x140018da4  nop     dword ptr [rax+rax+00h]
0x140018da9  mov     r15, rax
0x140018dac  test    rax, rax
0x140018daf  jnz     short loc_140018DD2
0x140018db1  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018db8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018dbf  lea     r14, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140018dc6  jz      loc_140018F73
0x140018dcc  lea     r9d, [rax+44h]
0x140018dd0  jmp     short loc_140018E2E
0x140018dd2  xor     edx, edx; SourceString
0x140018dd4  lea     rcx, [rbp+150h+DestinationString]; DestinationString
0x140018dd8  call    cs:__imp_RtlInitUnicodeString
0x140018ddf  nop     dword ptr [rax+rax+00h]
0x140018de4  movzx   eax, word ptr [rsi]
0x140018de7  mov     r8d, r14d
0x140018dea  add     ax, 16h
0x140018dee  mov     ecx, 100h
0x140018df3  movzx   edx, ax
0x140018df6  mov     [rbp+150h+DestinationString.MaximumLength], dx
0x140018dfa  call    cs:__imp_ExAllocatePool2
0x140018e01  nop     dword ptr [rax+rax+00h]
0x140018e06  mov     [rbp+150h+DestinationString.Buffer], rax
0x140018e0a  test    rax, rax
0x140018e0d  jnz     short loc_140018E53
0x140018e0f  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018e16  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018e1d  lea     r14, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140018e24  jz      loc_140018F73
0x140018e2a  lea     r9d, [rax+45h]
0x140018e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e35  mov     r8d, 11h
0x140018e3b  mov     [rsp+250h+var_228], rbx
0x140018e40  mov     [rsp+250h+var_230], r14
0x140018e45  mov     rcx, [rcx+40h]
0x140018e49  call    WPP_RECORDER_SF_S
0x140018e4e  jmp     loc_140018F73
0x140018e53  mov     rdx, rbx; Source
0x140018e56  lea     rcx, [rbp+150h+DestinationString]; Destination
0x140018e5a  call    cs:__imp_RtlAppendUnicodeToString
0x140018e61  nop     dword ptr [rax+rax+00h]
0x140018e66  lea     rdx, Source; "\\Crashdump"
0x140018e6d  lea     rcx, [rbp+150h+DestinationString]; Destination
0x140018e71  call    cs:__imp_RtlAppendUnicodeToString
0x140018e78  nop     dword ptr [rax+rax+00h]
0x140018e7d  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018e84  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018e8b  lea     r14, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140018e92  jz      short loc_140018EBC
0x140018e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e9b  mov     r9d, 46h ; 'F'
0x140018ea1  mov     rax, [rbp+150h+DestinationString.Buffer]
0x140018ea5  mov     [rsp+250h+var_228], rax
0x140018eaa  mov     [rsp+250h+var_230], r14
0x140018eaf  mov     rcx, [rcx+40h]
0x140018eb3  lea     r8d, [r9-36h]
0x140018eb7  call    WPP_RECORDER_SF_S
0x140018ebc  mov     edx, 120h
0x140018ec1  lea     rax, aDump1keys; "Dump1Keys"
0x140018ec8  mov     [r15+10h], rax
0x140018ecc  mov     ecx, 4000004h
0x140018ed1  mov     r8d, 4
0x140018ed7  mov     [r15+8], edx
0x140018edb  mov     [r15+20h], ecx
0x140018edf  lea     rax, [rbp+150h+var_174]
0x140018ee3  mov     [r15+18h], rax
0x140018ee7  xorps   xmm0, xmm0
0x140018eea  mov     [r15+40h], edx
0x140018eee  lea     rax, [rbp+150h+var_180]
0x140018ef2  mov     [r15+28h], rax
0x140018ef6  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140018efd  mov     [r15+58h], ecx
0x140018f01  lea     rax, aDump2key; "Dump2Key"
0x140018f08  mov     [r15+48h], rax
0x140018f0c  lea     rcx, [rbp+150h+SystemRoutineName]; DestinationString
0x140018f10  lea     rax, [rbp+150h+var_178]
0x140018f14  mov     [r15+30h], r8d
0x140018f18  mov     [r15+50h], rax
0x140018f1c  lea     rax, [rbp+150h+var_17C]
0x140018f20  mov     [r15+60h], rax
0x140018f24  mov     [r15+68h], r8d
0x140018f28  mov     rbx, [rbp+150h+DestinationString.Buffer]
0x140018f2c  movups  xmmword ptr [rbp+150h+SystemRoutineName.Length], xmm0
0x140018f30  call    cs:__imp_RtlInitUnicodeString
0x140018f37  nop     dword ptr [rax+rax+00h]
0x140018f3c  lea     rcx, [rbp+150h+SystemRoutineName]; SystemRoutineName
0x140018f40  call    cs:__imp_MmGetSystemRoutineAddress
0x140018f47  nop     dword ptr [rax+rax+00h]
0x140018f4c  mov     r8, r15
0x140018f4f  mov     [rsp+250h+var_230], r12
0x140018f54  test    rax, rax
0x140018f57  mov     rdx, rbx
0x140018f5a  mov     ecx, 80000000h
0x140018f5f  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140018f67  xor     r9d, r9d
0x140018f6a  call    _guard_dispatch_icall
0x140018f6f  test    eax, eax
0x140018f71  jns     short loc_140018F7E
0x140018f73  mov     ecx, [rbp+150h+var_17C]
0x140018f76  mov     eax, [rbp+150h+var_180]
0x140018f79  mov     [rbp+150h+var_178], ecx
0x140018f7c  jmp     short loc_140018F84
0x140018f7e  mov     eax, [rbp+150h+var_174]
0x140018f81  mov     ecx, [rbp+150h+var_178]
0x140018f84  mov     [rdi+3B0h], eax
0x140018f8a  mov     edx, eax
0x140018f8c  test    eax, eax
0x140018f8e  jz      short loc_140018FC1
0x140018f90  cmp     ecx, 7Ch ; '|'
0x140018f93  jnz     short loc_140018FA0
0x140018f95  mov     word ptr [rdi+3B8h], 54B7h
0x140018f9e  jmp     short loc_140018FC1
0x140018fa0  cmp     ecx, 85h
0x140018fa6  jg      short loc_140018FB1
0x140018fa8  movsxd  rax, ecx
0x140018fab  mov     cl, byte ptr [rsp+rax+250h+var_210]
0x140018faf  jmp     short loc_140018FB4
0x140018fb1  mov     cl, r12b
0x140018fb4  mov     [rdi+3B8h], cl
0x140018fba  mov     [rdi+3B9h], r12b
0x140018fc1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018fc8  jz      short loc_14001902B
0x140018fca  mov     rcx, cs:WPP_GLOBAL_Control
0x140018fd1  mov     r9d, 47h ; 'G'
0x140018fd7  mov     dword ptr [rsp+250h+var_228], edx
0x140018fdb  mov     [rsp+250h+var_230], r14
0x140018fe0  mov     rcx, [rcx+40h]
0x140018fe4  lea     ebx, [r9-39h]
0x140018fe8  mov     r8d, ebx
0x140018feb  call    WPP_RECORDER_SF_D
0x140018ff0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018ff7  jz      short loc_14001902B
0x140018ff9  movzx   ecx, byte ptr [rdi+3B8h]
0x140019000  lea     r9d, [rbx+3Ah]
0x140019004  movzx   eax, byte ptr [rdi+3B9h]
0x14001900b  mov     r8d, ebx
0x14001900e  mov     [rsp+250h+var_220], eax
0x140019012  mov     dword ptr [rsp+250h+var_228], ecx
0x140019016  mov     rcx, cs:WPP_GLOBAL_Control
0x14001901d  mov     [rsp+250h+var_230], r14
0x140019022  mov     rcx, [rcx+40h]
0x140019026  call    WPP_RECORDER_SF_dD
0x14001902b  mov     rcx, [rbp+150h+DestinationString.Buffer]; P
0x14001902f  test    rcx, rcx
0x140019032  jz      short loc_140019042
0x140019034  xor     edx, edx; Tag
0x140019036  call    cs:__imp_ExFreePoolWithTag
0x14001903d  nop     dword ptr [rax+rax+00h]
0x140019042  test    r15, r15
0x140019045  jz      short loc_140019058
0x140019047  xor     edx, edx; Tag
0x140019049  mov     rcx, r15; P
0x14001904c  call    cs:__imp_ExFreePoolWithTag
0x140019053  nop     dword ptr [rax+rax+00h]
0x140019058  mov     rcx, [rbp+150h+var_30]
0x14001905f  xor     rcx, rsp; StackCookie
0x140019062  call    __security_check_cookie
0x140019067  lea     r11, [rsp+250h+var_20]
0x14001906f  mov     rbx, [r11+40h]
0x140019073  mov     rsi, [r11+48h]
0x140019077  mov     rsp, r11
0x14001907a  pop     r15
0x14001907c  pop     r14
0x14001907e  pop     r12
0x140019080  pop     rdi
0x140019081  pop     rbp
0x140019082  retn
```
