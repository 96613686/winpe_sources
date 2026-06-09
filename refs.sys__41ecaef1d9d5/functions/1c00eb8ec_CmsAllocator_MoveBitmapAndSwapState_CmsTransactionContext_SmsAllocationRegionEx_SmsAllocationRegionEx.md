# CmsAllocator::MoveBitmapAndSwapState(CmsTransactionContext *,SmsAllocationRegionEx &,SmsAllocationRegionEx &)

- ea: `0x1c00eb8ec`
- end: `0x1c00eb9e8`
- name: `?MoveBitmapAndSwapState@CmsAllocator@@QEAAXPEAVCmsTransactionContext@@AEAUSmsAllocationRegionEx@@1@Z`
- size: `252`
- prototype: `void __fastcall(CmsAllocator *__hidden this, struct CmsTransactionContext *, struct SmsAllocationRegionEx *, struct SmsAllocationRegionEx *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1c00da6c4`

## callees

- `0x1c0025620`
- `0x1c00ed1bc`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x1c00eb92e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00eb947`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00eb92e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00eb947`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00eb9b0`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00eb9b0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00eb95f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00eb95f`
- `ntoskrnl!RtlCopyBitMap` at `0x1c00eb978`
- `ntoskrnl!RtlCopyBitMap` at `0x1c00eb978`

## pseudocode

```c
void __fastcall CmsAllocator::MoveBitmapAndSwapState(
        CmsAllocator *this,
        struct CmsTransactionContext *a2,
        struct SmsAllocationRegionEx *a3,
        struct SmsAllocationRegionEx *a4)
{
  CmsVolume *v4; // rdi
  ULONG v6; // r8d
  ULONG *v9; // rdx
  struct CmsTransactionContext *v11; // rdx
  struct _RTL_BITMAP BitMapHeader; // [rsp+40h] [rbp-38h] BYREF
  struct _RTL_BITMAP v13; // [rsp+50h] [rbp-28h] BYREF

  v4 = (CmsVolume *)*((_QWORD *)this + 6);
  v6 = *((_DWORD *)a3 + 2);
  v9 = (ULONG *)*((_QWORD *)a3 + 6);
  v13 = 0;
  BitMapHeader = 0;
  RtlInitializeBitMap(&v13, v9, v6);
  RtlInitializeBitMap(&BitMapHeader, *((PULONG *)a4 + 6), *((_DWORD *)a4 + 2));
  ExAcquirePushLockSharedEx((char *)v4 + 3264, 0);
  RtlCopyBitMap(&v13, &BitMapHeader, 0);
  CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(v4, v11, this, a3, 0, 0, &BitMapHeader, 0);
  ExReleasePushLockEx((char *)v4 + 3264, 0);
  CmsAllocator::SwapBitmapRegionStates(this, a2, a3, a4);
}

```

## disassembly

```asm
0x1c00eb8ec  mov     rax, rsp
0x1c00eb8ef  mov     [rax+8], rbx
0x1c00eb8f3  mov     [rax+10h], rbp
0x1c00eb8f7  mov     [rax+18h], rsi
0x1c00eb8fb  push    rdi
0x1c00eb8fc  push    r14
0x1c00eb8fe  push    r15
0x1c00eb900  sub     rsp, 60h
0x1c00eb904  mov     rdi, [rcx+30h]
0x1c00eb908  mov     rbp, r8
0x1c00eb90b  mov     r8d, [r8+8]; SizeOfBitMap
0x1c00eb90f  mov     r14, rdx
0x1c00eb912  mov     r15, rcx
0x1c00eb915  xorps   xmm0, xmm0
0x1c00eb918  xorps   xmm1, xmm1
0x1c00eb91b  lea     rcx, [rax-28h]; BitMapHeader
0x1c00eb91f  mov     rdx, [rbp+30h]; BitMapBuffer
0x1c00eb923  mov     rsi, r9
0x1c00eb926  movups  xmmword ptr [rax-28h], xmm0
0x1c00eb92a  movups  xmmword ptr [rax-38h], xmm1
0x1c00eb92e  call    cs:__imp_RtlInitializeBitMap
0x1c00eb935  nop     dword ptr [rax+rax+00h]
0x1c00eb93a  mov     r8d, [rsi+8]; SizeOfBitMap
0x1c00eb93e  lea     rcx, [rsp+78h+BitMapHeader]; BitMapHeader
0x1c00eb943  mov     rdx, [rsi+30h]; BitMapBuffer
0x1c00eb947  call    cs:__imp_RtlInitializeBitMap
0x1c00eb94e  nop     dword ptr [rax+rax+00h]
0x1c00eb953  lea     rbx, [rdi+0CC0h]
0x1c00eb95a  xor     edx, edx
0x1c00eb95c  mov     rcx, rbx
0x1c00eb95f  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00eb966  nop     dword ptr [rax+rax+00h]
0x1c00eb96b  xor     r8d, r8d
0x1c00eb96e  lea     rdx, [rsp+78h+BitMapHeader]
0x1c00eb973  lea     rcx, [rsp+78h+var_28]
0x1c00eb978  call    cs:__imp_RtlCopyBitMap
0x1c00eb97f  nop     dword ptr [rax+rax+00h]
0x1c00eb984  xor     ecx, ecx
0x1c00eb986  lea     rax, [rsp+78h+BitMapHeader]
0x1c00eb98b  mov     [rsp+78h+var_40], cl; bool
0x1c00eb98f  mov     r9, rbp; struct _RANGE *
0x1c00eb992  mov     [rsp+78h+var_48], rax; struct _RTL_BITMAP *
0x1c00eb997  mov     r8, r15; struct CmsAllocator *
0x1c00eb99a  mov     [rsp+78h+var_50], rcx; bool *
0x1c00eb99f  mov     [rsp+78h+var_58], cl; bool
0x1c00eb9a3  mov     rcx, rdi; this
0x1c00eb9a6  call    ?MaskUnmaskRecentlyDeallocatedTrim@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAVCmsAllocator@@AEBU_RANGE@@_NPEA_NPEAU_RTL_BITMAP@@3@Z; CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(CmsTransactionContext *,CmsAllocator *,_RANGE const &,bool,bool *,_RTL_BITMAP *,bool)
0x1c00eb9ab  xor     edx, edx
0x1c00eb9ad  mov     rcx, rbx
0x1c00eb9b0  call    cs:__imp_ExReleasePushLockEx
0x1c00eb9b7  nop     dword ptr [rax+rax+00h]
0x1c00eb9bc  mov     r9, rsi; struct SmsAllocationRegionEx *
0x1c00eb9bf  mov     r8, rbp; struct SmsAllocationRegionEx *
0x1c00eb9c2  mov     rdx, r14; struct CmsTransactionContext *
0x1c00eb9c5  mov     rcx, r15; this
0x1c00eb9c8  call    ?SwapBitmapRegionStates@CmsAllocator@@QEAAXPEAVCmsTransactionContext@@AEAUSmsAllocationRegionEx@@1@Z; CmsAllocator::SwapBitmapRegionStates(CmsTransactionContext *,SmsAllocationRegionEx &,SmsAllocationRegionEx &)
0x1c00eb9cd  lea     r11, [rsp+78h+var_18]
0x1c00eb9d2  mov     rbx, [r11+20h]
0x1c00eb9d6  mov     rbp, [r11+28h]
0x1c00eb9da  mov     rsi, [r11+30h]
0x1c00eb9de  mov     rsp, r11
0x1c00eb9e1  pop     r15
0x1c00eb9e3  pop     r14
0x1c00eb9e5  pop     rdi
0x1c00eb9e6  retn
```
