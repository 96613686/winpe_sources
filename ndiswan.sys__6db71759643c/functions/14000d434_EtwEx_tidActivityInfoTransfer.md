# EtwEx_tidActivityInfoTransfer

- ea: `0x14000d434`
- end: `0x14000d4e0`
- name: `EtwEx_tidActivityInfoTransfer`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e208`

## callees

- `0x14000d434`
- `0x1400161f0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000d4c1`
- `ntoskrnl!EtwWriteTransfer` at `0x14000d4c1`

## pseudocode

```c
NTSTATUS __fastcall EtwEx_tidActivityInfoTransfer(__int64 a1, __int64 a2, const GUID *a3, const GUID *a4)
{
  int v5; // [rsp+30h] [rbp-40h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-28h] BYREF
  int *v8; // [rsp+58h] [rbp-18h]
  __int64 v9; // [rsp+60h] [rbp-10h]

  *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
  EventDescriptor.Keyword = 0x8000000000000001uLL;
  v5 = 1;
  if ( !Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    return EtwWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, a3, a4, 0, 0);
  *(_QWORD *)&UserData.Size = 16;
  UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
  v8 = &v5;
  v9 = 4;
  return EtwWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, a3, a4, 2u, &UserData);
}

```

## disassembly

```asm
0x14000d434  push    rbp
0x14000d436  mov     rbp, rsp
0x14000d439  sub     rsp, 70h
0x14000d43d  mov     rax, cs:__security_cookie
0x14000d444  xor     rax, rsp
0x14000d447  mov     [rbp+var_8], rax
0x14000d44b  mov     rax, cs:ActivityTransfer
0x14000d452  xor     edx, edx
0x14000d454  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14000d45b  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x14000d45f  mov     rax, 8000000000000001h
0x14000d469  mov     [rbp+EventDescriptor.Keyword], rax
0x14000d46d  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x14000d473  mov     [rbp+var_40], 1
0x14000d47a  test    eax, eax
0x14000d47c  jz      short loc_14000D4B4
0x14000d47e  lea     rax, Microsoft_Windows_Networking_ProviderId
0x14000d485  mov     [rbp+var_20], 10h
0x14000d48d  mov     [rbp+var_28], rax
0x14000d491  lea     rax, [rbp+var_40]
0x14000d495  mov     [rbp+var_18], rax
0x14000d499  lea     rax, [rbp+var_28]
0x14000d49d  mov     [rsp+70h+UserData], rax
0x14000d4a2  mov     [rsp+70h+UserDataCount], 2
0x14000d4aa  mov     [rbp+var_10], 4
0x14000d4b2  jmp     short loc_14000D4BD
0x14000d4b4  mov     [rsp+70h+UserData], rdx; UserData
0x14000d4b9  mov     [rsp+70h+UserDataCount], edx; UserDataCount
0x14000d4bd  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x14000d4c1  call    cs:__imp_EtwWriteTransfer
0x14000d4c8  nop     dword ptr [rax+rax+00h]
0x14000d4cd  mov     rcx, [rbp+var_8]
0x14000d4d1  xor     rcx, rsp; StackCookie
0x14000d4d4  call    __security_check_cookie
0x14000d4d9  add     rsp, 70h
0x14000d4dd  pop     rbp
0x14000d4de  retn
```
