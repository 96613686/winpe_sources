# CKsPin::DispatchCreateNode(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003f610`
- end: `0x18003f6ce`
- name: `?DispatchCreateNode@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180019cb0`
- `0x18003f610`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18003f6b4`
- `ntoskrnl!IofCompleteRequest` at `0x18003f6b4`

## pseudocode

```c
__int64 __fastcall CKsPin::DispatchCreateNode(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rbx
  __int64 v3; // r9
  NTSTATUS v4; // eax
  unsigned int v5; // edi

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      84,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  }
  v3 = *(_QWORD *)(*(_QWORD *)v2->Tail.Overlay.CurrentStackLocation->FileObject->RelatedFileObject->FsContext + 112LL);
  v4 = (*(__int64 (__fastcall **)(_QWORD, struct _IRP *, __int64, _QWORD, __int64))(**(_QWORD **)(v3 - 128 + 648) + 40LL))(
         *(_QWORD *)(v3 - 128 + 648),
         v2,
         v3 - 128,
         *(_QWORD *)(v3 + 144),
         v3 - 128 + 656);
  v5 = v4;
  if ( v4 != 259 )
  {
    v2->IoStatus.Status = v4;
    IofCompleteRequest(v2, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x18003f610  mov     [rsp+arg_0], rbx
0x18003f615  push    rdi
0x18003f616  sub     rsp, 30h
0x18003f61a  mov     rbx, rdx
0x18003f61d  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f624  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f62b  jz      short loc_18003F65C
0x18003f62d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f634  cmp     word ptr [rcx+48h], 0
0x18003f639  jz      short loc_18003F65C
0x18003f63b  mov     rcx, [rcx+40h]
0x18003f63f  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x18003f646  mov     r9d, 54h ; 'T'
0x18003f64c  mov     [rsp+38h+var_18], rax
0x18003f651  mov     dl, 5
0x18003f653  lea     r8d, [r9-53h]
0x18003f657  call    WPP_RECORDER_SF_
0x18003f65c  mov     rax, [rbx+0B8h]
0x18003f663  mov     rcx, [rax+30h]
0x18003f667  mov     rax, [rcx+40h]
0x18003f66b  mov     rcx, [rax+18h]
0x18003f66f  mov     rax, [rcx]
0x18003f672  mov     r9, [rax+70h]
0x18003f676  lea     r8, [r9-80h]
0x18003f67a  mov     r9, [r9+90h]
0x18003f681  mov     rcx, [r8+288h]
0x18003f688  lea     rdx, [r8+290h]
0x18003f68f  mov     [rsp+38h+var_18], rdx
0x18003f694  mov     rdx, rbx
0x18003f697  mov     rax, [rcx]
0x18003f69a  mov     rax, [rax+28h]
0x18003f69e  call    _guard_dispatch_icall
0x18003f6a3  mov     edi, eax
0x18003f6a5  cmp     eax, 103h
0x18003f6aa  jz      short loc_18003F6C0
0x18003f6ac  xor     edx, edx; PriorityBoost
0x18003f6ae  mov     [rbx+30h], eax
0x18003f6b1  mov     rcx, rbx; Irp
0x18003f6b4  call    cs:__imp_IofCompleteRequest
0x18003f6bb  nop     dword ptr [rax+rax+00h]
0x18003f6c0  mov     rbx, [rsp+38h+arg_0]
0x18003f6c5  mov     eax, edi
0x18003f6c7  add     rsp, 30h
0x18003f6cb  pop     rdi
0x18003f6cc  retn
```
