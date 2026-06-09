# HsmpCompletePendedDehydrationRequests

- ea: `0x140056520`
- end: `0x140056648`
- name: `HsmpCompletePendedDehydrationRequests`
- size: `296`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140047b30`
- `0x140054910`
- `0x1400561cc`
- `0x14007b5ec`

## callees

- `0x140015c28`
- `0x140056520`
- `0x140056650`
- `0x140058cbc`
- `0x140075050`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140056573`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140056573`
- `ntoskrnl!ExReleaseResourceLite` at `0x140056567`
- `ntoskrnl!ExReleaseResourceLite` at `0x140056567`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400565fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400565fd`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400565e7`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400565e7`
- `FLTMGR!FltCbdqRemoveIo` at `0x1400565ae`
- `FLTMGR!FltCbdqRemoveIo` at `0x1400565ae`

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
0x140056520  push    rbx
0x140056522  push    rbp
0x140056523  push    rsi
0x140056524  push    rdi
0x140056525  push    r14
0x140056527  sub     rsp, 20h
0x14005652b  mov     rax, [rcx+10h]
0x14005652f  mov     ebp, r8d
0x140056532  mov     r14b, dl
0x140056535  mov     rdi, rcx
0x140056538  mov     rsi, [rax+10h]
0x14005653c  add     rsi, 0B8h
0x140056543  xor     edx, edx; Irql
0x140056545  mov     rcx, rsi; Cbdq
0x140056548  call    CldiStreamCdqACQUIRE
0x14005654d  mov     rax, [rdi+0A0h]
0x140056554  add     rax, 50h ; 'P'
0x140056558  mov     rbx, [rax]
0x14005655b  cmp     rbx, rax
0x14005655e  jnz     short loc_1400565A2
0x140056560  lea     rcx, [rsi+80h]; Resource
0x140056567  call    cs:__imp_ExReleaseResourceLite
0x14005656e  nop     dword ptr [rax+rax+00h]
0x140056573  call    cs:__imp_KeLeaveCriticalRegion
0x14005657a  nop     dword ptr [rax+rax+00h]
0x14005657f  test    r14b, r14b
0x140056582  jnz     loc_140056613
0x140056588  mov     rax, [rdi+0A0h]
0x14005658f  mov     dword ptr [rax+18h], 0
0x140056596  add     rsp, 20h
0x14005659a  pop     r14
0x14005659c  pop     rdi
0x14005659d  pop     rsi
0x14005659e  pop     rbp
0x14005659f  pop     rbx
0x1400565a0  retn
0x1400565a2  mov     rdx, [rbx+10h]; Context
0x1400565a6  test    rdx, rdx
0x1400565a9  jz      short loc_14005654D
0x1400565ab  mov     rcx, rsi; Cbdq
0x1400565ae  call    cs:__imp_FltCbdqRemoveIo
0x1400565b5  nop     dword ptr [rax+rax+00h]
0x1400565ba  xor     edx, edx; Irql
0x1400565bc  mov     rcx, rsi; Cbdq
0x1400565bf  call    CldiStreamCdqRELEASE
0x1400565c4  mov     rcx, [rbx+10h]; P
0x1400565c8  test    rcx, rcx
0x1400565cb  jnz     short loc_1400565F8
0x1400565cd  mov     edx, ebp
0x1400565cf  mov     [rbx-18h], ebp
0x1400565d2  not     edx
0x1400565d4  lea     rcx, [rbx-30h]; CallbackData
0x1400565d8  shr     rdx, 1Fh
0x1400565dc  xor     r8d, r8d; Context
0x1400565df  mov     [rbx-10h], rdx
0x1400565e3  lea     edx, [r8+4]; CallbackStatus
0x1400565e7  call    cs:__imp_FltCompletePendedPreOperation
0x1400565ee  nop     dword ptr [rax+rax+00h]
0x1400565f3  jmp     loc_140056543
0x1400565f8  mov     edx, 74436F49h; Tag
0x1400565fd  call    cs:__imp_ExFreePoolWithTag
0x140056604  nop     dword ptr [rax+rax+00h]
0x140056609  mov     qword ptr [rbx+10h], 0
0x140056611  jmp     short loc_1400565CD
0x140056613  mov     rax, [rdi+68h]
0x140056617  lea     r10, qword_1400294D0
0x14005661e  test    rax, rax
0x140056621  mov     rcx, rdi
0x140056624  cmovnz  r10, rax
0x140056628  call    HsmpGetStreamSize
0x14005662d  mov     rdx, [rdi+10h]
0x140056631  mov     r8, rax
0x140056634  mov     r9d, ebp
0x140056637  mov     rcx, r10
0x14005663a  mov     rdx, [rdx+20h]
0x14005663e  call    TlmWriteDehydrationCompleted
0x140056643  jmp     loc_140056588
```
