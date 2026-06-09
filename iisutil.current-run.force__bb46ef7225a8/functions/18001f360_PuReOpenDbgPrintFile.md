# PuReOpenDbgPrintFile

- ea: `0x18001f360`
- end: `0x18001f39f`
- name: `PuReOpenDbgPrintFile`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180015e20`
- `0x18001ecc8`
- `0x18001f360`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001f38c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001f38c`

## string_xrefs

- `0x18001f385`: ` Error: MakeBkupCopy() Not Yet Implemented\n`

## pseudocode

```c
__int64 __fastcall PuReOpenDbgPrintFile(__int64 a1)
{
  if ( !a1 )
    return 87;
  PuCloseDbgPrintFile();
  if ( (*(_BYTE *)(a1 + 648) & 0x10) != 0 )
    OutputDebugStringA(" Error: MakeBkupCopy() Not Yet Implemented\n");
  return PuOpenDbgFileLocal(a1);
}

```

## disassembly

```asm
0x18001f360  push    rbx
0x18001f362  sub     rsp, 20h
0x18001f366  mov     rbx, rcx
0x18001f369  test    rcx, rcx
0x18001f36c  jnz     short loc_18001F377
0x18001f36e  lea     eax, [rcx+57h]
0x18001f371  add     rsp, 20h
0x18001f375  pop     rbx
0x18001f376  retn
0x18001f377  call    PuCloseDbgPrintFile
0x18001f37c  test    byte ptr [rbx+288h], 10h
0x18001f383  jz      short loc_18001F392
0x18001f385  lea     rcx, aErrorMakebkupc; " Error: MakeBkupCopy() Not Yet Implemen"...
0x18001f38c  call    cs:__imp_OutputDebugStringA
0x18001f392  mov     rcx, rbx
0x18001f395  add     rsp, 20h
0x18001f399  pop     rbx
0x18001f39a  jmp     PuOpenDbgFileLocal
```
