# CKsSplitter::NewFrameHeader(ulong)

- ea: `0x180017d74`
- end: `0x180017e8d`
- name: `?NewFrameHeader@CKsSplitter@@AEAAPEAU_KSPPARENTFRAME_HEADER@@K@Z`
- size: `281`
- prototype: `struct _KSPPARENTFRAME_HEADER *__fastcall(CKsSplitter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017ea0`

## callees

- `0x18000b7bc`
- `0x180017d74`
- `0x180019fc0`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180017dce`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180017dce`
- `ntoskrnl!ExFreePoolWithTag` at `0x180017ded`
- `ntoskrnl!ExFreePoolWithTag` at `0x180017ded`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180017e16`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180017e16`

## pseudocode

```c
struct _KSPPARENTFRAME_HEADER *__fastcall CKsSplitter::NewFrameHeader(CKsSplitter *this, unsigned int a2)
{
  unsigned int v2; // esi
  struct _KSPPARENTFRAME_HEADER *result; // rax
  unsigned int v5; // ebp
  SIZE_T v6; // r14
  struct _KSPPARENTFRAME_HEADER *v7; // rbx
  struct _KSPPARENTFRAME_HEADER *v8; // rcx
  __int64 v9; // rdx
  _LIST_ENTRY *p_m_BranchList; // rdi
  _KSSPLITPIN *v11; // rdx
  _LIST_ENTRY *i; // r8

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      20,
      (__int64)WPP_08e49d3c55d235f0770001f41086c148_Traceguids);
  }
  result = (struct _KSPPARENTFRAME_HEADER *)ExInterlockedRemoveHeadList(
                                              &this->m_FrameHeadersAvailable.ListEntry,
                                              &this->m_FrameHeadersAvailable.SpinLock);
  if ( result )
  {
    if ( result->StreamHeaderSize >= v2 )
      return result;
    ExFreePoolWithTag(result, 0);
  }
  v5 = v2 + 32;
  v6 = this->m_BranchCount * (v2 + 48) + 56;
  result = (struct _KSPPARENTFRAME_HEADER *)ExAllocatePoolWithTag(NonPagedPoolNx, v6, 0x6866534Bu);
  v7 = result;
  if ( result )
  {
    memset(result, 0, v6);
    v8 = v7 + 1;
    v9 = this->m_BranchCount * v5;
    p_m_BranchList = &this->m_BranchList;
    v7->StreamHeaderSize = v2;
    v11 = (_KSSPLITPIN *)((char *)&v7[1] + v9);
    v7->SplitPins = v11;
    for ( i = p_m_BranchList->Flink; i != p_m_BranchList; i = i->Flink )
    {
      v11->Pin = (_KSPIN *)i[-2].Flink;
      v11->StreamHeader = (KSSTREAM_HEADER *)&v8->Data;
      ++v11;
      v8->StreamHeader = (KSSTREAM_HEADER *)v7;
      v8 = (struct _KSPPARENTFRAME_HEADER *)((char *)v8 + v5);
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180017d74  push    rbx
0x180017d76  push    rbp
0x180017d77  push    rsi
0x180017d78  push    rdi
0x180017d79  push    r14
0x180017d7b  push    r15
0x180017d7d  sub     rsp, 38h
0x180017d81  mov     esi, edx
0x180017d83  mov     rdi, rcx
0x180017d86  lea     rax, WPP_RECORDER_INITIALIZED
0x180017d8d  xor     r15d, r15d
0x180017d90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180017d97  jz      short loc_180017DC6
0x180017d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180017da0  cmp     [rcx+48h], r15w
0x180017da5  jz      short loc_180017DC6
0x180017da7  mov     rcx, [rcx+40h]
0x180017dab  lea     rax, WPP_08e49d3c55d235f0770001f41086c148_Traceguids
0x180017db2  lea     r9d, [r15+14h]
0x180017db6  mov     [rsp+68h+var_48], rax
0x180017dbb  lea     r8d, [r15+1]
0x180017dbf  mov     dl, 5
0x180017dc1  call    WPP_RECORDER_SF_
0x180017dc6  lea     rdx, [rdi+78h]; Lock
0x180017dca  lea     rcx, [rdi+68h]; ListHead
0x180017dce  call    cs:__imp_ExInterlockedRemoveHeadList
0x180017dd5  nop     dword ptr [rax+rax+00h]
0x180017dda  test    rax, rax
0x180017ddd  jz      short loc_180017DF9
0x180017ddf  cmp     [rax+30h], esi
0x180017de2  jnb     loc_180017E7F
0x180017de8  xor     edx, edx; Tag
0x180017dea  mov     rcx, rax; P
0x180017ded  call    cs:__imp_ExFreePoolWithTag
0x180017df4  nop     dword ptr [rax+rax+00h]
0x180017df9  lea     ebp, [rsi+20h]
0x180017dfc  mov     r8d, 6866534Bh; Tag
0x180017e02  lea     eax, [rbp+10h]
0x180017e05  mov     ecx, 200h; PoolType
0x180017e0a  imul    eax, [rdi+54h]
0x180017e0e  add     eax, 38h ; '8'
0x180017e11  mov     edx, eax; NumberOfBytes
0x180017e13  mov     r14d, eax
0x180017e16  call    cs:__imp_ExAllocatePoolWithTag
0x180017e1d  nop     dword ptr [rax+rax+00h]
0x180017e22  mov     rbx, rax
0x180017e25  test    rax, rax
0x180017e28  jz      short loc_180017E7F
0x180017e2a  mov     r8, r14; Size
0x180017e2d  xor     edx, edx; Val
0x180017e2f  mov     rcx, rbx; void *
0x180017e32  call    memset
0x180017e37  mov     edx, ebp
0x180017e39  lea     rcx, [rbx+38h]
0x180017e3d  imul    edx, [rdi+54h]
0x180017e41  add     rdi, 58h ; 'X'
0x180017e45  mov     [rbx+30h], esi
0x180017e48  add     rdx, rcx
0x180017e4b  mov     [rbx+28h], rdx
0x180017e4f  mov     r8, [rdi]
0x180017e52  cmp     r8, rdi
0x180017e55  jz      short loc_180017E7C
0x180017e57  mov     r9d, ebp
0x180017e5a  mov     rax, [r8-20h]
0x180017e5e  mov     [rdx], rax
0x180017e61  lea     rax, [rcx+20h]
0x180017e65  mov     [rdx+8], rax
0x180017e69  lea     rdx, [rdx+10h]
0x180017e6d  mov     [rcx+18h], rbx
0x180017e71  add     rcx, r9
0x180017e74  mov     r8, [r8]
0x180017e77  cmp     r8, rdi
0x180017e7a  jnz     short loc_180017E5A
0x180017e7c  mov     rax, rbx
0x180017e7f  add     rsp, 38h
0x180017e83  pop     r15
0x180017e85  pop     r14
0x180017e87  pop     rdi
0x180017e88  pop     rsi
0x180017e89  pop     rbp
0x180017e8a  pop     rbx
0x180017e8b  retn
```
