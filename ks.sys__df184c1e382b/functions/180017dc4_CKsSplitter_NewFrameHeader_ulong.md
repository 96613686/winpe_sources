# CKsSplitter::NewFrameHeader(ulong)

- ea: `0x180017dc4`
- end: `0x180017edd`
- name: `?NewFrameHeader@CKsSplitter@@AEAAPEAU_KSPPARENTFRAME_HEADER@@K@Z`
- size: `281`
- prototype: `struct _KSPPARENTFRAME_HEADER *__fastcall(CKsSplitter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017ef0`

## callees

- `0x18000b7bc`
- `0x180017dc4`
- `0x18001a000`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180017e1e`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180017e1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180017e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180017e3d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180017e66`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180017e66`

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
0x180017dc4  push    rbx
0x180017dc6  push    rbp
0x180017dc7  push    rsi
0x180017dc8  push    rdi
0x180017dc9  push    r14
0x180017dcb  push    r15
0x180017dcd  sub     rsp, 38h
0x180017dd1  mov     esi, edx
0x180017dd3  mov     rdi, rcx
0x180017dd6  lea     rax, WPP_RECORDER_INITIALIZED
0x180017ddd  xor     r15d, r15d
0x180017de0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180017de7  jz      short loc_180017E16
0x180017de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180017df0  cmp     [rcx+48h], r15w
0x180017df5  jz      short loc_180017E16
0x180017df7  mov     rcx, [rcx+40h]
0x180017dfb  lea     rax, WPP_08e49d3c55d235f0770001f41086c148_Traceguids
0x180017e02  lea     r9d, [r15+14h]
0x180017e06  mov     [rsp+68h+var_48], rax
0x180017e0b  lea     r8d, [r15+1]
0x180017e0f  mov     dl, 5
0x180017e11  call    WPP_RECORDER_SF_
0x180017e16  lea     rdx, [rdi+78h]; Lock
0x180017e1a  lea     rcx, [rdi+68h]; ListHead
0x180017e1e  call    cs:__imp_ExInterlockedRemoveHeadList
0x180017e25  nop     dword ptr [rax+rax+00h]
0x180017e2a  test    rax, rax
0x180017e2d  jz      short loc_180017E49
0x180017e2f  cmp     [rax+30h], esi
0x180017e32  jnb     loc_180017ECF
0x180017e38  xor     edx, edx; Tag
0x180017e3a  mov     rcx, rax; P
0x180017e3d  call    cs:__imp_ExFreePoolWithTag
0x180017e44  nop     dword ptr [rax+rax+00h]
0x180017e49  lea     ebp, [rsi+20h]
0x180017e4c  mov     r8d, 6866534Bh; Tag
0x180017e52  lea     eax, [rbp+10h]
0x180017e55  mov     ecx, 200h; PoolType
0x180017e5a  imul    eax, [rdi+54h]
0x180017e5e  add     eax, 38h ; '8'
0x180017e61  mov     edx, eax; NumberOfBytes
0x180017e63  mov     r14d, eax
0x180017e66  call    cs:__imp_ExAllocatePoolWithTag
0x180017e6d  nop     dword ptr [rax+rax+00h]
0x180017e72  mov     rbx, rax
0x180017e75  test    rax, rax
0x180017e78  jz      short loc_180017ECF
0x180017e7a  mov     r8, r14; Size
0x180017e7d  xor     edx, edx; Val
0x180017e7f  mov     rcx, rbx; void *
0x180017e82  call    memset
0x180017e87  mov     edx, ebp
0x180017e89  lea     rcx, [rbx+38h]
0x180017e8d  imul    edx, [rdi+54h]
0x180017e91  add     rdi, 58h ; 'X'
0x180017e95  mov     [rbx+30h], esi
0x180017e98  add     rdx, rcx
0x180017e9b  mov     [rbx+28h], rdx
0x180017e9f  mov     r8, [rdi]
0x180017ea2  cmp     r8, rdi
0x180017ea5  jz      short loc_180017ECC
0x180017ea7  mov     r9d, ebp
0x180017eaa  mov     rax, [r8-20h]
0x180017eae  mov     [rdx], rax
0x180017eb1  lea     rax, [rcx+20h]
0x180017eb5  mov     [rdx+8], rax
0x180017eb9  lea     rdx, [rdx+10h]
0x180017ebd  mov     [rcx+18h], rbx
0x180017ec1  add     rcx, r9
0x180017ec4  mov     r8, [r8]
0x180017ec7  cmp     r8, rdi
0x180017eca  jnz     short loc_180017EAA
0x180017ecc  mov     rax, rbx
0x180017ecf  add     rsp, 38h
0x180017ed3  pop     r15
0x180017ed5  pop     r14
0x180017ed7  pop     rdi
0x180017ed8  pop     rsi
0x180017ed9  pop     rbp
0x180017eda  pop     rbx
0x180017edb  retn
```
