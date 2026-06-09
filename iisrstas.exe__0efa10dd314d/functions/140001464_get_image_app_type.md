# _get_image_app_type

- ea: `0x140001464`
- end: `0x1400014aa`
- name: `_get_image_app_type`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001070`

## callees

- `0x14000140c`
- `0x140001464`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000146e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000146e`

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
0x140001464  push    rbx
0x140001466  sub     rsp, 20h
0x14000146a  mov     ebx, ecx
0x14000146c  xor     ecx, ecx; lpModuleName
0x14000146e  call    cs:__imp_GetModuleHandleW
0x140001474  test    rax, rax
0x140001477  jz      short loc_1400014A2
0x140001479  mov     rcx, rax
0x14000147c  call    RtlpImageNtHeader
0x140001481  test    rax, rax
0x140001484  jz      short loc_1400014A2
0x140001486  mov     ecx, 2
0x14000148b  cmp     [rax+5Ch], cx
0x14000148f  jnz     short loc_140001495
0x140001491  mov     eax, ecx
0x140001493  jmp     short loc_1400014A4
0x140001495  cmp     word ptr [rax+5Ch], 3
0x14000149a  mov     ecx, 1
0x14000149f  cmovz   ebx, ecx
0x1400014a2  mov     eax, ebx
0x1400014a4  add     rsp, 20h
0x1400014a8  pop     rbx
0x1400014a9  retn
```
