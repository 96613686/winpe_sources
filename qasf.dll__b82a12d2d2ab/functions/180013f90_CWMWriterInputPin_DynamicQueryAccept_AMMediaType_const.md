# CWMWriterInputPin::DynamicQueryAccept(_AMMediaType const *)

- ea: `0x180013f90`
- end: `0x180013fae`
- name: `?DynamicQueryAccept@CWMWriterInputPin@@UEAAJPEBU_AMMediaType@@@Z`
- size: `30`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, const struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180013f90`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::DynamicQueryAccept(CWMWriterInputPin *this, const struct _AMMediaType *a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 38) + 88LL))((char *)this - 304);
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180013f90  test    rdx, rdx
0x180013f93  jnz     short loc_180013F9B
0x180013f95  mov     eax, 80004003h
0x180013f9a  retn
0x180013f9b  add     rcx, 0FFFFFFFFFFFFFED0h
0x180013fa2  mov     rax, [rcx]
0x180013fa5  mov     rax, [rax+58h]
0x180013fa9  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
