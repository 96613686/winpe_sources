# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x180020950`
- end: `0x1800209ea`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180020c74`
- `0x180021314`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180020728`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002097c`
- `RPCRT4!UuidCreate` at `0x18002097c`

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
0x180020950  push    rbx
0x180020952  sub     rsp, 40h
0x180020956  mov     rax, cs:__security_cookie
0x18002095d  xor     rax, rsp
0x180020960  mov     [rsp+48h+var_18], rax
0x180020965  mov     rbx, rcx
0x180020968  mov     byte ptr [rcx+82h], 81h
0x18002096f  xorps   xmm0, xmm0
0x180020972  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180020977  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18002097c  call    cs:__imp_UuidCreate
0x180020983  nop     dword ptr [rax+rax+00h]
0x180020988  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18002098d  mov     rax, 1900000000h
0x180020997  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18002099d  xor     edx, edx; Val
0x18002099f  mov     byte ptr [rbx+81h], 17h
0x1800209a6  mov     r8d, 81h; Size
0x1800209ac  mov     rcx, rbx; void *
0x1800209af  mov     [rbx+88h], rax
0x1800209b6  call    memset_0
0x1800209bb  mov     r8, rbx
0x1800209be  lea     rcx, [rsp+48h+Uuid]
0x1800209c3  mov     edx, 10h
0x1800209c8  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1800209cd  mov     rax, rbx
0x1800209d0  mov     word ptr [rbx+16h], 2Eh ; '.'
0x1800209d6  mov     rcx, [rsp+48h+var_18]
0x1800209db  xor     rcx, rsp; StackCookie
0x1800209de  call    __security_check_cookie
0x1800209e3  add     rsp, 40h
0x1800209e7  pop     rbx
0x1800209e8  retn
```
