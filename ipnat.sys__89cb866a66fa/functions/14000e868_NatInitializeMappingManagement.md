# NatInitializeMappingManagement

- ea: `0x14000e868`
- end: `0x14000e981`
- name: `NatInitializeMappingManagement`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140006f00`

## callees

- `0x14000218c`
- `0x14000e868`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000e940`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000e940`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e8d3`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e8d3`

## pseudocode

```c
void NatInitializeMappingManagement()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  MappingCount = 0;
  qword_14003E2A8 = (__int64)&MappingList;
  MappingList = &MappingList;
  ExpiredMappingCount = 0;
  KeInitializeSpinLock(&MappingLock);
  MappingTree = 0;
  memset(MappingCache, 0, sizeof(MappingCache));
  memset(qword_1400382A0, 0, sizeof(qword_1400382A0));
  ExInitializeNPagedLookasideList(&MappingLookasideList, NatAllocateFunction, 0, 0x200u, 0x170u, 0x4D74614Eu, 0x14u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
}

```

## disassembly

```asm
0x14000e868  push    rdi
0x14000e86a  sub     rsp, 40h
0x14000e86e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e875  lea     rdi, WPP_GLOBAL_Control
0x14000e87c  cmp     rcx, rdi
0x14000e87f  jz      short loc_14000E8A3
0x14000e881  mov     eax, [rcx+2Ch]
0x14000e884  test    al, 1
0x14000e886  jz      short loc_14000E8A3
0x14000e888  cmp     byte ptr [rcx+29h], 6
0x14000e88c  jb      short loc_14000E8A3
0x14000e88e  mov     rcx, [rcx+18h]
0x14000e892  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000e899  mov     edx, 22h ; '"'
0x14000e89e  call    WPP_SF_
0x14000e8a3  lea     rax, MappingList
0x14000e8aa  mov     cs:MappingCount, 0
0x14000e8b4  lea     rcx, MappingLock; SpinLock
0x14000e8bb  mov     cs:qword_14003E2A8, rax
0x14000e8c2  mov     cs:MappingList, rax
0x14000e8c9  mov     cs:ExpiredMappingCount, 0
0x14000e8d3  call    cs:__imp_KeInitializeSpinLock
0x14000e8da  nop     dword ptr [rax+rax+00h]
0x14000e8df  mov     rcx, cs:off_14002F070; void *
0x14000e8e6  xorps   xmm0, xmm0
0x14000e8e9  xor     edx, edx; Val
0x14000e8eb  mov     r8d, 6000h; Size
0x14000e8f1  movups  cs:MappingTree, xmm0
0x14000e8f8  call    memset
0x14000e8fd  mov     rcx, cs:off_14002F088; void *
0x14000e904  xor     edx, edx; Val
0x14000e906  mov     r8d, 6000h; Size
0x14000e90c  call    memset
0x14000e911  mov     [rsp+48h+Depth], 14h; Depth
0x14000e918  lea     rdx, NatAllocateFunction; Allocate
0x14000e91f  mov     [rsp+48h+Tag], 4D74614Eh; Tag
0x14000e927  lea     rcx, MappingLookasideList; Lookaside
0x14000e92e  mov     r9d, 200h; Flags
0x14000e934  mov     [rsp+48h+Size], 170h; Size
0x14000e93d  xor     r8d, r8d; Free
0x14000e940  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000e947  nop     dword ptr [rax+rax+00h]
0x14000e94c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e953  cmp     rcx, rdi
0x14000e956  jz      short loc_14000E97A
0x14000e958  mov     eax, [rcx+2Ch]
0x14000e95b  test    al, 1
0x14000e95d  jz      short loc_14000E97A
0x14000e95f  cmp     byte ptr [rcx+29h], 6
0x14000e963  jb      short loc_14000E97A
0x14000e965  mov     rcx, [rcx+18h]
0x14000e969  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000e970  mov     edx, 23h ; '#'
0x14000e975  call    WPP_SF_
0x14000e97a  add     rsp, 40h
0x14000e97e  pop     rdi
0x14000e97f  retn
```
