# FltRequestOperationStatusCallback

- ea: `0x18001c7a0`
- end: `0x18001c908`
- name: `FltRequestOperationStatusCallback`
- size: `360`
- prototype: `NTSTATUS __stdcall(PFLT_CALLBACK_DATA Data, PFLT_GET_OPERATION_STATUS_CALLBACK CallbackRoutine, PVOID RequesterContext)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180080ba0`

## callees

- `0x18001c7a0`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x18001c87a`
- `ntoskrnl!ObfReferenceObject` at `0x18001c87a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18001c80f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18001c80f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001c8ee`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001c8ee`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001c861`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001c861`
- `ntoskrnl!IoWithinStackLimits` at `0x18001c7ef`
- `ntoskrnl!IoWithinStackLimits` at `0x18001c7ef`

## pseudocode

```c
NTSTATUS __stdcall FltRequestOperationStatusCallback(
        PFLT_CALLBACK_DATA Data,
        PFLT_GET_OPERATION_STATUS_CALLBACK CallbackRoutine,
        PVOID RequesterContext)
{
  ULONG_PTR Information; // rcx
  _QWORD *v7; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  void *v9; // rcx
  ULONG_PTR v10; // rcx
  NTSTATUS result; // eax

  if ( (Data->Flags & 1) == 0 || (Data->Flags & 0x80000) != 0 || Data->Iopb->MajorFunction == 2 )
    return -1073741811;
  Information = Data[-2].IoStatus.Information;
  if ( !Information || !IoWithinStackLimits(Information, 0x30u) )
    return -1071906806;
  v7 = ExAllocateFromNPagedLookasideList(&stru_18003F3C0);
  if ( !v7 )
    return -1073741670;
  Iopb = Data->Iopb;
  *(_OWORD *)(v7 + 3) = *(_OWORD *)&Iopb->IrpFlags;
  *(_OWORD *)(v7 + 5) = *(_OWORD *)&Iopb->TargetInstance;
  *(_OWORD *)(v7 + 7) = *(_OWORD *)&Iopb->Parameters.QueryEa.EaList;
  *(_OWORD *)(v7 + 9) = *(_OWORD *)(&Iopb->Parameters.ReleaseForModifiedPageWriter + 3);
  v7[11] = Iopb->Parameters.Create.AllocationSize.QuadPart;
  if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v7[5] + 56LL), 1u) )
  {
    v9 = (void *)v7[4];
    if ( v9 )
      ObfReferenceObject(v9);
    v7[1] = CallbackRoutine;
    v7[2] = RequesterContext;
    v10 = Data[-2].IoStatus.Information;
    *v7 = *(_QWORD *)(v10 + 32);
    result = 0;
    *(_QWORD *)(v10 + 32) = v7;
  }
  else
  {
    ExFreeToNPagedLookasideList(&stru_18003F3C0, v7);
    return -1071906805;
  }
  return result;
}

```

## disassembly

```asm
0x18001c7a0  mov     [rsp+arg_8], rbp
0x18001c7a5  mov     [rsp+arg_10], rsi
0x18001c7aa  push    rdi
0x18001c7ab  sub     rsp, 20h
0x18001c7af  mov     eax, [rcx]
0x18001c7b1  mov     rsi, r8
0x18001c7b4  mov     rbp, rdx
0x18001c7b7  mov     rdi, rcx
0x18001c7ba  test    al, 1
0x18001c7bc  jz      loc_18001C8B8
0x18001c7c2  bt      eax, 13h
0x18001c7c6  jb      loc_18001C8B8
0x18001c7cc  mov     rax, [rcx+10h]
0x18001c7d0  cmp     byte ptr [rax+4], 2
0x18001c7d4  jz      loc_18001C8B8
0x18001c7da  mov     rcx, [rcx-90h]; RegionStart
0x18001c7e1  test    rcx, rcx
0x18001c7e4  jz      loc_18001C8CE
0x18001c7ea  mov     edx, 30h ; '0'; RegionSize
0x18001c7ef  call    cs:__imp_IoWithinStackLimits
0x18001c7f6  nop     dword ptr [rax+rax+00h]
0x18001c7fb  test    eax, eax
0x18001c7fd  jz      loc_18001C8CE
0x18001c803  lea     rcx, stru_18003F3C0; Lookaside
0x18001c80a  mov     [rsp+28h+arg_0], rbx
0x18001c80f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18001c816  nop     dword ptr [rax+rax+00h]
0x18001c81b  mov     rbx, rax
0x18001c81e  test    rax, rax
0x18001c821  jz      loc_18001C901
0x18001c827  mov     rax, [rdi+10h]
0x18001c82b  mov     edx, 1; Count
0x18001c830  movups  xmm0, xmmword ptr [rax]
0x18001c833  movups  xmmword ptr [rbx+18h], xmm0
0x18001c837  movups  xmm1, xmmword ptr [rax+10h]
0x18001c83b  movups  xmmword ptr [rbx+28h], xmm1
0x18001c83f  movups  xmm0, xmmword ptr [rax+20h]
0x18001c843  movups  xmmword ptr [rbx+38h], xmm0
0x18001c847  movups  xmm1, xmmword ptr [rax+30h]
0x18001c84b  movups  xmmword ptr [rbx+48h], xmm1
0x18001c84f  movsd   xmm0, qword ptr [rax+40h]
0x18001c854  movsd   qword ptr [rbx+58h], xmm0
0x18001c859  mov     rcx, [rbx+28h]
0x18001c85d  mov     rcx, [rcx+38h]; RunRefCacheAware
0x18001c861  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x18001c868  nop     dword ptr [rax+rax+00h]
0x18001c86d  test    al, al
0x18001c86f  jz      short loc_18001C8E4
0x18001c871  mov     rcx, [rbx+20h]; Object
0x18001c875  test    rcx, rcx
0x18001c878  jz      short loc_18001C886
0x18001c87a  call    cs:__imp_ObfReferenceObject
0x18001c881  nop     dword ptr [rax+rax+00h]
0x18001c886  mov     [rbx+8], rbp
0x18001c88a  mov     [rbx+10h], rsi
0x18001c88e  mov     rcx, [rdi-90h]
0x18001c895  mov     rax, [rcx+20h]
0x18001c899  mov     [rbx], rax
0x18001c89c  xor     eax, eax
0x18001c89e  mov     [rcx+20h], rbx
0x18001c8a2  mov     rbx, [rsp+28h+arg_0]
0x18001c8a7  mov     rbp, [rsp+28h+arg_8]
0x18001c8ac  mov     rsi, [rsp+28h+arg_10]
0x18001c8b1  add     rsp, 20h
0x18001c8b5  pop     rdi
0x18001c8b6  retn
0x18001c8b8  mov     eax, 0C000000Dh
0x18001c8bd  mov     rbp, [rsp+28h+arg_8]
0x18001c8c2  mov     rsi, [rsp+28h+arg_10]
0x18001c8c7  add     rsp, 20h
0x18001c8cb  pop     rdi
0x18001c8cc  retn
0x18001c8ce  mov     rbp, [rsp+28h+arg_8]
0x18001c8d3  mov     eax, 0C01C000Ah
0x18001c8d8  mov     rsi, [rsp+28h+arg_10]
0x18001c8dd  add     rsp, 20h
0x18001c8e1  pop     rdi
0x18001c8e2  retn
0x18001c8e4  mov     rdx, rbx; Entry
0x18001c8e7  lea     rcx, stru_18003F3C0; Lookaside
0x18001c8ee  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001c8f5  nop     dword ptr [rax+rax+00h]
0x18001c8fa  mov     eax, 0C01C000Bh
0x18001c8ff  jmp     short loc_18001C8A2
0x18001c901  mov     eax, 0C000009Ah
0x18001c906  jmp     short loc_18001C8A2
```
