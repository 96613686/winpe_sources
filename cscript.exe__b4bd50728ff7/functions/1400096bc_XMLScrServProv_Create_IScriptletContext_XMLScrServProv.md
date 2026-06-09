# XMLScrServProv::Create(IScriptletContext *,XMLScrServProv * *)

- ea: `0x1400096bc`
- end: `0x14000971f`
- name: `?Create@XMLScrServProv@@SAJPEAUIScriptletContext@@PEAPEAV1@@Z`
- size: `99`
- prototype: `__int64 __fastcall(struct IScriptletContext *, struct XMLScrServProv **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400069d0`

## callees

- `0x1400096bc`
- `0x140009728`
- `0x140009c70`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrServProv::Create(struct IScriptletContext *a1, struct XMLScrServProv **a2)
{
  XMLScrServProv *v4; // rax
  XMLScrServProv *v5; // rax
  struct XMLScrServProv *v6; // rbx
  __int64 result; // rax

  v4 = (XMLScrServProv *)operator new(0x18u);
  if ( !v4 )
    return 2147942414LL;
  v5 = XMLScrServProv::XMLScrServProv(v4);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  *((_QWORD *)v5 + 1) = a1;
  (*(void (__fastcall **)(struct IScriptletContext *))(*(_QWORD *)a1 + 8LL))(a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1400096bc  mov     [rsp+arg_0], rbx
0x1400096c1  mov     [rsp+arg_8], rsi
0x1400096c6  push    rdi
0x1400096c7  sub     rsp, 20h
0x1400096cb  mov     rdi, rcx
0x1400096ce  mov     rsi, rdx
0x1400096d1  mov     ecx, 18h; Size
0x1400096d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400096db  test    rax, rax
0x1400096de  jz      short loc_14000970A
0x1400096e0  mov     rcx, rax; this
0x1400096e3  call    ??0XMLScrServProv@@AEAA@XZ; XMLScrServProv::XMLScrServProv(void)
0x1400096e8  mov     rbx, rax
0x1400096eb  test    rax, rax
0x1400096ee  jz      short loc_14000970A
0x1400096f0  mov     [rax+8], rdi
0x1400096f4  mov     rcx, [rdi]
0x1400096f7  mov     rax, [rcx+8]
0x1400096fb  mov     rcx, rdi
0x1400096fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009703  xor     eax, eax
0x140009705  mov     [rsi], rbx
0x140009708  jmp     short loc_14000970F
0x14000970a  mov     eax, 8007000Eh
0x14000970f  mov     rbx, [rsp+28h+arg_0]
0x140009714  mov     rsi, [rsp+28h+arg_8]
0x140009719  add     rsp, 20h
0x14000971d  pop     rdi
0x14000971e  retn
```
