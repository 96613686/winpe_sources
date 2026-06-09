# CADMCOMW::Release(void)

- ea: `0x180008430`
- end: `0x180008497`
- name: `?Release@CADMCOMW@@UEAAKXZ`
- size: `103`
- prototype: `unsigned int __fastcall(CADMCOMW *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010a4`
- `0x180001bd4`
- `0x180008430`
- `0x18000dba8`

## import_xrefs

- `IisRTL!WriteRefTraceLog` at `0x18000845a`
- `IisRTL!WriteRefTraceLog` at `0x18000845a`

## pseudocode

```c
__int64 __fastcall CADMCOMW::Release(CADMCOMW *this)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( CADMCOMW::sm_pDbgRefTraceLog )
    WriteRefTraceLog(CADMCOMW::sm_pDbgRefTraceLog, -v2, this);
  if ( v2 == 1 )
  {
    CADMCOMW::RemoveObjectFromList(this, 0);
  }
  else if ( !v2 && this )
  {
    CADMCOMW::~CADMCOMW(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180008430  mov     [rsp+arg_0], rbx
0x180008435  push    rdi
0x180008436  sub     rsp, 20h
0x18000843a  mov     rdi, rcx
0x18000843d  or      ebx, 0FFFFFFFFh
0x180008440  lock xadd [rcx+8], ebx
0x180008445  mov     rcx, cs:?sm_pDbgRefTraceLog@CADMCOMW@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * CADMCOMW::sm_pDbgRefTraceLog
0x18000844c  dec     ebx
0x18000844e  test    rcx, rcx
0x180008451  jz      short loc_180008460
0x180008453  mov     edx, ebx
0x180008455  mov     r8, rdi
0x180008458  neg     edx
0x18000845a  call    cs:__imp_WriteRefTraceLog
0x180008460  cmp     ebx, 1
0x180008463  jnz     short loc_180008471
0x180008465  xor     edx, edx; int
0x180008467  mov     rcx, rdi; this
0x18000846a  call    ?RemoveObjectFromList@CADMCOMW@@AEAAHH@Z; CADMCOMW::RemoveObjectFromList(int)
0x18000846f  jmp     short loc_18000848A
0x180008471  test    ebx, ebx
0x180008473  jnz     short loc_18000848A
0x180008475  test    rdi, rdi
0x180008478  jz      short loc_18000848A
0x18000847a  mov     rcx, rdi; this
0x18000847d  call    ??1CADMCOMW@@QEAA@XZ; CADMCOMW::~CADMCOMW(void)
0x180008482  mov     rcx, rdi; Block
0x180008485  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000848a  mov     eax, ebx
0x18000848c  mov     rbx, [rsp+28h+arg_0]
0x180008491  add     rsp, 20h
0x180008495  pop     rdi
0x180008496  retn
```
