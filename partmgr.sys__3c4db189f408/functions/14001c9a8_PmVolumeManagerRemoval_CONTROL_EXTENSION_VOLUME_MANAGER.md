# PmVolumeManagerRemoval(_CONTROL_EXTENSION *,_VOLUME_MANAGER *)

- ea: `0x14001c9a8`
- end: `0x14001ca06`
- name: `?PmVolumeManagerRemoval@@YAJPEAU_CONTROL_EXTENSION@@PEAU_VOLUME_MANAGER@@@Z`
- size: `94`
- prototype: `int(struct _CONTROL_EXTENSION *, struct _VOLUME_MANAGER *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000e398`
- `0x14001c660`
- `0x14001c880`

## callees

- `0x14001c9a8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c9ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c9ea`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c9d9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c9d9`

## pseudocode

```c
__int64 __fastcall PmVolumeManagerRemoval(struct _CONTROL_EXTENSION *a1, struct _VOLUME_MANAGER ***a2)
{
  struct _VOLUME_MANAGER **v3; // rax
  struct _VOLUME_MANAGER **v4; // rcx
  struct _VOLUME_MANAGER **v5; // rcx

  if ( !*((_DWORD *)a2 + 8) )
  {
    v3 = *a2;
    if ( (*a2)[1] != (struct _VOLUME_MANAGER *)a2 || (v4 = a2[1], *v4 != (struct _VOLUME_MANAGER *)a2) )
      __fastfail(3u);
    *v4 = (struct _VOLUME_MANAGER *)v3;
    v3[1] = (struct _VOLUME_MANAGER *)v4;
    v5 = a2[6];
    if ( v5 )
      ObfDereferenceObject(v5);
    ExFreePoolWithTag(a2, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001c9a8  push    rbx
0x14001c9aa  sub     rsp, 20h
0x14001c9ae  cmp     dword ptr [rdx+20h], 0
0x14001c9b2  mov     rbx, rdx
0x14001c9b5  jnz     short loc_14001C9F6
0x14001c9b7  mov     rax, [rdx]
0x14001c9ba  cmp     [rax+8], rdx
0x14001c9be  jnz     short loc_14001C9FF
0x14001c9c0  mov     rcx, [rdx+8]
0x14001c9c4  cmp     [rcx], rdx
0x14001c9c7  jnz     short loc_14001C9FF
0x14001c9c9  mov     [rcx], rax
0x14001c9cc  mov     [rax+8], rcx
0x14001c9d0  mov     rcx, [rdx+30h]; Object
0x14001c9d4  test    rcx, rcx
0x14001c9d7  jz      short loc_14001C9E5
0x14001c9d9  call    cs:__imp_ObfDereferenceObject
0x14001c9e0  nop     dword ptr [rax+rax+00h]
0x14001c9e5  xor     edx, edx; Tag
0x14001c9e7  mov     rcx, rbx; P
0x14001c9ea  call    cs:__imp_ExFreePoolWithTag
0x14001c9f1  nop     dword ptr [rax+rax+00h]
0x14001c9f6  xor     eax, eax
0x14001c9f8  add     rsp, 20h
0x14001c9fc  pop     rbx
0x14001c9fd  retn
0x14001c9ff  mov     ecx, 3
0x14001ca04  int     29h; Win8: RtlFailFast(ecx)
```
