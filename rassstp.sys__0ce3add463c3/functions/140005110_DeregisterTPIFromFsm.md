# DeregisterTPIFromFsm

- ea: `0x140005110`
- end: `0x140005392`
- name: `DeregisterTPIFromFsm`
- size: `642`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400031f0`
- `0x1400034d0`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140002c08`
- `0x140005110`
- `0x14000f3ec`
- `0x140016cf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005343`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005343`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000515f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400051c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000515f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400051c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000517a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005188`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000523b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000517a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005188`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000523b`
- `ntoskrnl!KeLowerIrql` at `0x14000521d`
- `ntoskrnl!KeLowerIrql` at `0x14000521d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005252`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140005252`
- `ntoskrnl!IoFreeWorkItem` at `0x14000532b`
- `ntoskrnl!IoFreeWorkItem` at `0x14000532b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400051a9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400051a9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400051ea`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400051ea`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005201`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005201`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140005273`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400052c6`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140005273`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400052c6`

## pseudocode

```c
void DeregisterTPIFromFsm()
{
  KSPIN_LOCK *v0; // rbx
  KIRQL v1; // al
  bool v2; // zf
  KIRQL v3; // al
  KIRQL v4; // si
  __int64 v5; // rdi
  void *v6; // rcx
  void *v7; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  v0 = (KSPIN_LOCK *)((char *)SstpFsmGlobalInfo + 24);
  *(_BYTE *)SstpFsmGlobalInfo = 0;
  v1 = KeAcquireSpinLockRaiseToDpc(v0);
  v2 = *((_DWORD *)v0 + 2) == 0;
  *((_BYTE *)v0 + 40) = 0;
  if ( v2 )
  {
    KeReleaseSpinLock(v0, v1);
  }
  else
  {
    KeReleaseSpinLock(v0, v1);
    KeWaitForSingleObject(v0 + 2, Executive, 0, 0, 0);
  }
  while ( 1 )
  {
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpFsmGlobalInfo + 9);
    v4 = v3;
    v5 = *((_QWORD *)SstpFsmGlobalInfo + 10);
    if ( (PVOID)v5 == (char *)SstpFsmGlobalInfo + 80 )
      break;
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 32));
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v5 + 16));
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)SstpFsmGlobalInfo + 9);
    MoveToCallDisconnectedState(v5, 0, 0);
    KeLowerIrql(v4);
    DereferenceRefCount(v5 + 32);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SstpFsmGlobalInfo + 9, v3);
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
  v6 = (void *)*((_QWORD *)SstpFsmGlobalInfo + 33);
  if ( v6 )
  {
    BCryptCloseAlgorithmProvider(v6, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    }
  }
  v7 = (void *)*((_QWORD *)SstpFsmGlobalInfo + 32);
  if ( v7 )
  {
    BCryptCloseAlgorithmProvider(v7, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    }
  }
  if ( *((_BYTE *)SstpFsmGlobalInfo + 12) )
    FipsDeInit((char *)SstpFsmGlobalInfo + 272);
  IoFreeWorkItem(*((PIO_WORKITEM *)SstpFsmGlobalInfo + 53));
  ExFreePoolWithTag(SstpFsmGlobalInfo, 0x69676653u);
  SstpFsmGlobalInfo = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 145, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x140005110  push    rbx
0x140005112  push    rsi
0x140005113  push    rdi
0x140005114  push    r12
0x140005116  sub     rsp, 38h
0x14000511a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005121  lea     r12, WPP_GLOBAL_Control
0x140005128  cmp     rcx, r12
0x14000512b  jz      short loc_14000514E
0x14000512d  mov     eax, [rcx+2Ch]
0x140005130  and     eax, 84h
0x140005135  cmp     al, 84h
0x140005137  jnz     short loc_14000514E
0x140005139  mov     rcx, [rcx+18h]
0x14000513d  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140005144  mov     edx, 8Eh
0x140005149  call    WPP_SF_
0x14000514e  mov     rax, cs:SstpFsmGlobalInfo
0x140005155  lea     rbx, [rax+18h]
0x140005159  mov     byte ptr [rax], 0
0x14000515c  mov     rcx, rbx; SpinLock
0x14000515f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005166  nop     dword ptr [rax+rax+00h]
0x14000516b  cmp     dword ptr [rbx+8], 0
0x14000516f  mov     rcx, rbx; SpinLock
0x140005172  mov     dl, al; NewIrql
0x140005174  mov     byte ptr [rbx+28h], 0
0x140005178  jnz     short loc_140005188
0x14000517a  call    cs:__imp_KeReleaseSpinLock
0x140005181  nop     dword ptr [rax+rax+00h]
0x140005186  jmp     short loc_1400051B5
0x140005188  call    cs:__imp_KeReleaseSpinLock
0x14000518f  nop     dword ptr [rax+rax+00h]
0x140005194  lea     rcx, [rbx+10h]; Object
0x140005198  mov     [rsp+58h+Timeout], 0; Timeout
0x1400051a1  xor     r9d, r9d; Alertable
0x1400051a4  xor     r8d, r8d; WaitMode
0x1400051a7  xor     edx, edx; WaitReason
0x1400051a9  call    cs:__imp_KeWaitForSingleObject
0x1400051b0  nop     dword ptr [rax+rax+00h]
0x1400051b5  mov     rcx, cs:SstpFsmGlobalInfo
0x1400051bc  add     rcx, 48h ; 'H'; SpinLock
0x1400051c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400051c7  nop     dword ptr [rax+rax+00h]
0x1400051cc  mov     rcx, cs:SstpFsmGlobalInfo
0x1400051d3  mov     sil, al
0x1400051d6  lea     rdx, [rcx+50h]
0x1400051da  mov     rdi, [rdx]
0x1400051dd  cmp     rdi, rdx
0x1400051e0  jz      short loc_140005234
0x1400051e2  lock inc dword ptr [rdi+20h]
0x1400051e6  lea     rcx, [rdi+10h]; SpinLock
0x1400051ea  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400051f1  nop     dword ptr [rax+rax+00h]
0x1400051f6  mov     rcx, cs:SstpFsmGlobalInfo
0x1400051fd  add     rcx, 48h ; 'H'; SpinLock
0x140005201  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005208  nop     dword ptr [rax+rax+00h]
0x14000520d  xor     r8d, r8d
0x140005210  xor     edx, edx
0x140005212  mov     rcx, rdi
0x140005215  call    MoveToCallDisconnectedState
0x14000521a  mov     cl, sil; NewIrql
0x14000521d  call    cs:__imp_KeLowerIrql
0x140005224  nop     dword ptr [rax+rax+00h]
0x140005229  lea     rcx, [rdi+20h]
0x14000522d  call    DereferenceRefCount
0x140005232  jmp     short loc_1400051B5
0x140005234  add     rcx, 48h ; 'H'; SpinLock
0x140005238  mov     dl, sil; NewIrql
0x14000523b  call    cs:__imp_KeReleaseSpinLock
0x140005242  nop     dword ptr [rax+rax+00h]
0x140005247  mov     rcx, cs:SstpFsmGlobalInfo
0x14000524e  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140005252  call    cs:__imp_ExDeleteNPagedLookasideList
0x140005259  nop     dword ptr [rax+rax+00h]
0x14000525e  mov     rax, cs:SstpFsmGlobalInfo
0x140005265  mov     rcx, [rax+108h]; hAlgorithm
0x14000526c  test    rcx, rcx
0x14000526f  jz      short loc_1400052B1
0x140005271  xor     edx, edx; dwFlags
0x140005273  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000527a  nop     dword ptr [rax+rax+00h]
0x14000527f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005286  cmp     rcx, r12
0x140005289  jz      short loc_1400052B1
0x14000528b  mov     edx, [rcx+2Ch]
0x14000528e  test    dl, 4
0x140005291  jz      short loc_1400052B1
0x140005293  cmp     byte ptr [rcx+29h], 2
0x140005297  jb      short loc_1400052B1
0x140005299  mov     rcx, [rcx+18h]
0x14000529d  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400052a4  mov     edx, 8Fh
0x1400052a9  mov     r9d, eax
0x1400052ac  call    WPP_SF_d
0x1400052b1  mov     rax, cs:SstpFsmGlobalInfo
0x1400052b8  mov     rcx, [rax+100h]; hAlgorithm
0x1400052bf  test    rcx, rcx
0x1400052c2  jz      short loc_140005304
0x1400052c4  xor     edx, edx; dwFlags
0x1400052c6  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400052cd  nop     dword ptr [rax+rax+00h]
0x1400052d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052d9  cmp     rcx, r12
0x1400052dc  jz      short loc_140005304
0x1400052de  mov     edx, [rcx+2Ch]
0x1400052e1  test    dl, 4
0x1400052e4  jz      short loc_140005304
0x1400052e6  cmp     byte ptr [rcx+29h], 2
0x1400052ea  jb      short loc_140005304
0x1400052ec  mov     rcx, [rcx+18h]
0x1400052f0  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400052f7  mov     edx, 90h
0x1400052fc  mov     r9d, eax
0x1400052ff  call    WPP_SF_d
0x140005304  mov     rcx, cs:SstpFsmGlobalInfo
0x14000530b  cmp     byte ptr [rcx+0Ch], 0
0x14000530f  jz      short loc_14000531D
0x140005311  add     rcx, 110h
0x140005318  call    FipsDeInit
0x14000531d  mov     rcx, cs:SstpFsmGlobalInfo
0x140005324  mov     rcx, [rcx+1A8h]; IoWorkItem
0x14000532b  call    cs:__imp_IoFreeWorkItem
0x140005332  nop     dword ptr [rax+rax+00h]
0x140005337  mov     rcx, cs:SstpFsmGlobalInfo; P
0x14000533e  mov     edx, 69676653h; Tag
0x140005343  call    cs:__imp_ExFreePoolWithTag
0x14000534a  nop     dword ptr [rax+rax+00h]
0x14000534f  mov     cs:SstpFsmGlobalInfo, 0
0x14000535a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005361  cmp     rcx, r12
0x140005364  jz      short loc_140005387
0x140005366  mov     eax, [rcx+2Ch]
0x140005369  and     eax, 84h
0x14000536e  cmp     al, 84h
0x140005370  jnz     short loc_140005387
0x140005372  mov     rcx, [rcx+18h]
0x140005376  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14000537d  mov     edx, 91h
0x140005382  call    WPP_SF_
0x140005387  add     rsp, 38h
0x14000538b  pop     r12
0x14000538d  pop     rdi
0x14000538e  pop     rsi
0x14000538f  pop     rbx
0x140005390  retn
```
