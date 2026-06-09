# PxClIncomingCall

- ea: `0x14000f830`
- end: `0x14000fba0`
- name: `PxClIncomingCall`
- size: `880`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140001c0c`
- `0x140001c60`
- `0x140001cd0`
- `0x140001d54`
- `0x140006e08`
- `0x140007040`
- `0x140007d84`
- `0x140007fc0`
- `0x140008000`
- `0x14000f830`
- `0x1400156d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f964`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fa97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fb49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f964`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fa97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fb49`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fa7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fb31`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fb70`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fa7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fb31`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fb70`
- `NDIS!NdisSetTimer` at `0x14000f9fb`
- `NDIS!NdisSetTimer` at `0x14000f9fb`

## pseudocode

```c
__int64 __fastcall PxClIncomingCall(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v6; // rsi
  char *v7; // rbx
  unsigned int v9; // esi
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rax
  KIRQL v14; // dl
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  KIRQL v20; // al
  PVOID Entry; // [rsp+40h] [rbp-40h] BYREF
  __int64 Src; // [rsp+48h] [rbp-38h] BYREF
  __int64 v24; // [rsp+50h] [rbp-30h]
  __int64 v25; // [rsp+58h] [rbp-28h]
  __int64 v26; // [rsp+60h] [rbp-20h]
  __int64 v27; // [rsp+68h] [rbp-18h]
  __int64 v28; // [rsp+70h] [rbp-10h]

  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a1, a2);
  if ( *(_DWORD *)(a1 + 16) != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
        a1,
        *(_DWORD *)(a1 + 16));
    return 3221225473LL;
  }
  v6 = *(_QWORD *)(a1 + 32);
  GetVcFromCtx(a2, &Entry);
  v7 = (char *)Entry;
  if ( !Entry )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned int)((_DWORD)Entry + 33),
        WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
        a2);
    return 3221225473LL;
  }
  v9 = (*(__int64 (__fastcall **)(PVOID, __int64))(v6 + 120))(Entry, a3);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a2);
    return v9;
  }
  else
  {
    v7[520] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 64);
    *((_QWORD *)v7 + 34) = _InterlockedExchangeAdd((_DWORD *)&WPP_MAIN_CB.Dpc.DpcData + 1, 2u);
    *((_DWORD *)v7 + 7) += 2;
    *((_DWORD *)v7 + 5) = *((_DWORD *)v7 + 4);
    *((_DWORD *)v7 + 4) = 2;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qLqLL(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        v11,
        v7,
        *((_DWORD *)v7 + 8),
        *((_QWORD *)v7 + 5),
        *((_DWORD *)v7 + 73),
        *((_DWORD *)v7 + 74));
    v12 = *((_DWORD *)v7 + 8);
    if ( (v12 & 4) == 0 )
    {
      ++*((_DWORD *)v7 + 7);
      *((_DWORD *)v7 + 8) = v12 | 4;
      NdisSetTimer((PNDIS_TIMER)(v7 + 320), 0xEA60u);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qPPD(WPP_GLOBAL_Control->AttachedDevice, v10, v11, v7, *((_QWORD *)v7 + 35), *((_QWORD *)v7 + 34));
    v13 = *((_QWORD *)v7 + 32);
    v14 = v7[520];
    v25 = 500;
    v28 = 0;
    v15 = *(_QWORD *)(v13 + 40);
    v16 = *((_QWORD *)v7 + 35);
    Src = v15;
    v24 = *((_QWORD *)v7 + 34);
    v27 = v24;
    v26 = v16;
    KeReleaseSpinLock((PKSPIN_LOCK)v7 + 64, v14);
    PxIndicateStatus(&Src);
    v7[520] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 64);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
        v7,
        2,
        0,
        *(_DWORD *)(*((_QWORD *)v7 + 38) + 32LL));
    v17 = *((_QWORD *)v7 + 32);
    v25 = 2;
    v26 = 2;
    v27 = 0;
    v18 = *(_QWORD *)(v17 + 40);
    v19 = *((_QWORD *)v7 + 34);
    Src = v18;
    v24 = v19;
    v28 = *(unsigned int *)(*((_QWORD *)v7 + 38) + 32LL);
    *(_QWORD *)(v7 + 292) = 2;
    KeReleaseSpinLock((PKSPIN_LOCK)v7 + 64, v7[520]);
    PxIndicateStatus(&Src);
    v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 64);
    v7[520] = v20;
    if ( (*((_DWORD *)v7 + 7))-- == 1 )
      DoDerefVcWork(v7);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v7 + 64, v20);
    return 259;
  }
}

```

## disassembly

```asm
0x14000f830  push    rbp
0x14000f832  push    rbx
0x14000f833  push    rsi
0x14000f834  push    rdi
0x14000f835  push    r13
0x14000f837  push    r14
0x14000f839  push    r15
0x14000f83b  mov     rbp, rsp
0x14000f83e  sub     rsp, 80h
0x14000f845  mov     rax, cs:__security_cookie
0x14000f84c  xor     rax, rsp
0x14000f84f  mov     [rbp+var_8], rax
0x14000f853  mov     r14, r8
0x14000f856  mov     [rbp+Entry], 0
0x14000f85e  mov     rdi, rdx
0x14000f861  mov     rbx, rcx
0x14000f864  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f86b  lea     r15, WPP_GLOBAL_Control
0x14000f872  lea     r13, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f879  cmp     rcx, r15
0x14000f87c  jz      short loc_14000F89D
0x14000f87e  cmp     byte ptr [rcx+29h], 5
0x14000f882  jb      short loc_14000F89D
0x14000f884  mov     rcx, [rcx+18h]
0x14000f888  mov     edx, 1Fh
0x14000f88d  mov     r9, rbx
0x14000f890  mov     [rsp+80h+var_60], rdi
0x14000f895  mov     r8, r13
0x14000f898  call    WPP_SF_qq
0x14000f89d  mov     eax, [rbx+10h]
0x14000f8a0  cmp     eax, 3
0x14000f8a3  jz      short loc_14000F8D1
0x14000f8a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8ac  cmp     rcx, r15
0x14000f8af  jz      short loc_14000F90E
0x14000f8b1  cmp     byte ptr [rcx+29h], 3
0x14000f8b5  jb      short loc_14000F90E
0x14000f8b7  mov     rcx, [rcx+18h]
0x14000f8bb  mov     edx, 20h ; ' '
0x14000f8c0  mov     r9, rbx
0x14000f8c3  mov     dword ptr [rsp+80h+var_60], eax
0x14000f8c7  mov     r8, r13
0x14000f8ca  call    WPP_SF_qD
0x14000f8cf  jmp     short loc_14000F90E
0x14000f8d1  mov     rsi, [rbx+20h]
0x14000f8d5  lea     rdx, [rbp+Entry]
0x14000f8d9  mov     rcx, rdi
0x14000f8dc  call    GetVcFromCtx
0x14000f8e1  mov     rbx, [rbp+Entry]
0x14000f8e5  test    rbx, rbx
0x14000f8e8  jnz     short loc_14000F918
0x14000f8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8f1  cmp     rcx, r15
0x14000f8f4  jz      short loc_14000F90E
0x14000f8f6  cmp     byte ptr [rcx+29h], 3
0x14000f8fa  jb      short loc_14000F90E
0x14000f8fc  mov     rcx, [rcx+18h]
0x14000f900  lea     edx, [rbx+21h]
0x14000f903  mov     r9, rdi
0x14000f906  mov     r8, r13
0x14000f909  call    WPP_SF_q
0x14000f90e  mov     eax, 0C0000001h
0x14000f913  jmp     loc_14000FB81
0x14000f918  mov     rax, [rsi+78h]
0x14000f91c  mov     rdx, r14
0x14000f91f  mov     rcx, rbx
0x14000f922  call    _guard_dispatch_icall
0x14000f927  mov     esi, eax
0x14000f929  test    eax, eax
0x14000f92b  jz      short loc_14000F95A
0x14000f92d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f934  cmp     rcx, r15
0x14000f937  jz      short loc_14000F953
0x14000f939  cmp     byte ptr [rcx+29h], 3
0x14000f93d  jb      short loc_14000F953
0x14000f93f  mov     rcx, [rcx+18h]
0x14000f943  mov     edx, 22h ; '"'
0x14000f948  mov     r9, rdi
0x14000f94b  mov     r8, r13
0x14000f94e  call    WPP_SF_q
0x14000f953  mov     eax, esi
0x14000f955  jmp     loc_14000FB81
0x14000f95a  lea     rdi, [rbx+200h]
0x14000f961  mov     rcx, rdi; SpinLock
0x14000f964  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f96b  nop     dword ptr [rax+rax+00h]
0x14000f970  mov     esi, 2
0x14000f975  mov     [rbx+208h], al
0x14000f97b  mov     eax, esi
0x14000f97d  lock xadd dword ptr cs:WPP_MAIN_CB.Dpc.DpcData+4, eax
0x14000f985  cdqe
0x14000f987  mov     [rbx+110h], rax
0x14000f98e  add     [rbx+1Ch], esi
0x14000f991  mov     eax, [rbx+10h]
0x14000f994  mov     [rbx+14h], eax
0x14000f997  mov     [rbx+10h], esi
0x14000f99a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9a1  cmp     rcx, r15
0x14000f9a4  jz      short loc_14000F9DF
0x14000f9a6  cmp     byte ptr [rcx+29h], 5
0x14000f9aa  jb      short loc_14000F9DF
0x14000f9ac  mov     eax, [rbx+128h]
0x14000f9b2  lea     edx, [rsi+1Fh]
0x14000f9b5  mov     rcx, [rcx+18h]
0x14000f9b9  mov     r9, rbx
0x14000f9bc  mov     [rsp+80h+var_48], eax
0x14000f9c0  mov     eax, [rbx+124h]
0x14000f9c6  mov     [rsp+80h+var_50], eax
0x14000f9ca  mov     rax, [rbx+28h]
0x14000f9ce  mov     [rsp+80h+var_58], rax
0x14000f9d3  mov     eax, [rbx+20h]
0x14000f9d6  mov     dword ptr [rsp+80h+var_60], eax
0x14000f9da  call    WPP_SF_qLqLL
0x14000f9df  mov     eax, [rbx+20h]
0x14000f9e2  test    al, 4
0x14000f9e4  jnz     short loc_14000FA07
0x14000f9e6  inc     dword ptr [rbx+1Ch]
0x14000f9e9  lea     rcx, [rbx+140h]; Timer
0x14000f9f0  or      eax, 4
0x14000f9f3  mov     edx, 0EA60h; MillisecondsToDelay
0x14000f9f8  mov     [rbx+20h], eax
0x14000f9fb  call    cs:__imp_NdisSetTimer
0x14000fa02  nop     dword ptr [rax+rax+00h]
0x14000fa07  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa0e  cmp     rcx, r15
0x14000fa11  jz      short loc_14000FA3D
0x14000fa13  cmp     byte ptr [rcx+29h], 5
0x14000fa17  jb      short loc_14000FA3D
0x14000fa19  mov     rax, [rbx+110h]
0x14000fa20  mov     r9, rbx
0x14000fa23  mov     rcx, [rcx+18h]
0x14000fa27  mov     [rsp+80h+var_58], rax
0x14000fa2c  mov     rax, [rbx+118h]
0x14000fa33  mov     [rsp+80h+var_60], rax
0x14000fa38  call    WPP_SF_qPPD
0x14000fa3d  mov     rax, [rbx+100h]
0x14000fa44  mov     dl, [rbx+208h]; NewIrql
0x14000fa4a  mov     [rbp+var_28], 1F4h
0x14000fa52  mov     [rbp+var_10], 0
0x14000fa5a  mov     rcx, [rax+28h]
0x14000fa5e  mov     rax, [rbx+118h]
0x14000fa65  mov     [rbp+Src], rcx
0x14000fa69  mov     rcx, [rbx+110h]
0x14000fa70  mov     [rbp+var_30], rcx
0x14000fa74  mov     [rbp+var_18], rcx
0x14000fa78  mov     rcx, rdi; SpinLock
0x14000fa7b  mov     [rbp+var_20], rax
0x14000fa7f  call    cs:__imp_KeReleaseSpinLock
0x14000fa86  nop     dword ptr [rax+rax+00h]
0x14000fa8b  lea     rcx, [rbp+Src]; Src
0x14000fa8f  call    PxIndicateStatus
0x14000fa94  mov     rcx, rdi; SpinLock
0x14000fa97  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fa9e  nop     dword ptr [rax+rax+00h]
0x14000faa3  mov     [rbx+208h], al
0x14000faa9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fab0  cmp     rcx, r15
0x14000fab3  jz      short loc_14000FAE9
0x14000fab5  cmp     byte ptr [rcx+29h], 5
0x14000fab9  jb      short loc_14000FAE9
0x14000fabb  mov     rax, [rbx+130h]
0x14000fac2  mov     edx, 24h ; '$'
0x14000fac7  mov     rcx, [rcx+18h]
0x14000facb  mov     r9, rbx
0x14000face  mov     r8, r13
0x14000fad1  mov     eax, [rax+20h]
0x14000fad4  mov     [rsp+80h+var_50], eax
0x14000fad8  mov     dword ptr [rsp+80h+var_58], 0
0x14000fae0  mov     dword ptr [rsp+80h+var_60], esi
0x14000fae4  call    WPP_SF_qDDD
0x14000fae9  mov     rax, [rbx+100h]
0x14000faf0  mov     [rbp+var_28], rsi
0x14000faf4  mov     [rbp+var_20], rsi
0x14000faf8  mov     [rbp+var_18], 0
0x14000fb00  mov     rcx, [rax+28h]
0x14000fb04  mov     rax, [rbx+110h]
0x14000fb0b  mov     [rbp+Src], rcx
0x14000fb0f  mov     [rbp+var_30], rax
0x14000fb13  mov     rax, [rbx+130h]
0x14000fb1a  mov     ecx, [rax+20h]
0x14000fb1d  mov     [rbp+var_10], rcx
0x14000fb21  mov     rcx, rdi; SpinLock
0x14000fb24  mov     [rbx+124h], rsi
0x14000fb2b  mov     dl, [rbx+208h]; NewIrql
0x14000fb31  call    cs:__imp_KeReleaseSpinLock
0x14000fb38  nop     dword ptr [rax+rax+00h]
0x14000fb3d  lea     rcx, [rbp+Src]; Src
0x14000fb41  call    PxIndicateStatus
0x14000fb46  mov     rcx, rdi; SpinLock
0x14000fb49  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fb50  nop     dword ptr [rax+rax+00h]
0x14000fb55  mov     [rbx+208h], al
0x14000fb5b  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x14000fb5f  jnz     short loc_14000FB6B
0x14000fb61  mov     rcx, rbx; Entry
0x14000fb64  call    DoDerefVcWork
0x14000fb69  jmp     short loc_14000FB7C
0x14000fb6b  mov     dl, al; NewIrql
0x14000fb6d  mov     rcx, rdi; SpinLock
0x14000fb70  call    cs:__imp_KeReleaseSpinLock
0x14000fb77  nop     dword ptr [rax+rax+00h]
0x14000fb7c  mov     eax, 103h
0x14000fb81  mov     rcx, [rbp+var_8]
0x14000fb85  xor     rcx, rsp; StackCookie
0x14000fb88  call    __security_check_cookie
0x14000fb8d  add     rsp, 80h
0x14000fb94  pop     r15
0x14000fb96  pop     r14
0x14000fb98  pop     r13
0x14000fb9a  pop     rdi
0x14000fb9b  pop     rsi
0x14000fb9c  pop     rbx
0x14000fb9d  pop     rbp
0x14000fb9e  retn
```
