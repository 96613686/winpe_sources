# CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>::_StandardDestroyCB(CCommand *,void *)

- ea: `0x1800040d0`
- end: `0x1800040f5`
- name: `?_StandardDestroyCB@?$CDPA_Base@VCCommand@@V?$CTContainer_PolicyRelease@VCCommand@@@@@@CAHPEAVCCommand@@PEAX@Z`
- size: `37`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800040d0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>::_StandardDestroyCB(char *p, void *pData)
{
  if ( p )
    (*(void (__fastcall **)(char *, void *))(*((_QWORD *)p + 4) + 16LL))(p + 32, pData);
  return 1;
}

```

## disassembly

```asm
0x1800040d0  sub     rsp, 28h
0x1800040d4  test    rcx, rcx
0x1800040d7  jz      short loc_1800040EA
0x1800040d9  mov     rax, [rcx+20h]
0x1800040dd  add     rcx, 20h ; ' '
0x1800040e1  mov     rax, [rax+10h]
0x1800040e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ea  mov     eax, 1
0x1800040ef  add     rsp, 28h
0x1800040f3  retn
```
