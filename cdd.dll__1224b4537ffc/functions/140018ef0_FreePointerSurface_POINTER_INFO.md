# FreePointerSurface(_POINTER_INFO *)

- ea: `0x140018ef0`
- end: `0x140018f3e`
- name: `?FreePointerSurface@@YAXPEAU_POINTER_INFO@@@Z`
- size: `78`
- prototype: `void __fastcall(struct _POINTER_INFO *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140018d9c`
- `0x140035150`
- `0x140035c20`

## callees

- `0x140018ef0`

## import_xrefs

- `WIN32K!EngDeleteSurface` at `0x140018f28`
- `WIN32K!EngDeleteSurface` at `0x140018f28`
- `WIN32K!EngUnlockSurface` at `0x140018f12`
- `WIN32K!EngUnlockSurface` at `0x140018f12`

## pseudocode

```c
void __fastcall FreePointerSurface(struct _POINTER_INFO *a1)
{
  SURFOBJ *v2; // rcx
  HSURF v3; // rcx

  v2 = (SURFOBJ *)*((_QWORD *)a1 + 7);
  if ( v2 )
  {
    EngUnlockSurface(v2);
    *((_QWORD *)a1 + 7) = 0;
  }
  v3 = (HSURF)*((_QWORD *)a1 + 8);
  if ( v3 )
  {
    EngDeleteSurface(v3);
    *((_QWORD *)a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x140018ef0  push    rbx
0x140018ef2  sub     rsp, 20h
0x140018ef6  mov     rbx, rcx
0x140018ef9  mov     rcx, [rcx+38h]; pso
0x140018efd  test    rcx, rcx
0x140018f00  jnz     short loc_140018F12
0x140018f02  mov     rcx, [rbx+40h]; hsurf
0x140018f06  test    rcx, rcx
0x140018f09  jnz     short loc_140018F28
0x140018f0b  add     rsp, 20h
0x140018f0f  pop     rbx
0x140018f10  retn
0x140018f12  call    cs:__imp_EngUnlockSurface
0x140018f19  nop     dword ptr [rax+rax+00h]
0x140018f1e  mov     qword ptr [rbx+38h], 0
0x140018f26  jmp     short loc_140018F02
0x140018f28  call    cs:__imp_EngDeleteSurface
0x140018f2f  nop     dword ptr [rax+rax+00h]
0x140018f34  mov     qword ptr [rbx+40h], 0
0x140018f3c  jmp     short loc_140018F0B
```
