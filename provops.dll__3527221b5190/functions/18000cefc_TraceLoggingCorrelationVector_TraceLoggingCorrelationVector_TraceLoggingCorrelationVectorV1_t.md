# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)

- ea: `0x18000cefc`
- end: `0x18000cf8f`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z`
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

- `RPCRT4!UuidCreate` at `0x18000cf28`
- `RPCRT4!UuidCreate` at `0x18000cf28`

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
0x18000cefc  push    rbx
0x18000cefe  sub     rsp, 40h
0x18000cf02  mov     rax, cs:__security_cookie
0x18000cf09  xor     rax, rsp
0x18000cf0c  mov     [rsp+48h+var_18], rax
0x18000cf11  mov     rbx, rcx
0x18000cf14  mov     byte ptr [rcx+82h], 41h ; 'A'
0x18000cf1b  xorps   xmm0, xmm0
0x18000cf1e  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18000cf23  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18000cf28  call    cs:__imp_UuidCreate
0x18000cf2e  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18000cf33  mov     rax, 1300000000h
0x18000cf3d  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18000cf43  xor     edx, edx; Val
0x18000cf45  mov     byte ptr [rbx+81h], 11h
0x18000cf4c  mov     r8d, 81h; Size
0x18000cf52  mov     rcx, rbx; void *
0x18000cf55  mov     [rbx+88h], rax
0x18000cf5c  call    memset_0
0x18000cf61  mov     r8, rbx
0x18000cf64  lea     rcx, [rsp+48h+Uuid]
0x18000cf69  mov     edx, 0Ch
0x18000cf6e  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18000cf73  mov     rax, rbx
0x18000cf76  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18000cf7c  mov     rcx, [rsp+48h+var_18]
0x18000cf81  xor     rcx, rsp; StackCookie
0x18000cf84  call    __security_check_cookie
0x18000cf89  add     rsp, 40h
0x18000cf8d  pop     rbx
0x18000cf8e  retn
```
