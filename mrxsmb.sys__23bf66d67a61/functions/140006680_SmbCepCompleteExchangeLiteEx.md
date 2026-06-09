# SmbCepCompleteExchangeLiteEx

- ea: `0x140006680`
- end: `0x140006b9b`
- name: `SmbCepCompleteExchangeLiteEx`
- size: `1307`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `14`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140002270`
- `0x140004b90`
- `0x140006150`
- `0x140006660`
- `0x140006ec0`
- `0x1400099d0`
- `0x14000a100`
- `0x14000a260`
- `0x14000c270`
- `0x14000c720`
- `0x14000e020`
- `0x14000ea90`
- `0x140012190`
- `0x140013cb0`

## callees

- `0x140004360`
- `0x140004938`
- `0x140006680`
- `0x14000d910`
- `0x140014370`
- `0x14001ad60`
- `0x14001c050`
- `0x140024f30`
- `0x140038008`
- `0x140038068`
- `0x1400383d0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400066da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006817`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006892`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400066da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006817`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006892`
- `ntoskrnl!KeSetEvent` at `0x140006b06`
- `ntoskrnl!KeSetEvent` at `0x140006b06`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006735`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006836`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006735`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006836`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068e6`
- `ntoskrnl!KeBugCheckEx` at `0x140006b38`
- `ntoskrnl!KeBugCheckEx` at `0x140006b38`
- `HAL!KeQueryPerformanceCounter` at `0x1400066c4`
- `HAL!KeQueryPerformanceCounter` at `0x1400066c4`
- `rdbss!RxRemoveIoFromTurboCache` at `0x140006790`
- `rdbss!RxRemoveIoFromTurboCache` at `0x140006790`
- `rdbss!RxPostToWorkerThread` at `0x140006ace`
- `rdbss!RxPostToWorkerThread` at `0x140006b7b`
- `rdbss!RxPostToWorkerThread` at `0x140006ace`
- `rdbss!RxPostToWorkerThread` at `0x140006b7b`

## pseudocode

```c
__int64 __fastcall SmbCepCompleteExchangeLiteEx(char *pContext, char *a2)
{
  int v2; // r14d
  LARGE_INTEGER *v3; // r15
  char v4; // r12
  __int64 v5; // rsi
  LARGE_INTEGER PerformanceCounter; // rbx
  KIRQL v8; // al
  __int64 v9; // r9
  LARGE_INTEGER v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rsi
  KIRQL v14; // al
  __int64 v15; // rbp
  KIRQL v16; // dl
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rbx
  int v20; // eax
  _QWORD *v21; // r8
  __int64 v22; // r10
  _QWORD *v23; // r9
  __int64 v24; // rcx
  char *v25; // rcx
  ULONG_PTR v26; // rcx
  unsigned int v27; // ebx
  ULONG_PTR v28; // rcx
  __int64 v29; // rax
  char v30; // al
  struct _RDBSS_DEVICE_OBJECT *v31; // rsi

  v2 = *((_DWORD *)pContext + 17);
  v3 = (LARGE_INTEGER *)(pContext + 512);
  v4 = (char)a2;
  v5 = *((_QWORD *)pContext + 6);
  if ( byte_14007D25F && pContext[1011] == 1 )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v3[50].QuadPart);
    v9 = BYTE6(v3[62].QuadPart);
    if ( (unsigned __int8)v9 < 0x2Au && (_BYTE)v9 != 19 )
    {
      v10 = v3[46];
      if ( PerformanceCounter.QuadPart > v10.QuadPart )
        _InterlockedAdd64((volatile signed __int64 *)&v3[v9 + 2], PerformanceCounter.QuadPart - v10.QuadPart);
      _InterlockedIncrement16((volatile signed __int16 *)&v3[51].QuadPart + v9 + 2);
    }
    BYTE6(v3[62].QuadPart) = 19;
    v3[46] = PerformanceCounter;
    KeReleaseSpinLock((PKSPIN_LOCK)&v3[50].QuadPart, v8);
    if ( byte_1400712C4 < 0 )
      McTemplateK0t_EtwWriteTransfer(v11, Smb2PerfWorkTransition, v3, 19);
  }
  if ( (*((_DWORD *)pContext + 17) & 0x40000) == 0 || (v2 & 1) != 0 )
    v4 = 0;
  if ( (*((_DWORD *)pContext + 17) & 0x2000000) != 0 )
  {
    if ( !v5 )
      goto LABEL_25;
    if ( !*(_QWORD *)(v5 + 40) )
    {
      if ( (unsigned __int8)RxRemoveIoFromTurboCache(v5)
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_d39beb3e593835eae73483c3886eb046_Traceguids, v5, pContext);
      }
      _InterlockedAnd((volatile signed __int32 *)pContext + 17, 0xFDFFFFFF);
    }
  }
  else if ( !v5 )
  {
    goto LABEL_25;
  }
  if ( (*((_DWORD *)pContext + 17) & 0x400) == 0 )
    SmbCeClearExchangeCancelRoutine(v5, pContext);
LABEL_25:
  v12 = pContext + 144;
  if ( (_QWORD *)*v12 != v12 )
  {
    v13 = *((_QWORD *)pContext + 15);
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 128));
    v15 = *((_QWORD *)pContext + 15);
    v16 = v14;
    if ( v13 != v15 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 128), v14);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
          pContext,
          v13,
          *((_QWORD *)pContext + 15));
      }
      v13 = v15;
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v15 + 128));
      v12 = pContext + 144;
    }
    if ( *((_QWORD *)pContext + 15) != v13 )
      __int2c();
    v17 = *v12;
    if ( *(_QWORD **)(*v12 + 8LL) != v12 || (v18 = (_QWORD *)v12[1], (_QWORD *)*v18 != v12) )
LABEL_66:
      __fastfail(3u);
    *v18 = v17;
    *(_QWORD *)(v17 + 8) = v18;
    v12[1] = v12;
    *v12 = v12;
    *((_QWORD *)pContext + 15) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 128), v16);
  }
  *((_DWORD *)pContext + 10) = 7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_d39beb3e593835eae73483c3886eb046_Traceguids, pContext);
  }
  v19 = *((_QWORD *)pContext + 7);
  if ( v19 )
  {
    SmbCseUnchainCompoundedBufferContextsLite(*((_QWORD *)pContext + 7));
    a2 = (char *)*((_QWORD *)pContext + 20);
    if ( a2 != pContext + 160 )
    {
      a2 -= 8;
      while ( a2 )
      {
        v20 = *((_DWORD *)a2 + 1);
        if ( (v20 & 0x40) != 0 )
        {
          v21 = a2 + 64;
          *((_DWORD *)a2 + 1) = v20 & 0xFFFFFF3F;
          v22 = *((_QWORD *)a2 + 8);
          if ( *(char **)(v22 + 8) != a2 + 64 )
            goto LABEL_66;
          v23 = (_QWORD *)*((_QWORD *)a2 + 9);
          if ( (_QWORD *)*v23 != v21 )
            goto LABEL_66;
          v24 = *(_QWORD *)(*((_QWORD *)a2 + 7) + 56LL);
          *v23 = v22;
          *(_QWORD *)(v22 + 8) = v23;
          --*(_DWORD *)(v24 + 64);
          *((_QWORD *)a2 + 9) = v21;
          *v21 = v21;
        }
        v25 = (char *)*((_QWORD *)a2 + 1);
        a2 = 0;
        if ( v25 != pContext + 160 )
          a2 = v25 - 8;
      }
    }
    if ( *(_DWORD *)(v19 + 20) == 3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_2ecbbf7dc68f37694aaad8a30b991413_Traceguids, v19);
      }
      _InterlockedAnd((volatile signed __int32 *)(v19 + 68), 0xFFFFFE7D);
      *(_DWORD *)(v19 + 28) = 0;
      *(_QWORD *)(v19 + 20) = 0;
      *(_QWORD *)(v19 + 72) = 0;
      *(_OWORD *)(v19 + 80) = 0;
      v26 = *(_QWORD *)(v19 + 96);
      if ( v26 )
      {
        SmbCeDereferenceBindingObject(v26);
        *(_QWORD *)(v19 + 96) = 0;
      }
    }
  }
  v27 = 0;
  v28 = _InterlockedExchange64((volatile __int64 *)pContext + 12, 0);
  if ( v28 )
    SmbCeDereferenceBindingObject(v28);
  if ( (*((_DWORD *)pContext + 17) & 0x10) != 0
    || (*((_DWORD *)pContext + 17) & 0x20) != 0
    || (v29 = *(_QWORD *)(*((_QWORD *)pContext + 9) + 56LL)) == 0
    || (v27 = (*(__int64 (__fastcall **)(char *))(v29 + 904))(pContext), v27 != -1069481983) )
  {
    if ( v4 )
    {
      return (unsigned int)-1073741802;
    }
    else if ( (*((_DWORD *)pContext + 17) & 1) != 0 )
    {
      KeSetEvent((PRKEVENT)(pContext + 176), 0, 0);
    }
    else
    {
      v31 = *(struct _RDBSS_DEVICE_OBJECT **)(*((_QWORD *)pContext + 9) + 24LL);
      LOBYTE(a2) = 20;
      RDR_PERF_ENTER(v3, a2);
      SmbCeIncrementTeardownOpCounter(v31, pContext, 7);
      RxPostToWorkerThread(
        v31,
        NormalWorkQueue,
        (PRX_WORK_QUEUE_ITEM)pContext + 6,
        SmbCepFinalizeExchangeWorker,
        pContext);
    }
  }
  else
  {
    if ( (*((_DWORD *)pContext + 17) & 0x10000) != 0 )
    {
      v30 = 1;
      _InterlockedAnd((volatile signed __int32 *)pContext + 17, 0xFFFEFFFF);
    }
    else
    {
      v30 = 0;
    }
    if ( *((_DWORD *)pContext + 11) <= 3u || v30 )
    {
      RxPostToWorkerThread(
        *(PRDBSS_DEVICE_OBJECT *)(*((_QWORD *)pContext + 9) + 24LL),
        NormalWorkQueue,
        (PRX_WORK_QUEUE_ITEM)pContext + 6,
        SmbCepRestartExchangeWorker,
        pContext);
      return 259;
    }
    else
    {
      Smb2DelayRestartExchange(pContext);
      return 259;
    }
  }
  return v27;
}

```

## disassembly

```asm
0x140006680  push    rbx
0x140006682  push    rbp
0x140006683  push    rsi
0x140006684  push    rdi
0x140006685  push    r12
0x140006687  push    r13
0x140006689  push    r14
0x14000668b  push    r15
0x14000668d  sub     rsp, 38h
0x140006691  mov     r14d, [rcx+44h]
0x140006695  lea     r15, [rcx+200h]
0x14000669c  cmp     cs:byte_14007D25F, 0
0x1400066a3  movzx   r12d, dl
0x1400066a7  mov     rsi, [rcx+30h]
0x1400066ab  mov     rdi, rcx
0x1400066ae  jz      loc_14000675F
0x1400066b4  cmp     byte ptr [r15+1F3h], 1
0x1400066bc  jnz     loc_14000675F
0x1400066c2  xor     ecx, ecx; PerformanceFrequency
0x1400066c4  call    cs:__imp_KeQueryPerformanceCounter
0x1400066cb  nop     dword ptr [rax+rax+00h]
0x1400066d0  lea     rcx, [r15+190h]; SpinLock
0x1400066d7  mov     rbx, rax
0x1400066da  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400066e1  nop     dword ptr [rax+rax+00h]
0x1400066e6  movzx   r9d, byte ptr [r15+1F6h]
0x1400066ee  cmp     r9b, 2Ah ; '*'
0x1400066f2  jnb     short loc_14000671C
0x1400066f4  cmp     r9b, 13h
0x1400066f8  jz      short loc_14000671C
0x1400066fa  mov     rdx, [r15+170h]
0x140006701  cmp     rbx, rdx
0x140006704  jle     short loc_140006712
0x140006706  mov     r8, rbx
0x140006709  sub     r8, rdx
0x14000670c  lock add [r15+r9*8+10h], r8
0x140006712  lock inc word ptr [r15+r9*2+19Ch]
0x14000671c  movzx   edx, al; NewIrql
0x14000671f  mov     byte ptr [r15+1F6h], 13h
0x140006727  lea     rcx, [r15+190h]; SpinLock
0x14000672e  mov     [r15+170h], rbx
0x140006735  call    cs:__imp_KeReleaseSpinLock
0x14000673c  nop     dword ptr [rax+rax+00h]
0x140006741  cmp     cs:byte_1400712C4, 0
0x140006748  jge     short loc_14000675F
0x14000674a  mov     r9d, 13h
0x140006750  lea     rdx, Smb2PerfWorkTransition
0x140006757  mov     r8, r15
0x14000675a  call    McTemplateK0t_EtwWriteTransfer
0x14000675f  mov     eax, [rdi+44h]
0x140006762  bt      eax, 12h
0x140006766  jnb     short loc_14000676E
0x140006768  test    r14b, 1
0x14000676c  jz      short loc_140006771
0x14000676e  xor     r12b, r12b
0x140006771  mov     eax, [rdi+44h]
0x140006774  lea     rbp, WPP_GLOBAL_Control
0x14000677b  bt      eax, 19h
0x14000677f  jnb     short loc_1400067E0
0x140006781  test    rsi, rsi
0x140006784  jz      short loc_1400067F9
0x140006786  cmp     qword ptr [rsi+28h], 0
0x14000678b  jnz     short loc_1400067E5
0x14000678d  mov     rcx, rsi
0x140006790  call    cs:__imp_RxRemoveIoFromTurboCache
0x140006797  nop     dword ptr [rax+rax+00h]
0x14000679c  test    al, al
0x14000679e  jz      short loc_1400067D6
0x1400067a0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400067a7  cmp     rcx, rbp
0x1400067aa  jz      short loc_1400067D6
0x1400067ac  mov     eax, [rcx+2Ch]
0x1400067af  test    al, 10h
0x1400067b1  jz      short loc_1400067D6
0x1400067b3  cmp     byte ptr [rcx+29h], 4
0x1400067b7  jb      short loc_1400067D6
0x1400067b9  mov     rcx, [rcx+18h]
0x1400067bd  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x1400067c4  mov     edx, 1Dh
0x1400067c9  mov     [rsp+78h+pContext], rdi
0x1400067ce  mov     r9, rsi
0x1400067d1  call    WPP_SF_qq
0x1400067d6  lock and dword ptr [rdi+44h], 0FDFFFFFFh
0x1400067de  jmp     short loc_1400067E5
0x1400067e0  test    rsi, rsi
0x1400067e3  jz      short loc_1400067F9
0x1400067e5  mov     eax, [rdi+44h]
0x1400067e8  bt      eax, 0Ah
0x1400067ec  jb      short loc_1400067F9
0x1400067ee  mov     rdx, rdi
0x1400067f1  mov     rcx, rsi
0x1400067f4  call    SmbCeClearExchangeCancelRoutine
0x1400067f9  lea     rbx, [rdi+90h]
0x140006800  xor     r13d, r13d
0x140006803  cmp     [rbx], rbx
0x140006806  jz      loc_1400068F9
0x14000680c  mov     rsi, [rdi+78h]
0x140006810  lea     rcx, [rsi+80h]; SpinLock
0x140006817  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000681e  nop     dword ptr [rax+rax+00h]
0x140006823  mov     rbp, [rdi+78h]
0x140006827  movzx   edx, al; NewIrql
0x14000682a  cmp     rsi, rbp
0x14000682d  jz      short loc_1400068A8
0x14000682f  lea     rcx, [rsi+80h]; SpinLock
0x140006836  call    cs:__imp_KeReleaseSpinLock
0x14000683d  nop     dword ptr [rax+rax+00h]
0x140006842  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006849  lea     rax, WPP_GLOBAL_Control
0x140006850  cmp     rcx, rax
0x140006853  jz      short loc_140006888
0x140006855  mov     eax, [rcx+2Ch]
0x140006858  test    al, 1
0x14000685a  jz      short loc_140006888
0x14000685c  cmp     byte ptr [rcx+29h], 1
0x140006860  jb      short loc_140006888
0x140006862  mov     rax, [rdi+78h]
0x140006866  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x14000686d  mov     rcx, [rcx+18h]
0x140006871  mov     edx, 1Eh
0x140006876  mov     [rsp+78h+var_50], rax
0x14000687b  mov     r9, rdi
0x14000687e  mov     [rsp+78h+pContext], rsi
0x140006883  call    WPP_SF_qqq
0x140006888  lea     rcx, [rbp+80h]; SpinLock
0x14000688f  mov     rsi, rbp
0x140006892  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006899  nop     dword ptr [rax+rax+00h]
0x14000689e  movzx   edx, al; NewIrql
0x1400068a1  lea     rbx, [rdi+90h]
0x1400068a8  mov     rax, [rdi+78h]
0x1400068ac  cmp     rax, rsi
0x1400068af  jz      short loc_1400068B3
0x1400068b1  int     2Ch; Windows NT - assertion failure
0x1400068b3  mov     rax, [rbx]
0x1400068b6  cmp     [rax+8], rbx
0x1400068ba  jnz     loc_140006A89
0x1400068c0  mov     rcx, [rbx+8]
0x1400068c4  cmp     [rcx], rbx
0x1400068c7  jnz     loc_140006A89
0x1400068cd  mov     [rcx], rax
0x1400068d0  mov     [rax+8], rcx
0x1400068d4  lea     rcx, [rsi+80h]; SpinLock
0x1400068db  mov     [rbx+8], rbx
0x1400068df  mov     [rbx], rbx
0x1400068e2  mov     [rdi+78h], r13
0x1400068e6  call    cs:__imp_KeReleaseSpinLock
0x1400068ed  nop     dword ptr [rax+rax+00h]
0x1400068f2  lea     rbp, WPP_GLOBAL_Control
0x1400068f9  mov     dword ptr [rdi+28h], 7
0x140006900  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006907  cmp     rcx, rbp
0x14000690a  jz      short loc_140006931
0x14000690c  mov     eax, [rcx+2Ch]
0x14000690f  test    al, 10h
0x140006911  jz      short loc_140006931
0x140006913  cmp     byte ptr [rcx+29h], 4
0x140006917  jb      short loc_140006931
0x140006919  mov     rcx, [rcx+18h]
0x14000691d  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x140006924  mov     edx, 1Fh
0x140006929  mov     r9, rdi
0x14000692c  call    WPP_SF_q
0x140006931  mov     rbx, [rdi+38h]
0x140006935  test    rbx, rbx
0x140006938  jz      loc_140006A21
0x14000693e  mov     rcx, rbx
0x140006941  call    SmbCseUnchainCompoundedBufferContextsLite
0x140006946  lea     r11, [rdi+0A0h]
0x14000694d  mov     rdx, [r11]
0x140006950  cmp     rdx, r11
0x140006953  jz      short loc_1400069BD
0x140006955  add     rdx, 0FFFFFFFFFFFFFFF8h
0x140006959  jz      short loc_1400069BD
0x14000695b  nop     dword ptr [rax+rax+00h]
0x140006960  mov     eax, [rdx+4]
0x140006963  test    al, 40h
0x140006965  jz      short loc_1400069A6
0x140006967  and     eax, 0FFFFFF3Fh
0x14000696c  lea     r8, [rdx+40h]
0x140006970  mov     [rdx+4], eax
0x140006973  mov     r10, [r8]
0x140006976  cmp     [r10+8], r8
0x14000697a  jnz     loc_140006A89
0x140006980  mov     r9, [rdx+48h]
0x140006984  cmp     [r9], r8
0x140006987  jnz     loc_140006A89
0x14000698d  mov     rax, [rdx+38h]
0x140006991  mov     rcx, [rax+38h]
0x140006995  mov     [r9], r10
0x140006998  mov     [r10+8], r9
0x14000699c  dec     dword ptr [rcx+40h]
0x14000699f  mov     [rdx+48h], r8
0x1400069a3  mov     [r8], r8
0x1400069a6  mov     rcx, [rdx+8]
0x1400069aa  mov     rdx, r13
0x1400069ad  cmp     rcx, r11
0x1400069b0  lea     rax, [rcx-8]
0x1400069b4  cmovnz  rdx, rax
0x1400069b8  test    rdx, rdx
0x1400069bb  jnz     short loc_140006960
0x1400069bd  cmp     dword ptr [rbx+14h], 3
0x1400069c1  jnz     short loc_140006A21
0x1400069c3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400069ca  cmp     rcx, rbp
0x1400069cd  jz      short loc_1400069F4
0x1400069cf  mov     eax, [rcx+2Ch]
0x1400069d2  test    al, 20h
0x1400069d4  jz      short loc_1400069F4
0x1400069d6  cmp     byte ptr [rcx+29h], 2
0x1400069da  jb      short loc_1400069F4
0x1400069dc  mov     rcx, [rcx+18h]
0x1400069e0  lea     r8, WPP_2ecbbf7dc68f37694aaad8a30b991413_Traceguids
0x1400069e7  mov     edx, 11h
0x1400069ec  mov     r9, rbx
0x1400069ef  call    WPP_SF_q
0x1400069f4  lock and dword ptr [rbx+44h], 0FFFFFE7Dh
0x1400069fc  mov     [rbx+1Ch], r13d
0x140006a00  xorps   xmm0, xmm0
0x140006a03  mov     [rbx+14h], r13
0x140006a07  mov     [rbx+48h], r13
0x140006a0b  movups  xmmword ptr [rbx+50h], xmm0
0x140006a0f  mov     rcx, [rbx+60h]; BugCheckParameter2
0x140006a13  test    rcx, rcx
0x140006a16  jz      short loc_140006A21
0x140006a18  call    SmbCeDereferenceBindingObject
0x140006a1d  mov     [rbx+60h], r13
0x140006a21  mov     rcx, r13
0x140006a24  mov     ebx, r13d
0x140006a27  xchg    rcx, [rdi+60h]; BugCheckParameter2
0x140006a2b  test    rcx, rcx
0x140006a2e  jz      short loc_140006A35
0x140006a30  call    SmbCeDereferenceBindingObject
0x140006a35  mov     eax, [rdi+44h]
0x140006a38  test    al, 10h
0x140006a3a  jnz     loc_140006AE4
0x140006a40  mov     eax, [rdi+44h]
0x140006a43  test    al, 20h
0x140006a45  jnz     loc_140006AE4
0x140006a4b  mov     rax, [rdi+48h]
0x140006a4f  mov     rax, [rax+38h]
0x140006a53  test    rax, rax
0x140006a56  jz      loc_140006AE4
0x140006a5c  mov     rax, [rax+388h]
0x140006a63  mov     rcx, rdi
0x140006a66  call    _guard_dispatch_icall
0x140006a6b  mov     ebx, eax
0x140006a6d  cmp     eax, 0C0410001h
0x140006a72  jnz     short loc_140006AE4
0x140006a74  mov     eax, [rdi+44h]
0x140006a77  bt      eax, 10h
0x140006a7b  jnb     short loc_140006A90
0x140006a7d  mov     al, 1
0x140006a7f  lock and dword ptr [rdi+44h], 0FFFEFFFFh
0x140006a87  jmp     short loc_140006A92
0x140006a89  mov     ecx, 3
0x140006a8e  int     29h; Win8: RtlFailFast(ecx)
0x140006a90  xor     al, al
0x140006a92  cmp     dword ptr [rdi+2Ch], 3
0x140006a96  jbe     short loc_140006AAE
0x140006a98  test    al, al
0x140006a9a  jnz     short loc_140006AAE
0x140006a9c  mov     rcx, rdi
0x140006a9f  call    Smb2DelayRestartExchange
0x140006aa4  mov     ebx, 103h
0x140006aa9  jmp     loc_140006B87
0x140006aae  mov     rcx, [rdi+48h]
0x140006ab2  lea     r8, [rdi+0F0h]; pWorkQueueItem
0x140006ab9  lea     r9, SmbCepRestartExchangeWorker; Routine
0x140006ac0  mov     [rsp+78h+pContext], rdi; pContext
0x140006ac5  mov     edx, 3; WorkQueueType
0x140006aca  mov     rcx, [rcx+18h]; pMRxDeviceObject
0x140006ace  call    cs:__imp_RxPostToWorkerThread
0x140006ad5  nop     dword ptr [rax+rax+00h]
0x140006ada  mov     ebx, 103h
0x140006adf  jmp     loc_140006B87
0x140006ae4  test    r12b, r12b
0x140006ae7  jz      short loc_140006AF3
0x140006ae9  mov     ebx, 0C0000016h
0x140006aee  jmp     loc_140006B87
0x140006af3  mov     eax, [rdi+44h]
0x140006af6  test    al, 1
0x140006af8  jz      short loc_140006B14
0x140006afa  lea     rcx, [rdi+0B0h]; Event
0x140006b01  xor     r8d, r8d; Wait
0x140006b04  xor     edx, edx; Increment
0x140006b06  call    cs:__imp_KeSetEvent
0x140006b0d  nop     dword ptr [rax+rax+00h]
0x140006b12  jmp     short loc_140006B87
0x140006b14  mov     rax, [rdi+48h]
0x140006b18  mov     rsi, [rax+18h]
0x140006b1c  mov     eax, [rdi+44h]
0x140006b1f  test    al, 1
0x140006b21  jz      short loc_140006B45
0x140006b23  xor     r9d, r9d; BugCheckParameter3
0x140006b26  mov     [rsp+78h+pContext], r13; BugCheckParameter4
0x140006b2b  mov     r8, rdi; BugCheckParameter2
0x140006b2e  mov     edx, 43584D5Fh; BugCheckParameter1
0x140006b33  mov     ecx, 27h ; '''; BugCheckCode
0x140006b38  call    cs:__imp_KeBugCheckEx
  ... truncated ...
```
