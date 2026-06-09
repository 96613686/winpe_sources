# EtwEx_tidActivityInfoTransfer

- ea: `0x180021f5c`
- end: `0x180021ffa`
- name: `EtwEx_tidActivityInfoTransfer`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d6d0`
- `0x18001c6c0`

## callees

- `0x180020250`
- `0x180021f5c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180021fe2`
- `ntdll!EtwEventWriteTransfer` at `0x180021fe2`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfoTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
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
0x180021f5c  push    rbp
0x180021f5e  mov     rbp, rsp
0x180021f61  sub     rsp, 70h
0x180021f65  mov     rax, cs:__security_cookie
0x180021f6c  xor     rax, rsp
0x180021f6f  mov     [rbp+var_10], rax
0x180021f73  mov     rax, cs:ActivityTransfer
0x180021f7a  xor     edx, edx
0x180021f7c  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle
0x180021f83  mov     [rbp+var_40], rax
0x180021f87  mov     rax, 8000000000000001h
0x180021f91  mov     [rbp+var_38], rax
0x180021f95  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180021f9b  test    eax, eax
0x180021f9d  jz      short loc_180021FD5
0x180021f9f  lea     rax, Microsoft_Windows_Networking_ProviderId
0x180021fa6  mov     [rbp+var_28], 10h
0x180021fae  mov     [rbp+var_30], rax
0x180021fb2  lea     rax, [rbp+arg_30]
0x180021fb6  mov     [rbp+var_20], rax
0x180021fba  lea     rax, [rbp+var_30]
0x180021fbe  mov     [rsp+70h+var_48], rax
0x180021fc3  mov     [rsp+70h+var_50], 2
0x180021fcb  mov     [rbp+var_18], 4
0x180021fd3  jmp     short loc_180021FDE
0x180021fd5  mov     [rsp+70h+var_48], rdx
0x180021fda  mov     [rsp+70h+var_50], edx
0x180021fde  lea     rdx, [rbp+var_40]
0x180021fe2  call    cs:__imp_EtwEventWriteTransfer
0x180021fe8  mov     rcx, [rbp+var_10]
0x180021fec  xor     rcx, rsp; StackCookie
0x180021fef  call    __security_check_cookie
0x180021ff4  add     rsp, 70h
0x180021ff8  pop     rbp
0x180021ff9  retn
```
