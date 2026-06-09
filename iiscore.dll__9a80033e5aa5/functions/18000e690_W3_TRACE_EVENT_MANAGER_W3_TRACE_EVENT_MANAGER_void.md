# W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER(void)

- ea: `0x18000e690`
- end: `0x18000e70a`
- name: `??1W3_TRACE_EVENT_MANAGER@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(W3_TRACE_EVENT_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000df90`
- `0x18001e7f0`

## callees

- `0x18000e690`
- `0x180018fa0`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000e6ec`

## pseudocode

```c
void __fastcall W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER(W3_TRACE_EVENT_MANAGER *this)
{
  W3_TRACE_CONFIG_LIST_ENTRY **v2; // rbx
  W3_TRACE_CONFIG_LIST_ENTRY *v3; // rcx
  W3_TRACE_CONFIG_LIST_ENTRY *v4; // rax
  W3_TRACE_CONFIG_LIST_ENTRY **v5; // rbx
  W3_TRACE_CONFIG_LIST_ENTRY *v6; // rcx
  W3_TRACE_CONFIG_LIST_ENTRY *v7; // rax

  v2 = (W3_TRACE_CONFIG_LIST_ENTRY **)((char *)this + 24);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (W3_TRACE_CONFIG_LIST_ENTRY *)v2 )
      break;
    if ( *((W3_TRACE_CONFIG_LIST_ENTRY ***)v3 + 1) != v2
      || (v4 = *(W3_TRACE_CONFIG_LIST_ENTRY **)v3, *(W3_TRACE_CONFIG_LIST_ENTRY **)(*(_QWORD *)v3 + 8LL) != v3) )
    {
LABEL_9:
      __fastfail(3u);
    }
    *v2 = v4;
    *((_QWORD *)v4 + 1) = v2;
    W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(v3);
  }
  v5 = (W3_TRACE_CONFIG_LIST_ENTRY **)((char *)this + 8);
  while ( 1 )
  {
    v6 = *v5;
    if ( *v5 == (W3_TRACE_CONFIG_LIST_ENTRY *)v5 )
      break;
    if ( *((W3_TRACE_CONFIG_LIST_ENTRY ***)v6 + 1) != v5 )
      goto LABEL_9;
    v7 = *(W3_TRACE_CONFIG_LIST_ENTRY **)v6;
    if ( *(W3_TRACE_CONFIG_LIST_ENTRY **)(*(_QWORD *)v6 + 8LL) != v6 )
      goto LABEL_9;
    *v5 = v7;
    *((_QWORD *)v7 + 1) = v5;
    W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(v6);
  }
  CReaderWriterLock3::~CReaderWriterLock3(this);
}

```

## disassembly

```asm
0x18000e690  mov     [rsp+arg_0], rbx
0x18000e695  push    rdi
0x18000e696  sub     rsp, 20h
0x18000e69a  mov     rdi, rcx
0x18000e69d  lea     rbx, [rcx+18h]
0x18000e6a1  mov     rcx, [rbx]; this
0x18000e6a4  cmp     rcx, rbx
0x18000e6a7  jz      short loc_18000E6C6
0x18000e6a9  cmp     [rcx+8], rbx
0x18000e6ad  jnz     short loc_18000E6D8
0x18000e6af  mov     rax, [rcx]
0x18000e6b2  cmp     [rax+8], rcx
0x18000e6b6  jnz     short loc_18000E6D8
0x18000e6b8  mov     [rbx], rax
0x18000e6bb  mov     [rax+8], rbx
0x18000e6bf  call    ?FreeEntry@W3_TRACE_CONFIG_LIST_ENTRY@@QEAAXXZ; W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(void)
0x18000e6c4  jmp     short loc_18000E6A1
0x18000e6c6  lea     rbx, [rdi+8]
0x18000e6ca  mov     rcx, [rbx]; this
0x18000e6cd  cmp     rcx, rbx
0x18000e6d0  jz      short loc_18000E6DF
0x18000e6d2  cmp     [rcx+8], rbx
0x18000e6d6  jz      short loc_18000E6F3
0x18000e6d8  mov     ecx, 3
0x18000e6dd  int     29h; Win8: RtlFailFast(ecx)
0x18000e6df  mov     rcx, rdi
0x18000e6e2  mov     rbx, [rsp+28h+arg_0]
0x18000e6e7  add     rsp, 20h
0x18000e6eb  pop     rdi
0x18000e6ec  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000e6f3  mov     rax, [rcx]
0x18000e6f6  cmp     [rax+8], rcx
0x18000e6fa  jnz     short loc_18000E6D8
0x18000e6fc  mov     [rbx], rax
0x18000e6ff  mov     [rax+8], rbx
0x18000e703  call    ?FreeEntry@W3_TRACE_CONFIG_LIST_ENTRY@@QEAAXXZ; W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(void)
0x18000e708  jmp     short loc_18000E6CA
```
