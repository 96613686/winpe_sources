# PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> *,_UNICODE_STRING const *)

- ea: `0x14000ed84`
- end: `0x14000f08c`
- name: `?FindOrCreate@PCW_SILO_NEUTRAL_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d2e0`
- `0x14000d460`
- `0x14000ddf4`
- `0x14000e3e8`
- `0x14000e8c0`

## callees

- `0x1400014c0`
- `0x14000cf6c`
- `0x14000e4e8`
- `0x14000e6f8`
- `0x14000ecc0`
- `0x14000ed0c`
- `0x14000ed84`
- `0x14000f094`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000edad`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000edad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ed98`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000efa4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ed98`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000efa4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000edf3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f017`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000edf3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f017`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000ede7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000ede7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000efb9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000efb9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f00b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f00b`
- `ntoskrnl!ExAllocatePool2` at `0x14000ee46`
- `ntoskrnl!ExAllocatePool2` at `0x14000eef3`
- `ntoskrnl!ExAllocatePool2` at `0x14000ee46`
- `ntoskrnl!ExAllocatePool2` at `0x14000eef3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f035`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f06f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f035`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f06f`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14000eeb4`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14000eeb4`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000eed9`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000ef98`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000f05e`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000eed9`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000ef98`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000f05e`

## pseudocode

```c
__int64 __fastcall PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(
        struct PCW_COUNTERSET_BASE **a1,
        const struct _UNICODE_STRING *a2)
{
  struct PCW_COUNTERSET_BASE *Node; // rax
  struct PCW_COUNTERSET_BASE *v5; // rbx
  __int64 v6; // rcx
  struct PCW_COUNTERSET_BASE *v7; // rdx
  int inited; // ebx
  unsigned __int64 v9; // r15
  __int64 v10; // rax
  void *Pool2; // rax
  void *v12; // rdi
  int v13; // eax
  void *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rbx
  __int16 v17; // r15
  void *v18; // rax
  struct PCW_COUNTERSET_BASE *v19; // rax
  struct PCW_COUNTERSET_BASE *v20; // rdi
  PCW_SILO_NEUTRAL_COUNTERSET *v21; // rsi
  void *v23; // [rsp+70h] [rbp+18h] BYREF

  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&qword_1400114A8, 0);
  Node = PCW_COUNTERSET_BASE::FindNode((struct _RTL_RB_TREE *)qword_1400114B0, a2);
  v5 = Node;
  if ( Node )
    _InterlockedAdd((volatile signed __int32 *)Node + 33, 1u);
  ExReleasePushLockSharedEx(&qword_1400114A8, 0);
  KeLeaveCriticalRegion();
  if ( v5 )
  {
    v7 = *a1;
    *a1 = v5;
LABEL_5:
    if ( v7 )
      ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v6, v7);
    return 0;
  }
  v9 = a2->Length >> 1;
  v10 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  Pool2 = (void *)ExAllocatePool2(256, v10, 1131897680);
  v12 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741801;
  memmove(Pool2, a2->Buffer, 2 * v9);
  v23 = 0;
  v13 = PcwpReadSecurityDescriptor(&v23, a2);
  inited = v13;
  if ( v13 < 0 )
  {
    if ( v13 != -1073741772 )
      goto LABEL_27;
    inited = PcwpInitDefaultSecurityDescriptor();
    if ( inited < 0 )
      goto LABEL_27;
    ObReferenceSecurityDescriptor(PcwDefaultSecurityDescriptor, 1);
    v14 = v23;
    v23 = PcwDefaultSecurityDescriptor;
    if ( v14 )
      ObDereferenceSecurityDescriptor(v14, 1);
  }
  v15 = ExAllocatePool2(256, 144, 1131897680);
  v16 = v15;
  if ( v15 )
  {
    v17 = 2 * v9;
    *(_OWORD *)v15 = 0;
    *(_QWORD *)(v15 + 16) = 0;
    *(_WORD *)(v15 + 24) = v17;
    *(_WORD *)(v15 + 26) = v17;
    *(_DWORD *)(v15 + 28) = 0;
    *(_QWORD *)(v15 + 32) = v12;
    *(_QWORD *)(v15 + 56) = 0;
    *(_QWORD *)(v15 + 72) = v15 + 64;
    *(_QWORD *)(v15 + 64) = v15 + 64;
    *(_QWORD *)(v15 + 48) = v15 + 40;
    *(_QWORD *)(v15 + 40) = v15 + 40;
    *(_QWORD *)(v15 + 80) = 0;
    *(_QWORD *)(v15 + 88) = 0;
    v18 = v23;
    v23 = 0;
    *(_QWORD *)(v16 + 96) = v18;
    *(_QWORD *)(v16 + 104) = 0;
    *(_QWORD *)(v16 + 120) = v16 + 112;
    *(_QWORD *)(v16 + 112) = v16 + 112;
    *(_DWORD *)(v16 + 128) = 0;
    *(_DWORD *)(v16 + 132) = 1;
    *(_QWORD *)(v16 + 136) = v12;
    if ( v23 )
      ObDereferenceSecurityDescriptor(v23, 1);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&qword_1400114A8, 0);
    v19 = PCW_COUNTERSET_BASE::FindNode(
            (struct _RTL_RB_TREE *)qword_1400114B0,
            (const struct _UNICODE_STRING *)(v16 + 24));
    v20 = v19;
    if ( v19 )
    {
      _InterlockedAdd((volatile signed __int32 *)v19 + 33, 1u);
      v21 = (PCW_SILO_NEUTRAL_COUNTERSET *)v16;
    }
    else
    {
      PCW_COUNTERSET_BASE::InsertNode(
        (struct _RTL_RB_TREE *)qword_1400114B0,
        (const struct _UNICODE_STRING *)(v16 + 24),
        (struct PCW_COUNTERSET_BASE *)v16);
      v21 = 0;
      v20 = (struct PCW_COUNTERSET_BASE *)v16;
    }
    ExReleasePushLockExclusiveEx(&qword_1400114A8, 0);
    KeLeaveCriticalRegion();
    if ( v21 )
    {
      PCW_SILO_NEUTRAL_COUNTERSET::~PCW_SILO_NEUTRAL_COUNTERSET(v21);
      ExFreePoolWithTag(v21, 0);
    }
    v7 = *a1;
    *a1 = v20;
    goto LABEL_5;
  }
  inited = -1073741801;
LABEL_27:
  if ( v23 )
    ObDereferenceSecurityDescriptor(v23, 1);
  ExFreePoolWithTag(v12, 0);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14000ed84  push    rbx
0x14000ed86  push    rsi
0x14000ed87  push    rdi
0x14000ed88  push    r12
0x14000ed8a  push    r14
0x14000ed8c  push    r15
0x14000ed8e  sub     rsp, 28h
0x14000ed92  mov     rsi, rdx
0x14000ed95  mov     r14, rcx
0x14000ed98  call    cs:__imp_KeEnterCriticalRegion
0x14000ed9f  nop     dword ptr [rax+rax+00h]
0x14000eda4  xor     edx, edx
0x14000eda6  lea     rcx, qword_1400114A8
0x14000edad  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000edb4  nop     dword ptr [rax+rax+00h]
0x14000edb9  mov     rdx, rsi; struct _UNICODE_STRING *
0x14000edbc  lea     rcx, qword_1400114B0; struct _RTL_RB_TREE *
0x14000edc3  call    ?FindNode@PCW_COUNTERSET_BASE@@KAPEAV1@PEAU_RTL_RB_TREE@@PEBU_UNICODE_STRING@@@Z; PCW_COUNTERSET_BASE::FindNode(_RTL_RB_TREE *,_UNICODE_STRING const *)
0x14000edc8  mov     rbx, rax
0x14000edcb  mov     r12d, 1
0x14000edd1  test    rax, rax
0x14000edd4  jz      short loc_14000EDDE
0x14000edd6  lock add [rax+84h], r12d
0x14000edde  xor     edx, edx
0x14000ede0  lea     rcx, qword_1400114A8
0x14000ede7  call    cs:__imp_ExReleasePushLockSharedEx
0x14000edee  nop     dword ptr [rax+rax+00h]
0x14000edf3  call    cs:__imp_KeLeaveCriticalRegion
0x14000edfa  nop     dword ptr [rax+rax+00h]
0x14000edff  test    rbx, rbx
0x14000ee02  jz      short loc_14000EE1B
0x14000ee04  mov     rdx, [r14]
0x14000ee07  mov     [r14], rbx
0x14000ee0a  test    rdx, rdx
0x14000ee0d  jz      short loc_14000EE14
0x14000ee0f  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000ee14  xor     ebx, ebx
0x14000ee16  jmp     loc_14000F07B
0x14000ee1b  movzx   eax, word ptr [rsi]
0x14000ee1e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000ee25  shr     ax, 1
0x14000ee28  mov     r8d, 43776350h
0x14000ee2e  movzx   r15d, ax
0x14000ee32  mov     eax, 2
0x14000ee37  mul     r15
0x14000ee3a  cmovb   rax, rcx
0x14000ee3e  mov     ecx, 100h
0x14000ee43  mov     rdx, rax
0x14000ee46  call    cs:__imp_ExAllocatePool2
0x14000ee4d  nop     dword ptr [rax+rax+00h]
0x14000ee52  mov     rdi, rax
0x14000ee55  test    rax, rax
0x14000ee58  jnz     short loc_14000EE64
0x14000ee5a  mov     ebx, 0C0000017h
0x14000ee5f  jmp     loc_14000F07B
0x14000ee64  mov     rdx, [rsi+8]; Src
0x14000ee68  lea     r8, [r15+r15]; Size
0x14000ee6c  mov     rcx, rdi; void *
0x14000ee6f  call    memmove
0x14000ee74  mov     rdx, rsi
0x14000ee77  mov     [rsp+58h+arg_10], 0
0x14000ee80  lea     rcx, [rsp+58h+arg_10]
0x14000ee85  call    ?PcwpReadSecurityDescriptor@@YAJPEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@utl@@PEBU_UNICODE_STRING@@@Z; PcwpReadSecurityDescriptor(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> *,_UNICODE_STRING const *)
0x14000ee8a  mov     ebx, eax
0x14000ee8c  test    eax, eax
0x14000ee8e  jns     short loc_14000EEE5
0x14000ee90  cmp     eax, 0C0000034h
0x14000ee95  jnz     loc_14000F051
0x14000ee9b  call    ?PcwpInitDefaultSecurityDescriptor@@YAJXZ; PcwpInitDefaultSecurityDescriptor(void)
0x14000eea0  mov     ebx, eax
0x14000eea2  test    eax, eax
0x14000eea4  js      loc_14000F051
0x14000eeaa  mov     rcx, cs:?PcwDefaultSecurityDescriptor@@3PEAXEA; void * PcwDefaultSecurityDescriptor
0x14000eeb1  mov     edx, r12d
0x14000eeb4  call    cs:__imp_ObReferenceSecurityDescriptor
0x14000eebb  nop     dword ptr [rax+rax+00h]
0x14000eec0  mov     rcx, [rsp+58h+arg_10]
0x14000eec5  mov     rax, cs:?PcwDefaultSecurityDescriptor@@3PEAXEA; void * PcwDefaultSecurityDescriptor
0x14000eecc  mov     [rsp+58h+arg_10], rax
0x14000eed1  test    rcx, rcx
0x14000eed4  jz      short loc_14000EEE5
0x14000eed6  mov     edx, r12d
0x14000eed9  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000eee0  nop     dword ptr [rax+rax+00h]
0x14000eee5  mov     edx, 90h
0x14000eeea  mov     r8d, 43776350h
0x14000eef0  lea     ecx, [rdx+70h]
0x14000eef3  call    cs:__imp_ExAllocatePool2
0x14000eefa  nop     dword ptr [rax+rax+00h]
0x14000eeff  mov     rbx, rax
0x14000ef02  test    rax, rax
0x14000ef05  jz      loc_14000F04C
0x14000ef0b  xor     eax, eax
0x14000ef0d  lea     rcx, [rbx+28h]
0x14000ef11  add     r15w, r15w
0x14000ef15  xorps   xmm0, xmm0
0x14000ef18  movups  xmmword ptr [rbx], xmm0
0x14000ef1b  mov     [rbx+10h], rax
0x14000ef1f  mov     [rbx+18h], r15w
0x14000ef24  mov     [rbx+1Ah], r15w
0x14000ef29  mov     [rbx+1Ch], eax
0x14000ef2c  mov     [rbx+20h], rdi
0x14000ef30  mov     [rbx+38h], rax
0x14000ef34  lea     rax, [rbx+40h]
0x14000ef38  mov     [rax+8], rax
0x14000ef3c  mov     [rax], rax
0x14000ef3f  xor     eax, eax
0x14000ef41  mov     [rcx+8], rcx
0x14000ef45  mov     [rcx], rcx
0x14000ef48  mov     [rbx+50h], rax
0x14000ef4c  mov     [rbx+58h], rax
0x14000ef50  mov     rax, [rsp+58h+arg_10]
0x14000ef55  mov     [rsp+58h+arg_10], 0
0x14000ef5e  mov     [rbx+60h], rax
0x14000ef62  xor     eax, eax
0x14000ef64  mov     [rbx+68h], rax
0x14000ef68  lea     rax, [rbx+70h]
0x14000ef6c  mov     [rax+8], rax
0x14000ef70  mov     [rax], rax
0x14000ef73  mov     dword ptr [rbx+80h], 0
0x14000ef7d  mov     [rbx+84h], r12d
0x14000ef84  mov     [rbx+88h], rdi
0x14000ef8b  mov     rcx, [rsp+58h+arg_10]
0x14000ef90  test    rcx, rcx
0x14000ef93  jz      short loc_14000EFA4
0x14000ef95  mov     edx, r12d
0x14000ef98  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000ef9f  nop     dword ptr [rax+rax+00h]
0x14000efa4  call    cs:__imp_KeEnterCriticalRegion
0x14000efab  nop     dword ptr [rax+rax+00h]
0x14000efb0  xor     edx, edx
0x14000efb2  lea     rcx, qword_1400114A8
0x14000efb9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000efc0  nop     dword ptr [rax+rax+00h]
0x14000efc5  lea     rdx, [rbx+18h]; struct _UNICODE_STRING *
0x14000efc9  lea     rcx, qword_1400114B0; struct _RTL_RB_TREE *
0x14000efd0  call    ?FindNode@PCW_COUNTERSET_BASE@@KAPEAV1@PEAU_RTL_RB_TREE@@PEBU_UNICODE_STRING@@@Z; PCW_COUNTERSET_BASE::FindNode(_RTL_RB_TREE *,_UNICODE_STRING const *)
0x14000efd5  mov     rdi, rax
0x14000efd8  test    rax, rax
0x14000efdb  jz      short loc_14000EFEA
0x14000efdd  lock add [rax+84h], r12d
0x14000efe5  mov     rsi, rbx
0x14000efe8  jmp     short loc_14000F002
0x14000efea  mov     r8, rbx; struct PCW_COUNTERSET_BASE *
0x14000efed  lea     rdx, [rbx+18h]; struct _UNICODE_STRING *
0x14000eff1  lea     rcx, qword_1400114B0; struct _RTL_RB_TREE *
0x14000eff8  call    ?InsertNode@PCW_COUNTERSET_BASE@@KAXPEAU_RTL_RB_TREE@@PEBU_UNICODE_STRING@@PEAV1@@Z; PCW_COUNTERSET_BASE::InsertNode(_RTL_RB_TREE *,_UNICODE_STRING const *,PCW_COUNTERSET_BASE *)
0x14000effd  xor     esi, esi
0x14000efff  mov     rdi, rbx
0x14000f002  xor     edx, edx
0x14000f004  lea     rcx, qword_1400114A8
0x14000f00b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f012  nop     dword ptr [rax+rax+00h]
0x14000f017  call    cs:__imp_KeLeaveCriticalRegion
0x14000f01e  nop     dword ptr [rax+rax+00h]
0x14000f023  test    rsi, rsi
0x14000f026  jz      short loc_14000F041
0x14000f028  mov     rcx, rsi; this
0x14000f02b  call    ??1PCW_SILO_NEUTRAL_COUNTERSET@@AEAA@XZ; PCW_SILO_NEUTRAL_COUNTERSET::~PCW_SILO_NEUTRAL_COUNTERSET(void)
0x14000f030  xor     edx, edx; Tag
0x14000f032  mov     rcx, rsi; P
0x14000f035  call    cs:__imp_ExFreePoolWithTag
0x14000f03c  nop     dword ptr [rax+rax+00h]
0x14000f041  mov     rdx, [r14]
0x14000f044  mov     [r14], rdi
0x14000f047  jmp     loc_14000EE0A
0x14000f04c  mov     ebx, 0C0000017h
0x14000f051  mov     rcx, [rsp+58h+arg_10]
0x14000f056  test    rcx, rcx
0x14000f059  jz      short loc_14000F06A
0x14000f05b  mov     edx, r12d
0x14000f05e  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000f065  nop     dword ptr [rax+rax+00h]
0x14000f06a  xor     edx, edx; Tag
0x14000f06c  mov     rcx, rdi; P
0x14000f06f  call    cs:__imp_ExFreePoolWithTag
0x14000f076  nop     dword ptr [rax+rax+00h]
0x14000f07b  mov     eax, ebx
0x14000f07d  add     rsp, 28h
0x14000f081  pop     r15
0x14000f083  pop     r14
0x14000f085  pop     r12
0x14000f087  pop     rdi
0x14000f088  pop     rsi
0x14000f089  pop     rbx
0x14000f08a  retn
```
