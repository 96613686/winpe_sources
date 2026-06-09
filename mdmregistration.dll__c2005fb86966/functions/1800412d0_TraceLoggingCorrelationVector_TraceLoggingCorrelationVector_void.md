# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x1800412d0`
- end: `0x18004136a`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `154`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180044194`
- `0x180044408`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x180041148`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800412fc`
- `RPCRT4!UuidCreate` at `0x1800412fc`

## pseudocode

```c
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
0x1800412d0  push    rbx
0x1800412d2  sub     rsp, 40h
0x1800412d6  mov     rax, cs:__security_cookie
0x1800412dd  xor     rax, rsp
0x1800412e0  mov     [rsp+48h+var_18], rax
0x1800412e5  mov     rbx, rcx
0x1800412e8  mov     byte ptr [rcx+82h], 41h ; 'A'
0x1800412ef  xorps   xmm0, xmm0
0x1800412f2  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800412f7  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800412fc  call    cs:__imp_UuidCreate
0x180041303  nop     dword ptr [rax+rax+00h]
0x180041308  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18004130d  mov     rax, 1300000000h
0x180041317  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18004131d  xor     edx, edx; Val
0x18004131f  mov     byte ptr [rbx+81h], 11h
0x180041326  mov     r8d, 81h; Size
0x18004132c  mov     rcx, rbx; void *
0x18004132f  mov     [rbx+88h], rax
0x180041336  call    memset_0
0x18004133b  mov     r8, rbx
0x18004133e  lea     rcx, [rsp+48h+Uuid]
0x180041343  mov     edx, 0Ch
0x180041348  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18004134d  mov     rax, rbx
0x180041350  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180041356  mov     rcx, [rsp+48h+var_18]
0x18004135b  xor     rcx, rsp; StackCookie
0x18004135e  call    __security_check_cookie
0x180041363  add     rsp, 40h
0x180041367  pop     rbx
0x180041368  retn
```
