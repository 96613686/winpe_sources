# NcaFreeMuiString

- ea: `0x180019344`
- end: `0x18001935f`
- name: `NcaFreeMuiString`
- size: `27`
- prototype: `void __fastcall(wchar_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d04`
- `0x18000966c`
- `0x180012214`
- `0x180019368`

## callees

- `0x180003770`
- `0x180019344`

## pseudocode

```c
void __fastcall NcaFreeMuiString(wchar_t *a1)
{
  if ( a1 != L"Unable to load string message" )
    NcaFree(a1);
}

```

## disassembly

```asm
0x180019344  sub     rsp, 28h
0x180019348  lea     rax, aUnableToLoadSt; "Unable to load string message"
0x18001934f  cmp     rcx, rax
0x180019352  jz      short loc_180019359
0x180019354  call    NcaFree
0x180019359  add     rsp, 28h
0x18001935d  retn
```
