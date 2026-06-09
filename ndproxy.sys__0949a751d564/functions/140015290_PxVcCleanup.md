# PxVcCleanup

- ea: `0x140015290`
- end: `0x1400155dd`
- name: `PxVcCleanup`
- size: `845`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `7`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400011b0`
- `0x140003940`
- `0x140004760`
- `0x14000fbb0`
- `0x140011ab0`
- `0x140012040`
- `0x1400166e0`

## callees

- `0x140007040`
- `0x140007254`
- `0x140007488`
- `0x1400074f4`
- `0x140007fc0`
- `0x140010924`
- `0x140010a14`
- `0x140015290`
- `0x140016380`
- `0x140016450`
- `0x1400167a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400153cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015487`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001551b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400153cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015487`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001551b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400153b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001545c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015502`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400153b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001545c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015502`
- `NDIS!NdisClIncomingCallComplete` at `0x140015478`
- `NDIS!NdisClIncomingCallComplete` at `0x140015478`

## pseudocode

```c
__int64 __fastcall PxVcCleanup(__int64 a1, int a2, __int64 a3)
{
  int v3; // ebx
  __int64 v5; // r8
  unsigned int v6; // esi
  int v7; // eax
  _QWORD *v8; // rcx
  _QWORD *v9; // rdx
  int v10; // eax
  int v11; // ecx
  KIRQL v12; // al
  int v13; // ecx
  KIRQL v14; // dl
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  KIRQL v18; // al
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  __int64 v21; // rdx
  _QWORD Src[6]; // [rsp+40h] [rbp-48h] BYREF

  v3 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qLLLL(
      WPP_GLOBAL_Control->AttachedDevice,
      157,
      a3,
      a1,
      *(_DWORD *)(a1 + 16),
      *(_DWORD *)(a1 + 24),
      a2,
      *(_DWORD *)(a1 + 32));
  v5 = *(unsigned int *)(a1 + 16);
  switch ( (_DWORD)v5 )
  {
    case 0:
      v6 = 0;
      goto LABEL_32;
    case 1:
      *(_DWORD *)(a1 + 20) = 1;
      *(_DWORD *)(a1 + 32) |= v3 | 0x88;
      *(_DWORD *)(a1 + 16) = 3;
      PxCloseCallWithCm(a1);
      goto LABEL_30;
    case 2:
      if ( (v3 & 0x10) != 0 )
      {
        v8 = *(_QWORD **)(a1 + 104);
        if ( *v8 != a1 + 96 )
          goto LABEL_36;
        v9 = (_QWORD *)v8[1];
        if ( (_QWORD *)*v9 != v8 )
          goto LABEL_36;
        *(_QWORD *)(a1 + 104) = v9;
        v3 &= ~0x10u;
        *v9 = a1 + 96;
      }
      v10 = *(_DWORD *)(a1 + 16);
      *(_DWORD *)(a1 + 32) |= v3 | 0x20;
      v11 = *(_DWORD *)(a1 + 32);
      *(_DWORD *)(a1 + 20) = v10;
      *(_DWORD *)(a1 + 16) = (v11 & 8) != 0 ? 3 : 0;
      if ( (v11 & 4) != 0 )
        PxStopIncomingCallTimeout(a1);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 512), *(_BYTE *)(a1 + 520));
      NdisClIncomingCallComplete(-1073741823, *(NDIS_HANDLE *)(a1 + 40), *(PCO_CALL_PARAMETERS *)(a1 + 312));
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 512));
      v13 = *(_DWORD *)(a1 + 32);
      v14 = v12;
      *(_BYTE *)(a1 + 520) = v12;
      if ( (v13 & 8) != 0 )
      {
        PxCloseCallWithCm(a1);
      }
      else
      {
        v15 = *(_QWORD *)(a1 + 256);
        Src[2] = 2;
        Src[3] = 0x4000;
        Src[4] = 0;
        v16 = *(_QWORD *)(v15 + 40);
        v17 = *(_QWORD *)(a1 + 272);
        Src[0] = v16;
        Src[1] = v17;
        Src[5] = *(unsigned int *)(*(_QWORD *)(a1 + 304) + 32LL);
        *(_QWORD *)(a1 + 292) = 0x4000;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 512), v14);
        PxIndicateStatus(Src);
        v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 512));
        --*(_DWORD *)(a1 + 28);
        *(_BYTE *)(a1 + 520) = v18;
      }
      v6 = 0;
      goto LABEL_16;
    case 3:
      *(_DWORD *)(a1 + 32) |= v3;
LABEL_30:
      v6 = 259;
      goto LABEL_16;
  }
  if ( (_DWORD)v5 != 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_qLL(WPP_GLOBAL_Control->AttachedDevice, 158, v5, a1, v5, *(_DWORD *)(a1 + 292));
    v6 = -1073741823;
LABEL_32:
    if ( (v3 & 0x10) == 0 )
      goto LABEL_16;
    v19 = *(_QWORD **)(a1 + 104);
    if ( *v19 == a1 + 96 )
    {
      v20 = (_QWORD *)v19[1];
      if ( (_QWORD *)*v20 == v19 )
      {
        *(_QWORD *)(a1 + 104) = v20;
        *v20 = a1 + 96;
        goto LABEL_16;
      }
    }
LABEL_36:
    __fastfail(3u);
  }
  v7 = *(_DWORD *)(a1 + 32);
  v6 = 259;
  if ( (v7 & 0x10) == 0 )
  {
    *(_DWORD *)(a1 + 20) = v5;
    *(_DWORD *)(a1 + 16) = 3;
    *(_DWORD *)(a1 + 32) = v3 | v7 | 8;
    if ( (unsigned int)PxCloseCallWithCl(a1) != 259 )
      PxCloseCallWithCm(a1);
  }
LABEL_16:
  if ( *(_DWORD *)(a1 + 248) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 512), *(_BYTE *)(a1 + 520));
    PxStopDigitReporting(a1);
    *(_BYTE *)(a1 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 512));
    *(_DWORD *)(a1 + 248) = 0;
  }
  else
  {
    v21 = *(_QWORD *)(a1 + 112);
    if ( v21 )
    {
      *(_QWORD *)(a1 + 112) = 0;
      PxTerminateDigitDetection(a1, v21, 16);
    }
  }
  RemoveVcFromClAfList(a1);
  return v6;
}

```

## disassembly

```asm
0x140015290  mov     [rsp+arg_8], rbx
0x140015295  mov     [rsp+arg_10], rsi
0x14001529a  push    rdi
0x14001529b  sub     rsp, 80h
0x1400152a2  mov     rax, cs:__security_cookie
0x1400152a9  xor     rax, rsp
0x1400152ac  mov     [rsp+88h+var_18], rax
0x1400152b1  mov     ebx, edx
0x1400152b3  mov     rdi, rcx
0x1400152b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400152bd  lea     rsi, WPP_GLOBAL_Control
0x1400152c4  cmp     rcx, rsi
0x1400152c7  jz      short loc_1400152F9
0x1400152c9  cmp     byte ptr [rcx+29h], 5
0x1400152cd  jb      short loc_1400152F9
0x1400152cf  mov     eax, [rdi+20h]
0x1400152d2  mov     edx, 9Dh
0x1400152d7  mov     rcx, [rcx+18h]
0x1400152db  mov     r9, rdi
0x1400152de  mov     [rsp+88h+var_50], eax
0x1400152e2  mov     eax, [rdi+18h]
0x1400152e5  mov     [rsp+88h+var_58], ebx
0x1400152e9  mov     [rsp+88h+var_60], eax
0x1400152ed  mov     eax, [rdi+10h]
0x1400152f0  mov     [rsp+88h+var_68], eax
0x1400152f4  call    WPP_SF_qLLLL
0x1400152f9  mov     r8d, [rdi+10h]
0x1400152fd  mov     ecx, r8d
0x140015300  test    r8d, r8d
0x140015303  jz      loc_14001555D
0x140015309  sub     ecx, 1
0x14001530c  jz      loc_140015537
0x140015312  sub     ecx, 1
0x140015315  jz      loc_1400153F5
0x14001531b  sub     ecx, 1
0x14001531e  jz      loc_1400153ED
0x140015324  cmp     ecx, 1
0x140015327  jz      short loc_140015365
0x140015329  mov     rcx, cs:WPP_GLOBAL_Control
0x140015330  cmp     rcx, rsi
0x140015333  jz      short loc_14001535B
0x140015335  cmp     byte ptr [rcx+29h], 1
0x140015339  jb      short loc_14001535B
0x14001533b  mov     eax, [rdi+124h]
0x140015341  mov     edx, 9Eh
0x140015346  mov     rcx, [rcx+18h]
0x14001534a  mov     r9, rdi
0x14001534d  mov     [rsp+88h+var_60], eax
0x140015351  mov     [rsp+88h+var_68], r8d
0x140015356  call    WPP_SF_qLL
0x14001535b  mov     esi, 0C0000001h
0x140015360  jmp     loc_14001555F
0x140015365  mov     eax, [rdi+20h]
0x140015368  mov     esi, 103h
0x14001536d  test    al, 10h
0x14001536f  jnz     short loc_140015398
0x140015371  or      eax, ebx
0x140015373  mov     [rdi+14h], r8d
0x140015377  or      eax, 8
0x14001537a  mov     dword ptr [rdi+10h], 3
0x140015381  mov     rcx, rdi
0x140015384  mov     [rdi+20h], eax
0x140015387  call    PxCloseCallWithCl
0x14001538c  cmp     eax, esi
0x14001538e  jz      short loc_140015398
0x140015390  mov     rcx, rdi
0x140015393  call    PxCloseCallWithCm
0x140015398  cmp     dword ptr [rdi+0F8h], 0
0x14001539f  jz      loc_140015591
0x1400153a5  mov     dl, [rdi+208h]; NewIrql
0x1400153ab  lea     rbx, [rdi+200h]
0x1400153b2  mov     rcx, rbx; SpinLock
0x1400153b5  call    cs:__imp_KeReleaseSpinLock
0x1400153bc  nop     dword ptr [rax+rax+00h]
0x1400153c1  mov     rcx, rdi
0x1400153c4  call    PxStopDigitReporting
0x1400153c9  mov     rcx, rbx; SpinLock
0x1400153cc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400153d3  nop     dword ptr [rax+rax+00h]
0x1400153d8  mov     [rdi+208h], al
0x1400153de  mov     dword ptr [rdi+0F8h], 0
0x1400153e8  jmp     loc_1400155B0
0x1400153ed  or      [rdi+20h], ebx
0x1400153f0  jmp     loc_140015553
0x1400153f5  test    bl, 10h
0x1400153f8  jz      short loc_140015422
0x1400153fa  lea     rax, [rdi+60h]
0x1400153fe  mov     rcx, [rax+8]
0x140015402  cmp     [rcx], rax
0x140015405  jnz     loc_14001558A
0x14001540b  mov     rdx, [rcx+8]
0x14001540f  cmp     [rdx], rcx
0x140015412  jnz     loc_14001558A
0x140015418  mov     [rax+8], rdx
0x14001541c  and     ebx, 0FFFFFFEFh
0x14001541f  mov     [rdx], rax
0x140015422  mov     eax, [rdi+10h]
0x140015425  or      ebx, 20h
0x140015428  or      [rdi+20h], ebx
0x14001542b  mov     ecx, [rdi+20h]
0x14001542e  mov     [rdi+14h], eax
0x140015431  mov     eax, ecx
0x140015433  and     al, 8
0x140015435  neg     al
0x140015437  sbb     eax, eax
0x140015439  and     eax, 3
0x14001543c  mov     [rdi+10h], eax
0x14001543f  test    cl, 4
0x140015442  jz      short loc_14001544C
0x140015444  mov     rcx, rdi
0x140015447  call    PxStopIncomingCallTimeout
0x14001544c  mov     dl, [rdi+208h]; NewIrql
0x140015452  lea     rbx, [rdi+200h]
0x140015459  mov     rcx, rbx; SpinLock
0x14001545c  call    cs:__imp_KeReleaseSpinLock
0x140015463  nop     dword ptr [rax+rax+00h]
0x140015468  mov     r8, [rdi+138h]; CallParameters
0x14001546f  mov     ecx, 0C0000001h; Status
0x140015474  mov     rdx, [rdi+28h]; NdisVcHandle
0x140015478  call    cs:__imp_NdisClIncomingCallComplete
0x14001547f  nop     dword ptr [rax+rax+00h]
0x140015484  mov     rcx, rbx; SpinLock
0x140015487  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001548e  nop     dword ptr [rax+rax+00h]
0x140015493  mov     ecx, [rdi+20h]
0x140015496  mov     dl, al; NewIrql
0x140015498  mov     [rdi+208h], al
0x14001549e  test    cl, 8
0x1400154a1  jz      short loc_1400154B0
0x1400154a3  mov     rcx, rdi
0x1400154a6  call    PxCloseCallWithCm
0x1400154ab  jmp     loc_140015530
0x1400154b0  mov     rax, [rdi+100h]
0x1400154b7  mov     r8d, 4000h
0x1400154bd  mov     [rsp+88h+var_38], 2
0x1400154c6  mov     [rsp+88h+var_30], r8
0x1400154cb  mov     [rsp+88h+var_28], 0
0x1400154d4  mov     rcx, [rax+28h]
0x1400154d8  mov     rax, [rdi+110h]
0x1400154df  mov     [rsp+88h+Src], rcx
0x1400154e4  mov     [rsp+88h+var_40], rax
0x1400154e9  mov     rax, [rdi+130h]
0x1400154f0  mov     ecx, [rax+20h]
0x1400154f3  mov     [rsp+88h+var_20], rcx
0x1400154f8  mov     rcx, rbx; SpinLock
0x1400154fb  mov     [rdi+124h], r8
0x140015502  call    cs:__imp_KeReleaseSpinLock
0x140015509  nop     dword ptr [rax+rax+00h]
0x14001550e  lea     rcx, [rsp+88h+Src]; Src
0x140015513  call    PxIndicateStatus
0x140015518  mov     rcx, rbx; SpinLock
0x14001551b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015522  nop     dword ptr [rax+rax+00h]
0x140015527  dec     dword ptr [rdi+1Ch]
0x14001552a  mov     [rdi+208h], al
0x140015530  xor     esi, esi
0x140015532  jmp     loc_140015398
0x140015537  or      ebx, 88h
0x14001553d  mov     [rdi+14h], r8d
0x140015541  or      [rdi+20h], ebx
0x140015544  mov     rcx, rdi
0x140015547  mov     dword ptr [rdi+10h], 3
0x14001554e  call    PxCloseCallWithCm
0x140015553  mov     esi, 103h
0x140015558  jmp     loc_140015398
0x14001555d  xor     esi, esi
0x14001555f  test    bl, 10h
0x140015562  jz      loc_140015398
0x140015568  lea     rax, [rdi+60h]
0x14001556c  mov     rcx, [rax+8]
0x140015570  cmp     [rcx], rax
0x140015573  jnz     short loc_14001558A
0x140015575  mov     rdx, [rcx+8]
0x140015579  cmp     [rdx], rcx
0x14001557c  jnz     short loc_14001558A
0x14001557e  mov     [rax+8], rdx
0x140015582  mov     [rdx], rax
0x140015585  jmp     loc_140015398
0x14001558a  mov     ecx, 3
0x14001558f  int     29h; Win8: RtlFailFast(ecx)
0x140015591  mov     rdx, [rdi+70h]
0x140015595  test    rdx, rdx
0x140015598  jz      short loc_1400155B0
0x14001559a  mov     r8d, 10h
0x1400155a0  mov     qword ptr [rdi+70h], 0
0x1400155a8  mov     rcx, rdi
0x1400155ab  call    PxTerminateDigitDetection
0x1400155b0  mov     rcx, rdi
0x1400155b3  call    RemoveVcFromClAfList
0x1400155b8  mov     eax, esi
0x1400155ba  mov     rcx, [rsp+88h+var_18]
0x1400155bf  xor     rcx, rsp; StackCookie
0x1400155c2  call    __security_check_cookie
0x1400155c7  lea     r11, [rsp+88h+var_8]
0x1400155cf  mov     rbx, [r11+18h]
0x1400155d3  mov     rsi, [r11+20h]
0x1400155d7  mov     rsp, r11
0x1400155da  pop     rdi
0x1400155db  retn
```
