# CModule::EnsureRedistDllLoaded(void)

- ea: `0x1800061d8`
- end: `0x180006221`
- name: `?EnsureRedistDllLoaded@CModule@@AEAAJXZ`
- size: `73`
- prototype: `__int64 __fastcall(CModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006110`

## callees

- `0x1800061d8`
- `0x18000670c`

## pseudocode

```c
__int64 __fastcall CModule::EnsureRedistDllLoaded(CModule *this)
{
  const char *v3; // r8
  struct D3DCoreModule *ExplicitModule; // rax

  if ( *((_QWORD *)this + 16) )
    return 0;
  v3 = (char *)this + 72;
  if ( *((_QWORD *)this + 12) > 0xFu )
    v3 = *(const char **)v3;
  ExplicitModule = CModule::LoadExplicitModule(this, *((_DWORD *)this + 16), v3, 1);
  *((_QWORD *)this + 16) = ExplicitModule;
  return ExplicitModule == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800061d8  push    rbx
0x1800061da  sub     rsp, 20h
0x1800061de  cmp     qword ptr [rcx+80h], 0
0x1800061e6  mov     rbx, rcx
0x1800061e9  jz      short loc_1800061EF
0x1800061eb  xor     eax, eax
0x1800061ed  jmp     short loc_18000621B
0x1800061ef  lea     r8, [rcx+48h]
0x1800061f3  cmp     qword ptr [r8+18h], 0Fh
0x1800061f8  jbe     short loc_1800061FD
0x1800061fa  mov     r8, [r8]; char *
0x1800061fd  mov     edx, [rcx+40h]; unsigned int
0x180006200  mov     r9b, 1; bool
0x180006203  call    ?LoadExplicitModule@CModule@@QEAAPEAVD3DCoreModule@@IPEBD_N@Z; CModule::LoadExplicitModule(uint,char const *,bool)
0x180006208  mov     [rbx+80h], rax
0x18000620f  neg     rax
0x180006212  sbb     eax, eax
0x180006214  not     eax
0x180006216  and     eax, 80004005h
0x18000621b  add     rsp, 20h
0x18000621f  pop     rbx
0x180006220  retn
```
