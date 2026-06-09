# RefsModifySecurity(_IRP_CONTEXT *,_FCB *,ulong *,void *)

- ea: `0x1403063e0`
- end: `0x1403066be`
- name: `?RefsModifySecurity@@YAJPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAKPEAX@Z`
- size: `734`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _FCB *, PSECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR ModificationDescriptor)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402cacc0`
- `0x140305020`
- `0x140306d6c`

## callees

- `0x140076ad0`
- `0x1400862c0`
- `0x140087380`
- `0x140093bc0`
- `0x1400d0fd8`
- `0x14028c008`
- `0x140302e10`
- `0x1403063e0`
- `0x140339524`
- `0x140339b3c`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140306448`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140306448`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140306534`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140341ed4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140306534`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140341ed4`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140306499`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140306499`
- `ntoskrnl!SeSetSecurityDescriptorInfoEx` at `0x140306478`
- `ntoskrnl!SeSetSecurityDescriptorInfoEx` at `0x140306478`
- `ntoskrnl!SeDeassignSecurity` at `0x1403065b0`
- `ntoskrnl!SeDeassignSecurity` at `0x140341f63`
- `ntoskrnl!SeDeassignSecurity` at `0x1403065b0`
- `ntoskrnl!SeDeassignSecurity` at `0x140341f63`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140306547`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140341ee7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140306547`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140341ee7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306579`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140341f1b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306579`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140341f1b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306585`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140341f27`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306585`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140341f27`
- `ntoskrnl!ExReleasePushLockEx` at `0x14030659a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140341f3c`
- `ntoskrnl!ExReleasePushLockEx` at `0x140341f85`
- `ntoskrnl!ExReleasePushLockEx` at `0x14030659a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140341f3c`
- `ntoskrnl!ExReleasePushLockEx` at `0x140341f85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140306561`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341eff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140306561`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341eff`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403064e1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403064e1`

## pseudocode

```c
__int64 __fastcall RefsModifySecurity(
        struct _IRP_CONTEXT *a1,
        struct _FCB *a2,
        PSECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR ModificationDescriptor)
{
  struct _IRP_CONTEXT *v8; // rcx
  struct _IRP_CONTEXT *v9; // rcx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // r14d
  ULONG v14; // eax
  unsigned int v15; // r8d
  struct _LIST_ENTRY *v16; // rbx
  struct _LIST_ENTRY *Flink; // r15
  PVOID *FileContextSupportPointer; // rbx
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+50h] [rbp-48h] BYREF
  __int64 v22; // [rsp+58h] [rbp-40h]
  struct _LIST_ENTRY *v23; // [rsp+60h] [rbp-38h]

  ObjectsSecurityDescriptor = 0;
  if ( !a2->ScavengerFinalizationList.Flink )
    RefsLoadSecurityDescriptor(a1, a2);
  if ( RefsIsTransactionActive(a1) && !RefsIsModifyingTransactionActive(v8) )
    RefsCheckpointCurrentTransaction(v9);
  ObjectsSecurityDescriptor = (char *)&a2->ScavengerFinalizationList.Flink[1].Flink + 4;
  GenericMapping = IoGetFileObjectGenericMapping();
  v11 = SeSetSecurityDescriptorInfoEx(
          0,
          SecurityInformation,
          ModificationDescriptor,
          &ObjectsSecurityDescriptor,
          0x4000u,
          PoolType,
          GenericMapping);
  v13 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids,
        (unsigned int)v11);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v13, a1, "SecurSup.c", 0x40Du);
    RefsRaiseStatusInternal(a1, v13, v12);
LABEL_18:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, a1, "SecurSup.c", 0x41Eu);
    RefsRaiseStatusInternal(a1, -1073741811, v15);
    __debugbreak();
    JUMPOUT(0x1403066BELL);
  }
  v14 = RtlLengthSecurityDescriptor(ObjectsSecurityDescriptor);
  v23 = 0;
  v22 = 0;
  if ( !v14 )
    goto LABEL_18;
  v16 = (struct _LIST_ENTRY *)RefsCacheSharedSecurityByDescriptor(a1, ObjectsSecurityDescriptor, v14, 1u);
  v23 = v16;
  ExAcquirePushLockExclusiveEx(&a2->ScavengerFinalizationList.Blink, 0);
  Flink = a2->ScavengerFinalizationList.Flink;
  v22 = *(__int64 *)((char *)&a2->pBufferingStateChangeCompletedEvent + 4);
  a2->ScavengerFinalizationList.Flink = v16;
  *(PKEVENT *)((char *)&a2->pBufferingStateChangeCompletedEvent + 4) = (PKEVENT)v16->Blink;
  RefsUpdateStandardInformation(a1, a2);
  RefsCheckpointCurrentTransaction(a1);
  FileContextSupportPointer = a2->Header.FileContextSupportPointer;
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)FileContextSupportPointer + 13);
  if ( LODWORD(Flink->Flink)-- == 1 )
    ExFreePoolWithTag(Flink, 0);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)FileContextSupportPointer + 13);
  KeLeaveGuardedRegion();
  ExReleasePushLockEx(&a2->ScavengerFinalizationList.Blink, 0);
  SeDeassignSecurity(&ObjectsSecurityDescriptor);
  *((_DWORD *)&a2->1 + 43) |= 0x100u;
  return v13;
}

```

## disassembly

```asm
0x1403063e0  mov     [rsp+arg_0], rbx
0x1403063e5  mov     [rsp+arg_10], rsi
0x1403063ea  mov     [rsp+arg_8], rdx
0x1403063ef  push    rdi
0x1403063f0  push    r12
0x1403063f2  push    r13
0x1403063f4  push    r14
0x1403063f6  push    r15
0x1403063f8  sub     rsp, 70h
0x1403063fc  mov     rbx, r9
0x1403063ff  mov     r14, r8
0x140306402  mov     rsi, rdx
0x140306405  mov     rdi, rcx
0x140306408  xor     r13d, r13d
0x14030640b  mov     [rsp+98h+ObjectsSecurityDescriptor], r13
0x140306410  cmp     [rdx+0C0h], r13
0x140306417  jnz     short loc_14030641E
0x140306419  call    ?RefsLoadSecurityDescriptor@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsLoadSecurityDescriptor(_IRP_CONTEXT *,_FCB *)
0x14030641e  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140306421  call    ?RefsIsTransactionActive@@YA_NPEAU_IRP_CONTEXT@@@Z; RefsIsTransactionActive(_IRP_CONTEXT *)
0x140306426  test    al, al
0x140306428  jz      short loc_140306438
0x14030642a  call    ?RefsIsModifyingTransactionActive@@YAEPEAU_IRP_CONTEXT@@@Z; RefsIsModifyingTransactionActive(_IRP_CONTEXT *)
0x14030642f  test    al, al
0x140306431  jnz     short loc_140306438
0x140306433  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x140306438  mov     rax, [rsi+0C0h]
0x14030643f  add     rax, 14h
0x140306443  mov     [rsp+98h+ObjectsSecurityDescriptor], rax
0x140306448  call    cs:__imp_IoGetFileObjectGenericMapping
0x14030644f  nop     dword ptr [rax+rax+00h]
0x140306454  mov     ecx, cs:PoolType
0x14030645a  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x14030645f  mov     [rsp+98h+PoolType], ecx; PoolType
0x140306463  mov     [rsp+98h+AutoInheritFlags], 4000h; AutoInheritFlags
0x14030646b  lea     r9, [rsp+98h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x140306470  mov     r8, rbx; ModificationDescriptor
0x140306473  mov     rdx, r14; SecurityInformation
0x140306476  xor     ecx, ecx; Object
0x140306478  call    cs:__imp_SeSetSecurityDescriptorInfoEx
0x14030647f  nop     dword ptr [rax+rax+00h]
0x140306484  mov     r14d, eax
0x140306487  test    eax, eax
0x140306489  js      loc_1403065E4
0x14030648f  mov     [rsp+98h+var_58], r13b
0x140306494  mov     rcx, [rsp+98h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x140306499  call    cs:__imp_RtlLengthSecurityDescriptor
0x1403064a0  nop     dword ptr [rax+rax+00h]
0x1403064a5  nop
0x1403064a6  mov     [rsp+98h+var_38], r13
0x1403064ab  mov     [rsp+98h+var_50], r13
0x1403064b0  mov     [rsp+98h+var_40], r13
0x1403064b5  test    eax, eax
0x1403064b7  jz      loc_14030664D
0x1403064bd  mov     r9b, 1; unsigned __int8
0x1403064c0  mov     r8d, eax; Size
0x1403064c3  mov     rdx, [rsp+98h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1403064c8  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1403064cb  call    ?RefsCacheSharedSecurityByDescriptor@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAXKE@Z; RefsCacheSharedSecurityByDescriptor(_IRP_CONTEXT *,void *,ulong,uchar)
0x1403064d0  mov     rbx, rax
0x1403064d3  mov     [rsp+98h+var_38], rax
0x1403064d8  xor     edx, edx
0x1403064da  lea     rcx, [rsi+0C8h]
0x1403064e1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1403064e8  nop     dword ptr [rax+rax+00h]
0x1403064ed  mov     [rsp+98h+var_58], 1
0x1403064f2  mov     r15, [rsi+0C0h]
0x1403064f9  mov     [rsp+98h+var_50], r15
0x1403064fe  mov     rcx, [rsi+0D4h]
0x140306505  mov     [rsp+98h+var_40], rcx
0x14030650a  mov     [rsi+0C0h], rbx
0x140306511  mov     rax, [rbx+8]
0x140306515  mov     [rsi+0D4h], rax
0x14030651c  mov     rdx, rsi; struct _FCB *
0x14030651f  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140306522  call    ?RefsUpdateStandardInformation@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsUpdateStandardInformation(_IRP_CONTEXT *,_FCB *)
0x140306527  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030652a  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x14030652f  nop
0x140306530  mov     rbx, [rsi+50h]
0x140306534  call    cs:__imp_KeEnterGuardedRegion
0x14030653b  nop     dword ptr [rax+rax+00h]
0x140306540  lea     rcx, [rbx+2D8h]; FastMutex
0x140306547  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14030654e  nop     dword ptr [rax+rax+00h]
0x140306553  add     dword ptr [r15], 0FFFFFFFFh
0x140306557  mov     eax, [r15]
0x14030655a  jnz     short loc_14030656D
0x14030655c  xor     edx, edx; Tag
0x14030655e  mov     rcx, r15; P
0x140306561  call    cs:__imp_ExFreePoolWithTag
0x140306568  nop     dword ptr [rax+rax+00h]
0x14030656d  mov     [rsp+98h+var_50], r13
0x140306572  lea     rcx, [rbx+2D8h]; FastMutex
0x140306579  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140306580  nop     dword ptr [rax+rax+00h]
0x140306585  call    cs:__imp_KeLeaveGuardedRegion
0x14030658c  nop     dword ptr [rax+rax+00h]
0x140306591  xor     edx, edx
0x140306593  lea     rcx, [rsi+0C8h]
0x14030659a  call    cs:__imp_ExReleasePushLockEx
0x1403065a1  nop     dword ptr [rax+rax+00h]
0x1403065a6  mov     [rsp+98h+var_58], 0
0x1403065ab  lea     rcx, [rsp+98h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1403065b0  call    cs:__imp_SeDeassignSecurity
0x1403065b7  nop     dword ptr [rax+rax+00h]
0x1403065bc  or      dword ptr [rsi+0ACh], 100h
0x1403065c6  mov     eax, r14d
0x1403065c9  lea     r11, [rsp+98h+var_28]
0x1403065ce  mov     rbx, [r11+30h]
0x1403065d2  mov     rsi, [r11+40h]
0x1403065d6  mov     rsp, r11
0x1403065d9  pop     r15
0x1403065db  pop     r14
0x1403065dd  pop     r13
0x1403065df  pop     r12
0x1403065e1  pop     rdi
0x1403065e2  retn
0x1403065e4  lea     rdx, WPP_GLOBAL_Control
0x1403065eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1403065f2  cmp     rcx, rdx
0x1403065f5  jz      short loc_14030661E
0x1403065f7  test    dword ptr [rcx+2Ch], 100h
0x1403065fe  jz      short loc_14030661E
0x140306600  cmp     byte ptr [rcx+29h], 4
0x140306604  jb      short loc_14030661E
0x140306606  mov     edx, 0Ah
0x14030660b  mov     r9d, eax
0x14030660e  lea     r8, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids
0x140306615  mov     rcx, [rcx+18h]
0x140306619  call    WPP_SF_d
0x14030661e  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140306625  test    al, al
0x140306627  jz      short loc_140306641
0x140306629  mov     r9d, 40Dh; unsigned int
0x14030662f  lea     r8, aSecursupC; "SecurSup.c"
0x140306636  mov     rdx, rdi; struct _IRP_CONTEXT *
0x140306639  mov     ecx, r14d; Status
0x14030663c  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140306641  mov     edx, r14d; int
0x140306644  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140306647  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14030664c  nop
0x14030664d  lea     rdx, WPP_GLOBAL_Control
0x140306654  mov     rcx, cs:WPP_GLOBAL_Control
0x14030665b  cmp     rcx, rdx
0x14030665e  jz      short loc_14030668A
0x140306660  mov     eax, [rcx+2Ch]
0x140306663  bt      eax, 8
0x140306667  jnb     short loc_14030668A
0x140306669  cmp     byte ptr [rcx+29h], 4
0x14030666d  jb      short loc_14030668A
0x14030666f  mov     edx, 0Bh
0x140306674  mov     r9d, 0C000000Dh
0x14030667a  lea     r8, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids
0x140306681  mov     rcx, [rcx+18h]
0x140306685  call    WPP_SF_d
0x14030668a  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140306691  test    al, al
0x140306693  jz      short loc_1403066AF
0x140306695  mov     r9d, 41Eh; unsigned int
0x14030669b  lea     r8, aSecursupC; "SecurSup.c"
0x1403066a2  mov     rdx, rdi; struct _IRP_CONTEXT *
0x1403066a5  mov     ecx, 0C000000Dh; Status
0x1403066aa  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1403066af  mov     edx, 0C000000Dh; int
0x1403066b4  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1403066b7  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1403066bc  nop
0x1403066bd  int     3; Trap to Debugger
0x140341e90  push    rbx
0x140341e92  push    rbp
0x140341e93  push    rsi
0x140341e94  push    rdi
0x140341e95  sub     rsp, 48h
0x140341e99  mov     rbp, rdx
0x140341e9c  mov     rbx, [rbp+0A8h]
0x140341ea3  test    cl, cl
0x140341ea5  jz      short loc_140341ECC
0x140341ea7  mov     rax, [rbp+48h]
0x140341eab  test    rax, rax
0x140341eae  jz      short loc_140341EC2
0x140341eb0  mov     [rbx+0C0h], rax
0x140341eb7  mov     rax, [rbp+58h]
0x140341ebb  mov     [rbx+0D4h], rax
0x140341ec2  mov     rdi, [rbp+60h]
0x140341ec6  mov     [rbp+48h], rdi
0x140341eca  jmp     short loc_140341ED0
0x140341ecc  mov     rdi, [rbp+48h]
0x140341ed0  mov     rsi, [rbx+50h]
0x140341ed4  call    cs:__imp_KeEnterGuardedRegion
0x140341edb  nop     dword ptr [rax+rax+00h]
0x140341ee0  lea     rcx, [rsi+2D8h]; FastMutex
0x140341ee7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140341eee  nop     dword ptr [rax+rax+00h]
0x140341ef3  add     dword ptr [rdi], 0FFFFFFFFh
0x140341ef6  mov     eax, [rdi]
0x140341ef8  jnz     short loc_140341F0C
0x140341efa  xor     edx, edx; Tag
0x140341efc  mov     rcx, rdi; P
0x140341eff  call    cs:__imp_ExFreePoolWithTag
0x140341f06  nop     dword ptr [rax+rax+00h]
0x140341f0b  nop
0x140341f0c  mov     qword ptr [rbp+48h], 0
0x140341f14  lea     rcx, [rsi+2D8h]; FastMutex
0x140341f1b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140341f22  nop     dword ptr [rax+rax+00h]
0x140341f27  call    cs:__imp_KeLeaveGuardedRegion
0x140341f2e  nop     dword ptr [rax+rax+00h]
0x140341f33  lea     rcx, [rbx+0C8h]
0x140341f3a  xor     edx, edx
0x140341f3c  call    cs:__imp_ExReleasePushLockEx
0x140341f43  nop     dword ptr [rax+rax+00h]
0x140341f48  mov     byte ptr [rbp+40h], 0
0x140341f4c  add     rsp, 48h
0x140341f50  pop     rdi
0x140341f51  pop     rsi
0x140341f52  pop     rbp
0x140341f53  pop     rbx
0x140341f54  retn
0x140341f56  push    rbp
0x140341f58  sub     rsp, 40h
0x140341f5c  mov     rbp, rdx
0x140341f5f  lea     rcx, [rbp+50h]; SecurityDescriptor
0x140341f63  call    cs:__imp_SeDeassignSecurity
0x140341f6a  nop     dword ptr [rax+rax+00h]
0x140341f6f  cmp     byte ptr [rbp+40h], 0
0x140341f73  jz      short loc_140341F92
0x140341f75  mov     rcx, [rbp+0A8h]
0x140341f7c  add     rcx, 0C8h
0x140341f83  xor     edx, edx
0x140341f85  call    cs:__imp_ExReleasePushLockEx
0x140341f8c  nop     dword ptr [rax+rax+00h]
0x140341f91  nop
0x140341f92  add     rsp, 40h
0x140341f96  pop     rbp
0x140341f97  retn
```
