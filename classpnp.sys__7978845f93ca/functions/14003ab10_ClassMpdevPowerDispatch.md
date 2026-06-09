# ClassMpdevPowerDispatch

- ea: `0x14003ab10`
- end: `0x14003abbb`
- name: `ClassMpdevPowerDispatch`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14001fc38`
- `0x14003ab10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003ab6f`
- `ntoskrnl!IofCompleteRequest` at `0x14003ab6f`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14003ab82`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14003ab82`
- `ntoskrnl!PoCallDriver` at `0x14003aba3`
- `ntoskrnl!PoCallDriver` at `0x14003aba3`

## pseudocode

```c
NTSTATUS __fastcall ClassMpdevPowerDispatch(__int64 a1, IRP *a2)
{
  __int64 v2; // rdi

  v2 = *(_QWORD *)(a1 + 64);
  if ( *(_BYTE *)(v2 + 582) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, a1);
    }
    a2->IoStatus.Status = -1073741632;
    IofCompleteRequest(a2, 0);
    return -1073741632;
  }
  else
  {
    PoStartNextPowerIrp(a2);
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    return PoCallDriver(*(PDEVICE_OBJECT *)(v2 + 520), a2);
  }
}

```

## disassembly

```asm
0x14003ab10  mov     [rsp+arg_0], rbx
0x14003ab15  push    rdi
0x14003ab16  sub     rsp, 20h
0x14003ab1a  mov     rdi, [rcx+40h]
0x14003ab1e  mov     rbx, rdx
0x14003ab21  mov     r9, rcx
0x14003ab24  cmp     byte ptr [rdi+246h], 0
0x14003ab2b  jz      short loc_14003AB7F
0x14003ab2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab34  lea     rax, WPP_GLOBAL_Control
0x14003ab3b  cmp     rcx, rax
0x14003ab3e  jz      short loc_14003AB62
0x14003ab40  mov     eax, [rcx+2Ch]
0x14003ab43  test    al, 4
0x14003ab45  jz      short loc_14003AB62
0x14003ab47  cmp     byte ptr [rcx+29h], 3
0x14003ab4b  jb      short loc_14003AB62
0x14003ab4d  mov     rcx, [rcx+18h]
0x14003ab51  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003ab58  mov     edx, 0Ch
0x14003ab5d  call    WPP_SF_q
0x14003ab62  mov     edi, 0C00000C0h
0x14003ab67  xor     edx, edx; PriorityBoost
0x14003ab69  mov     rcx, rbx; Irp
0x14003ab6c  mov     [rbx+30h], edi
0x14003ab6f  call    cs:__imp_IofCompleteRequest
0x14003ab76  nop     dword ptr [rax+rax+00h]
0x14003ab7b  mov     eax, edi
0x14003ab7d  jmp     short loc_14003ABAF
0x14003ab7f  mov     rcx, rbx; Irp
0x14003ab82  call    cs:__imp_PoStartNextPowerIrp
0x14003ab89  nop     dword ptr [rax+rax+00h]
0x14003ab8e  inc     byte ptr [rbx+43h]
0x14003ab91  mov     rdx, rbx; Irp
0x14003ab94  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14003ab9c  mov     rcx, [rdi+208h]; DeviceObject
0x14003aba3  call    cs:__imp_PoCallDriver
0x14003abaa  nop     dword ptr [rax+rax+00h]
0x14003abaf  mov     rbx, [rsp+28h+arg_0]
0x14003abb4  add     rsp, 20h
0x14003abb8  pop     rdi
0x14003abb9  retn
```
