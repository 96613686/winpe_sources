# CLexer::Initialize(ushort *)

- ea: `0x1800045e0`
- end: `0x180004622`
- name: `?Initialize@CLexer@@QEAAJPEAG@Z`
- size: `66`
- prototype: `int(CLexer *__hidden this, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a58`
- `0x18000683c`
- `0x18000745c`
- `0x18000828c`
- `0x180008fc0`
- `0x180009df0`
- `0x18000a94c`

## callees

- `0x1800045e0`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x1800045fc`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800045fc`

## pseudocode

```c
__int64 __fastcall CLexer::Initialize(CLexer *this, unsigned __int16 *a2)
{
  LPWSTR v3; // rax

  if ( a2 && *a2 )
  {
    v3 = AllocADsStr(a2);
    *((_QWORD *)this + 1) = v3;
    if ( !v3 )
      return 2147942414LL;
    *(_QWORD *)this = v3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800045e0  mov     [rsp+arg_0], rbx
0x1800045e5  push    rdi
0x1800045e6  sub     rsp, 20h
0x1800045ea  xor     edi, edi
0x1800045ec  mov     rbx, rcx
0x1800045ef  test    rdx, rdx
0x1800045f2  jz      short loc_180004615
0x1800045f4  cmp     [rdx], di
0x1800045f7  jz      short loc_180004615
0x1800045f9  mov     rcx, rdx; pStr
0x1800045fc  call    cs:__imp_AllocADsStr
0x180004602  mov     [rbx+8], rax
0x180004606  test    rax, rax
0x180004609  jnz     short loc_180004612
0x18000460b  mov     eax, 8007000Eh
0x180004610  jmp     short loc_180004617
0x180004612  mov     [rbx], rax
0x180004615  xor     eax, eax
0x180004617  mov     rbx, [rsp+28h+arg_0]
0x18000461c  add     rsp, 20h
0x180004620  pop     rdi
0x180004621  retn
```
