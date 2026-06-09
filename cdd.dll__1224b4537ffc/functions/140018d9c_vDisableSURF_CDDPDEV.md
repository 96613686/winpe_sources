# vDisableSURF(CDDPDEV *)

- ea: `0x140018d9c`
- end: `0x140018e29`
- name: `?vDisableSURF@@YAXPEAUCDDPDEV@@@Z`
- size: `141`
- prototype: `void __fastcall(struct CDDPDEV *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14002c640`
- `0x14002c6f0`

## callees

- `0x140018d9c`
- `0x140018e30`
- `0x140018ef0`
- `0x14002c510`

## import_xrefs

- `WIN32K!EngDeleteSurface` at `0x140018ddd`
- `WIN32K!EngDeleteSurface` at `0x140018df8`
- `WIN32K!EngDeleteSurface` at `0x140018ddd`
- `WIN32K!EngDeleteSurface` at `0x140018df8`
- `WIN32K!EngUnlockSurface` at `0x140018dce`
- `WIN32K!EngUnlockSurface` at `0x140018dce`

## pseudocode

```c
void __fastcall vDisableSURF(struct CDDPDEV *a1)
{
  SURFOBJ *v2; // rcx
  HSURF hsurf; // rbx
  HSURF v4; // rcx

  if ( *((_BYTE *)a1 + 2716) )
    DrvAssertMode((DHPDEV)a1, 0);
  FreePointerSurface((struct CDDPDEV *)((char *)a1 + 1120));
  v2 = (SURFOBJ *)*((_QWORD *)a1 + 349);
  if ( v2 )
  {
    hsurf = v2->hsurf;
    EngUnlockSurface(v2);
    EngDeleteSurface(hsurf);
    v4 = (HSURF)*((_QWORD *)a1 + 2);
    *((_QWORD *)a1 + 349) = 0;
    EngDeleteSurface(v4);
    *((_QWORD *)a1 + 2) = 0;
  }
  CddFreeShadowSysMem(a1);
}

```

## disassembly

```asm
0x140018d9c  mov     [rsp+arg_0], rbx
0x140018da1  push    rdi
0x140018da2  sub     rsp, 20h
0x140018da6  cmp     byte ptr [rcx+0A9Ch], 0
0x140018dad  mov     rdi, rcx
0x140018db0  jnz     short loc_140018E20
0x140018db2  lea     rcx, [rdi+460h]; struct _POINTER_INFO *
0x140018db9  call    ?FreePointerSurface@@YAXPEAU_POINTER_INFO@@@Z; FreePointerSurface(_POINTER_INFO *)
0x140018dbe  mov     rcx, [rdi+0AE8h]; pso
0x140018dc5  test    rcx, rcx
0x140018dc8  jz      short loc_140018E0C
0x140018dca  mov     rbx, [rcx+8]
0x140018dce  call    cs:__imp_EngUnlockSurface
0x140018dd5  nop     dword ptr [rax+rax+00h]
0x140018dda  mov     rcx, rbx; hsurf
0x140018ddd  call    cs:__imp_EngDeleteSurface
0x140018de4  nop     dword ptr [rax+rax+00h]
0x140018de9  mov     rcx, [rdi+10h]; hsurf
0x140018ded  mov     qword ptr [rdi+0AE8h], 0
0x140018df8  call    cs:__imp_EngDeleteSurface
0x140018dff  nop     dword ptr [rax+rax+00h]
0x140018e04  mov     qword ptr [rdi+10h], 0
0x140018e0c  mov     rcx, rdi; struct CDDPDEV *
0x140018e0f  call    ?CddFreeShadowSysMem@@YAXPEAUCDDPDEV@@@Z; CddFreeShadowSysMem(CDDPDEV *)
0x140018e14  mov     rbx, [rsp+28h+arg_0]
0x140018e19  add     rsp, 20h
0x140018e1d  pop     rdi
0x140018e1e  retn
0x140018e20  xor     edx, edx; bEnable
0x140018e22  call    DrvAssertMode
0x140018e27  jmp     short loc_140018DB2
```
