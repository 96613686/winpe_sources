# ClassMpdevDeviceControl

- ea: `0x14003a630`
- end: `0x14003a6f6`
- name: `ClassMpdevDeviceControl`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14001fc38`
- `0x14003a630`
- `0x14003ae28`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003a6d0`
- `ntoskrnl!IofCompleteRequest` at `0x14003a6d0`

## pseudocode

```c
__int64 __fastcall ClassMpdevDeviceControl(__int64 a1, IRP *a2)
{
  unsigned int v3; // edi
  __int64 v4; // rcx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IRP *MasterIrp; // rdx

  v3 = 0;
  v4 = *(_QWORD *)(a1 + 64);
  if ( *(_BYTE *)(v4 + 582) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, a1);
    }
    v3 = -1073741632;
  }
  else
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 2953344 )
      return (unsigned int)ClasspMpdevDefaultDispatch(a1, a2);
    if ( CurrentStackLocation->Parameters.Read.Length < 0xC )
    {
      v3 = -1073741789;
    }
    else
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      *(_DWORD *)&MasterIrp->Type = *(_DWORD *)(*(_QWORD *)(v4 + 8) + 72LL);
      *(_DWORD *)(&MasterIrp->Size + 1) = -1;
      LODWORD(MasterIrp->MdlAddress) = 0;
    }
    a2->IoStatus.Information = 12;
  }
  a2->IoStatus.Status = v3;
  IofCompleteRequest(a2, 0);
  return v3;
}

```

## disassembly

```asm
0x14003a630  mov     [rsp+arg_0], rbx
0x14003a635  push    rdi
0x14003a636  sub     rsp, 20h
0x14003a63a  mov     r8, rcx
0x14003a63d  xor     edi, edi
0x14003a63f  mov     rcx, [rcx+40h]
0x14003a643  mov     rbx, rdx
0x14003a646  cmp     [rcx+246h], dil
0x14003a64d  jz      short loc_14003A68C
0x14003a64f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a656  lea     rax, WPP_GLOBAL_Control
0x14003a65d  cmp     rcx, rax
0x14003a660  jz      short loc_14003A685
0x14003a662  mov     eax, [rcx+2Ch]
0x14003a665  test    al, 10h
0x14003a667  jz      short loc_14003A685
0x14003a669  cmp     byte ptr [rcx+29h], 3
0x14003a66d  jb      short loc_14003A685
0x14003a66f  mov     rcx, [rcx+18h]
0x14003a673  lea     edx, [rdi+0Bh]
0x14003a676  mov     r9, r8
0x14003a679  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a680  call    WPP_SF_q
0x14003a685  mov     edi, 0C00000C0h
0x14003a68a  jmp     short loc_14003A6C8
0x14003a68c  mov     rax, [rdx+0B8h]
0x14003a693  cmp     dword ptr [rax+18h], 2D1080h
0x14003a69a  jnz     short loc_14003A6DE
0x14003a69c  cmp     dword ptr [rax+8], 0Ch
0x14003a6a0  jb      short loc_14003A6BB
0x14003a6a2  mov     rax, [rcx+8]
0x14003a6a6  mov     rdx, [rdx+18h]
0x14003a6aa  mov     ecx, [rax+48h]
0x14003a6ad  mov     [rdx], ecx
0x14003a6af  mov     dword ptr [rdx+4], 0FFFFFFFFh
0x14003a6b6  mov     [rdx+8], edi
0x14003a6b9  jmp     short loc_14003A6C0
0x14003a6bb  mov     edi, 0C0000023h
0x14003a6c0  mov     qword ptr [rbx+38h], 0Ch
0x14003a6c8  xor     edx, edx; PriorityBoost
0x14003a6ca  mov     [rbx+30h], edi
0x14003a6cd  mov     rcx, rbx; Irp
0x14003a6d0  call    cs:__imp_IofCompleteRequest
0x14003a6d7  nop     dword ptr [rax+rax+00h]
0x14003a6dc  jmp     short loc_14003A6E8
0x14003a6de  mov     rcx, r8
0x14003a6e1  call    ClasspMpdevDefaultDispatch
0x14003a6e6  mov     edi, eax
0x14003a6e8  mov     rbx, [rsp+28h+arg_0]
0x14003a6ed  mov     eax, edi
0x14003a6ef  add     rsp, 20h
0x14003a6f3  pop     rdi
0x14003a6f4  retn
```
