# __acrt_uninitialize_stdio

- ea: `0x18001b850`
- end: `0x18001b8ad`
- name: `__acrt_uninitialize_stdio`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180015c20`
- `0x18001b850`
- `0x18001b910`
- `0x18001bd2c`
- `0x18001bd3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b881`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b881`

## pseudocode

```c
void _acrt_uninitialize_stdio()
{
  __int64 i; // rbx

  flushall();
  fcloseall();
  for ( i = 0; i != 3; ++i )
  {
    _acrt_stdio_free_buffer_nolock(*((_QWORD *)_piob + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)_piob + i) + 48LL));
  }
  free_base(_piob);
  _piob = 0;
}

```

## disassembly

```asm
0x18001b850  push    rbx
0x18001b852  sub     rsp, 20h
0x18001b856  call    _flushall
0x18001b85b  call    _fcloseall
0x18001b860  xor     ebx, ebx
0x18001b862  mov     rcx, cs:__piob
0x18001b869  mov     rcx, [rcx+rbx*8]
0x18001b86d  call    __acrt_stdio_free_buffer_nolock
0x18001b872  mov     rax, cs:__piob
0x18001b879  mov     rcx, [rax+rbx*8]
0x18001b87d  add     rcx, 30h ; '0'; lpCriticalSection
0x18001b881  call    cs:__imp_DeleteCriticalSection
0x18001b887  inc     rbx
0x18001b88a  cmp     rbx, 3
0x18001b88e  jnz     short loc_18001B862
0x18001b890  mov     rcx, cs:__piob; Block
0x18001b897  call    _free_base
0x18001b89c  mov     cs:__piob, 0
0x18001b8a7  add     rsp, 20h
0x18001b8ab  pop     rbx
0x18001b8ac  retn
```
