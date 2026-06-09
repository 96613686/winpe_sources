# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)

- ea: `0x1800208b0`
- end: `0x18002094a`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021314`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180020728`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800208dc`
- `RPCRT4!UuidCreate` at `0x1800208dc`

## pseudocode

```c
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  __int64 result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *(_BYTE *)(a1 + 130) = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(_BYTE *)(a1 + 129) = 17;
  *(_QWORD *)(a1 + 136) = 0x1300000000LL;
  memset_0((void *)a1, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, 12, a1);
  result = a1;
  *(_WORD *)(a1 + 16) = 46;
  return result;
}

```

## disassembly

```asm
0x1800208b0  push    rbx
0x1800208b2  sub     rsp, 40h
0x1800208b6  mov     rax, cs:__security_cookie
0x1800208bd  xor     rax, rsp
0x1800208c0  mov     [rsp+48h+var_18], rax
0x1800208c5  mov     rbx, rcx
0x1800208c8  mov     byte ptr [rcx+82h], 41h ; 'A'
0x1800208cf  xorps   xmm0, xmm0
0x1800208d2  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800208d7  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800208dc  call    cs:__imp_UuidCreate
0x1800208e3  nop     dword ptr [rax+rax+00h]
0x1800208e8  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1800208ed  mov     rax, 1300000000h
0x1800208f7  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800208fd  xor     edx, edx; Val
0x1800208ff  mov     byte ptr [rbx+81h], 11h
0x180020906  mov     r8d, 81h; Size
0x18002090c  mov     rcx, rbx; void *
0x18002090f  mov     [rbx+88h], rax
0x180020916  call    memset_0
0x18002091b  mov     r8, rbx
0x18002091e  lea     rcx, [rsp+48h+Uuid]
0x180020923  mov     edx, 0Ch
0x180020928  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18002092d  mov     rax, rbx
0x180020930  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180020936  mov     rcx, [rsp+48h+var_18]
0x18002093b  xor     rcx, rsp; StackCookie
0x18002093e  call    __security_check_cookie
0x180020943  add     rsp, 40h
0x180020947  pop     rbx
0x180020948  retn
```
