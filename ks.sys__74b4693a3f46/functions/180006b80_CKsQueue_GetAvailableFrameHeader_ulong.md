# CKsQueue::GetAvailableFrameHeader(ulong)

- ea: `0x180006b80`
- end: `0x180006c30`
- name: `?GetAvailableFrameHeader@CKsQueue@@AEAAPEAU_KSPFRAME_HEADER@@K@Z`
- size: `176`
- prototype: `struct _KSPFRAME_HEADER *__fastcall(CKsQueue *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f170`

## callees

- `0x180006b80`
- `0x18000b7bc`
- `0x180019fc0`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180006bd8`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180006bd8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180006bf9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180006bf9`

## pseudocode

```c
struct _KSPFRAME_HEADER *__fastcall CKsQueue::GetAvailableFrameHeader(CKsQueue *this)
{
  struct _KSPFRAME_HEADER *result; // rax
  PVOID PoolWithTag; // rax
  PVOID v4; // rbx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      32,
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
  result = (struct _KSPFRAME_HEADER *)ExInterlockedRemoveHeadList(
                                        &this->m_FrameHeadersAvailable.ListEntry,
                                        &this->m_FrameHeadersAvailable.SpinLock);
  if ( !result )
  {
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0xB0u, 0x68466350u);
    v4 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported )
    {
      if ( PoolWithTag )
        memset(PoolWithTag, 0, 0xB0u);
    }
    return (struct _KSPFRAME_HEADER *)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180006b80  push    rbx
0x180006b82  sub     rsp, 30h
0x180006b86  mov     rbx, rcx
0x180006b89  lea     rax, WPP_RECORDER_INITIALIZED
0x180006b90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180006b97  jz      short loc_180006BCA
0x180006b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ba0  cmp     word ptr [rcx+48h], 0
0x180006ba5  jz      short loc_180006BCA
0x180006ba7  mov     rcx, [rcx+40h]
0x180006bab  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x180006bb2  mov     r9d, 20h ; ' '
0x180006bb8  mov     [rsp+38h+var_18], rax
0x180006bbd  mov     r8d, 1
0x180006bc3  mov     dl, 5
0x180006bc5  call    WPP_RECORDER_SF_
0x180006bca  lea     rdx, [rbx+158h]; Lock
0x180006bd1  lea     rcx, [rbx+148h]; ListHead
0x180006bd8  call    cs:__imp_ExInterlockedRemoveHeadList
0x180006bdf  nop     dword ptr [rax+rax+00h]
0x180006be4  test    rax, rax
0x180006be7  jnz     short loc_180006C29
0x180006be9  mov     edx, 0B0h; NumberOfBytes
0x180006bee  mov     r8d, 68466350h; Tag
0x180006bf4  mov     ecx, 600h; PoolType
0x180006bf9  call    cs:__imp_ExAllocatePoolWithTag
0x180006c00  nop     dword ptr [rax+rax+00h]
0x180006c05  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180006c0c  mov     rbx, rax
0x180006c0f  jnz     short loc_180006C26
0x180006c11  test    rax, rax
0x180006c14  jz      short loc_180006C26
0x180006c16  xor     edx, edx; Val
0x180006c18  mov     r8d, 0B0h; Size
0x180006c1e  mov     rcx, rax; void *
0x180006c21  call    memset
0x180006c26  mov     rax, rbx
0x180006c29  add     rsp, 30h
0x180006c2d  pop     rbx
0x180006c2e  retn
```
