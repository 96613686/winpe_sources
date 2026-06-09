# FinishThreads(DIRECTCOLORCONVFRM *)

- ea: `0x18001005c`
- end: `0x180010073`
- name: `?FinishThreads@@YAXPEAUDIRECTCOLORCONVFRM@@@Z`
- size: `23`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cb10`
- `0x18001a170`

## callees

- `0x18000fd18`
- `0x18001005c`

## pseudocode

```c
void __fastcall FinishThreads(struct DIRECTCOLORCONVFRM *a1)
{
  if ( *((_DWORD *)a1 + 3658) )
    CloseThreads(a1);
}

```

## disassembly

```asm
0x18001005c  sub     rsp, 28h
0x180010060  cmp     dword ptr [rcx+3928h], 0
0x180010067  jz      short loc_18001006E
0x180010069  call    ?CloseThreads@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; CloseThreads(DIRECTCOLORCONVFRM *)
0x18001006e  add     rsp, 28h
0x180010072  retn
```
