# PrjfContextCleanup

- ea: `0x1400211e0`
- end: `0x14002135f`
- name: `PrjfContextCleanup`
- size: `383`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000666c`
- `0x140006938`
- `0x14000b1a0`
- `0x14000b1d0`
- `0x1400211e0`
- `0x140034428`
- `0x140042a88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400212e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400212ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021337`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400212e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400212ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021337`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400212c8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400212c8`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021347`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021347`
- `FLTMGR!FltReleaseContext` at `0x14002127f`
- `FLTMGR!FltReleaseContext` at `0x140021298`
- `FLTMGR!FltReleaseContext` at `0x14002127f`
- `FLTMGR!FltReleaseContext` at `0x140021298`

## pseudocode

```c
void __fastcall PrjfContextCleanup(__int64 a1, __int64 a2)
{
  _QWORD **v3; // rax
  _QWORD *v4; // rdx
  void *v5; // rcx
  void *v6; // rcx
  _QWORD *v7; // rdi
  void *v8; // rcx
  void *v9; // rcx
  struct _ERESOURCE *v10; // rcx
  void *v11; // rcx
  __int128 v12; // [rsp+30h] [rbp-18h] BYREF

  if ( (_WORD)a2 == 2 )
  {
    v11 = *(void **)(a1 + 16);
    if ( v11 )
      ExFreePoolWithTag(v11, 0x63694A50u);
    v10 = (struct _ERESOURCE *)(a1 + 48);
    goto LABEL_27;
  }
  if ( (_WORD)a2 != 4 )
  {
    if ( (_WORD)a2 == 8 )
    {
      v5 = *(void **)(a1 + 8);
      if ( !v5 )
        return;
    }
    else
    {
      if ( (_WORD)a2 != 16 )
      {
        if ( (_WORD)a2 != 32 )
          MicrosoftTelemetryAssertTriggeredMsgKM("Unrecognized context type!");
        return;
      }
      if ( (*(_DWORD *)(a1 + 40) & 2) != 0 )
      {
        v3 = *(_QWORD ***)(a1 + 48);
        v4 = *v3;
        v12 = *(_OWORD *)(a1 + 56);
        PrjfSendEndDirectoryEnumerationCommand(0, *v4, 0, (_DWORD)v3 + 96, (__int64)&v12);
      }
      PrjfFreeEnumContexts((void **)a1);
      PrjfCleanupProcessInfo((void **)(a1 + 72));
      v5 = *(void **)(a1 + 48);
    }
    FltReleaseContext(v5);
    return;
  }
  v6 = *(void **)a1;
  if ( v6 )
    FltReleaseContext(v6);
  v7 = *(_QWORD **)(a1 + 88);
  if ( v7 )
  {
    if ( (_QWORD *)v7[25] != v7 + 25 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, a2);
    ExFreeToNPagedLookasideList(&stru_14001AB40, v7);
  }
  v8 = *(void **)(a1 + 72);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x69724A50u);
  v9 = *(void **)(a1 + 128);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x6E664A50u);
  if ( !*(_BYTE *)(a1 + 281) )
  {
    PrjfFreeInMemoryTombstoneHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 240));
    v10 = (struct _ERESOURCE *)(a1 + 136);
LABEL_27:
    ExDeleteResourceLite(v10);
  }
}

```

## disassembly

```asm
0x1400211e0  mov     [rsp+arg_0], rbx
0x1400211e5  push    rdi
0x1400211e6  sub     rsp, 40h
0x1400211ea  mov     rbx, rcx
0x1400211ed  cmp     dx, 2
0x1400211f1  jz      loc_140021329
0x1400211f7  cmp     dx, 4
0x1400211fb  jz      loc_140021290
0x140021201  cmp     dx, 8
0x140021205  jz      short loc_140021272
0x140021207  cmp     dx, 10h
0x14002120b  jz      short loc_140021228
0x14002120d  cmp     dx, 20h ; ' '
0x140021211  jz      loc_140021353
0x140021217  lea     rcx, aUnrecognizedCo; "Unrecognized context type!"
0x14002121e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140021223  jmp     loc_140021353
0x140021228  mov     eax, [rcx+28h]
0x14002122b  test    al, 2
0x14002122d  jz      short loc_14002125B
0x14002122f  mov     rax, [rcx+30h]
0x140021233  xor     r8d, r8d
0x140021236  movups  xmm0, xmmword ptr [rcx+38h]
0x14002123a  xor     ecx, ecx
0x14002123c  mov     rdx, [rax]
0x14002123f  lea     r9, [rax+60h]
0x140021243  lea     rax, [rsp+48h+var_18]
0x140021248  movdqu  [rsp+48h+var_18], xmm0
0x14002124e  mov     [rsp+48h+var_28], rax
0x140021253  mov     rdx, [rdx]
0x140021256  call    PrjfSendEndDirectoryEnumerationCommand
0x14002125b  mov     rcx, rbx
0x14002125e  call    PrjfFreeEnumContexts
0x140021263  lea     rcx, [rbx+48h]
0x140021267  call    PrjfCleanupProcessInfo
0x14002126c  mov     rcx, [rbx+30h]
0x140021270  jmp     short loc_14002127F
0x140021272  mov     rcx, [rcx+8]; Context
0x140021276  test    rcx, rcx
0x140021279  jz      loc_140021353
0x14002127f  call    cs:__imp_FltReleaseContext
0x140021286  nop     dword ptr [rax+rax+00h]
0x14002128b  jmp     loc_140021353
0x140021290  mov     rcx, [rcx]; Context
0x140021293  test    rcx, rcx
0x140021296  jz      short loc_1400212A4
0x140021298  call    cs:__imp_FltReleaseContext
0x14002129f  nop     dword ptr [rax+rax+00h]
0x1400212a4  mov     rdi, [rbx+58h]
0x1400212a8  test    rdi, rdi
0x1400212ab  jz      short loc_1400212D4
0x1400212ad  lea     rax, [rdi+0C8h]
0x1400212b4  cmp     [rax], rax
0x1400212b7  jz      short loc_1400212BE
0x1400212b9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400212be  mov     rdx, rdi; Entry
0x1400212c1  lea     rcx, stru_14001AB40; Lookaside
0x1400212c8  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400212cf  nop     dword ptr [rax+rax+00h]
0x1400212d4  mov     rcx, [rbx+48h]; P
0x1400212d8  test    rcx, rcx
0x1400212db  jz      short loc_1400212EE
0x1400212dd  mov     edx, 69724A50h; Tag
0x1400212e2  call    cs:__imp_ExFreePoolWithTag
0x1400212e9  nop     dword ptr [rax+rax+00h]
0x1400212ee  mov     rcx, [rbx+80h]; P
0x1400212f5  test    rcx, rcx
0x1400212f8  jz      short loc_14002130B
0x1400212fa  mov     edx, 6E664A50h; Tag
0x1400212ff  call    cs:__imp_ExFreePoolWithTag
0x140021306  nop     dword ptr [rax+rax+00h]
0x14002130b  cmp     byte ptr [rbx+119h], 0
0x140021312  jnz     short loc_140021353
0x140021314  lea     rcx, [rbx+0F0h]; HashTable
0x14002131b  call    PrjfFreeInMemoryTombstoneHashTable
0x140021320  lea     rcx, [rbx+88h]
0x140021327  jmp     short loc_140021347
0x140021329  mov     rcx, [rcx+10h]; P
0x14002132d  test    rcx, rcx
0x140021330  jz      short loc_140021343
0x140021332  mov     edx, 63694A50h; Tag
0x140021337  call    cs:__imp_ExFreePoolWithTag
0x14002133e  nop     dword ptr [rax+rax+00h]
0x140021343  lea     rcx, [rbx+30h]; Resource
0x140021347  call    cs:__imp_ExDeleteResourceLite
0x14002134e  nop     dword ptr [rax+rax+00h]
0x140021353  mov     rbx, [rsp+48h+arg_0]
0x140021358  add     rsp, 40h
0x14002135c  pop     rdi
0x14002135d  retn
```
