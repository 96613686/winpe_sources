# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x180028354`
- end: `0x1800283e7`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002945c`
- `0x18002b7d8`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x180027d94`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180028380`
- `RPCRT4!UuidCreate` at `0x180028380`

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
0x180028354  push    rbx
0x180028356  sub     rsp, 40h
0x18002835a  mov     rax, cs:__security_cookie
0x180028361  xor     rax, rsp
0x180028364  mov     [rsp+48h+var_18], rax
0x180028369  mov     rbx, rcx
0x18002836c  mov     byte ptr [rcx+82h], 81h
0x180028373  xorps   xmm0, xmm0
0x180028376  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18002837b  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180028380  call    cs:__imp_UuidCreate
0x180028386  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18002838b  mov     rax, 1900000000h
0x180028395  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18002839b  xor     edx, edx; Val
0x18002839d  mov     byte ptr [rbx+81h], 17h
0x1800283a4  mov     r8d, 81h; Size
0x1800283aa  mov     rcx, rbx; void *
0x1800283ad  mov     [rbx+88h], rax
0x1800283b4  call    memset_0
0x1800283b9  mov     r8, rbx
0x1800283bc  lea     rcx, [rsp+48h+Uuid]
0x1800283c1  mov     edx, 10h
0x1800283c6  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1800283cb  mov     rax, rbx
0x1800283ce  mov     word ptr [rbx+16h], 2Eh ; '.'
0x1800283d4  mov     rcx, [rsp+48h+var_18]
0x1800283d9  xor     rcx, rsp; StackCookie
0x1800283dc  call    __security_check_cookie
0x1800283e1  add     rsp, 40h
0x1800283e5  pop     rbx
0x1800283e6  retn
```
