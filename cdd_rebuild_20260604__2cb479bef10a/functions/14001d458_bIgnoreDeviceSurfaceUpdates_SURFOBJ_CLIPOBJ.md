# bIgnoreDeviceSurfaceUpdates(_SURFOBJ *,_CLIPOBJ * *)

- ea: `0x14001d458`
- end: `0x14001d482`
- name: `?bIgnoreDeviceSurfaceUpdates@@YAHPEAU_SURFOBJ@@PEAPEAU_CLIPOBJ@@@Z`
- size: `42`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _CLIPOBJ **)`
- caller_count: `12`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000919c`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`

## callees

- `0x14001d458`

## import_xrefs

- `WIN32K!EngUpdateDeviceSurface` at `0x14001d46b`
- `WIN32K!EngUpdateDeviceSurface` at `0x14001d46b`

## pseudocode

```c
_BOOL8 __fastcall bIgnoreDeviceSurfaceUpdates(struct _SURFOBJ *a1, struct _CLIPOBJ **a2)
{
  return a1->iType == 1 && !EngUpdateDeviceSurface(a1, a2);
}

```

## disassembly

```asm
0x14001d458  sub     rsp, 28h
0x14001d45c  cmp     word ptr [rcx+4Ch], 1
0x14001d461  jz      short loc_14001D46B
0x14001d463  xor     eax, eax
0x14001d465  add     rsp, 28h
0x14001d469  retn
0x14001d46b  call    cs:__imp_EngUpdateDeviceSurface
0x14001d472  nop     dword ptr [rax+rax+00h]
0x14001d477  xor     ecx, ecx
0x14001d479  test    eax, eax
0x14001d47b  setz    cl
0x14001d47e  mov     eax, ecx
0x14001d480  jmp     short loc_14001D465
```
