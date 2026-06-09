# SmbCeCompleteSrvCallConstructionPhase2

- ea: `0x14003fbb0`
- end: `0x1400400bb`
- name: `SmbCeCompleteSrvCallConstructionPhase2`
- size: `1291`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002e40`
- `0x140003480`
- `0x140004360`
- `0x1400045c0`
- `0x14000fcd0`
- `0x140013470`
- `0x140014400`
- `0x14001b280`
- `0x140023b40`
- `0x1400267cc`
- `0x14002d320`
- `0x140031200`
- `0x140038158`
- `0x14003e14c`
- `0x14003e8b0`
- `0x14003faa8`
- `0x14003fb30`
- `0x14003fbb0`
- `0x1400400c4`
- `0x140040760`
- `0x14004b4cc`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003fc3b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003fc85`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003fcb5`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003ffc4`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003fc3b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003fc85`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003fcb5`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003ffc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004002a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004004f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004009d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004002a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004004f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004009d`
- `rdbss!RxPostToWorkerThread` at `0x140040084`
- `rdbss!RxPostToWorkerThread` at `0x140040084`

## pseudocode

```c
void __fastcall SmbCeCompleteSrvCallConstructionPhase2(__int64 a1)
{
  ULONG_PTR v1; // r15
  __int64 pContext; // r12
  __int64 v3; // rdi
  int v4; // ebx
  __int64 v5; // r13
  __int64 v6; // r14
  KIRQL v7; // bp
  __int64 FirstVcEndpoint; // rax
  __int64 v9; // rsi
  int v10; // ecx
  int DialectInfoFromNegotiateResponse; // eax
  __int64 v12; // r8
  void *v13; // rbp
  __int64 FirstBindingObject; // rax
  __int64 v15; // rax
  KIRQL v16; // dl
  int v17; // ecx
  int v18; // r8d
  void *v19; // rcx
  ULONG_PTR BugCheckParameter2; // [rsp+40h] [rbp-58h]
  int OldIrql; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v23; // [rsp+B0h] [rbp+18h]
  __int64 v24; // [rsp+B8h] [rbp+20h] BYREF

  v24 = 0;
  OldIrql = 0;
  v23 = 0;
  v1 = *(_QWORD *)(a1 + 24);
  pContext = *(_QWORD *)(a1 + 16);
  v3 = *(_QWORD *)(a1 + 32);
  v4 = *(_DWORD *)(a1 + 8);
  v5 = *(_QWORD *)(v1 + 24);
  v6 = *(_QWORD *)(pContext + 264);
  v7 = SmbCeAcquireSpinLock(v5);
  FirstVcEndpoint = SmbCeGetFirstVcEndpoint(v1);
  v9 = FirstVcEndpoint;
  if ( !FirstVcEndpoint )
  {
    *(_DWORD *)(v5 + 2352) = -1;
    if ( (v4 & 0xFFFFFF00) != 0xC0240100 )
      v4 = -1073741300;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920), v7);
    v10 = 806356061;
    goto LABEL_11;
  }
  if ( !(unsigned __int8)VctReferenceEndpointSafe(FirstVcEndpoint) )
  {
    *(_DWORD *)(v5 + 2352) = -1;
    v9 = 0;
    if ( (v4 & 0xFFFFFF00) != 0xC0240100 )
      v4 = -1073741300;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920), v7);
    v10 = 806356075;
LABEL_11:
    if ( v4 >= 0 )
      goto LABEL_47;
    goto LABEL_35;
  }
  *(_QWORD *)(v9 + 384) = 0;
  *(_DWORD *)(v5 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920), v7);
  if ( v4 )
  {
    v10 = 806356088;
    goto LABEL_11;
  }
  if ( !*(_QWORD *)v3 )
  {
    v4 = -1073741629;
    v23 = 0x19EC00000C3LL;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids);
    }
    v10 = 806356103;
LABEL_35:
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(v10, (unsigned int)CreateSrvCallError, *(_QWORD *)(pContext + 32) + 412, v4, v10);
    *(_QWORD *)(v6 + 32) = 0;
    if ( v9 )
    {
      SmbCeErrorInd(v9, v23, 0);
      VctDisconnectAndDereferenceEndpoint((PVOID)v9);
    }
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_38ca382afbca3a5878741f643c2fc975_Traceguids,
      v6,
      *(_DWORD *)(v3 + 16));
  }
  DialectInfoFromNegotiateResponse = GetDialectInfoFromNegotiateResponse(
                                       *(_QWORD *)(v1 + 24),
                                       *(_QWORD *)v3,
                                       *(_DWORD *)(v3 + 16),
                                       v1,
                                       &OldIrql,
                                       0,
                                       1);
  v4 = DialectInfoFromNegotiateResponse;
  if ( DialectInfoFromNegotiateResponse < 0 )
  {
    v23 = (unsigned int)DialectInfoFromNegotiateResponse | 0x19D00000000LL;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids);
    }
    v10 = 806356130;
    goto LABEL_35;
  }
  v24 = 0;
  v4 = SubRdrClaimSrvCall(pContext, v6, v1, (unsigned int)&v24, v9, OldIrql, v3);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qdLq(WPP_GLOBAL_Control->AttachedDevice, 1, v12, v6, OldIrql, v4, v9);
    }
    v23 = (unsigned int)v4 | 0x19C00000000LL;
    v10 = 806356161;
    goto LABEL_35;
  }
  v13 = 0;
  LOBYTE(OldIrql) = SmbCeAcquireSpinLock(v5);
  *(_QWORD *)(v24 + 48) = v6;
  if ( **(_WORD **)(v24 + 64) == 1 )
  {
    v13 = (void *)_InterlockedExchange64((volatile __int64 *)(v9 + 512), 0);
    FirstBindingObject = SmbCeGetFirstBindingObjectEx(v1, 0);
    BugCheckParameter2 = FirstBindingObject;
    if ( FirstBindingObject )
    {
      v23 = 3221225996LL;
      SmbCeUpperDisconnectBindingObjectLite(FirstBindingObject, 3221225996LL);
      SmbCeDereferenceBindingObject(BugCheckParameter2);
    }
    SmbCeRemoveVcEndpointLite(v1, v9);
  }
  VctDereferenceEndpoint((PVOID)v9);
  v15 = v24;
  *(_DWORD *)(v6 + 96) |= 0xCu;
  *(_QWORD *)(v6 + 32) = v15;
  *(_DWORD *)(v6 + 100) = *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(v5) + 8) + 1;
  v16 = OldIrql;
  *(_DWORD *)(v5 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920), v16);
  if ( v13 )
  {
    if ( (Microsoft_Windows_SMBClientEnableBits & 8) != 0 )
      McTemplateK0hzr0p_EtwWriteTransfer(
        v17,
        (unsigned int)SmbTeardownMidWindow,
        v18,
        *(_WORD *)(v1 + 112) >> 1,
        *(_QWORD *)(v1 + 120),
        (char)v13);
    SmbCseTeardownSlidingWindow(v13);
  }
LABEL_47:
  SmbCeDereferenceServerEntryEx(v1);
  *(_DWORD *)(pContext + 280) = v4;
  if ( *(_QWORD *)v3 )
  {
    ExFreePoolWithTag(*(PVOID *)v3, 0x6D53674Eu);
    *(_QWORD *)v3 = 0;
    *(_DWORD *)(v3 + 16) = 0;
  }
  v19 = *(void **)(v3 + 8);
  if ( v19 )
  {
    ExFreePoolWithTag(v19, 0x6D53674Eu);
    *(_QWORD *)(v3 + 8) = 0;
    *(_DWORD *)(v3 + 20) = 0;
  }
  RxPostToWorkerThread(
    *(PRDBSS_DEVICE_OBJECT *)pContext,
    CriticalWorkQueue,
    (PRX_WORK_QUEUE_ITEM)(pContext + 200),
    SmbCeCompleteSrvCallConstruction,
    (PVOID)pContext);
  ExFreePoolWithTag((PVOID)a1, 0x6D536243u);
}

```

## disassembly

```asm
0x14003fbb0  mov     r11, rsp
0x14003fbb3  mov     [r11+8], rcx
0x14003fbb7  push    rbx
0x14003fbb8  push    rbp
0x14003fbb9  push    rsi
0x14003fbba  push    rdi
0x14003fbbb  push    r12
0x14003fbbd  push    r13
0x14003fbbf  push    r14
0x14003fbc1  push    r15
0x14003fbc3  sub     rsp, 58h
0x14003fbc7  mov     rax, rcx
0x14003fbca  xor     ecx, ecx
0x14003fbcc  mov     [r11+20h], rcx
0x14003fbd0  mov     [r11+10h], ecx
0x14003fbd4  mov     [rsp+98h+arg_10], rcx
0x14003fbdc  mov     r15, [rax+18h]
0x14003fbe0  mov     r12, [rax+10h]
0x14003fbe4  mov     rdi, [rax+20h]
0x14003fbe8  mov     ebx, [rax+8]
0x14003fbeb  mov     r13, [r15+18h]
0x14003fbef  mov     r14, [r12+108h]
0x14003fbf7  mov     rcx, r13
0x14003fbfa  call    SmbCeAcquireSpinLock
0x14003fbff  mov     rcx, r15
0x14003fc02  mov     bpl, al
0x14003fc05  call    SmbCeGetFirstVcEndpoint
0x14003fc0a  mov     rsi, rax
0x14003fc0d  test    rax, rax
0x14003fc10  jnz     short loc_14003FC4E
0x14003fc12  mov     eax, ebx
0x14003fc14  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14003fc1f  and     eax, 0FFFFFF00h
0x14003fc24  mov     ecx, 0C000020Ch
0x14003fc29  cmp     eax, 0C0240100h
0x14003fc2e  mov     dl, bpl; OldIrql
0x14003fc31  cmovnz  ebx, ecx
0x14003fc34  lea     rcx, [r13+780h]; SpinLock
0x14003fc3b  call    cs:__imp_ExReleaseSpinLockExclusive
0x14003fc42  nop     dword ptr [rax+rax+00h]
0x14003fc47  mov     ecx, 3010045Dh
0x14003fc4c  jmp     short loc_14003FCCA
0x14003fc4e  mov     rcx, rsi
0x14003fc51  call    VctReferenceEndpointSafe
0x14003fc56  mov     dl, bpl; OldIrql
0x14003fc59  test    al, al
0x14003fc5b  jnz     short loc_14003FC98
0x14003fc5d  mov     eax, ebx
0x14003fc5f  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14003fc6a  and     eax, 0FFFFFF00h
0x14003fc6f  xor     esi, esi
0x14003fc71  cmp     eax, 0C0240100h
0x14003fc76  mov     ecx, 0C000020Ch
0x14003fc7b  cmovnz  ebx, ecx
0x14003fc7e  lea     rcx, [r13+780h]; SpinLock
0x14003fc85  call    cs:__imp_ExReleaseSpinLockExclusive
0x14003fc8c  nop     dword ptr [rax+rax+00h]
0x14003fc91  mov     ecx, 3010046Bh
0x14003fc96  jmp     short loc_14003FCCA
0x14003fc98  mov     qword ptr [rsi+180h], 0
0x14003fca3  lea     rcx, [r13+780h]; SpinLock
0x14003fcaa  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14003fcb5  call    cs:__imp_ExReleaseSpinLockExclusive
0x14003fcbc  nop     dword ptr [rax+rax+00h]
0x14003fcc1  test    ebx, ebx
0x14003fcc3  jz      short loc_14003FCD7
0x14003fcc5  mov     ecx, 30100478h
0x14003fcca  test    ebx, ebx
0x14003fccc  jns     loc_140040009
0x14003fcd2  jmp     loc_14003FE9E
0x14003fcd7  cmp     qword ptr [rdi], 0
0x14003fcdb  jnz     short loc_14003FD42
0x14003fcdd  mov     ebx, 0C00000C3h
0x14003fce2  mov     dword ptr [rsp+98h+arg_10+4], 19Eh
0x14003fced  mov     dword ptr [rsp+98h+arg_10], ebx
0x14003fcf4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003fcfb  lea     rbp, WPP_GLOBAL_Control
0x14003fd02  cmp     rcx, rbp
0x14003fd05  jz      short loc_14003FD38
0x14003fd07  mov     eax, [rcx+2Ch]
0x14003fd0a  mov     edx, 1
0x14003fd0f  test    dl, al
0x14003fd11  jz      short loc_14003FD38
0x14003fd13  cmp     [rcx+29h], dl
0x14003fd16  jb      short loc_14003FD38
0x14003fd18  mov     rcx, [rcx+18h]
0x14003fd1c  lea     r8, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids
0x14003fd23  mov     edx, 15h
0x14003fd28  mov     [rsp+98h+pContext], r14
0x14003fd2d  mov     r9d, 0C00000C3h
0x14003fd33  call    WPP_SF_dq
0x14003fd38  mov     ecx, 30100487h
0x14003fd3d  jmp     loc_14003FE9E
0x14003fd42  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003fd49  lea     rbp, WPP_GLOBAL_Control
0x14003fd50  cmp     rcx, rbp
0x14003fd53  jz      short loc_14003FD81
0x14003fd55  mov     eax, [rcx+2Ch]
0x14003fd58  test    al, 40h
0x14003fd5a  jz      short loc_14003FD81
0x14003fd5c  cmp     byte ptr [rcx+29h], 2
0x14003fd60  jb      short loc_14003FD81
0x14003fd62  mov     eax, [rdi+10h]
0x14003fd65  lea     r8, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids
0x14003fd6c  mov     rcx, [rcx+18h]
0x14003fd70  mov     edx, 16h
0x14003fd75  mov     r9, r14
0x14003fd78  mov     dword ptr [rsp+98h+pContext], eax
0x14003fd7c  call    WPP_SF_qD
0x14003fd81  mov     r8d, [rdi+10h]
0x14003fd85  lea     rax, [rsp+98h+OldIrql]
0x14003fd8d  mov     rdx, [rdi]
0x14003fd90  mov     r9, r15
0x14003fd93  mov     rcx, [r15+18h]
0x14003fd97  mov     byte ptr [rsp+98h+var_68], 1
0x14003fd9c  mov     [rsp+98h+var_70], 0
0x14003fda5  mov     [rsp+98h+pContext], rax
0x14003fdaa  call    GetDialectInfoFromNegotiateResponse
0x14003fdaf  mov     ebx, eax
0x14003fdb1  test    eax, eax
0x14003fdb3  jns     short loc_14003FE09
0x14003fdb5  mov     dword ptr [rsp+98h+arg_10], eax
0x14003fdbc  mov     dword ptr [rsp+98h+arg_10+4], 19Dh
0x14003fdc7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003fdce  cmp     rcx, rbp
0x14003fdd1  jz      short loc_14003FDFF
0x14003fdd3  mov     edx, [rcx+2Ch]
0x14003fdd6  mov     eax, 1
0x14003fddb  test    al, dl
0x14003fddd  jz      short loc_14003FDFF
0x14003fddf  cmp     [rcx+29h], al
0x14003fde2  jb      short loc_14003FDFF
0x14003fde4  mov     rcx, [rcx+18h]
0x14003fde8  lea     edx, [rax+16h]
0x14003fdeb  mov     r9d, ebx
0x14003fdee  mov     [rsp+98h+pContext], r14
0x14003fdf3  lea     r8, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids
0x14003fdfa  call    WPP_SF_dq
0x14003fdff  mov     ecx, 301004A2h
0x14003fe04  jmp     loc_14003FE9E
0x14003fe09  mov     eax, [rsp+98h+OldIrql]
0x14003fe10  lea     r9, [rsp+98h+arg_18]
0x14003fe18  mov     [rsp+98h+var_68], rdi
0x14003fe1d  mov     r8, r15
0x14003fe20  mov     dword ptr [rsp+98h+var_70], eax
0x14003fe24  mov     rdx, r14
0x14003fe27  mov     rcx, r12
0x14003fe2a  mov     [rsp+98h+pContext], rsi
0x14003fe2f  mov     [rsp+98h+arg_18], 0
0x14003fe3b  call    SubRdrClaimSrvCall
0x14003fe40  mov     ebx, eax
0x14003fe42  test    eax, eax
0x14003fe44  jns     loc_14003FEF9
0x14003fe4a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003fe51  cmp     rcx, rbp
0x14003fe54  jz      short loc_14003FE87
0x14003fe56  mov     eax, [rcx+2Ch]
0x14003fe59  mov     edx, 1
0x14003fe5e  test    dl, al
0x14003fe60  jz      short loc_14003FE87
0x14003fe62  cmp     [rcx+29h], dl
0x14003fe65  jb      short loc_14003FE87
0x14003fe67  mov     eax, [rsp+98h+OldIrql]
0x14003fe6e  mov     r9, r14
0x14003fe71  mov     rcx, [rcx+18h]
0x14003fe75  mov     [rsp+98h+var_68], rsi
0x14003fe7a  mov     dword ptr [rsp+98h+var_70], ebx
0x14003fe7e  mov     dword ptr [rsp+98h+pContext], eax
0x14003fe82  call    WPP_SF_qdLq
0x14003fe87  mov     dword ptr [rsp+98h+arg_10], ebx
0x14003fe8e  mov     ecx, 301004C1h
0x14003fe93  mov     dword ptr [rsp+98h+arg_10+4], 19Ch
0x14003fe9e  test    cs:Microsoft_Windows_SMBClientEnableBits, 1
0x14003fea5  jz      short loc_14003FEC6
0x14003fea7  mov     r8, [r12+20h]
0x14003feac  lea     rdx, CreateSrvCallError
0x14003feb3  add     r8, 19Ch
0x14003feba  mov     dword ptr [rsp+98h+pContext], ecx
0x14003febe  mov     r9d, ebx
0x14003fec1  call    McTemplateK0qqq_EtwWriteTransfer
0x14003fec6  mov     qword ptr [r14+20h], 0
0x14003fece  test    rsi, rsi
0x14003fed1  jz      loc_140040009
0x14003fed7  mov     rdx, [rsp+98h+arg_10]
0x14003fedf  xor     r8d, r8d
0x14003fee2  mov     rcx, rsi
0x14003fee5  call    SmbCeErrorInd
0x14003feea  xor     edx, edx
0x14003feec  mov     rcx, rsi; pContext
0x14003feef  call    VctDisconnectAndDereferenceEndpoint
0x14003fef4  jmp     loc_140040009
0x14003fef9  mov     rcx, r13
0x14003fefc  xor     ebp, ebp
0x14003fefe  call    SmbCeAcquireSpinLock
0x14003ff03  mov     rcx, [rsp+98h+arg_18]
0x14003ff0b  mov     byte ptr [rsp+98h+OldIrql], al
0x14003ff12  lea     eax, [rbp+1]
0x14003ff15  mov     [rcx+30h], r14
0x14003ff19  mov     rcx, [rsp+98h+arg_18]
0x14003ff21  mov     rdx, [rcx+40h]
0x14003ff25  cmp     [rdx], ax
0x14003ff28  jnz     short loc_14003FF81
0x14003ff2a  xchg    rbp, [rsi+200h]
0x14003ff31  xor     edx, edx
0x14003ff33  mov     rcx, r15
0x14003ff36  call    SmbCeGetFirstBindingObjectEx
0x14003ff3b  mov     [rsp+98h+BugCheckParameter2], rax
0x14003ff40  test    rax, rax
0x14003ff43  jz      short loc_14003FF76
0x14003ff45  mov     ecx, 0C000020Ch
0x14003ff4a  mov     dword ptr [rsp+98h+arg_10+4], 0
0x14003ff55  mov     dword ptr [rsp+98h+arg_10], ecx
0x14003ff5c  mov     rcx, rax
0x14003ff5f  mov     rdx, [rsp+98h+arg_10]
0x14003ff67  call    SmbCeUpperDisconnectBindingObjectLite
0x14003ff6c  mov     rcx, [rsp+98h+BugCheckParameter2]; BugCheckParameter2
0x14003ff71  call    SmbCeDereferenceBindingObject
0x14003ff76  mov     rdx, rsi
0x14003ff79  mov     rcx, r15; BugCheckParameter2
0x14003ff7c  call    SmbCeRemoveVcEndpointLite
0x14003ff81  mov     rcx, rsi; pContext
0x14003ff84  call    VctDereferenceEndpoint
0x14003ff89  mov     rax, [rsp+98h+arg_18]
0x14003ff91  mov     rcx, r13
0x14003ff94  or      dword ptr [r14+60h], 0Ch
0x14003ff99  mov     [r14+20h], rax
0x14003ff9d  call    MRxSmbGetInstanceConfigurationBlock
0x14003ffa2  lea     rcx, [r13+780h]; SpinLock
0x14003ffa9  mov     edx, [rax+8]
0x14003ffac  inc     edx
0x14003ffae  mov     [r14+64h], edx
0x14003ffb2  mov     dl, byte ptr [rsp+98h+OldIrql]; OldIrql
0x14003ffb9  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14003ffc4  call    cs:__imp_ExReleaseSpinLockExclusive
0x14003ffcb  nop     dword ptr [rax+rax+00h]
0x14003ffd0  test    rbp, rbp
0x14003ffd3  jz      short loc_140040009
0x14003ffd5  test    cs:Microsoft_Windows_SMBClientEnableBits, 8
0x14003ffdc  jz      short loc_140040001
0x14003ffde  movzx   r9d, word ptr [r15+70h]
0x14003ffe3  lea     rdx, SmbTeardownMidWindow
0x14003ffea  mov     rax, [r15+78h]
0x14003ffee  shr     r9w, 1
0x14003fff2  mov     [rsp+98h+var_70], rbp
0x14003fff7  mov     [rsp+98h+pContext], rax
0x14003fffc  call    McTemplateK0hzr0p_EtwWriteTransfer
0x140040001  mov     rcx, rbp; P
0x140040004  call    SmbCseTeardownSlidingWindow
0x140040009  xor     edx, edx
0x14004000b  mov     rcx, r15; BugCheckParameter2
0x14004000e  call    SmbCeDereferenceServerEntryEx
0x140040013  mov     [r12+118h], ebx
0x14004001b  mov     ebx, 6D53674Eh
0x140040020  mov     rcx, [rdi]; P
0x140040023  test    rcx, rcx
0x140040026  jz      short loc_140040044
0x140040028  mov     edx, ebx; Tag
0x14004002a  call    cs:__imp_ExFreePoolWithTag
0x140040031  nop     dword ptr [rax+rax+00h]
0x140040036  mov     qword ptr [rdi], 0
0x14004003d  mov     dword ptr [rdi+10h], 0
0x140040044  mov     rcx, [rdi+8]; P
0x140040048  test    rcx, rcx
0x14004004b  jz      short loc_14004006A
0x14004004d  mov     edx, ebx; Tag
0x14004004f  call    cs:__imp_ExFreePoolWithTag
0x140040056  nop     dword ptr [rax+rax+00h]
0x14004005b  mov     qword ptr [rdi+8], 0
0x140040063  mov     dword ptr [rdi+14h], 0
0x14004006a  mov     rcx, [r12]; pMRxDeviceObject
0x14004006e  lea     r8, [r12+0C8h]; pWorkQueueItem
0x140040076  lea     r9, SmbCeCompleteSrvCallConstruction; Routine
0x14004007d  mov     [rsp+98h+pContext], r12; pContext
0x140040082  xor     edx, edx; WorkQueueType
0x140040084  call    cs:__imp_RxPostToWorkerThread
0x14004008b  nop     dword ptr [rax+rax+00h]
0x140040090  mov     rcx, [rsp+98h+P]; P
0x140040098  mov     edx, 6D536243h; Tag
0x14004009d  call    cs:__imp_ExFreePoolWithTag
0x1400400a4  nop     dword ptr [rax+rax+00h]
0x1400400a9  add     rsp, 58h
0x1400400ad  pop     r15
0x1400400af  pop     r14
0x1400400b1  pop     r13
0x1400400b3  pop     r12
0x1400400b5  pop     rdi
0x1400400b6  pop     rsi
0x1400400b7  pop     rbp
0x1400400b8  pop     rbx
0x1400400b9  retn
```
