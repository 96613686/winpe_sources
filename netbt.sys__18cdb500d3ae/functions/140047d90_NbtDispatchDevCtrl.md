# NbtDispatchDevCtrl

- ea: `0x140047d90`
- end: `0x140047f19`
- name: `NbtDispatchDevCtrl`
- size: `393`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400062b0`
- `0x140006900`
- `0x14000dc40`
- `0x1400148a0`
- `0x1400400a4`
- `0x140040214`
- `0x14004025c`
- `0x140047d90`
- `0x140047f20`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140047e93`
- `ntoskrnl!IofCompleteRequest` at `0x140047e93`
- `TDI!TdiMapUserRequest` at `0x140047df1`
- `TDI!TdiMapUserRequest` at `0x140047df1`

## pseudocode

```c
__int64 __fastcall NbtDispatchDevCtrl(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  DWORD LowPart; // r14d
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int v8; // ebp
  _QWORD *p_NamedPipeType; // r9

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( (unsigned __int8)NBT_REFERENCE_DEVICE(DeviceObject, 0, 0) )
  {
    Irp->IoStatus.Status = 259;
    Irp->IoStatus.Information = 0;
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    if ( (xmmword_140038420 & 4) != 0 )
      WPP_SF_d(1026, 24, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, LowPart);
    if ( TdiMapUserRequest(DeviceObject, Irp, CurrentStackLocation) )
    {
      if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 2163203 )
      {
        p_NamedPipeType = &CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
        v8 = -1073741823;
        if ( p_NamedPipeType )
        {
          if ( Irp->RequestorMode )
          {
            v8 = -1073741790;
          }
          else
          {
            v8 = 0;
            *p_NamedPipeType = NTSend;
          }
        }
        if ( (xmmword_140038420 & 4) != 0 )
          WPP_SF_q(1026, 25, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, p_NamedPipeType);
        ReturnIrp(Irp);
        goto LABEL_8;
      }
      v7 = DispatchIoctls(DeviceObject, Irp, (__int64)CurrentStackLocation, v6);
    }
    else
    {
      v7 = NbtDispatchInternalCtrl((__int64)DeviceObject, (__int64)Irp);
    }
    v8 = v7;
LABEL_8:
    if ( LowPart != 2212024 )
      NBT_DEREFERENCE_DEVICE(DeviceObject, 0);
    return v8;
  }
  if ( (xmmword_140038420 & 4) != 0 )
    WPP_SF_qD(
      1026,
      23,
      WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids,
      DeviceObject,
      CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
  Irp->IoStatus.Status = -1073741436;
  IofCompleteRequest(Irp, 2);
  return 3221225860LL;
}

```

## disassembly

```asm
0x140047d90  mov     [rsp+arg_10], rbx
0x140047d95  mov     [rsp+arg_18], rsi
0x140047d9a  push    rdi
0x140047d9b  sub     rsp, 30h
0x140047d9f  mov     rsi, [rdx+0B8h]
0x140047da6  mov     rbx, rdx
0x140047da9  xor     edx, edx
0x140047dab  xor     r8d, r8d
0x140047dae  mov     rdi, rcx
0x140047db1  call    NBT_REFERENCE_DEVICE
0x140047db6  test    al, al
0x140047db8  jz      loc_140047E5E
0x140047dbe  mov     [rsp+38h+arg_0], rbp
0x140047dc3  mov     [rsp+38h+arg_8], r14
0x140047dc8  mov     dword ptr [rbx+30h], 103h
0x140047dcf  mov     qword ptr [rbx+38h], 0
0x140047dd7  mov     r14d, [rsi+18h]
0x140047ddb  test    byte ptr cs:xmmword_140038420, 4
0x140047de2  jnz     loc_140047EA6
0x140047de8  mov     r8, rsi; IrpSp
0x140047deb  mov     rdx, rbx; Irp
0x140047dee  mov     rcx, rdi; DeviceObject
0x140047df1  call    cs:__imp_TdiMapUserRequest
0x140047df8  nop     dword ptr [rax+rax+00h]
0x140047dfd  test    eax, eax
0x140047dff  jz      short loc_140047E51
0x140047e01  cmp     dword ptr [rsi+18h], 210203h
0x140047e08  jz      loc_140047EC4
0x140047e0e  mov     r8, rsi
0x140047e11  mov     rdx, rbx; Irp
0x140047e14  mov     rcx, rdi; DeviceObject
0x140047e17  call    DispatchIoctls
0x140047e1c  mov     ebp, eax
0x140047e1e  cmp     r14d, 21C0B8h
0x140047e25  mov     r14, [rsp+38h+arg_8]
0x140047e2a  jz      short loc_140047E39
0x140047e2c  xor     r8d, r8d
0x140047e2f  xor     edx, edx
0x140047e31  mov     rcx, rdi
0x140047e34  call    NBT_DEREFERENCE_DEVICE
0x140047e39  mov     eax, ebp
0x140047e3b  mov     rbp, [rsp+38h+arg_0]
0x140047e40  mov     rbx, [rsp+38h+arg_10]
0x140047e45  mov     rsi, [rsp+38h+arg_18]
0x140047e4a  add     rsp, 30h
0x140047e4e  pop     rdi
0x140047e4f  retn
0x140047e51  mov     rdx, rbx
0x140047e54  mov     rcx, rdi
0x140047e57  call    NbtDispatchInternalCtrl
0x140047e5c  jmp     short loc_140047E1C
0x140047e5e  test    byte ptr cs:xmmword_140038420, 4
0x140047e65  jz      short loc_140047E87
0x140047e67  mov     eax, [rsi+18h]
0x140047e6a  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140047e71  mov     edx, 17h
0x140047e76  mov     [rsp+38h+var_18], eax
0x140047e7a  mov     ecx, 402h
0x140047e7f  mov     r9, rdi
0x140047e82  call    WPP_SF_qD
0x140047e87  mov     dl, 2; PriorityBoost
0x140047e89  mov     dword ptr [rbx+30h], 0C0000184h
0x140047e90  mov     rcx, rbx; Irp
0x140047e93  call    cs:__imp_IofCompleteRequest
0x140047e9a  nop     dword ptr [rax+rax+00h]
0x140047e9f  mov     eax, 0C0000184h
0x140047ea4  jmp     short loc_140047E40
0x140047ea6  mov     edx, 18h
0x140047eab  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140047eb2  mov     ecx, 402h
0x140047eb7  mov     r9d, r14d
0x140047eba  call    WPP_SF_d
0x140047ebf  jmp     loc_140047DE8
0x140047ec4  mov     r9, [rsi+20h]
0x140047ec8  mov     ebp, 0C0000001h
0x140047ecd  test    r9, r9
0x140047ed0  jz      short loc_140047EEB
0x140047ed2  cmp     byte ptr [rbx+40h], 0
0x140047ed6  jz      short loc_140047EDF
0x140047ed8  mov     ebp, 0C0000022h
0x140047edd  jmp     short loc_140047EEB
0x140047edf  lea     rax, NTSend
0x140047ee6  xor     ebp, ebp
0x140047ee8  mov     [r9], rax
0x140047eeb  test    byte ptr cs:xmmword_140038420, 4
0x140047ef2  jz      short loc_140047F0A
0x140047ef4  mov     edx, 19h
0x140047ef9  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140047f00  mov     ecx, 402h
0x140047f05  call    WPP_SF_q
0x140047f0a  mov     edx, ebp
0x140047f0c  mov     rcx, rbx; Irp
0x140047f0f  call    ReturnIrp
0x140047f14  jmp     loc_140047E1E
```
