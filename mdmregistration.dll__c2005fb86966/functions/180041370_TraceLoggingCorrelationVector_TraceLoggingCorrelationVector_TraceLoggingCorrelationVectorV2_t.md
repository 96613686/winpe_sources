# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x180041370`
- end: `0x18004140a`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180044194`
- `0x180044afc`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x180041148`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18004139c`
- `RPCRT4!UuidCreate` at `0x18004139c`

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
0x180041370  push    rbx
0x180041372  sub     rsp, 40h
0x180041376  mov     rax, cs:__security_cookie
0x18004137d  xor     rax, rsp
0x180041380  mov     [rsp+48h+var_18], rax
0x180041385  mov     rbx, rcx
0x180041388  mov     byte ptr [rcx+82h], 81h
0x18004138f  xorps   xmm0, xmm0
0x180041392  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180041397  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18004139c  call    cs:__imp_UuidCreate
0x1800413a3  nop     dword ptr [rax+rax+00h]
0x1800413a8  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1800413ad  mov     rax, 1900000000h
0x1800413b7  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800413bd  xor     edx, edx; Val
0x1800413bf  mov     byte ptr [rbx+81h], 17h
0x1800413c6  mov     r8d, 81h; Size
0x1800413cc  mov     rcx, rbx; void *
0x1800413cf  mov     [rbx+88h], rax
0x1800413d6  call    memset_0
0x1800413db  mov     r8, rbx
0x1800413de  lea     rcx, [rsp+48h+Uuid]
0x1800413e3  mov     edx, 10h
0x1800413e8  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1800413ed  mov     rax, rbx
0x1800413f0  mov     word ptr [rbx+16h], 2Eh ; '.'
0x1800413f6  mov     rcx, [rsp+48h+var_18]
0x1800413fb  xor     rcx, rsp; StackCookie
0x1800413fe  call    __security_check_cookie
0x180041403  add     rsp, 40h
0x180041407  pop     rbx
0x180041408  retn
```
