# EtwEx_tidActivityInfoTransfer

- ea: `0x14000f5d8`
- end: `0x14000f67d`
- name: `EtwEx_tidActivityInfoTransfer`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f938`

## callees

- `0x14000f5d8`
- `0x140013110`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000f65e`
- `ntoskrnl!EtwWriteTransfer` at `0x14000f65e`

## pseudocode

```c
NTSTATUS __fastcall EtwEx_tidActivityInfoTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        const GUID *a4,
        int a5,
        int a6,
        char a7)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-30h] BYREF
  char *v10; // [rsp+50h] [rbp-20h]
  __int64 v11; // [rsp+58h] [rbp-18h]

  *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
  EventDescriptor.Keyword = 0x8000000000000001uLL;
  if ( !Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    return EtwWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, a3, a4, 0, 0);
  *(_QWORD *)&UserData.Size = 16;
  UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
  v10 = &a7;
  v11 = 4;
  return EtwWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, a3, a4, 2u, &UserData);
}

```

## disassembly

```asm
0x14000f5d8  push    rbp
0x14000f5da  mov     rbp, rsp
0x14000f5dd  sub     rsp, 70h
0x14000f5e1  mov     rax, cs:__security_cookie
0x14000f5e8  xor     rax, rsp
0x14000f5eb  mov     [rbp+var_10], rax
0x14000f5ef  mov     rax, cs:ActivityTransfer
0x14000f5f6  xor     edx, edx
0x14000f5f8  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14000f5ff  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x14000f603  mov     rax, 8000000000000001h
0x14000f60d  mov     [rbp+EventDescriptor.Keyword], rax
0x14000f611  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x14000f617  test    eax, eax
0x14000f619  jz      short loc_14000F651
0x14000f61b  lea     rax, Microsoft_Windows_Networking_ProviderId
0x14000f622  mov     [rbp+var_28], 10h
0x14000f62a  mov     [rbp+var_30], rax
0x14000f62e  lea     rax, [rbp+arg_30]
0x14000f632  mov     [rbp+var_20], rax
0x14000f636  lea     rax, [rbp+var_30]
0x14000f63a  mov     [rsp+70h+UserData], rax
0x14000f63f  mov     [rsp+70h+UserDataCount], 2
0x14000f647  mov     [rbp+var_18], 4
0x14000f64f  jmp     short loc_14000F65A
0x14000f651  mov     [rsp+70h+UserData], rdx; UserData
0x14000f656  mov     [rsp+70h+UserDataCount], edx; UserDataCount
0x14000f65a  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x14000f65e  call    cs:__imp_EtwWriteTransfer
0x14000f665  nop     dword ptr [rax+rax+00h]
0x14000f66a  mov     rcx, [rbp+var_10]
0x14000f66e  xor     rcx, rsp; StackCookie
0x14000f671  call    __security_check_cookie
0x14000f676  add     rsp, 70h
0x14000f67a  pop     rbp
0x14000f67b  retn
```
