# CFaxSecurity::GetInheritTypes(_SI_INHERIT_TYPE * *,ulong *)

- ea: `0x180013cd0`
- end: `0x180013cd6`
- name: `?GetInheritTypes@CFaxSecurity@@UEAAJPEAPEAU_SI_INHERIT_TYPE@@PEAK@Z`
- size: `6`
- prototype: `__int64 __fastcall(CFaxSecurity *__hidden this, struct _SI_INHERIT_TYPE **, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::GetInheritTypes(CFaxSecurity *this, struct _SI_INHERIT_TYPE **a2, unsigned int *a3)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180013cd0  mov     eax, 80004001h
0x180013cd5  retn
```
