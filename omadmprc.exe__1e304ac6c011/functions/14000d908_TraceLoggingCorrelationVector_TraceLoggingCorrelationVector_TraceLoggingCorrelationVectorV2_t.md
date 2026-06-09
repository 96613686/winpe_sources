# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x14000d908`
- end: `0x14000d9a2`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dc4c`
- `0x14000e934`

## callees

- `0x14000271f`
- `0x14000d674`
- `0x140015690`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x14000d934`
- `RPCRT4!UuidCreate` at `0x14000d934`

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
0x14000d908  push    rbx
0x14000d90a  sub     rsp, 40h
0x14000d90e  mov     rax, cs:__security_cookie
0x14000d915  xor     rax, rsp
0x14000d918  mov     [rsp+48h+var_18], rax
0x14000d91d  mov     rbx, rcx
0x14000d920  mov     byte ptr [rcx+82h], 81h
0x14000d927  xorps   xmm0, xmm0
0x14000d92a  lea     rcx, [rsp+48h+Uuid]; Uuid
0x14000d92f  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x14000d934  call    cs:__imp_UuidCreate
0x14000d93b  nop     dword ptr [rax+rax+00h]
0x14000d940  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x14000d945  mov     rax, 1900000000h
0x14000d94f  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x14000d955  xor     edx, edx; Val
0x14000d957  mov     byte ptr [rbx+81h], 17h
0x14000d95e  mov     r8d, 81h; Size
0x14000d964  mov     rcx, rbx; void *
0x14000d967  mov     [rbx+88h], rax
0x14000d96e  call    memset_0
0x14000d973  mov     r8, rbx
0x14000d976  lea     rcx, [rsp+48h+Uuid]
0x14000d97b  mov     edx, 10h
0x14000d980  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x14000d985  mov     rax, rbx
0x14000d988  mov     word ptr [rbx+16h], 2Eh ; '.'
0x14000d98e  mov     rcx, [rsp+48h+var_18]
0x14000d993  xor     rcx, rsp; StackCookie
0x14000d996  call    __security_check_cookie
0x14000d99b  add     rsp, 40h
0x14000d99f  pop     rbx
0x14000d9a0  retn
```
