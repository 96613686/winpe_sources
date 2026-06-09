# EtwEx_tidActivityInfoTransfer(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,uchar,_GUID const *,ulong)

- ea: `0x180010eac`
- end: `0x180010f51`
- name: `?EtwEx_tidActivityInfoTransfer@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2E2K@Z`
- size: `165`
- prototype: `ULONG __fastcall(__int64, const struct _EVENT_DESCRIPTOR *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011424`

## callees

- `0x180010eac`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180010f39`
- `ADVAPI32!EventWriteTransfer` at `0x180010f39`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall EtwEx_tidActivityInfoTransfer(
        __int64 a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
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
    return EventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, a3, a4, 0, 0);
  *(_QWORD *)&UserData.Size = 16;
  UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
  v8 = &v5;
  v9 = 4;
  return EventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, a3, a4, 2u, &UserData);
}

```

## disassembly

```asm
0x180010eac  push    rbp
0x180010eae  mov     rbp, rsp
0x180010eb1  sub     rsp, 70h
0x180010eb5  mov     rax, cs:__security_cookie
0x180010ebc  xor     rax, rsp
0x180010ebf  mov     [rbp+var_8], rax
0x180010ec3  mov     rax, cs:ActivityTransfer
0x180010eca  xor     edx, edx
0x180010ecc  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x180010ed3  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x180010ed7  mov     rax, 8000000000000001h
0x180010ee1  mov     [rbp+EventDescriptor.Keyword], rax
0x180010ee5  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180010eeb  mov     [rbp+var_40], 1
0x180010ef2  test    eax, eax
0x180010ef4  jz      short loc_180010F2C
0x180010ef6  lea     rax, Microsoft_Windows_Networking_ProviderId
0x180010efd  mov     [rbp+var_20], 10h
0x180010f05  mov     [rbp+var_28], rax
0x180010f09  lea     rax, [rbp+var_40]
0x180010f0d  mov     [rbp+var_18], rax
0x180010f11  lea     rax, [rbp+var_28]
0x180010f15  mov     [rsp+70h+UserData], rax
0x180010f1a  mov     [rsp+70h+UserDataCount], 2
0x180010f22  mov     [rbp+var_10], 4
0x180010f2a  jmp     short loc_180010F35
0x180010f2c  mov     [rsp+70h+UserData], rdx; UserData
0x180010f31  mov     [rsp+70h+UserDataCount], edx; UserDataCount
0x180010f35  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x180010f39  call    cs:__imp_EventWriteTransfer
0x180010f3f  mov     rcx, [rbp+var_8]
0x180010f43  xor     rcx, rsp; StackCookie
0x180010f46  call    __security_check_cookie
0x180010f4b  add     rsp, 70h
0x180010f4f  pop     rbp
0x180010f50  retn
```
