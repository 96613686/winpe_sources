# FveInlineWriteCompletionRoutine

- ea: `0x1400df5f8`
- end: `0x1400df84b`
- name: `FveInlineWriteCompletionRoutine`
- size: `595`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400bd800`
- `0x1400bd860`
- `0x1400bd8c0`

## callees

- `0x140008d94`
- `0x140009fc0`
- `0x14002a4e4`
- `0x14002d140`
- `0x1400df5f8`
- `0x1400dfa54`
- `0x1400ef2f8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400df72f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400df72f`
- `ntoskrnl!IoFreeMdl` at `0x1400df6ff`
- `ntoskrnl!IoFreeMdl` at `0x1400df6ff`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400df7a3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400df7a3`
- `ntoskrnl!KeBugCheckEx` at `0x1400df7d5`
- `ntoskrnl!KeBugCheckEx` at `0x1400df7d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400df7ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400df7ea`

## pseudocode

```c
__int64 __fastcall FveInlineWriteCompletionRoutine(__int64 a1, __int64 a2, __int64 a3, unsigned __int8 a4, char a5)
{
  _QWORD *v5; // rax
  ULONG_PTR v6; // r15
  __int64 v7; // rdi
  ULONG_PTR v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  PDEVICE_OBJECT v14; // rcx
  __int64 v16; // rcx
  char v17; // bp
  unsigned __int64 v18; // r14
  PVOID v19; // rsi
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rdx

  v5 = *(_QWORD **)(a2 + 184);
  v6 = 0;
  v7 = *(_QWORD *)(a1 + 64);
  if ( v5 )
  {
    v11 = v5[1];
    if ( v11 )
    {
      if ( !v5[2] && !v5[3] && !v5[4] )
      {
        v5[1] = 0;
        v6 = v11;
        v12 = *(_QWORD *)(v11 + 24);
        if ( v12 )
          *(_QWORD *)(v11 + 24) = MEMORY[0xFFFFF78000000008] - v12;
      }
    }
  }
  FvePerfTraceDevPtr(v7, FVE_PERF_WRITE_SUBREQUEST_STOP, a2);
  FvePerfTraceDevPtr(v7, FVE_PERF_WRITE_REQUEST_STOP, a2);
  if ( a5 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v7 + 8) + 9928LL) & 2) != 0 )
      FveIceSimCompleteWriteRequest(v7, a2);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v22 = 87;
      goto LABEL_20;
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v22 = 88;
LABEL_20:
      WPP_SF_qqd(v14->AttachedDevice, v22, v13, v7, a2, *(_DWORD *)(a2 + 48));
    }
  }
  if ( a3 )
  {
    v16 = *(_QWORD *)(a2 + 8);
    v17 = a3 & 3;
    v18 = a3 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (*(_BYTE *)(v16 + 10) & 5) != 0 )
      v19 = *(PVOID *)(v16 + 24);
    else
      v19 = MmMapLockedPagesSpecifyCache((PMDL)v16, 0, MmCached, 0, 0, 0x40000010u);
    IoFreeMdl(*(PMDL *)(a2 + 8));
    *(_QWORD *)(a2 + 8) = v18;
    if ( v17 == 1 )
    {
      v21 = *(_QWORD *)(v7 + 2024);
      if ( v21 )
      {
        LODWORD(v20) = HIDWORD(KeGetPcr()[1].LockArray);
        PplFreeToLookasideListProcessor(v21, v19, v20);
      }
      else
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v7 + 2016), v19);
      }
    }
    else
    {
      if ( v17 != 2 )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
      ExFreePoolWithTag(v19, 0x70455646u);
    }
  }
  ReleaseInlineControl(v6);
  FvepInformRundownFinishedWithDisk(v7, a2, a4);
  return 0;
}

```

## disassembly

```asm
0x1400df5f8  push    rbx
0x1400df5fa  push    rbp
0x1400df5fb  push    rsi
0x1400df5fc  push    rdi
0x1400df5fd  push    r12
0x1400df5ff  push    r14
0x1400df601  push    r15
0x1400df603  sub     rsp, 30h
0x1400df607  mov     rax, [rdx+0B8h]
0x1400df60e  xor     r15d, r15d
0x1400df611  mov     rdi, [rcx+40h]
0x1400df615  mov     r12d, r9d
0x1400df618  mov     r14, r8
0x1400df61b  mov     rbx, rdx
0x1400df61e  test    rax, rax
0x1400df621  jz      short loc_1400DF652
0x1400df623  mov     rcx, [rax+8]
0x1400df627  test    rcx, rcx
0x1400df62a  jz      short loc_1400DF652
0x1400df62c  cmp     [rax+10h], r15
0x1400df630  jnz     short loc_1400DF652
0x1400df632  cmp     [rax+18h], r15
0x1400df636  jnz     short loc_1400DF652
0x1400df638  cmp     [rax+20h], r15
0x1400df63c  jnz     short loc_1400DF652
0x1400df63e  mov     qword ptr [rax+8], 0
0x1400df646  mov     r15, rcx
0x1400df649  mov     rdx, [rcx+18h]
0x1400df64d  test    rdx, rdx
0x1400df650  jnz     short loc_1400DF6C8
0x1400df652  mov     r8, rbx
0x1400df655  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_STOP
0x1400df65c  mov     rcx, rdi
0x1400df65f  call    FvePerfTraceDevPtr
0x1400df664  mov     r8, rbx
0x1400df667  lea     rdx, FVE_PERF_WRITE_REQUEST_STOP
0x1400df66e  mov     rcx, rdi
0x1400df671  call    FvePerfTraceDevPtr
0x1400df676  cmp     [rsp+68h+arg_20], 0
0x1400df67e  jnz     loc_1400DF7FB
0x1400df684  mov     rcx, cs:WPP_GLOBAL_Control
0x1400df68b  lea     rax, WPP_GLOBAL_Control
0x1400df692  cmp     rcx, rax
0x1400df695  jnz     loc_1400DF740
0x1400df69b  test    r14, r14
0x1400df69e  jnz     short loc_1400DF6DE
0x1400df6a0  mov     rcx, r15; BugCheckParameter2
0x1400df6a3  call    ReleaseInlineControl
0x1400df6a8  mov     r8b, r12b
0x1400df6ab  mov     rdx, rbx
0x1400df6ae  mov     rcx, rdi
0x1400df6b1  call    FvepInformRundownFinishedWithDisk
0x1400df6b6  xor     eax, eax
0x1400df6b8  add     rsp, 30h
0x1400df6bc  pop     r15
0x1400df6be  pop     r14
0x1400df6c0  pop     r12
0x1400df6c2  pop     rdi
0x1400df6c3  pop     rsi
0x1400df6c4  pop     rbp
0x1400df6c5  pop     rbx
0x1400df6c6  retn
0x1400df6c8  mov     rax, ds:0FFFFF78000000008h
0x1400df6d2  sub     rax, rdx
0x1400df6d5  mov     [rcx+18h], rax
0x1400df6d9  jmp     loc_1400DF652
0x1400df6de  mov     rcx, [rbx+8]; MemoryDescriptorList
0x1400df6e2  mov     bpl, r14b
0x1400df6e5  and     bpl, 3
0x1400df6e9  and     r14, 0FFFFFFFFFFFFFFFCh
0x1400df6ed  test    byte ptr [rcx+0Ah], 5
0x1400df6f1  jz      loc_1400DF78A
0x1400df6f7  mov     rsi, [rcx+18h]
0x1400df6fb  mov     rcx, [rbx+8]; Mdl
0x1400df6ff  call    cs:__imp_IoFreeMdl
0x1400df706  nop     dword ptr [rax+rax+00h]
0x1400df70b  mov     [rbx+8], r14
0x1400df70f  cmp     bpl, 1
0x1400df713  jnz     loc_1400DF7B7
0x1400df719  mov     rcx, [rdi+7E8h]
0x1400df720  mov     rdx, rsi; Entry
0x1400df723  test    rcx, rcx
0x1400df726  jnz     short loc_1400DF777
0x1400df728  mov     rcx, [rdi+7E0h]; Lookaside
0x1400df72f  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400df736  nop     dword ptr [rax+rax+00h]
0x1400df73b  jmp     loc_1400DF6A0
0x1400df740  mov     eax, [rcx+2Ch]
0x1400df743  test    al, al
0x1400df745  jns     loc_1400DF69B
0x1400df74b  cmp     byte ptr [rcx+29h], 4
0x1400df74f  jb      loc_1400DF69B
0x1400df755  mov     edx, 58h ; 'X'
0x1400df75a  mov     eax, [rbx+30h]
0x1400df75d  mov     r9, rdi
0x1400df760  mov     rcx, [rcx+18h]
0x1400df764  mov     [rsp+68h+Priority], eax
0x1400df768  mov     qword ptr [rsp+68h+BugCheckOnFailure], rbx
0x1400df76d  call    WPP_SF_qqd
0x1400df772  jmp     loc_1400DF69B
0x1400df777  mov     r8d, gs:1A4h
0x1400df780  call    PplFreeToLookasideListProcessor
0x1400df785  jmp     loc_1400DF6A0
0x1400df78a  xor     r9d, r9d; RequestedAddress
0x1400df78d  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400df795  xor     edx, edx; AccessMode
0x1400df797  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400df79f  lea     r8d, [r9+1]; CacheType
0x1400df7a3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400df7aa  nop     dword ptr [rax+rax+00h]
0x1400df7af  mov     rsi, rax
0x1400df7b2  jmp     loc_1400DF6FB
0x1400df7b7  cmp     bpl, 2
0x1400df7bb  jz      short loc_1400DF7E2
0x1400df7bd  xor     r9d, r9d; BugCheckParameter3
0x1400df7c0  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; BugCheckParameter4
0x1400df7c9  xor     r8d, r8d; BugCheckParameter2
0x1400df7cc  mov     ecx, 120h; BugCheckCode
0x1400df7d1  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400df7d5  call    cs:__imp_KeBugCheckEx
0x1400df7e2  mov     edx, 70455646h; Tag
0x1400df7e7  mov     rcx, rsi; P
0x1400df7ea  call    cs:__imp_ExFreePoolWithTag
0x1400df7f1  nop     dword ptr [rax+rax+00h]
0x1400df7f6  jmp     loc_1400DF6A0
0x1400df7fb  mov     rax, [rdi+8]
0x1400df7ff  mov     ecx, [rax+26C8h]
0x1400df805  test    cl, 2
0x1400df808  jz      short loc_1400DF815
0x1400df80a  mov     rdx, rbx
0x1400df80d  mov     rcx, rdi
0x1400df810  call    FveIceSimCompleteWriteRequest
0x1400df815  mov     rcx, cs:WPP_GLOBAL_Control
0x1400df81c  lea     rax, WPP_GLOBAL_Control
0x1400df823  cmp     rcx, rax
0x1400df826  jz      loc_1400DF69B
0x1400df82c  mov     eax, [rcx+2Ch]
0x1400df82f  test    al, al
0x1400df831  jns     loc_1400DF69B
0x1400df837  cmp     byte ptr [rcx+29h], 4
0x1400df83b  jb      loc_1400DF69B
0x1400df841  mov     edx, 57h ; 'W'
0x1400df846  jmp     loc_1400DF75A
```
