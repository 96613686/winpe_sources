# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x18002e0f4`
- end: `0x18002e15b`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013250`

## callees

- `0x180014330`
- `0x18002e080`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002e120`
- `RPCRT4!UuidCreate` at `0x18002e120`

## pseudocode

```c
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  UUID v3; // [rsp+20h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-28h] BYREF

  *(_BYTE *)(a1 + 130) = -127;
  Uuid = 0;
  UuidCreate(&Uuid);
  v3 = Uuid;
  TraceLoggingCorrelationVector::CreateCvFromGuid<16>(a1, &v3);
  return a1;
}

```

## disassembly

```asm
0x18002e0f4  push    rbx
0x18002e0f6  sub     rsp, 50h
0x18002e0fa  mov     rax, cs:__security_cookie
0x18002e101  xor     rax, rsp
0x18002e104  mov     [rsp+58h+var_18], rax
0x18002e109  mov     rbx, rcx
0x18002e10c  mov     byte ptr [rcx+82h], 81h
0x18002e113  xorps   xmm0, xmm0
0x18002e116  lea     rcx, [rsp+58h+Uuid]; Uuid
0x18002e11b  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x18002e120  call    cs:__imp_UuidCreate
0x18002e127  nop     dword ptr [rax+rax+00h]
0x18002e12c  movaps  xmm0, xmmword ptr [rsp+58h+Uuid.Data1]
0x18002e131  lea     rdx, [rsp+58h+var_38]
0x18002e136  mov     rcx, rbx
0x18002e139  movdqa  [rsp+58h+var_38], xmm0
0x18002e13f  call    ??$CreateCvFromGuid@$0BA@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<16>(_GUID)
0x18002e144  mov     rax, rbx
0x18002e147  mov     rcx, [rsp+58h+var_18]
0x18002e14c  xor     rcx, rsp; StackCookie
0x18002e14f  call    __security_check_cookie
0x18002e154  add     rsp, 50h
0x18002e158  pop     rbx
0x18002e159  retn
```
