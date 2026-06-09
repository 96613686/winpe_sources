# PmGiveDisk(_DEVICE_EXTENSION *)

- ea: `0x140024e38`
- end: `0x140024f3c`
- name: `?PmGiveDisk@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `260`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400087c0`

## callees

- `0x140024e38`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140024e6e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024e6e`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140024f10`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140024f10`
- `ntoskrnl!IoReuseIrp` at `0x140024ebc`
- `ntoskrnl!IoReuseIrp` at `0x140024ebc`
- `ntoskrnl!KeReleaseMutex` at `0x140024e8f`
- `ntoskrnl!KeReleaseMutex` at `0x140024e8f`

## pseudocode

```c
void __fastcall PmGiveDisk(struct _DEVICE_EXTENSION *a1)
{
  char *DeviceExtension; // r14
  _QWORD *v3; // r14
  _QWORD *i; // rdi
  IRP *v5; // rcx
  __int64 v6; // rax
  IRP *v7; // rbx
  struct _DEVICE_OBJECT *v8; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = 0;
  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
  *((GUID *)a1 + 34) = GUID_NULL;
  KeReleaseMutex((PRKMUTEX)a1 + 1, 0);
  v3 = DeviceExtension + 72;
  for ( i = (_QWORD *)*v3; i != v3; i = (_QWORD *)*i )
  {
    v5 = (IRP *)*((_QWORD *)a1 + 107);
    v10 = *((_QWORD *)a1 + 3);
    IoReuseIrp(v5, -1073741637);
    v6 = *((_QWORD *)a1 + 107);
    --*(_BYTE *)(v6 + 67);
    *(_QWORD *)(v6 + 184) -= 72LL;
    v7 = (IRP *)*((_QWORD *)a1 + 107);
    v8 = (struct _DEVICE_OBJECT *)i[5];
    CurrentStackLocation = v7->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation->MajorFunction = 15;
    v7->AssociatedIrp.MasterIrp = (struct _IRP *)&v10;
    CurrentStackLocation->Parameters.Read.Length = 0;
    CurrentStackLocation->Parameters.Create.Options = 8;
    CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 7733292;
    IoForwardIrpSynchronously(v8, v7);
    if ( v7->IoStatus.Status == -1073741802 )
      break;
  }
}

```

## disassembly

```asm
0x140024e38  push    rbx
0x140024e3a  push    rsi
0x140024e3b  push    rdi
0x140024e3c  push    r14
0x140024e3e  sub     rsp, 38h
0x140024e42  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140024e49  mov     rsi, rcx
0x140024e4c  xor     r9d, r9d; Alertable
0x140024e4f  mov     [rsp+58h+arg_0], 0
0x140024e58  xor     r8d, r8d; WaitMode
0x140024e5b  mov     [rsp+58h+Timeout], 0; Timeout
0x140024e64  xor     edx, edx; WaitReason
0x140024e66  add     rcx, 38h ; '8'; Object
0x140024e6a  mov     r14, [rax+40h]
0x140024e6e  call    cs:__imp_KeWaitForSingleObject
0x140024e75  nop     dword ptr [rax+rax+00h]
0x140024e7a  movups  xmm0, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x140024e81  xor     edx, edx; Wait
0x140024e83  lea     rcx, [rsi+38h]; Mutex
0x140024e87  movdqu  xmmword ptr [rsi+220h], xmm0
0x140024e8f  call    cs:__imp_KeReleaseMutex
0x140024e96  nop     dword ptr [rax+rax+00h]
0x140024e9b  add     r14, 48h ; 'H'
0x140024e9f  mov     rdi, [r14]
0x140024ea2  jmp     loc_140024F28
0x140024ea7  mov     rax, [rsi+18h]
0x140024eab  mov     edx, 0C00000BBh; Iostatus
0x140024eb0  mov     rcx, [rsi+358h]; Irp
0x140024eb7  mov     [rsp+58h+arg_0], rax
0x140024ebc  call    cs:__imp_IoReuseIrp
0x140024ec3  nop     dword ptr [rax+rax+00h]
0x140024ec8  mov     rax, [rsi+358h]
0x140024ecf  lea     rdx, [rsp+58h+arg_0]
0x140024ed4  dec     byte ptr [rax+43h]
0x140024ed7  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140024edf  mov     rbx, [rsi+358h]
0x140024ee6  mov     rcx, [rdi+28h]; DeviceObject
0x140024eea  mov     rax, [rbx+0B8h]
0x140024ef1  mov     byte ptr [rax], 0Fh
0x140024ef4  mov     [rbx+18h], rdx
0x140024ef8  mov     rdx, rbx; Irp
0x140024efb  mov     dword ptr [rax+8], 0
0x140024f02  mov     dword ptr [rax+10h], 8
0x140024f09  mov     dword ptr [rax+18h], 76002Ch
0x140024f10  call    cs:__imp_IoForwardIrpSynchronously
0x140024f17  nop     dword ptr [rax+rax+00h]
0x140024f1c  cmp     dword ptr [rbx+30h], 0C0000016h
0x140024f23  jz      short loc_140024F31
0x140024f25  mov     rdi, [rdi]
0x140024f28  cmp     rdi, r14
0x140024f2b  jnz     loc_140024EA7
0x140024f31  add     rsp, 38h
0x140024f35  pop     r14
0x140024f37  pop     rdi
0x140024f38  pop     rsi
0x140024f39  pop     rbx
0x140024f3a  retn
```
