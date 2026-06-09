# ClassDeleteSrbLookasideList

- ea: `0x14005c540`
- end: `0x14005c5a0`
- name: `ClassDeleteSrbLookasideList`
- size: `96`
- prototype: `void __stdcall(PCOMMON_DEVICE_EXTENSION CommonExtension)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14001feac`
- `0x14005c540`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005c557`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005c557`

## pseudocode

```c
void __stdcall ClassDeleteSrbLookasideList(PCOMMON_DEVICE_EXTENSION CommonExtension)
{
  char v1; // al

  v1 = *((_BYTE *)CommonExtension + 104);
  if ( (v1 & 4) != 0 )
  {
    *((_BYTE *)CommonExtension + 104) = v1 & 0xFB;
    ExDeleteNPagedLookasideList(&CommonExtension->SrbLookasideList);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids);
  }
}

```

## disassembly

```asm
0x14005c540  sub     rsp, 28h
0x14005c544  mov     al, [rcx+68h]
0x14005c547  test    al, 4
0x14005c549  jz      short loc_14005C565
0x14005c54b  and     al, 0FBh
0x14005c54d  mov     [rcx+68h], al
0x14005c550  add     rcx, 100h; Lookaside
0x14005c557  call    cs:__imp_ExDeleteNPagedLookasideList
0x14005c55e  nop     dword ptr [rax+rax+00h]
0x14005c563  jmp     short loc_14005C59A
0x14005c565  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c56c  lea     rax, WPP_GLOBAL_Control
0x14005c573  cmp     rcx, rax
0x14005c576  jz      short loc_14005C59A
0x14005c578  mov     eax, [rcx+2Ch]
0x14005c57b  test    al, 1
0x14005c57d  jz      short loc_14005C59A
0x14005c57f  cmp     byte ptr [rcx+29h], 3
0x14005c583  jb      short loc_14005C59A
0x14005c585  mov     rcx, [rcx+18h]
0x14005c589  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x14005c590  mov     edx, 17h
0x14005c595  call    WPP_SF_
0x14005c59a  add     rsp, 28h
0x14005c59e  retn
```
