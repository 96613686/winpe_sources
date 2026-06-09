# XMLParser::GrowNodeInfo(void)

- ea: `0x180033da8`
- end: `0x180033e3c`
- name: `?GrowNodeInfo@XMLParser@@AEAAJXZ`
- size: `148`
- prototype: `__int64 __fastcall(XMLParser *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180035008`
- `0x18003510c`
- `0x18003522c`

## callees

- `0x180003740`
- `0x180003840`
- `0x180033da8`

## pseudocode

```c
__int64 __fastcall XMLParser::GrowNodeInfo(XMLParser *this)
{
  unsigned __int16 v2; // si
  unsigned __int128 v3; // rax
  _QWORD *v4; // rdi
  __int64 result; // rax
  int i; // edx

  v2 = *((_WORD *)this + 88) + 10;
  v3 = v2 * (unsigned __int128)8uLL;
  if ( !is_mul_ok(v2, 8u) )
    *(_QWORD *)&v3 = -1;
  v4 = operator new(v3, *((const struct NoThrow **)&v3 + 1));
  if ( !v4 )
    return 2147942414LL;
  for ( i = *((_DWORD *)this + 32); --i >= 0; v4[i] = *((_QWORD *)this + 15) + *((_DWORD *)this + 28) * i )
    ;
  operator delete(*((void **)this + 21));
  result = 0;
  *((_QWORD *)this + 21) = v4;
  *((_WORD *)this + 88) = v2;
  return result;
}

```

## disassembly

```asm
0x180033da8  mov     [rsp+arg_0], rbx
0x180033dad  mov     [rsp+arg_8], rsi
0x180033db2  push    rdi
0x180033db3  sub     rsp, 20h
0x180033db7  movzx   eax, word ptr [rcx+0B0h]
0x180033dbe  mov     rbx, rcx
0x180033dc1  add     ax, 0Ah
0x180033dc5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180033dcc  movzx   esi, ax
0x180033dcf  mov     eax, 8
0x180033dd4  mul     rsi
0x180033dd7  cmovb   rax, rcx
0x180033ddb  mov     rcx, rax; unsigned __int64
0x180033dde  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180033de3  mov     rdi, rax
0x180033de6  test    rax, rax
0x180033de9  jnz     short loc_180033DF2
0x180033deb  mov     eax, 8007000Eh
0x180033df0  jmp     short loc_180033E2C
0x180033df2  mov     edx, [rbx+80h]
0x180033df8  jmp     short loc_180033E0B
0x180033dfa  mov     eax, edx
0x180033dfc  imul    eax, [rbx+70h]
0x180033e00  movsxd  rcx, eax
0x180033e03  add     rcx, [rbx+78h]
0x180033e07  mov     [rdi+rdx*8], rcx
0x180033e0b  sub     edx, 1
0x180033e0e  jns     short loc_180033DFA
0x180033e10  mov     rcx, [rbx+0A8h]; void *
0x180033e17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033e1c  xor     eax, eax
0x180033e1e  mov     [rbx+0A8h], rdi
0x180033e25  mov     [rbx+0B0h], si
0x180033e2c  mov     rbx, [rsp+28h+arg_0]
0x180033e31  mov     rsi, [rsp+28h+arg_8]
0x180033e36  add     rsp, 20h
0x180033e3a  pop     rdi
0x180033e3b  retn
```
