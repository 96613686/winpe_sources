# HsmiRecallPopulationCompletionCallback

- ea: `0x1400445f0`
- end: `0x1400446ec`
- name: `HsmiRecallPopulationCompletionCallback`
- size: `252`
- prototype: `void __fastcall(PVOID Entry, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001910`
- `0x140007ddc`
- `0x14001e2a0`
- `0x14004450c`
- `0x1400445f0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140044664`
- `ntoskrnl!KeSetEvent` at `0x140044664`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400446c0`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400446c0`

## pseudocode

```c
void __fastcall HsmiRecallPopulationCompletionCallback(PVOID Entry, int a2)
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
    goto LABEL_12;
  }
  v4->IoStatus.Status = a2;
  v4->IoStatus.Information = 0;
  KeSetEvent(*((PRKEVENT *)Entry + 9), 0, 0);
LABEL_12:
  HsmiRecallFreePopulationContext(Entry);
}

```

## disassembly

```asm
0x1400445f0  push    rbx
0x1400445f2  push    rbp
0x1400445f3  push    rsi
0x1400445f4  push    rdi
0x1400445f5  sub     rsp, 48h
0x1400445f9  mov     r10, [rcx+38h]
0x1400445fd  mov     rbx, rcx
0x140044600  mov     rdi, [rcx+18h]
0x140044604  mov     r9, [r10+10h]
0x140044608  mov     rcx, [r9+10h]
0x14004460c  cmp     edx, 0C000CF16h
0x140044612  jnz     short loc_140044621
0x140044614  mov     rax, [rbx+30h]
0x140044618  test    rax, rax
0x14004461b  jz      short loc_140044621
0x14004461d  mov     byte ptr [rax+2Ch], 1
0x140044621  mov     rax, [rbx+50h]
0x140044625  test    rax, rax
0x140044628  jz      short loc_140044649
0x14004462a  mov     r8, [rdi+10h]
0x14004462e  mov     r9, [r9+20h]
0x140044632  mov     [rsp+68h+var_40], edx
0x140044636  mov     rdx, r10
0x140044639  mov     [rsp+68h+var_48], rdi
0x14004463e  mov     r8, [r8+8]
0x140044642  call    _guard_dispatch_icall
0x140044647  mov     edx, eax
0x140044649  cmp     qword ptr [rbx+48h], 0
0x14004464e  jz      short loc_140044672
0x140044650  mov     [rdi+18h], edx
0x140044653  xor     r8d, r8d; Wait
0x140044656  mov     qword ptr [rdi+20h], 0
0x14004465e  xor     edx, edx; Increment
0x140044660  mov     rcx, [rbx+48h]; Event
0x140044664  call    cs:__imp_KeSetEvent
0x14004466b  nop     dword ptr [rax+rax+00h]
0x140044670  jmp     short loc_1400446CC
0x140044672  mov     rax, [rdi+10h]
0x140044676  mov     esi, 4
0x14004467b  mov     r8b, [rax+4]
0x14004467f  lea     eax, [r8-0Ch]
0x140044683  neg     al
0x140044685  sbb     ecx, ecx
0x140044687  and     ecx, esi
0x140044689  test    edx, edx
0x14004468b  jns     short loc_1400446DE
0x14004468d  mov     [rdi+18h], edx
0x140044690  mov     qword ptr [rdi+20h], 0
0x140044698  mov     rcx, [rbx+38h]; Context
0x14004469c  xor     ebp, ebp
0x14004469e  call    HsmpReleaseUserRequestRundownProtection
0x1400446a3  mov     r9b, 1
0x1400446a6  mov     byte ptr [rsp+68h+var_48], 0
0x1400446ab  mov     r8, rbp
0x1400446ae  mov     rdx, rdi
0x1400446b1  mov     ecx, esi
0x1400446b3  call    HsmpTracePreCallbackExit
0x1400446b8  mov     r8, rbp; Context
0x1400446bb  mov     edx, esi; CallbackStatus
0x1400446bd  mov     rcx, rdi; CallbackData
0x1400446c0  call    cs:__imp_FltCompletePendedPreOperation
0x1400446c7  nop     dword ptr [rax+rax+00h]
0x1400446cc  mov     rcx, rbx; Entry
0x1400446cf  call    HsmiRecallFreePopulationContext
0x1400446d4  add     rsp, 48h
0x1400446d8  pop     rdi
0x1400446d9  pop     rsi
0x1400446da  pop     rbp
0x1400446db  pop     rbx
0x1400446dc  retn
0x1400446de  mov     esi, ecx
0x1400446e0  cmp     r8b, 0Ch
0x1400446e4  jnz     short loc_140044698
0x1400446e6  mov     rbp, [rbx+38h]
0x1400446ea  jmp     short loc_1400446A3
```
