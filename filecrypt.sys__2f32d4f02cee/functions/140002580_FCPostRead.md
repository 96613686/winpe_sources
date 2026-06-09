# FCPostRead

- ea: `0x140002580`
- end: `0x14000278c`
- name: `FCPostRead`
- size: `524`
- prototype: `__int64 __fastcall(__int64, __int64, PFLT_CONTEXT *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400022a0`
- `0x140002580`
- `0x140002fd0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000271e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003f09`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000271e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003f09`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400025e6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400025e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000274b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000274b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f39`
- `ntoskrnl!ExAllocatePool2` at `0x14000264d`
- `ntoskrnl!ExAllocatePool2` at `0x14000264d`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140002732`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140003f1e`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140002732`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140003f1e`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000268b`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000268b`
- `FLTMGR!FltReleaseContext` at `0x1400026f7`
- `FLTMGR!FltReleaseContext` at `0x140002708`
- `FLTMGR!FltReleaseContext` at `0x140003ee3`
- `FLTMGR!FltReleaseContext` at `0x140003ef3`
- `FLTMGR!FltReleaseContext` at `0x1400026f7`
- `FLTMGR!FltReleaseContext` at `0x140002708`
- `FLTMGR!FltReleaseContext` at `0x140003ee3`
- `FLTMGR!FltReleaseContext` at `0x140003ef3`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000261c`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000261c`

## pseudocode

```c
__int64 __fastcall FCPostRead(__int64 a1, __int64 a2, PFLT_CONTEXT *a3, char a4)
{
  char v6; // si
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // r15
  void *v8; // r14
  unsigned int v9; // r13d
  NTSTATUS v10; // ebx
  _QWORD *Context; // rax
  __int128 v13; // [rsp+48h] [rbp-50h] BYREF

  v6 = 1;
  GenericWorkItem = 0;
  v8 = 0;
  v13 = 0;
  v9 = 0;
  v10 = 0;
  if ( (a4 & 1) == 0 && *(int *)(a1 + 24) >= 0 && *(_QWORD *)(a1 + 32) )
  {
    if ( KeGetCurrentIrql() < 2u
      || *(_QWORD *)(a1 + 32) <= 0x20000u && (*(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL) || (*(_DWORD *)a1 & 8) != 0) )
    {
      *(_QWORD *)&v13 = a1;
      *((_QWORD *)&v13 + 1) = a3;
      FCDecryptWorker(0, *(PVOID *)(a2 + 24), &v13);
      v6 = 0;
      v10 = *(_DWORD *)(a1 + 24);
    }
    else
    {
      GenericWorkItem = FltAllocateGenericWorkItem();
      if ( GenericWorkItem && (Context = (_QWORD *)ExAllocatePool2(64, 16, 1667515206), (v8 = Context) != 0) )
      {
        *Context = a1;
        Context[1] = a3;
        v10 = FltQueueGenericWorkItem(
                GenericWorkItem,
                *(PVOID *)(a2 + 24),
                (PFLT_GENERIC_WORKITEM_ROUTINE)FCDecryptWorker,
                DelayedWorkQueue,
                Context);
        if ( v10 >= 0 )
        {
          v9 = 1;
          v6 = 0;
        }
      }
      else
      {
        v10 = -1073741670;
      }
    }
  }
  if ( v10 < 0 )
  {
    *(_DWORD *)(a1 + 24) = v10;
    *(_QWORD *)(a1 + 32) = 0;
  }
  if ( v6 )
  {
    FltReleaseContext(*a3);
    FltReleaseContext(a3[1]);
    ExFreeToNPagedLookasideList(&gPre2PostIoContextList, a3);
    if ( GenericWorkItem )
      FltFreeGenericWorkItem(GenericWorkItem);
    if ( v8 )
      ExFreePoolWithTag(v8, 0x63644346u);
    v9 = 0;
  }
  if ( v10 < 0 && (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
    McTemplateK0d_EtwWriteTransfer(
      (unsigned int)Microsoft_Windows_FileCryptEnableBits,
      &PostReadFailure,
      a3,
      (unsigned int)v10);
  return v9;
}

```

## disassembly

```asm
0x140002580  mov     rax, rsp
0x140002583  mov     [rax+18h], r8
0x140002587  mov     [rax+10h], rdx
0x14000258b  mov     [rax+8], rcx
0x14000258f  push    rbx
0x140002590  push    rsi
0x140002591  push    rdi
0x140002592  push    r12
0x140002594  push    r13
0x140002596  push    r14
0x140002598  push    r15
0x14000259a  sub     rsp, 60h
0x14000259e  mov     r12, r8
0x1400025a1  mov     rdi, rcx
0x1400025a4  mov     esi, 1
0x1400025a9  mov     [rax-68h], sil
0x1400025ad  xor     r15d, r15d
0x1400025b0  mov     [rax-60h], r15
0x1400025b4  xor     r14d, r14d
0x1400025b7  mov     [rax-58h], r14
0x1400025bb  xorps   xmm0, xmm0
0x1400025be  movups  xmmword ptr [rax-50h], xmm0
0x1400025c2  xor     r13d, r13d
0x1400025c5  xor     ebx, ebx
0x1400025c7  mov     [rax-64h], ebx
0x1400025ca  test    sil, r9b
0x1400025cd  jnz     loc_1400026DF
0x1400025d3  cmp     [rcx+18h], ebx
0x1400025d6  jl      loc_1400026DF
0x1400025dc  cmp     [rcx+20h], rbx
0x1400025e0  jz      loc_1400026DF
0x1400025e6  call    cs:__imp_KeGetCurrentIrql
0x1400025ed  nop     dword ptr [rax+rax+00h]
0x1400025f2  cmp     al, 2
0x1400025f4  jb      loc_1400026AE
0x1400025fa  cmp     qword ptr [rdi+20h], 20000h
0x140002602  ja      short loc_14000261C
0x140002604  mov     rax, [rdi+10h]
0x140002608  cmp     [rax+38h], rbx
0x14000260c  jnz     loc_1400026AE
0x140002612  mov     eax, [rdi]
0x140002614  test    al, 8
0x140002616  jnz     loc_1400026AE
0x14000261c  call    cs:__imp_FltAllocateGenericWorkItem
0x140002623  nop     dword ptr [rax+rax+00h]
0x140002628  mov     r15, rax
0x14000262b  mov     [rsp+98h+var_60], rax
0x140002630  test    rax, rax
0x140002633  jnz     short loc_14000263F
0x140002635  mov     ebx, 0C000009Ah
0x14000263a  jmp     loc_1400026DB
0x14000263f  mov     edx, 10h
0x140002644  lea     ecx, [rdx+30h]
0x140002647  mov     r8d, 63644346h
0x14000264d  call    cs:__imp_ExAllocatePool2
0x140002654  nop     dword ptr [rax+rax+00h]
0x140002659  mov     r14, rax
0x14000265c  mov     [rsp+98h+var_58], rax
0x140002661  test    rax, rax
0x140002664  jz      short loc_140002635
0x140002666  mov     [rax], rdi
0x140002669  mov     [rax+8], r12
0x14000266d  mov     [rsp+98h+Context], rax; Context
0x140002672  mov     r9d, esi; QueueType
0x140002675  lea     r8, FCDecryptWorker; WorkerRoutine
0x14000267c  mov     rdx, [rsp+98h+arg_8]
0x140002684  mov     rdx, [rdx+18h]; FltObject
0x140002688  mov     rcx, r15; FltWorkItem
0x14000268b  call    cs:__imp_FltQueueGenericWorkItem
0x140002692  nop     dword ptr [rax+rax+00h]
0x140002697  mov     ebx, eax
0x140002699  mov     [rsp+98h+var_64], eax
0x14000269d  test    eax, eax
0x14000269f  js      short loc_1400026DF
0x1400026a1  mov     r13d, esi
0x1400026a4  xor     sil, sil
0x1400026a7  mov     [rsp+98h+var_68], sil
0x1400026ac  jmp     short loc_1400026DF
0x1400026ae  mov     [rsp+98h+var_50], rdi
0x1400026b3  mov     [rsp+98h+var_48], r12
0x1400026b8  lea     r8, [rsp+98h+var_50]; Context
0x1400026bd  mov     rdx, [rsp+98h+arg_8]
0x1400026c5  mov     rdx, [rdx+18h]; FltObject
0x1400026c9  xor     ecx, ecx; FltWorkItem
0x1400026cb  call    FCDecryptWorker
0x1400026d0  xor     sil, sil
0x1400026d3  mov     [rsp+98h+var_68], sil
0x1400026d8  mov     ebx, [rdi+18h]
0x1400026db  mov     [rsp+98h+var_64], ebx
0x1400026df  test    ebx, ebx
0x1400026e1  jns     short loc_1400026EE
0x1400026e3  mov     [rdi+18h], ebx
0x1400026e6  mov     qword ptr [rdi+20h], 0
0x1400026ee  test    sil, sil
0x1400026f1  jz      short loc_14000275A
0x1400026f3  mov     rcx, [r12]; Context
0x1400026f7  call    cs:__imp_FltReleaseContext
0x1400026fe  nop     dword ptr [rax+rax+00h]
0x140002703  mov     rcx, [r12+8]; Context
0x140002708  call    cs:__imp_FltReleaseContext
0x14000270f  nop     dword ptr [rax+rax+00h]
0x140002714  mov     rdx, r12; Entry
0x140002717  lea     rcx, gPre2PostIoContextList; Lookaside
0x14000271e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002725  nop     dword ptr [rax+rax+00h]
0x14000272a  test    r15, r15
0x14000272d  jz      short loc_14000273E
0x14000272f  mov     rcx, r15; FltWorkItem
0x140002732  call    cs:__imp_FltFreeGenericWorkItem
0x140002739  nop     dword ptr [rax+rax+00h]
0x14000273e  test    r14, r14
0x140002741  jz      short loc_140002757
0x140002743  mov     edx, 63644346h; Tag
0x140002748  mov     rcx, r14; P
0x14000274b  call    cs:__imp_ExFreePoolWithTag
0x140002752  nop     dword ptr [rax+rax+00h]
0x140002757  xor     r13d, r13d
0x14000275a  test    ebx, ebx
0x14000275c  jns     short loc_140002778
0x14000275e  mov     ecx, cs:Microsoft_Windows_FileCryptEnableBits
0x140002764  test    cl, 2
0x140002767  jz      short loc_140002778
0x140002769  mov     r9d, ebx
0x14000276c  lea     rdx, PostReadFailure
0x140002773  call    McTemplateK0d_EtwWriteTransfer
0x140002778  mov     eax, r13d
0x14000277b  add     rsp, 60h
0x14000277f  pop     r15
0x140002781  pop     r14
0x140002783  pop     r13
0x140002785  pop     r12
0x140002787  pop     rdi
0x140002788  pop     rsi
0x140002789  pop     rbx
0x14000278a  retn
0x140003eb0  push    rbx
0x140003eb2  push    rbp
0x140003eb3  sub     rsp, 38h
0x140003eb7  mov     rbp, rdx
0x140003eba  mov     ecx, [rbp+34h]
0x140003ebd  test    ecx, ecx
0x140003ebf  jns     short loc_140003ED3
0x140003ec1  mov     rax, [rbp+0A0h]
0x140003ec8  mov     [rax+18h], ecx
0x140003ecb  mov     qword ptr [rax+20h], 0
0x140003ed3  cmp     byte ptr [rbp+30h], 0
0x140003ed7  jz      short loc_140003F46
0x140003ed9  mov     rbx, [rbp+0B0h]
0x140003ee0  mov     rcx, [rbx]; Context
0x140003ee3  call    cs:__imp_FltReleaseContext
0x140003eea  nop     dword ptr [rax+rax+00h]
0x140003eef  mov     rcx, [rbx+8]; Context
0x140003ef3  call    cs:__imp_FltReleaseContext
0x140003efa  nop     dword ptr [rax+rax+00h]
0x140003eff  mov     rdx, rbx; Entry
0x140003f02  lea     rcx, gPre2PostIoContextList; Lookaside
0x140003f09  call    cs:__imp_ExFreeToNPagedLookasideList
0x140003f10  nop     dword ptr [rax+rax+00h]
0x140003f15  mov     rcx, [rbp+38h]; FltWorkItem
0x140003f19  test    rcx, rcx
0x140003f1c  jz      short loc_140003F2B
0x140003f1e  call    cs:__imp_FltFreeGenericWorkItem
0x140003f25  nop     dword ptr [rax+rax+00h]
0x140003f2a  nop
0x140003f2b  mov     rcx, [rbp+40h]; P
0x140003f2f  test    rcx, rcx
0x140003f32  jz      short loc_140003F46
0x140003f34  mov     edx, 63644346h; Tag
0x140003f39  call    cs:__imp_ExFreePoolWithTag
0x140003f40  nop     dword ptr [rax+rax+00h]
0x140003f45  nop
0x140003f46  add     rsp, 38h
0x140003f4a  pop     rbp
0x140003f4b  pop     rbx
0x140003f4c  retn
```
