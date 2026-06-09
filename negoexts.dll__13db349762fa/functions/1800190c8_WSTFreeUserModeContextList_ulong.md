# WSTFreeUserModeContextList(ulong)

- ea: `0x1800190c8`
- end: `0x18001911c`
- name: `?WSTFreeUserModeContextList@@YAXK@Z`
- size: `84`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000cba0`
- `0x180019348`

## callees

- `0x1800190c8`
- `0x18001e1c0`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180019115`

## pseudocode

```c
void __fastcall WSTFreeUserModeContextList(unsigned int a1, struct basessp::_WST_LIST *a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // edi

  v2 = 0;
  v3 = a1;
  if ( NegoExtsGlobalUserModeContextsInitialized )
  {
    v3 = 256;
  }
  else if ( !a1 )
  {
    goto LABEL_5;
  }
  do
    basessp::WSTFreeList((basessp *)(&NegoExtsGlobalUserModeContextList + 7 * v2++), a2);
  while ( v2 < v3 );
LABEL_5:
  RtlDeleteResource(&NegoExtsGlobalUserModeContextResource);
}

```

## disassembly

```asm
0x1800190c8  mov     [rsp+arg_0], rbx
0x1800190cd  push    rdi
0x1800190ce  sub     rsp, 20h
0x1800190d2  xor     ebx, ebx
0x1800190d4  mov     edi, ecx
0x1800190d6  cmp     cs:?NegoExtsGlobalUserModeContextsInitialized@@3EA, bl; uchar NegoExtsGlobalUserModeContextsInitialized
0x1800190dc  jz      short loc_1800190E5
0x1800190de  mov     edi, 100h
0x1800190e3  jmp     short loc_1800190E9
0x1800190e5  test    ecx, ecx
0x1800190e7  jz      short loc_180019104
0x1800190e9  mov     eax, ebx
0x1800190eb  imul    rcx, rax, 38h ; '8'
0x1800190ef  lea     rax, ?NegoExtsGlobalUserModeContextList@@3PAU_WST_LIST@basessp@@A; basessp::_WST_LIST near * NegoExtsGlobalUserModeContextList
0x1800190f6  add     rcx, rax; this
0x1800190f9  call    ?WSTFreeList@basessp@@YAXPEAU_WST_LIST@1@@Z; basessp::WSTFreeList(basessp::_WST_LIST *)
0x1800190fe  inc     ebx
0x180019100  cmp     ebx, edi
0x180019102  jb      short loc_1800190E9
0x180019104  lea     rcx, ?NegoExtsGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE NegoExtsGlobalUserModeContextResource
0x18001910b  mov     rbx, [rsp+28h+arg_0]
0x180019110  add     rsp, 20h
0x180019114  pop     rdi
0x180019115  jmp     cs:__imp_RtlDeleteResource
```
