# WSTFreeUserModeContextList(ulong)

- ea: `0x18002f40c`
- end: `0x18002f460`
- name: `?WSTFreeUserModeContextList@@YAXK@Z`
- size: `84`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180022c9c`
- `0x18002f60c`

## callees

- `0x18002f40c`
- `0x180043d58`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18002f459`

## pseudocode

```c
void __fastcall WSTFreeUserModeContextList(unsigned int a1, struct basessp::_WST_LIST *a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // edi

  v2 = 0;
  v3 = a1;
  if ( Pku2uGlobalUserModeContextsInitialized )
  {
    v3 = 256;
  }
  else if ( !a1 )
  {
    goto LABEL_5;
  }
  do
    basessp::WSTFreeList((basessp *)(&Pku2uGlobalUserModeContextList + 7 * v2++), a2);
  while ( v2 < v3 );
LABEL_5:
  RtlDeleteResource(&Pku2uGlobalUserModeContextResource);
}

```

## disassembly

```asm
0x18002f40c  mov     [rsp+arg_0], rbx
0x18002f411  push    rdi
0x18002f412  sub     rsp, 20h
0x18002f416  xor     ebx, ebx
0x18002f418  mov     edi, ecx
0x18002f41a  cmp     cs:?Pku2uGlobalUserModeContextsInitialized@@3EA, bl; uchar Pku2uGlobalUserModeContextsInitialized
0x18002f420  jz      short loc_18002F429
0x18002f422  mov     edi, 100h
0x18002f427  jmp     short loc_18002F42D
0x18002f429  test    ecx, ecx
0x18002f42b  jz      short loc_18002F448
0x18002f42d  mov     eax, ebx
0x18002f42f  imul    rcx, rax, 38h ; '8'
0x18002f433  lea     rax, ?Pku2uGlobalUserModeContextList@@3PAU_WST_LIST@basessp@@A; basessp::_WST_LIST near * Pku2uGlobalUserModeContextList
0x18002f43a  add     rcx, rax; this
0x18002f43d  call    ?WSTFreeList@basessp@@YAXPEAU_WST_LIST@1@@Z; basessp::WSTFreeList(basessp::_WST_LIST *)
0x18002f442  inc     ebx
0x18002f444  cmp     ebx, edi
0x18002f446  jb      short loc_18002F42D
0x18002f448  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE Pku2uGlobalUserModeContextResource
0x18002f44f  mov     rbx, [rsp+28h+arg_0]
0x18002f454  add     rsp, 20h
0x18002f458  pop     rdi
0x18002f459  jmp     cs:__imp_RtlDeleteResource
```
