# MouHid_SystemControl

- ea: `0x14000c250`
- end: `0x14000c2e7`
- name: `MouHid_SystemControl`
- size: `151`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c250`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000c2c8`
- `ntoskrnl!IofCompleteRequest` at `0x14000c2c8`
- `ntoskrnl!IofCallDriver` at `0x14000c2b3`
- `ntoskrnl!IofCallDriver` at `0x14000c2b3`
- `WMILIB!WmiSystemControl` at `0x14000c27f`
- `WMILIB!WmiSystemControl` at `0x14000c27f`

## pseudocode

```c
__int64 __fastcall MouHid_SystemControl(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rsi
  unsigned int v4; // edi
  int v6; // [rsp+30h] [rbp+8h] BYREF

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v6 = 0;
  v4 = WmiSystemControl((PWMILIB_CONTEXT)(DeviceExtension + 408), DeviceObject, Irp, (PSYSCTL_IRP_DISPOSITION)&v6);
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      IofCompleteRequest(Irp, 0);
    }
    else
    {
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      return (unsigned int)IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Irp);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14000c250  mov     rax, rsp
0x14000c253  mov     [rax+10h], rbx
0x14000c257  mov     [rax+18h], rsi
0x14000c25b  push    rdi
0x14000c25c  sub     rsp, 20h
0x14000c260  mov     rsi, [rcx+40h]
0x14000c264  lea     r9, [rax+8]; IrpDisposition
0x14000c268  mov     rbx, rdx
0x14000c26b  mov     dword ptr [rax+8], 0
0x14000c272  mov     rdx, rcx; DeviceObject
0x14000c275  mov     r8, rbx; Irp
0x14000c278  lea     rcx, [rsi+198h]; WmiLibInfo
0x14000c27f  call    cs:__imp_WmiSystemControl
0x14000c286  nop     dword ptr [rax+rax+00h]
0x14000c28b  mov     r8d, [rsp+28h+arg_0]
0x14000c290  mov     edi, eax
0x14000c292  test    r8d, r8d
0x14000c295  jz      short loc_14000C2D4
0x14000c297  sub     r8d, 1
0x14000c29b  jz      short loc_14000C2C3
0x14000c29d  inc     byte ptr [rbx+43h]
0x14000c2a0  sub     r8d, 1
0x14000c2a4  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14000c2ac  mov     rdx, rbx; Irp
0x14000c2af  mov     rcx, [rsi+8]; DeviceObject
0x14000c2b3  call    cs:__imp_IofCallDriver
0x14000c2ba  nop     dword ptr [rax+rax+00h]
0x14000c2bf  mov     edi, eax
0x14000c2c1  jmp     short loc_14000C2D4
0x14000c2c3  xor     edx, edx; PriorityBoost
0x14000c2c5  mov     rcx, rbx; Irp
0x14000c2c8  call    cs:__imp_IofCompleteRequest
0x14000c2cf  nop     dword ptr [rax+rax+00h]
0x14000c2d4  mov     rbx, [rsp+28h+arg_8]
0x14000c2d9  mov     eax, edi
0x14000c2db  mov     rsi, [rsp+28h+arg_10]
0x14000c2e0  add     rsp, 20h
0x14000c2e4  pop     rdi
0x14000c2e5  retn
```
