# REQUEST_FILTER_CONFIG::CleanupStoredContext(void)

- ea: `0x1800071d0`
- end: `0x1800071f0`
- name: `?CleanupStoredContext@REQUEST_FILTER_CONFIG@@UEAAXXZ`
- size: `32`
- prototype: `void __fastcall(REQUEST_FILTER_CONFIG *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800058a0`
- `0x180007130`
- `0x1800071d0`

## pseudocode

```c
void __fastcall REQUEST_FILTER_CONFIG::CleanupStoredContext(REQUEST_FILTER_CONFIG *this)
{
  if ( this )
  {
    REQUEST_FILTER_CONFIG::~REQUEST_FILTER_CONFIG(this);
    operator delete(this);
  }
}

```

## disassembly

```asm
0x1800071d0  test    rcx, rcx
0x1800071d3  jz      short locret_1800071EF
0x1800071d5  push    rbx
0x1800071d6  sub     rsp, 20h
0x1800071da  mov     rbx, rcx
0x1800071dd  call    ??1REQUEST_FILTER_CONFIG@@AEAA@XZ
0x1800071e2  mov     rcx, rbx; Block
0x1800071e5  call    ??3@YAXPEAX@Z
0x1800071ea  add     rsp, 20h
0x1800071ee  pop     rbx
0x1800071ef  retn
```
