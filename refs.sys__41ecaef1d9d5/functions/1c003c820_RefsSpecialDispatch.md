# RefsSpecialDispatch

- ea: `0x1c003c820`
- end: `0x1c003cabc`
- name: `RefsSpecialDispatch`
- size: `668`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0014110`
- `0x1c003c820`
- `0x1c003cac4`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c016154c`
- `0x1c016d3c4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c003c9e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c003c9e9`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c006bf9a`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c006bf9a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c003c908`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c003c908`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c003c86e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c003c86e`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c003ca24`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c003ca24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c003ca78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c003ca78`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c003c8bc`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c003c8bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003ca37`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003ca37`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003ca63`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c003ca63`

## pseudocode

```c
void __fastcall RefsSpecialDispatch(__int64 a1)
{
  __int64 v2; // rsi
  void (__fastcall *v3)(__int64, __int64); // r15
  __int64 v4; // r12
  _OWORD *v5; // rax
  _QWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  KIRQL v13; // al
  __int64 v14; // [rsp+50h] [rbp-78h]
  _OWORD v15[2]; // [rsp+68h] [rbp-60h] BYREF
  __int64 v16; // [rsp+88h] [rbp-40h]
  _QWORD v17[3]; // [rsp+90h] [rbp-38h] BYREF

  memset(v15, 0, sizeof(v15));
  v16 = 0;
  memset(v17, 0, sizeof(v17));
  KeEnterCriticalRegion();
  do
  {
    v2 = *(_QWORD *)(a1 + 64);
    v3 = *(void (__fastcall **)(__int64, __int64))(a1 + 144);
    v4 = *(_QWORD *)(a1 + 72);
    *(_QWORD *)(a1 + 144) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    v5 = *(_OWORD **)(a1 + 80);
    if ( v5 )
    {
      *(_OWORD *)&v17[1] = *v5;
      v6 = &v17[1];
    }
    else
    {
      v6 = 0;
    }
    v17[0] = v6;
    v14 = IoSetActivityIdThread(v6);
    *(_QWORD *)(a1 + 120) = a1 + 112;
    *(_QWORD *)(a1 + 112) = a1 + 112;
    LOBYTE(v7) = 1;
    LOBYTE(v8) = 1;
    v9 = RefsInitializeTopLevelIrp(v15, v8, v7);
    v10 = *(_QWORD *)(v9 + 32);
    if ( !v10 )
    {
      *(_DWORD *)(v9 + 4) = 1397140410;
      *(_QWORD *)(v9 + 32) = a1;
      *(_DWORD *)(a1 + 8) |= 0x100000u;
      IoSetTopLevelIrp((PIRP)v9);
      v10 = *(_QWORD *)(v9 + 32);
    }
    *(_QWORD *)(a1 + 104) = v10;
    *(_DWORD *)(a1 + 8) |= 0x10000u;
    if ( a1 )
      RefsPreRequestProcessingExtend(a1);
    v3(a1, v4);
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(0);
    RefsExtendedCompleteRequestInternal(a1, 0, 0);
    *(_DWORD *)(a1 + 8) &= ~0x10000u;
    LOBYTE(v11) = 1;
    if ( *(int *)(a1 + 4) >= 0 )
      RefsAcquireExclusiveVcb(a1, v2, v11, v12);
    else
      RefsAcquireSharedVcb(a1, v2, v11, v12);
    _InterlockedDecrement((volatile signed __int32 *)(v2 + 228));
    _InterlockedDecrement((volatile signed __int32 *)(v2 + 220));
    if ( *(int *)(a1 + 4) >= 0 )
      RefsReleaseVcbCheckDelete(a1, v2);
    else
      ExReleaseResourceLite((PERESOURCE)(v2 + 1424));
    RefsCleanupIrpContext(a1, 1);
    IoClearActivityIdThread(v14);
    v13 = KeAcquireSpinLockRaiseToDpc(&RefsScavengerLock);
    a1 = RefsScavengerWorkList;
    if ( RefsScavengerWorkList )
      RefsScavengerWorkList = *(_QWORD *)(RefsScavengerWorkList + 112);
    else
      RefsScavengerRunning = 0;
    KeReleaseSpinLock(&RefsScavengerLock, v13);
  }
  while ( a1 );
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1c003c820  mov     r11, rsp
0x1c003c823  mov     [r11+10h], rbx
0x1c003c827  mov     [r11+18h], rsi
0x1c003c82b  push    r12
0x1c003c82d  push    r14
0x1c003c82f  push    r15
0x1c003c831  sub     rsp, 0B0h
0x1c003c838  mov     rax, cs:__security_cookie
0x1c003c83f  xor     rax, rsp
0x1c003c842  mov     [rsp+0C8h+var_20], rax
0x1c003c84a  mov     rbx, rcx
0x1c003c84d  mov     [rsp+0C8h+var_A0], rcx
0x1c003c852  xorps   xmm0, xmm0
0x1c003c855  xor     eax, eax
0x1c003c857  movups  [rsp+0C8h+var_60], xmm0
0x1c003c85c  movups  [rsp+0C8h+var_50], xmm0
0x1c003c861  mov     [r11-40h], rax
0x1c003c865  movups  xmmword ptr [r11-38h], xmm0
0x1c003c86a  mov     [r11-28h], rax
0x1c003c86e  call    cs:__imp_KeEnterCriticalRegion
0x1c003c875  nop     dword ptr [rax+rax+00h]
0x1c003c87a  mov     rsi, [rbx+40h]
0x1c003c87e  mov     [rsp+0C8h+var_90], rsi
0x1c003c883  mov     r15, [rbx+90h]
0x1c003c88a  mov     [rsp+0C8h+var_88], r15
0x1c003c88f  mov     r12, [rbx+48h]
0x1c003c893  mov     [rsp+0C8h+var_80], r12
0x1c003c898  and     qword ptr [rbx+90h], 0
0x1c003c8a0  and     qword ptr [rbx+48h], 0
0x1c003c8a5  mov     rax, [rbx+50h]
0x1c003c8a9  test    rax, rax
0x1c003c8ac  jnz     loc_1C00816D2
0x1c003c8b2  xor     ecx, ecx
0x1c003c8b4  mov     [rsp+0C8h+var_38], rcx
0x1c003c8bc  call    cs:__imp_IoSetActivityIdThread
0x1c003c8c3  nop     dword ptr [rax+rax+00h]
0x1c003c8c8  mov     [rsp+0C8h+var_78], rax
0x1c003c8cd  lea     rax, [rbx+70h]
0x1c003c8d1  mov     [rax+8], rax
0x1c003c8d5  mov     [rax], rax
0x1c003c8d8  mov     r8b, 1
0x1c003c8db  mov     dl, r8b
0x1c003c8de  lea     rcx, [rsp+0C8h+var_60]
0x1c003c8e3  call    RefsInitializeTopLevelIrp
0x1c003c8e8  mov     r14, rax
0x1c003c8eb  mov     rax, [rax+20h]
0x1c003c8ef  test    rax, rax
0x1c003c8f2  jnz     short loc_1C003C918
0x1c003c8f4  mov     dword ptr [r14+4], 5346ABBAh
0x1c003c8fc  mov     [r14+20h], rbx
0x1c003c900  bts     dword ptr [rbx+8], 14h
0x1c003c905  mov     rcx, r14; Irp
0x1c003c908  call    cs:__imp_IoSetTopLevelIrp
0x1c003c90f  nop     dword ptr [rax+rax+00h]
0x1c003c914  mov     rax, [r14+20h]
0x1c003c918  mov     [rbx+68h], rax
0x1c003c91c  bts     dword ptr [rbx+8], 10h
0x1c003c921  mov     [rsp+0C8h+var_A8], 0
0x1c003c926  test    rbx, rbx
0x1c003c929  jz      short loc_1C003C933
0x1c003c92b  mov     rcx, rbx
0x1c003c92e  call    RefsPreRequestProcessingExtend
0x1c003c933  mov     rdx, r12
0x1c003c936  mov     rcx, rbx
0x1c003c939  mov     rax, r15
0x1c003c93c  call    cs:__guard_dispatch_icall_fptr
0x1c003c942  mov     al, cs:RefsStatusDebugEnabled
0x1c003c948  test    al, al
0x1c003c94a  jz      short loc_1C003C960
0x1c003c94c  mov     r8d, 447h
0x1c003c952  lea     rdx, aFspdispC; "FspDisp.c"
0x1c003c959  xor     ecx, ecx; Status
0x1c003c95b  call    RefsStatusDebug
0x1c003c960  xor     r8d, r8d
0x1c003c963  xor     edx, edx
0x1c003c965  mov     rcx, rbx
0x1c003c968  call    RefsExtendedCompleteRequestInternal
0x1c003c96d  jmp     short loc_1C003C9AA
0x1c003c96f  mov     r8d, eax
0x1c003c972  xor     edx, edx
0x1c003c974  mov     rbx, [rsp+0C8h+var_A0]
0x1c003c979  mov     rcx, rbx
0x1c003c97c  call    RefsProcessException
0x1c003c981  cmp     eax, 0C00000D8h
0x1c003c986  jz      short loc_1C003C996
0x1c003c988  cmp     eax, 0C00001A8h
0x1c003c98d  jz      short loc_1C003C996
0x1c003c98f  cmp     eax, 0C0000188h
0x1c003c994  jnz     short loc_1C003C99B
0x1c003c996  mov     [rsp+0C8h+var_A8], 1
0x1c003c99b  mov     rsi, [rsp+0C8h+var_90]
0x1c003c9a0  mov     r15, [rsp+0C8h+var_88]
0x1c003c9a5  mov     r12, [rsp+0C8h+var_80]
0x1c003c9aa  cmp     [rsp+0C8h+var_A8], 0
0x1c003c9af  jnz     loc_1C003C921
0x1c003c9b5  btr     dword ptr [rbx+8], 10h
0x1c003c9ba  mov     r8b, 1
0x1c003c9bd  mov     rdx, rsi
0x1c003c9c0  mov     rcx, rbx
0x1c003c9c3  cmp     dword ptr [rbx+4], 0
0x1c003c9c7  jge     short loc_1C003CA04
0x1c003c9c9  call    RefsAcquireSharedVcb
0x1c003c9ce  lock dec dword ptr [rsi+0E4h]
0x1c003c9d5  lock dec dword ptr [rsi+0DCh]
0x1c003c9dc  cmp     dword ptr [rbx+4], 0
0x1c003c9e0  jge     short loc_1C003C9F7
0x1c003c9e2  lea     rcx, [rsi+590h]; Resource
0x1c003c9e9  call    cs:__imp_ExReleaseResourceLite
0x1c003c9f0  nop     dword ptr [rax+rax+00h]
0x1c003c9f5  jmp     short loc_1C003CA0B
0x1c003c9f7  mov     rdx, rsi
0x1c003c9fa  mov     rcx, rbx
0x1c003c9fd  call    RefsReleaseVcbCheckDelete
0x1c003ca02  jmp     short loc_1C003CA0B
0x1c003ca04  call    RefsAcquireExclusiveVcb
0x1c003ca09  jmp     short loc_1C003C9CE
0x1c003ca0b  jmp     short loc_1C003CA12
0x1c003ca0d  mov     rbx, [rsp+0C8h+var_A0]
0x1c003ca12  mov     edx, 1
0x1c003ca17  mov     rcx, rbx
0x1c003ca1a  call    RefsCleanupIrpContext
0x1c003ca1f  mov     rcx, [rsp+0C8h+var_78]
0x1c003ca24  call    cs:__imp_IoClearActivityIdThread
0x1c003ca2b  nop     dword ptr [rax+rax+00h]
0x1c003ca30  lea     rcx, RefsScavengerLock; SpinLock
0x1c003ca37  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c003ca3e  nop     dword ptr [rax+rax+00h]
0x1c003ca43  mov     rbx, cs:RefsScavengerWorkList
0x1c003ca4a  mov     [rsp+0C8h+var_A0], rbx
0x1c003ca4f  test    rbx, rbx
0x1c003ca52  jnz     short loc_1C003CAAF
0x1c003ca54  mov     cs:RefsScavengerRunning, bl
0x1c003ca5a  mov     dl, al; NewIrql
0x1c003ca5c  lea     rcx, RefsScavengerLock; SpinLock
0x1c003ca63  call    cs:__imp_KeReleaseSpinLock
0x1c003ca6a  nop     dword ptr [rax+rax+00h]
0x1c003ca6f  test    rbx, rbx
0x1c003ca72  jnz     loc_1C003C87A
0x1c003ca78  call    cs:__imp_KeLeaveCriticalRegion
0x1c003ca7f  nop     dword ptr [rax+rax+00h]
0x1c003ca84  mov     rcx, [rsp+0C8h+var_20]
0x1c003ca8c  xor     rcx, rsp; StackCookie
0x1c003ca8f  call    __security_check_cookie
0x1c003ca94  lea     r11, [rsp+0C8h+var_18]
0x1c003ca9c  mov     rbx, [r11+28h]
0x1c003caa0  mov     rsi, [r11+30h]
0x1c003caa4  mov     rsp, r11
0x1c003caa7  pop     r15
0x1c003caa9  pop     r14
0x1c003caab  pop     r12
0x1c003caad  retn
0x1c003caaf  mov     rcx, [rbx+70h]
0x1c003cab3  mov     cs:RefsScavengerWorkList, rcx
0x1c003caba  jmp     short loc_1C003CA5A
0x1c006bf64  push    rbp
0x1c006bf66  sub     rsp, 20h
0x1c006bf6a  mov     rbp, rdx
0x1c006bf6d  mov     [rbp+58h], rcx
0x1c006bf71  mov     rdx, rcx
0x1c006bf74  mov     rcx, [rbp+28h]
0x1c006bf78  call    RefsExceptionFilter
0x1c006bf7d  nop
0x1c006bf7e  add     rsp, 20h
0x1c006bf82  pop     rbp
0x1c006bf83  retn
0x1c006bf85  push    rbp
0x1c006bf87  sub     rsp, 20h
0x1c006bf8b  mov     rbp, rdx
0x1c006bf8e  mov     [rbp+60h], rcx
0x1c006bf92  mov     rax, [rcx]
0x1c006bf95  mov     ecx, [rax]; Exception
0x1c006bf97  mov     [rbp+30h], ecx
0x1c006bf9a  call    cs:__imp_FsRtlIsNtstatusExpected
0x1c006bfa1  nop     dword ptr [rax+rax+00h]
0x1c006bfa6  xor     ecx, ecx
0x1c006bfa8  test    al, al
0x1c006bfaa  setnz   cl
0x1c006bfad  mov     eax, ecx
0x1c006bfaf  add     rsp, 20h
0x1c006bfb3  pop     rbp
0x1c006bfb4  retn
0x1c00816d2  movups  xmm0, xmmword ptr [rax]
0x1c00816d5  movdqu  [rsp+0C8h+var_30], xmm0
0x1c00816de  lea     rcx, [rsp+0C8h+var_30]
0x1c00816e6  jmp     loc_1C003C8B4
```
