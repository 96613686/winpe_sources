# __acrt_lowio_destroy_handle_array

- ea: `0x18001c740`
- end: `0x18001c790`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ab50`

## callees

- `0x180019608`
- `0x18001c740`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001c769`
- `KERNEL32!DeleteCriticalSection` at `0x18001c769`

## pseudocode

```c
void __fastcall _acrt_lowio_destroy_handle_array(char *Block)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi

  if ( Block )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)(Block + 4096);
    v3 = (struct _RTL_CRITICAL_SECTION *)Block;
    do
    {
      DeleteCriticalSection(v3);
      v3 = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 64);
    }
    while ( v3 != v1 );
    free_base(Block);
  }
}

```

## disassembly

```asm
0x18001c740  test    rcx, rcx
0x18001c743  jz      short locret_18001C78F
0x18001c745  mov     [rsp+arg_0], rbx
0x18001c74a  mov     [rsp+arg_8], rsi
0x18001c74f  push    rdi
0x18001c750  sub     rsp, 20h
0x18001c754  lea     rsi, [rcx+1000h]
0x18001c75b  mov     rbx, rcx
0x18001c75e  mov     rdi, rcx
0x18001c761  cmp     rcx, rsi
0x18001c764  jz      short loc_18001C778
0x18001c766  mov     rcx, rdi; lpCriticalSection
0x18001c769  call    cs:__imp_DeleteCriticalSection
0x18001c76f  add     rdi, 40h ; '@'
0x18001c773  cmp     rdi, rsi
0x18001c776  jnz     short loc_18001C766
0x18001c778  mov     rcx, rbx; Block
0x18001c77b  call    _free_base
0x18001c780  mov     rbx, [rsp+28h+arg_0]
0x18001c785  mov     rsi, [rsp+28h+arg_8]
0x18001c78a  add     rsp, 20h
0x18001c78e  pop     rdi
0x18001c78f  retn
```
