# PxIOCreate

- ea: `0x140004a40`
- end: `0x140004ac6`
- name: `PxIOCreate`
- size: `134`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140004a40`

## import_xrefs

- `ntoskrnl!MmLockPagableDataSection` at `0x140004a8a`
- `ntoskrnl!MmLockPagableDataSection` at `0x140004a8a`
- `ntoskrnl!IofCompleteRequest` at `0x140004ab1`
- `ntoskrnl!IofCompleteRequest` at `0x140004ab1`

## pseudocode

```c
__int64 __fastcall PxIOCreate(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, a2);
  if ( !g_fPagesLocked )
  {
    MmLockPagableDataSection(PxVcCleanup);
    g_fPagesLocked = 1;
  }
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140004a40  push    rbx
0x140004a42  sub     rsp, 20h
0x140004a46  mov     rbx, rdx
0x140004a49  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a50  lea     rax, WPP_GLOBAL_Control
0x140004a57  cmp     rcx, rax
0x140004a5a  jz      short loc_140004A7A
0x140004a5c  cmp     byte ptr [rcx+29h], 5
0x140004a60  jb      short loc_140004A7A
0x140004a62  mov     rcx, [rcx+18h]
0x140004a66  lea     r8, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x140004a6d  mov     edx, 0Dh
0x140004a72  mov     r9, rbx
0x140004a75  call    WPP_SF_q
0x140004a7a  cmp     cs:g_fPagesLocked, 0
0x140004a81  jnz     short loc_140004A9D
0x140004a83  lea     rcx, PxVcCleanup; AddressWithinSection
0x140004a8a  call    cs:__imp_MmLockPagableDataSection
0x140004a91  nop     dword ptr [rax+rax+00h]
0x140004a96  mov     cs:g_fPagesLocked, 1
0x140004a9d  xor     edx, edx; PriorityBoost
0x140004a9f  mov     dword ptr [rbx+30h], 0
0x140004aa6  mov     rcx, rbx; Irp
0x140004aa9  mov     qword ptr [rbx+38h], 0
0x140004ab1  call    cs:__imp_IofCompleteRequest
0x140004ab8  nop     dword ptr [rax+rax+00h]
0x140004abd  xor     eax, eax
0x140004abf  add     rsp, 20h
0x140004ac3  pop     rbx
0x140004ac4  retn
```
