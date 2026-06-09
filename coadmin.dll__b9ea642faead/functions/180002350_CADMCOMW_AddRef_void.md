# CADMCOMW::AddRef(void)

- ea: `0x180002350`
- end: `0x180002384`
- name: `?AddRef@CADMCOMW@@UEAAKXZ`
- size: `52`
- prototype: `unsigned int __fastcall(CADMCOMW *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002350`

## import_xrefs

- `IisRTL!WriteRefTraceLog` at `0x180002375`
- `IisRTL!WriteRefTraceLog` at `0x180002375`

## pseudocode

```c
__int64 __fastcall CADMCOMW::AddRef(CADMCOMW *this)
{
  signed __int32 v1; // ebx

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 1u);
  if ( CADMCOMW::sm_pDbgRefTraceLog )
    WriteRefTraceLog(CADMCOMW::sm_pDbgRefTraceLog, (unsigned int)(v1 + 1), this);
  return (unsigned int)(v1 + 1);
}

```

## disassembly

```asm
0x180002350  push    rbx
0x180002352  sub     rsp, 20h
0x180002356  mov     ebx, 1
0x18000235b  lock xadd [rcx+8], ebx
0x180002360  mov     rax, cs:?sm_pDbgRefTraceLog@CADMCOMW@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * CADMCOMW::sm_pDbgRefTraceLog
0x180002367  test    rax, rax
0x18000236a  jz      short loc_18000237B
0x18000236c  mov     r8, rcx
0x18000236f  lea     edx, [rbx+1]
0x180002372  mov     rcx, rax
0x180002375  call    cs:__imp_WriteRefTraceLog
0x18000237b  lea     eax, [rbx+1]
0x18000237e  add     rsp, 20h
0x180002382  pop     rbx
0x180002383  retn
```
