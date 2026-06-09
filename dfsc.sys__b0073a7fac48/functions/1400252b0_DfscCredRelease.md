# DfscCredRelease

- ea: `0x1400252b0`
- end: `0x140025455`
- name: `DfscCredRelease`
- size: `421`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140012158`
- `0x140012668`
- `0x140017458`
- `0x14001f8a0`
- `0x140029160`

## callees

- `0x140002340`
- `0x1400025f4`
- `0x1400124c8`
- `0x1400252b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025444`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025444`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025438`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025438`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025383`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025383`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025371`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025371`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025328`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002534a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002541f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025328`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002534a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002541f`

## pseudocode

```c
__int64 __fastcall DfscCredRelease(ULONG_PTR BugCheckParameter3)
{
  struct _ERESOURCE *v1; // rdi
  unsigned int v2; // esi
  void *v4; // rcx
  void *v5; // rcx

  v1 = *(struct _ERESOURCE **)(BugCheckParameter3 + 24);
  v2 = 0;
  if ( v1 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(v1 + 1, 1u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids,
      BugCheckParameter3,
      *(_DWORD *)(BugCheckParameter3 + 4));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(BugCheckParameter3 + 4), 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids,
        BugCheckParameter3);
    }
    if ( v1 && *(_QWORD *)(BugCheckParameter3 + 24) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids,
          BugCheckParameter3);
      }
      DfscCredTableDelete(*(struct _RTL_AVL_TABLE **)(BugCheckParameter3 + 24), BugCheckParameter3);
    }
    v4 = *(void **)(BugCheckParameter3 + 16);
    if ( v4 )
    {
      ExFreePoolWithTag(v4, 0);
      *(_QWORD *)(BugCheckParameter3 + 16) = 0;
    }
    v5 = *(void **)(BugCheckParameter3 + 64);
    if ( v5 )
    {
      ExFreePoolWithTag(v5, 0);
      *(_QWORD *)(BugCheckParameter3 + 64) = 0;
    }
    ExFreePoolWithTag((PVOID)BugCheckParameter3, 0);
    v2 = 1;
  }
  if ( v1 )
  {
    ExReleaseResourceLite(v1 + 1);
    KeLeaveCriticalRegion();
  }
  return v2;
}

```

## disassembly

```asm
0x1400252b0  push    rbx
0x1400252b2  push    rsi
0x1400252b3  push    rdi
0x1400252b4  push    r14
0x1400252b6  sub     rsp, 38h
0x1400252ba  mov     rdi, [rcx+18h]
0x1400252be  xor     esi, esi
0x1400252c0  mov     rbx, rcx
0x1400252c3  test    rdi, rdi
0x1400252c6  jnz     loc_140025371
0x1400252cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400252d3  lea     r14, WPP_GLOBAL_Control
0x1400252da  cmp     rcx, r14
0x1400252dd  jz      short loc_1400252EC
0x1400252df  test    dword ptr [rcx+2Ch], 400000h
0x1400252e6  jnz     loc_140025394
0x1400252ec  mov     eax, 0FFFFFFFFh
0x1400252f1  lock xadd [rbx+4], eax
0x1400252f6  cmp     eax, 1
0x1400252f9  jnz     short loc_14002535B
0x1400252fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140025302  cmp     rcx, r14
0x140025305  jz      short loc_140025314
0x140025307  test    dword ptr [rcx+2Ch], 400000h
0x14002530e  jnz     loc_1400253B8
0x140025314  test    rdi, rdi
0x140025317  jnz     loc_1400253D5
0x14002531d  mov     rcx, [rbx+10h]; P
0x140025321  test    rcx, rcx
0x140025324  jz      short loc_140025338
0x140025326  xor     edx, edx; Tag
0x140025328  call    cs:__imp_ExFreePoolWithTag
0x14002532f  nop     dword ptr [rax+rax+00h]
0x140025334  mov     [rbx+10h], rsi
0x140025338  mov     rcx, [rbx+40h]; P
0x14002533c  test    rcx, rcx
0x14002533f  jnz     loc_14002541D
0x140025345  xor     edx, edx; Tag
0x140025347  mov     rcx, rbx; P
0x14002534a  call    cs:__imp_ExFreePoolWithTag
0x140025351  nop     dword ptr [rax+rax+00h]
0x140025356  mov     esi, 1
0x14002535b  test    rdi, rdi
0x14002535e  jnz     loc_140025434
0x140025364  mov     eax, esi
0x140025366  add     rsp, 38h
0x14002536a  pop     r14
0x14002536c  pop     rdi
0x14002536d  pop     rsi
0x14002536e  pop     rbx
0x14002536f  retn
0x140025371  call    cs:__imp_KeEnterCriticalRegion
0x140025378  nop     dword ptr [rax+rax+00h]
0x14002537d  lea     rcx, [rdi+68h]; Resource
0x140025381  mov     dl, 1; Wait
0x140025383  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002538a  nop     dword ptr [rax+rax+00h]
0x14002538f  jmp     loc_1400252CC
0x140025394  mov     eax, [rbx+4]
0x140025397  lea     r8, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids
0x14002539e  mov     rcx, [rcx+18h]
0x1400253a2  mov     edx, 10h
0x1400253a7  mov     r9, rbx
0x1400253aa  mov     [rsp+58h+var_38], eax
0x1400253ae  call    WPP_SF_qD
0x1400253b3  jmp     loc_1400252EC
0x1400253b8  mov     rcx, [rcx+18h]
0x1400253bc  lea     r8, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids
0x1400253c3  mov     edx, 11h
0x1400253c8  mov     r9, rbx
0x1400253cb  call    WPP_SF_q
0x1400253d0  jmp     loc_140025314
0x1400253d5  cmp     [rbx+18h], rsi
0x1400253d9  jz      loc_14002531D
0x1400253df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400253e6  cmp     rcx, r14
0x1400253e9  jz      short loc_14002540C
0x1400253eb  test    dword ptr [rcx+2Ch], 400000h
0x1400253f2  jz      short loc_14002540C
0x1400253f4  mov     rcx, [rcx+18h]
0x1400253f8  lea     r8, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids
0x1400253ff  mov     edx, 12h
0x140025404  mov     r9, rbx
0x140025407  call    WPP_SF_q
0x14002540c  mov     rcx, [rbx+18h]; BugCheckParameter2
0x140025410  mov     rdx, rbx; BugCheckParameter3
0x140025413  call    DfscCredTableDelete
0x140025418  jmp     loc_14002531D
0x14002541d  xor     edx, edx; Tag
0x14002541f  call    cs:__imp_ExFreePoolWithTag
0x140025426  nop     dword ptr [rax+rax+00h]
0x14002542b  mov     [rbx+40h], rsi
0x14002542f  jmp     loc_140025345
0x140025434  lea     rcx, [rdi+68h]; Resource
0x140025438  call    cs:__imp_ExReleaseResourceLite
0x14002543f  nop     dword ptr [rax+rax+00h]
0x140025444  call    cs:__imp_KeLeaveCriticalRegion
0x14002544b  nop     dword ptr [rax+rax+00h]
0x140025450  jmp     loc_140025364
```
