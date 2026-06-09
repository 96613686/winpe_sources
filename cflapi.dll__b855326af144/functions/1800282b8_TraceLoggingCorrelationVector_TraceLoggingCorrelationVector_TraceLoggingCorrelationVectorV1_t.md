# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)

- ea: `0x1800282b8`
- end: `0x18002834b`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z`
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

- `RPCRT4!UuidCreate` at `0x1800282e4`
- `RPCRT4!UuidCreate` at `0x1800282e4`

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
0x1800282b8  push    rbx
0x1800282ba  sub     rsp, 40h
0x1800282be  mov     rax, cs:__security_cookie
0x1800282c5  xor     rax, rsp
0x1800282c8  mov     [rsp+48h+var_18], rax
0x1800282cd  mov     rbx, rcx
0x1800282d0  mov     byte ptr [rcx+82h], 41h ; 'A'
0x1800282d7  xorps   xmm0, xmm0
0x1800282da  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800282df  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800282e4  call    cs:__imp_UuidCreate
0x1800282ea  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1800282ef  mov     rax, 1300000000h
0x1800282f9  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800282ff  xor     edx, edx; Val
0x180028301  mov     byte ptr [rbx+81h], 11h
0x180028308  mov     r8d, 81h; Size
0x18002830e  mov     rcx, rbx; void *
0x180028311  mov     [rbx+88h], rax
0x180028318  call    memset_0
0x18002831d  mov     r8, rbx
0x180028320  lea     rcx, [rsp+48h+Uuid]
0x180028325  mov     edx, 0Ch
0x18002832a  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18002832f  mov     rax, rbx
0x180028332  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180028338  mov     rcx, [rsp+48h+var_18]
0x18002833d  xor     rcx, rsp; StackCookie
0x180028340  call    __security_check_cookie
0x180028345  add     rsp, 40h
0x180028349  pop     rbx
0x18002834a  retn
```
