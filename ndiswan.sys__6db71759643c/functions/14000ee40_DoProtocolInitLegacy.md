# DoProtocolInitLegacy

- ea: `0x14000ee40`
- end: `0x14000ef5c`
- name: `DoProtocolInitLegacy`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140039008`

## callees

- `0x140016700`

## import_xrefs

- `NDIS!NdisRegisterProtocol` at `0x14000ef40`
- `NDIS!NdisRegisterProtocol` at `0x14000ef40`

## pseudocode

```c
__int64 __fastcall DoProtocolInitLegacy(__int64 a1)
{
  _QWORD v2[30]; // [rsp+20h] [rbp-99h] BYREF
  unsigned int v3; // [rsp+120h] [rbp+67h] BYREF
  int v4; // [rsp+124h] [rbp+6Bh]

  v4 = HIDWORD(a1);
  v3 = 0;
  memset(v2, 0, 0xD0u);
  v2[11] = 1835034;
  v2[12] = L"NdisWanLegacy";
  LOWORD(v2[0]) = 5;
  v2[1] = ProtoOpenAdapterCompleteLegacy;
  v2[4] = 0;
  v2[2] = ProtoCloseAdapterCompleteLegacy;
  v2[13] = 0;
  v2[3] = ProtoWanSendCompleteLegacy;
  v2[5] = ProtoResetCompleteLegacy;
  v2[6] = ProtoRequestCompleteLegacy;
  v2[7] = &ProtoWanReceiveIndicationLegacy;
  v2[8] = ProtoReceiveCompleteLegacy;
  v2[9] = ProtoIndicateStatusLegacy;
  v2[10] = BwcEtwTraceQosPacketDrop;
  v2[14] = &ProtoBindAdapterLegacy;
  v2[15] = &ProtoUnbindAdapterLegacy;
  v2[16] = ProtoPnPEventLegacy;
  v2[17] = ProtoUnloadLegacy;
  ((void (__fastcall *)(unsigned int *, __int64 *, _QWORD *, __int64))NdisRegisterProtocol)(
    &v3,
    &qword_14001E2E8,
    v2,
    208);
  return v3;
}

```

## disassembly

```asm
0x14000ee40  mov     [rsp-8+arg_0], rcx
0x14000ee45  push    rbp
0x14000ee46  push    rbx
0x14000ee47  push    rsi
0x14000ee48  push    rdi
0x14000ee49  lea     rbp, [rsp-3Fh]
0x14000ee4e  sub     rsp, 0F8h
0x14000ee55  xor     edx, edx; Val
0x14000ee57  mov     dword ptr [rbp+57h+arg_0], 0
0x14000ee5e  mov     r8d, 0D0h; Size
0x14000ee64  lea     rcx, [rsp+110h+var_F0]; void *
0x14000ee69  call    memset
0x14000ee6e  lea     rax, aNdiswanlegacy; "NdisWanLegacy"
0x14000ee75  mov     [rbp+57h+var_98], 1C001Ah
0x14000ee7d  mov     [rbp+57h+var_90], rax
0x14000ee81  lea     r8, [rsp+110h+var_F0]
0x14000ee86  lea     rax, ProtoOpenAdapterCompleteLegacy
0x14000ee8d  mov     [rsp+110h+var_F0], 5
0x14000ee94  mov     [rsp+110h+var_E8], rax
0x14000ee99  lea     rdx, qword_14001E2E8
0x14000eea0  lea     rax, ProtoCloseAdapterCompleteLegacy
0x14000eea7  mov     [rbp+57h+var_D0], 0
0x14000eeaf  mov     [rsp+110h+var_E0], rax
0x14000eeb4  lea     rcx, [rbp+57h+arg_0]
0x14000eeb8  lea     rax, ProtoWanSendCompleteLegacy
0x14000eebf  mov     [rbp+57h+var_88], 0
0x14000eec7  mov     [rsp+110h+var_D8], rax
0x14000eecc  mov     r9d, 0D0h
0x14000eed2  lea     rax, ProtoResetCompleteLegacy
0x14000eed9  mov     [rbp+57h+var_C8], rax
0x14000eedd  lea     rax, ProtoRequestCompleteLegacy
0x14000eee4  mov     [rbp+57h+var_C0], rax
0x14000eee8  lea     rax, ProtoWanReceiveIndicationLegacy
0x14000eeef  mov     [rbp+57h+var_B8], rax
0x14000eef3  lea     rax, ProtoReceiveCompleteLegacy
0x14000eefa  mov     [rbp+57h+var_B0], rax
0x14000eefe  lea     rax, ProtoIndicateStatusLegacy
0x14000ef05  mov     [rbp+57h+var_A8], rax
0x14000ef09  lea     rax, BwcEtwTraceQosPacketDrop
0x14000ef10  mov     [rbp+57h+var_A0], rax
0x14000ef14  lea     rax, ProtoBindAdapterLegacy
0x14000ef1b  mov     [rbp+57h+var_80], rax
0x14000ef1f  lea     rax, ProtoUnbindAdapterLegacy
0x14000ef26  mov     [rbp+57h+var_78], rax
0x14000ef2a  lea     rax, ProtoPnPEventLegacy
0x14000ef31  mov     [rbp+57h+var_70], rax
0x14000ef35  lea     rax, ProtoUnloadLegacy
0x14000ef3c  mov     [rbp+57h+var_68], rax
0x14000ef40  call    cs:__imp_NdisRegisterProtocol
0x14000ef47  nop     dword ptr [rax+rax+00h]
0x14000ef4c  mov     eax, dword ptr [rbp+57h+arg_0]
0x14000ef4f  add     rsp, 0F8h
0x14000ef56  pop     rdi
0x14000ef57  pop     rsi
0x14000ef58  pop     rbx
0x14000ef59  pop     rbp
0x14000ef5a  retn
```
