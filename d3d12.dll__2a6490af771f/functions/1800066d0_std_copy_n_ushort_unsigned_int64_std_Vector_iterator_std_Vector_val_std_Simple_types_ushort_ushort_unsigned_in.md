# std::copy_n<ushort *,unsigned __int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>>(ushort *,unsigned __int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>)

- ea: `0x1800066d0`
- end: `0x180006703`
- name: `??$copy_n@PEAG_KV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@PEAG_KV10@@Z`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a740`

## callees

- `0x1800066d0`
- `0x180006e70`

## pseudocode

```c
__int64 *__fastcall std::copy_n<unsigned short *,unsigned __int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>>(
        __int64 *a1,
        void *a2,
        __int64 a3,
        void *a4)
{
  if ( a3 )
    *a1 = std::_Copy_memmove_n<unsigned short const *,unsigned short *>(a2, a3, a4);
  else
    *a1 = (__int64)a4;
  return a1;
}

```

## disassembly

```asm
0x1800066d0  push    rbx
0x1800066d2  sub     rsp, 20h
0x1800066d6  mov     rax, r8
0x1800066d9  mov     r10, rdx
0x1800066dc  mov     rbx, rcx
0x1800066df  test    r8, r8
0x1800066e2  jz      short loc_1800066FE
0x1800066e4  mov     r8, r9
0x1800066e7  mov     rdx, rax
0x1800066ea  mov     rcx, r10; Src
0x1800066ed  call    ??$_Copy_memmove_n@PEBGPEAG@std@@YAPEAGPEBG_KPEAG@Z; std::_Copy_memmove_n<ushort const *,ushort *>(ushort const *,unsigned __int64,ushort *)
0x1800066f2  mov     [rbx], rax
0x1800066f5  mov     rax, rbx
0x1800066f8  add     rsp, 20h
0x1800066fc  pop     rbx
0x1800066fd  retn
0x1800066fe  mov     [rcx], r9
0x180006701  jmp     short loc_1800066F5
```
