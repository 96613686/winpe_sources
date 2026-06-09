# PCW_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> *,_UNICODE_STRING const *)

- ea: `0x14000d460`
- end: `0x14000d659`
- name: `?FindOrCreate@PCW_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14000d2e0`
- `0x14000d660`

## callees

- `0x140008140`
- `0x14000cb24`
- `0x14000cddc`
- `0x14000cf6c`
- `0x14000d460`
- `0x14000ed0c`
- `0x14000ed84`
- `0x14000f094`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000d4cc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000d4cc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d4bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d59d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d4bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d59d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d507`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d5fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d507`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d5fe`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000d4fb`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000d4fb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d5ae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d5ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d5f2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d5f2`
- `ntoskrnl!ExAllocatePool2` at `0x14000d55d`
- `ntoskrnl!ExAllocatePool2` at `0x14000d55d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d620`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d620`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000d4aa`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000d4aa`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14000d486`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14000d486`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000d494`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000d494`

## pseudocode

```c
__int64 __fastcall PCW_COUNTERSET::FindOrCreate(__int64 *a1, const struct _UNICODE_STRING *a2)
{
  unsigned int SiloMonitorContextSlot; // ebx
  __int64 CurrentServerSilo; // rax
  __int64 v6; // rbp
  struct PCW_COUNTERSET_BASE *Node; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // ebx
  __int64 v12; // rcx
  __int64 Pool2; // rax
  __int64 v14; // rsi
  struct PCW_COUNTERSET_BASE *v15; // rax
  PCW_COUNTERSET *v16; // rdi
  struct PCW_COUNTERSET_BASE *v18; // [rsp+60h] [rbp+18h] BYREF
  __int64 v19; // [rsp+68h] [rbp+20h] BYREF

  v19 = 0;
  SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(qword_1400114A0);
  CurrentServerSilo = PsGetCurrentServerSilo();
  PsGetPermanentSiloContext(CurrentServerSilo, SiloMonitorContextSlot, &v19);
  v6 = v19;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v6, 0);
  Node = PCW_COUNTERSET_BASE::FindNode((struct _RTL_RB_TREE *)(v6 + 8), a2);
  v8 = (__int64)Node;
  if ( Node )
    _InterlockedIncrement((volatile signed __int32 *)Node + 38);
  ExReleasePushLockSharedEx(v6, 0);
  KeLeaveCriticalRegion();
  if ( v8 )
    goto LABEL_4;
  v18 = 0;
  v11 = PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(&v18, a2);
  if ( v11 >= 0 )
  {
    Pool2 = ExAllocatePool2(256, 160, 1131897680);
    if ( Pool2 )
    {
      v14 = PCW_COUNTERSET::PCW_COUNTERSET(Pool2, &v18, v6);
      if ( v14 )
      {
        if ( v18 )
          ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v12, (volatile signed __int32 *)v18);
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v6, 0);
        v15 = PCW_COUNTERSET_BASE::FindNode((struct _RTL_RB_TREE *)(v6 + 8), a2);
        v8 = (__int64)v15;
        if ( v15 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v15 + 38);
          v16 = (PCW_COUNTERSET *)v14;
        }
        else
        {
          PCW_COUNTERSET_BASE::InsertNode(
            (struct _RTL_RB_TREE *)(v6 + 8),
            (const struct _UNICODE_STRING *)(v14 + 24),
            (struct PCW_COUNTERSET_BASE *)v14);
          v16 = 0;
          v8 = v14;
        }
        ExReleasePushLockExclusiveEx(v6, 0);
        KeLeaveCriticalRegion();
        if ( v16 )
        {
          PCW_COUNTERSET::~PCW_COUNTERSET(v16);
          ExFreePoolWithTag(v16, 0);
        }
LABEL_4:
        v10 = *a1;
        *a1 = v8;
        if ( v10 )
          ReleaseDeleter<PCW_COUNTERSET>::operator()(v9, v10);
        return 0;
      }
    }
    v11 = -1073741801;
  }
  if ( v18 )
    ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v12, (volatile signed __int32 *)v18);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000d460  mov     [rsp+arg_0], rbx
0x14000d465  push    rbp
0x14000d466  push    rsi
0x14000d467  push    rdi
0x14000d468  push    r14
0x14000d46a  push    r15
0x14000d46c  sub     rsp, 20h
0x14000d470  mov     r14, rcx
0x14000d473  mov     [rsp+48h+arg_18], 0
0x14000d47c  mov     rcx, cs:qword_1400114A0
0x14000d483  mov     rdi, rdx
0x14000d486  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14000d48d  nop     dword ptr [rax+rax+00h]
0x14000d492  mov     ebx, eax
0x14000d494  call    cs:__imp_PsGetCurrentServerSilo
0x14000d49b  nop     dword ptr [rax+rax+00h]
0x14000d4a0  lea     r8, [rsp+48h+arg_18]
0x14000d4a5  mov     edx, ebx
0x14000d4a7  mov     rcx, rax
0x14000d4aa  call    cs:__imp_PsGetPermanentSiloContext
0x14000d4b1  nop     dword ptr [rax+rax+00h]
0x14000d4b6  mov     rbp, [rsp+48h+arg_18]
0x14000d4bb  call    cs:__imp_KeEnterCriticalRegion
0x14000d4c2  nop     dword ptr [rax+rax+00h]
0x14000d4c7  xor     edx, edx
0x14000d4c9  mov     rcx, rbp
0x14000d4cc  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000d4d3  nop     dword ptr [rax+rax+00h]
0x14000d4d8  lea     r15, [rbp+8]
0x14000d4dc  mov     rdx, rdi; struct _UNICODE_STRING *
0x14000d4df  mov     rcx, r15; struct _RTL_RB_TREE *
0x14000d4e2  call    ?FindNode@PCW_COUNTERSET_BASE@@KAPEAV1@PEAU_RTL_RB_TREE@@PEBU_UNICODE_STRING@@@Z; PCW_COUNTERSET_BASE::FindNode(_RTL_RB_TREE *,_UNICODE_STRING const *)
0x14000d4e7  mov     rbx, rax
0x14000d4ea  test    rax, rax
0x14000d4ed  jz      short loc_14000D4F6
0x14000d4ef  lock inc dword ptr [rax+98h]
0x14000d4f6  xor     edx, edx
0x14000d4f8  mov     rcx, rbp
0x14000d4fb  call    cs:__imp_ExReleasePushLockSharedEx
0x14000d502  nop     dword ptr [rax+rax+00h]
0x14000d507  call    cs:__imp_KeLeaveCriticalRegion
0x14000d50e  nop     dword ptr [rax+rax+00h]
0x14000d513  test    rbx, rbx
0x14000d516  jz      short loc_14000D52F
0x14000d518  mov     rdx, [r14]
0x14000d51b  mov     [r14], rbx
0x14000d51e  test    rdx, rdx
0x14000d521  jz      short loc_14000D528
0x14000d523  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000d528  xor     ebx, ebx
0x14000d52a  jmp     loc_14000D645
0x14000d52f  mov     rdx, rdi
0x14000d532  mov     [rsp+48h+arg_10], 0
0x14000d53b  lea     rcx, [rsp+48h+arg_10]
0x14000d540  call    ?FindOrCreate@PCW_SILO_NEUTRAL_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z; PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> *,_UNICODE_STRING const *)
0x14000d545  mov     ebx, eax
0x14000d547  test    eax, eax
0x14000d549  js      loc_14000D636
0x14000d54f  mov     edx, 0A0h
0x14000d554  mov     r8d, 43776350h
0x14000d55a  lea     ecx, [rdx+60h]
0x14000d55d  call    cs:__imp_ExAllocatePool2
0x14000d564  nop     dword ptr [rax+rax+00h]
0x14000d569  test    rax, rax
0x14000d56c  jz      loc_14000D631
0x14000d572  mov     r8, rbp
0x14000d575  lea     rdx, [rsp+48h+arg_10]
0x14000d57a  mov     rcx, rax
0x14000d57d  call    ??0PCW_COUNTERSET@@AEAA@$$QEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@utl@@PEAVPCW_SILO_CONTEXT@@@Z; PCW_COUNTERSET::PCW_COUNTERSET(utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> &&,PCW_SILO_CONTEXT *)
0x14000d582  mov     rsi, rax
0x14000d585  test    rax, rax
0x14000d588  jz      loc_14000D631
0x14000d58e  mov     rdx, [rsp+48h+arg_10]
0x14000d593  test    rdx, rdx
0x14000d596  jz      short loc_14000D59D
0x14000d598  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000d59d  call    cs:__imp_KeEnterCriticalRegion
0x14000d5a4  nop     dword ptr [rax+rax+00h]
0x14000d5a9  xor     edx, edx
0x14000d5ab  mov     rcx, rbp
0x14000d5ae  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d5b5  nop     dword ptr [rax+rax+00h]
0x14000d5ba  mov     rdx, rdi; struct _UNICODE_STRING *
0x14000d5bd  mov     rcx, r15; struct _RTL_RB_TREE *
0x14000d5c0  call    ?FindNode@PCW_COUNTERSET_BASE@@KAPEAV1@PEAU_RTL_RB_TREE@@PEBU_UNICODE_STRING@@@Z; PCW_COUNTERSET_BASE::FindNode(_RTL_RB_TREE *,_UNICODE_STRING const *)
0x14000d5c5  mov     rbx, rax
0x14000d5c8  test    rax, rax
0x14000d5cb  jz      short loc_14000D5D9
0x14000d5cd  lock inc dword ptr [rax+98h]
0x14000d5d4  mov     rdi, rsi
0x14000d5d7  jmp     short loc_14000D5ED
0x14000d5d9  lea     rdx, [rsi+18h]; struct _UNICODE_STRING *
0x14000d5dd  mov     r8, rsi; struct PCW_COUNTERSET_BASE *
0x14000d5e0  mov     rcx, r15; struct _RTL_RB_TREE *
0x14000d5e3  call    ?InsertNode@PCW_COUNTERSET_BASE@@KAXPEAU_RTL_RB_TREE@@PEBU_UNICODE_STRING@@PEAV1@@Z; PCW_COUNTERSET_BASE::InsertNode(_RTL_RB_TREE *,_UNICODE_STRING const *,PCW_COUNTERSET_BASE *)
0x14000d5e8  xor     edi, edi
0x14000d5ea  mov     rbx, rsi
0x14000d5ed  xor     edx, edx
0x14000d5ef  mov     rcx, rbp
0x14000d5f2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d5f9  nop     dword ptr [rax+rax+00h]
0x14000d5fe  call    cs:__imp_KeLeaveCriticalRegion
0x14000d605  nop     dword ptr [rax+rax+00h]
0x14000d60a  test    rdi, rdi
0x14000d60d  jz      loc_14000D518
0x14000d613  mov     rcx, rdi; this
0x14000d616  call    ??1PCW_COUNTERSET@@AEAA@XZ; PCW_COUNTERSET::~PCW_COUNTERSET(void)
0x14000d61b  xor     edx, edx; Tag
0x14000d61d  mov     rcx, rdi; P
0x14000d620  call    cs:__imp_ExFreePoolWithTag
0x14000d627  nop     dword ptr [rax+rax+00h]
0x14000d62c  jmp     loc_14000D518
0x14000d631  mov     ebx, 0C0000017h
0x14000d636  mov     rdx, [rsp+48h+arg_10]
0x14000d63b  test    rdx, rdx
0x14000d63e  jz      short loc_14000D645
0x14000d640  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000d645  mov     eax, ebx
0x14000d647  mov     rbx, [rsp+48h+arg_0]
0x14000d64c  add     rsp, 20h
0x14000d650  pop     r15
0x14000d652  pop     r14
0x14000d654  pop     rdi
0x14000d655  pop     rsi
0x14000d656  pop     rbp
0x14000d657  retn
```
