# SmbCeProbeServerTransportInfo

- ea: `0x140023cc0`
- end: `0x140023db9`
- name: `SmbCeProbeServerTransportInfo`
- size: `249`
- prototype: `__int64 __fastcall(PRDBSS_DEVICE_OBJECT pMRxDeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001f0e0`

## callees

- `0x1400097e0`
- `0x140018680`
- `0x140023cc0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140023d27`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140023d27`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140023cdc`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140023cdc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023ceb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023ceb`
- `rdbss!RxDispatchToWorkerThread` at `0x14005f0f9`
- `rdbss!RxDispatchToWorkerThread` at `0x14005f0f9`

## pseudocode

```c
__int64 __fastcall SmbCeProbeServerTransportInfo(PRDBSS_DEVICE_OBJECT pMRxDeviceObject)
{
  unsigned int v2; // esi
  KIRQL v3; // bp
  struct _RDBSS_DEVICE_OBJECT *DpcData; // r14
  PFCB *p_CurrentFcbForClosePendingProcessing; // r14
  int v7; // eax
  struct _RDBSS_DEVICE_OBJECT *v8; // rdx
  char *v9; // rax
  char *v10; // rdx
  ULONG_PTR v11; // r13
  int v12; // eax
  char *i; // rcx
  char *v14; // rcx
  char *v15; // [rsp+50h] [rbp+8h]

  v2 = 0;
  v3 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)&pMRxDeviceObject[1].SecurityDescriptor);
  LODWORD(pMRxDeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Flink) = (unsigned int)PsGetCurrentThreadId();
  DpcData = (struct _RDBSS_DEVICE_OBJECT *)pMRxDeviceObject[1].DeviceObject.Dpc.DpcData;
  if ( DpcData != (struct _RDBSS_DEVICE_OBJECT *)&pMRxDeviceObject[1].Dpc.DpcData )
  {
    p_CurrentFcbForClosePendingProcessing = &DpcData[-1].RdbssScavengerInDeviceObject.CurrentFcbForClosePendingProcessing;
    while ( p_CurrentFcbForClosePendingProcessing )
    {
      if ( !byte_14007D16A )
      {
        v7 = *((_DWORD *)p_CurrentFcbForClosePendingProcessing + 179);
        if ( (v7 & 0x1000) != 0 && (v7 & 0x80u) == 0 )
        {
          v9 = (char *)p_CurrentFcbForClosePendingProcessing[66];
          if ( v9 != (char *)(p_CurrentFcbForClosePendingProcessing + 66) )
          {
            v10 = v9 - 392;
            v15 = v9 - 392;
            if ( v9 != (char *)392 )
            {
              v11 = 0;
              while ( !v11 )
              {
                if ( !*((_DWORD *)v10 + 3) )
                {
                  v12 = *((_DWORD *)v10 + 1);
                  if ( (v12 & 1) == 0 && (v12 & 2) == 0 )
                  {
                    for ( i = (char *)*((_QWORD *)v10 + 51); ; i = *(char **)(v11 + 384) )
                    {
                      v11 = 0;
                      if ( i != v10 + 408 )
                        v11 = (ULONG_PTR)(i - 384);
                      if ( !v11 )
                        break;
                      if ( !*(_DWORD *)(v11 + 12) )
                      {
                        SmbCeReferenceVNetRootContext(v11);
                        v10 = v15;
                        break;
                      }
                    }
                  }
                }
                v14 = (char *)*((_QWORD *)v10 + 49);
                v10 = 0;
                if ( v14 != (char *)(p_CurrentFcbForClosePendingProcessing + 66) )
                  v10 = v14 - 392;
                v15 = v10;
                if ( !v10 )
                {
                  if ( !v11 )
                    goto LABEL_6;
                  break;
                }
              }
              v2 = RxDispatchToWorkerThread(
                     pMRxDeviceObject,
                     NormalWorkQueue,
                     *(PRX_WORKERTHREAD_ROUTINE *)&p_CurrentFcbForClosePendingProcessing[7][1].FcbTableEntry.Lookups,
                     (PVOID)v11);
              if ( v2 )
                SmbCeDereferenceVNetRootContext(v11);
              _InterlockedIncrement((volatile signed __int32 *)p_CurrentFcbForClosePendingProcessing + 146);
            }
          }
        }
      }
LABEL_6:
      v8 = (struct _RDBSS_DEVICE_OBJECT *)p_CurrentFcbForClosePendingProcessing[4];
      p_CurrentFcbForClosePendingProcessing = 0;
      if ( v8 != (struct _RDBSS_DEVICE_OBJECT *)&pMRxDeviceObject[1].Dpc.DpcData )
        p_CurrentFcbForClosePendingProcessing = &v8[-1].RdbssScavengerInDeviceObject.CurrentFcbForClosePendingProcessing;
    }
  }
  LODWORD(pMRxDeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Flink) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)&pMRxDeviceObject[1].SecurityDescriptor, v3);
  return v2;
}

```

## disassembly

```asm
0x140023cc0  mov     [rsp+arg_18], rbx
0x140023cc5  push    rbp
0x140023cc6  push    rsi
0x140023cc7  push    rdi
0x140023cc8  push    r14
0x140023cca  push    r15
0x140023ccc  sub     rsp, 20h
0x140023cd0  mov     rbx, rcx
0x140023cd3  xor     esi, esi
0x140023cd5  add     rcx, 780h; SpinLock
0x140023cdc  call    cs:__imp_ExAcquireSpinLockExclusive
0x140023ce3  nop     dword ptr [rax+rax+00h]
0x140023ce8  movzx   ebp, al
0x140023ceb  call    cs:__imp_PsGetCurrentThreadId
0x140023cf2  nop     dword ptr [rax+rax+00h]
0x140023cf7  lea     r15, [rbx+770h]
0x140023cfe  mov     [rbx+930h], eax
0x140023d04  mov     r14, [r15]
0x140023d07  cmp     r14, r15
0x140023d0a  jz      short loc_140023D12
0x140023d0c  add     r14, 0FFFFFFFFFFFFFFE0h
0x140023d10  jnz     short loc_140023D47
0x140023d12  movzx   edx, bpl; OldIrql
0x140023d16  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140023d20  lea     rcx, [rbx+780h]; SpinLock
0x140023d27  call    cs:__imp_ExReleaseSpinLockExclusive
0x140023d2e  nop     dword ptr [rax+rax+00h]
0x140023d33  mov     rbx, [rsp+48h+arg_18]
0x140023d38  mov     eax, esi
0x140023d3a  add     rsp, 20h
0x140023d3e  pop     r15
0x140023d40  pop     r14
0x140023d42  pop     rdi
0x140023d43  pop     rsi
0x140023d44  pop     rbp
0x140023d45  retn
0x140023d47  mov     [rsp+48h+arg_8], r12
0x140023d4c  mov     [rsp+48h+arg_10], r13
0x140023d51  cmp     cs:byte_14007D16A, 0
0x140023d58  jnz     short loc_140023D67
0x140023d5a  mov     eax, [r14+2CCh]
0x140023d61  bt      eax, 0Ch
0x140023d65  jb      short loc_140023DB3
0x140023d67  mov     rdx, [r14+20h]
0x140023d6b  xor     r14d, r14d
0x140023d6e  cmp     rdx, r15
0x140023d71  lea     rax, [rdx-20h]
0x140023d75  cmovnz  r14, rax
0x140023d79  test    r14, r14
0x140023d7c  jnz     short loc_140023D51
0x140023d7e  mov     r13, [rsp+48h+arg_10]
0x140023d83  mov     r12, [rsp+48h+arg_8]
0x140023d88  jmp     short loc_140023D12
0x140023d8a  lea     r12, [r14+210h]
0x140023d91  mov     rax, [r12]
0x140023d95  cmp     rax, r12
0x140023d98  jz      short loc_140023D67
0x140023d9a  lea     rdx, [rax-188h]
0x140023da1  mov     [rsp+48h+arg_0], rdx
0x140023da6  test    rdx, rdx
0x140023da9  jz      short loc_140023D67
0x140023dab  xor     r13d, r13d
0x140023dae  jmp     loc_14005F066
0x140023db3  test    al, al
0x140023db5  js      short loc_140023D67
0x140023db7  jmp     short loc_140023D8A
0x14005f066  test    r13, r13
0x14005f069  jnz     short loc_14005F0E3
0x14005f06b  cmp     [rdx+0Ch], r13d
0x14005f06f  jnz     short loc_14005F0B9
0x14005f071  mov     eax, [rdx+4]
0x14005f074  test    al, 1
0x14005f076  jnz     short loc_14005F0B9
0x14005f078  test    al, 2
0x14005f07a  jnz     short loc_14005F0B9
0x14005f07c  lea     r8, [rdx+198h]
0x14005f083  mov     rcx, [r8]
0x14005f086  xor     r13d, r13d
0x14005f089  lea     rax, [rcx-180h]
0x14005f090  cmp     rcx, r8
0x14005f093  cmovnz  r13, rax
0x14005f097  test    r13, r13
0x14005f09a  jz      short loc_14005F0B9
0x14005f09c  cmp     dword ptr [r13+0Ch], 0
0x14005f0a1  jz      short loc_14005F0AC
0x14005f0a3  mov     rcx, [r13+180h]
0x14005f0aa  jmp     short loc_14005F086
0x14005f0ac  mov     rcx, r13
0x14005f0af  call    SmbCeReferenceVNetRootContext
0x14005f0b4  mov     rdx, [rsp+48h+arg_0]
0x14005f0b9  mov     rcx, [rdx+188h]
0x14005f0c0  xor     edx, edx
0x14005f0c2  cmp     rcx, r12
0x14005f0c5  lea     rax, [rcx-188h]
0x14005f0cc  cmovnz  rdx, rax
0x14005f0d0  mov     [rsp+48h+arg_0], rdx
0x14005f0d5  test    rdx, rdx
0x14005f0d8  jnz     short loc_14005F066
0x14005f0da  test    r13, r13
0x14005f0dd  jz      loc_140023D67
0x14005f0e3  mov     r8, [r14+38h]
0x14005f0e7  mov     r9, r13; pContext
0x14005f0ea  mov     edx, 3; WorkQueueType
0x14005f0ef  mov     rcx, rbx; pMRxDeviceObject
0x14005f0f2  mov     r8, [r8+398h]; Routine
0x14005f0f9  call    cs:__imp_RxDispatchToWorkerThread
0x14005f100  nop     dword ptr [rax+rax+00h]
0x14005f105  mov     esi, eax
0x14005f107  test    eax, eax
0x14005f109  jz      short loc_14005F113
0x14005f10b  mov     rcx, r13; BugCheckParameter2
0x14005f10e  call    SmbCeDereferenceVNetRootContext
0x14005f113  lock inc dword ptr [r14+248h]
0x14005f11b  jmp     loc_140023D67
```
