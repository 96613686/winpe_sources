# DfscCacheExpire

- ea: `0x14001a7bc`
- end: `0x14001a89d`
- name: `DfscCacheExpire`
- size: `225`
- prototype: `__int64 __fastcall(PUNICODE_PREFIX_TABLE PrefixTable)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014910`

## callees

- `0x140002340`
- `0x1400025f4`
- `0x14001a7bc`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x14001a80a`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x14001a80a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a837`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a837`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a82b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a82b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001a7dd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001a7dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a7cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a7cb`

## pseudocode

```c
void __fastcall DfscCacheExpire(PUNICODE_PREFIX_TABLE PrefixTable)
{
  int v2; // edi
  BOOLEAN i; // dl
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax

  v2 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)&PrefixTable[2].NextPrefixTree, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, PrefixTable);
  for ( i = 1; ; i = 0 )
  {
    UnicodePrefix = RtlNextUnicodePrefix(PrefixTable, i);
    if ( !UnicodePrefix )
      break;
    ++v2;
    UnicodePrefix[-1].CaseMatch = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, PrefixTable, v2);
  ExReleaseResourceLite((PERESOURCE)&PrefixTable[2].NextPrefixTree);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14001a7bc  push    rbx
0x14001a7be  push    rsi
0x14001a7bf  push    rdi
0x14001a7c0  push    r14
0x14001a7c2  sub     rsp, 38h
0x14001a7c6  mov     rbx, rcx
0x14001a7c9  xor     edi, edi
0x14001a7cb  call    cs:__imp_KeEnterCriticalRegion
0x14001a7d2  nop     dword ptr [rax+rax+00h]
0x14001a7d7  mov     dl, 1; Wait
0x14001a7d9  lea     rcx, [rbx+38h]; Resource
0x14001a7dd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001a7e4  nop     dword ptr [rax+rax+00h]
0x14001a7e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a7f0  lea     r14, WPP_GLOBAL_Control
0x14001a7f7  cmp     rcx, r14
0x14001a7fa  jz      short loc_14001A805
0x14001a7fc  test    dword ptr [rcx+2Ch], 200000h
0x14001a803  jnz     short loc_14001A84E
0x14001a805  mov     dl, 1; Restart
0x14001a807  mov     rcx, rbx; PrefixTable
0x14001a80a  call    cs:__imp_RtlNextUnicodePrefix
0x14001a811  nop     dword ptr [rax+rax+00h]
0x14001a816  test    rax, rax
0x14001a819  jnz     short loc_14001A868
0x14001a81b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a822  cmp     rcx, r14
0x14001a825  jnz     short loc_14001A876
0x14001a827  lea     rcx, [rbx+38h]; Resource
0x14001a82b  call    cs:__imp_ExReleaseResourceLite
0x14001a832  nop     dword ptr [rax+rax+00h]
0x14001a837  call    cs:__imp_KeLeaveCriticalRegion
0x14001a83e  nop     dword ptr [rax+rax+00h]
0x14001a843  add     rsp, 38h
0x14001a847  pop     r14
0x14001a849  pop     rdi
0x14001a84a  pop     rsi
0x14001a84b  pop     rbx
0x14001a84c  retn
0x14001a84e  mov     rcx, [rcx+18h]
0x14001a852  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001a859  mov     edx, 1Dh
0x14001a85e  mov     r9, rbx
0x14001a861  call    WPP_SF_q
0x14001a866  jmp     short loc_14001A805
0x14001a868  inc     edi
0x14001a86a  mov     qword ptr [rax-28h], 0
0x14001a872  xor     edx, edx
0x14001a874  jmp     short loc_14001A807
0x14001a876  test    dword ptr [rcx+2Ch], 200000h
0x14001a87d  jz      short loc_14001A827
0x14001a87f  mov     rcx, [rcx+18h]
0x14001a883  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001a88a  mov     edx, 1Eh
0x14001a88f  mov     [rsp+58h+var_38], edi
0x14001a893  mov     r9, rbx
0x14001a896  call    WPP_SF_qD
0x14001a89b  jmp     short loc_14001A827
```
