# XMLStream::push(long (XMLStream::*)(void),short)

- ea: `0x180038320`
- end: `0x180038385`
- name: `?push@XMLStream@@AEAAJP81@EAAJXZF@Z`
- size: `101`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180036150`
- `0x1800361a0`
- `0x1800362f0`
- `0x180036980`
- `0x180036ba0`
- `0x180036cd0`
- `0x180036ee0`
- `0x180037050`
- `0x180037640`
- `0x1800377f0`
- `0x180037970`
- `0x180037e00`
- `0x18003838c`

## callees

- `0x180034d18`
- `0x180038320`

## pseudocode

```c
__int64 __fastcall XMLStream::push(__int64 a1, __int64 a2, __int16 a3)
{
  char *v6; // rax
  __int64 result; // rax

  v6 = RawStack::_push((RawStack *)(a1 + 16));
  if ( !v6 )
    return 2147942414LL;
  *((_WORD *)v6 + 4) = a3;
  *(_QWORD *)v6 = *(_QWORD *)a1;
  *((_QWORD *)v6 + 2) = *(_QWORD *)(a1 + 176);
  *((_DWORD *)v6 + 6) = *(_DWORD *)(a1 + 80);
  result = 0;
  *(_WORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = a2;
  return result;
}

```

## disassembly

```asm
0x180038320  mov     [rsp+arg_0], rbx
0x180038325  mov     [rsp+arg_8], rsi
0x18003832a  push    rdi
0x18003832b  sub     rsp, 20h
0x18003832f  mov     rbx, rcx
0x180038332  movzx   edi, r8w
0x180038336  add     rcx, 10h; this
0x18003833a  mov     rsi, rdx
0x18003833d  call    ?_push@RawStack@@IEAAPEADXZ; RawStack::_push(void)
0x180038342  mov     rcx, rax
0x180038345  test    rax, rax
0x180038348  jnz     short loc_180038351
0x18003834a  mov     eax, 8007000Eh
0x18003834f  jmp     short loc_180038375
0x180038351  mov     [rax+8], di
0x180038355  mov     rax, [rbx]
0x180038358  mov     [rcx], rax
0x18003835b  mov     rax, [rbx+0B0h]
0x180038362  mov     [rcx+10h], rax
0x180038366  mov     eax, [rbx+50h]
0x180038369  mov     [rcx+18h], eax
0x18003836c  xor     eax, eax
0x18003836e  mov     [rbx+8], ax
0x180038372  mov     [rbx], rsi
0x180038375  mov     rbx, [rsp+28h+arg_0]
0x18003837a  mov     rsi, [rsp+28h+arg_8]
0x18003837f  add     rsp, 20h
0x180038383  pop     rdi
0x180038384  retn
```
