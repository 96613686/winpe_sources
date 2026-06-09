# PxTapiMakeCall

- ea: `0x140013bc0`
- end: `0x1400142fb`
- name: `PxTapiMakeCall`
- size: `1851`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x140001b54`
- `0x140001b84`
- `0x140001c60`
- `0x140006c1c`
- `0x140006ed4`
- `0x140007040`
- `0x140007308`
- `0x14000757c`
- `0x1400075d8`
- `0x14000785c`
- `0x140007fc0`
- `0x140008000`
- `0x14000fcb0`
- `0x140010e0c`
- `0x140010f64`
- `0x1400112d8`
- `0x140013bc0`
- `0x1400155e4`
- `0x1400162c8`
- `0x140016628`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013c90`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013d95`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013efa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014176`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001425e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013c90`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013d95`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013efa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014176`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001425e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013cde`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013db6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013e4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013ee4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f53`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f73`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014246`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014275`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400142c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013cde`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013db6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013e4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013ee4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f53`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f73`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014246`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014275`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400142c5`
- `NDIS!NdisClMakeCall` at `0x140014292`
- `NDIS!NdisClMakeCall` at `0x140014292`
- `NDIS!NdisCoDeleteVc` at `0x140014146`
- `NDIS!NdisCoDeleteVc` at `0x140014146`
- `NDIS!NdisCoCreateVc` at `0x1400140af`
- `NDIS!NdisCoCreateVc` at `0x1400140af`

## pseudocode

```c
__int64 __fastcall PxTapiMakeCall(__int64 a1)
{
  __int64 v1; // r14
  unsigned int v3; // eax
  __int64 v4; // r8
  char *v6; // rdi
  KSPIN_LOCK *v7; // r15
  char *v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int v11; // eax
  char *i; // rsi
  KIRQL v13; // al
  __int64 v15; // rcx
  __int64 v16; // r13
  __int64 v17; // r9
  unsigned __int64 v18; // rcx
  _BYTE *v19; // rax
  _WORD *v20; // rax
  unsigned __int64 v21; // rcx
  __int64 Vc; // rbx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // ecx
  NDIS_HANDLE *v27; // r12
  NDIS_HANDLE *v28; // rcx
  unsigned int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  KIRQL v34; // dl
  KIRQL v35; // al
  unsigned int v36; // eax
  PVOID P; // [rsp+40h] [rbp-39h] BYREF
  __int64 v38; // [rsp+48h] [rbp-31h] BYREF
  __int64 v39; // [rsp+50h] [rbp-29h]
  _QWORD Src[6]; // [rsp+58h] [rbp-21h] BYREF

  v39 = a1;
  P = 0;
  v1 = a1 + 48;
  v38 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  v3 = *(_DWORD *)(v1 + 36);
  if ( v3 < 0xE0 || v3 >= *(_DWORD *)(a1 + 40) )
    return 3221299225LL;
  if ( !(unsigned __int8)IsTapiLineValid(*(unsigned int *)(v1 + 8), &P) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_P(WPP_GLOBAL_Control->AttachedDevice, 11, v4, *(_QWORD *)(v1 + 8));
    return 4098;
  }
  v6 = (char *)P;
  v7 = (KSPIN_LOCK *)((char *)P + 120);
  v6[128] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 15);
  if ( (*(_DWORD *)(*((_QWORD *)v6 + 10) + 56LL) & 4) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    KeReleaseSpinLock(v7, v6[128]);
    v10 = 4099;
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qP(WPP_GLOBAL_Control->AttachedDevice, 13, v9, v6, *(_QWORD *)(v1 + 8));
  if ( *(_DWORD *)(v1 + 68) != 1 )
  {
    v8 = v6 + 96;
    for ( i = (char *)*((_QWORD *)v6 + 12); i != v8; i = *(char **)i )
    {
      if ( *((_DWORD *)i + 9) < *(_DWORD *)(*((_QWORD *)i + 5) + 84LL) )
        goto LABEL_22;
    }
    goto LABEL_23;
  }
  v11 = *(_DWORD *)(v1 + 72);
  if ( v11 >= *((_DWORD *)v6 + 22) )
    goto LABEL_23;
  _mm_lfence();
  i = *(char **)(*((_QWORD *)v6 + 14) + 8LL * v11);
LABEL_22:
  if ( !i )
  {
LABEL_23:
    v10 = 4098;
    KeReleaseSpinLock(v7, v6[128]);
    goto LABEL_24;
  }
  v15 = *(unsigned int *)(v1 + 36);
  v16 = *((_QWORD *)v6 + 7);
  P = *(PVOID *)(*((_QWORD *)v6 + 3) + 24LL);
  v17 = v15 + v1;
  if ( *((_DWORD *)P + 43) == 12 )
  {
    if ( v17 )
    {
      v18 = (unsigned int)(*(_DWORD *)(a1 + 40) - v15);
      if ( v18 > 0x7FFFFFFF )
        goto LABEL_41;
      v19 = (_BYTE *)v17;
      if ( !v18 )
        goto LABEL_41;
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        --v18;
      }
      while ( v18 );
      if ( !v18 )
        goto LABEL_41;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qs(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v8, v9, v17, v17);
  }
  else
  {
    if ( v17 )
    {
      v20 = (_WORD *)(v15 + v1);
      v21 = (unsigned __int64)(unsigned int)(*(_DWORD *)(a1 + 40) - v15) >> 1;
      if ( !v21 )
      {
LABEL_41:
        KeReleaseSpinLock(v7, v6[128]);
        v10 = -1073668071;
        goto LABEL_24;
      }
      while ( *v20 )
      {
        ++v20;
        if ( !--v21 )
          goto LABEL_41;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qS(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v8, v9, v17, v17);
  }
  KeReleaseSpinLock(v7, v6[128]);
  *(_BYTE *)(v16 + 192) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v16 + 184));
  Vc = PxAllocateVc(v16);
  if ( !Vc )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 184), *(_BYTE *)(v16 + 192));
    goto LABEL_58;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 184), *(_BYTE *)(v16 + 192));
  if ( (unsigned int)AllocateTapiCallInfo(Vc, 0) )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      goto LABEL_64;
    v24 = 17;
  }
  else
  {
    *(_QWORD *)(Vc + 256) = v6;
    *(_QWORD *)(Vc + 264) = i;
    _InterlockedIncrement((volatile signed __int32 *)i + 9);
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v6 + 10) + 20LL));
    v25 = *(_QWORD *)(Vc + 304);
    *(_QWORD *)(Vc + 272) = *(_QWORD *)(v1 + 16);
    *(_DWORD *)(v25 + 16) = *((_DWORD *)v6 + 13);
    *(_DWORD *)(*(_QWORD *)(Vc + 304) + 20LL) = *((_DWORD *)i + 8);
    *(_DWORD *)(*(_QWORD *)(Vc + 304) + 80LL) = 1;
    *(_DWORD *)(*(_QWORD *)(Vc + 304) + 24LL) = *(_DWORD *)(v1 + 48);
    *(_DWORD *)(*(_QWORD *)(Vc + 304) + 32LL) = *(_DWORD *)(v1 + 60);
    v26 = *(_DWORD *)(v1 + 56);
    if ( v26 )
      *(_DWORD *)(*(_QWORD *)(Vc + 304) + 28LL) = v26;
    else
      *(_DWORD *)(*(_QWORD *)(Vc + 304) + 28LL) = *(_DWORD *)(*((_QWORD *)v6 + 9) + 56LL);
    if ( (unsigned __int8)InsertVcInTable(Vc) )
    {
      v27 = (NDIS_HANDLE *)(Vc + 40);
      v28 = (NDIS_HANDLE *)P;
      *(_QWORD *)(v1 + 24) = *(_QWORD *)(Vc + 280);
      if ( NdisCoCreateVc(v28[4], *(NDIS_HANDLE *)(v16 + 24), *(NDIS_HANDLE *)(Vc + 280), (PNDIS_HANDLE)(Vc + 40)) )
      {
        RemoveVcFromTable(Vc);
        PxFreeVc((PVOID)Vc);
        v10 = -1073668094;
      }
      else
      {
        v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64, _DWORD, __int64 *))(v16 + 112))(
                Vc,
                *((unsigned int *)v6 + 13),
                *((unsigned int *)i + 8),
                1,
                v1,
                *(_DWORD *)(v39 + 40),
                &v38);
        if ( v29 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, v29);
          NdisCoDeleteVc(*v27);
          RemoveVcFromTable(Vc);
          PxFreeVc((PVOID)Vc);
          v10 = -1073668082;
        }
        else
        {
          *(_BYTE *)(Vc + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(Vc + 512));
          InsertVcInClAfList(Vc);
          v30 = v38;
          *(_DWORD *)(Vc + 32) |= 1u;
          ++*(_DWORD *)(Vc + 28);
          *(_QWORD *)(Vc + 312) = v30;
          *(_DWORD *)(Vc + 20) = *(_DWORD *)(Vc + 16);
          *(_DWORD *)(Vc + 16) = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_qDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
              Vc,
              512,
              0,
              *(_DWORD *)(*(_QWORD *)(Vc + 304) + 32LL));
          v31 = *(_QWORD *)(Vc + 256);
          Src[2] = 2;
          Src[3] = 512;
          Src[4] = 0;
          v32 = *(_QWORD *)(v31 + 40);
          Src[1] = *(_QWORD *)(Vc + 272);
          v33 = *(_QWORD *)(Vc + 304);
          Src[0] = v32;
          Src[5] = *(unsigned int *)(v33 + 32);
          v34 = *(_BYTE *)(Vc + 520);
          *(_QWORD *)(Vc + 292) = 512;
          KeReleaseSpinLock((PKSPIN_LOCK)(Vc + 512), v34);
          PxIndicateStatus(Src);
          v35 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(Vc + 512));
          *(_BYTE *)(Vc + 520) = v35;
          KeReleaseSpinLock((PKSPIN_LOCK)(Vc + 512), v35);
          v36 = NdisClMakeCall(*v27, *(PCO_CALL_PARAMETERS *)(Vc + 312), 0, 0);
          if ( v36 != 259 )
            PxClMakeCallComplete(v36, *(_QWORD *)(Vc + 280), 0, *(_QWORD *)(Vc + 312));
          v10 = 0;
        }
      }
      goto LABEL_24;
    }
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      goto LABEL_64;
    v24 = 18;
  }
  WPP_SF_(v23->AttachedDevice, v24, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
LABEL_64:
  PxFreeVc((PVOID)Vc);
LABEL_58:
  v10 = -1073668072;
LABEL_24:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, v10);
  v13 = KeAcquireSpinLockRaiseToDpc(v7);
  v6[128] = v13;
  if ( (*((_DWORD *)v6 + 4))-- == 1 )
  {
    KeReleaseSpinLock(v7, v13);
    FreeTapiLine(v6);
  }
  else
  {
    KeReleaseSpinLock(v7, v13);
  }
  return v10;
}

```

## disassembly

```asm
0x140013bc0  push    rbp
0x140013bc2  push    rbx
0x140013bc3  push    rsi
0x140013bc4  push    rdi
0x140013bc5  push    r12
0x140013bc7  push    r13
0x140013bc9  push    r14
0x140013bcb  push    r15
0x140013bcd  lea     rbp, [rsp-1Fh]
0x140013bd2  sub     rsp, 98h
0x140013bd9  mov     rax, cs:__security_cookie
0x140013be0  xor     rax, rsp
0x140013be3  mov     [rbp+57h+var_48], rax
0x140013be7  xor     r12d, r12d
0x140013bea  mov     [rbp+57h+var_80], rcx
0x140013bee  mov     [rbp+57h+P], r12
0x140013bf2  lea     r14, [rcx+30h]
0x140013bf6  mov     [rbp+57h+var_88], r12
0x140013bfa  mov     rbx, rcx
0x140013bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c04  lea     rsi, WPP_GLOBAL_Control
0x140013c0b  mov     r13b, 4
0x140013c0e  cmp     rcx, rsi
0x140013c11  jz      short loc_140013C2E
0x140013c13  cmp     [rcx+29h], r13b
0x140013c17  jb      short loc_140013C2E
0x140013c19  mov     rcx, [rcx+18h]
0x140013c1d  lea     edx, [r12+0Ah]
0x140013c22  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140013c29  call    WPP_SF_
0x140013c2e  mov     eax, [r14+24h]
0x140013c32  cmp     eax, 0E0h
0x140013c37  jb      loc_1400142D5
0x140013c3d  cmp     eax, [rbx+28h]
0x140013c40  jnb     loc_1400142D5
0x140013c46  mov     ecx, [r14+8]
0x140013c4a  lea     rdx, [rbp+57h+P]
0x140013c4e  call    IsTapiLineValid
0x140013c53  test    al, al
0x140013c55  jnz     short loc_140013C85
0x140013c57  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c5e  cmp     rcx, rsi
0x140013c61  jz      short loc_140013C7B
0x140013c63  cmp     byte ptr [rcx+29h], 3
0x140013c67  jb      short loc_140013C7B
0x140013c69  mov     r9, [r14+8]
0x140013c6d  mov     edx, 0Bh
0x140013c72  mov     rcx, [rcx+18h]
0x140013c76  call    WPP_SF_P
0x140013c7b  mov     eax, 1002h
0x140013c80  jmp     loc_1400142DA
0x140013c85  mov     rdi, [rbp+57h+P]
0x140013c89  lea     r15, [rdi+78h]
0x140013c8d  mov     rcx, r15; SpinLock
0x140013c90  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013c97  nop     dword ptr [rax+rax+00h]
0x140013c9c  mov     [rdi+80h], al
0x140013ca2  mov     rax, [rdi+50h]
0x140013ca6  mov     ecx, [rax+38h]
0x140013ca9  test    r13b, cl
0x140013cac  jnz     short loc_140013CF1
0x140013cae  mov     rcx, cs:WPP_GLOBAL_Control
0x140013cb5  cmp     rcx, rsi
0x140013cb8  jz      short loc_140013CD5
0x140013cba  cmp     byte ptr [rcx+29h], 5
0x140013cbe  jb      short loc_140013CD5
0x140013cc0  mov     rcx, [rcx+18h]
0x140013cc4  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140013ccb  mov     edx, 0Ch
0x140013cd0  call    WPP_SF_
0x140013cd5  mov     dl, [rdi+80h]; NewIrql
0x140013cdb  mov     rcx, r15; SpinLock
0x140013cde  call    cs:__imp_KeReleaseSpinLock
0x140013ce5  nop     dword ptr [rax+rax+00h]
0x140013cea  mov     ebx, 1003h
0x140013cef  jmp     short loc_140013D61
0x140013cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x140013cf8  cmp     rcx, rsi
0x140013cfb  jz      short loc_140013D1D
0x140013cfd  cmp     [rcx+29h], r13b
0x140013d01  jb      short loc_140013D1D
0x140013d03  mov     rax, [r14+8]
0x140013d07  mov     edx, 0Dh
0x140013d0c  mov     rcx, [rcx+18h]
0x140013d10  mov     r9, rdi
0x140013d13  mov     [rsp+0D0h+var_B0], rax
0x140013d18  call    WPP_SF_qP
0x140013d1d  cmp     dword ptr [r14+44h], 1
0x140013d22  jnz     loc_140013DCF
0x140013d28  mov     eax, [r14+48h]
0x140013d2c  cmp     eax, [rdi+58h]
0x140013d2f  jnb     short loc_140013D47
0x140013d31  lfence
0x140013d34  mov     ecx, eax
0x140013d36  mov     rax, [rdi+70h]
0x140013d3a  mov     rsi, [rax+rcx*8]
0x140013d3e  test    rsi, rsi
0x140013d41  jnz     loc_140013DF5
0x140013d47  mov     dl, [rdi+80h]; NewIrql
0x140013d4d  mov     rcx, r15; SpinLock
0x140013d50  mov     ebx, 1002h
0x140013d55  call    cs:__imp_KeReleaseSpinLock
0x140013d5c  nop     dword ptr [rax+rax+00h]
0x140013d61  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d68  lea     rax, WPP_GLOBAL_Control
0x140013d6f  cmp     rcx, rax
0x140013d72  jz      short loc_140013D92
0x140013d74  cmp     byte ptr [rcx+29h], 5
0x140013d78  jb      short loc_140013D92
0x140013d7a  mov     rcx, [rcx+18h]
0x140013d7e  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140013d85  mov     edx, 15h
0x140013d8a  mov     r9d, ebx
0x140013d8d  call    WPP_SF_d
0x140013d92  mov     rcx, r15; SpinLock
0x140013d95  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013d9c  nop     dword ptr [rax+rax+00h]
0x140013da1  mov     [rdi+80h], al
0x140013da7  mov     dl, al; NewIrql
0x140013da9  add     dword ptr [rdi+10h], 0FFFFFFFFh
0x140013dad  mov     rcx, r15; SpinLock
0x140013db0  jnz     loc_1400142C5
0x140013db6  call    cs:__imp_KeReleaseSpinLock
0x140013dbd  nop     dword ptr [rax+rax+00h]
0x140013dc2  mov     rcx, rdi; P
0x140013dc5  call    FreeTapiLine
0x140013dca  jmp     loc_1400142D1
0x140013dcf  lea     rdx, [rdi+60h]
0x140013dd3  mov     rsi, [rdx]
0x140013dd6  jmp     short loc_140013DEB
0x140013dd8  mov     rax, [rsi+28h]
0x140013ddc  mov     ecx, [rax+54h]
0x140013ddf  cmp     [rsi+24h], ecx
0x140013de2  jb      loc_140013D3E
0x140013de8  mov     rsi, [rsi]
0x140013deb  cmp     rsi, rdx
0x140013dee  jnz     short loc_140013DD8
0x140013df0  jmp     loc_140013D47
0x140013df5  mov     rax, [rdi+18h]
0x140013df9  mov     ecx, [r14+24h]
0x140013dfd  mov     r13, [rdi+38h]
0x140013e01  mov     rax, [rax+18h]
0x140013e05  mov     [rbp+57h+P], rax
0x140013e09  lea     r9, [rcx+r14]
0x140013e0d  cmp     dword ptr [rax+0ACh], 0Ch
0x140013e14  jnz     short loc_140013E8E
0x140013e16  test    r9, r9
0x140013e19  jz      short loc_140013E65
0x140013e1b  mov     eax, [rbx+28h]
0x140013e1e  sub     eax, ecx
0x140013e20  mov     ecx, eax
0x140013e22  cmp     rcx, 7FFFFFFFh
0x140013e29  ja      short loc_140013E46
0x140013e2b  mov     rax, r9
0x140013e2e  test    rcx, rcx
0x140013e31  jz      short loc_140013E46
0x140013e33  cmp     [rax], r12b
0x140013e36  jz      short loc_140013E41
0x140013e38  inc     rax
0x140013e3b  sub     rcx, 1
0x140013e3f  jnz     short loc_140013E33
0x140013e41  test    rcx, rcx
0x140013e44  jnz     short loc_140013E65
0x140013e46  mov     dl, [rdi+80h]; NewIrql
0x140013e4c  mov     rcx, r15; SpinLock
0x140013e4f  call    cs:__imp_KeReleaseSpinLock
0x140013e56  nop     dword ptr [rax+rax+00h]
0x140013e5b  mov     ebx, 0C0012019h
0x140013e60  jmp     loc_140013D61
0x140013e65  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e6c  lea     rax, WPP_GLOBAL_Control
0x140013e73  cmp     rcx, rax
0x140013e76  jz      short loc_140013EDB
0x140013e78  cmp     byte ptr [rcx+29h], 4
0x140013e7c  jb      short loc_140013EDB
0x140013e7e  mov     rcx, [rcx+18h]
0x140013e82  mov     [rsp+0D0h+var_B0], r9
0x140013e87  call    WPP_SF_qs
0x140013e8c  jmp     short loc_140013EDB
0x140013e8e  test    r9, r9
0x140013e91  jz      short loc_140013EB4
0x140013e93  mov     eax, [rbx+28h]
0x140013e96  sub     eax, ecx
0x140013e98  mov     ecx, eax
0x140013e9a  mov     rax, r9
0x140013e9d  shr     rcx, 1
0x140013ea0  jz      short loc_140013E46
0x140013ea2  cmp     [rax], r12w
0x140013ea6  jz      short loc_140013EB4
0x140013ea8  add     rax, 2
0x140013eac  sub     rcx, 1
0x140013eb0  jnz     short loc_140013EA2
0x140013eb2  jmp     short loc_140013E46
0x140013eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ebb  lea     rax, WPP_GLOBAL_Control
0x140013ec2  cmp     rcx, rax
0x140013ec5  jz      short loc_140013EDB
0x140013ec7  cmp     byte ptr [rcx+29h], 4
0x140013ecb  jb      short loc_140013EDB
0x140013ecd  mov     rcx, [rcx+18h]
0x140013ed1  mov     [rsp+0D0h+var_B0], r9
0x140013ed6  call    WPP_SF_qS
0x140013edb  mov     dl, [rdi+80h]; NewIrql
0x140013ee1  mov     rcx, r15; SpinLock
0x140013ee4  call    cs:__imp_KeReleaseSpinLock
0x140013eeb  nop     dword ptr [rax+rax+00h]
0x140013ef0  lea     r12, [r13+0B8h]
0x140013ef7  mov     rcx, r12; SpinLock
0x140013efa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013f01  nop     dword ptr [rax+rax+00h]
0x140013f06  mov     rcx, r13
0x140013f09  mov     [r13+0C0h], al
0x140013f10  call    PxAllocateVc
0x140013f15  mov     rbx, rax
0x140013f18  test    rax, rax
0x140013f1b  jnz     short loc_140013F69
0x140013f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f24  lea     rax, WPP_GLOBAL_Control
0x140013f2b  cmp     rcx, rax
0x140013f2e  jz      short loc_140013F49
0x140013f30  cmp     byte ptr [rcx+29h], 3
0x140013f34  jb      short loc_140013F49
0x140013f36  mov     rcx, [rcx+18h]
0x140013f3a  lea     edx, [rbx+10h]
0x140013f3d  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140013f44  call    WPP_SF_
0x140013f49  mov     dl, [r13+0C0h]; NewIrql
0x140013f50  mov     rcx, r12; SpinLock
0x140013f53  call    cs:__imp_KeReleaseSpinLock
0x140013f5a  nop     dword ptr [rax+rax+00h]
0x140013f5f  mov     ebx, 0C0012018h
0x140013f64  jmp     loc_140013D61
0x140013f69  mov     dl, [r13+0C0h]; NewIrql
0x140013f70  mov     rcx, r12; SpinLock
0x140013f73  call    cs:__imp_KeReleaseSpinLock
0x140013f7a  nop     dword ptr [rax+rax+00h]
0x140013f7f  xor     edx, edx
0x140013f81  mov     rcx, rbx
0x140013f84  call    AllocateTapiCallInfo
0x140013f89  test    eax, eax
0x140013f8b  jz      short loc_140013FC5
0x140013f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f94  lea     rax, WPP_GLOBAL_Control
0x140013f9b  cmp     rcx, rax
0x140013f9e  jz      short loc_140013FBB
0x140013fa0  cmp     byte ptr [rcx+29h], 3
0x140013fa4  jb      short loc_140013FBB
0x140013fa6  mov     edx, 11h
0x140013fab  mov     rcx, [rcx+18h]
0x140013faf  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140013fb6  call    WPP_SF_
0x140013fbb  mov     rcx, rbx; Entry
0x140013fbe  call    PxFreeVc
0x140013fc3  jmp     short loc_140013F5F
0x140013fc5  mov     [rbx+100h], rdi
0x140013fcc  mov     [rbx+108h], rsi
0x140013fd3  lock inc dword ptr [rsi+24h]
0x140013fd7  mov     rax, [rdi+50h]
0x140013fdb  lock inc dword ptr [rax+14h]
0x140013fdf  mov     rax, [r14+10h]
0x140013fe3  mov     rcx, [rbx+130h]
0x140013fea  mov     [rbx+110h], rax
0x140013ff1  mov     eax, [rdi+34h]
0x140013ff4  mov     [rcx+10h], eax
0x140013ff7  mov     rcx, [rbx+130h]
0x140013ffe  mov     eax, [rsi+20h]
0x140014001  mov     [rcx+14h], eax
0x140014004  mov     rax, [rbx+130h]
0x14001400b  mov     dword ptr [rax+50h], 1
0x140014012  mov     rcx, [rbx+130h]
0x140014019  mov     eax, [r14+30h]
0x14001401d  mov     [rcx+18h], eax
0x140014020  mov     rcx, [rbx+130h]
0x140014027  mov     eax, [r14+3Ch]
0x14001402b  mov     [rcx+20h], eax
0x14001402e  mov     ecx, [r14+38h]
0x140014032  test    ecx, ecx
0x140014034  jnz     short loc_140014049
0x140014036  mov     rax, [rdi+48h]
0x14001403a  mov     rcx, [rbx+130h]
0x140014041  mov     eax, [rax+38h]
0x140014044  mov     [rcx+1Ch], eax
0x140014047  jmp     short loc_140014053
0x140014049  mov     rax, [rbx+130h]
0x140014050  mov     [rax+1Ch], ecx
0x140014053  mov     rcx, rbx
0x140014056  call    InsertVcInTable
0x14001405b  test    al, al
0x14001405d  jnz     short loc_14001408A
0x14001405f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014066  lea     rax, WPP_GLOBAL_Control
0x14001406d  cmp     rcx, rax
0x140014070  jz      loc_140013FBB
0x140014076  cmp     byte ptr [rcx+29h], 3
0x14001407a  jb      loc_140013FBB
0x140014080  mov     edx, 12h
0x140014085  jmp     loc_140013FAB
0x14001408a  mov     rax, [rbx+118h]
0x140014091  lea     r12, [rbx+28h]
0x140014095  mov     rcx, [rbp+57h+P]
  ... truncated ...
```
