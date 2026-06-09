# PopCheckShutdownMarker

- ea: `0x140c762f0`
- end: `0x140c769d2`
- name: `PopCheckShutdownMarker`
- size: `1762`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140c2464c`

## callees

- `0x14025be90`
- `0x1404c9eec`
- `0x1404f72f0`
- `0x1406dc8c0`
- `0x1406ddaa0`
- `0x1406e01a0`
- `0x1406e1000`
- `0x140724374`
- `0x14078b0e4`
- `0x1407bdb20`
- `0x1407bdbd0`
- `0x140a3b1d0`
- `0x140ac8ba8`
- `0x140adce34`
- `0x140c762f0`
- `0x140c769d8`
- `0x140c779e8`
- `0x140c785cc`

## string_xrefs

- `0x140c76818`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`
- `0x140c76843`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`
- `0x140c76865`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\LastCrashdump`

## pseudocode

```c
char __fastcall PopCheckShutdownMarker(__int64 a1)
{
  __int64 v1; // rax
  char v3; // dl
  int SystemBootStatus; // ebx
  __int64 i; // rdx
  unsigned int ULongFromUser; // eax
  __int64 v7; // r9
  __int64 v8; // r8
  char v9; // cl
  char result; // al
  char v11; // bl
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned __int8 v15; // [rsp+40h] [rbp-C0h] BYREF
  char v16; // [rsp+41h] [rbp-BFh] BYREF
  bool v17; // [rsp+42h] [rbp-BEh] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  __int128 v27; // [rsp+70h] [rbp-90h] BYREF
  char v28[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  int *v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  int *v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  __int128 *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  int *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  int *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  int *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]
  int *v43; // [rsp+110h] [rbp+10h]
  __int64 v44; // [rsp+118h] [rbp+18h]
  char *v45; // [rsp+120h] [rbp+20h]
  __int64 v46; // [rsp+128h] [rbp+28h]
  bool *v47; // [rsp+130h] [rbp+30h]
  __int64 v48; // [rsp+138h] [rbp+38h]
  _DWORD v49[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 *v50; // [rsp+148h] [rbp+48h]
  int v51; // [rsp+150h] [rbp+50h]
  int v52; // [rsp+158h] [rbp+58h]
  __int128 *v53; // [rsp+160h] [rbp+60h]
  int v54; // [rsp+168h] [rbp+68h]
  int v55; // [rsp+170h] [rbp+70h]
  __int128 *v56; // [rsp+178h] [rbp+78h]
  int v57; // [rsp+180h] [rbp+80h]
  int v58; // [rsp+188h] [rbp+88h]
  int *v59; // [rsp+190h] [rbp+90h]
  int v60; // [rsp+198h] [rbp+98h]

  v1 = *(_QWORD *)(a1 + 240);
  v15 = 0;
  v18 = 0;
  v26 = 0;
  v19 = 0;
  v27 = 0;
  v3 = *(_BYTE *)(v1 + 132);
  v49[0] = 14;
  v50 = &PopBsdPhysicalPowerButtonInfo;
  PopDirtyTransitionDiagInfo = v3 & 1;
  v53 = &PopBsdPowerTransition;
  v56 = &PopBsdPowerTransitionExtension;
  v59 = &dword_140E4D6EC;
  v51 = 64;
  v52 = 7;
  v54 = 32;
  v55 = 16;
  v57 = 32;
  v58 = 11;
  v60 = 4;
  RtlCheckSystemBootStatusIntegrity(&byte_140E4D6E1);
  SystemBootStatus = RtlGetSystemBootStatusEx(v49, 4, &v27);
  if ( SystemBootStatus < 0 )
  {
    for ( i = 0; i != 4; ++i )
    {
      if ( !*(_DWORD *)&v28[4 * i - 16] )
        dword_140E4D6E4 |= 1 << LOBYTE(v49[6 * i]);
    }
    ULongFromUser = RtlReadULongFromUser((unsigned int *)0x7FFE02C4);
    LOBYTE(v7) = byte_140E4D6E1;
    PopDiagTraceInvalidBootStat(ULongFromUser, (unsigned int)dword_140E4D6E4, (unsigned int)SystemBootStatus, v7);
  }
  PopBsdPhysicalPowerButtonInfoAtBoot = PopBsdPhysicalPowerButtonInfo;
  xmmword_140E4D530 = xmmword_140E4D630;
  xmmword_140E4D540 = xmmword_140E4D640;
  xmmword_140E4D550 = xmmword_140E4D650;
  if ( _mm_srli_si128((__m128i)PopBsdPhysicalPowerButtonInfo, 8).m128i_u32[0]
    && (unsigned int)dword_140E0B718 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_140E0B718, 0x200000000000LL) )
  {
    v20 = WORD6(PopBsdPhysicalPowerButtonInfoAtBoot);
    v31 = &v20;
    v33 = &v21;
    v35 = &xmmword_140E4D540;
    v22 = WORD6(xmmword_140E4D540);
    v37 = &v22;
    v39 = &v23;
    v24 = HIWORD(xmmword_140E4D540);
    v41 = &v24;
    v25 = BYTE14(PopBsdPhysicalPowerButtonInfoAtBoot);
    v43 = &v25;
    v16 = HIBYTE(PopBsdPhysicalPowerButtonInfoAtBoot) & 1;
    v29 = v8;
    v45 = &v16;
    v21 = DWORD2(PopBsdPhysicalPowerButtonInfoAtBoot);
    v47 = &v17;
    v23 = DWORD2(PopBsdPhysicalPowerButtonInfoAtBoot);
    v17 = (HIBYTE(PopBsdPhysicalPowerButtonInfoAtBoot) & 2) != 0;
    v30 = 8;
    v32 = 4;
    v34 = 4;
    v36 = 8;
    v38 = 4;
    v40 = 4;
    v42 = 4;
    v44 = 4;
    v46 = 1;
    v48 = 1;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140E0B718, &word_1400493B6, 0, 0, 12, v28);
  }
  PopBsdPowerTransitionAtBoot = PopBsdPowerTransition;
  xmmword_140E4D590 = xmmword_140E4D690;
  PopBsdPowerTransitionOnDisk = PopBsdPowerTransition;
  xmmword_140E4D610 = xmmword_140E4D690;
  PopBsdPhysicalPowerButtonInfoOnDisk = PopBsdPhysicalPowerButtonInfo;
  xmmword_140E4D5B0 = xmmword_140E4D630;
  xmmword_140E4D5C0 = xmmword_140E4D640;
  xmmword_140E4D5D0 = xmmword_140E4D650;
  PopBsdPowerTransitionExtensionAtBoot = PopBsdPowerTransitionExtension;
  xmmword_140E4D570 = xmmword_140E4D670;
  PopBsdPowerTransitionExtensionOnDisk = PopBsdPowerTransitionExtension;
  xmmword_140E4D5F0 = xmmword_140E4D670;
  if ( (qword_140EED038 & 4) != 0 )
    BYTE8(PopBsdPowerTransitionAtBoot) &= ~1u;
  if ( (PopSimulate & 0x200) != 0 )
    BYTE8(PopBsdPowerTransitionAtBoot) |= 1u;
  v9 = BYTE14(PopBsdPowerTransitionAtBoot) & 0xDF;
  BYTE14(PopBsdPowerTransitionAtBoot) &= ~0x20u;
  if ( DWORD2(PopBsdPhysicalPowerButtonInfoAtBoot) && (HIBYTE(PopBsdPhysicalPowerButtonInfoAtBoot) & 4) != 0 )
  {
    BYTE14(PopBsdPowerTransitionAtBoot) = v9 | 0x20;
    *(_QWORD *)&PopBsdPowerTransitionAtBoot = PopBsdPhysicalPowerButtonInfoAtBoot;
  }
  PopAutoChkCausedReboot = (BYTE14(PopBsdPowerTransition) & 0x10) != 0;
  v26 = WNF_PO_PREVIOUS_SHUTDOWN_STATE;
  v18 = BYTE8(PopBsdPowerTransitionAtBoot) & 1;
  result = ZwUpdateWnfStateData(&v26, &v18, 4, 0, 0, 0, 0);
  if ( (PopSimulate & 0x400) != 0 )
  {
    WORD6(PopBsdPowerTransitionAtBoot) = 1;
    result = BYTE8(PopBsdPowerTransitionAtBoot) & 0xF | 0x50;
    BYTE8(PopBsdPowerTransitionAtBoot) = result;
  }
  if ( (PopSimulate & 0x20000000) != 0 )
  {
    BYTE8(PopBsdPowerTransitionAtBoot) |= 2u;
    *((_QWORD *)&xmmword_140E4D570 + 1) = 1;
  }
  if ( (BYTE8(PopBsdPowerTransitionAtBoot) & 1) != 0 )
  {
    v19 = 1;
    if ( (int)ExGetFirmwareEnvironmentVariable(
                (unsigned int)L"*,",
                (unsigned int)SYSTEM_SLEEP_ETW_CHECKPOINT_GUID,
                (unsigned int)&v15,
                (unsigned int)&v19,
                0) < 0 )
    {
      v11 = BYTE2(PopBsdPowerTransitionExtensionAtBoot);
      BYTE1(PopBsdPowerTransitionExtensionAtBoot) = BYTE1(PopBsdPowerTransitionExtensionAtBoot) & 0xF3 | 8;
      PopRecordSleepCheckpointSource(2);
    }
    else
    {
      v11 = v15;
      BYTE2(PopBsdPowerTransitionExtensionAtBoot) = v15;
      BYTE1(PopBsdPowerTransitionExtensionAtBoot) = BYTE1(PopBsdPowerTransitionExtensionAtBoot) & 0xF3 | 4;
      PopRecordSleepCheckpoint(v15);
      PopRecordSleepCheckpointSource(1);
      LOBYTE(v12) = 1;
      PopClearSystemSleepCheckpoint(v12);
    }
    v13 = *(_QWORD *)(a1 + 240);
    if ( v13 )
    {
      v14 = *(_QWORD *)(v13 + 280);
      if ( v14 )
      {
        dword_140E4D6F0 = *(_DWORD *)(v14 + 56);
        qword_140E4D6F8 = *(_QWORD *)(v14 + 64);
        qword_140E4D700 = *(_QWORD *)(v14 + 72);
        qword_140E4D708 = *(_QWORD *)(v14 + 80);
        qword_140E4D710 = *(_QWORD *)(v14 + 88);
      }
    }
    dword_140E4D768 = 0;
    PopReadRegKeyValue(
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl",
      L"CrashDumpEnabled",
      4,
      4,
      &dword_140E4D768);
    dword_140E4D76C = 0;
    PopReadRegKeyValue(
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl",
      L"FilterPages",
      4,
      4,
      &dword_140E4D76C);
    if ( (int)PopReadRegKeyValue(
                L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\LastCrashdump",
                L"Info",
                48,
                0,
                &dword_140E4D770) >= 0
      && !dword_140E4D6F0
      && dword_140E4D778 )
    {
      dword_140E4D6F0 = dword_140E4D778;
      qword_140E4D6F8 = qword_140E4D780;
      dword_140E4D718 = 1;
    }
    dword_140E4D6E8 = RtlReadULongFromUser((unsigned int *)0x7FFE02C4);
    byte_140E4D730 = v11;
    qword_140E4D738 = (__int64)&PopBsdPhysicalPowerButtonInfoAtBoot;
    qword_140E4D720 = (__int64)&PopBsdPowerTransitionAtBoot;
    qword_140E4D728 = (__int64)&PopBsdPowerTransitionExtensionAtBoot;
    dword_140E4D740 = ExBootAppErrorDiagCode;
    dword_140E4D744 = ExBootAppFailureStatus;
    ZwQuerySystemInformation(90, qword_140E4D748, 32, 0);
    dword_140E4D7A8 = 7;
    qword_140E4D7B0 = (__int64)&PopFirmwareResetReason;
    if ( (int)ZwQuerySystemInformationEx(72, &dword_140E4D7A8, 4, &dword_140E4D7A8, 8, 0) >= 0 )
    {
      dword_140E4D7A0 = dword_140E4D7AC;
      if ( dword_140E4D7AC )
      {
        dword_140E4D7A8 = 8;
        if ( (int)ZwQuerySystemInformationEx(72, &dword_140E4D7A8, 4, &dword_140E4D7A8, 8, 0) >= 0 )
          dword_140E4D7A4 = dword_140E4D7AC;
      }
    }
    PopReadWheaBootErrorCount(&dword_140E4D7B8);
    return PopDiagTraceDirtyTransition(&PopDirtyTransitionDiagInfo);
  }
  return result;
}

```

## disassembly

```asm
0x140c762f0  push    rbp
0x140c762f2  push    rbx
0x140c762f3  push    rsi
0x140c762f4  push    rdi
0x140c762f5  push    r12
0x140c762f7  push    r14
0x140c762f9  push    r15
0x140c762fb  lea     rbp, [rsp-0B0h]
0x140c76303  sub     rsp, 1B0h
0x140c7630a  mov     rax, cs:__security_cookie
0x140c76311  xor     rax, rsp
0x140c76314  mov     [rbp+0E0h+var_40], rax
0x140c7631b  mov     rax, [rcx+0F0h]
0x140c76322  xor     esi, esi
0x140c76324  xorps   xmm0, xmm0
0x140c76327  mov     [rsp+1E0h+var_1A0], sil
0x140c7632c  mov     [rsp+1E0h+var_19C], esi
0x140c76330  mov     rdi, rcx
0x140c76333  mov     [rsp+1E0h+var_178], rsi
0x140c76338  lea     rcx, byte_140E4D6E1
0x140c7633f  mov     [rsp+1E0h+var_198], esi
0x140c76343  lea     r14d, [rsi+1]
0x140c76347  movups  [rsp+1E0h+var_170], xmm0
0x140c7634c  mov     dl, [rax+84h]
0x140c76352  lea     r15d, [rsi+4]
0x140c76356  lea     rax, PopBsdPhysicalPowerButtonInfo
0x140c7635d  mov     [rbp+0E0h+var_A0], 0Eh
0x140c76364  mov     [rbp+0E0h+var_98], rax
0x140c76368  and     dl, r14b
0x140c7636b  lea     rax, PopBsdPowerTransition
0x140c76372  mov     cs:PopDirtyTransitionDiagInfo, dl
0x140c76378  mov     [rbp+0E0h+var_80], rax
0x140c7637c  lea     rax, PopBsdPowerTransitionExtension
0x140c76383  mov     [rbp+0E0h+var_68], rax
0x140c76387  lea     rax, dword_140E4D6EC
0x140c7638e  mov     [rbp+0E0h+var_50], rax
0x140c76395  mov     [rbp+0E0h+var_90], 40h ; '@'
0x140c7639c  mov     [rbp+0E0h+var_88], 7
0x140c763a3  mov     [rbp+0E0h+var_78], 20h ; ' '
0x140c763aa  mov     [rbp+0E0h+var_70], 10h
0x140c763b1  mov     [rbp+0E0h+var_60], 20h ; ' '
0x140c763bb  mov     [rbp+0E0h+var_58], 0Bh
0x140c763c5  mov     [rbp+0E0h+var_48], r15d
0x140c763cc  call    RtlCheckSystemBootStatusIntegrity
0x140c763d1  lea     r8, [rsp+1E0h+var_170]
0x140c763d6  mov     edx, r15d
0x140c763d9  lea     rcx, [rbp+0E0h+var_A0]
0x140c763dd  call    RtlGetSystemBootStatusEx
0x140c763e2  mov     ebx, eax
0x140c763e4  test    eax, eax
0x140c763e6  jns     short loc_140C76430
0x140c763e8  mov     edx, esi
0x140c763ea  cmp     dword ptr [rsp+rdx*4+1E0h+var_170], esi
0x140c763ee  jnz     short loc_140C76407
0x140c763f0  mov     ecx, cs:dword_140E4D6E4
0x140c763f6  lea     rax, [rdx+rdx*2]
0x140c763fa  mov     eax, [rbp+rax*8+0E0h+var_A0]
0x140c763fe  bts     ecx, eax
0x140c76401  mov     cs:dword_140E4D6E4, ecx
0x140c76407  add     rdx, r14
0x140c7640a  cmp     rdx, r15
0x140c7640d  jnz     short loc_140C763EA
0x140c7640f  mov     ecx, 7FFE02C4h
0x140c76414  call    RtlReadULongFromUser
0x140c76419  mov     r9b, cs:byte_140E4D6E1
0x140c76420  mov     r8d, ebx
0x140c76423  mov     edx, cs:dword_140E4D6E4
0x140c76429  mov     ecx, eax
0x140c7642b  call    PopDiagTraceInvalidBootStat
0x140c76430  movaps  xmm2, cs:PopBsdPhysicalPowerButtonInfo
0x140c76437  lea     r8, PopBsdPhysicalPowerButtonInfoAtBoot
0x140c7643e  movaps  xmm0, cs:xmmword_140E4D630
0x140c76445  mov     r12d, 8
0x140c7644b  movaps  xmm1, cs:xmmword_140E4D640
0x140c76452  movaps  cs:PopBsdPhysicalPowerButtonInfoAtBoot, xmm2
0x140c76459  psrldq  xmm2, 8
0x140c7645e  movq    rax, xmm2
0x140c76463  movaps  cs:xmmword_140E4D530, xmm0
0x140c7646a  movaps  xmm0, cs:xmmword_140E4D650
0x140c76471  movaps  cs:xmmword_140E4D540, xmm1
0x140c76478  movaps  cs:xmmword_140E4D550, xmm0
0x140c7647f  test    eax, eax
0x140c76481  jz      loc_140C765AF
0x140c76487  mov     eax, cs:dword_140E0B718
0x140c7648d  cmp     eax, 5
0x140c76490  jbe     loc_140C765AF
0x140c76496  mov     rdx, 200000000000h
0x140c764a0  lea     rcx, dword_140E0B718
0x140c764a7  call    _tlgKeywordOn
0x140c764ac  test    al, al
0x140c764ae  jz      loc_140C765AF
0x140c764b4  mov     dl, byte ptr cs:PopBsdPhysicalPowerButtonInfoAtBoot+0Fh
0x140c764ba  xor     r9d, r9d
0x140c764bd  movzx   eax, word ptr cs:PopBsdPhysicalPowerButtonInfoAtBoot+0Ch
0x140c764c4  mov     ecx, dword ptr cs:PopBsdPhysicalPowerButtonInfoAtBoot+8
0x140c764ca  mov     [rsp+1E0h+var_194], eax
0x140c764ce  lea     rax, [rsp+1E0h+var_194]
0x140c764d3  mov     [rbp+0E0h+var_130], rax
0x140c764d7  lea     rax, [rsp+1E0h+var_190]
0x140c764dc  mov     [rbp+0E0h+var_120], rax
0x140c764e0  lea     rax, xmmword_140E4D540
0x140c764e7  mov     [rbp+0E0h+var_110], rax
0x140c764eb  movzx   eax, word ptr cs:xmmword_140E4D540+0Ch
0x140c764f2  mov     [rsp+1E0h+var_18C], eax
0x140c764f6  lea     rax, [rsp+1E0h+var_18C]
0x140c764fb  mov     [rbp+0E0h+var_100], rax
0x140c764ff  lea     rax, [rsp+1E0h+var_188]
0x140c76504  mov     [rbp+0E0h+var_F0], rax
0x140c76508  movzx   eax, word ptr cs:xmmword_140E4D540+0Eh
0x140c7650f  mov     [rsp+1E0h+var_184], eax
0x140c76513  lea     rax, [rsp+1E0h+var_184]
0x140c76518  mov     [rbp+0E0h+var_E0], rax
0x140c7651c  movzx   eax, byte ptr cs:PopBsdPhysicalPowerButtonInfoAtBoot+0Eh
0x140c76523  mov     [rsp+1E0h+var_180], eax
0x140c76527  lea     rax, [rsp+1E0h+var_180]
0x140c7652c  mov     [rbp+0E0h+var_D0], rax
0x140c76530  mov     al, dl
0x140c76532  and     al, r14b
0x140c76535  shr     dl, 1
0x140c76537  mov     [rsp+1E0h+var_19F], al
0x140c7653b  and     dl, r14b
0x140c7653e  lea     rax, [rsp+1E0h+var_19F]
0x140c76543  mov     [rbp+0E0h+var_140], r8
0x140c76547  mov     [rbp+0E0h+var_C0], rax
0x140c7654b  xor     r8d, r8d
0x140c7654e  lea     rax, [rsp+1E0h+var_19E]
0x140c76553  mov     [rsp+1E0h+var_190], ecx
0x140c76557  mov     [rbp+0E0h+var_B0], rax
0x140c7655b  lea     rax, [rbp+0E0h+var_160]
0x140c7655f  mov     [rsp+1E0h+var_188], ecx
0x140c76563  lea     rcx, dword_140E0B718
0x140c7656a  mov     [rsp+1E0h+var_19E], dl
0x140c7656e  lea     rdx, word_1400493B6
0x140c76575  mov     [rsp+1E0h+var_1B8], rax
0x140c7657a  mov     dword ptr [rsp+1E0h+var_1C0], 0Ch
0x140c76582  mov     [rbp+0E0h+var_138], r12
0x140c76586  mov     [rbp+0E0h+var_128], r15
0x140c7658a  mov     [rbp+0E0h+var_118], r15
0x140c7658e  mov     [rbp+0E0h+var_108], r12
0x140c76592  mov     [rbp+0E0h+var_F8], r15
0x140c76596  mov     [rbp+0E0h+var_E8], r15
0x140c7659a  mov     [rbp+0E0h+var_D8], r15
0x140c7659e  mov     [rbp+0E0h+var_C8], r15
0x140c765a2  mov     [rbp+0E0h+var_B8], r14
0x140c765a6  mov     [rbp+0E0h+var_A8], r14
0x140c765aa  call    _tlgWriteTransfer_EtwWriteTransfer
0x140c765af  test    byte ptr cs:qword_140EED038, r15b
0x140c765b6  movups  xmm1, cs:PopBsdPowerTransition
0x140c765bd  movups  xmm0, cs:xmmword_140E4D690
0x140c765c4  movups  xmm3, cs:PopBsdPowerTransitionExtension
0x140c765cb  movups  xmm2, cs:xmmword_140E4D670
0x140c765d2  movups  cs:PopBsdPowerTransitionAtBoot, xmm1
0x140c765d9  movups  cs:xmmword_140E4D590, xmm0
0x140c765e0  movups  cs:PopBsdPowerTransitionOnDisk, xmm1
0x140c765e7  movaps  xmm1, cs:xmmword_140E4D630
0x140c765ee  movups  cs:xmmword_140E4D610, xmm0
0x140c765f5  movaps  xmm0, cs:PopBsdPhysicalPowerButtonInfo
0x140c765fc  movaps  cs:PopBsdPhysicalPowerButtonInfoOnDisk, xmm0
0x140c76603  movaps  xmm0, cs:xmmword_140E4D640
0x140c7660a  movaps  cs:xmmword_140E4D5B0, xmm1
0x140c76611  movaps  xmm1, cs:xmmword_140E4D650
0x140c76618  movaps  cs:xmmword_140E4D5C0, xmm0
0x140c7661f  movaps  cs:xmmword_140E4D5D0, xmm1
0x140c76626  movups  cs:PopBsdPowerTransitionExtensionAtBoot, xmm3
0x140c7662d  movups  cs:xmmword_140E4D570, xmm2
0x140c76634  movups  cs:PopBsdPowerTransitionExtensionOnDisk, xmm3
0x140c7663b  movups  cs:xmmword_140E4D5F0, xmm2
0x140c76642  jz      short loc_140C7664B
0x140c76644  and     byte ptr cs:PopBsdPowerTransitionAtBoot+8, 0FEh
0x140c7664b  test    cs:PopSimulate, 200h
0x140c76655  jz      short loc_140C7665E
0x140c76657  or      byte ptr cs:PopBsdPowerTransitionAtBoot+8, r14b
0x140c7665e  mov     cl, byte ptr cs:PopBsdPowerTransitionAtBoot+0Eh
0x140c76664  and     cl, 0DFh
0x140c76667  cmp     dword ptr cs:PopBsdPhysicalPowerButtonInfoAtBoot+8, esi
0x140c7666d  mov     byte ptr cs:PopBsdPowerTransitionAtBoot+0Eh, cl
0x140c76673  jz      short loc_140C76695
0x140c76675  test    byte ptr cs:PopBsdPhysicalPowerButtonInfoAtBoot+0Fh, r15b
0x140c7667c  jz      short loc_140C76695
0x140c7667e  mov     rax, qword ptr cs:PopBsdPhysicalPowerButtonInfoAtBoot
0x140c76685  or      cl, 20h
0x140c76688  mov     byte ptr cs:PopBsdPowerTransitionAtBoot+0Eh, cl
0x140c7668e  mov     qword ptr cs:PopBsdPowerTransitionAtBoot, rax
0x140c76695  mov     al, byte ptr cs:PopBsdPowerTransition+0Eh
0x140c7669b  lea     rdx, [rsp+1E0h+var_19C]
0x140c766a0  shr     al, 4
0x140c766a3  lea     rcx, [rsp+1E0h+var_178]
0x140c766a8  and     al, r14b
0x140c766ab  mov     [rsp+1E0h+var_1B0], esi
0x140c766af  mov     cs:PopAutoChkCausedReboot, al
0x140c766b5  xor     r9d, r9d
0x140c766b8  mov     rax, cs:WNF_PO_PREVIOUS_SHUTDOWN_STATE
0x140c766bf  mov     r8d, r15d
0x140c766c2  mov     [rsp+1E0h+var_178], rax
0x140c766c7  movzx   eax, byte ptr cs:PopBsdPowerTransitionAtBoot+8
0x140c766ce  and     eax, r14d
0x140c766d1  mov     dword ptr [rsp+1E0h+var_1B8], esi
0x140c766d5  mov     [rsp+1E0h+var_19C], eax
0x140c766d9  mov     [rsp+1E0h+var_1C0], rsi
0x140c766de  call    ZwUpdateWnfStateData
0x140c766e3  mov     ecx, cs:PopSimulate
0x140c766e9  bt      ecx, 0Ah
0x140c766ed  jnb     short loc_140C76707
0x140c766ef  mov     al, byte ptr cs:PopBsdPowerTransitionAtBoot+8
0x140c766f5  and     al, 0Fh
0x140c766f7  mov     word ptr cs:PopBsdPowerTransitionAtBoot+0Ch, r14w
0x140c766ff  or      al, 50h
0x140c76701  mov     byte ptr cs:PopBsdPowerTransitionAtBoot+8, al
0x140c76707  bt      ecx, 1Dh
0x140c7670b  jnb     short loc_140C7671B
0x140c7670d  or      byte ptr cs:PopBsdPowerTransitionAtBoot+8, 2
0x140c76714  mov     qword ptr cs:xmmword_140E4D570+8, r14
0x140c7671b  test    byte ptr cs:PopBsdPowerTransitionAtBoot+8, r14b
0x140c76722  jz      loc_140C769B0
0x140c76728  lea     r9, [rsp+1E0h+var_198]
0x140c7672d  mov     [rsp+1E0h+var_198], r14d
0x140c76732  lea     r8, [rsp+1E0h+var_1A0]
0x140c76737  mov     [rsp+1E0h+var_1C0], rsi
0x140c7673c  lea     rdx, SYSTEM_SLEEP_ETW_CHECKPOINT_GUID
0x140c76743  lea     rcx, PopCheckpointSystemSleepVariable; "*,"
0x140c7674a  call    ExGetFirmwareEnvironmentVariable
0x140c7674f  test    eax, eax
0x140c76751  js      short loc_140C7678A
0x140c76753  movzx   eax, [rsp+1E0h+var_1A0]
0x140c76758  mov     ebx, eax
0x140c7675a  mov     byte ptr cs:PopBsdPowerTransitionExtensionAtBoot+2, al
0x140c76760  mov     al, byte ptr cs:PopBsdPowerTransitionExtensionAtBoot+1
0x140c76766  mov     ecx, ebx
0x140c76768  and     al, 0F7h
0x140c7676a  or      al, r15b
0x140c7676d  mov     byte ptr cs:PopBsdPowerTransitionExtensionAtBoot+1, al
0x140c76773  call    PopRecordSleepCheckpoint
0x140c76778  mov     ecx, r14d
0x140c7677b  call    PopRecordSleepCheckpointSource
0x140c76780  mov     cl, r14b
0x140c76783  call    PopClearSystemSleepCheckpoint
0x140c76788  jmp     short loc_140C767AC
0x140c7678a  mov     al, byte ptr cs:PopBsdPowerTransitionExtensionAtBoot+1
0x140c76790  mov     ecx, 2
0x140c76795  movzx   ebx, byte ptr cs:PopBsdPowerTransitionExtensionAtBoot+2
0x140c7679c  and     al, 0FBh
0x140c7679e  or      al, r12b
0x140c767a1  mov     byte ptr cs:PopBsdPowerTransitionExtensionAtBoot+1, al
0x140c767a7  call    PopRecordSleepCheckpointSource
0x140c767ac  mov     rcx, [rdi+0F0h]
0x140c767b3  test    rcx, rcx
0x140c767b6  jz      short loc_140C767F9
0x140c767b8  mov     rcx, [rcx+118h]
0x140c767bf  test    rcx, rcx
0x140c767c2  jz      short loc_140C767F9
0x140c767c4  mov     eax, [rcx+38h]
0x140c767c7  mov     cs:dword_140E4D6F0, eax
0x140c767cd  mov     rax, [rcx+40h]
0x140c767d1  mov     cs:qword_140E4D6F8, rax
0x140c767d8  mov     rax, [rcx+48h]
0x140c767dc  mov     cs:qword_140E4D700, rax
0x140c767e3  mov     rax, [rcx+50h]
0x140c767e7  mov     cs:qword_140E4D708, rax
0x140c767ee  mov     rax, [rcx+58h]
0x140c767f2  mov     cs:qword_140E4D710, rax
0x140c767f9  lea     rax, dword_140E4D768
0x140c76800  mov     cs:dword_140E4D768, esi
0x140c76806  mov     r9d, r15d
0x140c76809  mov     [rsp+1E0h+var_1C0], rax
0x140c7680e  mov     r8, r15
0x140c76811  lea     rdx, aCrashdumpenabl_0; "CrashDumpEnabled"
0x140c76818  lea     rcx, aRegistryMachin_146; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c7681f  call    PopReadRegKeyValue
0x140c76824  lea     rax, dword_140E4D76C
0x140c7682b  mov     cs:dword_140E4D76C, esi
0x140c76831  mov     r9d, r15d
0x140c76834  mov     [rsp+1E0h+var_1C0], rax
0x140c76839  mov     r8, r15
0x140c7683c  lea     rdx, aFilterpages; "FilterPages"
0x140c76843  lea     rcx, aRegistryMachin_146; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c7684a  call    PopReadRegKeyValue
0x140c7684f  xor     r9d, r9d
0x140c76852  lea     rax, dword_140E4D770
0x140c76859  lea     rdx, aInfo; "Info"
0x140c76860  mov     [rsp+1E0h+var_1C0], rax
0x140c76865  lea     rcx, aRegistryMachin_110; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c7686c  lea     r8d, [r9+30h]
0x140c76870  call    PopReadRegKeyValue
0x140c76875  test    eax, eax
0x140c76877  js      short loc_140C768A6
0x140c76879  cmp     cs:dword_140E4D6F0, esi
0x140c7687f  jnz     short loc_140C768A6
0x140c76881  mov     eax, cs:dword_140E4D778
0x140c76887  test    eax, eax
0x140c76889  jz      short loc_140C768A6
0x140c7688b  mov     cs:dword_140E4D6F0, eax
0x140c76891  mov     rax, cs:qword_140E4D780
0x140c76898  mov     cs:qword_140E4D6F8, rax
0x140c7689f  mov     cs:dword_140E4D718, r14d
0x140c768a6  mov     ecx, 7FFE02C4h
0x140c768ab  call    RtlReadULongFromUser
0x140c768b0  mov     cs:dword_140E4D6E8, eax
0x140c768b6  lea     rdx, qword_140E4D748
0x140c768bd  xor     r9d, r9d
0x140c768c0  mov     cs:byte_140E4D730, bl
  ... truncated ...
```
