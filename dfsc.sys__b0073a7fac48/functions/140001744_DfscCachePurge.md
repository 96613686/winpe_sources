# DfscCachePurge

- ea: `0x140001744`
- end: `0x14000187b`
- name: `DfscCachePurge`
- size: `311`
- prototype: `void __fastcall(PUNICODE_PREFIX_TABLE PrefixTable)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140011b78`
- `0x140014910`
- `0x140015050`
- `0x14001520c`
- `0x140018320`
- `0x140018994`
- `0x14001a4a0`

## callees

- `0x140001744`
- `0x1400025f4`
- `0x140002638`
- `0x1400199e4`
- `0x14001d090`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400017f7`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400017f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001843`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000185f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001843`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000185f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001837`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001853`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001837`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001853`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000176c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001790`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000176c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001790`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000175a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001778`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000175a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001778`

## pseudocode

```c
void __fastcall DfscCachePurge(PUNICODE_PREFIX_TABLE PrefixTable)
{
  int v2; // ebp
  int v3; // esi
  BOOLEAN i; // dl
  struct _RTL_SPLAY_LINKS **p_RightChild; // rbx
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  __int64 v7; // r8

  v2 = 0;
  v3 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)&PrefixTable[2].NextPrefixTree, 1u);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)&PrefixTable[6].LastNextEntry, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, PrefixTable);
  for ( i = 1; ; i = 0 )
  {
    UnicodePrefix = RtlNextUnicodePrefix(PrefixTable, i);
    if ( !UnicodePrefix )
      break;
    p_RightChild = &UnicodePrefix[-2].Links.RightChild;
    if ( LOBYTE(UnicodePrefix[-1].NodeTypeCode) )
    {
      ++v3;
    }
    else
    {
      DfscRmUnlinkReferral(&UnicodePrefix[-2].Links.RightChild);
      DfscRmDereferenceReferral(p_RightChild);
      ++v2;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 26, v7, PrefixTable, v2, v3);
  ExReleaseResourceLite((PERESOURCE)&PrefixTable[6].LastNextEntry);
  KeLeaveCriticalRegion();
  ExReleaseResourceLite((PERESOURCE)&PrefixTable[2].NextPrefixTree);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140001744  push    rbx
0x140001746  push    rbp
0x140001747  push    rsi
0x140001748  push    rdi
0x140001749  push    r13
0x14000174b  push    r14
0x14000174d  push    r15
0x14000174f  sub     rsp, 30h
0x140001753  mov     rdi, rcx
0x140001756  xor     ebp, ebp
0x140001758  xor     esi, esi
0x14000175a  call    cs:__imp_KeEnterCriticalRegion
0x140001761  nop     dword ptr [rax+rax+00h]
0x140001766  mov     dl, 1; Wait
0x140001768  lea     rcx, [rdi+38h]; Resource
0x14000176c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001773  nop     dword ptr [rax+rax+00h]
0x140001778  call    cs:__imp_KeEnterCriticalRegion
0x14000177f  nop     dword ptr [rax+rax+00h]
0x140001784  lea     r15, [rdi+0A0h]
0x14000178b  mov     dl, 1; Wait
0x14000178d  mov     rcx, r15; Resource
0x140001790  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001797  nop     dword ptr [rax+rax+00h]
0x14000179c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400017a3  lea     r13, WPP_GLOBAL_Control
0x1400017aa  cmp     rcx, r13
0x1400017ad  jz      short loc_1400017CE
0x1400017af  test    dword ptr [rcx+2Ch], 200000h
0x1400017b6  jz      short loc_1400017CE
0x1400017b8  mov     rcx, [rcx+18h]
0x1400017bc  lea     edx, [rbp+19h]
0x1400017bf  mov     r9, rdi
0x1400017c2  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x1400017c9  call    WPP_SF_q
0x1400017ce  mov     dl, 1
0x1400017d0  jmp     short loc_1400017F4
0x1400017d2  lea     rbx, [rax-48h]
0x1400017d6  cmp     byte ptr [rbx+10h], 0
0x1400017da  jz      short loc_1400017E0
0x1400017dc  inc     esi
0x1400017de  jmp     short loc_1400017F2
0x1400017e0  mov     rcx, rbx
0x1400017e3  call    DfscRmUnlinkReferral
0x1400017e8  mov     rcx, rbx; P
0x1400017eb  call    DfscRmDereferenceReferral
0x1400017f0  inc     ebp
0x1400017f2  xor     edx, edx; Restart
0x1400017f4  mov     rcx, rdi; PrefixTable
0x1400017f7  call    cs:__imp_RtlNextUnicodePrefix
0x1400017fe  nop     dword ptr [rax+rax+00h]
0x140001803  test    rax, rax
0x140001806  jnz     short loc_1400017D2
0x140001808  mov     rcx, cs:WPP_GLOBAL_Control
0x14000180f  cmp     rcx, r13
0x140001812  jz      short loc_140001834
0x140001814  test    dword ptr [rcx+2Ch], 200000h
0x14000181b  jz      short loc_140001834
0x14000181d  mov     rcx, [rcx+18h]
0x140001821  lea     edx, [rax+1Ah]
0x140001824  mov     [rsp+68h+var_40], esi
0x140001828  mov     r9, rdi
0x14000182b  mov     [rsp+68h+var_48], ebp
0x14000182f  call    WPP_SF_qDD
0x140001834  mov     rcx, r15; Resource
0x140001837  call    cs:__imp_ExReleaseResourceLite
0x14000183e  nop     dword ptr [rax+rax+00h]
0x140001843  call    cs:__imp_KeLeaveCriticalRegion
0x14000184a  nop     dword ptr [rax+rax+00h]
0x14000184f  lea     rcx, [rdi+38h]; Resource
0x140001853  call    cs:__imp_ExReleaseResourceLite
0x14000185a  nop     dword ptr [rax+rax+00h]
0x14000185f  call    cs:__imp_KeLeaveCriticalRegion
0x140001866  nop     dword ptr [rax+rax+00h]
0x14000186b  add     rsp, 30h
0x14000186f  pop     r15
0x140001871  pop     r14
0x140001873  pop     r13
0x140001875  pop     rdi
0x140001876  pop     rsi
0x140001877  pop     rbp
0x140001878  pop     rbx
0x140001879  retn
```
