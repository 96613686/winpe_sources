# CKsFilter::DispatchCreateNode(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003c800`
- end: `0x18003c8ba`
- name: `?DispatchCreateNode@CKsFilter@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `186`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180019c60`
- `0x18003c800`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18003c8a0`
- `ntoskrnl!IofCompleteRequest` at `0x18003c8a0`

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
0x18003c800  mov     [rsp+arg_0], rbx
0x18003c805  push    rdi
0x18003c806  sub     rsp, 30h
0x18003c80a  mov     rbx, rdx
0x18003c80d  lea     rax, WPP_RECORDER_INITIALIZED
0x18003c814  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003c81b  jz      short loc_18003C84C
0x18003c81d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c824  cmp     word ptr [rcx+48h], 0
0x18003c829  jz      short loc_18003C84C
0x18003c82b  mov     rcx, [rcx+40h]
0x18003c82f  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x18003c836  mov     r9d, 1Ch
0x18003c83c  mov     [rsp+38h+var_18], rax
0x18003c841  mov     dl, 5
0x18003c843  lea     r8d, [r9-1Bh]
0x18003c847  call    WPP_RECORDER_SF_
0x18003c84c  mov     rax, [rbx+0B8h]
0x18003c853  xor     r8d, r8d
0x18003c856  mov     rcx, [rax+30h]
0x18003c85a  mov     rax, [rcx+40h]
0x18003c85e  mov     rcx, [rax+18h]
0x18003c862  mov     rax, [rcx]
0x18003c865  mov     r9, [rax+70h]
0x18003c869  lea     rcx, [r9-58h]
0x18003c86d  mov     r9, [r9+90h]
0x18003c874  mov     rax, [rcx]
0x18003c877  lea     rdx, [rcx+180h]
0x18003c87e  mov     [rsp+38h+var_18], rdx
0x18003c883  mov     rdx, rbx
0x18003c886  mov     rax, [rax+28h]
0x18003c88a  call    _guard_dispatch_icall
0x18003c88f  mov     edi, eax
0x18003c891  cmp     eax, 103h
0x18003c896  jz      short loc_18003C8AC
0x18003c898  xor     edx, edx; PriorityBoost
0x18003c89a  mov     [rbx+30h], eax
0x18003c89d  mov     rcx, rbx; Irp
0x18003c8a0  call    cs:__imp_IofCompleteRequest
0x18003c8a7  nop     dword ptr [rax+rax+00h]
0x18003c8ac  mov     rbx, [rsp+38h+arg_0]
0x18003c8b1  mov     eax, edi
0x18003c8b3  add     rsp, 30h
0x18003c8b7  pop     rdi
0x18003c8b8  retn
```
