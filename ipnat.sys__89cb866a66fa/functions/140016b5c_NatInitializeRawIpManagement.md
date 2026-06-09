# NatInitializeRawIpManagement

- ea: `0x140016b5c`
- end: `0x140016c44`
- name: `NatInitializeRawIpManagement`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140006f00`

## callees

- `0x14000218c`
- `0x140016b5c`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140016c03`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140016c03`
- `ntoskrnl!KeInitializeSpinLock` at `0x140016b9e`
- `ntoskrnl!KeInitializeSpinLock` at `0x140016b9e`

## pseudocode

```c
void NatInitializeRawIpManagement()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_1f8b4279a5713c8ad951a68c72f6413f_Traceguids);
  }
  KeInitializeSpinLock(&IpMappingLock);
  qword_140032088 = (__int64)&IpMappingList;
  IpMappingList = &IpMappingList;
  qword_140032098 = (__int64)&qword_140032090;
  qword_140032090 = (__int64)&qword_140032090;
  ExInitializeNPagedLookasideList(&IpLookasideList, NatAllocateFunction, 0, 0x200u, 0x40u, 0x5049614Eu, 0xAu);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_1f8b4279a5713c8ad951a68c72f6413f_Traceguids);
  }
}

```

## disassembly

```asm
0x140016b5c  push    rbx
0x140016b5e  sub     rsp, 40h
0x140016b62  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b69  lea     rbx, WPP_GLOBAL_Control
0x140016b70  cmp     rcx, rbx
0x140016b73  jz      short loc_140016B97
0x140016b75  mov     eax, [rcx+2Ch]
0x140016b78  test    al, 1
0x140016b7a  jz      short loc_140016B97
0x140016b7c  cmp     byte ptr [rcx+29h], 6
0x140016b80  jb      short loc_140016B97
0x140016b82  mov     rcx, [rcx+18h]
0x140016b86  lea     r8, WPP_1f8b4279a5713c8ad951a68c72f6413f_Traceguids
0x140016b8d  mov     edx, 14h
0x140016b92  call    WPP_SF_
0x140016b97  lea     rcx, IpMappingLock; SpinLock
0x140016b9e  call    cs:__imp_KeInitializeSpinLock
0x140016ba5  nop     dword ptr [rax+rax+00h]
0x140016baa  lea     rax, IpMappingList
0x140016bb1  mov     [rsp+48h+Depth], 0Ah; Depth
0x140016bb8  mov     cs:qword_140032088, rax
0x140016bbf  lea     rdx, NatAllocateFunction; Allocate
0x140016bc6  mov     cs:IpMappingList, rax
0x140016bcd  lea     rcx, IpLookasideList; Lookaside
0x140016bd4  lea     rax, qword_140032090
0x140016bdb  mov     [rsp+48h+Tag], 5049614Eh; Tag
0x140016be3  mov     r9d, 200h; Flags
0x140016be9  mov     cs:qword_140032098, rax
0x140016bf0  xor     r8d, r8d; Free
0x140016bf3  mov     cs:qword_140032090, rax
0x140016bfa  mov     [rsp+48h+Size], 40h ; '@'; Size
0x140016c03  call    cs:__imp_ExInitializeNPagedLookasideList
0x140016c0a  nop     dword ptr [rax+rax+00h]
0x140016c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c16  cmp     rcx, rbx
0x140016c19  jz      short loc_140016C3D
0x140016c1b  mov     eax, [rcx+2Ch]
0x140016c1e  test    al, 1
0x140016c20  jz      short loc_140016C3D
0x140016c22  cmp     byte ptr [rcx+29h], 6
0x140016c26  jb      short loc_140016C3D
0x140016c28  mov     rcx, [rcx+18h]
0x140016c2c  lea     r8, WPP_1f8b4279a5713c8ad951a68c72f6413f_Traceguids
0x140016c33  mov     edx, 15h
0x140016c38  call    WPP_SF_
0x140016c3d  add     rsp, 40h
0x140016c41  pop     rbx
0x140016c42  retn
```
