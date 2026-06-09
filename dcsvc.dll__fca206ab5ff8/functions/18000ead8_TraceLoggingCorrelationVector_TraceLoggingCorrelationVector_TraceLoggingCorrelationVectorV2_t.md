# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x18000ead8`
- end: `0x18000eb66`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ed9c`

## callees

- `0x180001cf0`
- `0x1800026c8`
- `0x18000e990`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000eb04`
- `RPCRT4!UuidCreate` at `0x18000eb04`

## pseudocode

```c
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  __int64 v2; // rdx
  __int64 result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *(_BYTE *)(a1 + 130) = -127;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(_BYTE *)(a1 + 129) = 23;
  *(_QWORD *)(a1 + 136) = 0x1900000000LL;
  memset_0((void *)a1, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, v2, a1);
  result = a1;
  *(_WORD *)(a1 + 22) = 46;
  return result;
}

```

## disassembly

```asm
0x18000ead8  push    rbx
0x18000eada  sub     rsp, 40h
0x18000eade  mov     rax, cs:__security_cookie
0x18000eae5  xor     rax, rsp
0x18000eae8  mov     [rsp+48h+var_18], rax
0x18000eaed  mov     rbx, rcx
0x18000eaf0  mov     byte ptr [rcx+82h], 81h
0x18000eaf7  xorps   xmm0, xmm0
0x18000eafa  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18000eaff  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18000eb04  call    cs:__imp_UuidCreate
0x18000eb0a  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18000eb0f  mov     rax, 1900000000h
0x18000eb19  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18000eb1f  xor     edx, edx; Val
0x18000eb21  mov     byte ptr [rbx+81h], 17h
0x18000eb28  mov     r8d, 81h; Size
0x18000eb2e  mov     rcx, rbx; void *
0x18000eb31  mov     [rbx+88h], rax
0x18000eb38  call    memset_0
0x18000eb3d  mov     r8, rbx
0x18000eb40  lea     rcx, [rsp+48h+Uuid]
0x18000eb45  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18000eb4a  mov     rax, rbx
0x18000eb4d  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18000eb53  mov     rcx, [rsp+48h+var_18]
0x18000eb58  xor     rcx, rsp; StackCookie
0x18000eb5b  call    __security_check_cookie
0x18000eb60  add     rsp, 40h
0x18000eb64  pop     rbx
0x18000eb65  retn
```
