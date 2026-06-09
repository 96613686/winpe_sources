# SmbCeHoldExchangeForSessionRecovery

- ea: `0x140044a9c`
- end: `0x140044c5b`
- name: `SmbCeHoldExchangeForSessionRecovery`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140044790`

## callees

- `0x14000a440`
- `0x14000cd90`
- `0x14000e52c`
- `0x14000ebd8`
- `0x140044a9c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044c3f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044c3f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044c33`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044c33`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140044ace`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140044ace`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140044ab9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140044ab9`
- `rdbss!RxDispatchToWorkerThread` at `0x140044bad`
- `rdbss!RxDispatchToWorkerThread` at `0x140044bad`
- `mrxsmb!MRxSmbDeviceObject` at `0x140044b8c`

## pseudocode

```c
__int64 __fastcall SmbCeHoldExchangeForSessionRecovery(__int64 a1)
{
  __int64 v1; // rbp
  int v3; // eax
  NTSTATUS v4; // edi
  __int64 Object; // rax
  __int64 v6; // r14
  _QWORD *v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  _QWORD *v10; // rcx

  v1 = *(_QWORD *)(a1 + 88);
  if ( v1 )
    v1 = *(_QWORD *)(v1 + 96);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
  v3 = *(_DWORD *)(v1 + 12);
  if ( (v3 & 0xFFFFFFF6) == 0 && v3 != 8 )
  {
    v4 = -1073741802;
    goto LABEL_22;
  }
  Object = SmbMmAllocateObject(3);
  v6 = Object;
  if ( !Object )
  {
    v4 = -1073741670;
    goto LABEL_22;
  }
  *(_DWORD *)(Object + 48) = 4;
  *(_QWORD *)(Object + 56) = a1;
  *(_QWORD *)(Object + 64) = SmbPseContinueOrdinaryExchange;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 116));
  v7 = *(_QWORD **)(v1 + 88);
  if ( *v7 != v1 + 80 )
LABEL_20:
    __fastfail(3u);
  v8 = Object + 32;
  *(_QWORD *)(Object + 32) = v1 + 80;
  *(_QWORD *)(Object + 40) = v7;
  *v7 = Object + 32;
  *(_QWORD *)(v1 + 88) = Object + 32;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids, a1);
  v4 = 259;
  if ( !*(_BYTE *)(v1 + 409) )
  {
    *(_BYTE *)(v1 + 409) = 1;
    v4 = RxDispatchToWorkerThread(MRxSmbDeviceObject, DelayedWorkQueue, SmbCeReconnect, *(PVOID *)(a1 + 88));
    if ( v4 >= 0 )
    {
      v4 = 259;
      goto LABEL_22;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        44,
        WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
        *(_QWORD *)(a1 + 88),
        a1);
    v9 = *(_QWORD *)v8;
    if ( *(_QWORD *)(*(_QWORD *)v8 + 8LL) == v8 )
    {
      v10 = *(_QWORD **)(v6 + 40);
      if ( *v10 == v8 )
      {
        *v10 = v9;
        *(_QWORD *)(v9 + 8) = v10;
        SmbMmFreeObject(v6);
        _InterlockedDecrement((volatile signed __int32 *)(a1 + 116));
        goto LABEL_22;
      }
    }
    goto LABEL_20;
  }
LABEL_22:
  ExReleaseResourceLite(&s_SmbCeDbResource);
  KeLeaveCriticalRegion();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140044a9c  push    rbx
0x140044a9e  push    rbp
0x140044a9f  push    rsi
0x140044aa0  push    rdi
0x140044aa1  push    r13
0x140044aa3  push    r14
0x140044aa5  sub     rsp, 38h
0x140044aa9  mov     rbp, [rcx+58h]
0x140044aad  mov     rbx, rcx
0x140044ab0  test    rbp, rbp
0x140044ab3  jz      short loc_140044AB9
0x140044ab5  mov     rbp, [rbp+60h]
0x140044ab9  call    cs:__imp_KeEnterCriticalRegion
0x140044ac0  nop     dword ptr [rax+rax+00h]
0x140044ac5  mov     dl, 1; Wait
0x140044ac7  lea     rcx, s_SmbCeDbResource; Resource
0x140044ace  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140044ad5  nop     dword ptr [rax+rax+00h]
0x140044ada  mov     eax, [rbp+0Ch]
0x140044add  test    eax, 0FFFFFFF6h
0x140044ae2  jnz     short loc_140044AF3
0x140044ae4  cmp     eax, 8
0x140044ae7  jz      short loc_140044AF3
0x140044ae9  mov     edi, 0C0000016h
0x140044aee  jmp     loc_140044C2C
0x140044af3  mov     ecx, 3
0x140044af8  call    SmbMmAllocateObject
0x140044afd  mov     r14, rax
0x140044b00  test    rax, rax
0x140044b03  jz      loc_140044C27
0x140044b09  mov     dword ptr [rax+30h], 4
0x140044b10  mov     [rax+38h], rbx
0x140044b14  lea     rax, SmbPseContinueOrdinaryExchange
0x140044b1b  mov     [r14+40h], rax
0x140044b1f  lock inc dword ptr [rbx+74h]
0x140044b23  lea     rax, [rbp+50h]
0x140044b27  mov     rcx, [rax+8]
0x140044b2b  cmp     [rcx], rax
0x140044b2e  jnz     loc_140044C20
0x140044b34  lea     rsi, [r14+20h]
0x140044b38  mov     [rsi], rax
0x140044b3b  mov     [rsi+8], rcx
0x140044b3f  mov     [rcx], rsi
0x140044b42  mov     [rax+8], rsi
0x140044b46  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044b4d  lea     r13, WPP_GLOBAL_Control
0x140044b54  cmp     rcx, r13
0x140044b57  jz      short loc_140044B7A
0x140044b59  test    dword ptr [rcx+2Ch], 200h
0x140044b60  jz      short loc_140044B7A
0x140044b62  mov     rcx, [rcx+18h]
0x140044b66  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x140044b6d  mov     edx, 2Bh ; '+'
0x140044b72  mov     r9, rbx
0x140044b75  call    WPP_SF_q
0x140044b7a  cmp     byte ptr [rbp+199h], 0
0x140044b81  mov     edi, 103h
0x140044b86  jnz     loc_140044C2C
0x140044b8c  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140044b93  lea     r8, SmbCeReconnect; Routine
0x140044b9a  mov     byte ptr [rbp+199h], 1
0x140044ba1  mov     edx, 1; WorkQueueType
0x140044ba6  mov     r9, [rbx+58h]; pContext
0x140044baa  mov     rcx, [rcx]; pMRxDeviceObject
0x140044bad  call    cs:__imp_RxDispatchToWorkerThread
0x140044bb4  nop     dword ptr [rax+rax+00h]
0x140044bb9  mov     edi, eax
0x140044bbb  test    eax, eax
0x140044bbd  jns     short loc_140044C19
0x140044bbf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044bc6  cmp     rcx, r13
0x140044bc9  jz      short loc_140044BF2
0x140044bcb  test    dword ptr [rcx+2Ch], 100h
0x140044bd2  jz      short loc_140044BF2
0x140044bd4  mov     r9, [rbx+58h]
0x140044bd8  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x140044bdf  mov     rcx, [rcx+18h]
0x140044be3  mov     edx, 2Ch ; ','
0x140044be8  mov     [rsp+68h+var_48], rbx
0x140044bed  call    WPP_SF_qq
0x140044bf2  mov     rax, [rsi]
0x140044bf5  cmp     [rax+8], rsi
0x140044bf9  jnz     short loc_140044C20
0x140044bfb  mov     rcx, [rsi+8]
0x140044bff  cmp     [rcx], rsi
0x140044c02  jnz     short loc_140044C20
0x140044c04  mov     [rcx], rax
0x140044c07  mov     [rax+8], rcx
0x140044c0b  mov     rcx, r14
0x140044c0e  call    SmbMmFreeObject
0x140044c13  lock dec dword ptr [rbx+74h]
0x140044c17  jmp     short loc_140044C2C
0x140044c19  mov     edi, 103h
0x140044c1e  jmp     short loc_140044C2C
0x140044c20  mov     ecx, 3
0x140044c25  int     29h; Win8: RtlFailFast(ecx)
0x140044c27  mov     edi, 0C000009Ah
0x140044c2c  lea     rcx, s_SmbCeDbResource; Resource
0x140044c33  call    cs:__imp_ExReleaseResourceLite
0x140044c3a  nop     dword ptr [rax+rax+00h]
0x140044c3f  call    cs:__imp_KeLeaveCriticalRegion
0x140044c46  nop     dword ptr [rax+rax+00h]
0x140044c4b  mov     eax, edi
0x140044c4d  add     rsp, 38h
0x140044c51  pop     r14
0x140044c53  pop     r13
0x140044c55  pop     rdi
0x140044c56  pop     rsi
0x140044c57  pop     rbp
0x140044c58  pop     rbx
0x140044c59  retn
```
