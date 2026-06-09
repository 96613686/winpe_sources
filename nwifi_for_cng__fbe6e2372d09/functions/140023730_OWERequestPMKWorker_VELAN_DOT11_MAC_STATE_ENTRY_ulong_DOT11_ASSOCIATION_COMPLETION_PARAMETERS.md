# OWERequestPMKWorker(_VELAN *,DOT11_MAC_STATE_ENTRY *,ulong,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)

- ea: `0x140023730`
- end: `0x14002384d`
- name: `?OWERequestPMKWorker@@YAXPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@KPEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@@Z`
- size: `285`
- prototype: `void __fastcall(struct _VELAN *, struct DOT11_MAC_STATE_ENTRY *, unsigned int, struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140046610`

## callees

- `0x140023730`
- `0x1400239f8`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002379d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002379d`
- `ntoskrnl!ExAllocatePool2` at `0x1400237b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400237b5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002381d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002381d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023831`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023831`

## pseudocode

```c
void __fastcall OWERequestPMKWorker(
        struct _VELAN *a1,
        struct DOT11_MAC_STATE_ENTRY *a2,
        unsigned int a3,
        struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *a4)
{
  size_t v4; // rbp
  unsigned int v8; // esi
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  ULONG *v12; // rdi
  _QWORD *v13; // rbx

  v4 = a3;
  v8 = a3 + 8;
  v9 = a3 + 24;
  if ( a3 + 24 < 0x10 )
    return;
  if ( v9 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v9 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v9 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v9 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v9, 2053731191);
LABEL_12:
  v12 = (ULONG *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = p_DeviceQueue;
    v13 = Pool2 + 16;
    *((_DWORD *)Pool2 + 2) = 2053731191;
    memset(Pool2 + 16, 0, v8);
    *v13 = a2;
    memmove(v13 + 1, a4, v4);
    Dot11WorkerRequestHandler(a1, DOT11_WORKER_REQUEST_TYPE_OWE_CALCULATE_PMK, OWECalculatePMKCallbackFn, v8, v13);
    if ( *(_QWORD *)v12 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12, v12);
    else
      ExFreePoolWithTag(v12, v12[2]);
  }
}

```

## disassembly

```asm
0x140023730  push    rbx
0x140023732  push    rbp
0x140023733  push    rsi
0x140023734  push    rdi
0x140023735  push    r12
0x140023737  push    r14
0x140023739  push    r15
0x14002373b  sub     rsp, 30h
0x14002373f  mov     ebp, r8d
0x140023742  mov     r14, r9
0x140023745  mov     r15, rdx
0x140023748  mov     r12, rcx
0x14002374b  lea     esi, [rbp+8]
0x14002374e  lea     eax, [rsi+10h]
0x140023751  cmp     eax, 10h
0x140023754  jb      loc_14002383D
0x14002375a  mov     ecx, 40h ; '@'
0x14002375f  cmp     eax, ecx
0x140023761  ja      short loc_14002376C
0x140023763  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14002376a  jmp     short loc_14002379A
0x14002376c  cmp     eax, 100h
0x140023771  ja      short loc_14002377C
0x140023773  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14002377a  jmp     short loc_14002379A
0x14002377c  cmp     eax, 400h
0x140023781  ja      short loc_14002378C
0x140023783  lea     rbx, Lookaside
0x14002378a  jmp     short loc_14002379A
0x14002378c  cmp     eax, 800h
0x140023791  ja      short loc_1400237AB
0x140023793  lea     rbx, stru_1400B31C0
0x14002379a  mov     rcx, rbx; Lookaside
0x14002379d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400237a4  nop     dword ptr [rax+rax+00h]
0x1400237a9  jmp     short loc_1400237C1
0x1400237ab  xor     ebx, ebx
0x1400237ad  mov     edx, eax
0x1400237af  mov     r8d, 7A697377h
0x1400237b5  call    cs:__imp_ExAllocatePool2
0x1400237bc  nop     dword ptr [rax+rax+00h]
0x1400237c1  mov     rdi, rax
0x1400237c4  test    rax, rax
0x1400237c7  jz      short loc_14002383D
0x1400237c9  mov     [rax], rbx
0x1400237cc  xor     edx, edx; Val
0x1400237ce  lea     rbx, [rax+10h]
0x1400237d2  mov     r8d, esi; Size
0x1400237d5  mov     rcx, rbx; void *
0x1400237d8  mov     dword ptr [rax+8], 7A697377h
0x1400237df  call    memset
0x1400237e4  mov     r8, rbp; Size
0x1400237e7  mov     [rbx], r15
0x1400237ea  lea     rcx, [rbx+8]; void *
0x1400237ee  mov     rdx, r14; Src
0x1400237f1  call    memmove
0x1400237f6  mov     r9d, esi; Size
0x1400237f9  mov     [rsp+68h+var_48], rbx; void *
0x1400237fe  lea     r8, ?OWECalculatePMKCallbackFn@@YAXPEAU_VELAN@@PEAU_NWIFI_LOCK_STATE@@PEAX@Z; void (*)(struct _VELAN *, struct _NWIFI_LOCK_STATE *, void *)
0x140023805  mov     edx, 2; enum DOT11_WORKER_REQUEST_TYPE
0x14002380a  mov     rcx, r12; struct _VELAN *
0x14002380d  call    ?Dot11WorkerRequestHandler@@YAJPEAU_VELAN@@W4DOT11_WORKER_REQUEST_TYPE@@P6AX0PEAU_NWIFI_LOCK_STATE@@PEAX@ZK3@Z; Dot11WorkerRequestHandler(_VELAN *,DOT11_WORKER_REQUEST_TYPE,void (*)(_VELAN *,_NWIFI_LOCK_STATE *,void *),ulong,void *)
0x140023812  mov     rcx, [rdi]; Lookaside
0x140023815  test    rcx, rcx
0x140023818  jz      short loc_14002382B
0x14002381a  mov     rdx, rdi; Entry
0x14002381d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140023824  nop     dword ptr [rax+rax+00h]
0x140023829  jmp     short loc_14002383D
0x14002382b  mov     edx, [rdi+8]; Tag
0x14002382e  mov     rcx, rdi; P
0x140023831  call    cs:__imp_ExFreePoolWithTag
0x140023838  nop     dword ptr [rax+rax+00h]
0x14002383d  add     rsp, 30h
0x140023841  pop     r15
0x140023843  pop     r14
0x140023845  pop     r12
0x140023847  pop     rdi
0x140023848  pop     rsi
0x140023849  pop     rbp
0x14002384a  pop     rbx
0x14002384b  retn
```
