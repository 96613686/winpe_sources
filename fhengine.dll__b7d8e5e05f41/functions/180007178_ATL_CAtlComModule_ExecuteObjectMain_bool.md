# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x180007178`
- end: `0x1800071c4`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `76`
- prototype: `void __fastcall(ATL::CAtlComModule *this, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800016d0`
- `0x18000696c`

## callees

- `0x180007178`
- `0x180034010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v4; // rax

  v2 = off_1800401C0;
  v4 = off_1800401C8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v2 )
    {
      LOBYTE(this) = a2;
      (*((void (__fastcall **)(ATL::CAtlComModule *))*v2 + 8))(this);
      v4 = off_1800401C8;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x180007178  mov     [rsp+arg_0], rbx
0x18000717d  push    rdi
0x18000717e  sub     rsp, 20h
0x180007182  mov     rbx, cs:off_1800401C0
0x180007189  mov     dil, dl
0x18000718c  mov     rax, cs:off_1800401C8
0x180007193  jmp     short loc_1800071B4
0x180007195  mov     r8, [rbx]
0x180007198  test    r8, r8
0x18000719b  jz      short loc_1800071B0
0x18000719d  mov     rax, [r8+40h]
0x1800071a1  mov     cl, dil
0x1800071a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a9  mov     rax, cs:off_1800401C8
0x1800071b0  add     rbx, 8
0x1800071b4  cmp     rbx, rax
0x1800071b7  jb      short loc_180007195
0x1800071b9  mov     rbx, [rsp+28h+arg_0]
0x1800071be  add     rsp, 20h
0x1800071c2  pop     rdi
0x1800071c3  retn
```
