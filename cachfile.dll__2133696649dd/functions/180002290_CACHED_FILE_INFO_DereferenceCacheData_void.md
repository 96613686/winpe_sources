# CACHED_FILE_INFO::DereferenceCacheData(void)

- ea: `0x180002290`
- end: `0x1800022eb`
- name: `?DereferenceCacheData@CACHED_FILE_INFO@@UEAAXXZ`
- size: `91`
- prototype: `void __fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002290`
- `0x180002300`
- `0x180002920`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800022e3`
- `iisutil!WriteRefTraceLog` at `0x1800022e3`

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::DereferenceCacheData(CACHED_FILE_INFO *this)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 65);
  if ( g_pTraceLog )
    WriteRefTraceLog(g_pTraceLog, v2, this);
  if ( !v2 )
  {
    if ( this )
    {
      CACHED_FILE_INFO::~CACHED_FILE_INFO(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x180002290  mov     [rsp+arg_0], rbx
0x180002295  push    rdi
0x180002296  sub     rsp, 20h
0x18000229a  mov     rdi, rcx
0x18000229d  mov     ebx, 0FFFFFFFFh
0x1800022a2  lock xadd [rcx+104h], ebx
0x1800022aa  mov     rcx, cs:?g_pTraceLog@@3PEAU_TRACE_LOG@@EA; _TRACE_LOG * g_pTraceLog
0x1800022b1  dec     ebx
0x1800022b3  test    rcx, rcx
0x1800022b6  jnz     short loc_1800022DE
0x1800022b8  test    ebx, ebx
0x1800022ba  jz      short loc_1800022C7
0x1800022bc  mov     rbx, [rsp+28h+arg_0]
0x1800022c1  add     rsp, 20h
0x1800022c5  pop     rdi
0x1800022c6  retn
0x1800022c7  test    rdi, rdi
0x1800022ca  jz      short loc_1800022BC
0x1800022cc  mov     rcx, rdi; this
0x1800022cf  call    ??1CACHED_FILE_INFO@@AEAA@XZ; CACHED_FILE_INFO::~CACHED_FILE_INFO(void)
0x1800022d4  mov     rcx, rdi; Block
0x1800022d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800022dc  jmp     short loc_1800022BC
0x1800022de  mov     r8, rdi
0x1800022e1  mov     edx, ebx
0x1800022e3  call    cs:__imp_WriteRefTraceLog
0x1800022e9  jmp     short loc_1800022B8
```
