# EtwEx_tidActivityInfoTransfer(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,uchar,_GUID const *,ulong)

- ea: `0x18005ecb4`
- end: `0x18005ed52`
- name: `?EtwEx_tidActivityInfoTransfer@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2E2K@Z`
- size: `158`
- prototype: `unsigned int __fastcall(unsigned __int64, const struct _EVENT_DESCRIPTOR *, const struct _GUID *, const struct _GUID *, unsigned __int8, const struct _GUID *, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005f6b8`

## callees

- `0x180047240`
- `0x18005ecb4`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18005ed3a`
- `ntdll!EtwEventWriteTransfer` at `0x18005ed3a`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfoTransfer(
        __int64 a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        unsigned __int8 a5,
        const struct _GUID *a6,
        char a7)
{
  _QWORD v8[2]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v9[4]; // [rsp+40h] [rbp-30h] BYREF

  v8[0] = ActivityTransfer;
  v8[1] = 0x8000000000000001uLL;
  if ( !Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    return EtwEventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, v8, a3, a4, 0, 0);
  v9[1] = 16;
  v9[0] = &Microsoft_Windows_Networking_ProviderId;
  v9[2] = &a7;
  v9[3] = 4;
  return EtwEventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, v8, a3, a4, 2, v9);
}

```

## disassembly

```asm
0x18005ecb4  push    rbp
0x18005ecb6  mov     rbp, rsp
0x18005ecb9  sub     rsp, 70h
0x18005ecbd  mov     rax, cs:__security_cookie
0x18005ecc4  xor     rax, rsp
0x18005ecc7  mov     [rbp+var_10], rax
0x18005eccb  mov     rax, cs:ActivityTransfer
0x18005ecd2  xor     edx, edx
0x18005ecd4  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle
0x18005ecdb  mov     [rbp+var_40], rax
0x18005ecdf  mov     rax, 8000000000000001h
0x18005ece9  mov     [rbp+var_38], rax
0x18005eced  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x18005ecf3  test    eax, eax
0x18005ecf5  jz      short loc_18005ED2D
0x18005ecf7  lea     rax, Microsoft_Windows_Networking_ProviderId
0x18005ecfe  mov     [rbp+var_28], 10h
0x18005ed06  mov     [rbp+var_30], rax
0x18005ed0a  lea     rax, [rbp+arg_30]
0x18005ed0e  mov     [rbp+var_20], rax
0x18005ed12  lea     rax, [rbp+var_30]
0x18005ed16  mov     [rsp+70h+var_48], rax
0x18005ed1b  mov     [rsp+70h+var_50], 2
0x18005ed23  mov     [rbp+var_18], 4
0x18005ed2b  jmp     short loc_18005ED36
0x18005ed2d  mov     [rsp+70h+var_48], rdx
0x18005ed32  mov     [rsp+70h+var_50], edx
0x18005ed36  lea     rdx, [rbp+var_40]
0x18005ed3a  call    cs:__imp_EtwEventWriteTransfer
0x18005ed40  mov     rcx, [rbp+var_10]
0x18005ed44  xor     rcx, rsp; StackCookie
0x18005ed47  call    __security_check_cookie
0x18005ed4c  add     rsp, 70h
0x18005ed50  pop     rbp
0x18005ed51  retn
```
