# _get_image_app_type

- ea: `0x140001474`
- end: `0x1400014ba`
- name: `_get_image_app_type`
- size: `70`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001090`

## callees

- `0x14000141c`
- `0x140001474`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000147e`
- `KERNEL32!GetModuleHandleW` at `0x14000147e`

## pseudocode

```c
__int64 __fastcall get_image_app_type(unsigned int a1)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rax

  ModuleHandleW = GetModuleHandleW(0);
  if ( ModuleHandleW )
  {
    v3 = RtlpImageNtHeader(ModuleHandleW);
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
0x140001474  push    rbx
0x140001476  sub     rsp, 20h
0x14000147a  mov     ebx, ecx
0x14000147c  xor     ecx, ecx; lpModuleName
0x14000147e  call    cs:__imp_GetModuleHandleW
0x140001484  test    rax, rax
0x140001487  jz      short loc_1400014B2
0x140001489  mov     rcx, rax
0x14000148c  call    RtlpImageNtHeader
0x140001491  test    rax, rax
0x140001494  jz      short loc_1400014B2
0x140001496  mov     ecx, 2
0x14000149b  cmp     [rax+5Ch], cx
0x14000149f  jnz     short loc_1400014A5
0x1400014a1  mov     eax, ecx
0x1400014a3  jmp     short loc_1400014B4
0x1400014a5  cmp     word ptr [rax+5Ch], 3
0x1400014aa  mov     ecx, 1
0x1400014af  cmovz   ebx, ecx
0x1400014b2  mov     eax, ebx
0x1400014b4  add     rsp, 20h
0x1400014b8  pop     rbx
0x1400014b9  retn
```
