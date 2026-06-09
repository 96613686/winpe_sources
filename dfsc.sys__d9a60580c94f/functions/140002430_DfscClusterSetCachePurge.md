# DfscClusterSetCachePurge

- ea: `0x140002430`
- end: `0x140002567`
- name: `DfscClusterSetCachePurge`
- size: `311`
- prototype: `__int64 __fastcall(PUNICODE_PREFIX_TABLE PrefixTable)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140014d30`
- `0x1400169f8`

## callees

- `0x140002430`
- `0x1400025f4`
- `0x140002638`
- `0x1400199e4`
- `0x14001d090`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400024e3`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400024e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000252f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000254b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000252f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000254b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002523`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000253f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002523`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000253f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140002458`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000247c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140002458`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000247c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002446`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002464`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002446`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002464`

## pseudocode

```c
void __fastcall DfscClusterSetCachePurge(PUNICODE_PREFIX_TABLE PrefixTable)
{
  int v2; // ebp
  int v3; // esi
  BOOLEAN i; // dl
  volatile signed __int32 *p_RightChild; // rbx
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  __int64 v7; // r8

  v2 = 0;
  v3 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)&PrefixTable[2].NextPrefixTree, 1u);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)&PrefixTable[6].LastNextEntry, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, PrefixTable);
  for ( i = 1; ; i = 0 )
  {
    UnicodePrefix = RtlNextUnicodePrefix(PrefixTable, i);
    if ( !UnicodePrefix )
      break;
    p_RightChild = (volatile signed __int32 *)&UnicodePrefix[-2].Links.RightChild;
    if ( LOBYTE(UnicodePrefix[-1].NodeTypeCode) )
    {
      DfscRmUnlinkReferral((__int64)&UnicodePrefix[-2].Links.RightChild);
      DfscRmDereferenceReferral(p_RightChild);
      ++v2;
    }
    else
    {
      ++v3;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 28, v7, PrefixTable, v2, v3);
  ExReleaseResourceLite((PERESOURCE)&PrefixTable[6].LastNextEntry);
  KeLeaveCriticalRegion();
  ExReleaseResourceLite((PERESOURCE)&PrefixTable[2].NextPrefixTree);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140002430  push    rbx
0x140002432  push    rbp
0x140002433  push    rsi
0x140002434  push    rdi
0x140002435  push    r13
0x140002437  push    r14
0x140002439  push    r15
0x14000243b  sub     rsp, 30h
0x14000243f  mov     rdi, rcx
0x140002442  xor     ebp, ebp
0x140002444  xor     esi, esi
0x140002446  call    cs:__imp_KeEnterCriticalRegion
0x14000244d  nop     dword ptr [rax+rax+00h]
0x140002452  mov     dl, 1; Wait
0x140002454  lea     rcx, [rdi+38h]; Resource
0x140002458  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000245f  nop     dword ptr [rax+rax+00h]
0x140002464  call    cs:__imp_KeEnterCriticalRegion
0x14000246b  nop     dword ptr [rax+rax+00h]
0x140002470  lea     r15, [rdi+0A0h]
0x140002477  mov     dl, 1; Wait
0x140002479  mov     rcx, r15; Resource
0x14000247c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140002483  nop     dword ptr [rax+rax+00h]
0x140002488  mov     rcx, cs:WPP_GLOBAL_Control
0x14000248f  lea     r13, WPP_GLOBAL_Control
0x140002496  cmp     rcx, r13
0x140002499  jz      short loc_1400024BA
0x14000249b  test    dword ptr [rcx+2Ch], 200000h
0x1400024a2  jz      short loc_1400024BA
0x1400024a4  mov     rcx, [rcx+18h]
0x1400024a8  lea     edx, [rbp+1Bh]
0x1400024ab  mov     r9, rdi
0x1400024ae  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x1400024b5  call    WPP_SF_q
0x1400024ba  mov     dl, 1
0x1400024bc  jmp     short loc_1400024E0
0x1400024be  lea     rbx, [rax-48h]
0x1400024c2  cmp     byte ptr [rbx+10h], 0
0x1400024c6  jnz     short loc_1400024CC
0x1400024c8  inc     esi
0x1400024ca  jmp     short loc_1400024DE
0x1400024cc  mov     rcx, rbx
0x1400024cf  call    DfscRmUnlinkReferral
0x1400024d4  mov     rcx, rbx; P
0x1400024d7  call    DfscRmDereferenceReferral
0x1400024dc  inc     ebp
0x1400024de  xor     edx, edx; Restart
0x1400024e0  mov     rcx, rdi; PrefixTable
0x1400024e3  call    cs:__imp_RtlNextUnicodePrefix
0x1400024ea  nop     dword ptr [rax+rax+00h]
0x1400024ef  test    rax, rax
0x1400024f2  jnz     short loc_1400024BE
0x1400024f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400024fb  cmp     rcx, r13
0x1400024fe  jz      short loc_140002520
0x140002500  test    dword ptr [rcx+2Ch], 200000h
0x140002507  jz      short loc_140002520
0x140002509  mov     rcx, [rcx+18h]
0x14000250d  lea     edx, [rax+1Ch]
0x140002510  mov     [rsp+68h+var_40], esi
0x140002514  mov     r9, rdi
0x140002517  mov     [rsp+68h+var_48], ebp
0x14000251b  call    WPP_SF_qDD
0x140002520  mov     rcx, r15; Resource
0x140002523  call    cs:__imp_ExReleaseResourceLite
0x14000252a  nop     dword ptr [rax+rax+00h]
0x14000252f  call    cs:__imp_KeLeaveCriticalRegion
0x140002536  nop     dword ptr [rax+rax+00h]
0x14000253b  lea     rcx, [rdi+38h]; Resource
0x14000253f  call    cs:__imp_ExReleaseResourceLite
0x140002546  nop     dword ptr [rax+rax+00h]
0x14000254b  call    cs:__imp_KeLeaveCriticalRegion
0x140002552  nop     dword ptr [rax+rax+00h]
0x140002557  add     rsp, 30h
0x14000255b  pop     r15
0x14000255d  pop     r14
0x14000255f  pop     r13
0x140002561  pop     rdi
0x140002562  pop     rsi
0x140002563  pop     rbp
0x140002564  pop     rbx
0x140002565  retn
```
