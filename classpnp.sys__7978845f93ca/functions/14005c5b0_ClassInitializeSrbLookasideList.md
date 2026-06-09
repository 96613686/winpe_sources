# ClassInitializeSrbLookasideList

- ea: `0x14005c5b0`
- end: `0x14005c619`
- name: `ClassInitializeSrbLookasideList`
- size: `105`
- prototype: `void __stdcall(PCOMMON_DEVICE_EXTENSION CommonExtension, ULONG NumberElements)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14005c5b0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005c602`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005c602`

## pseudocode

```c
void __stdcall ClassInitializeSrbLookasideList(PCOMMON_DEVICE_EXTENSION CommonExtension, ULONG NumberElements)
{
  char v2; // al
  USHORT Depth; // r8
  SIZE_T Size; // rdx

  v2 = *((_BYTE *)CommonExtension + 104);
  Depth = NumberElements;
  if ( (v2 & 4) == 0 )
  {
    Size = 184;
    if ( (v2 & 1) != 0 && BYTE6(CommonExtension[1].LowerDeviceObject->AttachedDevice) != 1 )
      Size = 88;
    ExInitializeNPagedLookasideList(&CommonExtension->SrbLookasideList, 0, 0, 0x200u, Size, 0x24736353u, Depth);
    *((_BYTE *)CommonExtension + 104) |= 4u;
  }
}

```

## disassembly

```asm
0x14005c5b0  push    rbx
0x14005c5b2  sub     rsp, 40h
0x14005c5b6  mov     al, [rcx+68h]
0x14005c5b9  mov     r8d, edx
0x14005c5bc  mov     rbx, rcx
0x14005c5bf  test    al, 4
0x14005c5c1  jnz     short loc_14005C612
0x14005c5c3  mov     edx, 0B8h
0x14005c5c8  test    al, 1
0x14005c5ca  jz      short loc_14005C5DD
0x14005c5cc  mov     rax, [rcx+210h]
0x14005c5d3  lea     ecx, [rdx-60h]
0x14005c5d6  cmp     byte ptr [rax+1Eh], 1
0x14005c5da  cmovnz  edx, ecx
0x14005c5dd  mov     [rsp+48h+Depth], r8w; Depth
0x14005c5e3  lea     rcx, [rbx+100h]; Lookaside
0x14005c5ea  mov     [rsp+48h+Tag], 24736353h; Tag
0x14005c5f2  mov     r9d, 200h; Flags
0x14005c5f8  mov     [rsp+48h+Size], rdx; Size
0x14005c5fd  xor     r8d, r8d; Free
0x14005c600  xor     edx, edx; Allocate
0x14005c602  call    cs:__imp_ExInitializeNPagedLookasideList
0x14005c609  nop     dword ptr [rax+rax+00h]
0x14005c60e  or      byte ptr [rbx+68h], 4
0x14005c612  add     rsp, 40h
0x14005c616  pop     rbx
0x14005c617  retn
```
