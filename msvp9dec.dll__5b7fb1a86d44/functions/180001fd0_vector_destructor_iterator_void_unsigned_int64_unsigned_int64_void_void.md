# `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))

- ea: `0x180001fd0`
- end: `0x18000200d`
- name: `??_I@YAXPEAX_K1P6AX0@Z@Z`
- size: `61`
- prototype: `void __fastcall(void *, unsigned __int64, unsigned __int64, void (*)(void *))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002420`
- `0x180004438`

## callees

- `0x180001fd0`
- `0x1800043f0`

## pseudocode

```c
void __fastcall `vector destructor iterator'(char *a1, __int64 a2, __int64 a3, void (*a4)(void *))
{
  __int64 v4; // rdi
  char *v5; // rbx

  v4 = 124;
  v5 = a1 + 1984;
  do
  {
    v5 -= 16;
    --v4;
  }
  while ( v4 );
}

```

## disassembly

```asm
0x180001fd0  mov     [rsp+arg_0], rbx
0x180001fd5  push    rdi
0x180001fd6  sub     rsp, 20h
0x180001fda  mov     edi, 7Ch ; '|'
0x180001fdf  lea     rbx, [rcx+7C0h]
0x180001fe6  nop     word ptr [rax+rax+00000000h]
0x180001ff0  sub     rbx, 10h
0x180001ff4  mov     rcx, rbx
0x180001ff7  call    _guard_check_icall_nop
0x180001ffc  sub     rdi, 1
0x180002000  jnz     short loc_180001FF0
0x180002002  mov     rbx, [rsp+28h+arg_0]
0x180002007  add     rsp, 20h
0x18000200b  pop     rdi
0x18000200c  retn
```
