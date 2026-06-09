# PcQoSPCopyFlow

- ea: `0x140010040`
- end: `0x1400100c5`
- name: `PcQoSPCopyFlow`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x14000adf8`
- `0x14000c75c`
- `0x140013110`

## pseudocode

```c
__int64 __fastcall PcQoSPCopyFlow(__int64 *a1)
{
  __int64 v1; // r8
  _QWORD *v2; // rcx
  unsigned int Flow; // eax
  _QWORD v5[2]; // [rsp+50h] [rbp-28h] BYREF

  v1 = *a1;
  v2 = (_QWORD *)a1[1];
  v5[1] = *((_QWORD *)&QOS_FLOW_PROVIDER_GUID + 1);
  v5[0] = v1;
  Flow = PcpCreateFlow(
           v2,
           2,
           0,
           0,
           *(_DWORD *)(v1 + 608),
           (unsigned __int8)*(_DWORD *)(v1 + 48),
           *(void **)(v1 + 600),
           0,
           (__int64)v5);
  return PcpNormalizeNtStatus(Flow);
}

```

## disassembly

```asm
0x140010040  mov     r11, rsp
0x140010043  sub     rsp, 78h
0x140010047  mov     rax, cs:__security_cookie
0x14001004e  xor     rax, rsp
0x140010051  mov     [rsp+78h+var_18], rax
0x140010056  mov     r8, [rcx]
0x140010059  xor     r9d, r9d
0x14001005c  movups  xmm0, cs:QOS_FLOW_PROVIDER_GUID
0x140010063  mov     rcx, [rcx+8]
0x140010067  movdqu  [rsp+78h+var_28], xmm0
0x14001006d  mov     [r11-28h], r8
0x140010071  mov     eax, [r8+30h]
0x140010075  movzx   edx, al
0x140010078  lea     rax, [r11-28h]
0x14001007c  mov     [r11-38h], rax
0x140010080  mov     rax, [r8+258h]
0x140010087  mov     [rsp+78h+var_40], 0
0x14001008c  mov     [r11-48h], rax
0x140010090  mov     eax, [r8+260h]
0x140010097  xor     r8d, r8d
0x14001009a  mov     [rsp+78h+var_50], edx
0x14001009e  lea     edx, [r9+2]
0x1400100a2  mov     [rsp+78h+var_58], eax
0x1400100a6  call    PcpCreateFlow
0x1400100ab  mov     ecx, eax
0x1400100ad  call    PcpNormalizeNtStatus
0x1400100b2  mov     rcx, [rsp+78h+var_18]
0x1400100b7  xor     rcx, rsp; StackCookie
0x1400100ba  call    __security_check_cookie
0x1400100bf  add     rsp, 78h
0x1400100c3  retn
```
