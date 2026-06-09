# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)

- ea: `0x180054ae4`
- end: `0x180054b77`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180054c40`
- `0x18005506c`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x180054960`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180054b10`
- `RPCRT4!UuidCreate` at `0x180054b10`

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
0x180054ae4  push    rbx
0x180054ae6  sub     rsp, 40h
0x180054aea  mov     rax, cs:__security_cookie
0x180054af1  xor     rax, rsp
0x180054af4  mov     [rsp+48h+var_18], rax
0x180054af9  mov     rbx, rcx
0x180054afc  mov     byte ptr [rcx+82h], 41h ; 'A'
0x180054b03  xorps   xmm0, xmm0
0x180054b06  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180054b0b  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180054b10  call    cs:__imp_UuidCreate
0x180054b16  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180054b1b  mov     rax, 1300000000h
0x180054b25  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180054b2b  xor     edx, edx; Val
0x180054b2d  mov     byte ptr [rbx+81h], 11h
0x180054b34  mov     r8d, 81h; Size
0x180054b3a  mov     rcx, rbx; void *
0x180054b3d  mov     [rbx+88h], rax
0x180054b44  call    memset_0
0x180054b49  mov     r8, rbx
0x180054b4c  lea     rcx, [rsp+48h+Uuid]
0x180054b51  mov     edx, 0Ch
0x180054b56  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180054b5b  mov     rax, rbx
0x180054b5e  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180054b64  mov     rcx, [rsp+48h+var_18]
0x180054b69  xor     rcx, rsp; StackCookie
0x180054b6c  call    __security_check_cookie
0x180054b71  add     rsp, 40h
0x180054b75  pop     rbx
0x180054b76  retn
```
