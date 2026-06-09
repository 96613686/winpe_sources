# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x18001dc54`
- end: `0x18001dce2`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e478`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x18001db74`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001dc80`
- `RPCRT4!UuidCreate` at `0x18001dc80`

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
0x18001dc54  push    rbx
0x18001dc56  sub     rsp, 40h
0x18001dc5a  mov     rax, cs:__security_cookie
0x18001dc61  xor     rax, rsp
0x18001dc64  mov     [rsp+48h+var_18], rax
0x18001dc69  mov     rbx, rcx
0x18001dc6c  mov     byte ptr [rcx+82h], 81h
0x18001dc73  xorps   xmm0, xmm0
0x18001dc76  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18001dc7b  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18001dc80  call    cs:__imp_UuidCreate
0x18001dc86  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18001dc8b  mov     rax, 1900000000h
0x18001dc95  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18001dc9b  xor     edx, edx; Val
0x18001dc9d  mov     byte ptr [rbx+81h], 17h
0x18001dca4  mov     r8d, 81h; Size
0x18001dcaa  mov     rcx, rbx; void *
0x18001dcad  mov     [rbx+88h], rax
0x18001dcb4  call    memset_0
0x18001dcb9  mov     r8, rbx
0x18001dcbc  lea     rcx, [rsp+48h+Uuid]
0x18001dcc1  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18001dcc6  mov     rax, rbx
0x18001dcc9  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18001dccf  mov     rcx, [rsp+48h+var_18]
0x18001dcd4  xor     rcx, rsp; StackCookie
0x18001dcd7  call    __security_check_cookie
0x18001dcdc  add     rsp, 40h
0x18001dce0  pop     rbx
0x18001dce1  retn
```
