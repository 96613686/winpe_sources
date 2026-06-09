# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x1800080a4`
- end: `0x1800080f0`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `76`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001140`
- `0x180007b04`

## callees

- `0x1800080a4`
- `0x180026010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, char a2)
{
  __int64 *v2; // rbx
  __int64 *v4; // rax

  v2 = off_1800338F0[0];
  v4 = off_1800338F8;
  while ( v2 < v4 )
  {
    if ( *v2 )
    {
      LOBYTE(this) = a2;
      (*(void (__fastcall **)(ATL::CAtlComModule *))(*v2 + 64))(this);
      v4 = off_1800338F8;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x1800080a4  mov     [rsp+arg_0], rbx
0x1800080a9  push    rdi
0x1800080aa  sub     rsp, 20h
0x1800080ae  mov     rbx, cs:off_1800338F0
0x1800080b5  mov     dil, dl
0x1800080b8  mov     rax, cs:off_1800338F8
0x1800080bf  jmp     short loc_1800080E0
0x1800080c1  mov     r8, [rbx]
0x1800080c4  test    r8, r8
0x1800080c7  jz      short loc_1800080DC
0x1800080c9  mov     rax, [r8+40h]
0x1800080cd  mov     cl, dil
0x1800080d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d5  mov     rax, cs:off_1800338F8
0x1800080dc  add     rbx, 8
0x1800080e0  cmp     rbx, rax
0x1800080e3  jb      short loc_1800080C1
0x1800080e5  mov     rbx, [rsp+28h+arg_0]
0x1800080ea  add     rsp, 20h
0x1800080ee  pop     rdi
0x1800080ef  retn
```
