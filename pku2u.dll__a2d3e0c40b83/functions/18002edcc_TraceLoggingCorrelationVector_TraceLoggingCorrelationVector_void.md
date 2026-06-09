# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x18002edcc`
- end: `0x18002ee5a`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `142`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022c9c`

## callees

- `0x1800210f0`
- `0x180021a54`
- `0x18002ed2c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002edf8`
- `RPCRT4!UuidCreate` at `0x18002edf8`

## pseudocode

```c
TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(
        TraceLoggingCorrelationVector *this)
{
  __int64 v2; // rdx
  TraceLoggingCorrelationVector *result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *((_BYTE *)this + 130) = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  *((_BYTE *)this + 129) = 17;
  *((_QWORD *)this + 17) = 0x1300000000LL;
  memset_0(this, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, v2, this);
  result = this;
  *((_WORD *)this + 8) = 46;
  return result;
}

```

## disassembly

```asm
0x18002edcc  push    rbx
0x18002edce  sub     rsp, 40h
0x18002edd2  mov     rax, cs:__security_cookie
0x18002edd9  xor     rax, rsp
0x18002eddc  mov     [rsp+48h+var_18], rax
0x18002ede1  mov     rbx, rcx
0x18002ede4  mov     byte ptr [rcx+82h], 41h ; 'A'
0x18002edeb  xorps   xmm0, xmm0
0x18002edee  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18002edf3  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18002edf8  call    cs:__imp_UuidCreate
0x18002edfe  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18002ee03  mov     rax, 1300000000h
0x18002ee0d  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18002ee13  xor     edx, edx; Val
0x18002ee15  mov     byte ptr [rbx+81h], 11h
0x18002ee1c  mov     r8d, 81h; Size
0x18002ee22  mov     rcx, rbx; void *
0x18002ee25  mov     [rbx+88h], rax
0x18002ee2c  call    memset_0
0x18002ee31  mov     r8, rbx
0x18002ee34  lea     rcx, [rsp+48h+Uuid]
0x18002ee39  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18002ee3e  mov     rax, rbx
0x18002ee41  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18002ee47  mov     rcx, [rsp+48h+var_18]
0x18002ee4c  xor     rcx, rsp; StackCookie
0x18002ee4f  call    __security_check_cookie
0x18002ee54  add     rsp, 40h
0x18002ee58  pop     rbx
0x18002ee59  retn
```
