# HsmpCompletePendedDehydrationRequests

- ea: `0x140056640`
- end: `0x140056768`
- name: `HsmpCompletePendedDehydrationRequests`
- size: `296`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140047c20`
- `0x140054a30`
- `0x1400562ec`
- `0x14007b72c`

## callees

- `0x140015ca8`
- `0x140056640`
- `0x140056770`
- `0x140058ddc`
- `0x140075170`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140056693`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140056693`
- `ntoskrnl!ExReleaseResourceLite` at `0x140056687`
- `ntoskrnl!ExReleaseResourceLite` at `0x140056687`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005671d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005671d`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140056707`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140056707`
- `FLTMGR!FltCbdqRemoveIo` at `0x1400566ce`
- `FLTMGR!FltCbdqRemoveIo` at `0x1400566ce`

## pseudocode

```c
__int64 __fastcall HsmpCompletePendedDehydrationRequests(__int64 a1, char a2, unsigned int a3)
{
  __int64 v6; // rsi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  __int64 result; // rax
  IO_CSQ_IRP_CONTEXT *v10; // rdx
  void *v11; // rcx
  __int64 StreamSize; // rax
  __int64 v13; // r10

  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 184LL;
LABEL_2:
  CldiStreamCdqACQUIRE((PFLT_CALLBACK_DATA_QUEUE)v6, 0);
  while ( 1 )
  {
    v7 = (_QWORD *)(*(_QWORD *)(a1 + 160) + 80LL);
    v8 = (_QWORD *)*v7;
    if ( (_QWORD *)*v7 == v7 )
      break;
    v10 = (IO_CSQ_IRP_CONTEXT *)v8[2];
    if ( v10 )
    {
      FltCbdqRemoveIo((PFLT_CALLBACK_DATA_QUEUE)v6, v10);
      CldiStreamCdqRELEASE((PFLT_CALLBACK_DATA_QUEUE)v6, 0);
      v11 = (void *)v8[2];
      if ( v11 )
      {
        ExFreePoolWithTag(v11, 0x74436F49u);
        v8[2] = 0;
      }
      *((_DWORD *)v8 - 6) = a3;
      *(v8 - 2) = (unsigned __int64)~a3 >> 31;
      FltCompletePendedPreOperation((PFLT_CALLBACK_DATA)(v8 - 6), FLT_PREOP_COMPLETE, 0);
      goto LABEL_2;
    }
  }
  ExReleaseResourceLite((PERESOURCE)(v6 + 128));
  KeLeaveCriticalRegion();
  if ( a2 )
  {
    StreamSize = HsmpGetStreamSize(a1);
    TlmWriteDehydrationCompleted(v13, *(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL), StreamSize, a3);
  }
  result = *(_QWORD *)(a1 + 160);
  *(_DWORD *)(result + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x140056640  push    rbx
0x140056642  push    rbp
0x140056643  push    rsi
0x140056644  push    rdi
0x140056645  push    r14
0x140056647  sub     rsp, 20h
0x14005664b  mov     rax, [rcx+10h]
0x14005664f  mov     ebp, r8d
0x140056652  mov     r14b, dl
0x140056655  mov     rdi, rcx
0x140056658  mov     rsi, [rax+10h]
0x14005665c  add     rsi, 0B8h
0x140056663  xor     edx, edx; Irql
0x140056665  mov     rcx, rsi; Cbdq
0x140056668  call    CldiStreamCdqACQUIRE
0x14005666d  mov     rax, [rdi+0A0h]
0x140056674  add     rax, 50h ; 'P'
0x140056678  mov     rbx, [rax]
0x14005667b  cmp     rbx, rax
0x14005667e  jnz     short loc_1400566C2
0x140056680  lea     rcx, [rsi+80h]; Resource
0x140056687  call    cs:__imp_ExReleaseResourceLite
0x14005668e  nop     dword ptr [rax+rax+00h]
0x140056693  call    cs:__imp_KeLeaveCriticalRegion
0x14005669a  nop     dword ptr [rax+rax+00h]
0x14005669f  test    r14b, r14b
0x1400566a2  jnz     loc_140056733
0x1400566a8  mov     rax, [rdi+0A0h]
0x1400566af  mov     dword ptr [rax+18h], 0
0x1400566b6  add     rsp, 20h
0x1400566ba  pop     r14
0x1400566bc  pop     rdi
0x1400566bd  pop     rsi
0x1400566be  pop     rbp
0x1400566bf  pop     rbx
0x1400566c0  retn
0x1400566c2  mov     rdx, [rbx+10h]; Context
0x1400566c6  test    rdx, rdx
0x1400566c9  jz      short loc_14005666D
0x1400566cb  mov     rcx, rsi; Cbdq
0x1400566ce  call    cs:__imp_FltCbdqRemoveIo
0x1400566d5  nop     dword ptr [rax+rax+00h]
0x1400566da  xor     edx, edx; Irql
0x1400566dc  mov     rcx, rsi; Cbdq
0x1400566df  call    CldiStreamCdqRELEASE
0x1400566e4  mov     rcx, [rbx+10h]; P
0x1400566e8  test    rcx, rcx
0x1400566eb  jnz     short loc_140056718
0x1400566ed  mov     edx, ebp
0x1400566ef  mov     [rbx-18h], ebp
0x1400566f2  not     edx
0x1400566f4  lea     rcx, [rbx-30h]; CallbackData
0x1400566f8  shr     rdx, 1Fh
0x1400566fc  xor     r8d, r8d; Context
0x1400566ff  mov     [rbx-10h], rdx
0x140056703  lea     edx, [r8+4]; CallbackStatus
0x140056707  call    cs:__imp_FltCompletePendedPreOperation
0x14005670e  nop     dword ptr [rax+rax+00h]
0x140056713  jmp     loc_140056663
0x140056718  mov     edx, 74436F49h; Tag
0x14005671d  call    cs:__imp_ExFreePoolWithTag
0x140056724  nop     dword ptr [rax+rax+00h]
0x140056729  mov     qword ptr [rbx+10h], 0
0x140056731  jmp     short loc_1400566ED
0x140056733  mov     rax, [rdi+68h]
0x140056737  lea     r10, qword_1400294D0
0x14005673e  test    rax, rax
0x140056741  mov     rcx, rdi
0x140056744  cmovnz  r10, rax
0x140056748  call    HsmpGetStreamSize
0x14005674d  mov     rdx, [rdi+10h]
0x140056751  mov     r8, rax
0x140056754  mov     r9d, ebp
0x140056757  mov     rcx, r10
0x14005675a  mov     rdx, [rdx+20h]
0x14005675e  call    TlmWriteDehydrationCompleted
0x140056763  jmp     loc_1400566A8
```
