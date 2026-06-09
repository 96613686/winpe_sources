# PuReOpenDbgPrintFile

- ea: `0x1800205f0`
- end: `0x180020636`
- name: `PuReOpenDbgPrintFile`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180016a20`
- `0x18001fed8`
- `0x1800205f0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002061d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002061d`

## string_xrefs

- `0x180020616`: ` Error: MakeBkupCopy() Not Yet Implemented\n`

## pseudocode

```c
__int64 __fastcall PuReOpenDbgPrintFile(__int64 a1)
{
  if ( !a1 )
    return 87;
  PuCloseDbgPrintFile(a1);
  if ( (*(_BYTE *)(a1 + 648) & 0x10) != 0 )
    OutputDebugStringA(" Error: MakeBkupCopy() Not Yet Implemented\n");
  return PuOpenDbgFileLocal(a1);
}

```

## disassembly

```asm
0x1800205f0  push    rbx
0x1800205f2  sub     rsp, 20h
0x1800205f6  mov     rbx, rcx
0x1800205f9  test    rcx, rcx
0x1800205fc  jnz     short loc_180020608
0x1800205fe  lea     eax, [rcx+57h]
0x180020601  add     rsp, 20h
0x180020605  pop     rbx
0x180020606  retn
0x180020608  call    PuCloseDbgPrintFile
0x18002060d  test    byte ptr [rbx+288h], 10h
0x180020614  jz      short loc_180020629
0x180020616  lea     rcx, aErrorMakebkupc; " Error: MakeBkupCopy() Not Yet Implemen"...
0x18002061d  call    cs:__imp_OutputDebugStringA
0x180020624  nop     dword ptr [rax+rax+00h]
0x180020629  mov     rcx, rbx
0x18002062c  add     rsp, 20h
0x180020630  pop     rbx
0x180020631  jmp     PuOpenDbgFileLocal
```
