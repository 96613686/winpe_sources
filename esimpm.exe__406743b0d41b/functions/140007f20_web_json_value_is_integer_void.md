# web::json::value::is_integer(void)

- ea: `0x140007f20`
- end: `0x140007f58`
- name: `?is_integer@value@json@web@@QEBA_NXZ`
- size: `56`
- prototype: `bool __fastcall(web::json::value *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14003a9d8`
- `0x14003aba0`
- `0x14003b25c`
- `0x14003b424`
- `0x14003b8bc`
- `0x14003ba84`

## callees

- `0x140007f20`
- `0x14003e010`

## pseudocode

```c
bool __fastcall web::json::value::is_integer(web::json::value *this)
{
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 88LL))(*(_QWORD *)this) )
    return 0;
  else
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 96LL))(*(_QWORD *)this);
}

```

## disassembly

```asm
0x140007f20  push    rbx
0x140007f22  sub     rsp, 20h
0x140007f26  mov     rbx, rcx
0x140007f29  mov     rcx, [rcx]
0x140007f2c  mov     rax, [rcx]
0x140007f2f  mov     rax, [rax+58h]
0x140007f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f38  test    eax, eax
0x140007f3a  jz      short loc_140007F44
0x140007f3c  xor     al, al
0x140007f3e  add     rsp, 20h
0x140007f42  pop     rbx
0x140007f43  retn
0x140007f44  mov     rcx, [rbx]
0x140007f47  mov     rax, [rcx]
0x140007f4a  mov     rax, [rax+60h]
0x140007f4e  add     rsp, 20h
0x140007f52  pop     rbx
0x140007f53  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
