# HidpRegisterSleepstudyBlockerReasons

- ea: `0x18002136c`
- end: `0x1800218c9`
- name: `HidpRegisterSleepstudyBlockerReasons`
- size: `1373`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003b748`

## callees

- `0x18000ddc8`
- `0x18001a0b8`
- `0x18001e8ec`
- `0x1800211b0`
- `0x18002136c`
- `0x180027ba0`

## import_xrefs

- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x1800213c9`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x18002147d`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x18002156d`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x180021635`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x1800216fd`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x1800217c5`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x1800213c9`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x18002147d`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x18002156d`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x180021635`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x1800216fd`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x1800217c5`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GetPdoFriendlyName` at `0x1800213dd`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GetPdoFriendlyName` at `0x1800213dd`

## string_xrefs

- `0x1800214b1`: `Collection Not Ready`

## pseudocode

```c
__int64 __fastcall HidpRegisterSleepstudyBlockerReasons(__int64 a1, KSPIN_LOCK *a2)
{
  int v4; // edx
  int PdoFriendlyName; // ebx
  int v6; // r8d
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  const wchar_t *v10; // r9
  __int128 *v11; // r8
  __int128 *v12; // rcx
  int v13; // edx
  int v14; // r8d
  PDEVICE_OBJECT v15; // r10
  __int16 v17; // [rsp+30h] [rbp-D0h]
  KSPIN_LOCK v18; // [rsp+40h] [rbp-C0h]
  char v19; // [rsp+48h] [rbp-B8h]
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v23; // [rsp+80h] [rbp-80h] BYREF
  __int128 v24; // [rsp+90h] [rbp-70h] BYREF
  char v25; // [rsp+A0h] [rbp-60h] BYREF

  v22[0] = 0x2000000;
  v22[1] = &v25;
  v24 = 0;
  v23 = 0;
  SleepstudyHelper_GenerateGuid(0, a1, &v24);
  PdoFriendlyName = SleepstudyHelper_GetPdoFriendlyName(a1, v22);
  if ( PdoFriendlyName < 0 )
  {
    LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v4,
        v6,
        a2[84],
        2,
        11,
        103,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *a2,
        PdoFriendlyName);
    }
    goto LABEL_59;
  }
  SleepstudyHelper_GenerateGuid(7, a1 + 336, &v23);
  if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(v8, v7, v9) )
  {
    v20 = v23;
    v10 = L"Collection Not Ready";
    v21 = v24;
    v11 = &v20;
    v12 = &v21;
  }
  else
  {
    v21 = v23;
    v10 = L"Collection Not Started";
    v20 = v24;
    v11 = &v21;
    v12 = &v20;
  }
  PdoFriendlyName = HidpRegisterSleepstudyBlockerReason(v12, (__int64)v22, v11, (__int64)v10, (__int64)(a2 + 268));
  if ( PdoFriendlyName < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_59;
    v19 = PdoFriendlyName;
    v18 = *a2;
    v17 = 104;
    goto LABEL_58;
  }
  SleepstudyHelper_GenerateGuid(7, a1 + 672, &v23);
  v21 = v23;
  v20 = v24;
  PdoFriendlyName = HidpRegisterSleepstudyBlockerReason(
                      &v20,
                      (__int64)v22,
                      &v21,
                      (__int64)L"Hardware IO",
                      (__int64)(a2 + 269));
  if ( PdoFriendlyName < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_59;
    v19 = PdoFriendlyName;
    v18 = *a2;
    v17 = 105;
    goto LABEL_58;
  }
  SleepstudyHelper_GenerateGuid(7, a1 + 1008, &v23);
  v21 = v23;
  v20 = v24;
  PdoFriendlyName = HidpRegisterSleepstudyBlockerReason(
                      &v20,
                      (__int64)v22,
                      &v21,
                      (__int64)L"Software IO",
                      (__int64)(a2 + 270));
  if ( PdoFriendlyName < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_59;
    v19 = PdoFriendlyName;
    v18 = *a2;
    v17 = 106;
    goto LABEL_58;
  }
  SleepstudyHelper_GenerateGuid(7, a1 + 1344, &v23);
  v21 = v23;
  v20 = v24;
  PdoFriendlyName = HidpRegisterSleepstudyBlockerReason(
                      &v20,
                      (__int64)v22,
                      &v21,
                      (__int64)L"Internal Error: Po Callback Pending",
                      (__int64)(a2 + 271));
  if ( PdoFriendlyName < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_59;
    v19 = PdoFriendlyName;
    v18 = *a2;
    v17 = 107;
    goto LABEL_58;
  }
  SleepstudyHelper_GenerateGuid(7, a1 + 1680, &v23);
  v21 = v23;
  v20 = v24;
  PdoFriendlyName = HidpRegisterSleepstudyBlockerReason(
                      &v20,
                      (__int64)v22,
                      &v21,
                      (__int64)L"EPM Disabled",
                      (__int64)(a2 + 272));
  if ( PdoFriendlyName < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_59;
    v19 = PdoFriendlyName;
    v18 = *a2;
    v17 = 108;
LABEL_58:
    WPP_RECORDER_AND_TRACE_SF_qL(
      v15->AttachedDevice,
      v13,
      v14,
      a2[84],
      3,
      11,
      v17,
      (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
      v18,
      v19);
LABEL_59:
    HidpUnregisterSleepstudyBlockerReasons(a2);
  }
  return (unsigned int)PdoFriendlyName;
}

```

## disassembly

```asm
0x18002136c  mov     [rsp-8+arg_10], rbx
0x180021371  mov     [rsp-8+arg_18], rsi
0x180021376  push    rbp
0x180021377  push    rdi
0x180021378  push    r14
0x18002137a  lea     rbp, [rsp-1B0h]
0x180021382  sub     rsp, 2B0h
0x180021389  mov     rax, cs:__security_cookie
0x180021390  xor     rax, rsp
0x180021393  mov     [rbp+1C0h+var_20], rax
0x18002139a  mov     rdi, rdx
0x18002139d  mov     [rsp+2C0h+var_250], 2000000h
0x1800213a6  mov     rdx, rcx
0x1800213a9  lea     rax, [rbp+1C0h+var_220]
0x1800213ad  mov     rsi, rcx
0x1800213b0  mov     [rsp+2C0h+var_248], rax
0x1800213b5  xorps   xmm0, xmm0
0x1800213b8  lea     r8, [rbp+1C0h+var_230]
0x1800213bc  xorps   xmm1, xmm1
0x1800213bf  xor     ecx, ecx
0x1800213c1  movups  [rbp+1C0h+var_230], xmm0
0x1800213c5  movups  [rbp+1C0h+var_240], xmm1
0x1800213c9  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x1800213d0  nop     dword ptr [rax+rax+00h]
0x1800213d5  lea     rdx, [rsp+2C0h+var_250]
0x1800213da  mov     rcx, rsi
0x1800213dd  call    cs:__imp_SleepstudyHelper_GetPdoFriendlyName
0x1800213e4  nop     dword ptr [rax+rax+00h]
0x1800213e9  mov     ebx, eax
0x1800213eb  test    eax, eax
0x1800213ed  jns     short loc_180021469
0x1800213ef  mov     r10, cs:WPP_GLOBAL_Control
0x1800213f6  lea     rcx, WPP_GLOBAL_Control
0x1800213fd  cmp     r10, rcx
0x180021400  jz      short loc_180021417
0x180021402  test    dword ptr [r10+2Ch], 400h
0x18002140a  jz      short loc_180021417
0x18002140c  cmp     byte ptr [r10+29h], 2
0x180021411  jb      short loc_180021417
0x180021413  mov     dl, 1
0x180021415  jmp     short loc_180021419
0x180021417  xor     dl, dl
0x180021419  lea     rax, WPP_RECORDER_INITIALIZED
0x180021420  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180021427  setnz   r8b
0x18002142b  test    dl, dl
0x18002142d  jnz     short loc_180021438
0x18002142f  test    r8b, r8b
0x180021432  jz      loc_180021897
0x180021438  mov     rax, [rdi]
0x18002143b  mov     dword ptr [rsp+2C0h+var_278], ebx
0x18002143f  mov     [rsp+2C0h+var_280], rax
0x180021444  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18002144b  mov     [rsp+2C0h+var_288], rax
0x180021450  mov     [rsp+2C0h+var_290], 67h ; 'g'
0x180021457  mov     [rsp+2C0h+var_298], 0Bh
0x18002145f  mov     byte ptr [rsp+2C0h+var_2A0], 2
0x180021464  jmp     loc_180021887
0x180021469  mov     r14d, 7
0x18002146f  lea     rdx, [rsi+150h]
0x180021476  mov     ecx, r14d
0x180021479  lea     r8, [rbp+1C0h+var_240]
0x18002147d  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x180021484  nop     dword ptr [rax+rax+00h]
0x180021489  lea     rbx, [rdi+860h]
0x180021490  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline
0x180021495  movaps  xmm0, [rbp+1C0h+var_240]
0x180021499  lea     rdx, [rsp+2C0h+var_250]
0x18002149e  movaps  xmm1, [rbp+1C0h+var_230]
0x1800214a2  mov     [rsp+2C0h+var_2A0], rbx
0x1800214a7  test    eax, eax
0x1800214a9  jz      short loc_1800214CA
0x1800214ab  movdqa  [rsp+2C0h+var_270], xmm0
0x1800214b1  lea     r9, aCollectionNotR; "Collection Not Ready"
0x1800214b8  movdqa  [rsp+2C0h+var_260], xmm1
0x1800214be  lea     r8, [rsp+2C0h+var_270]
0x1800214c3  lea     rcx, [rsp+2C0h+var_260]
0x1800214c8  jmp     short loc_1800214E7
0x1800214ca  movdqa  [rsp+2C0h+var_260], xmm0
0x1800214d0  lea     r9, aCollectionNotS; "Collection Not Started"
0x1800214d7  movdqa  [rsp+2C0h+var_270], xmm1
0x1800214dd  lea     r8, [rsp+2C0h+var_260]
0x1800214e2  lea     rcx, [rsp+2C0h+var_270]
0x1800214e7  call    HidpRegisterSleepstudyBlockerReason
0x1800214ec  mov     ebx, eax
0x1800214ee  test    eax, eax
0x1800214f0  jns     short loc_18002155F
0x1800214f2  mov     r10, cs:WPP_GLOBAL_Control
0x1800214f9  lea     rcx, WPP_GLOBAL_Control
0x180021500  cmp     r10, rcx
0x180021503  jz      short loc_18002151A
0x180021505  test    dword ptr [r10+2Ch], 400h
0x18002150d  jz      short loc_18002151A
0x18002150f  cmp     byte ptr [r10+29h], 3
0x180021514  jb      short loc_18002151A
0x180021516  mov     dl, 1
0x180021518  jmp     short loc_18002151C
0x18002151a  xor     dl, dl
0x18002151c  lea     rax, WPP_RECORDER_INITIALIZED
0x180021523  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002152a  setnz   r8b
0x18002152e  test    dl, dl
0x180021530  jnz     short loc_18002153B
0x180021532  test    r8b, r8b
0x180021535  jz      loc_180021897
0x18002153b  mov     rax, [rdi]
0x18002153e  mov     dword ptr [rsp+2C0h+var_278], ebx
0x180021542  mov     [rsp+2C0h+var_280], rax
0x180021547  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18002154e  mov     [rsp+2C0h+var_288], rax
0x180021553  mov     [rsp+2C0h+var_290], 68h ; 'h'
0x18002155a  jmp     loc_18002187A
0x18002155f  lea     rdx, [rsi+2A0h]
0x180021566  mov     ecx, r14d
0x180021569  lea     r8, [rbp+1C0h+var_240]
0x18002156d  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x180021574  nop     dword ptr [rax+rax+00h]
0x180021579  movaps  xmm0, [rbp+1C0h+var_240]
0x18002157d  lea     rax, [rdi+868h]
0x180021584  movaps  xmm1, [rbp+1C0h+var_230]
0x180021588  lea     r9, aHardwareIo; "Hardware IO"
0x18002158f  lea     r8, [rsp+2C0h+var_260]
0x180021594  movdqa  [rsp+2C0h+var_260], xmm0
0x18002159a  lea     rdx, [rsp+2C0h+var_250]
0x18002159f  movdqa  [rsp+2C0h+var_270], xmm1
0x1800215a5  lea     rcx, [rsp+2C0h+var_270]
0x1800215aa  mov     [rsp+2C0h+var_2A0], rax
0x1800215af  call    HidpRegisterSleepstudyBlockerReason
0x1800215b4  mov     ebx, eax
0x1800215b6  test    eax, eax
0x1800215b8  jns     short loc_180021627
0x1800215ba  mov     r10, cs:WPP_GLOBAL_Control
0x1800215c1  lea     rcx, WPP_GLOBAL_Control
0x1800215c8  cmp     r10, rcx
0x1800215cb  jz      short loc_1800215E2
0x1800215cd  test    dword ptr [r10+2Ch], 400h
0x1800215d5  jz      short loc_1800215E2
0x1800215d7  cmp     byte ptr [r10+29h], 3
0x1800215dc  jb      short loc_1800215E2
0x1800215de  mov     dl, 1
0x1800215e0  jmp     short loc_1800215E4
0x1800215e2  xor     dl, dl
0x1800215e4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800215eb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800215f2  setnz   r8b
0x1800215f6  test    dl, dl
0x1800215f8  jnz     short loc_180021603
0x1800215fa  test    r8b, r8b
0x1800215fd  jz      loc_180021897
0x180021603  mov     rax, [rdi]
0x180021606  mov     dword ptr [rsp+2C0h+var_278], ebx
0x18002160a  mov     [rsp+2C0h+var_280], rax
0x18002160f  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x180021616  mov     [rsp+2C0h+var_288], rax
0x18002161b  mov     [rsp+2C0h+var_290], 69h ; 'i'
0x180021622  jmp     loc_18002187A
0x180021627  lea     rdx, [rsi+3F0h]
0x18002162e  mov     ecx, r14d
0x180021631  lea     r8, [rbp+1C0h+var_240]
0x180021635  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x18002163c  nop     dword ptr [rax+rax+00h]
0x180021641  movaps  xmm0, [rbp+1C0h+var_240]
0x180021645  lea     rax, [rdi+870h]
0x18002164c  movaps  xmm1, [rbp+1C0h+var_230]
0x180021650  lea     r9, aSoftwareIo; "Software IO"
0x180021657  lea     r8, [rsp+2C0h+var_260]
0x18002165c  movdqa  [rsp+2C0h+var_260], xmm0
0x180021662  lea     rdx, [rsp+2C0h+var_250]
0x180021667  movdqa  [rsp+2C0h+var_270], xmm1
0x18002166d  lea     rcx, [rsp+2C0h+var_270]
0x180021672  mov     [rsp+2C0h+var_2A0], rax
0x180021677  call    HidpRegisterSleepstudyBlockerReason
0x18002167c  mov     ebx, eax
0x18002167e  test    eax, eax
0x180021680  jns     short loc_1800216EF
0x180021682  mov     r10, cs:WPP_GLOBAL_Control
0x180021689  lea     rcx, WPP_GLOBAL_Control
0x180021690  cmp     r10, rcx
0x180021693  jz      short loc_1800216AA
0x180021695  test    dword ptr [r10+2Ch], 400h
0x18002169d  jz      short loc_1800216AA
0x18002169f  cmp     byte ptr [r10+29h], 3
0x1800216a4  jb      short loc_1800216AA
0x1800216a6  mov     dl, 1
0x1800216a8  jmp     short loc_1800216AC
0x1800216aa  xor     dl, dl
0x1800216ac  lea     rax, WPP_RECORDER_INITIALIZED
0x1800216b3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800216ba  setnz   r8b
0x1800216be  test    dl, dl
0x1800216c0  jnz     short loc_1800216CB
0x1800216c2  test    r8b, r8b
0x1800216c5  jz      loc_180021897
0x1800216cb  mov     rax, [rdi]
0x1800216ce  mov     dword ptr [rsp+2C0h+var_278], ebx
0x1800216d2  mov     [rsp+2C0h+var_280], rax
0x1800216d7  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x1800216de  mov     [rsp+2C0h+var_288], rax
0x1800216e3  mov     [rsp+2C0h+var_290], 6Ah ; 'j'
0x1800216ea  jmp     loc_18002187A
0x1800216ef  lea     rdx, [rsi+540h]
0x1800216f6  mov     ecx, r14d
0x1800216f9  lea     r8, [rbp+1C0h+var_240]
0x1800216fd  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x180021704  nop     dword ptr [rax+rax+00h]
0x180021709  movaps  xmm0, [rbp+1C0h+var_240]
0x18002170d  lea     rax, [rdi+878h]
0x180021714  movaps  xmm1, [rbp+1C0h+var_230]
0x180021718  lea     r9, aInternalErrorP; "Internal Error: Po Callback Pending"
0x18002171f  lea     r8, [rsp+2C0h+var_260]
0x180021724  movdqa  [rsp+2C0h+var_260], xmm0
0x18002172a  lea     rdx, [rsp+2C0h+var_250]
0x18002172f  movdqa  [rsp+2C0h+var_270], xmm1
0x180021735  lea     rcx, [rsp+2C0h+var_270]
0x18002173a  mov     [rsp+2C0h+var_2A0], rax
0x18002173f  call    HidpRegisterSleepstudyBlockerReason
0x180021744  mov     ebx, eax
0x180021746  test    eax, eax
0x180021748  jns     short loc_1800217B7
0x18002174a  mov     r10, cs:WPP_GLOBAL_Control
0x180021751  lea     rcx, WPP_GLOBAL_Control
0x180021758  cmp     r10, rcx
0x18002175b  jz      short loc_180021772
0x18002175d  test    dword ptr [r10+2Ch], 400h
0x180021765  jz      short loc_180021772
0x180021767  cmp     byte ptr [r10+29h], 3
0x18002176c  jb      short loc_180021772
0x18002176e  mov     dl, 1
0x180021770  jmp     short loc_180021774
0x180021772  xor     dl, dl
0x180021774  lea     rax, WPP_RECORDER_INITIALIZED
0x18002177b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180021782  setnz   r8b
0x180021786  test    dl, dl
0x180021788  jnz     short loc_180021793
0x18002178a  test    r8b, r8b
0x18002178d  jz      loc_180021897
0x180021793  mov     rax, [rdi]
0x180021796  mov     dword ptr [rsp+2C0h+var_278], ebx
0x18002179a  mov     [rsp+2C0h+var_280], rax
0x18002179f  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x1800217a6  mov     [rsp+2C0h+var_288], rax
0x1800217ab  mov     [rsp+2C0h+var_290], 6Bh ; 'k'
0x1800217b2  jmp     loc_18002187A
0x1800217b7  lea     rdx, [rsi+690h]
0x1800217be  mov     ecx, r14d
0x1800217c1  lea     r8, [rbp+1C0h+var_240]
0x1800217c5  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x1800217cc  nop     dword ptr [rax+rax+00h]
0x1800217d1  movaps  xmm0, [rbp+1C0h+var_240]
0x1800217d5  lea     rax, [rdi+880h]
0x1800217dc  movaps  xmm1, [rbp+1C0h+var_230]
0x1800217e0  lea     r9, aEpmDisabled; "EPM Disabled"
0x1800217e7  lea     r8, [rsp+2C0h+var_260]
0x1800217ec  movdqa  [rsp+2C0h+var_260], xmm0
0x1800217f2  lea     rdx, [rsp+2C0h+var_250]
0x1800217f7  movdqa  [rsp+2C0h+var_270], xmm1
0x1800217fd  lea     rcx, [rsp+2C0h+var_270]
0x180021802  mov     [rsp+2C0h+var_2A0], rax
0x180021807  call    HidpRegisterSleepstudyBlockerReason
0x18002180c  mov     ebx, eax
0x18002180e  test    eax, eax
0x180021810  jns     loc_18002189F
0x180021816  mov     r10, cs:WPP_GLOBAL_Control
0x18002181d  lea     rcx, WPP_GLOBAL_Control
0x180021824  cmp     r10, rcx
0x180021827  jz      short loc_18002183E
0x180021829  test    dword ptr [r10+2Ch], 400h
0x180021831  jz      short loc_18002183E
0x180021833  cmp     byte ptr [r10+29h], 3
0x180021838  jb      short loc_18002183E
0x18002183a  mov     dl, 1
0x18002183c  jmp     short loc_180021840
0x18002183e  xor     dl, dl
0x180021840  lea     rax, WPP_RECORDER_INITIALIZED
0x180021847  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002184e  setnz   r8b
0x180021852  test    dl, dl
0x180021854  jnz     short loc_18002185B
0x180021856  test    r8b, r8b
0x180021859  jz      short loc_180021897
0x18002185b  mov     rax, [rdi]
0x18002185e  mov     dword ptr [rsp+2C0h+var_278], ebx
0x180021862  mov     [rsp+2C0h+var_280], rax
0x180021867  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18002186e  mov     [rsp+2C0h+var_288], rax
0x180021873  mov     [rsp+2C0h+var_290], 6Ch ; 'l'
0x18002187a  mov     [rsp+2C0h+var_298], 0Bh
0x180021882  mov     byte ptr [rsp+2C0h+var_2A0], 3
0x180021887  mov     r9, [rdi+2A0h]
0x18002188e  mov     rcx, [r10+18h]
0x180021892  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180021897  mov     rcx, rdi
0x18002189a  call    HidpUnregisterSleepstudyBlockerReasons
0x18002189f  mov     eax, ebx
0x1800218a1  mov     rcx, [rbp+1C0h+var_20]
0x1800218a8  xor     rcx, rsp; StackCookie
0x1800218ab  call    __security_check_cookie
0x1800218b0  lea     r11, [rsp+2C0h+var_10]
0x1800218b8  mov     rbx, [r11+30h]
  ... truncated ...
```
