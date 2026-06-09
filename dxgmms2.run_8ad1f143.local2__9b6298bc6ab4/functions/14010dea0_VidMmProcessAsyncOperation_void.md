# VidMmProcessAsyncOperation(void *)

- ea: `0x14010dea0`
- end: `0x14010e10d`
- name: `?VidMmProcessAsyncOperation@@YAXPEAX@Z`
- size: `621`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000dbfc`
- `0x14001265c`
- `0x140030ae0`
- `0x1400357d8`
- `0x1400bb7fc`
- `0x14010dea0`
- `0x14010e114`
- `0x14010e160`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14010debf`
- `ntoskrnl!ObfDereferenceObject` at `0x14010df21`
- `ntoskrnl!ObfDereferenceObject` at `0x14010debf`
- `ntoskrnl!ObfDereferenceObject` at `0x14010df21`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010e0db`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010e0db`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010dfda`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010e069`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010dfda`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010e069`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010dfeb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010e07a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010dfeb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010e07a`
- `ntoskrnl!KeSetEvent` at `0x14010e013`
- `ntoskrnl!KeSetEvent` at `0x14010e013`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010e028`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010e028`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010e034`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010e034`
- `watchdog!WdLogSingleEntry1` at `0x14010e0b3`
- `watchdog!WdLogSingleEntry1` at `0x14010e0b3`
- `dxgkrnl!DxgkUnreferenceDxgAllocation` at `0x14010e058`
- `dxgkrnl!DxgkUnreferenceDxgAllocation` at `0x14010e058`
- `dxgkrnl!DxgkUnreferenceDxgResource` at `0x14010e048`
- `dxgkrnl!DxgkUnreferenceDxgResource` at `0x14010e048`

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
      if ( (byte_140086201 & 1) != 0 )
        McTemplateK0ppp_EtwWriteTransfer(
          v9,
          (unsigned int)EndVidMmUnmapViewAsync,
          v10,
          *((_QWORD *)a1 + 5),
          *((_QWORD *)a1 + 6),
          *((_QWORD *)a1 + 7));
    }
  }
  else
  {
    ObfDereferenceObject(*((PVOID *)a1 + 5));
    if ( (byte_140086201 & 1) != 0 )
      McTemplateK0x_EtwWriteTransfer(v5, EndVidMmDereferenceObjectAsync, v6, *((_QWORD *)a1 + 5));
  }
  operator delete(a1);
  _InterlockedDecrement(&g_VidMmAsyncOpPendingCount);
}

```

## disassembly

```asm
0x14010dea0  mov     [rsp+arg_10], rbx
0x14010dea5  push    rbp
0x14010dea6  push    rsi
0x14010dea7  push    rdi
0x14010dea8  push    r14
0x14010deaa  push    r15
0x14010deac  sub     rsp, 30h
0x14010deb0  mov     rbx, rcx
0x14010deb3  mov     ecx, [rcx+20h]
0x14010deb6  sub     ecx, 1
0x14010deb9  jnz     short loc_14010DEFE
0x14010debb  mov     rcx, [rbx+28h]; Object
0x14010debf  call    cs:__imp_ObfDereferenceObject
0x14010dec6  nop     dword ptr [rax+rax+00h]
0x14010decb  mov     edi, 1
0x14010ded0  test    cs:byte_140086201, dil
0x14010ded7  jnz     loc_14010E0F8
0x14010dedd  mov     rcx, rbx; void *
0x14010dee0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14010dee5  lock dec cs:?g_VidMmAsyncOpPendingCount@@3JA; long g_VidMmAsyncOpPendingCount
0x14010deec  mov     rbx, [rsp+58h+arg_10]
0x14010def1  add     rsp, 30h
0x14010def5  pop     r15
0x14010def7  pop     r14
0x14010def9  pop     rdi
0x14010defa  pop     rsi
0x14010defb  pop     rbp
0x14010defc  retn
0x14010defe  sub     ecx, 1
0x14010df01  jnz     short loc_14010DF62
0x14010df03  mov     rdx, [rbx+38h]; void *
0x14010df07  mov     rcx, [rbx+28h]; struct _EPROCESS *
0x14010df0b  call    ?VidMmUnmapView@@YAXPEAU_EPROCESS@@PEAX@Z; VidMmUnmapView(_EPROCESS *,void *)
0x14010df10  mov     rax, [rbx+40h]
0x14010df14  test    rax, rax
0x14010df17  jnz     loc_14010E0EC
0x14010df1d  mov     rcx, [rbx+30h]; Object
0x14010df21  call    cs:__imp_ObfDereferenceObject
0x14010df28  nop     dword ptr [rax+rax+00h]
0x14010df2d  mov     edi, 1
0x14010df32  test    cs:byte_140086201, dil
0x14010df39  jz      short loc_14010DEDD
0x14010df3b  mov     rax, [rbx+38h]
0x14010df3f  lea     rdx, EndVidMmUnmapViewAsync
0x14010df46  mov     r9, [rbx+28h]
0x14010df4a  mov     [rsp+58h+var_30], rax
0x14010df4f  mov     rax, [rbx+30h]
0x14010df53  mov     [rsp+58h+var_38], rax
0x14010df58  call    McTemplateK0ppp_EtwWriteTransfer
0x14010df5d  jmp     loc_14010DEDD
0x14010df62  cmp     ecx, 1
0x14010df65  jnz     loc_14010DEDD
0x14010df6b  mov     rax, [rbx+30h]
0x14010df6f  xor     esi, esi
0x14010df71  mov     r15, [rbx+28h]
0x14010df75  mov     r14, [rax+18h]
0x14010df79  mov     [rsp+58h+arg_8], r14
0x14010df7e  mov     rax, [r14]
0x14010df81  mov     rbp, [rax]
0x14010df84  add     rbp, 0D8h
0x14010df8b  jnz     loc_14010E069
0x14010df91  mov     edi, 1
0x14010df96  mov     eax, [r14+68h]
0x14010df9a  mov     rcx, [r14+60h]; this
0x14010df9e  test    eax, eax
0x14010dfa0  jg      loc_14010E08B
0x14010dfa6  call    ?HasOutstandingPresentReferences@VIDMM_GLOBAL_ALLOC_NONPAGED@@QEBA_NXZ; VIDMM_GLOBAL_ALLOC_NONPAGED::HasOutstandingPresentReferences(void)
0x14010dfab  test    al, al
0x14010dfad  movzx   ecx, sil
0x14010dfb1  cmovnz  ecx, edi; this
0x14010dfb4  mov     rax, [r14+60h]
0x14010dfb8  mov     edx, [rax+10h]
0x14010dfbb  test    cl, cl
0x14010dfbd  jnz     loc_14010E093
0x14010dfc3  mov     r8, rbp
0x14010dfc6  lea     rdx, [rsp+58h+arg_8]
0x14010dfcb  mov     rcx, r15
0x14010dfce  call    VidMmCompleteAsyncUnpin
0x14010dfd3  lea     rdi, [r15+0A038h]
0x14010dfda  call    cs:__imp_KeEnterCriticalRegion
0x14010dfe1  nop     dword ptr [rax+rax+00h]
0x14010dfe6  xor     edx, edx
0x14010dfe8  mov     rcx, rdi
0x14010dfeb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14010dff2  nop     dword ptr [rax+rax+00h]
0x14010dff7  mov     rax, gs:188h
0x14010e000  mov     [rdi+8], rax
0x14010e004  sub     dword ptr [rdi+30h], 1
0x14010e008  jnz     short loc_14010E01F
0x14010e00a  lea     rcx, [rdi+18h]; Event
0x14010e00e  xor     r8d, r8d; Wait
0x14010e011  xor     edx, edx; Increment
0x14010e013  call    cs:__imp_KeSetEvent
0x14010e01a  nop     dword ptr [rax+rax+00h]
0x14010e01f  xor     edx, edx
0x14010e021  mov     [rdi+8], rsi
0x14010e025  mov     rcx, rdi
0x14010e028  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14010e02f  nop     dword ptr [rax+rax+00h]
0x14010e034  call    cs:__imp_KeLeaveCriticalRegion
0x14010e03b  nop     dword ptr [rax+rax+00h]
0x14010e040  mov     rcx, [rbx+30h]
0x14010e044  mov     rcx, [rcx+28h]
0x14010e048  call    cs:__imp_?DxgkUnreferenceDxgResource@@YAXPEAVDXGRESOURCE@@@Z; DxgkUnreferenceDxgResource(DXGRESOURCE *)
0x14010e04f  nop     dword ptr [rax+rax+00h]
0x14010e054  mov     rcx, [rbx+30h]
0x14010e058  call    cs:__imp_?DxgkUnreferenceDxgAllocation@@YAXPEAVDXGALLOCATION@@@Z; DxgkUnreferenceDxgAllocation(DXGALLOCATION *)
0x14010e05f  nop     dword ptr [rax+rax+00h]
0x14010e064  jmp     loc_14010DEDD
0x14010e069  call    cs:__imp_KeEnterCriticalRegion
0x14010e070  nop     dword ptr [rax+rax+00h]
0x14010e075  xor     edx, edx
0x14010e077  mov     rcx, rbp
0x14010e07a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14010e081  nop     dword ptr [rax+rax+00h]
0x14010e086  jmp     loc_14010DF91
0x14010e08b  mov     cl, dil
0x14010e08e  jmp     loc_14010DFB4
0x14010e093  cmp     edx, edi
0x14010e095  ja      loc_14010DFC3
0x14010e09b  mov     rdx, r14; struct VIDMM_MULTI_ALLOC *
0x14010e09e  call    ?WaitOnAllocationPresentQueue@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_MULTI_ALLOC@@I@Z; VIDMM_GLOBAL::WaitOnAllocationPresentQueue(VIDMM_MULTI_ALLOC *,uint)
0x14010e0a3  test    eax, eax
0x14010e0a5  jns     loc_14010DFC3
0x14010e0ab  movsxd  rdx, eax
0x14010e0ae  mov     ecx, 3
0x14010e0b3  call    cs:__imp_WdLogSingleEntry1
0x14010e0ba  nop     dword ptr [rax+rax+00h]
0x14010e0bf  lea     r8, [rsp+58h+Interval]; Interval
0x14010e0c4  mov     cs:WdLogGlobalForLineNumber, 33Fh
0x14010e0ce  xor     edx, edx; Alertable
0x14010e0d0  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFFF6Ah
0x14010e0d9  xor     ecx, ecx; WaitMode
0x14010e0db  call    cs:__imp_KeDelayExecutionThread
0x14010e0e2  nop     dword ptr [rax+rax+00h]
0x14010e0e7  jmp     loc_14010DF96
0x14010e0ec  lock dec dword ptr [rax+1ACh]
0x14010e0f3  jmp     loc_14010DF1D
0x14010e0f8  mov     r9, [rbx+28h]
0x14010e0fc  lea     rdx, EndVidMmDereferenceObjectAsync
0x14010e103  call    McTemplateK0x_EtwWriteTransfer
0x14010e108  jmp     loc_14010DEDD
```
