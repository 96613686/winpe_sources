# COleScript::ValidateBaseThread(void)

- ea: `0x1800174b4`
- end: `0x1800174df`
- name: `?ValidateBaseThread@COleScript@@AEAAJXZ`
- size: `43`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x18001643c`
- `0x180017400`
- `0x18004de60`
- `0x18004e54c`
- `0x1800784d0`
- `0x180078770`
- `0x180078b30`
- `0x1800795c0`
- `0x18007c580`
- `0x18007d498`
- `0x18007daa0`
- `0x18007dce0`
- `0x18007ecc0`
- `0x18007ed00`
- `0x18007f500`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800174bd`
- `KERNEL32!GetCurrentThreadId` at `0x1800174bd`

## pseudocode

```c
__int64 __fastcall COleScript::ValidateBaseThread(COleScript *this)
{
  return *((_DWORD *)this + 65) != GetCurrentThreadId() ? 0x8000FFFF : 0;
}

```

## disassembly

```asm
0x1800174b4  push    rbx
0x1800174b6  sub     rsp, 20h
0x1800174ba  mov     rbx, rcx
0x1800174bd  call    cs:__imp_GetCurrentThreadId
0x1800174c4  nop     dword ptr [rax+rax+00h]
0x1800174c9  sub     eax, [rbx+104h]
0x1800174cf  neg     eax
0x1800174d1  sbb     eax, eax
0x1800174d3  and     eax, 8000FFFFh
0x1800174d8  add     rsp, 20h
0x1800174dc  pop     rbx
0x1800174dd  retn
```
