# _get_image_app_type

- ea: `0x140001454`
- end: `0x14000149a`
- name: `_get_image_app_type`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001060`

## callees

- `0x1400013fc`
- `0x140001454`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000145e`
- `KERNEL32!GetModuleHandleW` at `0x14000145e`

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
0x140001454  push    rbx
0x140001456  sub     rsp, 20h
0x14000145a  mov     ebx, ecx
0x14000145c  xor     ecx, ecx; lpModuleName
0x14000145e  call    cs:__imp_GetModuleHandleW
0x140001464  test    rax, rax
0x140001467  jz      short loc_140001492
0x140001469  mov     rcx, rax
0x14000146c  call    RtlpImageNtHeader
0x140001471  test    rax, rax
0x140001474  jz      short loc_140001492
0x140001476  mov     ecx, 2
0x14000147b  cmp     [rax+5Ch], cx
0x14000147f  jnz     short loc_140001485
0x140001481  mov     eax, ecx
0x140001483  jmp     short loc_140001494
0x140001485  cmp     word ptr [rax+5Ch], 3
0x14000148a  mov     ecx, 1
0x14000148f  cmovz   ebx, ecx
0x140001492  mov     eax, ebx
0x140001494  add     rsp, 20h
0x140001498  pop     rbx
0x140001499  retn
```
