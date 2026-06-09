# UserSecurityContext::`scalar deleting destructor'(uint)

- ea: `0x180016310`
- end: `0x180016341`
- name: `??_GUserSecurityContext@@UEAAPEAXI@Z`
- size: `49`
- prototype: `void *__fastcall(UserSecurityContext *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180016278`
- `0x180016310`

## import_xrefs

- `msvcrt!free` at `0x18001632c`
- `msvcrt!free` at `0x18001632c`

## pseudocode

```c
UserSecurityContext *__fastcall UserSecurityContext::`scalar deleting destructor'(UserSecurityContext *this, char a2)
{
  UserSecurityContext::~UserSecurityContext(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x180016310  mov     [rsp+arg_0], rbx
0x180016315  push    rdi
0x180016316  sub     rsp, 20h
0x18001631a  mov     ebx, edx
0x18001631c  mov     rdi, rcx
0x18001631f  call    ??1UserSecurityContext@@UEAA@XZ; UserSecurityContext::~UserSecurityContext(void)
0x180016324  test    bl, 1
0x180016327  jz      short loc_180016333
0x180016329  mov     rcx, rdi; Block
0x18001632c  call    cs:__imp_free
0x180016332  nop
0x180016333  mov     rax, rdi
0x180016336  mov     rbx, [rsp+28h+arg_0]
0x18001633b  add     rsp, 20h
0x18001633f  pop     rdi
0x180016340  retn
```
