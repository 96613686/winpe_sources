# FveInlineWriteCompletionRoutineRdpLevel2

- ea: `0x1400dc9d0`
- end: `0x1400dcbbb`
- name: `FveInlineWriteCompletionRoutineRdpLevel2`
- size: `491`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008cd4`
- `0x140009f00`
- `0x1400294e4`
- `0x14002c140`
- `0x1400dc9d0`
- `0x1400dcbc4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400dcaef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400dcaef`
- `ntoskrnl!IoFreeMdl` at `0x1400dcabf`
- `ntoskrnl!IoFreeMdl` at `0x1400dcabf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400dcb63`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400dcb63`
- `ntoskrnl!KeBugCheckEx` at `0x1400dcb95`
- `ntoskrnl!KeBugCheckEx` at `0x1400dcb95`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dcbaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dcbaa`

## pseudocode

```c
__int64 __fastcall FveInlineWriteCompletionRoutineRdpLevel2(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rax
  void *v4; // r15
  __int64 v5; // rdi
  _QWORD *v8; // rcx
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
    v8 = (_QWORD *)v3[1];
    if ( v8 )
    {
      if ( !v3[2] && !v3[3] && !v3[4] )
      {
        v3[1] = 0;
        v4 = v8;
        v9 = v8[3];
        if ( v9 )
          v8[3] = MEMORY[0xFFFFF78000000008] - v9;
      }
    }
  }
  FvePerfTraceDevPtr(v5, FVE_PERF_WRITE_SUBREQUEST_STOP, a2);
  FvePerfTraceDevPtr(v5, FVE_PERF_WRITE_REQUEST_STOP, a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 81, v10, v5, a2, *(_DWORD *)(a2 + 48));
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
0x1400dc9d0  push    rbx
0x1400dc9d2  push    rbp
0x1400dc9d3  push    rsi
0x1400dc9d4  push    rdi
0x1400dc9d5  push    r14
0x1400dc9d7  push    r15
0x1400dc9d9  sub     rsp, 38h
0x1400dc9dd  mov     rax, [rdx+0B8h]
0x1400dc9e4  xor     r15d, r15d
0x1400dc9e7  mov     rdi, [rcx+40h]
0x1400dc9eb  mov     rbp, r8
0x1400dc9ee  mov     rbx, rdx
0x1400dc9f1  test    rax, rax
0x1400dc9f4  jz      short loc_1400DCA25
0x1400dc9f6  mov     rcx, [rax+8]
0x1400dc9fa  test    rcx, rcx
0x1400dc9fd  jz      short loc_1400DCA25
0x1400dc9ff  cmp     [rax+10h], r15
0x1400dca03  jnz     short loc_1400DCA25
0x1400dca05  cmp     [rax+18h], r15
0x1400dca09  jnz     short loc_1400DCA25
0x1400dca0b  cmp     [rax+20h], r15
0x1400dca0f  jnz     short loc_1400DCA25
0x1400dca11  mov     qword ptr [rax+8], 0
0x1400dca19  mov     r15, rcx
0x1400dca1c  mov     rdx, [rcx+18h]
0x1400dca20  test    rdx, rdx
0x1400dca23  jnz     short loc_1400DCA8B
0x1400dca25  mov     r8, rbx
0x1400dca28  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_STOP
0x1400dca2f  mov     rcx, rdi
0x1400dca32  call    FvePerfTraceDevPtr
0x1400dca37  mov     r8, rbx
0x1400dca3a  lea     rdx, FVE_PERF_WRITE_REQUEST_STOP
0x1400dca41  mov     rcx, rdi
0x1400dca44  call    FvePerfTraceDevPtr
0x1400dca49  mov     rcx, cs:WPP_GLOBAL_Control
0x1400dca50  lea     rax, WPP_GLOBAL_Control
0x1400dca57  cmp     rcx, rax
0x1400dca5a  jnz     loc_1400DCB00
0x1400dca60  test    rbp, rbp
0x1400dca63  jnz     short loc_1400DCA9E
0x1400dca65  mov     rcx, r15; Entry
0x1400dca68  call    ReleaseInlineControl
0x1400dca6d  mov     r8b, 2
0x1400dca70  mov     rdx, rbx
0x1400dca73  mov     rcx, rdi
0x1400dca76  call    FvepInformRundownFinishedWithDisk
0x1400dca7b  xor     eax, eax
0x1400dca7d  add     rsp, 38h
0x1400dca81  pop     r15
0x1400dca83  pop     r14
0x1400dca85  pop     rdi
0x1400dca86  pop     rsi
0x1400dca87  pop     rbp
0x1400dca88  pop     rbx
0x1400dca89  retn
0x1400dca8b  mov     rax, ds:0FFFFF78000000008h
0x1400dca95  sub     rax, rdx
0x1400dca98  mov     [rcx+18h], rax
0x1400dca9c  jmp     short loc_1400DCA25
0x1400dca9e  mov     rcx, [rbx+8]; MemoryDescriptorList
0x1400dcaa2  mov     r14b, bpl
0x1400dcaa5  and     r14b, 3
0x1400dcaa9  and     rbp, 0FFFFFFFFFFFFFFFCh
0x1400dcaad  test    byte ptr [rcx+0Ah], 5
0x1400dcab1  jz      loc_1400DCB4A
0x1400dcab7  mov     rsi, [rcx+18h]
0x1400dcabb  mov     rcx, [rbx+8]; Mdl
0x1400dcabf  call    cs:__imp_IoFreeMdl
0x1400dcac6  nop     dword ptr [rax+rax+00h]
0x1400dcacb  mov     [rbx+8], rbp
0x1400dcacf  cmp     r14b, 1
0x1400dcad3  jnz     loc_1400DCB77
0x1400dcad9  mov     rcx, [rdi+7E8h]
0x1400dcae0  mov     rdx, rsi; Entry
0x1400dcae3  test    rcx, rcx
0x1400dcae6  jnz     short loc_1400DCB37
0x1400dcae8  mov     rcx, [rdi+7E0h]; Lookaside
0x1400dcaef  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400dcaf6  nop     dword ptr [rax+rax+00h]
0x1400dcafb  jmp     loc_1400DCA65
0x1400dcb00  mov     eax, [rcx+2Ch]
0x1400dcb03  test    al, al
0x1400dcb05  jns     loc_1400DCA60
0x1400dcb0b  cmp     byte ptr [rcx+29h], 4
0x1400dcb0f  jb      loc_1400DCA60
0x1400dcb15  mov     eax, [rbx+30h]
0x1400dcb18  mov     edx, 51h ; 'Q'
0x1400dcb1d  mov     rcx, [rcx+18h]
0x1400dcb21  mov     r9, rdi
0x1400dcb24  mov     [rsp+68h+Priority], eax
0x1400dcb28  mov     qword ptr [rsp+68h+BugCheckOnFailure], rbx
0x1400dcb2d  call    WPP_SF_qqd
0x1400dcb32  jmp     loc_1400DCA60
0x1400dcb37  mov     r8d, gs:1A4h
0x1400dcb40  call    PplFreeToLookasideListProcessor
0x1400dcb45  jmp     loc_1400DCA65
0x1400dcb4a  xor     r9d, r9d; RequestedAddress
0x1400dcb4d  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400dcb55  xor     edx, edx; AccessMode
0x1400dcb57  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400dcb5f  lea     r8d, [r9+1]; CacheType
0x1400dcb63  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400dcb6a  nop     dword ptr [rax+rax+00h]
0x1400dcb6f  mov     rsi, rax
0x1400dcb72  jmp     loc_1400DCABB
0x1400dcb77  cmp     r14b, 2
0x1400dcb7b  jz      short loc_1400DCBA2
0x1400dcb7d  xor     r9d, r9d; BugCheckParameter3
0x1400dcb80  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; BugCheckParameter4
0x1400dcb89  xor     r8d, r8d; BugCheckParameter2
0x1400dcb8c  mov     ecx, 120h; BugCheckCode
0x1400dcb91  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400dcb95  call    cs:__imp_KeBugCheckEx
0x1400dcba2  mov     edx, 70455646h; Tag
0x1400dcba7  mov     rcx, rsi; P
0x1400dcbaa  call    cs:__imp_ExFreePoolWithTag
0x1400dcbb1  nop     dword ptr [rax+rax+00h]
0x1400dcbb6  jmp     loc_1400DCA65
```
