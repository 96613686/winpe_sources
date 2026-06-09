# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x18000cf98`
- end: `0x18000d02b`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017a44`

## callees

- `0x180009ce0`
- `0x180033e9a`
- `0x180033ed0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000cfc4`
- `RPCRT4!UuidCreate` at `0x18000cfc4`

## pseudocode

```c
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  __int64 result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *(_BYTE *)(a1 + 130) = -127;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(_BYTE *)(a1 + 129) = 23;
  *(_QWORD *)(a1 + 136) = 0x1900000000LL;
  memset_0((void *)a1, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, 16, a1);
  result = a1;
  *(_WORD *)(a1 + 22) = 46;
  return result;
}

```

## disassembly

```asm
0x18000cf98  push    rbx
0x18000cf9a  sub     rsp, 40h
0x18000cf9e  mov     rax, cs:__security_cookie
0x18000cfa5  xor     rax, rsp
0x18000cfa8  mov     [rsp+48h+var_18], rax
0x18000cfad  mov     rbx, rcx
0x18000cfb0  mov     byte ptr [rcx+82h], 81h
0x18000cfb7  xorps   xmm0, xmm0
0x18000cfba  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18000cfbf  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18000cfc4  call    cs:__imp_UuidCreate
0x18000cfca  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18000cfcf  mov     rax, 1900000000h
0x18000cfd9  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18000cfdf  xor     edx, edx; Val
0x18000cfe1  mov     byte ptr [rbx+81h], 17h
0x18000cfe8  mov     r8d, 81h; Size
0x18000cfee  mov     rcx, rbx; void *
0x18000cff1  mov     [rbx+88h], rax
0x18000cff8  call    memset_0
0x18000cffd  mov     r8, rbx
0x18000d000  lea     rcx, [rsp+48h+Uuid]
0x18000d005  mov     edx, 10h
0x18000d00a  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18000d00f  mov     rax, rbx
0x18000d012  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18000d018  mov     rcx, [rsp+48h+var_18]
0x18000d01d  xor     rcx, rsp; StackCookie
0x18000d020  call    __security_check_cookie
0x18000d025  add     rsp, 40h
0x18000d029  pop     rbx
0x18000d02a  retn
```
