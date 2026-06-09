# PcpAddFilter

- ea: `0x14000d284`
- end: `0x14000d702`
- name: `PcpAddFilter`
- size: `1150`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x14001d47c`
- `0x14001d5bc`

## callees

- `0x14000577c`
- `0x1400057b0`
- `0x140007e10`
- `0x140009100`
- `0x14000d284`
- `0x14000dbb8`
- `0x14000eb54`
- `0x140013110`
- `0x140013600`
- `0x14001d008`
- `0x14001ee0c`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14000d438`
- `ntoskrnl!ExUuidCreate` at `0x14000d438`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d619`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d631`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d619`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d631`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d51b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d51b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d3f8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d3f8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000d607`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000d607`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6b2`
- `ntoskrnl!ExAllocatePool2` at `0x14000d35a`
- `ntoskrnl!ExAllocatePool2` at `0x14000d35a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000d3cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000d3cb`
- `NETIO!HfAllocateHandle32` at `0x14000d3e5`
- `NETIO!HfAllocateHandle32` at `0x14000d3e5`
- `fwpkclnt!FwpmFilterAdd0` at `0x14000d4f0`
- `fwpkclnt!FwpmFilterAdd0` at `0x14000d4f0`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14000d648`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14000d648`

## pseudocode

```c
__int64 __fastcall PcpAddFilter(
        __int64 a1,
        _OWORD *a2,
        unsigned __int16 a3,
        UINT64 a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7)
{
  int v7; // r12d
  int v9; // r13d
  int v11; // ecx
  FWPM_FILTER_CONDITION0 *v12; // r15
  char *Pool2; // rdi
  int Handle32; // ebx
  GUID v15; // xmm0
  union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6 v16; // xmm1
  __int64 v17; // rbx
  KSPIN_LOCK *v18; // r12
  KIRQL v19; // r13
  __int64 v20; // rax
  UUID v21; // xmm0
  __int64 v22; // xmm1_8
  _OWORD *v23; // rax
  __int128 v24; // xmm0
  _OWORD *v25; // rax
  _QWORD *v26; // rcx
  NTSTATUS v27; // eax
  int v29; // [rsp+30h] [rbp-D0h]
  UINT32 v30; // [rsp+34h] [rbp-CCh] BYREF
  FWPM_FILTER_CONDITION0 *v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h]
  _OWORD *v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  _QWORD *v35; // [rsp+58h] [rbp-A8h]
  _DWORD *v36; // [rsp+60h] [rbp-A0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-98h] BYREF
  FWPM_FILTER0 filter; // [rsp+80h] [rbp-80h] BYREF
  UUID Uuid; // [rsp+150h] [rbp+50h] BYREF

  v7 = a1;
  v32 = a1;
  v9 = (int)a2;
  v34 = a5;
  v35 = a6;
  v33 = a2;
  v36 = a7;
  memset(&filter, 0, sizeof(filter));
  v30 = 0;
  v11 = 0;
  v12 = 0;
  v29 = 0;
  Pool2 = 0;
  v31 = 0;
  Uuid = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( a3 != 2 && a3 != 23 )
  {
    Handle32 = -1073741811;
    goto LABEL_41;
  }
  Handle32 = PcpRegisterCallout();
  if ( Handle32 < 0 )
  {
    v11 = 0;
    goto LABEL_41;
  }
  Pool2 = (char *)ExAllocatePool2(64, 144, 1717991248);
  if ( !Pool2 )
  {
    Handle32 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids, 3221225626LL);
    }
    goto LABEL_38;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, &LockHandle);
  Handle32 = HfAllocateHandle32(*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement, Pool2, Pool2 + 40);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( Handle32 < 0 )
    goto LABEL_37;
  Handle32 = PcpCreateWfpFilterConditionList(a3, v7, v9, (unsigned int)&v30, (__int64)&v31);
  if ( Handle32 < 0 || (Handle32 = ExUuidCreate(&Uuid), Handle32 < 0) )
  {
    v12 = v31;
    goto LABEL_37;
  }
  memset(&filter, 0, sizeof(filter));
  v12 = v31;
  filter.displayData.name = L"QoS";
  filter.action.type = 24580;
  filter.rawContext = a4;
  filter.numFilterConditions = v30;
  filter.filterCondition = v31;
  filter.filterKey = Uuid;
  filter.subLayerKey = FWPM_SUBLAYER_INSPECTION;
  if ( a3 == 2 )
  {
    v15 = FWPM_LAYER_OUTBOUND_TRANSPORT_V4;
    v16 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)PcgWfpCalloutGuid;
  }
  else
  {
    v15 = FWPM_LAYER_OUTBOUND_TRANSPORT_V6;
    v16 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)PcgWfpV6CalloutGuid;
  }
  filter.action.4 = v16;
  filter.layerKey = v15;
  if ( !PcpReferenceFlow(a4) )
  {
    Handle32 = -1073741275;
    goto LABEL_37;
  }
  Handle32 = FwpmFilterAdd0(PcgWfpEngineHandle, &filter, 0, 0);
  if ( Handle32 )
  {
    PcpDereferenceFlow(a4);
  }
  else
  {
    v17 = v34;
    v18 = (KSPIN_LOCK *)(v34 + 32);
    v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v34 + 32));
    if ( *(_BYTE *)(v17 + 52) == 1 || (Handle32 = PcpFindFlow((_QWORD *)a4, v17), Handle32 == -1073741275) )
    {
      KeReleaseSpinLock(v18, v19);
      v27 = FwpmFilterDeleteByKey0(PcgWfpEngineHandle, &Uuid);
      if ( v27 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids,
          (unsigned int)v27);
      }
      Handle32 = -1073741738;
      goto LABEL_37;
    }
    v20 = v32;
    *((_QWORD *)Pool2 + 4) = a4;
    v21 = Uuid;
    *((_WORD *)Pool2 + 22) = a3;
    *((UUID *)Pool2 + 1) = v21;
    *((_OWORD *)Pool2 + 3) = *(_OWORD *)v20;
    if ( a3 == 2 )
    {
      v22 = *(_QWORD *)(v20 + 16);
      v23 = v33;
      *((_QWORD *)Pool2 + 8) = v22;
      *(_OWORD *)(Pool2 + 72) = *v23;
      *((_QWORD *)Pool2 + 11) = *((_QWORD *)v23 + 2);
    }
    else
    {
      *((_OWORD *)Pool2 + 4) = *(_OWORD *)(v20 + 16);
      v24 = *(_OWORD *)(v20 + 32);
      v25 = v33;
      *((_OWORD *)Pool2 + 5) = v24;
      *((_OWORD *)Pool2 + 6) = *v25;
      *((_OWORD *)Pool2 + 7) = v25[1];
      *((_OWORD *)Pool2 + 8) = v25[2];
    }
    v29 = *((_DWORD *)Pool2 + 10);
    RtlAcquireWriteLockAtDpcLevel(a4 + 96, &LockHandle);
    v26 = *(_QWORD **)(a4 + 576);
    if ( *v26 != a4 + 568 )
      __fastfail(3u);
    *((_QWORD *)Pool2 + 1) = v26;
    *(_QWORD *)Pool2 = a4 + 568;
    *v26 = Pool2;
    *(_QWORD *)(a4 + 576) = Pool2;
    ++*(_DWORD *)(a4 + 584);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    KeReleaseSpinLock(v18, v19);
  }
  if ( Handle32 < 0 )
  {
LABEL_37:
    PcpFreeFilter(Pool2);
    Pool2 = 0;
  }
LABEL_38:
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  v11 = v29;
LABEL_41:
  if ( v35 )
    *v35 = Pool2;
  if ( v36 )
    *v36 = v11;
  return (unsigned int)Handle32;
}

```

## disassembly

```asm
0x14000d284  push    rbp
0x14000d286  push    rbx
0x14000d287  push    rsi
0x14000d288  push    rdi
0x14000d289  push    r12
0x14000d28b  push    r13
0x14000d28d  push    r14
0x14000d28f  push    r15
0x14000d291  lea     rbp, [rsp-78h]
0x14000d296  sub     rsp, 178h
0x14000d29d  mov     rax, cs:__security_cookie
0x14000d2a4  xor     rax, rsp
0x14000d2a7  mov     [rbp+0B0h+var_50], rax
0x14000d2ab  mov     rax, [rbp+0B0h+arg_20]
0x14000d2b2  mov     r12, rcx
0x14000d2b5  mov     [rsp+1B0h+var_170], rcx
0x14000d2ba  movzx   r14d, r8w
0x14000d2be  mov     rcx, [rbp+0B0h+arg_28]
0x14000d2c5  mov     r13, rdx
0x14000d2c8  mov     [rsp+1B0h+var_160], rax
0x14000d2cd  mov     r8d, 0C8h; Size
0x14000d2d3  mov     rax, [rbp+0B0h+arg_30]
0x14000d2da  mov     rsi, r9
0x14000d2dd  mov     [rsp+1B0h+var_158], rcx
0x14000d2e2  lea     rcx, [rbp+0B0h+filter]; void *
0x14000d2e6  mov     [rsp+1B0h+var_168], rdx
0x14000d2eb  xor     edx, edx; Val
0x14000d2ed  mov     [rsp+1B0h+var_150], rax
0x14000d2f2  call    memset
0x14000d2f7  xor     eax, eax
0x14000d2f9  mov     [rsp+1B0h+var_17C], 0
0x14000d301  xor     ecx, ecx
0x14000d303  mov     qword ptr [rsp+1B0h+LockHandle.OldIrql], rax
0x14000d308  xor     r15d, r15d
0x14000d30b  mov     [rsp+1B0h+var_180], ecx
0x14000d30f  xor     edi, edi
0x14000d311  mov     [rsp+1B0h+var_178], r15
0x14000d316  xorps   xmm0, xmm0
0x14000d319  xorps   xmm1, xmm1
0x14000d31c  movups  xmmword ptr [rbp+0B0h+Uuid.Data1], xmm0
0x14000d320  movups  xmmword ptr [rsp+1B0h+LockHandle.LockQueue.Next], xmm1
0x14000d325  cmp     r14w, 2
0x14000d32a  jz      short loc_14000D33D
0x14000d32c  cmp     r14w, 17h
0x14000d331  jz      short loc_14000D33D
0x14000d333  mov     ebx, 0C000000Dh
0x14000d338  jmp     loc_14000D6C2
0x14000d33d  call    PcpRegisterCallout
0x14000d342  mov     ebx, eax
0x14000d344  test    eax, eax
0x14000d346  js      loc_14000D6FE
0x14000d34c  mov     edx, 90h
0x14000d351  mov     r8d, 66667750h
0x14000d357  lea     ecx, [rdx-50h]
0x14000d35a  call    cs:__imp_ExAllocatePool2
0x14000d361  nop     dword ptr [rax+rax+00h]
0x14000d366  mov     rdi, rax
0x14000d369  test    rax, rax
0x14000d36c  jnz     short loc_14000D3BF
0x14000d36e  mov     ebx, 0C000009Ah
0x14000d373  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d37a  lea     rax, WPP_GLOBAL_Control
0x14000d381  cmp     rcx, rax
0x14000d384  jz      loc_14000D6A8
0x14000d38a  cmp     byte ptr [rcx+29h], 2
0x14000d38e  jb      loc_14000D6A8
0x14000d394  test    dword ptr [rcx+2Ch], 800h
0x14000d39b  jz      loc_14000D6A8
0x14000d3a1  mov     rcx, [rcx+18h]
0x14000d3a5  lea     edx, [rdi+0Bh]
0x14000d3a8  mov     r9d, 0C000009Ah
0x14000d3ae  lea     r8, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids
0x14000d3b5  call    WPP_SF_D
0x14000d3ba  jmp     loc_14000D6A8
0x14000d3bf  lea     rdx, [rsp+1B0h+LockHandle]; LockHandle
0x14000d3c4  lea     rcx, WPP_MAIN_CB.Queue+40h; SpinLock
0x14000d3cb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000d3d2  nop     dword ptr [rax+rax+00h]
0x14000d3d7  mov     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x14000d3de  lea     r8, [rdi+28h]
0x14000d3e2  mov     rdx, rdi
0x14000d3e5  call    cs:__imp_HfAllocateHandle32
0x14000d3ec  nop     dword ptr [rax+rax+00h]
0x14000d3f1  lea     rcx, [rsp+1B0h+LockHandle]; LockHandle
0x14000d3f6  mov     ebx, eax
0x14000d3f8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000d3ff  nop     dword ptr [rax+rax+00h]
0x14000d404  test    ebx, ebx
0x14000d406  js      loc_14000D69E
0x14000d40c  lea     rax, [rsp+1B0h+var_178]
0x14000d411  mov     r8, r13
0x14000d414  lea     r9, [rsp+1B0h+var_17C]
0x14000d419  mov     [rsp+1B0h+var_190], rax
0x14000d41e  mov     rdx, r12
0x14000d421  movzx   ecx, r14w
0x14000d425  call    PcpCreateWfpFilterConditionList
0x14000d42a  mov     ebx, eax
0x14000d42c  test    eax, eax
0x14000d42e  js      loc_14000D699
0x14000d434  lea     rcx, [rbp+0B0h+Uuid]; Uuid
0x14000d438  call    cs:__imp_ExUuidCreate
0x14000d43f  nop     dword ptr [rax+rax+00h]
0x14000d444  mov     ebx, eax
0x14000d446  test    eax, eax
0x14000d448  js      loc_14000D699
0x14000d44e  xor     edx, edx; Val
0x14000d450  lea     rcx, [rbp+0B0h+filter]; void *
0x14000d454  mov     r8d, 0C8h; Size
0x14000d45a  call    memset
0x14000d45f  mov     r15, [rsp+1B0h+var_178]
0x14000d464  lea     rax, aQos; "QoS"
0x14000d46b  mov     [rbp+0B0h+filter.displayData.name], rax
0x14000d46f  mov     eax, [rsp+1B0h+var_17C]
0x14000d473  mov     [rbp+0B0h+filter.action.type], 6004h
0x14000d47a  mov     qword ptr [rbp+0B0h+filter.98h], rsi
0x14000d47e  mov     [rbp+0B0h+filter.numFilterConditions], eax
0x14000d481  mov     [rbp+0B0h+filter.filterCondition], r15
0x14000d485  movups  xmm0, xmmword ptr [rbp+0B0h+Uuid.Data1]
0x14000d489  movdqu  xmmword ptr [rbp+0B0h+filter.filterKey.Data1], xmm0
0x14000d48e  movups  xmm0, xmmword ptr cs:FWPM_SUBLAYER_INSPECTION.Data1
0x14000d495  movdqu  xmmword ptr [rbp+0B0h+filter.subLayerKey.Data1], xmm0
0x14000d49a  cmp     r14w, 2
0x14000d49f  jnz     short loc_14000D4B1
0x14000d4a1  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_TRANSPORT_V4.Data1
0x14000d4a8  movups  xmm1, cs:PcgWfpCalloutGuid
0x14000d4af  jmp     short loc_14000D4BF
0x14000d4b1  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_TRANSPORT_V6.Data1
0x14000d4b8  movups  xmm1, cs:PcgWfpV6CalloutGuid
0x14000d4bf  mov     rcx, rsi
0x14000d4c2  movdqu  xmmword ptr [rbp+0B0h+filter.action.4], xmm1
0x14000d4c7  movdqu  xmmword ptr [rbp+0B0h+filter.layerKey.Data1], xmm0
0x14000d4cc  call    PcpReferenceFlow
0x14000d4d1  test    al, al
0x14000d4d3  jnz     short loc_14000D4DF
0x14000d4d5  mov     ebx, 0C0000225h
0x14000d4da  jmp     loc_14000D69E
0x14000d4df  mov     rcx, cs:PcgWfpEngineHandle; engineHandle
0x14000d4e6  lea     rdx, [rbp+0B0h+filter]; filter
0x14000d4ea  xor     r9d, r9d; id
0x14000d4ed  xor     r8d, r8d; sd
0x14000d4f0  call    cs:__imp_FwpmFilterAdd0
0x14000d4f7  nop     dword ptr [rax+rax+00h]
0x14000d4fc  mov     ebx, eax
0x14000d4fe  test    eax, eax
0x14000d500  jz      short loc_14000D50F
0x14000d502  mov     rcx, rsi
0x14000d505  call    PcpDereferenceFlow
0x14000d50a  jmp     loc_14000D625
0x14000d50f  mov     rbx, [rsp+1B0h+var_160]
0x14000d514  lea     r12, [rbx+20h]
0x14000d518  mov     rcx, r12; SpinLock
0x14000d51b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d522  nop     dword ptr [rax+rax+00h]
0x14000d527  cmp     byte ptr [rbx+34h], 1
0x14000d52b  mov     r13b, al
0x14000d52e  jz      loc_14000D62B
0x14000d534  mov     rdx, rbx
0x14000d537  mov     rcx, rsi
0x14000d53a  call    PcpFindFlow
0x14000d53f  mov     ebx, eax
0x14000d541  cmp     eax, 0C0000225h
0x14000d546  jz      loc_14000D62B
0x14000d54c  mov     rax, [rsp+1B0h+var_170]
0x14000d551  mov     [rdi+20h], rsi
0x14000d555  movups  xmm0, xmmword ptr [rbp+0B0h+Uuid.Data1]
0x14000d559  mov     [rdi+2Ch], r14w
0x14000d55e  movdqu  xmmword ptr [rdi+10h], xmm0
0x14000d563  movups  xmm0, xmmword ptr [rax]
0x14000d566  movups  xmmword ptr [rdi+30h], xmm0
0x14000d56a  cmp     r14w, 2
0x14000d56f  jnz     short loc_14000D593
0x14000d571  movsd   xmm1, qword ptr [rax+10h]
0x14000d576  mov     rax, [rsp+1B0h+var_168]
0x14000d57b  movsd   qword ptr [rdi+40h], xmm1
0x14000d580  movups  xmm0, xmmword ptr [rax]
0x14000d583  movups  xmmword ptr [rdi+48h], xmm0
0x14000d587  movsd   xmm1, qword ptr [rax+10h]
0x14000d58c  movsd   qword ptr [rdi+58h], xmm1
0x14000d591  jmp     short loc_14000D5C2
0x14000d593  movups  xmm1, xmmword ptr [rax+10h]
0x14000d597  movups  xmmword ptr [rdi+40h], xmm1
0x14000d59b  movups  xmm0, xmmword ptr [rax+20h]
0x14000d59f  mov     rax, [rsp+1B0h+var_168]
0x14000d5a4  movups  xmmword ptr [rdi+50h], xmm0
0x14000d5a8  movups  xmm0, xmmword ptr [rax]
0x14000d5ab  movups  xmmword ptr [rdi+60h], xmm0
0x14000d5af  movups  xmm1, xmmword ptr [rax+10h]
0x14000d5b3  movups  xmmword ptr [rdi+70h], xmm1
0x14000d5b7  movups  xmm0, xmmword ptr [rax+20h]
0x14000d5bb  movups  xmmword ptr [rdi+80h], xmm0
0x14000d5c2  mov     eax, [rdi+28h]
0x14000d5c5  lea     rcx, [rsi+60h]
0x14000d5c9  lea     rdx, [rsp+1B0h+LockHandle]
0x14000d5ce  mov     [rsp+1B0h+var_180], eax
0x14000d5d2  call    RtlAcquireWriteLockAtDpcLevel
0x14000d5d7  lea     rax, [rsi+238h]
0x14000d5de  mov     rcx, [rax+8]
0x14000d5e2  cmp     [rcx], rax
0x14000d5e5  jz      short loc_14000D5EE
0x14000d5e7  mov     ecx, 3
0x14000d5ec  int     29h; Win8: RtlFailFast(ecx)
0x14000d5ee  mov     [rdi+8], rcx
0x14000d5f2  mov     [rdi], rax
0x14000d5f5  mov     [rcx], rdi
0x14000d5f8  lea     rcx, [rsp+1B0h+LockHandle]; LockHandle
0x14000d5fd  mov     [rax+8], rdi
0x14000d601  inc     dword ptr [rsi+248h]
0x14000d607  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000d60e  nop     dword ptr [rax+rax+00h]
0x14000d613  mov     dl, r13b; NewIrql
0x14000d616  mov     rcx, r12; SpinLock
0x14000d619  call    cs:__imp_KeReleaseSpinLock
0x14000d620  nop     dword ptr [rax+rax+00h]
0x14000d625  test    ebx, ebx
0x14000d627  jns     short loc_14000D6A8
0x14000d629  jmp     short loc_14000D69E
0x14000d62b  mov     dl, r13b; NewIrql
0x14000d62e  mov     rcx, r12; SpinLock
0x14000d631  call    cs:__imp_KeReleaseSpinLock
0x14000d638  nop     dword ptr [rax+rax+00h]
0x14000d63d  mov     rcx, cs:PcgWfpEngineHandle; engineHandle
0x14000d644  lea     rdx, [rbp+0B0h+Uuid]; key
0x14000d648  call    cs:__imp_FwpmFilterDeleteByKey0
0x14000d64f  nop     dword ptr [rax+rax+00h]
0x14000d654  mov     r9d, eax
0x14000d657  test    eax, eax
0x14000d659  jns     short loc_14000D692
0x14000d65b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d662  lea     rax, WPP_GLOBAL_Control
0x14000d669  cmp     rcx, rax
0x14000d66c  jz      short loc_14000D692
0x14000d66e  cmp     byte ptr [rcx+29h], 3
0x14000d672  jb      short loc_14000D692
0x14000d674  test    dword ptr [rcx+2Ch], 800h
0x14000d67b  jz      short loc_14000D692
0x14000d67d  mov     rcx, [rcx+18h]
0x14000d681  lea     r8, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids
0x14000d688  mov     edx, 0Ch
0x14000d68d  call    WPP_SF_D
0x14000d692  mov     ebx, 0C0000056h
0x14000d697  jmp     short loc_14000D69E
0x14000d699  mov     r15, [rsp+1B0h+var_178]
0x14000d69e  mov     rcx, rdi; P
0x14000d6a1  call    PcpFreeFilter
0x14000d6a6  xor     edi, edi
0x14000d6a8  test    r15, r15
0x14000d6ab  jz      short loc_14000D6BE
0x14000d6ad  xor     edx, edx; Tag
0x14000d6af  mov     rcx, r15; P
0x14000d6b2  call    cs:__imp_ExFreePoolWithTag
0x14000d6b9  nop     dword ptr [rax+rax+00h]
0x14000d6be  mov     ecx, [rsp+1B0h+var_180]
0x14000d6c2  mov     rax, [rsp+1B0h+var_158]
0x14000d6c7  test    rax, rax
0x14000d6ca  jz      short loc_14000D6CF
0x14000d6cc  mov     [rax], rdi
0x14000d6cf  mov     rax, [rsp+1B0h+var_150]
0x14000d6d4  test    rax, rax
0x14000d6d7  jz      short loc_14000D6DB
0x14000d6d9  mov     [rax], ecx
0x14000d6db  mov     eax, ebx
0x14000d6dd  mov     rcx, [rbp+0B0h+var_50]
0x14000d6e1  xor     rcx, rsp; StackCookie
0x14000d6e4  call    __security_check_cookie
0x14000d6e9  add     rsp, 178h
0x14000d6f0  pop     r15
0x14000d6f2  pop     r14
0x14000d6f4  pop     r13
0x14000d6f6  pop     r12
0x14000d6f8  pop     rdi
0x14000d6f9  pop     rsi
0x14000d6fa  pop     rbx
0x14000d6fb  pop     rbp
0x14000d6fc  retn
0x14000d6fe  mov     ecx, edi
0x14000d700  jmp     short loc_14000D6C2
```
