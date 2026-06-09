# ISAPI_CONTEXT::DereferenceIsapiContext(void)

- ea: `0x180005e34`
- end: `0x180005e81`
- name: `?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ`
- size: `77`
- prototype: `void __fastcall(ISAPI_CONTEXT *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180003744`
- `0x1800038ec`
- `0x180003ef0`
- `0x180004b70`
- `0x180005ff4`
- `0x180006588`
- `0x1800068bc`
- `0x180006970`
- `0x180009980`
- `0x18000a1ec`
- `0x18000a820`

## callees

- `0x180005dc8`
- `0x180005e34`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180005e5f`
- `iisutil!WriteRefTraceLog` at `0x180005e5f`

## pseudocode

```c
void __fastcall ISAPI_CONTEXT::DereferenceIsapiContext(ISAPI_CONTEXT *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 65);
  if ( ISAPI_CONTEXT::sm_pTraceLog )
    WriteRefTraceLog(ISAPI_CONTEXT::sm_pTraceLog, v2, this);
  if ( !v2 )
  {
    if ( this )
      ISAPI_CONTEXT::~ISAPI_CONTEXT(this);
  }
}

```

## disassembly

```asm
0x180005e34  mov     [rsp+arg_0], rbx
0x180005e39  push    rdi
0x180005e3a  sub     rsp, 20h
0x180005e3e  mov     rbx, rcx
0x180005e41  or      edi, 0FFFFFFFFh
0x180005e44  lock xadd [rcx+104h], edi
0x180005e4c  mov     rcx, cs:?sm_pTraceLog@ISAPI_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_CONTEXT::sm_pTraceLog
0x180005e53  dec     edi
0x180005e55  test    rcx, rcx
0x180005e58  jz      short loc_180005E65
0x180005e5a  mov     r8, rbx
0x180005e5d  mov     edx, edi
0x180005e5f  call    cs:__imp_WriteRefTraceLog
0x180005e65  test    edi, edi
0x180005e67  jnz     short loc_180005E76
0x180005e69  test    rbx, rbx
0x180005e6c  jz      short loc_180005E76
0x180005e6e  mov     rcx, rbx; this
0x180005e71  call    ??1ISAPI_CONTEXT@@AEAA@XZ; ISAPI_CONTEXT::~ISAPI_CONTEXT(void)
0x180005e76  mov     rbx, [rsp+28h+arg_0]
0x180005e7b  add     rsp, 20h
0x180005e7f  pop     rdi
0x180005e80  retn
```
