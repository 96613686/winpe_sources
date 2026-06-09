# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x18001c244`
- end: `0x18001c2d2`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c2d8`
- `0x18001cb04`
- `0x180025058`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18001c164`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001c270`
- `RPCRT4!UuidCreate` at `0x18001c270`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18001c244  push    rbx
0x18001c246  sub     rsp, 40h
0x18001c24a  mov     rax, cs:__security_cookie
0x18001c251  xor     rax, rsp
0x18001c254  mov     [rsp+48h+var_18], rax
0x18001c259  mov     rbx, rcx
0x18001c25c  mov     byte ptr [rcx+82h], 81h
0x18001c263  xorps   xmm0, xmm0
0x18001c266  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18001c26b  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18001c270  call    cs:__imp_UuidCreate
0x18001c276  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18001c27b  mov     rax, 1900000000h
0x18001c285  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18001c28b  xor     edx, edx; Val
0x18001c28d  mov     byte ptr [rbx+81h], 17h
0x18001c294  mov     r8d, 81h; Size
0x18001c29a  mov     rcx, rbx; void *
0x18001c29d  mov     [rbx+88h], rax
0x18001c2a4  call    memset_0
0x18001c2a9  mov     r8, rbx
0x18001c2ac  lea     rcx, [rsp+48h+Uuid]
0x18001c2b1  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18001c2b6  mov     rax, rbx
0x18001c2b9  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18001c2bf  mov     rcx, [rsp+48h+var_18]
0x18001c2c4  xor     rcx, rsp; StackCookie
0x18001c2c7  call    __security_check_cookie
0x18001c2cc  add     rsp, 40h
0x18001c2d0  pop     rbx
0x18001c2d1  retn
```
