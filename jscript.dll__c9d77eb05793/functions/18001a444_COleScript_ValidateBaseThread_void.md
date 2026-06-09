# COleScript::ValidateBaseThread(void)

- ea: `0x18001a444`
- end: `0x18001a468`
- name: `?ValidateBaseThread@COleScript@@AEAAJXZ`
- size: `36`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180019420`
- `0x18001a390`
- `0x18004d0d0`
- `0x18004d6ec`
- `0x180076f30`
- `0x1800771d0`
- `0x180077560`
- `0x180077fb0`
- `0x18007ada0`
- `0x18007bc34`
- `0x18007c230`
- `0x18007c470`
- `0x18007d3c0`
- `0x18007d400`
- `0x18007dbc0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001a44d`
- `KERNEL32!GetCurrentThreadId` at `0x18001a44d`

## pseudocode

```c
__int64 __fastcall COleScript::ValidateBaseThread(COleScript *this)
{
  return *((_DWORD *)this + 65) != GetCurrentThreadId() ? 0x8000FFFF : 0;
}

```

## disassembly

```asm
0x18001a444  push    rbx
0x18001a446  sub     rsp, 20h
0x18001a44a  mov     rbx, rcx
0x18001a44d  call    cs:__imp_GetCurrentThreadId
0x18001a453  sub     eax, [rbx+104h]
0x18001a459  neg     eax
0x18001a45b  sbb     eax, eax
0x18001a45d  and     eax, 8000FFFFh
0x18001a462  add     rsp, 20h
0x18001a466  pop     rbx
0x18001a467  retn
```
