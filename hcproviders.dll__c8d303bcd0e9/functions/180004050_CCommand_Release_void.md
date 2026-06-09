# CCommand::Release(void)

- ea: `0x180004050`
- end: `0x180004086`
- name: `?Release@CCommand@@UEAAKXZ`
- size: `54`
- prototype: `unsigned int __fastcall(CCommand *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004050`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CCommand::Release(CCommand *this)
{
  unsigned __int32 v1; // ebx
  char *v3; // rcx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 )
  {
    v3 = (char *)this - 32;
    if ( v3 )
      (**(void (__fastcall ***)(char *, __int64))v3)(v3, 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180004050  push    rbx
0x180004052  sub     rsp, 20h
0x180004056  mov     ebx, 0FFFFFFFFh
0x18000405b  lock xadd [rcx+8], ebx
0x180004060  sub     ebx, 1
0x180004063  jz      short loc_18000406E
0x180004065  mov     eax, ebx
0x180004067  add     rsp, 20h
0x18000406b  pop     rbx
0x18000406c  retn
0x18000406e  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180004072  jz      short loc_180004065
0x180004074  mov     rax, [rcx]
0x180004077  mov     edx, 1
0x18000407c  mov     rax, [rax]
0x18000407f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004084  jmp     short loc_180004065
```
