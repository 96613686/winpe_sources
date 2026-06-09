# _get_image_app_type

- ea: `0x140001404`
- end: `0x14000144a`
- name: `_get_image_app_type`
- size: `70`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001030`

## callees

- `0x1400013ac`
- `0x140001404`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000140e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000140e`

## pseudocode

```c
__int64 __fastcall get_image_app_type(unsigned int a1)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rax

  ModuleHandleW = GetModuleHandleW(0);
  if ( ModuleHandleW )
  {
    v3 = RtlpImageNtHeader((__int64)ModuleHandleW);
    if ( v3 )
    {
      if ( *(_WORD *)(v3 + 92) == 2 )
        return 2;
      if ( *(_WORD *)(v3 + 92) == 3 )
        return 1;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140001404  push    rbx
0x140001406  sub     rsp, 20h
0x14000140a  mov     ebx, ecx
0x14000140c  xor     ecx, ecx; lpModuleName
0x14000140e  call    cs:__imp_GetModuleHandleW
0x140001414  test    rax, rax
0x140001417  jz      short loc_140001442
0x140001419  mov     rcx, rax
0x14000141c  call    RtlpImageNtHeader
0x140001421  test    rax, rax
0x140001424  jz      short loc_140001442
0x140001426  mov     ecx, 2
0x14000142b  cmp     [rax+5Ch], cx
0x14000142f  jnz     short loc_140001435
0x140001431  mov     eax, ecx
0x140001433  jmp     short loc_140001444
0x140001435  cmp     word ptr [rax+5Ch], 3
0x14000143a  mov     ecx, 1
0x14000143f  cmovz   ebx, ecx
0x140001442  mov     eax, ebx
0x140001444  add     rsp, 20h
0x140001448  pop     rbx
0x140001449  retn
```
