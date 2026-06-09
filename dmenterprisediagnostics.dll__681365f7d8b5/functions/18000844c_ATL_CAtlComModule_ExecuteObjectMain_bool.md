# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x18000844c`
- end: `0x180008499`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `77`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001150`
- `0x180007e74`

## callees

- `0x18000844c`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, char a2)
{
  __int64 *v2; // rbx
  __int64 *v4; // rax

  v2 = off_1800348F0[0];
  v4 = off_1800348F8;
  while ( v2 < v4 )
  {
    if ( *v2 )
    {
      LOBYTE(this) = a2;
      (*(void (__fastcall **)(ATL::CAtlComModule *))(*v2 + 64))(this);
      v4 = off_1800348F8;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x18000844c  mov     [rsp+arg_0], rbx
0x180008451  push    rdi
0x180008452  sub     rsp, 20h
0x180008456  mov     rbx, cs:off_1800348F0
0x18000845d  mov     dil, dl
0x180008460  mov     rax, cs:off_1800348F8
0x180008467  jmp     short loc_180008488
0x180008469  mov     r8, [rbx]
0x18000846c  test    r8, r8
0x18000846f  jz      short loc_180008484
0x180008471  mov     rax, [r8+40h]
0x180008475  mov     cl, dil
0x180008478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000847d  mov     rax, cs:off_1800348F8
0x180008484  add     rbx, 8
0x180008488  cmp     rbx, rax
0x18000848b  jb      short loc_180008469
0x18000848d  mov     rbx, [rsp+28h+arg_0]
0x180008492  add     rsp, 20h
0x180008496  pop     rdi
0x180008497  retn
```
