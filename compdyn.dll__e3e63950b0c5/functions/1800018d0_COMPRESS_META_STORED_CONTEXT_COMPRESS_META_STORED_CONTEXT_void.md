# COMPRESS_META_STORED_CONTEXT::~COMPRESS_META_STORED_CONTEXT(void)

- ea: `0x1800018d0`
- end: `0x180001903`
- name: `??1COMPRESS_META_STORED_CONTEXT@@EEAA@XZ`
- size: `51`
- prototype: `void __fastcall(COMPRESS_META_STORED_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001890`

## callees

- `0x180001910`
- `0x1800019a0`

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
0x1800018d0  push    rbx
0x1800018d2  sub     rsp, 20h
0x1800018d6  lea     rax, ??_7COMPRESS_META_STORED_CONTEXT@@6B@; const COMPRESS_META_STORED_CONTEXT::`vftable'
0x1800018dd  mov     rbx, rcx
0x1800018e0  mov     [rcx], rax
0x1800018e3  add     rcx, 18h; struct _LIST_ENTRY *
0x1800018e7  call    ?Terminate@CONTENT_TYPE_ALLOWED_ENTRY@@SAXPEAU_LIST_ENTRY@@@Z; CONTENT_TYPE_ALLOWED_ENTRY::Terminate(_LIST_ENTRY *)
0x1800018ec  lea     rcx, [rbx+30h]; struct _LIST_ENTRY *
0x1800018f0  call    ?Terminate@CONTENT_TYPE_ALLOWED_ENTRY@@SAXPEAU_LIST_ENTRY@@@Z; CONTENT_TYPE_ALLOWED_ENTRY::Terminate(_LIST_ENTRY *)
0x1800018f5  lea     rcx, [rbx+48h]; this
0x1800018f9  add     rsp, 20h
0x1800018fd  pop     rbx
0x1800018fe  jmp     ??1MIME_MAP@@UEAA@XZ; MIME_MAP::~MIME_MAP(void)
```
