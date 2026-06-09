# KsDefaultForwardIrp

- ea: `0x180049580`
- end: `0x180049651`
- name: `KsDefaultForwardIrp`
- size: `209`
- prototype: `DRIVER_DISPATCH`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800481d0`
- `0x180049530`

## callees

- `0x18000b7bc`
- `0x180049580`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x180049602`
- `ntoskrnl!IofCallDriver` at `0x180049602`
- `ntoskrnl!IofCompleteRequest` at `0x1800495ae`
- `ntoskrnl!IofCompleteRequest` at `0x1800495ae`

## pseudocode

```c
NTSTATUS __stdcall KsDefaultForwardIrp(struct _DEVICE_OBJECT *DeviceObject, struct _IRP *Irp)
{
  __int64 *DeviceExtension; // rax
  struct _IRP *v3; // rbx
  __int64 v4; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax

  DeviceExtension = (__int64 *)DeviceObject->DeviceExtension;
  v3 = Irp;
  v4 = *DeviceExtension;
  if ( !*(_QWORD *)(*DeviceExtension + 120) && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(Irp) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      1,
      11,
      (__int64)WPP_b72a458f9d94362ddf6ee6b7a421f900_Traceguids);
  }
  if ( v3->CurrentLocation > 1 && *(_QWORD *)(v4 + 120) )
  {
    CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    return IofCallDriver(*(PDEVICE_OBJECT *)(v4 + 120), v3);
  }
  else
  {
    v3->IoStatus.Status = -1073741808;
    IofCompleteRequest(v3, 0);
    return -1073741808;
  }
}

```

## disassembly

```asm
0x180049580  mov     [rsp+arg_0], rbx
0x180049585  push    rdi
0x180049586  sub     rsp, 30h
0x18004958a  mov     rax, [rcx+40h]
0x18004958e  mov     rbx, rdx
0x180049591  mov     rdi, [rax]
0x180049594  cmp     qword ptr [rdi+78h], 0
0x180049599  jz      short loc_180049610
0x18004959b  cmp     byte ptr [rbx+43h], 1
0x18004959f  jg      short loc_1800495C8
0x1800495a1  mov     edi, 0C0000010h
0x1800495a6  xor     edx, edx; PriorityBoost
0x1800495a8  mov     rcx, rbx; Irp
0x1800495ab  mov     [rbx+30h], edi
0x1800495ae  call    cs:__imp_IofCompleteRequest
0x1800495b5  nop     dword ptr [rax+rax+00h]
0x1800495ba  mov     eax, edi
0x1800495bc  mov     rbx, [rsp+38h+arg_0]
0x1800495c1  add     rsp, 30h
0x1800495c5  pop     rdi
0x1800495c6  retn
0x1800495c8  cmp     qword ptr [rdi+78h], 0
0x1800495cd  jz      short loc_1800495A1
0x1800495cf  mov     rax, [rbx+0B8h]
0x1800495d6  mov     rdx, rbx; Irp
0x1800495d9  movups  xmm0, xmmword ptr [rax]
0x1800495dc  movups  xmmword ptr [rax-48h], xmm0
0x1800495e0  movups  xmm1, xmmword ptr [rax+10h]
0x1800495e4  movups  xmmword ptr [rax-38h], xmm1
0x1800495e8  movups  xmm0, xmmword ptr [rax+20h]
0x1800495ec  movups  xmmword ptr [rax-28h], xmm0
0x1800495f0  movsd   xmm1, qword ptr [rax+30h]
0x1800495f5  movsd   qword ptr [rax-18h], xmm1
0x1800495fa  mov     byte ptr [rax-45h], 0
0x1800495fe  mov     rcx, [rdi+78h]; DeviceObject
0x180049602  call    cs:__imp_IofCallDriver
0x180049609  nop     dword ptr [rax+rax+00h]
0x18004960e  jmp     short loc_1800495BC
0x180049610  lea     rax, WPP_RECORDER_INITIALIZED
0x180049617  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004961e  jz      loc_18004959B
0x180049624  mov     rcx, cs:WPP_GLOBAL_Control
0x18004962b  lea     rax, WPP_b72a458f9d94362ddf6ee6b7a421f900_Traceguids
0x180049632  mov     r9d, 0Bh
0x180049638  mov     [rsp+38h+var_18], rax
0x18004963d  mov     dl, 4
0x18004963f  mov     rcx, [rcx+40h]
0x180049643  lea     r8d, [r9-0Ah]
0x180049647  call    WPP_RECORDER_SF_
0x18004964c  jmp     loc_18004959B
```
