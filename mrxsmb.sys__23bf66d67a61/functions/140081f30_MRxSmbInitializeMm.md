# MRxSmbInitializeMm

- ea: `0x140081f30`
- end: `0x1400821a8`
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
- `0x140081f30`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140081fe7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140082014`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140082041`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14008206e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14008209b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140081fe7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140082014`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140082041`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14008206e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14008209b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140081f46`
- `ntoskrnl!KeInitializeSpinLock` at `0x140081f46`
- `ntoskrnl!ExAllocatePool2` at `0x1400820e8`
- `ntoskrnl!ExAllocatePool2` at `0x14008214b`
- `ntoskrnl!ExAllocatePool2` at `0x1400820e8`
- `ntoskrnl!ExAllocatePool2` at `0x14008214b`

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
  xmmword_140070ED0 = 0;
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
  LODWORD(xmmword_140070ED0) = 640;
  DWORD2(xmmword_140070ED0) = 576;
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
0x140081f30  mov     [rsp+arg_0], rbx
0x140081f35  mov     [rsp+arg_8], rsi
0x140081f3a  push    rdi
0x140081f3b  sub     rsp, 50h
0x140081f3f  lea     rcx, SmbMmSpinLock; SpinLock
0x140081f46  call    cs:__imp_KeInitializeSpinLock
0x140081f4d  nop     dword ptr [rax+rax+00h]
0x140081f52  xor     edx, edx
0x140081f54  lea     r8, SmbMmObjectsInUse
0x140081f5b  xorps   xmm0, xmm0
0x140081f5e  xor     ecx, ecx
0x140081f60  movups  cs:ObjectSizeInBytes, xmm0
0x140081f67  lea     esi, [rdx+1]
0x140081f6a  movups  cs:xmmword_140070ED0, xmm0
0x140081f71  lea     rax, [rcx+r8]
0x140081f75  add     rdx, rsi
0x140081f78  mov     [rcx+r8+8], rax
0x140081f7d  lea     rcx, [rcx+10h]
0x140081f81  mov     [rax], rax
0x140081f84  cmp     rdx, 8
0x140081f88  jnz     short loc_140081F71
0x140081f8a  mov     [rsp+58h+Depth], si; Depth
0x140081f8f  lea     rcx, SmbBufferLookasideList; Lookaside
0x140081f96  mov     edi, 6D536C42h
0x140081f9b  mov     dword ptr cs:ObjectSizeInBytes, 400h
0x140081fa5  mov     ebx, 200h
0x140081faa  mov     [rsp+58h+Tag], edi; Tag
0x140081fae  mov     r9d, ebx; Flags
0x140081fb1  mov     [rsp+58h+Size], 4000h; Size
0x140081fba  xor     r8d, r8d; Free
0x140081fbd  mov     dword ptr cs:ObjectSizeInBytes+4, 5D8h
0x140081fc7  xor     edx, edx; Allocate
0x140081fc9  mov     dword ptr cs:ObjectSizeInBytes+8, 2C0h
0x140081fd3  mov     dword ptr cs:xmmword_140070ED0, 280h
0x140081fdd  mov     dword ptr cs:xmmword_140070ED0+8, 240h
0x140081fe7  call    cs:__imp_ExInitializeNPagedLookasideList
0x140081fee  nop     dword ptr [rax+rax+00h]
0x140081ff3  mov     [rsp+58h+Depth], si; Depth
0x140081ff8  lea     rcx, Lookaside; Lookaside
0x140081fff  mov     [rsp+58h+Tag], edi; Tag
0x140082003  mov     r9d, ebx; Flags
0x140082006  xor     r8d, r8d; Free
0x140082009  mov     [rsp+58h+Size], 9000h; Size
0x140082012  xor     edx, edx; Allocate
0x140082014  call    cs:__imp_ExInitializeNPagedLookasideList
0x14008201b  nop     dword ptr [rax+rax+00h]
0x140082020  mov     [rsp+58h+Depth], si; Depth
0x140082025  lea     rcx, stru_140070740; Lookaside
0x14008202c  mov     [rsp+58h+Tag], edi; Tag
0x140082030  mov     r9d, ebx; Flags
0x140082033  xor     r8d, r8d; Free
0x140082036  mov     [rsp+58h+Size], 11000h; Size
0x14008203f  xor     edx, edx; Allocate
0x140082041  call    cs:__imp_ExInitializeNPagedLookasideList
0x140082048  nop     dword ptr [rax+rax+00h]
0x14008204d  mov     [rsp+58h+Depth], si; Depth
0x140082052  lea     rcx, stru_1400707C0; Lookaside
0x140082059  mov     [rsp+58h+Tag], edi; Tag
0x14008205d  mov     r9d, ebx; Flags
0x140082060  xor     r8d, r8d; Free
0x140082063  mov     [rsp+58h+Size], 101000h; Size
0x14008206c  xor     edx, edx; Allocate
0x14008206e  call    cs:__imp_ExInitializeNPagedLookasideList
0x140082075  nop     dword ptr [rax+rax+00h]
0x14008207a  mov     [rsp+58h+Depth], si; Depth
0x14008207f  lea     rcx, stru_140070840; Lookaside
0x140082086  mov     [rsp+58h+Tag], edi; Tag
0x14008208a  mov     r9d, ebx; Flags
0x14008208d  xor     r8d, r8d; Free
0x140082090  mov     [rsp+58h+Size], 801000h; int
0x140082099  xor     edx, edx; Allocate
0x14008209b  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400820a2  nop     dword ptr [rax+rax+00h]
0x1400820a7  mov     eax, 6D536358h
0x1400820ac  mov     [rsp+58h+var_18], eax; ULONG
0x1400820b0  mov     dword ptr [rsp+58h+Depth], eax; ULONG
0x1400820b4  mov     qword ptr [rsp+58h+Tag], 1000h; SIZE_T
0x1400820bd  call    PplCreateLookasideList
0x1400820c2  mov     cs:SmbMmExchangeLookasideList, rax
0x1400820c9  test    rax, rax
0x1400820cc  jnz     short loc_1400820D8
0x1400820ce  mov     eax, 0C000009Ah
0x1400820d3  jmp     loc_140082197
0x1400820d8  xor     ebx, ebx
0x1400820da  mov     edx, 2000h
0x1400820df  mov     r8d, 6D536254h
0x1400820e5  lea     ecx, [rbx+42h]
0x1400820e8  call    cs:__imp_ExAllocatePool2
0x1400820ef  nop     dword ptr [rax+rax+00h]
0x1400820f4  mov     cs:GlobalTrashBuffer, rax
0x1400820fb  lea     rdi, WPP_GLOBAL_Control
0x140082102  test    rax, rax
0x140082105  jnz     short loc_14008213B
0x140082107  mov     ebx, 0C000009Ah
0x14008210c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140082113  cmp     rcx, rdi
0x140082116  jz      short loc_14008213B
0x140082118  mov     eax, [rcx+2Ch]
0x14008211b  test    sil, al
0x14008211e  jz      short loc_14008213B
0x140082120  cmp     [rcx+29h], sil
0x140082124  jb      short loc_14008213B
0x140082126  mov     rcx, [rcx+18h]
0x14008212a  lea     r8, WPP_e7b6edac773635936dfdf853ea49dd93_Traceguids
0x140082131  mov     edx, 10h
0x140082136  call    WPP_SF_
0x14008213b  mov     edx, 1000h
0x140082140  mov     ecx, 40h ; '@'
0x140082145  mov     r8d, 6D536150h
0x14008214b  call    cs:__imp_ExAllocatePool2
0x140082152  nop     dword ptr [rax+rax+00h]
0x140082157  mov     cs:GlobalPaddingBuffer, rax
0x14008215e  test    rax, rax
0x140082161  jnz     short loc_140082195
0x140082163  mov     ebx, 0C000009Ah
0x140082168  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008216f  cmp     rcx, rdi
0x140082172  jz      short loc_140082195
0x140082174  mov     edx, [rcx+2Ch]
0x140082177  test    sil, dl
0x14008217a  jz      short loc_140082195
0x14008217c  cmp     [rcx+29h], sil
0x140082180  jb      short loc_140082195
0x140082182  mov     rcx, [rcx+18h]
0x140082186  lea     edx, [rax+11h]
0x140082189  lea     r8, WPP_e7b6edac773635936dfdf853ea49dd93_Traceguids
0x140082190  call    WPP_SF_
0x140082195  mov     eax, ebx
0x140082197  mov     rbx, [rsp+58h+arg_0]
0x14008219c  mov     rsi, [rsp+58h+arg_8]
0x1400821a1  add     rsp, 50h
0x1400821a5  pop     rdi
0x1400821a6  retn
```
