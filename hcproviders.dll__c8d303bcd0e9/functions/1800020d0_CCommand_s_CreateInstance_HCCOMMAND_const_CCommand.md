# CCommand::s_CreateInstance(HCCOMMAND const *,CCommand * *)

- ea: `0x1800020d0`
- end: `0x18000215b`
- name: `?s_CreateInstance@CCommand@@SAJPEBUHCCOMMAND@@PEAPEAV1@@Z`
- size: `139`
- prototype: `__int64 __fastcall(const struct HCCOMMAND *, struct CCommand **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009a10`

## callees

- `0x1800020d0`
- `0x180002170`
- `0x180004fc8`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CCommand::s_CreateInstance(const struct HCCOMMAND *a1, struct CCommand **a2)
{
  CCommand *v4; // rax
  CCommand *v5; // rax
  struct CCommand *v6; // rbx
  __int64 result; // rax
  unsigned int v8; // edi

  v4 = (CCommand *)operator new(0x30u);
  if ( !v4 )
    return 2147942414LL;
  v5 = CCommand::CCommand(v4);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  result = (*(__int64 (__fastcall **)(CCommand *, const struct HCCOMMAND *))(*(_QWORD *)v5 + 8LL))(v5, a1);
  v8 = result;
  if ( (int)result < 0 )
  {
    (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v6 + 4) + 16LL))((_QWORD *)v6 + 4);
    return v8;
  }
  else
  {
    *a2 = v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800020d0  mov     [rsp+arg_0], rbx
0x1800020d5  mov     [rsp+arg_8], rsi
0x1800020da  push    rdi
0x1800020db  sub     rsp, 20h
0x1800020df  mov     rdi, rcx
0x1800020e2  mov     rsi, rdx
0x1800020e5  mov     ecx, 30h ; '0'; Size
0x1800020ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800020ef  test    rax, rax
0x1800020f2  jz      short loc_180002154
0x1800020f4  mov     rcx, rax; this
0x1800020f7  call    ??0CCommand@@AEAA@XZ; CCommand::CCommand(void)
0x1800020fc  mov     rbx, rax
0x1800020ff  test    rax, rax
0x180002102  jz      short loc_180002154
0x180002104  mov     rax, [rax]
0x180002107  mov     rdx, rdi
0x18000210a  mov     rcx, rbx
0x18000210d  mov     rax, [rax+8]
0x180002111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002116  mov     edi, eax
0x180002118  test    eax, eax
0x18000211a  js      short loc_180002130
0x18000211c  mov     [rsi], rbx
0x18000211f  mov     rbx, [rsp+28h+arg_0]
0x180002124  mov     rsi, [rsp+28h+arg_8]
0x180002129  add     rsp, 20h
0x18000212d  pop     rdi
0x18000212e  retn
0x180002130  mov     rax, [rbx+20h]
0x180002134  lea     rcx, [rbx+20h]
0x180002138  mov     rax, [rax+10h]
0x18000213c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002141  mov     rbx, [rsp+28h+arg_0]
0x180002146  mov     eax, edi
0x180002148  mov     rsi, [rsp+28h+arg_8]
0x18000214d  add     rsp, 20h
0x180002151  pop     rdi
0x180002152  retn
0x180002154  mov     eax, 8007000Eh
0x180002159  jmp     short loc_18000211F
```
