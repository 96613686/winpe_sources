# CKsRequestor::GetAvailableFrameHeader(ulong)

- ea: `0x18001759c`
- end: `0x180017682`
- name: `?GetAvailableFrameHeader@CKsRequestor@@AEAAPEAU_KSPFRAME_HEADER@@K@Z`
- size: `230`
- prototype: `struct _KSPFRAME_HEADER *__fastcall(CKsRequestor *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800172e8`

## callees

- `0x18000b7bc`
- `0x18001759c`
- `0x18001a000`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1800175fc`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1800175fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001761a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001761a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180017638`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180017638`

## pseudocode

```c
struct _KSPFRAME_HEADER *__fastcall CKsRequestor::GetAvailableFrameHeader(CKsRequestor *this, unsigned int a2)
{
  __int64 v2; // rdi
  PLIST_ENTRY v4; // rax
  PLIST_ENTRY v5; // rbx
  struct _LIST_ENTRY *PoolWithTag; // rax

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      45,
      (__int64)WPP_01e97eabb7fe30ad0eb84e4d86b22be6_Traceguids);
  }
  v4 = ExInterlockedRemoveHeadList(&this->m_FrameHeadersAvailable.ListEntry, &this->m_FrameHeadersAvailable.SpinLock);
  v5 = v4;
  if ( v4 )
  {
    if ( LODWORD(v4[5].Blink) >= (unsigned int)v2 )
      return (struct _KSPFRAME_HEADER *)v5;
    ExFreePoolWithTag(v4, 0);
  }
  PoolWithTag = (struct _LIST_ENTRY *)ExAllocatePoolWithTag(NonPagedPoolNx, v2 + 176, 0x68466350u);
  v5 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, 0xB0u);
    if ( (_DWORD)v2 )
    {
      LODWORD(v5[5].Blink) = v2;
      v5[4].Flink = v5 + 11;
    }
  }
  return (struct _KSPFRAME_HEADER *)v5;
}

```

## disassembly

```asm
0x18001759c  mov     [rsp+arg_0], rbx
0x1800175a1  mov     [rsp+arg_8], rsi
0x1800175a6  push    rdi
0x1800175a7  sub     rsp, 30h
0x1800175ab  mov     edi, edx
0x1800175ad  mov     rbx, rcx
0x1800175b0  lea     rax, WPP_RECORDER_INITIALIZED
0x1800175b7  xor     esi, esi
0x1800175b9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800175c0  jz      short loc_1800175EE
0x1800175c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175c9  cmp     [rcx+48h], si
0x1800175cd  jz      short loc_1800175EE
0x1800175cf  mov     rcx, [rcx+40h]
0x1800175d3  lea     rax, WPP_01e97eabb7fe30ad0eb84e4d86b22be6_Traceguids
0x1800175da  lea     r9d, [rsi+2Dh]
0x1800175de  mov     [rsp+38h+var_18], rax
0x1800175e3  lea     r8d, [rsi+1]
0x1800175e7  mov     dl, 5
0x1800175e9  call    WPP_RECORDER_SF_
0x1800175ee  lea     rdx, [rbx+0F8h]; Lock
0x1800175f5  lea     rcx, [rbx+0E8h]; ListHead
0x1800175fc  call    cs:__imp_ExInterlockedRemoveHeadList
0x180017603  nop     dword ptr [rax+rax+00h]
0x180017608  mov     rbx, rax
0x18001760b  test    rax, rax
0x18001760e  jz      short loc_180017626
0x180017610  cmp     [rax+58h], edi
0x180017613  jnb     short loc_18001766E
0x180017615  xor     edx, edx; Tag
0x180017617  mov     rcx, rax; P
0x18001761a  call    cs:__imp_ExFreePoolWithTag
0x180017621  nop     dword ptr [rax+rax+00h]
0x180017626  lea     rdx, [rdi+0B0h]; NumberOfBytes
0x18001762d  mov     ecx, 200h; PoolType
0x180017632  mov     r8d, 68466350h; Tag
0x180017638  call    cs:__imp_ExAllocatePoolWithTag
0x18001763f  nop     dword ptr [rax+rax+00h]
0x180017644  mov     rbx, rax
0x180017647  test    rax, rax
0x18001764a  jz      short loc_18001766E
0x18001764c  xor     edx, edx; Val
0x18001764e  mov     r8d, 0B0h; Size
0x180017654  mov     rcx, rax; void *
0x180017657  call    memset
0x18001765c  test    edi, edi
0x18001765e  jz      short loc_18001766E
0x180017660  lea     rcx, [rbx+0B0h]
0x180017667  mov     [rbx+58h], edi
0x18001766a  mov     [rbx+40h], rcx
0x18001766e  mov     rsi, [rsp+38h+arg_8]
0x180017673  mov     rax, rbx
0x180017676  mov     rbx, [rsp+38h+arg_0]
0x18001767b  add     rsp, 30h
0x18001767f  pop     rdi
0x180017680  retn
```
