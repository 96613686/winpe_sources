# NdisWanCleanup

- ea: `0x14000bb00`
- end: `0x14000bbaf`
- name: `NdisWanCleanup`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140006d9c`
- `0x14000a290`
- `0x14000bb00`
- `0x14002e540`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000bb67`
- `ntoskrnl!IofCompleteRequest` at `0x14000bb67`

## pseudocode

```c
__int64 __fastcall NdisWanCleanup(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  _InterlockedDecrement(&dword_14001E290);
  ConnectionTableCleanUp();
  NdisWanResetProtocolInfoTable();
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14000bb00  mov     [rsp+arg_0], rbx
0x14000bb05  push    rdi
0x14000bb06  sub     rsp, 20h
0x14000bb0a  mov     rbx, rdx
0x14000bb0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb14  lea     rdi, WPP_GLOBAL_Control
0x14000bb1b  cmp     rcx, rdi
0x14000bb1e  jz      short loc_14000BB42
0x14000bb20  mov     eax, [rcx+2Ch]
0x14000bb23  test    al, 20h
0x14000bb25  jz      short loc_14000BB42
0x14000bb27  cmp     byte ptr [rcx+29h], 5
0x14000bb2b  jb      short loc_14000BB42
0x14000bb2d  mov     rcx, [rcx+18h]
0x14000bb31  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14000bb38  mov     edx, 0Ch
0x14000bb3d  call    WPP_SF_
0x14000bb42  lock dec cs:dword_14001E290
0x14000bb49  call    ConnectionTableCleanUp
0x14000bb4e  call    NdisWanResetProtocolInfoTable
0x14000bb53  xor     edx, edx; PriorityBoost
0x14000bb55  mov     qword ptr [rbx+38h], 0
0x14000bb5d  mov     rcx, rbx; Irp
0x14000bb60  mov     dword ptr [rbx+30h], 0
0x14000bb67  call    cs:__imp_IofCompleteRequest
0x14000bb6e  nop     dword ptr [rax+rax+00h]
0x14000bb73  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb7a  cmp     rcx, rdi
0x14000bb7d  jz      short loc_14000BBA1
0x14000bb7f  mov     eax, [rcx+2Ch]
0x14000bb82  test    al, 20h
0x14000bb84  jz      short loc_14000BBA1
0x14000bb86  cmp     byte ptr [rcx+29h], 5
0x14000bb8a  jb      short loc_14000BBA1
0x14000bb8c  mov     rcx, [rcx+18h]
0x14000bb90  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14000bb97  mov     edx, 0Dh
0x14000bb9c  call    WPP_SF_
0x14000bba1  mov     rbx, [rsp+28h+arg_0]
0x14000bba6  xor     eax, eax
0x14000bba8  add     rsp, 20h
0x14000bbac  pop     rdi
0x14000bbad  retn
```
