# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x180002f4c`
- end: `0x180002f98`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `76`
- prototype: `void __fastcall(ATL::CAtlComModule *this, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001800`
- `0x180002a3c`

## callees

- `0x180002f4c`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v4; // rax

  v2 = off_18001D090;
  v4 = off_18001D098;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v2 )
    {
      LOBYTE(this) = a2;
      (*((void (__fastcall **)(ATL::CAtlComModule *))*v2 + 8))(this);
      v4 = off_18001D098;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x180002f4c  mov     [rsp+arg_0], rbx
0x180002f51  push    rdi
0x180002f52  sub     rsp, 20h
0x180002f56  mov     rbx, cs:off_18001D090
0x180002f5d  mov     dil, dl
0x180002f60  mov     rax, cs:off_18001D098
0x180002f67  jmp     short loc_180002F88
0x180002f69  mov     r8, [rbx]
0x180002f6c  test    r8, r8
0x180002f6f  jz      short loc_180002F84
0x180002f71  mov     rax, [r8+40h]
0x180002f75  mov     cl, dil
0x180002f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7d  mov     rax, cs:off_18001D098
0x180002f84  add     rbx, 8
0x180002f88  cmp     rbx, rax
0x180002f8b  jb      short loc_180002F69
0x180002f8d  mov     rbx, [rsp+28h+arg_0]
0x180002f92  add     rsp, 20h
0x180002f96  pop     rdi
0x180002f97  retn
```
