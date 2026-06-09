# FIVolumeQueueQuery

- ea: `0x140016494`
- end: `0x1400165ed`
- name: `FIVolumeQueueQuery`
- size: `345`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e5a0`
- `0x140012c54`
- `0x140013560`
- `0x1400138d4`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x140016494`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x140016547`
- `ntoskrnl!ObfReferenceObject` at `0x140016547`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1400164e4`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1400164e4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400165df`
- `ntoskrnl!ObfDereferenceObject` at `0x1400165df`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400165cb`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400165cb`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140016569`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140016569`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14001652c`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14001652c`

## pseudocode

```c
__int64 __fastcall FIVolumeQueueQuery(__int64 a1, __int64 a2)
{
  BOOL v4; // ebx
  int v5; // eax
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // r14
  void *Context; // rbp
  NTSTATUS v8; // ebx

  if ( dword_1400099F8 )
    return (unsigned int)-1073741079;
  FILockSharedAcquire(&qword_140009388);
  v4 = qword_140009390 == qword_140009398;
  FILockExclusiveRelease(&qword_140009388);
  if ( !v4 && !FsRtlAreVolumeStartupApplicationsComplete() )
    return (unsigned int)-1073741267;
  FILockExclusiveAcquire(a2 + 24);
  if ( *(WCHAR **)(a2 + 104) != FIUnknown || (v5 = *(_DWORD *)(a2 + 132), (v5 & 2) != 0) )
  {
    FILockExclusiveRelease(a2 + 24);
    return 0;
  }
  *(_DWORD *)(a2 + 132) = v5 | 2;
  FILockExclusiveRelease(a2 + 24);
  GenericWorkItem = FltAllocateGenericWorkItem();
  if ( GenericWorkItem )
  {
    Context = *(void **)(a1 + 16);
    ObfReferenceObject(Context);
    v8 = FltQueueGenericWorkItem(GenericWorkItem, *(PVOID *)(a1 + 8), FIVolumeQueryWorker, CriticalWorkQueue, Context);
    if ( v8 < 0 )
      goto LABEL_15;
    return 0;
  }
  Context = 0;
  v8 = -1073741670;
LABEL_15:
  FILockExclusiveAcquire(a2 + 24);
  *(_DWORD *)(a2 + 132) &= ~2u;
  FILockExclusiveRelease(a2 + 24);
  if ( GenericWorkItem )
    FltFreeGenericWorkItem(GenericWorkItem);
  if ( Context )
    ObfDereferenceObject(Context);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140016494  push    rbx
0x140016496  push    rbp
0x140016497  push    rsi
0x140016498  push    rdi
0x140016499  push    r14
0x14001649b  push    r15
0x14001649d  sub     rsp, 38h
0x1400164a1  mov     eax, cs:dword_1400099F8
0x1400164a7  mov     rdi, rdx
0x1400164aa  mov     r15, rcx
0x1400164ad  test    eax, eax
0x1400164af  jnz     loc_140016597
0x1400164b5  lea     rcx, qword_140009388
0x1400164bc  call    FILockSharedAcquire
0x1400164c1  mov     rax, cs:qword_140009398
0x1400164c8  lea     rcx, qword_140009388
0x1400164cf  xor     ebx, ebx
0x1400164d1  cmp     cs:qword_140009390, rax
0x1400164d8  setz    bl
0x1400164db  call    FILockExclusiveRelease
0x1400164e0  test    ebx, ebx
0x1400164e2  jnz     short loc_1400164F8
0x1400164e4  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x1400164eb  nop     dword ptr [rax+rax+00h]
0x1400164f0  test    al, al
0x1400164f2  jz      loc_14001659E
0x1400164f8  lea     rsi, [rdi+18h]
0x1400164fc  mov     rcx, rsi
0x1400164ff  call    FILockExclusiveAcquire
0x140016504  lea     rax, FIUnknown; "\\FI_UNKNOWN"
0x14001650b  cmp     [rdi+68h], rax
0x14001650f  jnz     short loc_14001657D
0x140016511  mov     eax, [rdi+84h]
0x140016517  test    al, 2
0x140016519  jnz     short loc_14001657D
0x14001651b  or      eax, 2
0x14001651e  mov     rcx, rsi
0x140016521  mov     [rdi+84h], eax
0x140016527  call    FILockExclusiveRelease
0x14001652c  call    cs:__imp_FltAllocateGenericWorkItem
0x140016533  nop     dword ptr [rax+rax+00h]
0x140016538  mov     r14, rax
0x14001653b  test    rax, rax
0x14001653e  jz      short loc_1400165A5
0x140016540  mov     rbp, [r15+10h]
0x140016544  mov     rcx, rbp; Object
0x140016547  call    cs:__imp_ObfReferenceObject
0x14001654e  nop     dword ptr [rax+rax+00h]
0x140016553  mov     rdx, [r15+8]; FltObject
0x140016557  lea     r8, FIVolumeQueryWorker; WorkerRoutine
0x14001655e  xor     r9d, r9d; QueueType
0x140016561  mov     [rsp+68h+Context], rbp; Context
0x140016566  mov     rcx, r14; FltWorkItem
0x140016569  call    cs:__imp_FltQueueGenericWorkItem
0x140016570  nop     dword ptr [rax+rax+00h]
0x140016575  mov     ebx, eax
0x140016577  test    eax, eax
0x140016579  jns     short loc_140016585
0x14001657b  jmp     short loc_1400165AC
0x14001657d  mov     rcx, rsi
0x140016580  call    FILockExclusiveRelease
0x140016585  xor     ebx, ebx
0x140016587  mov     eax, ebx
0x140016589  add     rsp, 38h
0x14001658d  pop     r15
0x14001658f  pop     r14
0x140016591  pop     rdi
0x140016592  pop     rsi
0x140016593  pop     rbp
0x140016594  pop     rbx
0x140016595  retn
0x140016597  mov     ebx, 0C00002E9h
0x14001659c  jmp     short loc_140016587
0x14001659e  mov     ebx, 0C000022Dh
0x1400165a3  jmp     short loc_140016587
0x1400165a5  xor     ebp, ebp
0x1400165a7  mov     ebx, 0C000009Ah
0x1400165ac  mov     rcx, rsi
0x1400165af  call    FILockExclusiveAcquire
0x1400165b4  and     dword ptr [rdi+84h], 0FFFFFFFDh
0x1400165bb  mov     rcx, rsi
0x1400165be  call    FILockExclusiveRelease
0x1400165c3  test    r14, r14
0x1400165c6  jz      short loc_1400165D7
0x1400165c8  mov     rcx, r14; FltWorkItem
0x1400165cb  call    cs:__imp_FltFreeGenericWorkItem
0x1400165d2  nop     dword ptr [rax+rax+00h]
0x1400165d7  test    rbp, rbp
0x1400165da  jz      short loc_140016587
0x1400165dc  mov     rcx, rbp; Object
0x1400165df  call    cs:__imp_ObfDereferenceObject
0x1400165e6  nop     dword ptr [rax+rax+00h]
0x1400165eb  jmp     short loc_140016587
```
