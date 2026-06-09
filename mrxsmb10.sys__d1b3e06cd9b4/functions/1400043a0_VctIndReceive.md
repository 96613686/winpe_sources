# VctIndReceive

- ea: `0x1400043a0`
- end: `0x140004a4f`
- name: `VctIndReceive`
- size: `1711`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, unsigned int, int, unsigned int *, __int64, _QWORD *, __int128 **, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004330`
- `0x140008840`

## callees

- `0x140001e40`
- `0x140002470`
- `0x1400043a0`
- `0x140004a60`
- `0x14000b524`
- `0x14000bd10`
- `0x14000ebd8`
- `0x140010358`
- `0x140010a04`
- `0x140014db4`
- `0x140015344`
- `0x14001565c`
- `0x1400157a8`
- `0x140015804`
- `0x140016560`

## import_xrefs

- `ntoskrnl!RtlGetCallersAddress` at `0x140004643`
- `ntoskrnl!RtlGetCallersAddress` at `0x140004643`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004428`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400044d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400046a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004750`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a01`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004428`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400044d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400046a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004750`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a01`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400043ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400044ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004610`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400043ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400044ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004610`
- `ntoskrnl!DbgPrint` at `0x140004790`
- `ntoskrnl!DbgPrint` at `0x140004790`
- `ntoskrnl!ExAllocatePool2` at `0x140004462`
- `ntoskrnl!ExAllocatePool2` at `0x140004462`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046fe`
- `rdbss!RxDispatchToWorkerThread` at `0x140004775`
- `rdbss!RxDispatchToWorkerThread` at `0x140004775`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140004485`
- `mrxsmb!CopyBufferToMdl` at `0x14000489e`
- `mrxsmb!CopyBufferToMdl` at `0x14000489e`
- `mrxsmb!MRxSmbDeviceObject` at `0x14000475c`

## pseudocode

```c
__int64 __fastcall VctIndReceive(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned int *a6,
        __int64 a7,
        _QWORD *a8,
        __int128 **a9,
        unsigned int *a10)
{
  _BYTE *v10; // r15
  unsigned int v11; // ebx
  KIRQL v15; // dl
  char v16; // r13
  __int128 *Pool2; // rdi
  KIRQL v18; // al
  bool v19; // zf
  unsigned int v20; // eax
  KIRQL v22; // al
  signed __int32 v23; // r12d
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rax
  unsigned int v28; // eax
  struct _DEVICE_OBJECT *v29; // rcx
  __int128 v30; // [rsp+30h] [rbp-40h] BYREF
  __int128 v31; // [rsp+40h] [rbp-30h]
  __int128 v32; // [rsp+50h] [rbp-20h]
  __int64 v33; // [rsp+60h] [rbp-10h]
  unsigned int v34; // [rsp+70h] [rbp+0h] BYREF
  unsigned int v35; // [rsp+74h] [rbp+4h] BYREF
  PVOID CallersAddress; // [rsp+78h] [rbp+8h] BYREF
  __int64 v37; // [rsp+80h] [rbp+10h] BYREF
  PVOID CallersCaller; // [rsp+88h] [rbp+18h] BYREF

  v10 = *(_BYTE **)(a1 + 384);
  v11 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  LODWORD(CallersAddress) = a2;
  s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v15 = s_SmbCeDbSpinLockSavedIrql;
  if ( v10 && *(_BYTE **)(a1 + 384) == v10 && !*v10 )
  {
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
    if ( a3 == a4 )
    {
      Pool2 = &v30;
      v30 = 0;
      v16 = 1;
      v31 = 0;
      v32 = 0;
      v33 = 0;
    }
    else
    {
      v16 = 0;
      Pool2 = (__int128 *)_InterlockedExchange64((volatile __int64 *)(a1 + 480), 0);
      if ( !Pool2 )
      {
        Pool2 = (__int128 *)ExAllocatePool2(64, 56, 1666608467);
        if ( !Pool2 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)
                                                          + MRxSmbLegacyPerfCtrs
                                                          + 144));
          *((_DWORD *)v10 + 82) = -1073741300;
          v18 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
          v19 = *((_DWORD *)v10 + 3) == 9;
          s_SmbCeDbSpinLockSavedIrql = v18;
          if ( v19 )
          {
            KeReleaseSpinLock(&s_SmbCeDbSpinLock, v18);
            *a6 = a4;
          }
          else
          {
            MRxSmbTrackRefCount(v10, "SmbCeErrorInd", 1280);
            SmbReferenceRecord(v10 + 792, "SmbCeErrorInd", 1280);
            _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
            KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
            if ( RxDispatchToWorkerThread(
                   MRxSmbDeviceObject,
                   NormalWorkQueue,
                   SmbCeResumeAllOutstandingRequestsOnError,
                   v10) )
            {
              DbgPrint("Error Indication not dispatched\n");
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, v10);
              }
            }
            *a6 = a4;
          }
          return v11;
        }
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids, a1, a3, a4);
    v20 = 128;
    if ( a4 <= 0x80 )
      v20 = a4;
    if ( a3 && a3 >= v20 )
    {
      v11 = SmbCeReceiveInd(
              a1,
              (_DWORD)v10,
              a3,
              a4,
              (__int64)&v35,
              a7,
              (__int64)&v37,
              (__int64)&v34,
              (_DWORD)CallersAddress);
      if ( v11 == -1073741802 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_GLOBAL_Control, v35, v34);
        }
        v25 = v35;
        v26 = v35 + v34;
        LODWORD(CallersAddress) = v26;
        if ( (unsigned int)v26 > a4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_GLOBAL_Control, v26, a4);
            v25 = v35;
          }
          LODWORD(CallersAddress) = a4;
          LODWORD(v26) = a4;
          v34 = a4 - v25;
        }
        if ( (unsigned int)v26 > a3 )
        {
          v27 = v37;
          *a6 = v25;
          *((_QWORD *)Pool2 + 1) = v27;
          *a8 = v37;
          *((_DWORD *)Pool2 + 1) = v34;
          *a10 = v34;
          *((_QWORD *)Pool2 + 2) = v37;
          *((_DWORD *)Pool2 + 6) = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_qDqDD(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, a6, a1, *a6, *a8, *a10, a4);
          }
          *a9 = Pool2;
          Pool2 = 0;
        }
        else
        {
          CopyBufferToMdl(v37, a7 + v25);
          SmbCeDataReadyInd(v10, v37, v34, 0);
          v11 = 0;
          *a6 = (unsigned int)CallersAddress;
          *a8 = 0;
          *a10 = 0;
        }
      }
      else
      {
        *a6 = v35;
        *a8 = 0;
        *a10 = 0;
      }
    }
    else
    {
      CallersAddress = 0;
      CallersCaller = 0;
      v22 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
      s_SmbCeDbSpinLockSavedIrql = v22;
      if ( *(_DWORD *)(a1 + 12) )
      {
        KeReleaseSpinLock(&s_SmbCeDbSpinLock, v22);
        v11 = 0;
      }
      else
      {
        v23 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
        RtlGetCallersAddress(&CallersAddress, &CallersCaller);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          DWORD2(v31) = v23;
          LODWORD(v31) = v23 - 1;
          WPP_SF_qDDqq(
            AttachedDevice,
            11,
            (unsigned int)(v23 - 1),
            a1,
            v31,
            *((_QWORD *)&v31 + 1),
            CallersCaller,
            CallersAddress,
            v33);
        }
        KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
        if ( (int)VctpSetupReceiveContextForRemainingMessage(Pool2, a4) >= 0 )
        {
          *a6 = 0;
          *a8 = *((_QWORD *)Pool2 + 4);
          *a10 = *((_DWORD *)Pool2 + 6);
          *a9 = Pool2;
          Pool2 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            v28 = *a10;
            v29 = WPP_GLOBAL_Control->AttachedDevice;
            LODWORD(v32) = a4;
            DWORD2(v31) = v28;
            WPP_SF_qqDD(
              v29,
              23,
              WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids,
              a1,
              *a8,
              *((_QWORD *)&v31 + 1),
              v32,
              *((_QWORD *)&v32 + 1));
          }
          v11 = -1073741802;
          goto LABEL_19;
        }
        SmbCeErrorInd(v10);
        v11 = 0;
      }
      *a6 = a4;
    }
LABEL_19:
    if ( !v16 )
    {
      if ( Pool2 )
      {
        *Pool2 = 0;
        *(__int128 *)((char *)Pool2 + 12) = 0;
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 480), (signed __int64)Pool2, 0) )
        {
          VctTeardownReceiveContext(Pool2);
          ExFreePoolWithTag(Pool2, 0);
        }
      }
    }
    return v11;
  }
  *a6 = a4;
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, v15);
  return 0;
}

```

## disassembly

```asm
0x1400043a0  push    rbp
0x1400043a2  push    rbx
0x1400043a3  push    rsi
0x1400043a4  push    rdi
0x1400043a5  push    r12
0x1400043a7  push    r13
0x1400043a9  push    r14
0x1400043ab  push    r15
0x1400043ad  sub     rsp, 88h
0x1400043b4  lea     rbp, [rsp+50h]
0x1400043b9  mov     rax, cs:__security_cookie
0x1400043c0  xor     rax, rbp
0x1400043c3  mov     [rbp+70h+var_50], rax
0x1400043c7  mov     r15, [rcx+180h]
0x1400043ce  xor     ebx, ebx
0x1400043d0  mov     r14, rcx
0x1400043d3  mov     [rbp+70h+var_60], rbx
0x1400043d7  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400043de  mov     [rbp+70h+var_70], ebx
0x1400043e1  mov     [rbp+70h+var_6C], ebx
0x1400043e4  mov     esi, r9d
0x1400043e7  mov     r12d, r8d
0x1400043ea  mov     dword ptr [rbp+70h+CallersAddress], edx
0x1400043ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400043f4  nop     dword ptr [rax+rax+00h]
0x1400043f9  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x1400043ff  movzx   edx, al; NewIrql
0x140004402  test    r15, r15
0x140004405  jz      loc_140004A2C
0x14000440b  cmp     [r14+180h], r15
0x140004412  jnz     loc_140004A2C
0x140004418  cmp     [r15], bl
0x14000441b  jnz     loc_140004A2C
0x140004421  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004428  call    cs:__imp_KeReleaseSpinLock
0x14000442f  nop     dword ptr [rax+rax+00h]
0x140004434  cmp     r12d, esi
0x140004437  jz      loc_1400044EF
0x14000443d  mov     edi, ebx
0x14000443f  xor     r13b, r13b
0x140004442  xchg    rdi, [r14+1E0h]
0x140004449  test    rdi, rdi
0x14000444c  jnz     loc_140004514
0x140004452  mov     edx, 38h ; '8'
0x140004457  mov     ecx, 40h ; '@'
0x14000445c  mov     r8d, 63566D53h
0x140004462  call    cs:__imp_ExAllocatePool2
0x140004469  nop     dword ptr [rax+rax+00h]
0x14000446e  mov     rdi, rax
0x140004471  test    rax, rax
0x140004474  jnz     loc_140004514
0x14000447a  mov     eax, gs:1A4h
0x140004482  mov     r8d, eax
0x140004485  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14000448c  shl     r8, 8
0x140004490  mov     rdx, [rax]
0x140004493  lock inc dword ptr [r8+rdx+90h]
0x14000449c  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400044a3  mov     dword ptr [r15+148h], 0C000020Ch
0x1400044ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400044b5  nop     dword ptr [rax+rax+00h]
0x1400044ba  cmp     dword ptr [r15+0Ch], 9
0x1400044bf  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x1400044c5  jnz     loc_14000470F
0x1400044cb  movzx   edx, al; NewIrql
0x1400044ce  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400044d5  call    cs:__imp_KeReleaseSpinLock
0x1400044dc  nop     dword ptr [rax+rax+00h]
0x1400044e1  mov     rax, [rbp+70h+arg_28]
0x1400044e8  mov     [rax], esi
0x1400044ea  jmp     loc_1400045C6
0x1400044ef  mov     eax, [rsp+0C0h+var_C0]
0x1400044f2  sub     rsp, 40h
0x1400044f6  lea     rdi, [rsp+100h+var_B0]
0x1400044fb  mov     eax, [rdi]
0x1400044fd  xorps   xmm0, xmm0
0x140004500  xor     eax, eax
0x140004502  movups  xmmword ptr [rdi], xmm0
0x140004505  mov     r13b, 1
0x140004508  movups  xmmword ptr [rdi+10h], xmm0
0x14000450c  movups  xmmword ptr [rdi+20h], xmm0
0x140004510  mov     [rdi+30h], rax
0x140004514  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000451b  lea     rbx, WPP_GLOBAL_Control
0x140004522  cmp     rcx, rbx
0x140004525  jz      short loc_140004534
0x140004527  test    dword ptr [rcx+2Ch], 400h
0x14000452e  jnz     loc_1400047D5
0x140004534  mov     eax, 80h
0x140004539  cmp     esi, eax
0x14000453b  cmovbe  eax, esi
0x14000453e  test    r12d, r12d
0x140004541  jz      loc_1400045FE
0x140004547  cmp     r12d, eax
0x14000454a  jb      loc_1400045FE
0x140004550  mov     eax, dword ptr [rbp+70h+CallersAddress]
0x140004553  mov     r9d, esi
0x140004556  mov     dword ptr [rsp+0C0h+var_80], eax
0x14000455a  mov     r8d, r12d
0x14000455d  lea     rax, [rbp+70h+var_70]
0x140004561  mov     rdx, r15
0x140004564  mov     [rsp+0C0h+var_88], rax
0x140004569  mov     rcx, r14
0x14000456c  lea     rax, [rbp+70h+var_60]
0x140004570  mov     [rsp+0C0h+var_90], rax
0x140004575  mov     rax, [rbp+70h+arg_30]
0x14000457c  mov     [rsp+0C0h+var_98], rax
0x140004581  lea     rax, [rbp+70h+var_6C]
0x140004585  mov     [rsp+0C0h+var_A0], rax
0x14000458a  call    SmbCeReceiveInd
0x14000458f  mov     ebx, eax
0x140004591  cmp     eax, 0C0000016h
0x140004596  jz      loc_1400047FB
0x14000459c  mov     rcx, [rbp+70h+arg_28]
0x1400045a3  mov     eax, [rbp+70h+var_6C]
0x1400045a6  mov     [rcx], eax
0x1400045a8  xor     ecx, ecx
0x1400045aa  mov     rax, [rbp+70h+arg_38]
0x1400045b1  mov     [rax], rcx
0x1400045b4  mov     rax, [rbp+70h+arg_48]
0x1400045bb  mov     [rax], ecx
0x1400045bd  test    r13b, r13b
0x1400045c0  jz      loc_140004A1E
0x1400045c6  mov     eax, ebx
0x1400045c8  mov     rcx, [rbp+70h+var_50]
0x1400045cc  xor     rcx, rbp; StackCookie
0x1400045cf  call    __security_check_cookie
0x1400045d4  lea     rsp, [rbp+38h]
0x1400045d8  pop     r15
0x1400045da  pop     r14
0x1400045dc  pop     r13
0x1400045de  pop     r12
0x1400045e0  pop     rdi
0x1400045e1  pop     rsi
0x1400045e2  pop     rbx
0x1400045e3  pop     rbp
0x1400045e4  retn
0x1400045e6  test    dword ptr [rcx+2Ch], 200h
0x1400045ed  jnz     loc_1400047B8
0x1400045f3  mov     rax, [rbp+70h+arg_28]
0x1400045fa  mov     [rax], esi
0x1400045fc  jmp     short loc_1400045C6
0x1400045fe  xor     r12d, r12d
0x140004601  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004608  mov     [rbp+70h+CallersAddress], r12
0x14000460c  mov     [rbp+70h+CallersCaller], r12
0x140004610  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004617  nop     dword ptr [rax+rax+00h]
0x14000461c  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140004622  cmp     [r14+0Ch], r12d
0x140004626  jnz     loc_1400049F7
0x14000462c  mov     r12d, 1
0x140004632  lock xadd [r14+8], r12d
0x140004638  inc     r12d
0x14000463b  lea     rdx, [rbp+70h+CallersCaller]; CallersCaller
0x14000463f  lea     rcx, [rbp+70h+CallersAddress]; CallersAddress
0x140004643  call    cs:__imp_RtlGetCallersAddress
0x14000464a  nop     dword ptr [rax+rax+00h]
0x14000464f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004656  cmp     rcx, rbx
0x140004659  jz      short loc_140004696
0x14000465b  test    dword ptr [rcx+2Ch], 200h
0x140004662  jz      short loc_140004696
0x140004664  mov     rax, [rbp+70h+CallersAddress]
0x140004668  lea     r8d, [r12-1]
0x14000466d  mov     rcx, [rcx+18h]
0x140004671  mov     edx, 0Bh
0x140004676  mov     [rsp+0C0h+var_88], rax
0x14000467b  mov     r9, r14
0x14000467e  mov     rax, [rbp+70h+CallersCaller]
0x140004682  mov     [rsp+0C0h+var_90], rax
0x140004687  mov     dword ptr [rsp+0C0h+var_98], r12d
0x14000468c  mov     dword ptr [rsp+0C0h+var_A0], r8d
0x140004691  call    WPP_SF_qDDqq
0x140004696  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000469d  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400046a4  call    cs:__imp_KeReleaseSpinLock
0x1400046ab  nop     dword ptr [rax+rax+00h]
0x1400046b0  mov     edx, esi
0x1400046b2  mov     rcx, rdi
0x1400046b5  call    VctpSetupReceiveContextForRemainingMessage
0x1400046ba  test    eax, eax
0x1400046bc  jns     loc_140004979
0x1400046c2  mov     edx, 0C000020Ch
0x1400046c7  mov     rcx, r15; pContext
0x1400046ca  call    SmbCeErrorInd
0x1400046cf  xor     ebx, ebx
0x1400046d1  jmp     loc_140004A10
0x1400046d6  xorps   xmm0, xmm0
0x1400046d9  xor     eax, eax
0x1400046db  movups  xmmword ptr [rdi], xmm0
0x1400046de  movups  xmmword ptr [rdi+0Ch], xmm0
0x1400046e2  lock cmpxchg [r14+1E0h], rdi
0x1400046eb  jz      loc_1400045C6
0x1400046f1  mov     rcx, rdi
0x1400046f4  call    VctTeardownReceiveContext
0x1400046f9  xor     edx, edx; Tag
0x1400046fb  mov     rcx, rdi; P
0x1400046fe  call    cs:__imp_ExFreePoolWithTag
0x140004705  nop     dword ptr [rax+rax+00h]
0x14000470a  jmp     loc_1400045C6
0x14000470f  mov     r8d, 500h
0x140004715  lea     rdx, aSmbceerrorind; "SmbCeErrorInd"
0x14000471c  mov     rcx, r15
0x14000471f  call    MRxSmbTrackRefCount
0x140004724  lea     rcx, [r15+318h]
0x14000472b  mov     r8d, 500h
0x140004731  lea     rdx, aSmbceerrorind; "SmbCeErrorInd"
0x140004738  call    SmbReferenceRecord
0x14000473d  lock inc dword ptr [r15+8]
0x140004742  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x140004749  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004750  call    cs:__imp_KeReleaseSpinLock
0x140004757  nop     dword ptr [rax+rax+00h]
0x14000475c  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140004763  lea     r8, SmbCeResumeAllOutstandingRequestsOnError; Routine
0x14000476a  mov     r9, r15; pContext
0x14000476d  mov     edx, 3; WorkQueueType
0x140004772  mov     rcx, [rcx]; pMRxDeviceObject
0x140004775  call    cs:__imp_RxDispatchToWorkerThread
0x14000477c  nop     dword ptr [rax+rax+00h]
0x140004781  test    eax, eax
0x140004783  jz      loc_1400045F3
0x140004789  lea     rcx, aErrorIndicatio; "Error Indication not dispatched\n"
0x140004790  call    cs:__imp_DbgPrint
0x140004797  nop     dword ptr [rax+rax+00h]
0x14000479c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400047a3  lea     rax, WPP_GLOBAL_Control
0x1400047aa  cmp     rcx, rax
0x1400047ad  jz      loc_1400045F3
0x1400047b3  jmp     loc_1400045E6
0x1400047b8  mov     rcx, [rcx+18h]
0x1400047bc  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x1400047c3  mov     edx, 14h
0x1400047c8  mov     r9, r15
0x1400047cb  call    WPP_SF_q
0x1400047d0  jmp     loc_1400045F3
0x1400047d5  mov     rcx, [rcx+18h]
0x1400047d9  lea     r8, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids
0x1400047e0  mov     edx, 13h
0x1400047e5  mov     dword ptr [rsp+0C0h+var_98], esi
0x1400047e9  mov     r9, r14
0x1400047ec  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x1400047f1  call    WPP_SF_qDD
0x1400047f6  jmp     loc_140004534
0x1400047fb  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004802  lea     rcx, WPP_GLOBAL_Control
0x140004809  cmp     r8, rcx
0x14000480c  jz      short loc_140004838
0x14000480e  test    dword ptr [r8+2Ch], 400h
0x140004816  jz      short loc_140004838
0x140004818  mov     eax, [rbp+70h+var_70]
0x14000481b  mov     edx, 14h
0x140004820  mov     r9d, [rbp+70h+var_6C]
0x140004824  mov     rcx, [r8+18h]
0x140004828  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14000482c  call    WPP_SF_DD
0x140004831  lea     rcx, WPP_GLOBAL_Control
0x140004838  mov     edx, [rbp+70h+var_6C]
0x14000483b  mov     r8d, [rbp+70h+var_70]
0x14000483f  lea     r9d, [rdx+r8]
0x140004843  mov     dword ptr [rbp+70h+CallersAddress], r9d
0x140004847  cmp     r9d, esi
0x14000484a  jbe     short loc_14000488E
0x14000484c  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004853  cmp     r8, rcx
0x140004856  jz      short loc_14000487E
0x140004858  test    dword ptr [r8+2Ch], 400h
0x140004860  jz      short loc_14000487E
0x140004862  mov     rcx, [r8+18h]
0x140004866  mov     edx, 15h
0x14000486b  mov     dword ptr [rsp+0C0h+var_A0], esi
0x14000486f  call    WPP_SF_DD
0x140004874  mov     edx, [rbp+70h+var_6C]
0x140004877  lea     rcx, WPP_GLOBAL_Control
0x14000487e  mov     r8d, esi
0x140004881  mov     dword ptr [rbp+70h+CallersAddress], esi
0x140004884  sub     r8d, edx
0x140004887  mov     r9d, esi
0x14000488a  mov     [rbp+70h+var_70], r8d
0x14000488e  cmp     r9d, r12d
0x140004891  ja      short loc_1400048EB
0x140004893  add     rdx, [rbp+70h+arg_30]
0x14000489a  mov     rcx, [rbp+70h+var_60]
0x14000489e  call    cs:__imp_CopyBufferToMdl
0x1400048a5  nop     dword ptr [rax+rax+00h]
0x1400048aa  mov     r8d, [rbp+70h+var_70]
0x1400048ae  xor     r9d, r9d
0x1400048b1  mov     rdx, [rbp+70h+var_60]
0x1400048b5  mov     rcx, r15
0x1400048b8  call    SmbCeDataReadyInd
0x1400048bd  mov     rax, [rbp+70h+arg_28]
0x1400048c4  xor     ebx, ebx
0x1400048c6  mov     ecx, dword ptr [rbp+70h+CallersAddress]
0x1400048c9  mov     [rax], ecx
0x1400048cb  mov     rax, [rbp+70h+arg_38]
0x1400048d2  mov     qword ptr [rax], 0
0x1400048d9  mov     rax, [rbp+70h+arg_48]
0x1400048e0  mov     dword ptr [rax], 0
0x1400048e6  jmp     loc_1400045BD
  ... truncated ...
```
