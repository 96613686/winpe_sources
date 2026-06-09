# SmbCeTearDownServerEntry

- ea: `0x140044ae0`
- end: `0x140044dd1`
- name: `SmbCeTearDownServerEntry`
- size: `753`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140003480`
- `0x140013470`
- `0x14001c0f0`
- `0x1400267cc`
- `0x140026d60`
- `0x14002d320`
- `0x140034e10`
- `0x140037bb8`
- `0x140044ae0`
- `0x14004ace4`
- `0x14004b4cc`

## import_xrefs

- `ntoskrnl!PsDereferenceSiloContext` at `0x140044c81`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140044c81`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140044b93`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140044b93`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140044b80`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140044c69`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140044b80`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140044c69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044c06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044cb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044d09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044d2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044d57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044d7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044c06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044cb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044d09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044d2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044d57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044d7c`
- `rdbss!RxTearDownDiagnosticLogger` at `0x140044d9f`
- `rdbss!RxTearDownDiagnosticLogger` at `0x140044d9f`
- `rdbss!RxFinalizeSecurityContext` at `0x140044c9f`
- `rdbss!RxFinalizeSecurityContext` at `0x140044c9f`

## pseudocode

```c
void __fastcall SmbCeTearDownServerEntry(char *Context)
{
  __int64 v1; // rsi
  KIRQL v3; // r12
  __int64 v4; // rdx
  __int64 FirstVcEndpoint; // rdi
  char v6; // bp
  char *v7; // rcx
  char *v8; // r14
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx

  v1 = *((_QWORD *)Context + 3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      (unsigned int)WPP_948a51171ac53989b14c3e6a960354da_Traceguids,
      (_DWORD)Context,
      (__int64)(Context + 80));
  }
  v3 = SmbCeAcquireSpinLock(v1);
  FirstVcEndpoint = SmbCeGetFirstVcEndpoint(Context);
  if ( FirstVcEndpoint )
  {
    do
    {
      v6 = VctReferenceEndpointSafe(FirstVcEndpoint, v4);
      if ( v6 )
      {
        *(_DWORD *)(v1 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920), v3);
        ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(FirstVcEndpoint + 496));
        v3 = SmbCeAcquireSpinLock(v1);
      }
      v7 = *(char **)(FirstVcEndpoint + 536);
      v8 = 0;
      if ( v7 != Context + 616 )
        v8 = v7 - 536;
      if ( *(_DWORD *)(FirstVcEndpoint + 12) != 1 )
        _InterlockedDecrement((volatile signed __int32 *)Context + 158);
      SmbCeRemoveVcEndpointLite((ULONG_PTR)Context, FirstVcEndpoint);
      if ( v6 )
        VctDereferenceEndpoint((PVOID)FirstVcEndpoint);
      FirstVcEndpoint = (__int64)v8;
    }
    while ( v8 );
  }
  v9 = (void *)*((_QWORD *)Context + 71);
  if ( v9 )
  {
    ExFreePoolWithTag(v9, 0x6D53634Du);
    *((_QWORD *)Context + 71) = 0;
  }
  v10 = (void *)*((_QWORD *)Context + 72);
  if ( v10 )
  {
    SmbCeDereferenceConnectionInfo(v10);
    *((_QWORD *)Context + 72) = 0;
  }
  v11 = (void *)*((_QWORD *)Context + 75);
  if ( v11 )
  {
    SmbCeDeReferenceMoveClientAddrList(v11);
    *((_QWORD *)Context + 75) = 0;
  }
  *(_DWORD *)(v1 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920), v3);
  if ( *((_QWORD *)Context + 65) )
  {
    PsDereferenceSiloContext();
    *((_QWORD *)Context + 65) = 0;
  }
  RxFinalizeSecurityContext(Context + 224);
  v12 = (void *)*((_QWORD *)Context + 74);
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0x6D53634Du);
    *((_QWORD *)Context + 74) = 0;
  }
  v13 = (void *)*((_QWORD *)Context + 11);
  if ( v13 )
    ExFreePoolWithTag(v13, 0x6D537653u);
  *((_QWORD *)Context + 11) = 0;
  *((_DWORD *)Context + 20) = 0;
  v14 = (void *)*((_QWORD *)Context + 13);
  if ( v14 )
    ExFreePoolWithTag(v14, 0x6D536E44u);
  *((_QWORD *)Context + 13) = 0;
  *((_DWORD *)Context + 24) = 0;
  v15 = (void *)*((_QWORD *)Context + 15);
  if ( v15 )
    ExFreePoolWithTag(v15, 0x6D536E44u);
  *((_QWORD *)Context + 15) = 0;
  *((_DWORD *)Context + 28) = 0;
  v16 = (void *)*((_QWORD *)Context + 19);
  if ( v16 )
  {
    ExFreePoolWithTag(v16, 0x394D7852u);
    *((_QWORD *)Context + 19) = 0;
  }
  v17 = (void *)*((_QWORD *)Context + 81);
  if ( v17 )
    ExFreePoolWithTag(v17, 0x6D537653u);
  *((_QWORD *)Context + 81) = 0;
  *((_DWORD *)Context + 160) = 0;
  RxTearDownDiagnosticLogger(*((_QWORD *)Context + 2));
  SmbCeDecrementTeardownOpCounterAndUnblockWaiters(v1, Context, 0);
  SmbMmFreeObjectPool(Context);
}

```

## disassembly

```asm
0x140044ae0  push    rbx
0x140044ae2  push    rbp
0x140044ae3  push    rsi
0x140044ae4  push    rdi
0x140044ae5  push    r12
0x140044ae7  push    r14
0x140044ae9  push    r15
0x140044aeb  sub     rsp, 30h
0x140044aef  mov     rsi, [rcx+18h]
0x140044af3  mov     rbx, rcx
0x140044af6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044afd  lea     rax, WPP_GLOBAL_Control
0x140044b04  cmp     rcx, rax
0x140044b07  jz      short loc_140044B37
0x140044b09  mov     eax, [rcx+2Ch]
0x140044b0c  test    al, 40h
0x140044b0e  jz      short loc_140044B37
0x140044b10  cmp     byte ptr [rcx+29h], 2
0x140044b14  jb      short loc_140044B37
0x140044b16  mov     rcx, [rcx+18h]
0x140044b1a  lea     rax, [rbx+50h]
0x140044b1e  mov     edx, 1Ch
0x140044b23  mov     [rsp+68h+var_48], rax
0x140044b28  mov     r9, rbx
0x140044b2b  lea     r8, WPP_948a51171ac53989b14c3e6a960354da_Traceguids
0x140044b32  call    WPP_SF_qZ
0x140044b37  mov     rcx, rsi
0x140044b3a  call    SmbCeAcquireSpinLock
0x140044b3f  mov     rcx, rbx
0x140044b42  mov     r12b, al
0x140044b45  call    SmbCeGetFirstVcEndpoint
0x140044b4a  mov     rdi, rax
0x140044b4d  test    rax, rax
0x140044b50  jz      loc_140044BF3
0x140044b56  lea     r15, [rbx+268h]
0x140044b5d  mov     rcx, rdi
0x140044b60  call    VctReferenceEndpointSafe
0x140044b65  mov     bpl, al
0x140044b68  test    al, al
0x140044b6a  jz      short loc_140044BAA
0x140044b6c  lea     rcx, [rsi+780h]; SpinLock
0x140044b73  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x140044b7d  mov     dl, r12b; OldIrql
0x140044b80  call    cs:__imp_ExReleaseSpinLockExclusive
0x140044b87  nop     dword ptr [rax+rax+00h]
0x140044b8c  lea     rcx, [rdi+1F0h]; RunRef
0x140044b93  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140044b9a  nop     dword ptr [rax+rax+00h]
0x140044b9f  mov     rcx, rsi
0x140044ba2  call    SmbCeAcquireSpinLock
0x140044ba7  mov     r12b, al
0x140044baa  mov     rcx, [rdi+218h]
0x140044bb1  xor     r14d, r14d
0x140044bb4  cmp     rcx, r15
0x140044bb7  lea     rax, [rcx-218h]
0x140044bbe  cmovnz  r14, rax
0x140044bc2  cmp     dword ptr [rdi+0Ch], 1
0x140044bc6  jz      short loc_140044BCF
0x140044bc8  lock dec dword ptr [rbx+278h]
0x140044bcf  mov     rdx, rdi
0x140044bd2  mov     rcx, rbx; BugCheckParameter2
0x140044bd5  call    SmbCeRemoveVcEndpointLite
0x140044bda  test    bpl, bpl
0x140044bdd  jz      short loc_140044BE7
0x140044bdf  mov     rcx, rdi; pContext
0x140044be2  call    VctDereferenceEndpoint
0x140044be7  mov     rdi, r14
0x140044bea  test    r14, r14
0x140044bed  jnz     loc_140044B5D
0x140044bf3  mov     rcx, [rbx+238h]; P
0x140044bfa  mov     edi, 6D53634Dh
0x140044bff  test    rcx, rcx
0x140044c02  jz      short loc_140044C1D
0x140044c04  mov     edx, edi; Tag
0x140044c06  call    cs:__imp_ExFreePoolWithTag
0x140044c0d  nop     dword ptr [rax+rax+00h]
0x140044c12  mov     qword ptr [rbx+238h], 0
0x140044c1d  mov     rcx, [rbx+240h]; P
0x140044c24  test    rcx, rcx
0x140044c27  jz      short loc_140044C39
0x140044c29  call    SmbCeDereferenceConnectionInfo
0x140044c2e  mov     qword ptr [rbx+240h], 0
0x140044c39  mov     rcx, [rbx+258h]; P
0x140044c40  test    rcx, rcx
0x140044c43  jz      short loc_140044C55
0x140044c45  call    SmbCeDeReferenceMoveClientAddrList
0x140044c4a  mov     qword ptr [rbx+258h], 0
0x140044c55  lea     rcx, [rsi+780h]; SpinLock
0x140044c5c  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x140044c66  mov     dl, r12b; OldIrql
0x140044c69  call    cs:__imp_ExReleaseSpinLockExclusive
0x140044c70  nop     dword ptr [rax+rax+00h]
0x140044c75  mov     rcx, [rbx+208h]
0x140044c7c  test    rcx, rcx
0x140044c7f  jz      short loc_140044C98
0x140044c81  call    cs:__imp_PsDereferenceSiloContext
0x140044c88  nop     dword ptr [rax+rax+00h]
0x140044c8d  mov     qword ptr [rbx+208h], 0
0x140044c98  lea     rcx, [rbx+0E0h]
0x140044c9f  call    cs:__imp_RxFinalizeSecurityContext
0x140044ca6  nop     dword ptr [rax+rax+00h]
0x140044cab  mov     rcx, [rbx+250h]; P
0x140044cb2  test    rcx, rcx
0x140044cb5  jz      short loc_140044CD0
0x140044cb7  mov     edx, edi; Tag
0x140044cb9  call    cs:__imp_ExFreePoolWithTag
0x140044cc0  nop     dword ptr [rax+rax+00h]
0x140044cc5  mov     qword ptr [rbx+250h], 0
0x140044cd0  mov     rcx, [rbx+58h]; P
0x140044cd4  mov     ebp, 6D537653h
0x140044cd9  test    rcx, rcx
0x140044cdc  jz      short loc_140044CEC
0x140044cde  mov     edx, ebp; Tag
0x140044ce0  call    cs:__imp_ExFreePoolWithTag
0x140044ce7  nop     dword ptr [rax+rax+00h]
0x140044cec  xor     eax, eax
0x140044cee  mov     qword ptr [rbx+58h], 0
0x140044cf6  mov     [rbx+50h], eax
0x140044cf9  mov     edi, 6D536E44h
0x140044cfe  mov     rcx, [rbx+68h]; P
0x140044d02  test    rcx, rcx
0x140044d05  jz      short loc_140044D15
0x140044d07  mov     edx, edi; Tag
0x140044d09  call    cs:__imp_ExFreePoolWithTag
0x140044d10  nop     dword ptr [rax+rax+00h]
0x140044d15  xor     eax, eax
0x140044d17  mov     qword ptr [rbx+68h], 0
0x140044d1f  mov     [rbx+60h], eax
0x140044d22  mov     rcx, [rbx+78h]; P
0x140044d26  test    rcx, rcx
0x140044d29  jz      short loc_140044D39
0x140044d2b  mov     edx, edi; Tag
0x140044d2d  call    cs:__imp_ExFreePoolWithTag
0x140044d34  nop     dword ptr [rax+rax+00h]
0x140044d39  xor     eax, eax
0x140044d3b  mov     qword ptr [rbx+78h], 0
0x140044d43  mov     [rbx+70h], eax
0x140044d46  mov     rcx, [rbx+98h]; P
0x140044d4d  test    rcx, rcx
0x140044d50  jz      short loc_140044D6E
0x140044d52  mov     edx, 394D7852h; Tag
0x140044d57  call    cs:__imp_ExFreePoolWithTag
0x140044d5e  nop     dword ptr [rax+rax+00h]
0x140044d63  mov     qword ptr [rbx+98h], 0
0x140044d6e  mov     rcx, [rbx+288h]; P
0x140044d75  test    rcx, rcx
0x140044d78  jz      short loc_140044D88
0x140044d7a  mov     edx, ebp; Tag
0x140044d7c  call    cs:__imp_ExFreePoolWithTag
0x140044d83  nop     dword ptr [rax+rax+00h]
0x140044d88  xor     eax, eax
0x140044d8a  mov     qword ptr [rbx+288h], 0
0x140044d95  mov     [rbx+280h], eax
0x140044d9b  mov     rcx, [rbx+10h]
0x140044d9f  call    cs:__imp_RxTearDownDiagnosticLogger
0x140044da6  nop     dword ptr [rax+rax+00h]
0x140044dab  xor     r8d, r8d
0x140044dae  mov     rdx, rbx
0x140044db1  mov     rcx, rsi
0x140044db4  call    SmbCeDecrementTeardownOpCounterAndUnblockWaiters
0x140044db9  mov     rcx, rbx
0x140044dbc  call    SmbMmFreeObjectPool
0x140044dc1  add     rsp, 30h
0x140044dc5  pop     r15
0x140044dc7  pop     r14
0x140044dc9  pop     r12
0x140044dcb  pop     rdi
0x140044dcc  pop     rsi
0x140044dcd  pop     rbp
0x140044dce  pop     rbx
0x140044dcf  retn
```
