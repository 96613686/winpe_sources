# HTTP_TRACING_TABLE::`scalar deleting destructor'(uint)

- ea: `0x180001960`
- end: `0x18000199e`
- name: `??_GHTTP_TRACING_TABLE@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(HTTP_TRACING_TABLE *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180001960`

## import_xrefs

- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000197d`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000197d`

## pseudocode

```c
HTTP_TRACING_TABLE *__fastcall HTTP_TRACING_TABLE::`scalar deleting destructor'(HTTP_TRACING_TABLE *this, char a2)
{
  *(_QWORD *)this = &HTTP_TRACING_TABLE::`vftable';
  CLKRHashTable::~CLKRHashTable((HTTP_TRACING_TABLE *)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001960  mov     [rsp+arg_0], rbx
0x180001965  push    rdi
0x180001966  sub     rsp, 20h
0x18000196a  lea     rax, ??_7HTTP_TRACING_TABLE@@6B@; const HTTP_TRACING_TABLE::`vftable'
0x180001971  mov     rdi, rcx
0x180001974  mov     [rcx], rax
0x180001977  mov     ebx, edx
0x180001979  add     rcx, 8
0x18000197d  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180001983  test    bl, 1
0x180001986  jz      short loc_180001990
0x180001988  mov     rcx, rdi; Block
0x18000198b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001990  mov     rbx, [rsp+28h+arg_0]
0x180001995  mov     rax, rdi
0x180001998  add     rsp, 20h
0x18000199c  pop     rdi
0x18000199d  retn
```
