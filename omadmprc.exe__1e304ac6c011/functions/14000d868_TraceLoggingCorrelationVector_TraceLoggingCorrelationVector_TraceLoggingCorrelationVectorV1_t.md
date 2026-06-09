# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)

- ea: `0x14000d868`
- end: `0x14000d902`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e934`

## callees

- `0x14000271f`
- `0x14000d674`
- `0x140015690`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x14000d894`
- `RPCRT4!UuidCreate` at `0x14000d894`

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
0x14000d868  push    rbx
0x14000d86a  sub     rsp, 40h
0x14000d86e  mov     rax, cs:__security_cookie
0x14000d875  xor     rax, rsp
0x14000d878  mov     [rsp+48h+var_18], rax
0x14000d87d  mov     rbx, rcx
0x14000d880  mov     byte ptr [rcx+82h], 41h ; 'A'
0x14000d887  xorps   xmm0, xmm0
0x14000d88a  lea     rcx, [rsp+48h+Uuid]; Uuid
0x14000d88f  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x14000d894  call    cs:__imp_UuidCreate
0x14000d89b  nop     dword ptr [rax+rax+00h]
0x14000d8a0  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x14000d8a5  mov     rax, 1300000000h
0x14000d8af  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x14000d8b5  xor     edx, edx; Val
0x14000d8b7  mov     byte ptr [rbx+81h], 11h
0x14000d8be  mov     r8d, 81h; Size
0x14000d8c4  mov     rcx, rbx; void *
0x14000d8c7  mov     [rbx+88h], rax
0x14000d8ce  call    memset_0
0x14000d8d3  mov     r8, rbx
0x14000d8d6  lea     rcx, [rsp+48h+Uuid]
0x14000d8db  mov     edx, 0Ch
0x14000d8e0  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x14000d8e5  mov     rax, rbx
0x14000d8e8  mov     word ptr [rbx+10h], 2Eh ; '.'
0x14000d8ee  mov     rcx, [rsp+48h+var_18]
0x14000d8f3  xor     rcx, rsp; StackCookie
0x14000d8f6  call    __security_check_cookie
0x14000d8fb  add     rsp, 40h
0x14000d8ff  pop     rbx
0x14000d900  retn
```
