# ClassCreateClose

- ea: `0x14005d0d0`
- end: `0x14005d171`
- name: `ClassCreateClose`
- size: `161`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x1400157d0`
- `0x14003e470`
- `0x14005d0d0`
- `0x14005d180`

## string_xrefs

- `0x14005d0dd`: `minkernel\storage\classpnp\create.c`

## pseudocode

```c
__int64 __fastcall ClassCreateClose(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // rbp
  NTSTATUS Close; // esi
  __int64 (__fastcall *v6)(PDEVICE_OBJECT, PIRP); // rax
  unsigned int MajorFunction; // ecx
  int v9; // eax

  DeviceExtension = DeviceObject->DeviceExtension;
  if ( ClassAcquireRemoveLockEx(DeviceObject, Irp, "minkernel\\storage\\classpnp\\create.c", 0x5Cu) )
  {
    MajorFunction = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
    if ( (unsigned __int8)MajorFunction > 0x12u || (v9 = 327684, !_bittest(&v9, MajorFunction)) )
    {
      Close = -1073741632;
LABEL_4:
      Irp->IoStatus.Status = Close;
      ClassReleaseRemoveLock(DeviceObject, Irp);
      ClassCompleteRequest(DeviceObject, Irp, 0);
      return (unsigned int)Close;
    }
  }
  Close = ClasspCreateClose(DeviceObject, Irp);
  if ( Close < 0 )
    goto LABEL_4;
  v6 = *(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(DeviceExtension[20] + 48LL);
  if ( !v6 )
    goto LABEL_4;
  return v6(DeviceObject, Irp);
}

```

## disassembly

```asm
0x14005d0d0  push    rbx
0x14005d0d2  push    rbp
0x14005d0d3  push    rsi
0x14005d0d4  push    rdi
0x14005d0d5  sub     rsp, 28h
0x14005d0d9  mov     rbp, [rcx+40h]
0x14005d0dd  lea     r8, aMinkernelStora_2; "minkernel\\storage\\classpnp\\create.c"
0x14005d0e4  mov     r9d, 5Ch ; '\'; Line
0x14005d0ea  mov     rbx, rdx
0x14005d0ed  mov     rdi, rcx
0x14005d0f0  call    ClassAcquireRemoveLockEx
0x14005d0f5  test    eax, eax
0x14005d0f7  jnz     short loc_14005D142
0x14005d0f9  mov     rdx, rbx
0x14005d0fc  mov     rcx, rdi
0x14005d0ff  call    ClasspCreateClose
0x14005d104  mov     esi, eax
0x14005d106  test    eax, eax
0x14005d108  js      short loc_14005D11A
0x14005d10a  mov     rcx, [rbp+0A0h]
0x14005d111  mov     rax, [rcx+30h]
0x14005d115  test    rax, rax
0x14005d118  jnz     short loc_14005D164
0x14005d11a  mov     rdx, rbx; Tag
0x14005d11d  mov     [rbx+30h], esi
0x14005d120  mov     rcx, rdi; DeviceObject
0x14005d123  call    ClassReleaseRemoveLock
0x14005d128  xor     r8d, r8d; PriorityBoost
0x14005d12b  mov     rdx, rbx; Irp
0x14005d12e  mov     rcx, rdi; DeviceObject
0x14005d131  call    ClassCompleteRequest
0x14005d136  mov     eax, esi
0x14005d138  add     rsp, 28h
0x14005d13c  pop     rdi
0x14005d13d  pop     rsi
0x14005d13e  pop     rbp
0x14005d13f  pop     rbx
0x14005d140  retn
0x14005d142  mov     rax, [rbx+0B8h]
0x14005d149  movzx   ecx, byte ptr [rax]
0x14005d14c  cmp     cl, 12h
0x14005d14f  ja      loc_140061646
0x14005d155  mov     eax, 50004h
0x14005d15a  bt      eax, ecx
0x14005d15d  jb      short loc_14005D0F9
0x14005d15f  jmp     loc_140061646
0x14005d164  mov     rdx, rbx
0x14005d167  mov     rcx, rdi
0x14005d16a  call    _guard_dispatch_icall
0x14005d16f  jmp     short loc_14005D138
0x140061646  mov     esi, 0C00000C0h
0x14006164b  jmp     loc_14005D11A
```
