# RefsModifySecurity(_IRP_CONTEXT *,_FCB *,ulong *,void *)

- ea: `0x140302330`
- end: `0x14030260e`
- name: `?RefsModifySecurity@@YAJPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAKPEAX@Z`
- size: `734`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _FCB *, PSECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR ModificationDescriptor)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402c5430`
- `0x140300f70`
- `0x1403036e4`

## callees

- `0x140081670`
- `0x14008dbd0`
- `0x14008e280`
- `0x140099960`
- `0x1400ca788`
- `0x140285008`
- `0x1402fec90`
- `0x140302330`
- `0x14033034c`
- `0x14033783c`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140302398`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140302398`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140302484`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033ef14`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140302484`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033ef14`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1403023e9`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1403023e9`
- `ntoskrnl!SeSetSecurityDescriptorInfoEx` at `0x1403023c8`
- `ntoskrnl!SeSetSecurityDescriptorInfoEx` at `0x1403023c8`
- `ntoskrnl!SeDeassignSecurity` at `0x140302500`
- `ntoskrnl!SeDeassignSecurity` at `0x14033efa3`
- `ntoskrnl!SeDeassignSecurity` at `0x140302500`
- `ntoskrnl!SeDeassignSecurity` at `0x14033efa3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140302497`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033ef27`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140302497`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033ef27`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403024c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033ef5b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403024c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033ef5b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403024d5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033ef67`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403024d5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033ef67`
- `ntoskrnl!ExReleasePushLockEx` at `0x1403024ea`
- `ntoskrnl!ExReleasePushLockEx` at `0x14033ef7c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14033efc5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1403024ea`
- `ntoskrnl!ExReleasePushLockEx` at `0x14033ef7c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14033efc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403024b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033ef3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403024b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033ef3f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140302431`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140302431`

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
    JUMPOUT(0x14030260ELL);
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
0x140302330  mov     [rsp+arg_0], rbx
0x140302335  mov     [rsp+arg_10], rsi
0x14030233a  mov     [rsp+arg_8], rdx
0x14030233f  push    rdi
0x140302340  push    r12
0x140302342  push    r13
0x140302344  push    r14
0x140302346  push    r15
0x140302348  sub     rsp, 70h
0x14030234c  mov     rbx, r9
0x14030234f  mov     r14, r8
0x140302352  mov     rsi, rdx
0x140302355  mov     rdi, rcx
0x140302358  xor     r13d, r13d
0x14030235b  mov     [rsp+98h+ObjectsSecurityDescriptor], r13
0x140302360  cmp     [rdx+0C0h], r13
0x140302367  jnz     short loc_14030236E
0x140302369  call    ?RefsLoadSecurityDescriptor@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsLoadSecurityDescriptor(_IRP_CONTEXT *,_FCB *)
0x14030236e  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140302371  call    ?RefsIsTransactionActive@@YA_NPEAU_IRP_CONTEXT@@@Z; RefsIsTransactionActive(_IRP_CONTEXT *)
0x140302376  test    al, al
0x140302378  jz      short loc_140302388
0x14030237a  call    ?RefsIsModifyingTransactionActive@@YAEPEAU_IRP_CONTEXT@@@Z; RefsIsModifyingTransactionActive(_IRP_CONTEXT *)
0x14030237f  test    al, al
0x140302381  jnz     short loc_140302388
0x140302383  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x140302388  mov     rax, [rsi+0C0h]
0x14030238f  add     rax, 14h
0x140302393  mov     [rsp+98h+ObjectsSecurityDescriptor], rax
0x140302398  call    cs:__imp_IoGetFileObjectGenericMapping
0x14030239f  nop     dword ptr [rax+rax+00h]
0x1403023a4  mov     ecx, cs:PoolType
0x1403023aa  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x1403023af  mov     [rsp+98h+PoolType], ecx; PoolType
0x1403023b3  mov     [rsp+98h+AutoInheritFlags], 4000h; AutoInheritFlags
0x1403023bb  lea     r9, [rsp+98h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1403023c0  mov     r8, rbx; ModificationDescriptor
0x1403023c3  mov     rdx, r14; SecurityInformation
0x1403023c6  xor     ecx, ecx; Object
0x1403023c8  call    cs:__imp_SeSetSecurityDescriptorInfoEx
0x1403023cf  nop     dword ptr [rax+rax+00h]
0x1403023d4  mov     r14d, eax
0x1403023d7  test    eax, eax
0x1403023d9  js      loc_140302534
0x1403023df  mov     [rsp+98h+var_58], r13b
0x1403023e4  mov     rcx, [rsp+98h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1403023e9  call    cs:__imp_RtlLengthSecurityDescriptor
0x1403023f0  nop     dword ptr [rax+rax+00h]
0x1403023f5  nop
0x1403023f6  mov     [rsp+98h+var_38], r13
0x1403023fb  mov     [rsp+98h+var_50], r13
0x140302400  mov     [rsp+98h+var_40], r13
0x140302405  test    eax, eax
0x140302407  jz      loc_14030259D
0x14030240d  mov     r9b, 1; unsigned __int8
0x140302410  mov     r8d, eax; Size
0x140302413  mov     rdx, [rsp+98h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x140302418  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030241b  call    ?RefsCacheSharedSecurityByDescriptor@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAXKE@Z; RefsCacheSharedSecurityByDescriptor(_IRP_CONTEXT *,void *,ulong,uchar)
0x140302420  mov     rbx, rax
0x140302423  mov     [rsp+98h+var_38], rax
0x140302428  xor     edx, edx
0x14030242a  lea     rcx, [rsi+0C8h]
0x140302431  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140302438  nop     dword ptr [rax+rax+00h]
0x14030243d  mov     [rsp+98h+var_58], 1
0x140302442  mov     r15, [rsi+0C0h]
0x140302449  mov     [rsp+98h+var_50], r15
0x14030244e  mov     rcx, [rsi+0D4h]
0x140302455  mov     [rsp+98h+var_40], rcx
0x14030245a  mov     [rsi+0C0h], rbx
0x140302461  mov     rax, [rbx+8]
0x140302465  mov     [rsi+0D4h], rax
0x14030246c  mov     rdx, rsi; struct _FCB *
0x14030246f  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140302472  call    ?RefsUpdateStandardInformation@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsUpdateStandardInformation(_IRP_CONTEXT *,_FCB *)
0x140302477  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030247a  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x14030247f  nop
0x140302480  mov     rbx, [rsi+50h]
0x140302484  call    cs:__imp_KeEnterGuardedRegion
0x14030248b  nop     dword ptr [rax+rax+00h]
0x140302490  lea     rcx, [rbx+2D8h]; FastMutex
0x140302497  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14030249e  nop     dword ptr [rax+rax+00h]
0x1403024a3  add     dword ptr [r15], 0FFFFFFFFh
0x1403024a7  mov     eax, [r15]
0x1403024aa  jnz     short loc_1403024BD
0x1403024ac  xor     edx, edx; Tag
0x1403024ae  mov     rcx, r15; P
0x1403024b1  call    cs:__imp_ExFreePoolWithTag
0x1403024b8  nop     dword ptr [rax+rax+00h]
0x1403024bd  mov     [rsp+98h+var_50], r13
0x1403024c2  lea     rcx, [rbx+2D8h]; FastMutex
0x1403024c9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1403024d0  nop     dword ptr [rax+rax+00h]
0x1403024d5  call    cs:__imp_KeLeaveGuardedRegion
0x1403024dc  nop     dword ptr [rax+rax+00h]
0x1403024e1  xor     edx, edx
0x1403024e3  lea     rcx, [rsi+0C8h]
0x1403024ea  call    cs:__imp_ExReleasePushLockEx
0x1403024f1  nop     dword ptr [rax+rax+00h]
0x1403024f6  mov     [rsp+98h+var_58], 0
0x1403024fb  lea     rcx, [rsp+98h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x140302500  call    cs:__imp_SeDeassignSecurity
0x140302507  nop     dword ptr [rax+rax+00h]
0x14030250c  or      dword ptr [rsi+0ACh], 100h
0x140302516  mov     eax, r14d
0x140302519  lea     r11, [rsp+98h+var_28]
0x14030251e  mov     rbx, [r11+30h]
0x140302522  mov     rsi, [r11+40h]
0x140302526  mov     rsp, r11
0x140302529  pop     r15
0x14030252b  pop     r14
0x14030252d  pop     r13
0x14030252f  pop     r12
0x140302531  pop     rdi
0x140302532  retn
0x140302534  lea     rdx, WPP_GLOBAL_Control
0x14030253b  mov     rcx, cs:WPP_GLOBAL_Control
0x140302542  cmp     rcx, rdx
0x140302545  jz      short loc_14030256E
0x140302547  test    dword ptr [rcx+2Ch], 100h
0x14030254e  jz      short loc_14030256E
0x140302550  cmp     byte ptr [rcx+29h], 4
0x140302554  jb      short loc_14030256E
0x140302556  mov     edx, 0Ah
0x14030255b  mov     r9d, eax
0x14030255e  lea     r8, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids
0x140302565  mov     rcx, [rcx+18h]
0x140302569  call    WPP_SF_d
0x14030256e  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140302575  test    al, al
0x140302577  jz      short loc_140302591
0x140302579  mov     r9d, 40Dh; unsigned int
0x14030257f  lea     r8, aSecursupC; "SecurSup.c"
0x140302586  mov     rdx, rdi; struct _IRP_CONTEXT *
0x140302589  mov     ecx, r14d; Status
0x14030258c  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140302591  mov     edx, r14d; int
0x140302594  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140302597  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14030259c  nop
0x14030259d  lea     rdx, WPP_GLOBAL_Control
0x1403025a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1403025ab  cmp     rcx, rdx
0x1403025ae  jz      short loc_1403025DA
0x1403025b0  mov     eax, [rcx+2Ch]
0x1403025b3  bt      eax, 8
0x1403025b7  jnb     short loc_1403025DA
0x1403025b9  cmp     byte ptr [rcx+29h], 4
0x1403025bd  jb      short loc_1403025DA
0x1403025bf  mov     edx, 0Bh
0x1403025c4  mov     r9d, 0C000000Dh
0x1403025ca  lea     r8, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids
0x1403025d1  mov     rcx, [rcx+18h]
0x1403025d5  call    WPP_SF_d
0x1403025da  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1403025e1  test    al, al
0x1403025e3  jz      short loc_1403025FF
0x1403025e5  mov     r9d, 41Eh; unsigned int
0x1403025eb  lea     r8, aSecursupC; "SecurSup.c"
0x1403025f2  mov     rdx, rdi; struct _IRP_CONTEXT *
0x1403025f5  mov     ecx, 0C000000Dh; Status
0x1403025fa  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1403025ff  mov     edx, 0C000000Dh; int
0x140302604  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140302607  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14030260c  nop
0x14030260d  int     3; Trap to Debugger
0x14033eed0  push    rbx
0x14033eed2  push    rbp
0x14033eed3  push    rsi
0x14033eed4  push    rdi
0x14033eed5  sub     rsp, 48h
0x14033eed9  mov     rbp, rdx
0x14033eedc  mov     rbx, [rbp+0A8h]
0x14033eee3  test    cl, cl
0x14033eee5  jz      short loc_14033EF0C
0x14033eee7  mov     rax, [rbp+48h]
0x14033eeeb  test    rax, rax
0x14033eeee  jz      short loc_14033EF02
0x14033eef0  mov     [rbx+0C0h], rax
0x14033eef7  mov     rax, [rbp+58h]
0x14033eefb  mov     [rbx+0D4h], rax
0x14033ef02  mov     rdi, [rbp+60h]
0x14033ef06  mov     [rbp+48h], rdi
0x14033ef0a  jmp     short loc_14033EF10
0x14033ef0c  mov     rdi, [rbp+48h]
0x14033ef10  mov     rsi, [rbx+50h]
0x14033ef14  call    cs:__imp_KeEnterGuardedRegion
0x14033ef1b  nop     dword ptr [rax+rax+00h]
0x14033ef20  lea     rcx, [rsi+2D8h]; FastMutex
0x14033ef27  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14033ef2e  nop     dword ptr [rax+rax+00h]
0x14033ef33  add     dword ptr [rdi], 0FFFFFFFFh
0x14033ef36  mov     eax, [rdi]
0x14033ef38  jnz     short loc_14033EF4C
0x14033ef3a  xor     edx, edx; Tag
0x14033ef3c  mov     rcx, rdi; P
0x14033ef3f  call    cs:__imp_ExFreePoolWithTag
0x14033ef46  nop     dword ptr [rax+rax+00h]
0x14033ef4b  nop
0x14033ef4c  mov     qword ptr [rbp+48h], 0
0x14033ef54  lea     rcx, [rsi+2D8h]; FastMutex
0x14033ef5b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14033ef62  nop     dword ptr [rax+rax+00h]
0x14033ef67  call    cs:__imp_KeLeaveGuardedRegion
0x14033ef6e  nop     dword ptr [rax+rax+00h]
0x14033ef73  lea     rcx, [rbx+0C8h]
0x14033ef7a  xor     edx, edx
0x14033ef7c  call    cs:__imp_ExReleasePushLockEx
0x14033ef83  nop     dword ptr [rax+rax+00h]
0x14033ef88  mov     byte ptr [rbp+40h], 0
0x14033ef8c  add     rsp, 48h
0x14033ef90  pop     rdi
0x14033ef91  pop     rsi
0x14033ef92  pop     rbp
0x14033ef93  pop     rbx
0x14033ef94  retn
0x14033ef96  push    rbp
0x14033ef98  sub     rsp, 40h
0x14033ef9c  mov     rbp, rdx
0x14033ef9f  lea     rcx, [rbp+50h]; SecurityDescriptor
0x14033efa3  call    cs:__imp_SeDeassignSecurity
0x14033efaa  nop     dword ptr [rax+rax+00h]
0x14033efaf  cmp     byte ptr [rbp+40h], 0
0x14033efb3  jz      short loc_14033EFD2
0x14033efb5  mov     rcx, [rbp+0A8h]
0x14033efbc  add     rcx, 0C8h
0x14033efc3  xor     edx, edx
0x14033efc5  call    cs:__imp_ExReleasePushLockEx
0x14033efcc  nop     dword ptr [rax+rax+00h]
0x14033efd1  nop
0x14033efd2  add     rsp, 40h
0x14033efd6  pop     rbp
0x14033efd7  retn
```
