# CKsPin::DispatchCreateAllocator(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003f300`
- end: `0x18003f447`
- name: `?DispatchCreateAllocator@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `327`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000dddc`
- `0x180033ba0`
- `0x18003f300`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003f411`
- `ntoskrnl!KeReleaseMutex` at `0x18003f411`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f377`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f377`
- `ntoskrnl!IofCompleteRequest` at `0x18003f42d`
- `ntoskrnl!IofCompleteRequest` at `0x18003f42d`

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
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
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
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
0x18003f300  push    rbx
0x18003f302  push    rbp
0x18003f303  push    rsi
0x18003f304  push    rdi
0x18003f305  push    r15
0x18003f307  sub     rsp, 30h
0x18003f30b  mov     rdi, rdx
0x18003f30e  lea     rbp, WPP_RECORDER_INITIALIZED
0x18003f315  xor     ebx, ebx
0x18003f317  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003f31e  lea     r15, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18003f325  jz      short loc_18003F34C
0x18003f327  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f32e  cmp     [rcx+48h], bx
0x18003f332  jz      short loc_18003F34C
0x18003f334  mov     rcx, [rcx+40h]
0x18003f338  lea     r9d, [rbx+51h]
0x18003f33c  lea     r8d, [rbx+1]
0x18003f340  mov     [rsp+58h+Timeout], r15
0x18003f345  mov     dl, 5
0x18003f347  call    WPP_RECORDER_SF_
0x18003f34c  mov     rax, [rdi+0B8h]
0x18003f353  xor     r9d, r9d; Alertable
0x18003f356  xor     r8d, r8d; WaitMode
0x18003f359  mov     [rsp+58h+Timeout], rbx; Timeout
0x18003f35e  xor     edx, edx; WaitReason
0x18003f360  mov     rcx, [rax+30h]
0x18003f364  mov     rax, [rcx+40h]
0x18003f368  mov     rcx, [rax+18h]
0x18003f36c  mov     rax, [rcx]
0x18003f36f  mov     rsi, [rax+70h]
0x18003f373  mov     rcx, [rsi+58h]; Object
0x18003f377  call    cs:__imp_KeWaitForSingleObject
0x18003f37e  nop     dword ptr [rax+rax+00h]
0x18003f383  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003f38a  jz      short loc_18003F3BC
0x18003f38c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f393  cmp     [rcx+48h], bx
0x18003f397  jz      short loc_18003F3BC
0x18003f399  mov     rcx, [rcx+40h]
0x18003f39d  lea     rax, [rsi-80h]
0x18003f3a1  mov     r9d, 52h ; 'R'
0x18003f3a7  mov     [rsp+58h+DeleteAllocator], rax
0x18003f3ac  mov     dl, 5
0x18003f3ae  mov     [rsp+58h+Timeout], r15
0x18003f3b3  lea     r8d, [r9-51h]
0x18003f3b7  call    WPP_RECORDER_SF_q
0x18003f3bc  lea     rdx, [rsi+80h]
0x18003f3c3  mov     rax, [rdx]
0x18003f3c6  mov     rax, [rax]
0x18003f3c9  test    rax, rax
0x18003f3cc  jz      short loc_18003F3E8
0x18003f3ce  mov     rax, [rax+48h]
0x18003f3d2  test    rax, rax
0x18003f3d5  jz      short loc_18003F3E8
0x18003f3d7  mov     r8, [rax+10h]
0x18003f3db  mov     r9, [rax+18h]
0x18003f3df  mov     rcx, [rax]
0x18003f3e2  mov     r10, [rax+8]
0x18003f3e6  jmp     short loc_18003F3F7
0x18003f3e8  mov     rdx, rbx; InitializeContext
0x18003f3eb  mov     r8, rbx; DefaultAllocate
0x18003f3ee  mov     r9, rbx; DefaultFree
0x18003f3f1  mov     rcx, rbx
0x18003f3f4  mov     r10, rbx
0x18003f3f7  mov     [rsp+58h+DeleteAllocator], r10; DeleteAllocator
0x18003f3fc  mov     [rsp+58h+Timeout], rcx; InitializeAllocator
0x18003f401  mov     rcx, rdi; Irp
0x18003f404  call    KsCreateDefaultAllocatorEx
0x18003f409  mov     rcx, [rsi+58h]; Mutex
0x18003f40d  xor     edx, edx; Wait
0x18003f40f  mov     ebx, eax
0x18003f411  call    cs:__imp_KeReleaseMutex
0x18003f418  nop     dword ptr [rax+rax+00h]
0x18003f41d  cmp     ebx, 103h
0x18003f423  jz      short loc_18003F439
0x18003f425  xor     edx, edx; PriorityBoost
0x18003f427  mov     [rdi+30h], ebx
0x18003f42a  mov     rcx, rdi; Irp
0x18003f42d  call    cs:__imp_IofCompleteRequest
0x18003f434  nop     dword ptr [rax+rax+00h]
0x18003f439  mov     eax, ebx
0x18003f43b  add     rsp, 30h
0x18003f43f  pop     r15
0x18003f441  pop     rdi
0x18003f442  pop     rsi
0x18003f443  pop     rbp
0x18003f444  pop     rbx
0x18003f445  retn
```
