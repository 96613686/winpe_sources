# FveInlineWriteCompletionRoutine

- ea: `0x1400dc768`
- end: `0x1400dc9bb`
- name: `FveInlineWriteCompletionRoutine`
- size: `595`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ba0e0`
- `0x1400ba140`
- `0x1400ba1a0`

## callees

- `0x140008cd4`
- `0x140009f00`
- `0x1400294e4`
- `0x14002c140`
- `0x1400dc768`
- `0x1400dcbc4`
- `0x1400ea2f8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400dc89f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400dc89f`
- `ntoskrnl!IoFreeMdl` at `0x1400dc86f`
- `ntoskrnl!IoFreeMdl` at `0x1400dc86f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400dc913`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400dc913`
- `ntoskrnl!KeBugCheckEx` at `0x1400dc945`
- `ntoskrnl!KeBugCheckEx` at `0x1400dc945`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dc95a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dc95a`

## pseudocode

```c
__int64 __fastcall FveInlineWriteCompletionRoutine(__int64 a1, __int64 a2, __int64 a3, unsigned __int8 a4, char a5)
{
  _QWORD *v5; // rax
  void *v6; // r15
  __int64 v7; // rdi
  _QWORD *v11; // rcx
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
    v11 = (_QWORD *)v5[1];
    if ( v11 )
    {
      if ( !v5[2] && !v5[3] && !v5[4] )
      {
        v5[1] = 0;
        v6 = v11;
        v12 = v11[3];
        if ( v12 )
          v11[3] = MEMORY[0xFFFFF78000000008] - v12;
      }
    }
  }
  FvePerfTraceDevPtr(v7, FVE_PERF_WRITE_SUBREQUEST_STOP, a2);
  FvePerfTraceDevPtr(v7, FVE_PERF_WRITE_REQUEST_STOP, a2);
  if ( a5 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v7 + 8) + 9680LL) & 2) != 0 )
      FveIceSimCompleteWriteRequest(v7, a2);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v22 = 80;
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
      v22 = 81;
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
0x1400dc768  push    rbx
0x1400dc76a  push    rbp
0x1400dc76b  push    rsi
0x1400dc76c  push    rdi
0x1400dc76d  push    r12
0x1400dc76f  push    r14
0x1400dc771  push    r15
0x1400dc773  sub     rsp, 30h
0x1400dc777  mov     rax, [rdx+0B8h]
0x1400dc77e  xor     r15d, r15d
0x1400dc781  mov     rdi, [rcx+40h]
0x1400dc785  mov     r12d, r9d
0x1400dc788  mov     r14, r8
0x1400dc78b  mov     rbx, rdx
0x1400dc78e  test    rax, rax
0x1400dc791  jz      short loc_1400DC7C2
0x1400dc793  mov     rcx, [rax+8]
0x1400dc797  test    rcx, rcx
0x1400dc79a  jz      short loc_1400DC7C2
0x1400dc79c  cmp     [rax+10h], r15
0x1400dc7a0  jnz     short loc_1400DC7C2
0x1400dc7a2  cmp     [rax+18h], r15
0x1400dc7a6  jnz     short loc_1400DC7C2
0x1400dc7a8  cmp     [rax+20h], r15
0x1400dc7ac  jnz     short loc_1400DC7C2
0x1400dc7ae  mov     qword ptr [rax+8], 0
0x1400dc7b6  mov     r15, rcx
0x1400dc7b9  mov     rdx, [rcx+18h]
0x1400dc7bd  test    rdx, rdx
0x1400dc7c0  jnz     short loc_1400DC838
0x1400dc7c2  mov     r8, rbx
0x1400dc7c5  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_STOP
0x1400dc7cc  mov     rcx, rdi
0x1400dc7cf  call    FvePerfTraceDevPtr
0x1400dc7d4  mov     r8, rbx
0x1400dc7d7  lea     rdx, FVE_PERF_WRITE_REQUEST_STOP
0x1400dc7de  mov     rcx, rdi
0x1400dc7e1  call    FvePerfTraceDevPtr
0x1400dc7e6  cmp     [rsp+68h+arg_20], 0
0x1400dc7ee  jnz     loc_1400DC96B
0x1400dc7f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400dc7fb  lea     rax, WPP_GLOBAL_Control
0x1400dc802  cmp     rcx, rax
0x1400dc805  jnz     loc_1400DC8B0
0x1400dc80b  test    r14, r14
0x1400dc80e  jnz     short loc_1400DC84E
0x1400dc810  mov     rcx, r15; Entry
0x1400dc813  call    ReleaseInlineControl
0x1400dc818  mov     r8b, r12b
0x1400dc81b  mov     rdx, rbx
0x1400dc81e  mov     rcx, rdi
0x1400dc821  call    FvepInformRundownFinishedWithDisk
0x1400dc826  xor     eax, eax
0x1400dc828  add     rsp, 30h
0x1400dc82c  pop     r15
0x1400dc82e  pop     r14
0x1400dc830  pop     r12
0x1400dc832  pop     rdi
0x1400dc833  pop     rsi
0x1400dc834  pop     rbp
0x1400dc835  pop     rbx
0x1400dc836  retn
0x1400dc838  mov     rax, ds:0FFFFF78000000008h
0x1400dc842  sub     rax, rdx
0x1400dc845  mov     [rcx+18h], rax
0x1400dc849  jmp     loc_1400DC7C2
0x1400dc84e  mov     rcx, [rbx+8]; MemoryDescriptorList
0x1400dc852  mov     bpl, r14b
0x1400dc855  and     bpl, 3
0x1400dc859  and     r14, 0FFFFFFFFFFFFFFFCh
0x1400dc85d  test    byte ptr [rcx+0Ah], 5
0x1400dc861  jz      loc_1400DC8FA
0x1400dc867  mov     rsi, [rcx+18h]
0x1400dc86b  mov     rcx, [rbx+8]; Mdl
0x1400dc86f  call    cs:__imp_IoFreeMdl
0x1400dc876  nop     dword ptr [rax+rax+00h]
0x1400dc87b  mov     [rbx+8], r14
0x1400dc87f  cmp     bpl, 1
0x1400dc883  jnz     loc_1400DC927
0x1400dc889  mov     rcx, [rdi+7E8h]
0x1400dc890  mov     rdx, rsi; Entry
0x1400dc893  test    rcx, rcx
0x1400dc896  jnz     short loc_1400DC8E7
0x1400dc898  mov     rcx, [rdi+7E0h]; Lookaside
0x1400dc89f  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400dc8a6  nop     dword ptr [rax+rax+00h]
0x1400dc8ab  jmp     loc_1400DC810
0x1400dc8b0  mov     eax, [rcx+2Ch]
0x1400dc8b3  test    al, al
0x1400dc8b5  jns     loc_1400DC80B
0x1400dc8bb  cmp     byte ptr [rcx+29h], 4
0x1400dc8bf  jb      loc_1400DC80B
0x1400dc8c5  mov     edx, 51h ; 'Q'
0x1400dc8ca  mov     eax, [rbx+30h]
0x1400dc8cd  mov     r9, rdi
0x1400dc8d0  mov     rcx, [rcx+18h]
0x1400dc8d4  mov     [rsp+68h+Priority], eax
0x1400dc8d8  mov     qword ptr [rsp+68h+BugCheckOnFailure], rbx
0x1400dc8dd  call    WPP_SF_qqd
0x1400dc8e2  jmp     loc_1400DC80B
0x1400dc8e7  mov     r8d, gs:1A4h
0x1400dc8f0  call    PplFreeToLookasideListProcessor
0x1400dc8f5  jmp     loc_1400DC810
0x1400dc8fa  xor     r9d, r9d; RequestedAddress
0x1400dc8fd  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400dc905  xor     edx, edx; AccessMode
0x1400dc907  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400dc90f  lea     r8d, [r9+1]; CacheType
0x1400dc913  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400dc91a  nop     dword ptr [rax+rax+00h]
0x1400dc91f  mov     rsi, rax
0x1400dc922  jmp     loc_1400DC86B
0x1400dc927  cmp     bpl, 2
0x1400dc92b  jz      short loc_1400DC952
0x1400dc92d  xor     r9d, r9d; BugCheckParameter3
0x1400dc930  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; BugCheckParameter4
0x1400dc939  xor     r8d, r8d; BugCheckParameter2
0x1400dc93c  mov     ecx, 120h; BugCheckCode
0x1400dc941  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400dc945  call    cs:__imp_KeBugCheckEx
0x1400dc952  mov     edx, 70455646h; Tag
0x1400dc957  mov     rcx, rsi; P
0x1400dc95a  call    cs:__imp_ExFreePoolWithTag
0x1400dc961  nop     dword ptr [rax+rax+00h]
0x1400dc966  jmp     loc_1400DC810
0x1400dc96b  mov     rax, [rdi+8]
0x1400dc96f  mov     ecx, [rax+25D0h]
0x1400dc975  test    cl, 2
0x1400dc978  jz      short loc_1400DC985
0x1400dc97a  mov     rdx, rbx
0x1400dc97d  mov     rcx, rdi
0x1400dc980  call    FveIceSimCompleteWriteRequest
0x1400dc985  mov     rcx, cs:WPP_GLOBAL_Control
0x1400dc98c  lea     rax, WPP_GLOBAL_Control
0x1400dc993  cmp     rcx, rax
0x1400dc996  jz      loc_1400DC80B
0x1400dc99c  mov     eax, [rcx+2Ch]
0x1400dc99f  test    al, al
0x1400dc9a1  jns     loc_1400DC80B
0x1400dc9a7  cmp     byte ptr [rcx+29h], 4
0x1400dc9ab  jb      loc_1400DC80B
0x1400dc9b1  mov     edx, 50h ; 'P'
0x1400dc9b6  jmp     loc_1400DC8CA
```
