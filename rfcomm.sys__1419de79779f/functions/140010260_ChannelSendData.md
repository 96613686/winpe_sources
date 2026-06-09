# ChannelSendData

- ea: `0x140010260`
- end: `0x1400105e3`
- name: `ChannelSendData`
- size: `899`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fe48`
- `0x140010810`
- `0x1400114c0`
- `0x140011634`
- `0x140012c60`
- `0x140014210`
- `0x140015c4c`

## callees

- `0x140003bf4`
- `0x140004684`
- `0x140005050`
- `0x140010260`
- `0x140013abc`
- `0x140016b84`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001028b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010568`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001028b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010568`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010306`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010359`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001054e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400105c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010306`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010359`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001054e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400105c6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400104c4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400104c4`

## string_xrefs

- `0x140010428`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x1400102c2`: `Already Sending Data`

## pseudocode

```c
__int64 __fastcall ChannelSendData(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v3; // edi
  _BYTE *v4; // r14
  const char *v5; // rcx
  int v6; // edx
  int *v7; // rcx
  int *v8; // r12
  __int64 v9; // r15
  int v10; // eax
  __int64 v11; // rcx
  KIRQL v12; // dl
  _QWORD *v14; // rdi
  __int64 v15; // rax
  _QWORD *v16; // rcx
  int v17; // edx
  int v18; // ebp
  __int64 v19; // rcx
  _BYTE *v20; // r15
  _BYTE *v21; // rax
  int v22; // ebp
  int BugCheckOnFailure; // [rsp+20h] [rbp-58h]
  int v24; // [rsp+80h] [rbp+8h]

  v1 = *(_QWORD *)(a1 + 56);
  v3 = 0;
  *(_BYTE *)(v1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 56));
  v4 = (_BYTE *)(v1 + 466);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v5 = "Already Sending Data";
    if ( !*v4 )
      v5 = " ";
    WPP_RECORDER_SF_qs(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)" ",
      3,
      21,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a1,
      (__int64)v5);
  }
  if ( *v4 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 56), *(_BYTE *)(v1 + 64));
    goto LABEL_14;
  }
  v7 = (int *)(a1 + 228);
  *v4 = 1;
  v8 = (int *)(a1 + 228);
  v9 = a1 + 104;
  while ( 1 )
  {
    if ( *(_QWORD *)v9 == v9 || (v10 = *(_DWORD *)(a1 + 48), v10 != 5) && (v8 = v7, v10 != 7) )
    {
LABEL_13:
      v12 = *(_BYTE *)(v1 + 64);
      *v4 = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 56), v12);
      v3 = 0;
      goto LABEL_14;
    }
    v11 = *(_QWORD *)(a1 + 56);
    if ( *(_BYTE *)(v11 + 465) )
    {
      if ( *v8 <= 0 )
        goto LABEL_13;
    }
    else if ( (*(_BYTE *)(a1 + 208) & 2) != 0 || *(_BYTE *)(v11 + 464) )
    {
      goto LABEL_13;
    }
    --*v8;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Dd(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        9,
        25,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
        *(_BYTE *)(a1 + 184),
        *v8);
    v14 = *(_QWORD **)v9;
    if ( *(_QWORD *)(*(_QWORD *)v9 + 8LL) != v9
      || (v15 = *v14, *(_QWORD **)(*v14 + 8LL) != v14)
      || (*(_QWORD *)v9 = v15,
          *(_QWORD *)(v15 + 8) = v9,
          RefObj_AddRefEx(v14 + 3, 1346917442, 1036, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c"),
          v16 = *(_QWORD **)(a1 + 128),
          *v16 != a1 + 120) )
    {
      __fastfail(3u);
    }
    *v14 = a1 + 120;
    v14[1] = v16;
    *v16 = v14;
    *(_QWORD *)(a1 + 128) = v14;
    if ( *(_BYTE *)(v1 + 465) )
    {
      v17 = *(_DWORD *)(a1 + 192);
      v18 = *(_DWORD *)(a1 + 188);
      v24 = v17;
      if ( v18 != v17 )
        break;
    }
LABEL_36:
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 56), *(_BYTE *)(v1 + 64));
    RfcommFrameWrite(v1, v14);
    *(_BYTE *)(v1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 56));
    v7 = (int *)(a1 + 228);
  }
  v19 = v14[15];
  if ( !v19 )
  {
    v20 = (_BYTE *)(v14[18] - 1LL);
LABEL_33:
    v22 = v18 - v17;
    *(_DWORD *)(a1 + 192) += v22;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        9,
        23,
        BugCheckOnFailure,
        v22,
        *(_BYTE *)(a1 + 184),
        *(_DWORD *)(a1 + 192));
    *v20 = v22;
    v9 = a1 + 104;
    goto LABEL_36;
  }
  if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
  {
    v21 = *(_BYTE **)(v19 + 24);
  }
  else
  {
    v21 = MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000010u);
    v17 = v24;
  }
  if ( v21 )
  {
    v20 = &v21[((v21[2] & 1) == 0) + 3];
    goto LABEL_33;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      1,
      22,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 56), *(_BYTE *)(v1 + 64));
  v3 = -1073741670;
LABEL_14:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3,
      24,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x140010260  mov     [rsp+arg_10], rbx
0x140010265  push    rbp
0x140010266  push    rsi
0x140010267  push    rdi
0x140010268  push    r12
0x14001026a  push    r13
0x14001026c  push    r14
0x14001026e  push    r15
0x140010270  sub     rsp, 40h
0x140010274  mov     rsi, [rcx+38h]
0x140010278  mov     rbx, rcx
0x14001027b  xor     edi, edi
0x14001027d  mov     [rsp+78h+arg_8], edi
0x140010284  lea     r13, [rsi+38h]
0x140010288  mov     rcx, r13; SpinLock
0x14001028b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010292  nop     dword ptr [rax+rax+00h]
0x140010297  mov     [rsi+40h], al
0x14001029a  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400102a1  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400102a8  lea     r14, [rsi+1D2h]
0x1400102af  lea     rbp, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400102b6  jz      short loc_1400102FB
0x1400102b8  cmp     [r14], dil
0x1400102bb  lea     rdx, asc_140022D68; " "
0x1400102c2  lea     rcx, aAlreadySending; "Already Sending Data"
0x1400102c9  cmovz   rcx, rdx
0x1400102cd  lea     r9d, [rdi+15h]
0x1400102d1  mov     [rsp+78h+var_48], rcx
0x1400102d6  lea     r8d, [rdi+3]
0x1400102da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400102e1  mov     qword ptr [rsp+78h+Priority], rbx
0x1400102e6  mov     qword ptr [rsp+78h+BugCheckOnFailure], rbp
0x1400102eb  mov     rcx, [rcx+40h]
0x1400102ef  call    WPP_RECORDER_SF_qs
0x1400102f4  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400102fb  cmp     [r14], dil
0x1400102fe  jz      short loc_140010314
0x140010300  mov     dl, [rsi+40h]; NewIrql
0x140010303  mov     rcx, r13; SpinLock
0x140010306  call    cs:__imp_KeReleaseSpinLock
0x14001030d  nop     dword ptr [rax+rax+00h]
0x140010312  jmp     short loc_14001036C
0x140010314  lea     rcx, [rbx+0E4h]
0x14001031b  mov     byte ptr [r14], 1
0x14001031f  mov     r12, rcx
0x140010322  lea     r15, [rbx+68h]
0x140010326  cmp     [r15], r15
0x140010329  jz      short loc_14001034F
0x14001032b  mov     eax, [rbx+30h]
0x14001032e  cmp     eax, 5
0x140010331  jz      short loc_14001033B
0x140010333  mov     r12, rcx
0x140010336  cmp     eax, 7
0x140010339  jnz     short loc_14001034F
0x14001033b  mov     rcx, [rbx+38h]
0x14001033f  cmp     byte ptr [rcx+1D1h], 0
0x140010346  jz      short loc_1400103B6
0x140010348  cmp     dword ptr [r12], 0
0x14001034d  jg      short loc_1400103C8
0x14001034f  mov     dl, [rsi+40h]; NewIrql
0x140010352  mov     rcx, r13; SpinLock
0x140010355  mov     byte ptr [r14], 0
0x140010359  call    cs:__imp_KeReleaseSpinLock
0x140010360  nop     dword ptr [rax+rax+00h]
0x140010365  mov     edi, [rsp+78h+arg_8]
0x14001036c  lea     rax, WPP_RECORDER_INITIALIZED
0x140010373  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001037a  jz      short loc_14001039B
0x14001037c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010383  mov     r9d, 18h
0x140010389  mov     qword ptr [rsp+78h+BugCheckOnFailure], rbp
0x14001038e  mov     rcx, [rcx+40h]
0x140010392  lea     r8d, [r9-15h]
0x140010396  call    WPP_RECORDER_SF_
0x14001039b  mov     rbx, [rsp+78h+arg_10]
0x1400103a3  mov     eax, edi
0x1400103a5  add     rsp, 40h
0x1400103a9  pop     r15
0x1400103ab  pop     r14
0x1400103ad  pop     r13
0x1400103af  pop     r12
0x1400103b1  pop     rdi
0x1400103b2  pop     rsi
0x1400103b3  pop     rbp
0x1400103b4  retn
0x1400103b6  test    byte ptr [rbx+0D0h], 2
0x1400103bd  jnz     short loc_14001034F
0x1400103bf  cmp     byte ptr [rcx+1D0h], 0
0x1400103c6  jnz     short loc_14001034F
0x1400103c8  dec     dword ptr [r12]
0x1400103cc  mov     ecx, [r12]
0x1400103d0  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400103d7  jz      short loc_140010407
0x1400103d9  movzx   eax, byte ptr [rbx+0B8h]
0x1400103e0  mov     r9d, 19h
0x1400103e6  mov     dword ptr [rsp+78h+var_48], ecx
0x1400103ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103f1  mov     [rsp+78h+Priority], eax
0x1400103f5  lea     r8d, [r9-10h]
0x1400103f9  mov     qword ptr [rsp+78h+BugCheckOnFailure], rbp
0x1400103fe  mov     rcx, [rcx+40h]
0x140010402  call    WPP_RECORDER_SF_Dd
0x140010407  mov     rdi, [r15]
0x14001040a  cmp     [rdi+8], r15
0x14001040e  jnz     loc_1400105DC
0x140010414  mov     rax, [rdi]
0x140010417  cmp     [rax+8], rdi
0x14001041b  jnz     loc_1400105DC
0x140010421  mov     [r15], rax
0x140010424  lea     rcx, [rdi+18h]
0x140010428  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001042f  mov     [rax+8], r15
0x140010433  mov     edx, 50485442h
0x140010438  mov     r8d, 40Ch
0x14001043e  call    RefObj_AddRefEx
0x140010443  lea     rax, [rbx+78h]
0x140010447  mov     rcx, [rax+8]
0x14001044b  cmp     [rcx], rax
0x14001044e  jnz     loc_1400105DC
0x140010454  mov     [rdi], rax
0x140010457  mov     [rdi+8], rcx
0x14001045b  mov     [rcx], rdi
0x14001045e  mov     [rax+8], rdi
0x140010462  cmp     byte ptr [rsi+1D1h], 0
0x140010469  jz      loc_140010548
0x14001046f  mov     edx, [rbx+0C0h]
0x140010475  mov     ebp, [rbx+0BCh]
0x14001047b  mov     [rsp+78h+arg_0], edx
0x140010482  cmp     ebp, edx
0x140010484  jz      loc_140010541
0x14001048a  mov     rcx, [rdi+78h]; MemoryDescriptorList
0x14001048e  test    rcx, rcx
0x140010491  jnz     short loc_14001049F
0x140010493  mov     r15, [rdi+90h]
0x14001049a  dec     r15
0x14001049d  jmp     short loc_1400104EF
0x14001049f  test    byte ptr [rcx+0Ah], 5
0x1400104a3  jz      short loc_1400104AB
0x1400104a5  mov     rax, [rcx+18h]
0x1400104a9  jmp     short loc_1400104D7
0x1400104ab  xor     r9d, r9d; RequestedAddress
0x1400104ae  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400104b6  xor     edx, edx; AccessMode
0x1400104b8  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400104c0  lea     r8d, [r9+1]; CacheType
0x1400104c4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400104cb  nop     dword ptr [rax+rax+00h]
0x1400104d0  mov     edx, [rsp+78h+arg_0]
0x1400104d7  test    rax, rax
0x1400104da  jz      loc_14001058A
0x1400104e0  mov     cl, [rax+2]
0x1400104e3  not     cl
0x1400104e5  and     ecx, 1
0x1400104e8  lea     r15, [rcx+3]
0x1400104ec  add     r15, rax
0x1400104ef  sub     ebp, edx
0x1400104f1  add     [rbx+0C0h], ebp
0x1400104f7  mov     ecx, [rbx+0C0h]
0x1400104fd  lea     rax, WPP_RECORDER_INITIALIZED
0x140010504  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001050b  jz      short loc_14001053A
0x14001050d  movzx   eax, byte ptr [rbx+0B8h]
0x140010514  mov     r9d, 17h
0x14001051a  mov     [rsp+78h+var_40], ecx
0x14001051e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010525  mov     dword ptr [rsp+78h+var_48], eax
0x140010529  lea     r8d, [r9-0Eh]
0x14001052d  mov     [rsp+78h+Priority], ebp
0x140010531  mov     rcx, [rcx+40h]
0x140010535  call    WPP_RECORDER_SF_dDd
0x14001053a  mov     [r15], bpl
0x14001053d  lea     r15, [rbx+68h]
0x140010541  lea     rbp, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140010548  mov     dl, [rsi+40h]; NewIrql
0x14001054b  mov     rcx, r13; SpinLock
0x14001054e  call    cs:__imp_KeReleaseSpinLock
0x140010555  nop     dword ptr [rax+rax+00h]
0x14001055a  mov     rdx, rdi
0x14001055d  mov     rcx, rsi
0x140010560  call    RfcommFrameWrite
0x140010565  mov     rcx, r13; SpinLock
0x140010568  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001056f  nop     dword ptr [rax+rax+00h]
0x140010574  mov     [rsi+40h], al
0x140010577  lea     rcx, [rbx+0E4h]
0x14001057e  lea     rdx, WPP_RECORDER_INITIALIZED
0x140010585  jmp     loc_140010326
0x14001058a  lea     rax, WPP_RECORDER_INITIALIZED
0x140010591  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010598  lea     rbp, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001059f  jz      short loc_1400105C0
0x1400105a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105a8  mov     r9d, 16h
0x1400105ae  mov     qword ptr [rsp+78h+BugCheckOnFailure], rbp
0x1400105b3  mov     rcx, [rcx+40h]
0x1400105b7  lea     r8d, [r9-15h]
0x1400105bb  call    WPP_RECORDER_SF_
0x1400105c0  mov     dl, [rsi+40h]; NewIrql
0x1400105c3  mov     rcx, r13; SpinLock
0x1400105c6  call    cs:__imp_KeReleaseSpinLock
0x1400105cd  nop     dword ptr [rax+rax+00h]
0x1400105d2  mov     edi, 0C000009Ah
0x1400105d7  jmp     loc_14001036C
0x1400105dc  mov     ecx, 3
0x1400105e1  int     29h; Win8: RtlFailFast(ecx)
```
