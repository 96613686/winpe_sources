# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x1800071b0`
- end: `0x180007243`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `147`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007cc0`
- `0x180009b84`
- `0x180016f5c`

## callees

- `0x18000636c`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800071dc`
- `RPCRT4!UuidCreate` at `0x1800071dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(
        TraceLoggingCorrelationVector *this)
{
  TraceLoggingCorrelationVector *result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *((_BYTE *)this + 130) = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  *((_BYTE *)this + 129) = 17;
  *((_QWORD *)this + 17) = 0x1300000000LL;
  memset_0(this, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, 12, this);
  result = this;
  *((_WORD *)this + 8) = 46;
  return result;
}

```

## disassembly

```asm
0x1800071b0  push    rbx
0x1800071b2  sub     rsp, 40h
0x1800071b6  mov     rax, cs:__security_cookie
0x1800071bd  xor     rax, rsp
0x1800071c0  mov     [rsp+48h+var_18], rax
0x1800071c5  mov     rbx, rcx
0x1800071c8  mov     byte ptr [rcx+82h], 41h ; 'A'
0x1800071cf  xorps   xmm0, xmm0
0x1800071d2  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800071d7  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800071dc  call    cs:__imp_UuidCreate
0x1800071e2  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1800071e7  mov     rax, 1300000000h
0x1800071f1  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800071f7  xor     edx, edx; Val
0x1800071f9  mov     byte ptr [rbx+81h], 11h
0x180007200  mov     r8d, 81h; Size
0x180007206  mov     rcx, rbx; void *
0x180007209  mov     [rbx+88h], rax
0x180007210  call    memset_0
0x180007215  mov     r8, rbx
0x180007218  lea     rcx, [rsp+48h+Uuid]
0x18000721d  mov     edx, 0Ch
0x180007222  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180007227  mov     rax, rbx
0x18000722a  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180007230  mov     rcx, [rsp+48h+var_18]
0x180007235  xor     rcx, rsp; StackCookie
0x180007238  call    __security_check_cookie
0x18000723d  add     rsp, 40h
0x180007241  pop     rbx
0x180007242  retn
```
