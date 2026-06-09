# W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER(void)

- ea: `0x18000f2cc`
- end: `0x18000f34b`
- name: `??1W3_TRACE_EVENT_MANAGER@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(W3_TRACE_EVENT_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000eb20`
- `0x1800202bc`

## callees

- `0x18000f2cc`
- `0x18001a550`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000f328`

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
0x18000f2cc  mov     [rsp+arg_0], rbx
0x18000f2d1  push    rdi
0x18000f2d2  sub     rsp, 20h
0x18000f2d6  mov     rdi, rcx
0x18000f2d9  lea     rbx, [rcx+18h]
0x18000f2dd  mov     rcx, [rbx]; this
0x18000f2e0  cmp     rcx, rbx
0x18000f2e3  jz      short loc_18000F302
0x18000f2e5  cmp     [rcx+8], rbx
0x18000f2e9  jnz     short loc_18000F314
0x18000f2eb  mov     rax, [rcx]
0x18000f2ee  cmp     [rax+8], rcx
0x18000f2f2  jnz     short loc_18000F314
0x18000f2f4  mov     [rbx], rax
0x18000f2f7  mov     [rax+8], rbx
0x18000f2fb  call    ?FreeEntry@W3_TRACE_CONFIG_LIST_ENTRY@@QEAAXXZ; W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(void)
0x18000f300  jmp     short loc_18000F2DD
0x18000f302  lea     rbx, [rdi+8]
0x18000f306  mov     rcx, [rbx]; this
0x18000f309  cmp     rcx, rbx
0x18000f30c  jz      short loc_18000F31B
0x18000f30e  cmp     [rcx+8], rbx
0x18000f312  jz      short loc_18000F334
0x18000f314  mov     ecx, 3
0x18000f319  int     29h; Win8: RtlFailFast(ecx)
0x18000f31b  mov     rcx, rdi
0x18000f31e  mov     rbx, [rsp+28h+arg_0]
0x18000f323  add     rsp, 20h
0x18000f327  pop     rdi
0x18000f328  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000f334  mov     rax, [rcx]
0x18000f337  cmp     [rax+8], rcx
0x18000f33b  jnz     short loc_18000F314
0x18000f33d  mov     [rbx], rax
0x18000f340  mov     [rax+8], rbx
0x18000f344  call    ?FreeEntry@W3_TRACE_CONFIG_LIST_ENTRY@@QEAAXXZ; W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(void)
0x18000f349  jmp     short loc_18000F306
```
