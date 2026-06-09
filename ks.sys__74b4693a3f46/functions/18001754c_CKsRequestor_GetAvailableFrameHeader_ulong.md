# CKsRequestor::GetAvailableFrameHeader(ulong)

- ea: `0x18001754c`
- end: `0x180017632`
- name: `?GetAvailableFrameHeader@CKsRequestor@@AEAAPEAU_KSPFRAME_HEADER@@K@Z`
- size: `230`
- prototype: `struct _KSPFRAME_HEADER *__fastcall(CKsRequestor *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017298`

## callees

- `0x18000b7bc`
- `0x18001754c`
- `0x180019fc0`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1800175ac`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1800175ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800175ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800175ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800175e8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800175e8`

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
0x18001754c  mov     [rsp+arg_0], rbx
0x180017551  mov     [rsp+arg_8], rsi
0x180017556  push    rdi
0x180017557  sub     rsp, 30h
0x18001755b  mov     edi, edx
0x18001755d  mov     rbx, rcx
0x180017560  lea     rax, WPP_RECORDER_INITIALIZED
0x180017567  xor     esi, esi
0x180017569  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180017570  jz      short loc_18001759E
0x180017572  mov     rcx, cs:WPP_GLOBAL_Control
0x180017579  cmp     [rcx+48h], si
0x18001757d  jz      short loc_18001759E
0x18001757f  mov     rcx, [rcx+40h]
0x180017583  lea     rax, WPP_01e97eabb7fe30ad0eb84e4d86b22be6_Traceguids
0x18001758a  lea     r9d, [rsi+2Dh]
0x18001758e  mov     [rsp+38h+var_18], rax
0x180017593  lea     r8d, [rsi+1]
0x180017597  mov     dl, 5
0x180017599  call    WPP_RECORDER_SF_
0x18001759e  lea     rdx, [rbx+0F8h]; Lock
0x1800175a5  lea     rcx, [rbx+0E8h]; ListHead
0x1800175ac  call    cs:__imp_ExInterlockedRemoveHeadList
0x1800175b3  nop     dword ptr [rax+rax+00h]
0x1800175b8  mov     rbx, rax
0x1800175bb  test    rax, rax
0x1800175be  jz      short loc_1800175D6
0x1800175c0  cmp     [rax+58h], edi
0x1800175c3  jnb     short loc_18001761E
0x1800175c5  xor     edx, edx; Tag
0x1800175c7  mov     rcx, rax; P
0x1800175ca  call    cs:__imp_ExFreePoolWithTag
0x1800175d1  nop     dword ptr [rax+rax+00h]
0x1800175d6  lea     rdx, [rdi+0B0h]; NumberOfBytes
0x1800175dd  mov     ecx, 200h; PoolType
0x1800175e2  mov     r8d, 68466350h; Tag
0x1800175e8  call    cs:__imp_ExAllocatePoolWithTag
0x1800175ef  nop     dword ptr [rax+rax+00h]
0x1800175f4  mov     rbx, rax
0x1800175f7  test    rax, rax
0x1800175fa  jz      short loc_18001761E
0x1800175fc  xor     edx, edx; Val
0x1800175fe  mov     r8d, 0B0h; Size
0x180017604  mov     rcx, rax; void *
0x180017607  call    memset
0x18001760c  test    edi, edi
0x18001760e  jz      short loc_18001761E
0x180017610  lea     rcx, [rbx+0B0h]
0x180017617  mov     [rbx+58h], edi
0x18001761a  mov     [rbx+40h], rcx
0x18001761e  mov     rsi, [rsp+38h+arg_8]
0x180017623  mov     rax, rbx
0x180017626  mov     rbx, [rsp+38h+arg_0]
0x18001762b  add     rsp, 30h
0x18001762f  pop     rdi
0x180017630  retn
```
