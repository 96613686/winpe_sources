# FveInlineWriteCompletionRoutineRdpLevel2

- ea: `0x1400df860`
- end: `0x1400dfa4b`
- name: `FveInlineWriteCompletionRoutineRdpLevel2`
- size: `491`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008d94`
- `0x140009fc0`
- `0x14002a4e4`
- `0x14002d140`
- `0x1400df860`
- `0x1400dfa54`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400df97f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400df97f`
- `ntoskrnl!IoFreeMdl` at `0x1400df94f`
- `ntoskrnl!IoFreeMdl` at `0x1400df94f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400df9f3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400df9f3`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfa25`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfa25`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dfa3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dfa3a`

## pseudocode

```c
__int64 __fastcall FveInlineWriteCompletionRoutineRdpLevel2(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rax
  ULONG_PTR v4; // r15
  __int64 v5; // rdi
  ULONG_PTR v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v12; // rcx
  char v13; // r14
  unsigned __int64 v14; // rbp
  PVOID v15; // rsi
  __int64 v16; // r8
  __int64 v17; // rcx

  v3 = *(_QWORD **)(a2 + 184);
  v4 = 0;
  v5 = *(_QWORD *)(a1 + 64);
  if ( v3 )
  {
    v8 = v3[1];
    if ( v8 )
    {
      if ( !v3[2] && !v3[3] && !v3[4] )
      {
        v3[1] = 0;
        v4 = v8;
        v9 = *(_QWORD *)(v8 + 24);
        if ( v9 )
          *(_QWORD *)(v8 + 24) = MEMORY[0xFFFFF78000000008] - v9;
      }
    }
  }
  FvePerfTraceDevPtr(v5, FVE_PERF_WRITE_SUBREQUEST_STOP, a2);
  FvePerfTraceDevPtr(v5, FVE_PERF_WRITE_REQUEST_STOP, a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 88, v10, v5, a2, *(_DWORD *)(a2 + 48));
  }
  if ( a3 )
  {
    v12 = *(_QWORD *)(a2 + 8);
    v13 = a3 & 3;
    v14 = a3 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (*(_BYTE *)(v12 + 10) & 5) != 0 )
      v15 = *(PVOID *)(v12 + 24);
    else
      v15 = MmMapLockedPagesSpecifyCache((PMDL)v12, 0, MmCached, 0, 0, 0x40000010u);
    IoFreeMdl(*(PMDL *)(a2 + 8));
    *(_QWORD *)(a2 + 8) = v14;
    if ( v13 == 1 )
    {
      v17 = *(_QWORD *)(v5 + 2024);
      if ( v17 )
      {
        LODWORD(v16) = HIDWORD(KeGetPcr()[1].LockArray);
        PplFreeToLookasideListProcessor(v17, v15, v16);
      }
      else
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 2016), v15);
      }
    }
    else
    {
      if ( v13 != 2 )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
      ExFreePoolWithTag(v15, 0x70455646u);
    }
  }
  ReleaseInlineControl(v4);
  FvepInformRundownFinishedWithDisk(v5, a2, 2u);
  return 0;
}

```

## disassembly

```asm
0x1400df860  push    rbx
0x1400df862  push    rbp
0x1400df863  push    rsi
0x1400df864  push    rdi
0x1400df865  push    r14
0x1400df867  push    r15
0x1400df869  sub     rsp, 38h
0x1400df86d  mov     rax, [rdx+0B8h]
0x1400df874  xor     r15d, r15d
0x1400df877  mov     rdi, [rcx+40h]
0x1400df87b  mov     rbp, r8
0x1400df87e  mov     rbx, rdx
0x1400df881  test    rax, rax
0x1400df884  jz      short loc_1400DF8B5
0x1400df886  mov     rcx, [rax+8]
0x1400df88a  test    rcx, rcx
0x1400df88d  jz      short loc_1400DF8B5
0x1400df88f  cmp     [rax+10h], r15
0x1400df893  jnz     short loc_1400DF8B5
0x1400df895  cmp     [rax+18h], r15
0x1400df899  jnz     short loc_1400DF8B5
0x1400df89b  cmp     [rax+20h], r15
0x1400df89f  jnz     short loc_1400DF8B5
0x1400df8a1  mov     qword ptr [rax+8], 0
0x1400df8a9  mov     r15, rcx
0x1400df8ac  mov     rdx, [rcx+18h]
0x1400df8b0  test    rdx, rdx
0x1400df8b3  jnz     short loc_1400DF91B
0x1400df8b5  mov     r8, rbx
0x1400df8b8  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_STOP
0x1400df8bf  mov     rcx, rdi
0x1400df8c2  call    FvePerfTraceDevPtr
0x1400df8c7  mov     r8, rbx
0x1400df8ca  lea     rdx, FVE_PERF_WRITE_REQUEST_STOP
0x1400df8d1  mov     rcx, rdi
0x1400df8d4  call    FvePerfTraceDevPtr
0x1400df8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400df8e0  lea     rax, WPP_GLOBAL_Control
0x1400df8e7  cmp     rcx, rax
0x1400df8ea  jnz     loc_1400DF990
0x1400df8f0  test    rbp, rbp
0x1400df8f3  jnz     short loc_1400DF92E
0x1400df8f5  mov     rcx, r15; BugCheckParameter2
0x1400df8f8  call    ReleaseInlineControl
0x1400df8fd  mov     r8b, 2
0x1400df900  mov     rdx, rbx
0x1400df903  mov     rcx, rdi
0x1400df906  call    FvepInformRundownFinishedWithDisk
0x1400df90b  xor     eax, eax
0x1400df90d  add     rsp, 38h
0x1400df911  pop     r15
0x1400df913  pop     r14
0x1400df915  pop     rdi
0x1400df916  pop     rsi
0x1400df917  pop     rbp
0x1400df918  pop     rbx
0x1400df919  retn
0x1400df91b  mov     rax, ds:0FFFFF78000000008h
0x1400df925  sub     rax, rdx
0x1400df928  mov     [rcx+18h], rax
0x1400df92c  jmp     short loc_1400DF8B5
0x1400df92e  mov     rcx, [rbx+8]; MemoryDescriptorList
0x1400df932  mov     r14b, bpl
0x1400df935  and     r14b, 3
0x1400df939  and     rbp, 0FFFFFFFFFFFFFFFCh
0x1400df93d  test    byte ptr [rcx+0Ah], 5
0x1400df941  jz      loc_1400DF9DA
0x1400df947  mov     rsi, [rcx+18h]
0x1400df94b  mov     rcx, [rbx+8]; Mdl
0x1400df94f  call    cs:__imp_IoFreeMdl
0x1400df956  nop     dword ptr [rax+rax+00h]
0x1400df95b  mov     [rbx+8], rbp
0x1400df95f  cmp     r14b, 1
0x1400df963  jnz     loc_1400DFA07
0x1400df969  mov     rcx, [rdi+7E8h]
0x1400df970  mov     rdx, rsi; Entry
0x1400df973  test    rcx, rcx
0x1400df976  jnz     short loc_1400DF9C7
0x1400df978  mov     rcx, [rdi+7E0h]; Lookaside
0x1400df97f  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400df986  nop     dword ptr [rax+rax+00h]
0x1400df98b  jmp     loc_1400DF8F5
0x1400df990  mov     eax, [rcx+2Ch]
0x1400df993  test    al, al
0x1400df995  jns     loc_1400DF8F0
0x1400df99b  cmp     byte ptr [rcx+29h], 4
0x1400df99f  jb      loc_1400DF8F0
0x1400df9a5  mov     eax, [rbx+30h]
0x1400df9a8  mov     edx, 58h ; 'X'
0x1400df9ad  mov     rcx, [rcx+18h]
0x1400df9b1  mov     r9, rdi
0x1400df9b4  mov     [rsp+68h+Priority], eax
0x1400df9b8  mov     qword ptr [rsp+68h+BugCheckOnFailure], rbx
0x1400df9bd  call    WPP_SF_qqd
0x1400df9c2  jmp     loc_1400DF8F0
0x1400df9c7  mov     r8d, gs:1A4h
0x1400df9d0  call    PplFreeToLookasideListProcessor
0x1400df9d5  jmp     loc_1400DF8F5
0x1400df9da  xor     r9d, r9d; RequestedAddress
0x1400df9dd  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400df9e5  xor     edx, edx; AccessMode
0x1400df9e7  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400df9ef  lea     r8d, [r9+1]; CacheType
0x1400df9f3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400df9fa  nop     dword ptr [rax+rax+00h]
0x1400df9ff  mov     rsi, rax
0x1400dfa02  jmp     loc_1400DF94B
0x1400dfa07  cmp     r14b, 2
0x1400dfa0b  jz      short loc_1400DFA32
0x1400dfa0d  xor     r9d, r9d; BugCheckParameter3
0x1400dfa10  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; BugCheckParameter4
0x1400dfa19  xor     r8d, r8d; BugCheckParameter2
0x1400dfa1c  mov     ecx, 120h; BugCheckCode
0x1400dfa21  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400dfa25  call    cs:__imp_KeBugCheckEx
0x1400dfa32  mov     edx, 70455646h; Tag
0x1400dfa37  mov     rcx, rsi; P
0x1400dfa3a  call    cs:__imp_ExFreePoolWithTag
0x1400dfa41  nop     dword ptr [rax+rax+00h]
0x1400dfa46  jmp     loc_1400DF8F5
```
