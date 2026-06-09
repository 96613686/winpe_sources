# NatInitializeIcmpManagement

- ea: `0x14000918c`
- end: `0x140009274`
- name: `NatInitializeIcmpManagement`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140006f00`

## callees

- `0x14000218c`
- `0x14000918c`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140009233`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140009233`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400091ce`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400091ce`

## pseudocode

```c
void NatInitializeIcmpManagement()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
  }
  KeInitializeSpinLock(&IcmpMappingLock);
  qword_14003E4A8 = (__int64)&IcmpMappingList;
  IcmpMappingList = &IcmpMappingList;
  qword_14003E4B8 = (__int64)&qword_14003E4B0;
  qword_14003E4B0 = (__int64)&qword_14003E4B0;
  ExInitializeNPagedLookasideList(&IcmpLookasideList, NatAllocateFunction, 0, 0x200u, 0x40u, 0x4349614Eu, 0xAu);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
  }
}

```

## disassembly

```asm
0x14000918c  push    rbx
0x14000918e  sub     rsp, 40h
0x140009192  mov     rcx, cs:WPP_GLOBAL_Control
0x140009199  lea     rbx, WPP_GLOBAL_Control
0x1400091a0  cmp     rcx, rbx
0x1400091a3  jz      short loc_1400091C7
0x1400091a5  mov     eax, [rcx+2Ch]
0x1400091a8  test    al, 1
0x1400091aa  jz      short loc_1400091C7
0x1400091ac  cmp     byte ptr [rcx+29h], 6
0x1400091b0  jb      short loc_1400091C7
0x1400091b2  mov     rcx, [rcx+18h]
0x1400091b6  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x1400091bd  mov     edx, 1Dh
0x1400091c2  call    WPP_SF_
0x1400091c7  lea     rcx, IcmpMappingLock; SpinLock
0x1400091ce  call    cs:__imp_KeInitializeSpinLock
0x1400091d5  nop     dword ptr [rax+rax+00h]
0x1400091da  lea     rax, IcmpMappingList
0x1400091e1  mov     [rsp+48h+Depth], 0Ah; Depth
0x1400091e8  mov     cs:qword_14003E4A8, rax
0x1400091ef  lea     rdx, NatAllocateFunction; Allocate
0x1400091f6  mov     cs:IcmpMappingList, rax
0x1400091fd  lea     rcx, IcmpLookasideList; Lookaside
0x140009204  lea     rax, qword_14003E4B0
0x14000920b  mov     [rsp+48h+Tag], 4349614Eh; Tag
0x140009213  mov     r9d, 200h; Flags
0x140009219  mov     cs:qword_14003E4B8, rax
0x140009220  xor     r8d, r8d; Free
0x140009223  mov     cs:qword_14003E4B0, rax
0x14000922a  mov     [rsp+48h+Size], 40h ; '@'; Size
0x140009233  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000923a  nop     dword ptr [rax+rax+00h]
0x14000923f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009246  cmp     rcx, rbx
0x140009249  jz      short loc_14000926D
0x14000924b  mov     eax, [rcx+2Ch]
0x14000924e  test    al, 1
0x140009250  jz      short loc_14000926D
0x140009252  cmp     byte ptr [rcx+29h], 6
0x140009256  jb      short loc_14000926D
0x140009258  mov     rcx, [rcx+18h]
0x14000925c  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140009263  mov     edx, 1Eh
0x140009268  call    WPP_SF_
0x14000926d  add     rsp, 40h
0x140009271  pop     rbx
0x140009272  retn
```
