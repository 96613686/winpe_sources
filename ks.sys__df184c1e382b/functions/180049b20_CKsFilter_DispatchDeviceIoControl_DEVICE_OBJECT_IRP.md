# CKsFilter::DispatchDeviceIoControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180049b20`
- end: `0x180049bde`
- name: `?DispatchDeviceIoControl@CKsFilter@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180049b20`
- `0x180049c20`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180049b9c`
- `ntoskrnl!IofCompleteRequest` at `0x180049b9c`

## pseudocode

```c
__int64 __fastcall CKsFilter::DispatchDeviceIoControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rbx
  __int64 v3; // rdx
  __int64 result; // rax
  unsigned int v5; // edi

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      30,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  }
  v3 = *(_QWORD *)(*(_QWORD *)v2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext + 112LL);
  result = KspHandleAutomationIoControl((_DWORD)v2, *(_QWORD *)(v3 + 280), *(_DWORD *)(v3 + 288));
  v5 = result;
  if ( (_DWORD)result != 259 )
  {
    v2->IoStatus.Status = result;
    IofCompleteRequest(v2, 0);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180049b20  mov     [rsp+arg_0], rbx
0x180049b25  push    rdi
0x180049b26  sub     rsp, 30h
0x180049b2a  mov     rbx, rdx
0x180049b2d  lea     rax, WPP_RECORDER_INITIALIZED
0x180049b34  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180049b3b  jz      short loc_180049B4B
0x180049b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b44  cmp     word ptr [rcx+48h], 0
0x180049b49  jnz     short loc_180049BB6
0x180049b4b  mov     rax, [rbx+0B8h]
0x180049b52  mov     rcx, [rax+30h]
0x180049b56  mov     rax, [rcx+18h]
0x180049b5a  mov     rcx, [rax]
0x180049b5d  mov     rdx, [rcx+70h]
0x180049b61  mov     rcx, rbx
0x180049b64  mov     eax, [rdx+120h]
0x180049b6a  lea     r8, [rdx+68h]
0x180049b6e  mov     [rsp+38h+var_10], eax
0x180049b72  lea     r9, [r8+10h]
0x180049b76  mov     rax, [rdx+118h]
0x180049b7d  mov     rdx, [rdx+60h]
0x180049b81  mov     [rsp+38h+var_18], rax
0x180049b86  call    KspHandleAutomationIoControl
0x180049b8b  mov     edi, eax
0x180049b8d  cmp     eax, 103h
0x180049b92  jz      short loc_180049BAA
0x180049b94  xor     edx, edx; PriorityBoost
0x180049b96  mov     [rbx+30h], eax
0x180049b99  mov     rcx, rbx; Irp
0x180049b9c  call    cs:__imp_IofCompleteRequest
0x180049ba3  nop     dword ptr [rax+rax+00h]
0x180049ba8  mov     eax, edi
0x180049baa  mov     rbx, [rsp+38h+arg_0]
0x180049baf  add     rsp, 30h
0x180049bb3  pop     rdi
0x180049bb4  retn
0x180049bb6  mov     rcx, [rcx+40h]
0x180049bba  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180049bc1  mov     r9d, 1Eh
0x180049bc7  mov     [rsp+38h+var_18], rax
0x180049bcc  mov     r8d, 1
0x180049bd2  mov     dl, 5
0x180049bd4  call    WPP_RECORDER_SF_
0x180049bd9  jmp     loc_180049B4B
```
