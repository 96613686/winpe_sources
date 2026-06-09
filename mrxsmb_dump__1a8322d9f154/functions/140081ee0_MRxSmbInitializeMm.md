# MRxSmbInitializeMm

- ea: `0x140081ee0`
- end: `0x140082158`
- name: `MRxSmbInitializeMm`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14007fd3c`

## callees

- `0x140039fa8`
- `0x14003b830`
- `0x140081ee0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140081f97`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140081fc4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140081ff1`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14008201e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14008204b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140081f97`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140081fc4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140081ff1`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14008201e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14008204b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140081ef6`
- `ntoskrnl!KeInitializeSpinLock` at `0x140081ef6`
- `ntoskrnl!ExAllocatePool2` at `0x140082098`
- `ntoskrnl!ExAllocatePool2` at `0x1400820fb`
- `ntoskrnl!ExAllocatePool2` at `0x140082098`
- `ntoskrnl!ExAllocatePool2` at `0x1400820fb`

## pseudocode

```c
__int64 MRxSmbInitializeMm()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 *v2; // rax
  int v3; // edx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  unsigned int v8; // ebx
  int Size; // [rsp+20h] [rbp-38h]
  int v10; // [rsp+38h] [rbp-20h]

  KeInitializeSpinLock(&SmbMmSpinLock);
  v0 = 0;
  v1 = 0;
  ObjectSizeInBytes = 0;
  xmmword_140070EB0 = 0;
  do
  {
    v2 = &SmbMmObjectsInUse[v1];
    ++v0;
    SmbMmObjectsInUse[v1 + 1] = (__int64)&SmbMmObjectsInUse[v1];
    v1 += 2;
    *v2 = (__int64)v2;
  }
  while ( v0 != 8 );
  *(_QWORD *)&ObjectSizeInBytes = 0x5D800000400LL;
  DWORD2(ObjectSizeInBytes) = 704;
  LODWORD(xmmword_140070EB0) = 640;
  DWORD2(xmmword_140070EB0) = 576;
  ExInitializeNPagedLookasideList(&SmbBufferLookasideList, 0, 0, 0x200u, 0x4000u, 0x6D536C42u, 1u);
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x9000u, 0x6D536C42u, 1u);
  ExInitializeNPagedLookasideList(&stru_140070740, 0, 0, 0x200u, 0x11000u, 0x6D536C42u, 1u);
  ExInitializeNPagedLookasideList(&stru_1400707C0, 0, 0, 0x200u, 0x101000u, 0x6D536C42u, 1u);
  ExInitializeNPagedLookasideList(&stru_140070840, 0, 0, 0x200u, 0x801000u, 0x6D536C42u, 1u);
  SmbMmExchangeLookasideList = (PVOID)PplCreateLookasideList(
                                        v4,
                                        v3,
                                        v5,
                                        v6,
                                        Size,
                                        0x1000u,
                                        0x6D536358u,
                                        v10,
                                        0x6D536358u);
  if ( !SmbMmExchangeLookasideList )
    return 3221225626LL;
  v8 = 0;
  GlobalTrashBuffer = (PVOID)ExAllocatePool2(66, 0x2000, 1834181204);
  if ( !GlobalTrashBuffer )
  {
    v8 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_e7b6edac773635936dfdf853ea49dd93_Traceguids);
    }
  }
  GlobalPaddingBuffer = (PVOID)ExAllocatePool2(64, 4096, 1834180944);
  if ( !GlobalPaddingBuffer )
  {
    v8 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_e7b6edac773635936dfdf853ea49dd93_Traceguids);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140081ee0  mov     [rsp+arg_0], rbx
0x140081ee5  mov     [rsp+arg_8], rsi
0x140081eea  push    rdi
0x140081eeb  sub     rsp, 50h
0x140081eef  lea     rcx, SmbMmSpinLock; SpinLock
0x140081ef6  call    cs:__imp_KeInitializeSpinLock
0x140081efd  nop     dword ptr [rax+rax+00h]
0x140081f02  xor     edx, edx
0x140081f04  lea     r8, SmbMmObjectsInUse
0x140081f0b  xorps   xmm0, xmm0
0x140081f0e  xor     ecx, ecx
0x140081f10  movups  cs:ObjectSizeInBytes, xmm0
0x140081f17  lea     esi, [rdx+1]
0x140081f1a  movups  cs:xmmword_140070EB0, xmm0
0x140081f21  lea     rax, [rcx+r8]
0x140081f25  add     rdx, rsi
0x140081f28  mov     [rcx+r8+8], rax
0x140081f2d  lea     rcx, [rcx+10h]
0x140081f31  mov     [rax], rax
0x140081f34  cmp     rdx, 8
0x140081f38  jnz     short loc_140081F21
0x140081f3a  mov     [rsp+58h+Depth], si; Depth
0x140081f3f  lea     rcx, SmbBufferLookasideList; Lookaside
0x140081f46  mov     edi, 6D536C42h
0x140081f4b  mov     dword ptr cs:ObjectSizeInBytes, 400h
0x140081f55  mov     ebx, 200h
0x140081f5a  mov     [rsp+58h+Tag], edi; Tag
0x140081f5e  mov     r9d, ebx; Flags
0x140081f61  mov     [rsp+58h+Size], 4000h; Size
0x140081f6a  xor     r8d, r8d; Free
0x140081f6d  mov     dword ptr cs:ObjectSizeInBytes+4, 5D8h
0x140081f77  xor     edx, edx; Allocate
0x140081f79  mov     dword ptr cs:ObjectSizeInBytes+8, 2C0h
0x140081f83  mov     dword ptr cs:xmmword_140070EB0, 280h
0x140081f8d  mov     dword ptr cs:xmmword_140070EB0+8, 240h
0x140081f97  call    cs:__imp_ExInitializeNPagedLookasideList
0x140081f9e  nop     dword ptr [rax+rax+00h]
0x140081fa3  mov     [rsp+58h+Depth], si; Depth
0x140081fa8  lea     rcx, Lookaside; Lookaside
0x140081faf  mov     [rsp+58h+Tag], edi; Tag
0x140081fb3  mov     r9d, ebx; Flags
0x140081fb6  xor     r8d, r8d; Free
0x140081fb9  mov     [rsp+58h+Size], 9000h; Size
0x140081fc2  xor     edx, edx; Allocate
0x140081fc4  call    cs:__imp_ExInitializeNPagedLookasideList
0x140081fcb  nop     dword ptr [rax+rax+00h]
0x140081fd0  mov     [rsp+58h+Depth], si; Depth
0x140081fd5  lea     rcx, stru_140070740; Lookaside
0x140081fdc  mov     [rsp+58h+Tag], edi; Tag
0x140081fe0  mov     r9d, ebx; Flags
0x140081fe3  xor     r8d, r8d; Free
0x140081fe6  mov     [rsp+58h+Size], 11000h; Size
0x140081fef  xor     edx, edx; Allocate
0x140081ff1  call    cs:__imp_ExInitializeNPagedLookasideList
0x140081ff8  nop     dword ptr [rax+rax+00h]
0x140081ffd  mov     [rsp+58h+Depth], si; Depth
0x140082002  lea     rcx, stru_1400707C0; Lookaside
0x140082009  mov     [rsp+58h+Tag], edi; Tag
0x14008200d  mov     r9d, ebx; Flags
0x140082010  xor     r8d, r8d; Free
0x140082013  mov     [rsp+58h+Size], 101000h; Size
0x14008201c  xor     edx, edx; Allocate
0x14008201e  call    cs:__imp_ExInitializeNPagedLookasideList
0x140082025  nop     dword ptr [rax+rax+00h]
0x14008202a  mov     [rsp+58h+Depth], si; Depth
0x14008202f  lea     rcx, stru_140070840; Lookaside
0x140082036  mov     [rsp+58h+Tag], edi; Tag
0x14008203a  mov     r9d, ebx; Flags
0x14008203d  xor     r8d, r8d; Free
0x140082040  mov     [rsp+58h+Size], 801000h; int
0x140082049  xor     edx, edx; Allocate
0x14008204b  call    cs:__imp_ExInitializeNPagedLookasideList
0x140082052  nop     dword ptr [rax+rax+00h]
0x140082057  mov     eax, 6D536358h
0x14008205c  mov     [rsp+58h+var_18], eax; ULONG
0x140082060  mov     dword ptr [rsp+58h+Depth], eax; ULONG
0x140082064  mov     qword ptr [rsp+58h+Tag], 1000h; SIZE_T
0x14008206d  call    PplCreateLookasideList
0x140082072  mov     cs:SmbMmExchangeLookasideList, rax
0x140082079  test    rax, rax
0x14008207c  jnz     short loc_140082088
0x14008207e  mov     eax, 0C000009Ah
0x140082083  jmp     loc_140082147
0x140082088  xor     ebx, ebx
0x14008208a  mov     edx, 2000h
0x14008208f  mov     r8d, 6D536254h
0x140082095  lea     ecx, [rbx+42h]
0x140082098  call    cs:__imp_ExAllocatePool2
0x14008209f  nop     dword ptr [rax+rax+00h]
0x1400820a4  mov     cs:GlobalTrashBuffer, rax
0x1400820ab  lea     rdi, WPP_GLOBAL_Control
0x1400820b2  test    rax, rax
0x1400820b5  jnz     short loc_1400820EB
0x1400820b7  mov     ebx, 0C000009Ah
0x1400820bc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400820c3  cmp     rcx, rdi
0x1400820c6  jz      short loc_1400820EB
0x1400820c8  mov     eax, [rcx+2Ch]
0x1400820cb  test    sil, al
0x1400820ce  jz      short loc_1400820EB
0x1400820d0  cmp     [rcx+29h], sil
0x1400820d4  jb      short loc_1400820EB
0x1400820d6  mov     rcx, [rcx+18h]
0x1400820da  lea     r8, WPP_e7b6edac773635936dfdf853ea49dd93_Traceguids
0x1400820e1  mov     edx, 10h
0x1400820e6  call    WPP_SF_
0x1400820eb  mov     edx, 1000h
0x1400820f0  mov     ecx, 40h ; '@'
0x1400820f5  mov     r8d, 6D536150h
0x1400820fb  call    cs:__imp_ExAllocatePool2
0x140082102  nop     dword ptr [rax+rax+00h]
0x140082107  mov     cs:GlobalPaddingBuffer, rax
0x14008210e  test    rax, rax
0x140082111  jnz     short loc_140082145
0x140082113  mov     ebx, 0C000009Ah
0x140082118  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008211f  cmp     rcx, rdi
0x140082122  jz      short loc_140082145
0x140082124  mov     edx, [rcx+2Ch]
0x140082127  test    sil, dl
0x14008212a  jz      short loc_140082145
0x14008212c  cmp     [rcx+29h], sil
0x140082130  jb      short loc_140082145
0x140082132  mov     rcx, [rcx+18h]
0x140082136  lea     edx, [rax+11h]
0x140082139  lea     r8, WPP_e7b6edac773635936dfdf853ea49dd93_Traceguids
0x140082140  call    WPP_SF_
0x140082145  mov     eax, ebx
0x140082147  mov     rbx, [rsp+58h+arg_0]
0x14008214c  mov     rsi, [rsp+58h+arg_8]
0x140082151  add     rsp, 50h
0x140082155  pop     rdi
0x140082156  retn
```
