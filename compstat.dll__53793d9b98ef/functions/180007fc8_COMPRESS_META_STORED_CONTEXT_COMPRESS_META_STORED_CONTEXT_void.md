# COMPRESS_META_STORED_CONTEXT::~COMPRESS_META_STORED_CONTEXT(void)

- ea: `0x180007fc8`
- end: `0x180007ffb`
- name: `??1COMPRESS_META_STORED_CONTEXT@@EEAA@XZ`
- size: `51`
- prototype: `void __fastcall(COMPRESS_META_STORED_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008050`

## callees

- `0x180008004`
- `0x1800088c0`

## pseudocode

```c
void __fastcall COMPRESS_META_STORED_CONTEXT::~COMPRESS_META_STORED_CONTEXT(COMPRESS_META_STORED_CONTEXT *this)
{
  *(_QWORD *)this = &COMPRESS_META_STORED_CONTEXT::`vftable';
  CONTENT_TYPE_ALLOWED_ENTRY::Terminate((struct _LIST_ENTRY *)((char *)this + 24));
  CONTENT_TYPE_ALLOWED_ENTRY::Terminate((struct _LIST_ENTRY *)this + 3);
  MIME_MAP::~MIME_MAP((COMPRESS_META_STORED_CONTEXT *)((char *)this + 72));
}

```

## disassembly

```asm
0x180007fc8  push    rbx
0x180007fca  sub     rsp, 20h
0x180007fce  lea     rax, ??_7COMPRESS_META_STORED_CONTEXT@@6B@; const COMPRESS_META_STORED_CONTEXT::`vftable'
0x180007fd5  mov     rbx, rcx
0x180007fd8  mov     [rcx], rax
0x180007fdb  add     rcx, 18h; struct _LIST_ENTRY *
0x180007fdf  call    ?Terminate@CONTENT_TYPE_ALLOWED_ENTRY@@SAXPEAU_LIST_ENTRY@@@Z; CONTENT_TYPE_ALLOWED_ENTRY::Terminate(_LIST_ENTRY *)
0x180007fe4  lea     rcx, [rbx+30h]; struct _LIST_ENTRY *
0x180007fe8  call    ?Terminate@CONTENT_TYPE_ALLOWED_ENTRY@@SAXPEAU_LIST_ENTRY@@@Z; CONTENT_TYPE_ALLOWED_ENTRY::Terminate(_LIST_ENTRY *)
0x180007fed  lea     rcx, [rbx+48h]; this
0x180007ff1  add     rsp, 20h
0x180007ff5  pop     rbx
0x180007ff6  jmp     ??1MIME_MAP@@UEAA@XZ; MIME_MAP::~MIME_MAP(void)
```
