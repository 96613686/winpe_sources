# CKsFilter::DispatchCreateNode(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003c7f0`
- end: `0x18003c8aa`
- name: `?DispatchCreateNode@CKsFilter@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180019cb0`
- `0x18003c7f0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18003c890`
- `ntoskrnl!IofCompleteRequest` at `0x18003c890`

## pseudocode

```c
__int64 __fastcall CKsFilter::DispatchCreateNode(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
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
      28,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  }
  v3 = *(_QWORD *)(*(_QWORD *)v2->Tail.Overlay.CurrentStackLocation->FileObject->RelatedFileObject->FsContext + 112LL);
  v4 = (*(__int64 (__fastcall **)(__int64, struct _IRP *, _QWORD, _QWORD, __int64))(*(_QWORD *)(v3 - 88) + 40LL))(
         v3 - 88,
         v2,
         0,
         *(_QWORD *)(v3 + 144),
         v3 - 88 + 384);
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
0x18003c7f0  mov     [rsp+arg_0], rbx
0x18003c7f5  push    rdi
0x18003c7f6  sub     rsp, 30h
0x18003c7fa  mov     rbx, rdx
0x18003c7fd  lea     rax, WPP_RECORDER_INITIALIZED
0x18003c804  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003c80b  jz      short loc_18003C83C
0x18003c80d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c814  cmp     word ptr [rcx+48h], 0
0x18003c819  jz      short loc_18003C83C
0x18003c81b  mov     rcx, [rcx+40h]
0x18003c81f  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x18003c826  mov     r9d, 1Ch
0x18003c82c  mov     [rsp+38h+var_18], rax
0x18003c831  mov     dl, 5
0x18003c833  lea     r8d, [r9-1Bh]
0x18003c837  call    WPP_RECORDER_SF_
0x18003c83c  mov     rax, [rbx+0B8h]
0x18003c843  xor     r8d, r8d
0x18003c846  mov     rcx, [rax+30h]
0x18003c84a  mov     rax, [rcx+40h]
0x18003c84e  mov     rcx, [rax+18h]
0x18003c852  mov     rax, [rcx]
0x18003c855  mov     r9, [rax+70h]
0x18003c859  lea     rcx, [r9-58h]
0x18003c85d  mov     r9, [r9+90h]
0x18003c864  mov     rax, [rcx]
0x18003c867  lea     rdx, [rcx+180h]
0x18003c86e  mov     [rsp+38h+var_18], rdx
0x18003c873  mov     rdx, rbx
0x18003c876  mov     rax, [rax+28h]
0x18003c87a  call    _guard_dispatch_icall
0x18003c87f  mov     edi, eax
0x18003c881  cmp     eax, 103h
0x18003c886  jz      short loc_18003C89C
0x18003c888  xor     edx, edx; PriorityBoost
0x18003c88a  mov     [rbx+30h], eax
0x18003c88d  mov     rcx, rbx; Irp
0x18003c890  call    cs:__imp_IofCompleteRequest
0x18003c897  nop     dword ptr [rax+rax+00h]
0x18003c89c  mov     rbx, [rsp+38h+arg_0]
0x18003c8a1  mov     eax, edi
0x18003c8a3  add     rsp, 30h
0x18003c8a7  pop     rdi
0x18003c8a8  retn
```
