# CKsPin::DispatchCreateNode(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003f620`
- end: `0x18003f6de`
- name: `?DispatchCreateNode@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `190`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180019c60`
- `0x18003f620`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18003f6c4`
- `ntoskrnl!IofCompleteRequest` at `0x18003f6c4`

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
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
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
0x18003f620  mov     [rsp+arg_0], rbx
0x18003f625  push    rdi
0x18003f626  sub     rsp, 30h
0x18003f62a  mov     rbx, rdx
0x18003f62d  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f634  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f63b  jz      short loc_18003F66C
0x18003f63d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f644  cmp     word ptr [rcx+48h], 0
0x18003f649  jz      short loc_18003F66C
0x18003f64b  mov     rcx, [rcx+40h]
0x18003f64f  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18003f656  mov     r9d, 54h ; 'T'
0x18003f65c  mov     [rsp+38h+var_18], rax
0x18003f661  mov     dl, 5
0x18003f663  lea     r8d, [r9-53h]
0x18003f667  call    WPP_RECORDER_SF_
0x18003f66c  mov     rax, [rbx+0B8h]
0x18003f673  mov     rcx, [rax+30h]
0x18003f677  mov     rax, [rcx+40h]
0x18003f67b  mov     rcx, [rax+18h]
0x18003f67f  mov     rax, [rcx]
0x18003f682  mov     r9, [rax+70h]
0x18003f686  lea     r8, [r9-80h]
0x18003f68a  mov     r9, [r9+90h]
0x18003f691  mov     rcx, [r8+288h]
0x18003f698  lea     rdx, [r8+290h]
0x18003f69f  mov     [rsp+38h+var_18], rdx
0x18003f6a4  mov     rdx, rbx
0x18003f6a7  mov     rax, [rcx]
0x18003f6aa  mov     rax, [rax+28h]
0x18003f6ae  call    _guard_dispatch_icall
0x18003f6b3  mov     edi, eax
0x18003f6b5  cmp     eax, 103h
0x18003f6ba  jz      short loc_18003F6D0
0x18003f6bc  xor     edx, edx; PriorityBoost
0x18003f6be  mov     [rbx+30h], eax
0x18003f6c1  mov     rcx, rbx; Irp
0x18003f6c4  call    cs:__imp_IofCompleteRequest
0x18003f6cb  nop     dword ptr [rax+rax+00h]
0x18003f6d0  mov     rbx, [rsp+38h+arg_0]
0x18003f6d5  mov     eax, edi
0x18003f6d7  add     rsp, 30h
0x18003f6db  pop     rdi
0x18003f6dc  retn
```
