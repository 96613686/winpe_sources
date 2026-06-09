# CKsFilter::DispatchCreatePin(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180055b00`
- end: `0x180055cb2`
- name: `?DispatchCreatePin@CKsFilter@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180055b00`
- `0x180055cb8`
- `0x18005632c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180055bc4`
- `ntoskrnl!KeReleaseMutex` at `0x180055bc4`
- `ntoskrnl!KeWaitForSingleObject` at `0x180055b6b`
- `ntoskrnl!KeWaitForSingleObject` at `0x180055b6b`
- `ntoskrnl!IofCompleteRequest` at `0x180055be0`
- `ntoskrnl!IofCompleteRequest` at `0x180055be0`

## pseudocode

```c
__int64 __fastcall CKsFilter::DispatchCreatePin(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdx
  int Pin; // ebx
  __int64 PinId; // rdx
  __int64 v8; // r9
  struct _KSPIN_DESCRIPTOR_EX *v9; // rdx
  int v10; // [rsp+78h] [rbp+10h] BYREF
  struct KSPIN_CONNECT *v11; // [rsp+80h] [rbp+18h] BYREF

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      27,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  }
  v3 = *(_QWORD *)(*(_QWORD *)v2->Tail.Overlay.CurrentStackLocation->FileObject->RelatedFileObject->FsContext + 112LL);
  KeWaitForSingleObject((PVOID)(v3 + 312), Executive, 0, 0, 0);
  v4 = *(_QWORD *)(v3 + 128);
  v11 = 0;
  v10 = 0;
  Pin = KspValidateConnectRequest(
          (__int64)v2,
          *(_DWORD *)(v4 + 32),
          *(_QWORD *)(v4 + 40) + 16LL,
          *(_DWORD *)(v4 + 36),
          (__int64 *)&v11,
          &v10);
  if ( Pin >= 0 )
  {
    PinId = v11->PinId;
    v8 = *(_QWORD *)(v3 + 376) + 88 * PinId;
    v9 = (struct _KSPIN_DESCRIPTOR_EX *)(*(_QWORD *)(*(_QWORD *)(v3 + 128) + 40LL)
                                       + (unsigned int)(*(_DWORD *)(*(_QWORD *)(v3 + 128) + 36LL) * PinId));
    if ( *(_DWORD *)v8 >= v9->InstancesPossible )
      Pin = -1073741823;
    else
      Pin = KspCreatePin(
              v2,
              (struct _KSFILTER_EXT *)v3,
              (struct _LIST_ENTRY *)(v8 + 8),
              v11,
              v10 - 72,
              v9,
              *(struct KSAUTOMATION_TABLE_ **)(v8 + 24),
              *(struct KSAUTOMATION_TABLE_ ***)(v3 + 280),
              *(_DWORD *)(v3 + 288),
              (unsigned int *)v8);
  }
  KeReleaseMutex((PRKMUTEX)(v3 + 312), 0);
  if ( Pin != 259 )
  {
    v2->IoStatus.Status = Pin;
    IofCompleteRequest(v2, 0);
  }
  return (unsigned int)Pin;
}

```

## disassembly

```asm
0x180055b00  mov     [rsp+arg_0], rbx
0x180055b05  mov     [rsp+arg_18], rbp
0x180055b0a  push    rsi
0x180055b0b  push    rdi
0x180055b0c  push    r14
0x180055b0e  sub     rsp, 50h
0x180055b12  mov     rdi, rdx
0x180055b15  lea     rax, WPP_RECORDER_INITIALIZED
0x180055b1c  xor     r14d, r14d
0x180055b1f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180055b26  jz      short loc_180055B3A
0x180055b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180055b2f  cmp     [rcx+48h], r14w
0x180055b34  jnz     loc_180055C8C
0x180055b3a  mov     rax, [rdi+0B8h]
0x180055b41  xor     r9d, r9d; Alertable
0x180055b44  xor     r8d, r8d; WaitMode
0x180055b47  mov     [rsp+68h+Timeout], r14; Timeout
0x180055b4c  xor     edx, edx; WaitReason
0x180055b4e  mov     rcx, [rax+30h]
0x180055b52  mov     rax, [rcx+40h]
0x180055b56  mov     rcx, [rax+18h]
0x180055b5a  mov     rax, [rcx]
0x180055b5d  mov     rsi, [rax+70h]
0x180055b61  lea     rbp, [rsi+138h]
0x180055b68  mov     rcx, rbp; Object
0x180055b6b  call    cs:__imp_KeWaitForSingleObject
0x180055b72  nop     dword ptr [rax+rax+00h]
0x180055b77  mov     rdx, [rsi+80h]
0x180055b7e  lea     rax, [rsp+68h+arg_8]
0x180055b83  mov     [rsp+68h+var_40], rax
0x180055b88  mov     rcx, rdi
0x180055b8b  lea     rax, [rsp+68h+arg_10]
0x180055b93  mov     [rsp+68h+arg_10], r14
0x180055b9b  mov     [rsp+68h+arg_8], r14d
0x180055ba0  mov     r8, [rdx+28h]
0x180055ba4  mov     r9d, [rdx+24h]
0x180055ba8  add     r8, 10h
0x180055bac  mov     edx, [rdx+20h]
0x180055baf  mov     [rsp+68h+Timeout], rax
0x180055bb4  call    KspValidateConnectRequest
0x180055bb9  mov     ebx, eax
0x180055bbb  test    eax, eax
0x180055bbd  jns     short loc_180055C04
0x180055bbf  xor     edx, edx; Wait
0x180055bc1  mov     rcx, rbp; Mutex
0x180055bc4  call    cs:__imp_KeReleaseMutex
0x180055bcb  nop     dword ptr [rax+rax+00h]
0x180055bd0  cmp     ebx, 103h
0x180055bd6  jz      short loc_180055BEC
0x180055bd8  xor     edx, edx; PriorityBoost
0x180055bda  mov     [rdi+30h], ebx
0x180055bdd  mov     rcx, rdi; Irp
0x180055be0  call    cs:__imp_IofCompleteRequest
0x180055be7  nop     dword ptr [rax+rax+00h]
0x180055bec  lea     r11, [rsp+68h+var_18]
0x180055bf1  mov     eax, ebx
0x180055bf3  mov     rbx, [r11+20h]
0x180055bf7  mov     rbp, [r11+38h]
0x180055bfb  mov     rsp, r11
0x180055bfe  pop     r14
0x180055c00  pop     rdi
0x180055c01  pop     rsi
0x180055c02  retn
0x180055c04  mov     rax, [rsi+80h]
0x180055c0b  mov     r11, [rsp+68h+arg_10]
0x180055c13  mov     edx, [r11+30h]
0x180055c17  imul    r9, rdx, 58h ; 'X'
0x180055c1b  imul    edx, [rax+24h]
0x180055c1f  add     r9, [rsi+178h]
0x180055c26  add     rdx, [rax+28h]
0x180055c2a  mov     eax, [rdx+6Ch]
0x180055c2d  cmp     [r9], eax
0x180055c30  jnb     short loc_180055C82
0x180055c32  mov     eax, [rsi+120h]
0x180055c38  lea     r8, [r9+8]; struct _LIST_ENTRY *
0x180055c3c  mov     r10d, [rsp+68h+arg_8]
0x180055c41  mov     rcx, rdi; struct _IRP *
0x180055c44  mov     [rsp+68h+var_20], r9; unsigned int *
0x180055c49  add     r10d, 0FFFFFFB8h
0x180055c4d  mov     [rsp+68h+var_28], eax; unsigned int
0x180055c51  mov     rax, [rsi+118h]
0x180055c58  mov     [rsp+68h+var_30], rax; struct KSAUTOMATION_TABLE_ **
0x180055c5d  mov     rax, [r9+18h]
0x180055c61  mov     r9, r11; struct KSPIN_CONNECT *
0x180055c64  mov     [rsp+68h+var_38], rax; struct KSAUTOMATION_TABLE_ *
0x180055c69  mov     [rsp+68h+var_40], rdx; struct _KSPIN_DESCRIPTOR_EX *
0x180055c6e  mov     rdx, rsi; struct _KSFILTER_EXT *
0x180055c71  mov     dword ptr [rsp+68h+Timeout], r10d; unsigned int
0x180055c76  call    KspCreatePin
0x180055c7b  mov     ebx, eax
0x180055c7d  jmp     loc_180055BBF
0x180055c82  mov     ebx, 0C0000001h
0x180055c87  jmp     loc_180055BBF
0x180055c8c  mov     rcx, [rcx+40h]
0x180055c90  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180055c97  mov     r9d, 1Bh
0x180055c9d  mov     [rsp+68h+Timeout], rax
0x180055ca2  mov     dl, 5
0x180055ca4  lea     r8d, [r9-1Ah]
0x180055ca8  call    WPP_RECORDER_SF_
0x180055cad  jmp     loc_180055B3A
```
