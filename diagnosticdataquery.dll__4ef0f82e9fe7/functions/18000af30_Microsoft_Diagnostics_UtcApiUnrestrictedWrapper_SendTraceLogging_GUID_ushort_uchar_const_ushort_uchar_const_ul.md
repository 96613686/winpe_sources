# Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::SendTraceLogging(_GUID,ushort,uchar const *,ushort,uchar const *,ulong,uchar const *,tagUTC_TRACELOGGING_EVENT_DESCRIPTOR,_GUID const *,_GUID const *,ulong)

- ea: `0x18000af30`
- end: `0x18000b013`
- name: `?SendTraceLogging@UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@QEBAJU_GUID@@GPEBEG1K1UtagUTC_TRACELOGGING_EVENT_DESCRIPTOR@@PEBU4@3K@Z`
- size: `227`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int128 *, unsigned __int16, __int64, unsigned __int16, __int64, int, __int64, __int128 *, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a5b0`
- `0x18000a6c0`

## callees

- `0x18000af30`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000afe1`
- `RPCRT4!NdrClientCall3` at `0x18000afe1`
- `RPCRT4!RpcExceptionFilter` at `0x18000c01f`
- `RPCRT4!RpcExceptionFilter` at `0x18000c01f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::SendTraceLogging(
        __int64 a1,
        __int128 *a2,
        unsigned __int16 a3,
        __int64 a4,
        unsigned __int16 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int128 *a9,
        __int64 a10,
        __int64 a11,
        int a12)
{
  int v13; // [rsp+28h] [rbp-90h]
  int v14; // [rsp+38h] [rbp-80h]
  __int128 v17; // [rsp+90h] [rbp-28h] BYREF
  __int128 v18; // [rsp+A0h] [rbp-18h] BYREF

  v17 = *a9;
  v18 = *a2;
  v14 = a5;
  v13 = a3;
  return NdrClientCall3(
           (MIDL_STUBLESS_PROXY_INFO *)&stru_18000FA50,
           1u,
           0,
           *(_QWORD *)(a1 + 8),
           &v18,
           v13,
           a4,
           v14,
           a6,
           a7,
           a8,
           &v17,
           a10,
           a11,
           a12);
}

```

## disassembly

```asm
0x18000af30  mov     r11, rsp
0x18000af33  sub     rsp, 0B8h
0x18000af3a  mov     r10, rcx
0x18000af3d  mov     qword ptr [r11-30h], 0
0x18000af45  mov     rax, [rsp+0B8h+arg_40]
0x18000af4d  movaps  xmm0, xmmword ptr [rax]
0x18000af50  movdqa  xmmword ptr [r11-28h], xmm0
0x18000af56  movaps  xmm1, xmmword ptr [rdx]
0x18000af59  movdqa  xmmword ptr [r11-18h], xmm1
0x18000af5f  movzx   ecx, [rsp+0B8h+arg_20]
0x18000af67  movzx   edx, r8w
0x18000af6b  mov     eax, [rsp+0B8h+arg_58]
0x18000af72  mov     [rsp+0B8h+var_48], eax
0x18000af76  mov     rax, [rsp+0B8h+arg_50]
0x18000af7e  mov     [r11-50h], rax
0x18000af82  mov     rax, [rsp+0B8h+arg_48]
0x18000af8a  mov     [r11-58h], rax
0x18000af8e  lea     rax, [r11-28h]
0x18000af92  mov     [r11-60h], rax
0x18000af96  mov     rax, [rsp+0B8h+arg_38]
0x18000af9e  mov     [r11-68h], rax
0x18000afa2  mov     eax, [rsp+0B8h+arg_30]
0x18000afa9  mov     [rsp+0B8h+var_70], eax
0x18000afad  mov     rax, [rsp+0B8h+arg_28]
0x18000afb5  mov     [r11-78h], rax
0x18000afb9  mov     [rsp+0B8h+var_80], ecx
0x18000afbd  mov     [rsp+0B8h+var_88], r9
0x18000afc2  mov     [rsp+0B8h+var_90], edx
0x18000afc6  lea     rax, [r11-18h]
0x18000afca  mov     [rsp+0B8h+var_98], rax
0x18000afcf  mov     r9, [r10+8]
0x18000afd3  xor     r8d, r8d; pReturnValue
0x18000afd6  lea     edx, [r8+1]; nProcNum
0x18000afda  lea     rcx, stru_18000FA50; pProxyInfo
0x18000afe1  call    cs:__imp_NdrClientCall3
0x18000afe7  mov     [rsp+0B8h+var_30], rax
0x18000afef  mov     [rsp+0B8h+var_38], eax
0x18000aff6  jmp     short loc_18000B00B
0x18000aff8  test    eax, eax
0x18000affa  jle     short loc_18000B004
0x18000affc  movzx   eax, ax
0x18000afff  or      eax, 80070000h
0x18000b004  mov     [rsp+0B8h+var_38], eax
0x18000b00b  add     rsp, 0B8h
0x18000b012  retn
0x18000c00e  push    rbp
0x18000c010  sub     rsp, 80h
0x18000c017  mov     rbp, rdx
0x18000c01a  mov     rcx, [rcx]
0x18000c01d  mov     ecx, [rcx]; ExceptionCode
0x18000c01f  call    cs:__imp_RpcExceptionFilter
0x18000c025  nop
0x18000c026  add     rsp, 80h
0x18000c02d  pop     rbp
0x18000c02e  retn
```
