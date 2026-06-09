# HsmiRecallPopulationCompletionCallback

- ea: `0x140044500`
- end: `0x1400445fc`
- name: `HsmiRecallPopulationCompletionCallback`
- size: `252`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001910`
- `0x140007ddc`
- `0x14001e220`
- `0x14004441c`
- `0x140044500`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140044574`
- `ntoskrnl!KeSetEvent` at `0x140044574`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400445d0`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400445d0`

## pseudocode

```c
__int64 __fastcall HsmiRecallPopulationCompletionCallback(PVOID Entry, int a2)
{
  __int64 v2; // r10
  struct _FLT_CALLBACK_DATA *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(__int64, __int64, PFILE_OBJECT, _QWORD, struct _FLT_CALLBACK_DATA *, int); // rax
  FLT_PREOP_CALLBACK_STATUS v9; // esi
  UCHAR MajorFunction; // r8
  void *v11; // rbp

  v2 = *((_QWORD *)Entry + 7);
  v4 = (struct _FLT_CALLBACK_DATA *)*((_QWORD *)Entry + 3);
  v5 = *(_QWORD *)(v2 + 16);
  v6 = *(_QWORD *)(v5 + 16);
  if ( a2 == -1073688810 )
  {
    v7 = *((_QWORD *)Entry + 6);
    if ( v7 )
      *(_BYTE *)(v7 + 44) = 1;
  }
  v8 = (__int64 (__fastcall *)(__int64, __int64, PFILE_OBJECT, _QWORD, struct _FLT_CALLBACK_DATA *, int))*((_QWORD *)Entry + 10);
  if ( v8 )
    a2 = v8(v6, v2, v4->Iopb->TargetFileObject, *(_QWORD *)(v5 + 32), v4, a2);
  if ( !*((_QWORD *)Entry + 9) )
  {
    v9 = FLT_PREOP_COMPLETE;
    MajorFunction = v4->Iopb->MajorFunction;
    if ( a2 >= 0 )
    {
      v9 = MajorFunction != 12 ? FLT_PREOP_COMPLETE : FLT_PREOP_SUCCESS_WITH_CALLBACK;
      if ( MajorFunction == 12 )
      {
        v11 = (void *)*((_QWORD *)Entry + 7);
        goto LABEL_11;
      }
    }
    else
    {
      v4->IoStatus.Status = a2;
      v4->IoStatus.Information = 0;
    }
    v11 = 0;
    HsmpReleaseUserRequestRundownProtection(*((PFLT_CONTEXT *)Entry + 7));
LABEL_11:
    LOBYTE(v5) = 1;
    HsmpTracePreCallbackExit(v9, (_DWORD)v4, (_DWORD)v11, v5, 0);
    FltCompletePendedPreOperation(v4, v9, v11);
    return HsmiRecallFreePopulationContext(Entry);
  }
  v4->IoStatus.Status = a2;
  v4->IoStatus.Information = 0;
  KeSetEvent(*((PRKEVENT *)Entry + 9), 0, 0);
  return HsmiRecallFreePopulationContext(Entry);
}

```

## disassembly

```asm
0x140044500  push    rbx
0x140044502  push    rbp
0x140044503  push    rsi
0x140044504  push    rdi
0x140044505  sub     rsp, 48h
0x140044509  mov     r10, [rcx+38h]
0x14004450d  mov     rbx, rcx
0x140044510  mov     rdi, [rcx+18h]
0x140044514  mov     r9, [r10+10h]
0x140044518  mov     rcx, [r9+10h]
0x14004451c  cmp     edx, 0C000CF16h
0x140044522  jnz     short loc_140044531
0x140044524  mov     rax, [rbx+30h]
0x140044528  test    rax, rax
0x14004452b  jz      short loc_140044531
0x14004452d  mov     byte ptr [rax+2Ch], 1
0x140044531  mov     rax, [rbx+50h]
0x140044535  test    rax, rax
0x140044538  jz      short loc_140044559
0x14004453a  mov     r8, [rdi+10h]
0x14004453e  mov     r9, [r9+20h]
0x140044542  mov     [rsp+68h+var_40], edx
0x140044546  mov     rdx, r10
0x140044549  mov     [rsp+68h+var_48], rdi
0x14004454e  mov     r8, [r8+8]
0x140044552  call    _guard_dispatch_icall
0x140044557  mov     edx, eax
0x140044559  cmp     qword ptr [rbx+48h], 0
0x14004455e  jz      short loc_140044582
0x140044560  mov     [rdi+18h], edx
0x140044563  xor     r8d, r8d; Wait
0x140044566  mov     qword ptr [rdi+20h], 0
0x14004456e  xor     edx, edx; Increment
0x140044570  mov     rcx, [rbx+48h]; Event
0x140044574  call    cs:__imp_KeSetEvent
0x14004457b  nop     dword ptr [rax+rax+00h]
0x140044580  jmp     short loc_1400445DC
0x140044582  mov     rax, [rdi+10h]
0x140044586  mov     esi, 4
0x14004458b  mov     r8b, [rax+4]
0x14004458f  lea     eax, [r8-0Ch]
0x140044593  neg     al
0x140044595  sbb     ecx, ecx
0x140044597  and     ecx, esi
0x140044599  test    edx, edx
0x14004459b  jns     short loc_1400445EE
0x14004459d  mov     [rdi+18h], edx
0x1400445a0  mov     qword ptr [rdi+20h], 0
0x1400445a8  mov     rcx, [rbx+38h]; Context
0x1400445ac  xor     ebp, ebp
0x1400445ae  call    HsmpReleaseUserRequestRundownProtection
0x1400445b3  mov     r9b, 1
0x1400445b6  mov     byte ptr [rsp+68h+var_48], 0
0x1400445bb  mov     r8, rbp
0x1400445be  mov     rdx, rdi
0x1400445c1  mov     ecx, esi
0x1400445c3  call    HsmpTracePreCallbackExit
0x1400445c8  mov     r8, rbp; Context
0x1400445cb  mov     edx, esi; CallbackStatus
0x1400445cd  mov     rcx, rdi; CallbackData
0x1400445d0  call    cs:__imp_FltCompletePendedPreOperation
0x1400445d7  nop     dword ptr [rax+rax+00h]
0x1400445dc  mov     rcx, rbx; Entry
0x1400445df  call    HsmiRecallFreePopulationContext
0x1400445e4  add     rsp, 48h
0x1400445e8  pop     rdi
0x1400445e9  pop     rsi
0x1400445ea  pop     rbp
0x1400445eb  pop     rbx
0x1400445ec  retn
0x1400445ee  mov     esi, ecx
0x1400445f0  cmp     r8b, 0Ch
0x1400445f4  jnz     short loc_1400445A8
0x1400445f6  mov     rbp, [rbx+38h]
0x1400445fa  jmp     short loc_1400445B3
```
