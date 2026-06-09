# ClassBuildRequest

- ea: `0x140037db0`
- end: `0x140037dfc`
- name: `ClassBuildRequest`
- size: `76`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140037db0`
- `0x140038294`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140037dc8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140037dc8`

## pseudocode

```c
NTSTATUS __stdcall ClassBuildRequest(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // rbx

  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  if ( !ExAllocateFromNPagedLookasideList(&DeviceExtension->CommonExtension.SrbLookasideList) )
    return -1073741670;
  ClasspBuildRequestEx(DeviceExtension);
  return 0;
}

```

## disassembly

```asm
0x140037db0  mov     [rsp+arg_0], rbx
0x140037db5  push    rdi
0x140037db6  sub     rsp, 20h
0x140037dba  mov     rbx, [rcx+40h]
0x140037dbe  mov     rdi, rdx
0x140037dc1  lea     rcx, [rbx+100h]; Lookaside
0x140037dc8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140037dcf  nop     dword ptr [rax+rax+00h]
0x140037dd4  test    rax, rax
0x140037dd7  jnz     short loc_140037DE0
0x140037dd9  mov     eax, 0C000009Ah
0x140037dde  jmp     short loc_140037DF0
0x140037de0  mov     r8, rax
0x140037de3  mov     rdx, rdi
0x140037de6  mov     rcx, rbx; FdoExtension
0x140037de9  call    ClasspBuildRequestEx
0x140037dee  xor     eax, eax
0x140037df0  mov     rbx, [rsp+28h+arg_0]
0x140037df5  add     rsp, 20h
0x140037df9  pop     rdi
0x140037dfa  retn
```
