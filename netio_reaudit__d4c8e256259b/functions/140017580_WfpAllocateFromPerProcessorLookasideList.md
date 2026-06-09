# WfpAllocateFromPerProcessorLookasideList

- ea: `0x140017580`
- end: `0x140017678`
- name: `WfpAllocateFromPerProcessorLookasideList`
- size: `248`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140013638`
- `0x140015a80`
- `0x140018cf0`
- `0x14004e7d0`

## callees

- `0x140017580`
- `0x14001771c`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400175ae`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400175ae`

## string_xrefs

- `0x140017613`: `WfpAllocateFromPerProcessorLookasideList`
- `0x140017653`: `WfpAllocateFromPerProcessorLookasideList`

## pseudocode

```c
__int64 __fastcall WfpAllocateFromPerProcessorLookasideList(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rbx
  PVOID v4; // rax

  v3 = a1 + ((unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1) << 7);
  if ( !*(_BYTE *)(v3 + 176) )
    PplpLazyInitializeLookasideList(a1, v3 + 64);
  v4 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v3 + 64));
  *a2 = v4;
  if ( v4 )
    return 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAllocateFromPerProcessorLookasideList",
      23);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAllocateFromPerProcessorLookasideList",
      23);
  }
  return -1073741801;
}

```

## disassembly

```asm
0x140017580  mov     [rsp+arg_0], rbx
0x140017585  push    rdi
0x140017586  sub     rsp, 30h
0x14001758a  mov     eax, gs:1A4h
0x140017592  mov     rdi, rdx
0x140017595  lea     ebx, [rax+1]
0x140017598  shl     rbx, 7
0x14001759c  add     rbx, rcx
0x14001759f  movzx   eax, byte ptr [rbx+0B0h]
0x1400175a6  test    al, al
0x1400175a8  jz      short loc_1400175D0
0x1400175aa  lea     rcx, [rbx+40h]; Lookaside
0x1400175ae  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400175b5  nop     dword ptr [rax+rax+00h]
0x1400175ba  mov     [rdi], rax
0x1400175bd  test    rax, rax
0x1400175c0  jz      short loc_1400175DB
0x1400175c2  xor     eax, eax
0x1400175c4  mov     rbx, [rsp+38h+arg_0]
0x1400175c9  add     rsp, 30h
0x1400175cd  pop     rdi
0x1400175ce  retn
0x1400175d0  lea     rdx, [rbx+40h]
0x1400175d4  call    PplpLazyInitializeLookasideList
0x1400175d9  jmp     short loc_1400175AA
0x1400175db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175e2  lea     rbx, WPP_GLOBAL_Control
0x1400175e9  cmp     rcx, rbx
0x1400175ec  jz      short loc_1400175F4
0x1400175ee  cmp     byte ptr [rcx+29h], 2
0x1400175f2  jnb     short loc_140017646
0x1400175f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175fb  cmp     rcx, rbx
0x1400175fe  jz      short loc_140017633
0x140017600  cmp     byte ptr [rcx+29h], 2
0x140017604  jb      short loc_140017633
0x140017606  test    dword ptr [rcx+2Ch], 1000h
0x14001760d  jz      short loc_140017633
0x14001760f  mov     rcx, [rcx+18h]
0x140017613  lea     r9, aWfpallocatefro_0; "WfpAllocateFromPerProcessorLookasideLis"...
0x14001761a  mov     edx, 0Fh
0x14001761f  mov     [rsp+38h+var_18], 0C0000017h
0x140017627  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14001762e  call    WPP_SF_sd
0x140017633  mov     rbx, [rsp+38h+arg_0]
0x140017638  mov     rax, 0FFFFFFFFC0000017h
0x14001763f  add     rsp, 30h
0x140017643  pop     rdi
0x140017644  retn
0x140017646  test    dword ptr [rcx+2Ch], 1000h
0x14001764d  jz      short loc_1400175F4
0x14001764f  mov     rcx, [rcx+18h]
0x140017653  lea     r9, aWfpallocatefro_0; "WfpAllocateFromPerProcessorLookasideLis"...
0x14001765a  mov     edx, 0Ah
0x14001765f  mov     [rsp+38h+var_18], 0C0000017h
0x140017667  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14001766e  call    WPP_SF_sd
0x140017673  jmp     loc_1400175F4
```
