# SmbCeTearDownBindingObject

- ea: `0x140031500`
- end: `0x140031940`
- name: `SmbCeTearDownBindingObject`
- size: `1088`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140003040`
- `0x140013470`
- `0x140014400`
- `0x14001c0f0`
- `0x140026d60`
- `0x140031500`
- `0x1400383d0`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003178a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003178a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140031724`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140031724`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400317cd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400317cd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400316d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400316d7`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003165e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003165e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400315f7`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400315f7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140031606`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140031606`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031820`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003187e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400318c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031820`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003187e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400318c3`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14003179d`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14003179d`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x1400316f4`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x1400316f4`
- `rdbss!RxFinalizeSecurityContext` at `0x1400317dd`
- `rdbss!RxFinalizeSecurityContext` at `0x1400317dd`
- `ksecdd!FreeCredentialsHandle` at `0x140031750`
- `ksecdd!FreeCredentialsHandle` at `0x140031750`
- `ksecdd!DeleteSecurityContext` at `0x140031776`
- `ksecdd!DeleteSecurityContext` at `0x140031776`
- `ksecdd!BCryptDestroyKey` at `0x14003186a`
- `ksecdd!BCryptDestroyKey` at `0x1400318af`
- `ksecdd!BCryptDestroyKey` at `0x14003186a`
- `ksecdd!BCryptDestroyKey` at `0x1400318af`
- `ksecdd!BCryptDestroyHash` at `0x1400317ff`
- `ksecdd!BCryptDestroyHash` at `0x1400317ff`

## pseudocode

```c
void __fastcall SmbCeTearDownBindingObject(char *Context)
{
  __int64 v1; // r13
  __int64 v3; // rcx
  KIRQL v4; // si
  unsigned int CurrentThreadId; // eax
  _QWORD *v6; // rdx
  __int64 v7; // r9
  _QWORD *v8; // r8
  __int64 v9; // rdi
  char v10; // bp
  __int64 v11; // r15
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // r14
  _QWORD *v15; // rsi
  void *v16; // rcx
  void *v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // rsi
  ULONG_PTR v20; // rcx

  v1 = *((_QWORD *)Context + 3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids, Context);
  }
  v3 = *((_QWORD *)Context + 49);
  *((_DWORD *)Context + 3) = 10;
  if ( v3 )
  {
    if ( Context[440] )
    {
      VctSetConnectionKeepAlive(v3, 0, 0);
      Context[440] = 0;
    }
    if ( Context[441] )
    {
      VctSetConnectionKeepAlive(*((_QWORD *)Context + 49), 0, 1);
      Context[441] = 0;
    }
    if ( Context[442] )
    {
      VctSetConnectionKeepAlive(*((_QWORD *)Context + 49), 0, 2);
      Context[442] = 0;
    }
    if ( Context[443] )
    {
      VctSetConnectionKeepAlive(*((_QWORD *)Context + 49), 0, 3);
      Context[443] = 0;
    }
    v4 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920));
    CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
    v6 = Context + 416;
    *(_DWORD *)(v1 + 2352) = CurrentThreadId;
    v7 = *((_QWORD *)Context + 52);
    if ( *(char **)(v7 + 8) != Context + 416 || (v8 = (_QWORD *)*((_QWORD *)Context + 53), (_QWORD *)*v8 != v6) )
      __fastfail(3u);
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    *((_QWORD *)Context + 53) = Context + 416;
    *v6 = v6;
    *(_DWORD *)(v1 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920), v4);
    VctDereferenceEndpoint(*((PVOID *)Context + 49));
    *((_QWORD *)Context + 49) = 0;
  }
  v9 = *((_QWORD *)Context + 54);
  v10 = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids, Context);
  }
  ExAcquirePushLockExclusiveEx(Context + 456, 0);
  if ( v9 && *(_QWORD *)(v9 + 520) )
  {
    if ( !RxReferenceSiloAndAcquireRundown() )
    {
      v14 = Context + 480;
      v15 = Context + 464;
      goto LABEL_37;
    }
    v12 = *(_QWORD *)(v9 + 520);
    if ( v12 )
      v13 = *(_QWORD *)(v12 + 40);
    else
      v13 = 0;
    v11 = PsAttachSiloToCurrentThread(v13);
    v10 = 1;
  }
  v14 = Context + 480;
  if ( *((_QWORD *)Context + 60) != -1 && *((_QWORD *)Context + 61) != -1 )
    FreeCredentialsHandle((PCredHandle)Context + 30);
  v15 = Context + 464;
  if ( *((_QWORD *)Context + 58) != -1 && *((_QWORD *)Context + 59) != -1 )
    DeleteSecurityContext((PCtxtHandle)Context + 29);
  if ( v10 )
  {
    PsDetachSiloFromCurrentThread(v11);
    RxDereferenceSiloAndReleaseRundown(*(_QWORD *)(v9 + 520));
  }
LABEL_37:
  *((_QWORD *)Context + 61) = -1;
  *v14 = -1;
  *((_QWORD *)Context + 59) = -1;
  *v15 = -1;
  ExReleasePushLockExclusiveEx(Context + 456, 0);
  RxFinalizeSecurityContext(Context + 96);
  v16 = (void *)*((_QWORD *)Context + 62);
  if ( v16 )
  {
    BCryptDestroyHash(v16);
    v17 = (void *)*((_QWORD *)Context + 63);
    *((_QWORD *)Context + 62) = 0;
    ExFreePoolWithTag(v17, 0x6D536F48u);
    *((_QWORD *)Context + 63) = 0;
  }
  v18 = *((_QWORD *)Context + 66);
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v18 )
        BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)v18);
      ExFreePoolWithTag((PVOID)v18, 0x2332534Cu);
    }
    *((_QWORD *)Context + 66) = 0;
  }
  v19 = *((_QWORD *)Context + 67);
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v19 )
        BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)v19);
      ExFreePoolWithTag((PVOID)v19, 0x2332534Cu);
    }
    *((_QWORD *)Context + 67) = 0;
  }
  v20 = *((_QWORD *)Context + 54);
  if ( v20 )
  {
    SmbCeDereferenceServerEntryEx(v20);
    *((_QWORD *)Context + 54) = 0;
  }
  SmbCeDecrementTeardownOpCounterAndUnblockWaiters(v1, Context, 6);
  memset(Context, 0, 0x240u);
  SmbMmFreeObjectPool(Context);
}

```

## disassembly

```asm
0x140031500  push    rbx
0x140031502  push    r13
0x140031504  push    r14
0x140031506  sub     rsp, 30h
0x14003150a  mov     r13, [rcx+18h]
0x14003150e  mov     rbx, rcx
0x140031511  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140031518  lea     r14, WPP_GLOBAL_Control
0x14003151f  cmp     rcx, r14
0x140031522  jz      short loc_140031549
0x140031524  mov     eax, [rcx+2Ch]
0x140031527  test    al, 40h
0x140031529  jz      short loc_140031549
0x14003152b  cmp     byte ptr [rcx+29h], 2
0x14003152f  jb      short loc_140031549
0x140031531  mov     rcx, [rcx+18h]
0x140031535  lea     r8, WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids
0x14003153c  mov     edx, 10h
0x140031541  mov     r9, rbx
0x140031544  call    WPP_SF_q
0x140031549  mov     rcx, [rbx+188h]
0x140031550  mov     [rsp+48h+arg_8], rsi
0x140031555  mov     [rsp+48h+arg_10], rdi
0x14003155a  mov     dword ptr [rbx+0Ch], 0Ah
0x140031561  test    rcx, rcx
0x140031564  jz      loc_140031681
0x14003156a  cmp     byte ptr [rbx+1B8h], 0
0x140031571  jz      short loc_140031584
0x140031573  xor     r8d, r8d
0x140031576  xor     edx, edx
0x140031578  call    VctSetConnectionKeepAlive
0x14003157d  mov     byte ptr [rbx+1B8h], 0
0x140031584  cmp     byte ptr [rbx+1B9h], 0
0x14003158b  jz      short loc_1400315A8
0x14003158d  mov     rcx, [rbx+188h]
0x140031594  xor     edx, edx
0x140031596  mov     r8d, 1
0x14003159c  call    VctSetConnectionKeepAlive
0x1400315a1  mov     byte ptr [rbx+1B9h], 0
0x1400315a8  cmp     byte ptr [rbx+1BAh], 0
0x1400315af  jz      short loc_1400315CC
0x1400315b1  mov     rcx, [rbx+188h]
0x1400315b8  xor     edx, edx
0x1400315ba  mov     r8d, 2
0x1400315c0  call    VctSetConnectionKeepAlive
0x1400315c5  mov     byte ptr [rbx+1BAh], 0
0x1400315cc  cmp     byte ptr [rbx+1BBh], 0
0x1400315d3  jz      short loc_1400315F0
0x1400315d5  mov     rcx, [rbx+188h]
0x1400315dc  xor     edx, edx
0x1400315de  mov     r8d, 3
0x1400315e4  call    VctSetConnectionKeepAlive
0x1400315e9  mov     byte ptr [rbx+1BBh], 0
0x1400315f0  lea     rcx, [r13+780h]; SpinLock
0x1400315f7  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400315fe  nop     dword ptr [rax+rax+00h]
0x140031603  movzx   esi, al
0x140031606  call    cs:__imp_PsGetCurrentThreadId
0x14003160d  nop     dword ptr [rax+rax+00h]
0x140031612  lea     rdx, [rbx+1A0h]
0x140031619  mov     [r13+930h], eax
0x140031620  mov     r9, [rdx]
0x140031623  cmp     [r9+8], rdx
0x140031627  jnz     loc_14003171B
0x14003162d  mov     r8, [rdx+8]
0x140031631  cmp     [r8], rdx
0x140031634  jnz     loc_14003171B
0x14003163a  mov     [r8], r9
0x14003163d  lea     rcx, [r13+780h]; SpinLock
0x140031644  mov     [r9+8], r8
0x140031648  mov     [rdx+8], rdx
0x14003164c  mov     [rdx], rdx
0x14003164f  movzx   edx, sil; OldIrql
0x140031653  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14003165e  call    cs:__imp_ExReleaseSpinLockExclusive
0x140031665  nop     dword ptr [rax+rax+00h]
0x14003166a  mov     rcx, [rbx+188h]; pContext
0x140031671  call    VctDereferenceEndpoint
0x140031676  mov     qword ptr [rbx+188h], 0
0x140031681  mov     rdi, [rbx+1B0h]
0x140031688  mov     [rsp+48h+arg_0], rbp
0x14003168d  xor     bpl, bpl
0x140031690  mov     [rsp+48h+var_20], r12
0x140031695  mov     [rsp+48h+var_28], r15
0x14003169a  xor     r15d, r15d
0x14003169d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400316a4  cmp     rcx, r14
0x1400316a7  jz      short loc_1400316CE
0x1400316a9  mov     eax, [rcx+2Ch]
0x1400316ac  test    al, 40h
0x1400316ae  jz      short loc_1400316CE
0x1400316b0  cmp     byte ptr [rcx+29h], 4
0x1400316b4  jb      short loc_1400316CE
0x1400316b6  mov     rcx, [rcx+18h]
0x1400316ba  lea     r8, WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids
0x1400316c1  mov     edx, 11h
0x1400316c6  mov     r9, rbx
0x1400316c9  call    WPP_SF_q
0x1400316ce  xor     edx, edx
0x1400316d0  lea     rcx, [rbx+1C8h]
0x1400316d7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400316de  nop     dword ptr [rax+rax+00h]
0x1400316e3  test    rdi, rdi
0x1400316e6  jz      short loc_140031736
0x1400316e8  mov     rcx, [rdi+208h]
0x1400316ef  test    rcx, rcx
0x1400316f2  jz      short loc_140031736
0x1400316f4  call    cs:__imp_RxReferenceSiloAndAcquireRundown
0x1400316fb  nop     dword ptr [rax+rax+00h]
0x140031700  test    rax, rax
0x140031703  jz      loc_140031835
0x140031709  mov     rax, [rdi+208h]
0x140031710  test    rax, rax
0x140031713  jz      short loc_140031722
0x140031715  mov     rcx, [rax+28h]
0x140031719  jmp     short loc_140031724
0x14003171b  mov     ecx, 3
0x140031720  int     29h; Win8: RtlFailFast(ecx)
0x140031722  xor     ecx, ecx
0x140031724  call    cs:__imp_PsAttachSiloToCurrentThread
0x14003172b  nop     dword ptr [rax+rax+00h]
0x140031730  mov     r15, rax
0x140031733  mov     bpl, 1
0x140031736  lea     r14, [rbx+1E0h]
0x14003173d  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x140031741  jz      short loc_14003175C
0x140031743  cmp     qword ptr [rbx+1E8h], 0FFFFFFFFFFFFFFFFh
0x14003174b  jz      short loc_14003175C
0x14003174d  mov     rcx, r14; phCredential
0x140031750  call    cs:__imp_FreeCredentialsHandle
0x140031757  nop     dword ptr [rax+rax+00h]
0x14003175c  lea     rsi, [rbx+1D0h]
0x140031763  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140031767  jz      short loc_140031782
0x140031769  cmp     qword ptr [rbx+1D8h], 0FFFFFFFFFFFFFFFFh
0x140031771  jz      short loc_140031782
0x140031773  mov     rcx, rsi; phContext
0x140031776  call    cs:__imp_DeleteSecurityContext
0x14003177d  nop     dword ptr [rax+rax+00h]
0x140031782  test    bpl, bpl
0x140031785  jz      short loc_1400317A9
0x140031787  mov     rcx, r15
0x14003178a  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140031791  nop     dword ptr [rax+rax+00h]
0x140031796  mov     rcx, [rdi+208h]
0x14003179d  call    cs:__imp_RxDereferenceSiloAndReleaseRundown
0x1400317a4  nop     dword ptr [rax+rax+00h]
0x1400317a9  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1400317b0  lea     rcx, [rbx+1C8h]
0x1400317b7  xor     edx, edx
0x1400317b9  mov     [rbx+1E8h], rdi
0x1400317c0  mov     [r14], rdi
0x1400317c3  mov     [rbx+1D8h], rdi
0x1400317ca  mov     [rsi], rdi
0x1400317cd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400317d4  nop     dword ptr [rax+rax+00h]
0x1400317d9  lea     rcx, [rbx+60h]
0x1400317dd  call    cs:__imp_RxFinalizeSecurityContext
0x1400317e4  nop     dword ptr [rax+rax+00h]
0x1400317e9  mov     rcx, [rbx+1F0h]; hHash
0x1400317f0  mov     r15, [rsp+48h+var_28]
0x1400317f5  mov     r12, [rsp+48h+var_20]
0x1400317fa  test    rcx, rcx
0x1400317fd  jz      short loc_140031848
0x1400317ff  call    cs:__imp_BCryptDestroyHash
0x140031806  nop     dword ptr [rax+rax+00h]
0x14003180b  mov     rcx, [rbx+1F8h]; P
0x140031812  xor     ebp, ebp
0x140031814  mov     edx, 6D536F48h; Tag
0x140031819  mov     [rbx+1F0h], rbp
0x140031820  call    cs:__imp_ExFreePoolWithTag
0x140031827  nop     dword ptr [rax+rax+00h]
0x14003182c  mov     [rbx+1F8h], rbp
0x140031833  jmp     short loc_14003184A
0x140031835  lea     r14, [rbx+1E0h]
0x14003183c  lea     rsi, [rbx+1D0h]
0x140031843  jmp     loc_1400317A9
0x140031848  xor     ebp, ebp
0x14003184a  mov     rsi, [rbx+210h]
0x140031851  test    rsi, rsi
0x140031854  jz      short loc_140031891
0x140031856  mov     eax, edi
0x140031858  lock xadd [rsi+10h], eax
0x14003185d  cmp     eax, 1
0x140031860  jnz     short loc_14003188A
0x140031862  mov     rcx, [rsi]; hKey
0x140031865  test    rcx, rcx
0x140031868  jz      short loc_140031876
0x14003186a  call    cs:__imp_BCryptDestroyKey
0x140031871  nop     dword ptr [rax+rax+00h]
0x140031876  mov     edx, 2332534Ch; Tag
0x14003187b  mov     rcx, rsi; P
0x14003187e  call    cs:__imp_ExFreePoolWithTag
0x140031885  nop     dword ptr [rax+rax+00h]
0x14003188a  mov     [rbx+210h], rbp
0x140031891  mov     rsi, [rbx+218h]
0x140031898  test    rsi, rsi
0x14003189b  jz      short loc_1400318D6
0x14003189d  lock xadd [rsi+10h], edi
0x1400318a2  cmp     edi, 1
0x1400318a5  jnz     short loc_1400318CF
0x1400318a7  mov     rcx, [rsi]; hKey
0x1400318aa  test    rcx, rcx
0x1400318ad  jz      short loc_1400318BB
0x1400318af  call    cs:__imp_BCryptDestroyKey
0x1400318b6  nop     dword ptr [rax+rax+00h]
0x1400318bb  mov     edx, 2332534Ch; Tag
0x1400318c0  mov     rcx, rsi; P
0x1400318c3  call    cs:__imp_ExFreePoolWithTag
0x1400318ca  nop     dword ptr [rax+rax+00h]
0x1400318cf  mov     [rbx+218h], rbp
0x1400318d6  mov     rcx, [rbx+1B0h]; BugCheckParameter2
0x1400318dd  test    rcx, rcx
0x1400318e0  jz      short loc_1400318F0
0x1400318e2  xor     edx, edx
0x1400318e4  call    SmbCeDereferenceServerEntryEx
0x1400318e9  mov     [rbx+1B0h], rbp
0x1400318f0  mov     r8d, 6
0x1400318f6  mov     rdx, rbx
0x1400318f9  mov     rcx, r13
0x1400318fc  call    SmbCeDecrementTeardownOpCounterAndUnblockWaiters
0x140031901  xor     edx, edx; Val
0x140031903  mov     r8d, 240h; Size
0x140031909  mov     rcx, rbx; void *
0x14003190c  call    memset
0x140031911  mov     rcx, rbx
0x140031914  call    SmbMmFreeObjectPool
0x140031919  mov     rbp, [rsp+48h+arg_0]
0x14003191e  mov     rdi, [rsp+48h+arg_10]
0x140031923  mov     rsi, [rsp+48h+arg_8]
0x140031928  add     rsp, 30h
0x14003192c  pop     r14
0x14003192e  pop     r13
0x140031930  pop     rbx
0x140031931  retn
```
