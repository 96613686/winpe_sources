# std::copy<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort *>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort *)

- ea: `0x18000a8bc`
- end: `0x18000a8ec`
- name: `??$copy@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAG@std@@YAPEAGV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@0PEAG@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a740`
- `0x1800131b4`

## callees

- `0x18000c341`

## pseudocode

```c
__int64 __fastcall std::copy<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short *>(
        void *Src,
        __int64 a2,
        void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x18000a8bc  mov     [rsp+arg_0], rbx
0x18000a8c1  push    rdi
0x18000a8c2  sub     rsp, 20h
0x18000a8c6  mov     rbx, rdx
0x18000a8c9  mov     rdi, r8
0x18000a8cc  sub     rbx, rcx
0x18000a8cf  mov     rdx, rcx; Src
0x18000a8d2  mov     r8, rbx; Size
0x18000a8d5  mov     rcx, rdi; void *
0x18000a8d8  call    memmove_0
0x18000a8dd  lea     rax, [rbx+rdi]
0x18000a8e1  mov     rbx, [rsp+28h+arg_0]
0x18000a8e6  add     rsp, 20h
0x18000a8ea  pop     rdi
0x18000a8eb  retn
```
