# CKsPin::DispatchCreateAllocator(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003f2f0`
- end: `0x18003f437`
- name: `?DispatchCreateAllocator@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000dddc`
- `0x180033ba0`
- `0x18003f2f0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003f401`
- `ntoskrnl!KeReleaseMutex` at `0x18003f401`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f367`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f367`
- `ntoskrnl!IofCompleteRequest` at `0x18003f41d`
- `ntoskrnl!IofCompleteRequest` at `0x18003f41d`

## pseudocode

```c
__int64 __fastcall CKsPin::DispatchCreateAllocator(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rdi
  __int64 v3; // rsi
  int v4; // edx
  void *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  PVOID (__stdcall *v8)(PVOID); // r8
  void (__stdcall *v9)(PVOID, PVOID); // r9
  NTSTATUS (__stdcall *v10)(PVOID, PKSALLOCATOR_FRAMING, PVOID *); // rcx
  void (__stdcall *DeleteAllocator)(PVOID); // r10
  unsigned int DefaultAllocator; // ebx

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      81,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  }
  v3 = *(_QWORD *)(*(_QWORD *)v2->Tail.Overlay.CurrentStackLocation->FileObject->RelatedFileObject->FsContext + 112LL);
  KeWaitForSingleObject(*(PVOID *)(v3 + 88), Executive, 0, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      82,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
      v3 + 0x80);
  }
  v5 = (void *)(v3 + 128);
  v6 = **(_QWORD **)(v3 + 128);
  if ( v6 && (v7 = *(_QWORD *)(v6 + 72)) != 0 )
  {
    v8 = *(PVOID (__stdcall **)(PVOID))(v7 + 16);
    v9 = *(void (__stdcall **)(PVOID, PVOID))(v7 + 24);
    v10 = *(NTSTATUS (__stdcall **)(PVOID, PKSALLOCATOR_FRAMING, PVOID *))v7;
    DeleteAllocator = *(void (__stdcall **)(PVOID))(v7 + 8);
  }
  else
  {
    v5 = 0;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    DeleteAllocator = 0;
  }
  DefaultAllocator = KsCreateDefaultAllocatorEx(v2, v5, v8, v9, v10, DeleteAllocator);
  KeReleaseMutex(*(PRKMUTEX *)(v3 + 88), 0);
  if ( DefaultAllocator != 259 )
  {
    v2->IoStatus.Status = DefaultAllocator;
    IofCompleteRequest(v2, 0);
  }
  return DefaultAllocator;
}

```

## disassembly

```asm
0x18003f2f0  push    rbx
0x18003f2f2  push    rbp
0x18003f2f3  push    rsi
0x18003f2f4  push    rdi
0x18003f2f5  push    r15
0x18003f2f7  sub     rsp, 30h
0x18003f2fb  mov     rdi, rdx
0x18003f2fe  lea     rbp, WPP_RECORDER_INITIALIZED
0x18003f305  xor     ebx, ebx
0x18003f307  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003f30e  lea     r15, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x18003f315  jz      short loc_18003F33C
0x18003f317  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f31e  cmp     [rcx+48h], bx
0x18003f322  jz      short loc_18003F33C
0x18003f324  mov     rcx, [rcx+40h]
0x18003f328  lea     r9d, [rbx+51h]
0x18003f32c  lea     r8d, [rbx+1]
0x18003f330  mov     [rsp+58h+Timeout], r15
0x18003f335  mov     dl, 5
0x18003f337  call    WPP_RECORDER_SF_
0x18003f33c  mov     rax, [rdi+0B8h]
0x18003f343  xor     r9d, r9d; Alertable
0x18003f346  xor     r8d, r8d; WaitMode
0x18003f349  mov     [rsp+58h+Timeout], rbx; Timeout
0x18003f34e  xor     edx, edx; WaitReason
0x18003f350  mov     rcx, [rax+30h]
0x18003f354  mov     rax, [rcx+40h]
0x18003f358  mov     rcx, [rax+18h]
0x18003f35c  mov     rax, [rcx]
0x18003f35f  mov     rsi, [rax+70h]
0x18003f363  mov     rcx, [rsi+58h]; Object
0x18003f367  call    cs:__imp_KeWaitForSingleObject
0x18003f36e  nop     dword ptr [rax+rax+00h]
0x18003f373  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003f37a  jz      short loc_18003F3AC
0x18003f37c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f383  cmp     [rcx+48h], bx
0x18003f387  jz      short loc_18003F3AC
0x18003f389  mov     rcx, [rcx+40h]
0x18003f38d  lea     rax, [rsi-80h]
0x18003f391  mov     r9d, 52h ; 'R'
0x18003f397  mov     [rsp+58h+DeleteAllocator], rax
0x18003f39c  mov     dl, 5
0x18003f39e  mov     [rsp+58h+Timeout], r15
0x18003f3a3  lea     r8d, [r9-51h]
0x18003f3a7  call    WPP_RECORDER_SF_q
0x18003f3ac  lea     rdx, [rsi+80h]
0x18003f3b3  mov     rax, [rdx]
0x18003f3b6  mov     rax, [rax]
0x18003f3b9  test    rax, rax
0x18003f3bc  jz      short loc_18003F3D8
0x18003f3be  mov     rax, [rax+48h]
0x18003f3c2  test    rax, rax
0x18003f3c5  jz      short loc_18003F3D8
0x18003f3c7  mov     r8, [rax+10h]
0x18003f3cb  mov     r9, [rax+18h]
0x18003f3cf  mov     rcx, [rax]
0x18003f3d2  mov     r10, [rax+8]
0x18003f3d6  jmp     short loc_18003F3E7
0x18003f3d8  mov     rdx, rbx; InitializeContext
0x18003f3db  mov     r8, rbx; DefaultAllocate
0x18003f3de  mov     r9, rbx; DefaultFree
0x18003f3e1  mov     rcx, rbx
0x18003f3e4  mov     r10, rbx
0x18003f3e7  mov     [rsp+58h+DeleteAllocator], r10; DeleteAllocator
0x18003f3ec  mov     [rsp+58h+Timeout], rcx; InitializeAllocator
0x18003f3f1  mov     rcx, rdi; Irp
0x18003f3f4  call    KsCreateDefaultAllocatorEx
0x18003f3f9  mov     rcx, [rsi+58h]; Mutex
0x18003f3fd  xor     edx, edx; Wait
0x18003f3ff  mov     ebx, eax
0x18003f401  call    cs:__imp_KeReleaseMutex
0x18003f408  nop     dword ptr [rax+rax+00h]
0x18003f40d  cmp     ebx, 103h
0x18003f413  jz      short loc_18003F429
0x18003f415  xor     edx, edx; PriorityBoost
0x18003f417  mov     [rdi+30h], ebx
0x18003f41a  mov     rcx, rdi; Irp
0x18003f41d  call    cs:__imp_IofCompleteRequest
0x18003f424  nop     dword ptr [rax+rax+00h]
0x18003f429  mov     eax, ebx
0x18003f42b  add     rsp, 30h
0x18003f42f  pop     r15
0x18003f431  pop     rdi
0x18003f432  pop     rsi
0x18003f433  pop     rbp
0x18003f434  pop     rbx
0x18003f435  retn
```
