# SmbCeRemoveVcEndpointLite

- ea: `0x14004b4cc`
- end: `0x14004b792`
- name: `SmbCeRemoveVcEndpointLite`
- size: `710`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14002d3f0`
- `0x14003fbb0`
- `0x140044ae0`

## callees

- `0x140013540`
- `0x140014400`
- `0x140021130`
- `0x1400221e0`
- `0x140024220`
- `0x140025584`
- `0x1400383d0`
- `0x1400468c8`
- `0x1400481f0`
- `0x14004b4cc`

## import_xrefs

- `rdbss!RxDiagnosticTrace` at `0x14004b6dc`
- `rdbss!RxDiagnosticTrace` at `0x14004b73b`
- `rdbss!RxDiagnosticTrace` at `0x14004b6dc`
- `rdbss!RxDiagnosticTrace` at `0x14004b73b`
- `rdbss!RxDispatchToWorkerThread` at `0x14004b5c0`
- `rdbss!RxDispatchToWorkerThread` at `0x14004b627`
- `rdbss!RxDispatchToWorkerThread` at `0x14004b5c0`
- `rdbss!RxDispatchToWorkerThread` at `0x14004b627`

## string_xrefs

- `0x14004b6b3`: `Remove:Index %d TargetCount %d CurrentCount %d FailureCount %d`
- `0x14004b72c`: `Remove TDI connection endpoint %p`

## pseudocode

```c
_QWORD *__fastcall SmbCeRemoveVcEndpointLite(ULONG_PTR BugCheckParameter2, __int64 a2)
{
  __int64 v2; // rbx
  int v5; // edi
  unsigned int v6; // r12d
  unsigned int i; // r15d
  __int64 v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  struct _RDBSS_DEVICE_OBJECT *v12; // r13
  _QWORD *v13; // r12
  __int64 v14; // rax
  _QWORD *j; // rcx
  ULONG_PTR v16; // rdi
  __int64 v17; // rcx
  _QWORD *result; // rax
  __int64 v19; // rcx
  _QWORD *v20; // rdx

  v2 = *(_QWORD *)(BugCheckParameter2 + 576);
  if ( v2 )
  {
    v5 = *(_DWORD *)(a2 + 320);
    if ( v5 )
    {
      v6 = *(_DWORD *)(v2 + 8);
      for ( i = 0; i < v6; ++i )
      {
        v8 = 312LL * i;
        if ( ((*(_BYTE *)(v8 + v2 + 36) & 0x10) != 0) == (v5 == 2)
          && (unsigned __int8)SmbCeIsEqualAddressPair(v8 + v2 + 56, v8 + v2 + 200, a2 + 400, a2 + 428) )
        {
          v12 = *(struct _RDBSS_DEVICE_OBJECT **)(BugCheckParameter2 + 24);
          v13 = (_QWORD *)(BugCheckParameter2 + 528);
          --*(_DWORD *)(v8 + v2 + 24);
          if ( (_QWORD *)*v13 != v13 )
          {
            if ( v5 != 2
              || (v14 = *(_QWORD *)(a2 + 32), *(_DWORD *)(v14 + 56) == 1)
              && *(_BYTE *)(v14 + 69)
              && (_BYTE)word_14007D202
              && !*(_DWORD *)(BugCheckParameter2 + 784)
              && !MRxSmbIsRdmaRundownActive(v10, v9, v11) )
            {
              for ( j = (_QWORD *)*v13; ; j = *(_QWORD **)(v16 + 392) )
              {
                v16 = 0;
                if ( j != v13 )
                  v16 = (ULONG_PTR)(j - 49);
                if ( !v16 )
                  break;
                if ( !*(_DWORD *)(v16 + 12) && (unsigned __int8)SmbCeMultiChannelInitiated(v16) )
                {
                  SmbCeReferenceSessionEntry(v17);
                  if ( RxDispatchToWorkerThread(
                         v12,
                         NormalWorkQueue,
                         (PRX_WORKERTHREAD_ROUTINE)SmbCeEstablishMultipleConnections,
                         (PVOID)v16) )
                  {
                    SmbCeDereferenceSessionEntryEx(v16);
                  }
                  break;
                }
              }
            }
            else
            {
              SmbCeReferenceServerEntry(BugCheckParameter2);
              if ( RxDispatchToWorkerThread(
                     v12,
                     NormalWorkQueue,
                     (PRX_WORKERTHREAD_ROUTINE)SmbCeComputeConnectionInfo,
                     (PVOID)BugCheckParameter2) )
              {
                SmbCeDereferenceServerEntryEx(BugCheckParameter2);
              }
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qddddd(
                WPP_GLOBAL_Control->AttachedDevice,
                13,
                WPP_94e1a31e0cd6309a61e483fe0815e01e_Traceguids,
                BugCheckParameter2,
                i,
                (*(unsigned __int8 *)(v8 + v2 + 36) >> 4) & 1,
                *(_DWORD *)(v8 + v2 + 20),
                *(_DWORD *)(v8 + v2 + 24),
                *(_DWORD *)(v8 + v2 + 28));
            }
            RxDiagnosticTrace(
              *(_QWORD *)(BugCheckParameter2 + 16),
              1,
              "Remove:Index %d TargetCount %d CurrentCount %d FailureCount %d",
              i,
              *(_DWORD *)(v8 + v2 + 20),
              *(_DWORD *)(v8 + v2 + 24),
              *(_DWORD *)(v8 + v2 + 28));
          }
          break;
        }
      }
    }
    else
    {
      *(_BYTE *)(v2 + 5) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_94e1a31e0cd6309a61e483fe0815e01e_Traceguids, a2);
      }
      RxDiagnosticTrace(*(_QWORD *)(BugCheckParameter2 + 16), 1, "Remove TDI connection endpoint %p", (const void *)a2);
    }
  }
  result = (_QWORD *)(a2 + 536);
  v19 = *(_QWORD *)(a2 + 536);
  if ( *(_QWORD *)(v19 + 8) != a2 + 536 || (v20 = *(_QWORD **)(a2 + 544), (_QWORD *)*v20 != result) )
    __fastfail(3u);
  *v20 = v19;
  *(_QWORD *)(v19 + 8) = v20;
  *(_QWORD *)(a2 + 544) = a2 + 536;
  *result = result;
  *(_QWORD *)(a2 + 504) = 0;
  return result;
}

```

## disassembly

```asm
0x14004b4cc  push    rbx
0x14004b4ce  push    rbp
0x14004b4cf  push    rsi
0x14004b4d0  push    rdi
0x14004b4d1  push    r12
0x14004b4d3  push    r13
0x14004b4d5  push    r14
0x14004b4d7  push    r15
0x14004b4d9  sub     rsp, 58h
0x14004b4dd  mov     rbx, [rcx+240h]
0x14004b4e4  mov     rbp, rdx
0x14004b4e7  mov     rsi, rcx
0x14004b4ea  test    rbx, rbx
0x14004b4ed  jz      loc_14004B747
0x14004b4f3  mov     edi, [rdx+140h]
0x14004b4f9  test    edi, edi
0x14004b4fb  jz      loc_14004B6EA
0x14004b501  mov     r12d, [rbx+8]
0x14004b505  xor     r15d, r15d
0x14004b508  cmp     r15d, r12d
0x14004b50b  jnb     loc_14004B747
0x14004b511  mov     eax, r15d
0x14004b514  imul    r14, rax, 138h
0x14004b51b  cmp     edi, 2
0x14004b51e  setz    cl
0x14004b521  mov     al, [r14+rbx+24h]
0x14004b526  shr     al, 4
0x14004b529  and     al, 1
0x14004b52b  cmp     al, cl
0x14004b52d  jnz     short loc_14004B557
0x14004b52f  lea     rdx, [rbx+0C8h]
0x14004b536  lea     rcx, [rbx+38h]
0x14004b53a  add     rdx, r14
0x14004b53d  add     rcx, r14
0x14004b540  lea     r9, [rbp+1ACh]
0x14004b547  lea     r8, [rbp+190h]
0x14004b54e  call    SmbCeIsEqualAddressPair
0x14004b553  test    al, al
0x14004b555  jnz     short loc_14004B55C
0x14004b557  inc     r15d
0x14004b55a  jmp     short loc_14004B508
0x14004b55c  mov     r13, [rsi+18h]
0x14004b560  lea     r12, [rsi+210h]
0x14004b567  dec     dword ptr [r14+rbx+18h]
0x14004b56c  cmp     [r12], r12
0x14004b570  jz      loc_14004B747
0x14004b576  cmp     edi, 2
0x14004b579  jnz     short loc_14004B5DC
0x14004b57b  mov     rax, [rbp+20h]
0x14004b57f  cmp     dword ptr [rax+38h], 1
0x14004b583  jnz     short loc_14004B5A6
0x14004b585  cmp     byte ptr [rax+45h], 0
0x14004b589  jz      short loc_14004B5A6
0x14004b58b  cmp     byte ptr cs:word_14007D202, 0
0x14004b592  jz      short loc_14004B5A6
0x14004b594  cmp     dword ptr [rsi+310h], 0
0x14004b59b  jnz     short loc_14004B5A6
0x14004b59d  call    MRxSmbIsRdmaRundownActive
0x14004b5a2  test    al, al
0x14004b5a4  jz      short loc_14004B5DC
0x14004b5a6  mov     rcx, rsi; BugCheckParameter2
0x14004b5a9  call    SmbCeReferenceServerEntry
0x14004b5ae  mov     r9, rsi; pContext
0x14004b5b1  lea     r8, SmbCeComputeConnectionInfo; Routine
0x14004b5b8  mov     edx, 3; WorkQueueType
0x14004b5bd  mov     rcx, r13; pMRxDeviceObject
0x14004b5c0  call    cs:__imp_RxDispatchToWorkerThread
0x14004b5c7  nop     dword ptr [rax+rax+00h]
0x14004b5cc  test    eax, eax
0x14004b5ce  jz      short loc_14004B641
0x14004b5d0  xor     edx, edx
0x14004b5d2  mov     rcx, rsi; BugCheckParameter2
0x14004b5d5  call    SmbCeDereferenceServerEntryEx
0x14004b5da  jmp     short loc_14004B641
0x14004b5dc  mov     rcx, [r12]
0x14004b5e0  xor     edi, edi
0x14004b5e2  lea     rax, [rcx-188h]
0x14004b5e9  cmp     rcx, r12
0x14004b5ec  cmovnz  rdi, rax
0x14004b5f0  test    rdi, rdi
0x14004b5f3  jz      short loc_14004B641
0x14004b5f5  cmp     dword ptr [rdi+0Ch], 0
0x14004b5f9  jnz     short loc_14004B607
0x14004b5fb  mov     rcx, rdi
0x14004b5fe  call    SmbCeMultiChannelInitiated
0x14004b603  test    al, al
0x14004b605  jnz     short loc_14004B610
0x14004b607  mov     rcx, [rdi+188h]
0x14004b60e  jmp     short loc_14004B5E0
0x14004b610  call    SmbCeReferenceSessionEntry
0x14004b615  mov     r9, rdi; pContext
0x14004b618  lea     r8, SmbCeEstablishMultipleConnections; Routine
0x14004b61f  mov     edx, 3; WorkQueueType
0x14004b624  mov     rcx, r13; pMRxDeviceObject
0x14004b627  call    cs:__imp_RxDispatchToWorkerThread
0x14004b62e  nop     dword ptr [rax+rax+00h]
0x14004b633  test    eax, eax
0x14004b635  jz      short loc_14004B641
0x14004b637  mov     dl, 1
0x14004b639  mov     rcx, rdi; BugCheckParameter2
0x14004b63c  call    SmbCeDereferenceSessionEntryEx
0x14004b641  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004b648  lea     rax, WPP_GLOBAL_Control
0x14004b64f  cmp     rcx, rax
0x14004b652  jz      short loc_14004B6AE
0x14004b654  test    dword ptr [rcx+2Ch], 100h
0x14004b65b  jz      short loc_14004B6AE
0x14004b65d  cmp     byte ptr [rcx+29h], 2
0x14004b661  jb      short loc_14004B6AE
0x14004b663  movzx   r8d, byte ptr [r14+rbx+24h]
0x14004b669  mov     edx, 0Dh
0x14004b66e  mov     eax, [r14+rbx+1Ch]
0x14004b673  mov     r9, rsi
0x14004b676  mov     rcx, [rcx+18h]
0x14004b67a  mov     [rsp+98h+var_58], eax
0x14004b67e  mov     eax, [r14+rbx+18h]
0x14004b683  mov     [rsp+98h+var_60], eax
0x14004b687  mov     eax, [r14+rbx+14h]
0x14004b68c  shr     r8d, 4
0x14004b690  and     r8d, 1
0x14004b694  mov     [rsp+98h+var_68], eax
0x14004b698  mov     [rsp+98h+var_70], r8d
0x14004b69d  lea     r8, WPP_94e1a31e0cd6309a61e483fe0815e01e_Traceguids
0x14004b6a4  mov     [rsp+98h+var_78], r15d
0x14004b6a9  call    WPP_SF_qddddd
0x14004b6ae  mov     eax, [r14+rbx+1Ch]
0x14004b6b3  lea     r8, aRemoveIndexDTa; "Remove:Index %d TargetCount %d CurrentC"...
0x14004b6ba  mov     rcx, [rsi+10h]
0x14004b6be  mov     r9d, r15d
0x14004b6c1  mov     [rsp+98h+var_68], eax
0x14004b6c5  mov     edx, 1
0x14004b6ca  mov     eax, [r14+rbx+18h]
0x14004b6cf  mov     [rsp+98h+var_70], eax
0x14004b6d3  mov     eax, [r14+rbx+14h]
0x14004b6d8  mov     [rsp+98h+var_78], eax
0x14004b6dc  call    cs:__imp_RxDiagnosticTrace
0x14004b6e3  nop     dword ptr [rax+rax+00h]
0x14004b6e8  jmp     short loc_14004B747
0x14004b6ea  mov     byte ptr [rbx+5], 0
0x14004b6ee  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004b6f5  lea     rax, WPP_GLOBAL_Control
0x14004b6fc  cmp     rcx, rax
0x14004b6ff  jz      short loc_14004B728
0x14004b701  test    dword ptr [rcx+2Ch], 100h
0x14004b708  jz      short loc_14004B728
0x14004b70a  cmp     byte ptr [rcx+29h], 2
0x14004b70e  jb      short loc_14004B728
0x14004b710  mov     rcx, [rcx+18h]
0x14004b714  lea     r8, WPP_94e1a31e0cd6309a61e483fe0815e01e_Traceguids
0x14004b71b  mov     edx, 0Eh
0x14004b720  mov     r9, rbp
0x14004b723  call    WPP_SF_q
0x14004b728  mov     rcx, [rsi+10h]
0x14004b72c  lea     r8, aRemoveTdiConne; "Remove TDI connection endpoint %p"
0x14004b733  mov     r9, rbp
0x14004b736  mov     edx, 1
0x14004b73b  call    cs:__imp_RxDiagnosticTrace
0x14004b742  nop     dword ptr [rax+rax+00h]
0x14004b747  lea     rax, [rbp+218h]
0x14004b74e  mov     rcx, [rax]
0x14004b751  cmp     [rcx+8], rax
0x14004b755  jnz     short loc_14004B78B
0x14004b757  mov     rdx, [rax+8]
0x14004b75b  cmp     [rdx], rax
0x14004b75e  jnz     short loc_14004B78B
0x14004b760  mov     [rdx], rcx
0x14004b763  mov     [rcx+8], rdx
0x14004b767  mov     [rax+8], rax
0x14004b76b  mov     [rax], rax
0x14004b76e  mov     qword ptr [rbp+1F8h], 0
0x14004b779  add     rsp, 58h
0x14004b77d  pop     r15
0x14004b77f  pop     r14
0x14004b781  pop     r13
0x14004b783  pop     r12
0x14004b785  pop     rdi
0x14004b786  pop     rsi
0x14004b787  pop     rbp
0x14004b788  pop     rbx
0x14004b789  retn
0x14004b78b  mov     ecx, 3
0x14004b790  int     29h; Win8: RtlFailFast(ecx)
```
