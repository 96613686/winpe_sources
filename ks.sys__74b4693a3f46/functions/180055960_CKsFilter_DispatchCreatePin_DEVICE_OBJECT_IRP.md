# CKsFilter::DispatchCreatePin(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180055960`
- end: `0x180055b12`
- name: `?DispatchCreatePin@CKsFilter@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `434`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180055960`
- `0x180055b18`
- `0x18005618c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180055a24`
- `ntoskrnl!KeReleaseMutex` at `0x180055a24`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800559cb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800559cb`
- `ntoskrnl!IofCompleteRequest` at `0x180055a40`
- `ntoskrnl!IofCompleteRequest` at `0x180055a40`

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
          (_DWORD)v2,
          *(_DWORD *)(v4 + 32),
          (unsigned int)*(_QWORD *)(v4 + 40) + 16,
          *(_DWORD *)(v4 + 36),
          (__int64)&v11,
          (__int64)&v10);
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
0x180055960  mov     [rsp+arg_0], rbx
0x180055965  mov     [rsp+arg_18], rbp
0x18005596a  push    rsi
0x18005596b  push    rdi
0x18005596c  push    r14
0x18005596e  sub     rsp, 50h
0x180055972  mov     rdi, rdx
0x180055975  lea     rax, WPP_RECORDER_INITIALIZED
0x18005597c  xor     r14d, r14d
0x18005597f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180055986  jz      short loc_18005599A
0x180055988  mov     rcx, cs:WPP_GLOBAL_Control
0x18005598f  cmp     [rcx+48h], r14w
0x180055994  jnz     loc_180055AEC
0x18005599a  mov     rax, [rdi+0B8h]
0x1800559a1  xor     r9d, r9d; Alertable
0x1800559a4  xor     r8d, r8d; WaitMode
0x1800559a7  mov     [rsp+68h+Timeout], r14; Timeout
0x1800559ac  xor     edx, edx; WaitReason
0x1800559ae  mov     rcx, [rax+30h]
0x1800559b2  mov     rax, [rcx+40h]
0x1800559b6  mov     rcx, [rax+18h]
0x1800559ba  mov     rax, [rcx]
0x1800559bd  mov     rsi, [rax+70h]
0x1800559c1  lea     rbp, [rsi+138h]
0x1800559c8  mov     rcx, rbp; Object
0x1800559cb  call    cs:__imp_KeWaitForSingleObject
0x1800559d2  nop     dword ptr [rax+rax+00h]
0x1800559d7  mov     rdx, [rsi+80h]
0x1800559de  lea     rax, [rsp+68h+arg_8]
0x1800559e3  mov     [rsp+68h+var_40], rax
0x1800559e8  mov     rcx, rdi
0x1800559eb  lea     rax, [rsp+68h+arg_10]
0x1800559f3  mov     [rsp+68h+arg_10], r14
0x1800559fb  mov     [rsp+68h+arg_8], r14d
0x180055a00  mov     r8, [rdx+28h]
0x180055a04  mov     r9d, [rdx+24h]
0x180055a08  add     r8, 10h
0x180055a0c  mov     edx, [rdx+20h]
0x180055a0f  mov     [rsp+68h+Timeout], rax
0x180055a14  call    KspValidateConnectRequest
0x180055a19  mov     ebx, eax
0x180055a1b  test    eax, eax
0x180055a1d  jns     short loc_180055A64
0x180055a1f  xor     edx, edx; Wait
0x180055a21  mov     rcx, rbp; Mutex
0x180055a24  call    cs:__imp_KeReleaseMutex
0x180055a2b  nop     dword ptr [rax+rax+00h]
0x180055a30  cmp     ebx, 103h
0x180055a36  jz      short loc_180055A4C
0x180055a38  xor     edx, edx; PriorityBoost
0x180055a3a  mov     [rdi+30h], ebx
0x180055a3d  mov     rcx, rdi; Irp
0x180055a40  call    cs:__imp_IofCompleteRequest
0x180055a47  nop     dword ptr [rax+rax+00h]
0x180055a4c  lea     r11, [rsp+68h+var_18]
0x180055a51  mov     eax, ebx
0x180055a53  mov     rbx, [r11+20h]
0x180055a57  mov     rbp, [r11+38h]
0x180055a5b  mov     rsp, r11
0x180055a5e  pop     r14
0x180055a60  pop     rdi
0x180055a61  pop     rsi
0x180055a62  retn
0x180055a64  mov     rax, [rsi+80h]
0x180055a6b  mov     r11, [rsp+68h+arg_10]
0x180055a73  mov     edx, [r11+30h]
0x180055a77  imul    r9, rdx, 58h ; 'X'
0x180055a7b  imul    edx, [rax+24h]
0x180055a7f  add     r9, [rsi+178h]
0x180055a86  add     rdx, [rax+28h]
0x180055a8a  mov     eax, [rdx+6Ch]
0x180055a8d  cmp     [r9], eax
0x180055a90  jnb     short loc_180055AE2
0x180055a92  mov     eax, [rsi+120h]
0x180055a98  lea     r8, [r9+8]; struct _LIST_ENTRY *
0x180055a9c  mov     r10d, [rsp+68h+arg_8]
0x180055aa1  mov     rcx, rdi; struct _IRP *
0x180055aa4  mov     [rsp+68h+var_20], r9; unsigned int *
0x180055aa9  add     r10d, 0FFFFFFB8h
0x180055aad  mov     [rsp+68h+var_28], eax; unsigned int
0x180055ab1  mov     rax, [rsi+118h]
0x180055ab8  mov     [rsp+68h+var_30], rax; struct KSAUTOMATION_TABLE_ **
0x180055abd  mov     rax, [r9+18h]
0x180055ac1  mov     r9, r11; struct KSPIN_CONNECT *
0x180055ac4  mov     [rsp+68h+var_38], rax; struct KSAUTOMATION_TABLE_ *
0x180055ac9  mov     [rsp+68h+var_40], rdx; struct _KSPIN_DESCRIPTOR_EX *
0x180055ace  mov     rdx, rsi; struct _KSFILTER_EXT *
0x180055ad1  mov     dword ptr [rsp+68h+Timeout], r10d; unsigned int
0x180055ad6  call    KspCreatePin
0x180055adb  mov     ebx, eax
0x180055add  jmp     loc_180055A1F
0x180055ae2  mov     ebx, 0C0000001h
0x180055ae7  jmp     loc_180055A1F
0x180055aec  mov     rcx, [rcx+40h]
0x180055af0  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180055af7  mov     r9d, 1Bh
0x180055afd  mov     [rsp+68h+Timeout], rax
0x180055b02  mov     dl, 5
0x180055b04  lea     r8d, [r9-1Ah]
0x180055b08  call    WPP_RECORDER_SF_
0x180055b0d  jmp     loc_18005599A
```
