# VidMmProcessAsyncOperation(void *)

- ea: `0x140111820`
- end: `0x140111a8d`
- name: `?VidMmProcessAsyncOperation@@YAXPEAX@Z`
- size: `621`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400120fc`
- `0x1400167c0`
- `0x14002e6c0`
- `0x1400344cc`
- `0x1400bf29c`
- `0x140111820`
- `0x140111a94`
- `0x140111ae0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14011183f`
- `ntoskrnl!ObfDereferenceObject` at `0x1401118a1`
- `ntoskrnl!ObfDereferenceObject` at `0x14011183f`
- `ntoskrnl!ObfDereferenceObject` at `0x1401118a1`
- `ntoskrnl!KeDelayExecutionThread` at `0x140111a5b`
- `ntoskrnl!KeDelayExecutionThread` at `0x140111a5b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14011195a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401119e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14011195a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401119e9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14011196b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401119fa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14011196b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401119fa`
- `ntoskrnl!KeSetEvent` at `0x140111993`
- `ntoskrnl!KeSetEvent` at `0x140111993`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401119a8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401119a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401119b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401119b4`
- `watchdog!WdLogSingleEntry1` at `0x140111a33`
- `watchdog!WdLogSingleEntry1` at `0x140111a33`
- `dxgkrnl!DxgkUnreferenceDxgAllocation` at `0x1401119d8`
- `dxgkrnl!DxgkUnreferenceDxgAllocation` at `0x1401119d8`
- `dxgkrnl!DxgkUnreferenceDxgResource` at `0x1401119c8`
- `dxgkrnl!DxgkUnreferenceDxgResource` at `0x1401119c8`

## pseudocode

```c
void __fastcall VidMmProcessAsyncOperation(void *a1, __int64 a2, unsigned int a3)
{
  int v4; // ecx
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // ecx
  __int64 v8; // rax
  int v9; // ecx
  int v10; // r8d
  struct _KEVENT *v11; // r15
  __int64 v12; // r14
  __int64 v13; // rbp
  VIDMM_GLOBAL_ALLOC_NONPAGED *HasOutstandingPresentReferences; // rcx
  int v16; // eax
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v4 = *((_DWORD *)a1 + 8) - 1;
  if ( v4 )
  {
    v7 = v4 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        v11 = (struct _KEVENT *)*((_QWORD *)a1 + 5);
        v12 = *(_QWORD *)(*((_QWORD *)a1 + 6) + 24LL);
        v18 = v12;
        v13 = **(_QWORD **)v12 + 216LL;
        if ( **(_QWORD **)v12 != -216 )
        {
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(v13, 0);
        }
        while ( 1 )
        {
          HasOutstandingPresentReferences = *(VIDMM_GLOBAL_ALLOC_NONPAGED **)(v12 + 96);
          if ( *(int *)(v12 + 104) > 0 )
            LOBYTE(HasOutstandingPresentReferences) = 1;
          else
            HasOutstandingPresentReferences = (VIDMM_GLOBAL_ALLOC_NONPAGED *)VIDMM_GLOBAL_ALLOC_NONPAGED::HasOutstandingPresentReferences(HasOutstandingPresentReferences);
          if ( !(_BYTE)HasOutstandingPresentReferences )
            break;
          if ( *(_DWORD *)(*(_QWORD *)(v12 + 96) + 16LL) > 1u )
            break;
          v16 = VIDMM_GLOBAL::WaitOnAllocationPresentQueue(
                  HasOutstandingPresentReferences,
                  (struct VIDMM_MULTI_ALLOC *)v12,
                  a3);
          if ( v16 >= 0 )
            break;
          WdLogSingleEntry1(3, v16);
          WdLogGlobalForLineNumber = 831;
          Interval.QuadPart = -150;
          KeDelayExecutionThread(0, 0, &Interval);
        }
        VidMmCompleteAsyncUnpin(v11, &v18, v13);
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(&v11[1709], 0);
        v11[1709].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)KeGetCurrentThread();
        if ( v11[1711].Header.LockNV-- == 1 )
          KeSetEvent(v11 + 1710, 0, 0);
        v11[1709].Header.WaitListHead.Flink = 0;
        ExReleasePushLockExclusiveEx(&v11[1709], 0);
        KeLeaveCriticalRegion();
        DxgkUnreferenceDxgResource(*(struct DXGRESOURCE **)(*((_QWORD *)a1 + 6) + 40LL));
        DxgkUnreferenceDxgAllocation(*((struct DXGALLOCATION **)a1 + 6));
      }
    }
    else
    {
      VidMmUnmapView(*((struct _EPROCESS **)a1 + 5), *((void **)a1 + 7));
      v8 = *((_QWORD *)a1 + 8);
      if ( v8 )
        _InterlockedDecrement((volatile signed __int32 *)(v8 + 428));
      ObfDereferenceObject(*((PVOID *)a1 + 6));
      if ( (byte_140087201 & 1) != 0 )
        McTemplateK0ppp_EtwWriteTransfer(
          v9,
          (unsigned int)&EndVidMmUnmapViewAsync,
          v10,
          *((_QWORD *)a1 + 5),
          *((_QWORD *)a1 + 6),
          *((_QWORD *)a1 + 7));
    }
  }
  else
  {
    ObfDereferenceObject(*((PVOID *)a1 + 5));
    if ( (byte_140087201 & 1) != 0 )
      McTemplateK0x_EtwWriteTransfer(v5, &EndVidMmDereferenceObjectAsync, v6, *((_QWORD *)a1 + 5));
  }
  operator delete(a1);
  _InterlockedDecrement(&g_VidMmAsyncOpPendingCount);
}

```

## disassembly

```asm
0x140111820  mov     [rsp+arg_10], rbx
0x140111825  push    rbp
0x140111826  push    rsi
0x140111827  push    rdi
0x140111828  push    r14
0x14011182a  push    r15
0x14011182c  sub     rsp, 30h
0x140111830  mov     rbx, rcx
0x140111833  mov     ecx, [rcx+20h]
0x140111836  sub     ecx, 1
0x140111839  jnz     short loc_14011187E
0x14011183b  mov     rcx, [rbx+28h]; Object
0x14011183f  call    cs:__imp_ObfDereferenceObject
0x140111846  nop     dword ptr [rax+rax+00h]
0x14011184b  mov     edi, 1
0x140111850  test    cs:byte_140087201, dil
0x140111857  jnz     loc_140111A78
0x14011185d  mov     rcx, rbx; void *
0x140111860  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140111865  lock dec cs:?g_VidMmAsyncOpPendingCount@@3JA; long g_VidMmAsyncOpPendingCount
0x14011186c  mov     rbx, [rsp+58h+arg_10]
0x140111871  add     rsp, 30h
0x140111875  pop     r15
0x140111877  pop     r14
0x140111879  pop     rdi
0x14011187a  pop     rsi
0x14011187b  pop     rbp
0x14011187c  retn
0x14011187e  sub     ecx, 1
0x140111881  jnz     short loc_1401118E2
0x140111883  mov     rdx, [rbx+38h]; void *
0x140111887  mov     rcx, [rbx+28h]; struct _EPROCESS *
0x14011188b  call    ?VidMmUnmapView@@YAXPEAU_EPROCESS@@PEAX@Z; VidMmUnmapView(_EPROCESS *,void *)
0x140111890  mov     rax, [rbx+40h]
0x140111894  test    rax, rax
0x140111897  jnz     loc_140111A6C
0x14011189d  mov     rcx, [rbx+30h]; Object
0x1401118a1  call    cs:__imp_ObfDereferenceObject
0x1401118a8  nop     dword ptr [rax+rax+00h]
0x1401118ad  mov     edi, 1
0x1401118b2  test    cs:byte_140087201, dil
0x1401118b9  jz      short loc_14011185D
0x1401118bb  mov     rax, [rbx+38h]
0x1401118bf  lea     rdx, EndVidMmUnmapViewAsync
0x1401118c6  mov     r9, [rbx+28h]
0x1401118ca  mov     [rsp+58h+var_30], rax
0x1401118cf  mov     rax, [rbx+30h]
0x1401118d3  mov     [rsp+58h+var_38], rax
0x1401118d8  call    McTemplateK0ppp_EtwWriteTransfer
0x1401118dd  jmp     loc_14011185D
0x1401118e2  cmp     ecx, 1
0x1401118e5  jnz     loc_14011185D
0x1401118eb  mov     rax, [rbx+30h]
0x1401118ef  xor     esi, esi
0x1401118f1  mov     r15, [rbx+28h]
0x1401118f5  mov     r14, [rax+18h]
0x1401118f9  mov     [rsp+58h+arg_8], r14
0x1401118fe  mov     rax, [r14]
0x140111901  mov     rbp, [rax]
0x140111904  add     rbp, 0D8h
0x14011190b  jnz     loc_1401119E9
0x140111911  mov     edi, 1
0x140111916  mov     eax, [r14+68h]
0x14011191a  mov     rcx, [r14+60h]; this
0x14011191e  test    eax, eax
0x140111920  jg      loc_140111A0B
0x140111926  call    ?HasOutstandingPresentReferences@VIDMM_GLOBAL_ALLOC_NONPAGED@@QEBA_NXZ; VIDMM_GLOBAL_ALLOC_NONPAGED::HasOutstandingPresentReferences(void)
0x14011192b  test    al, al
0x14011192d  movzx   ecx, sil
0x140111931  cmovnz  ecx, edi; this
0x140111934  mov     rax, [r14+60h]
0x140111938  mov     edx, [rax+10h]
0x14011193b  test    cl, cl
0x14011193d  jnz     loc_140111A13
0x140111943  mov     r8, rbp
0x140111946  lea     rdx, [rsp+58h+arg_8]
0x14011194b  mov     rcx, r15
0x14011194e  call    VidMmCompleteAsyncUnpin
0x140111953  lea     rdi, [r15+0A038h]
0x14011195a  call    cs:__imp_KeEnterCriticalRegion
0x140111961  nop     dword ptr [rax+rax+00h]
0x140111966  xor     edx, edx
0x140111968  mov     rcx, rdi
0x14011196b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140111972  nop     dword ptr [rax+rax+00h]
0x140111977  mov     rax, gs:188h
0x140111980  mov     [rdi+8], rax
0x140111984  sub     dword ptr [rdi+30h], 1
0x140111988  jnz     short loc_14011199F
0x14011198a  lea     rcx, [rdi+18h]; Event
0x14011198e  xor     r8d, r8d; Wait
0x140111991  xor     edx, edx; Increment
0x140111993  call    cs:__imp_KeSetEvent
0x14011199a  nop     dword ptr [rax+rax+00h]
0x14011199f  xor     edx, edx
0x1401119a1  mov     [rdi+8], rsi
0x1401119a5  mov     rcx, rdi
0x1401119a8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401119af  nop     dword ptr [rax+rax+00h]
0x1401119b4  call    cs:__imp_KeLeaveCriticalRegion
0x1401119bb  nop     dword ptr [rax+rax+00h]
0x1401119c0  mov     rcx, [rbx+30h]
0x1401119c4  mov     rcx, [rcx+28h]
0x1401119c8  call    cs:__imp_?DxgkUnreferenceDxgResource@@YAXPEAVDXGRESOURCE@@@Z; DxgkUnreferenceDxgResource(DXGRESOURCE *)
0x1401119cf  nop     dword ptr [rax+rax+00h]
0x1401119d4  mov     rcx, [rbx+30h]
0x1401119d8  call    cs:__imp_?DxgkUnreferenceDxgAllocation@@YAXPEAVDXGALLOCATION@@@Z; DxgkUnreferenceDxgAllocation(DXGALLOCATION *)
0x1401119df  nop     dword ptr [rax+rax+00h]
0x1401119e4  jmp     loc_14011185D
0x1401119e9  call    cs:__imp_KeEnterCriticalRegion
0x1401119f0  nop     dword ptr [rax+rax+00h]
0x1401119f5  xor     edx, edx
0x1401119f7  mov     rcx, rbp
0x1401119fa  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140111a01  nop     dword ptr [rax+rax+00h]
0x140111a06  jmp     loc_140111911
0x140111a0b  mov     cl, dil
0x140111a0e  jmp     loc_140111934
0x140111a13  cmp     edx, edi
0x140111a15  ja      loc_140111943
0x140111a1b  mov     rdx, r14; struct VIDMM_MULTI_ALLOC *
0x140111a1e  call    ?WaitOnAllocationPresentQueue@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_MULTI_ALLOC@@I@Z; VIDMM_GLOBAL::WaitOnAllocationPresentQueue(VIDMM_MULTI_ALLOC *,uint)
0x140111a23  test    eax, eax
0x140111a25  jns     loc_140111943
0x140111a2b  movsxd  rdx, eax
0x140111a2e  mov     ecx, 3
0x140111a33  call    cs:__imp_WdLogSingleEntry1
0x140111a3a  nop     dword ptr [rax+rax+00h]
0x140111a3f  lea     r8, [rsp+58h+Interval]; Interval
0x140111a44  mov     cs:WdLogGlobalForLineNumber, 33Fh
0x140111a4e  xor     edx, edx; Alertable
0x140111a50  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFFF6Ah
0x140111a59  xor     ecx, ecx; WaitMode
0x140111a5b  call    cs:__imp_KeDelayExecutionThread
0x140111a62  nop     dword ptr [rax+rax+00h]
0x140111a67  jmp     loc_140111916
0x140111a6c  lock dec dword ptr [rax+1ACh]
0x140111a73  jmp     loc_14011189D
0x140111a78  mov     r9, [rbx+28h]
0x140111a7c  lea     rdx, EndVidMmDereferenceObjectAsync
0x140111a83  call    McTemplateK0x_EtwWriteTransfer
0x140111a88  jmp     loc_14011185D
```
