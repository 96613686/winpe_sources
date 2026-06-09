# FwHashtableCreate

- ea: `0x180012da0`
- end: `0x180012ddc`
- name: `FwHashtableCreate`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800047e0`
- `0x180012da0`
- `0x180012de4`

## string_xrefs

- `0x180012dbe`: `FwHashtableCreate`
- `0x180012dcc`: `FwHashtableCreate`

## pseudocode

```c
__int64 __fastcall FwHashtableCreate(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx

  v1 = FwHashtableCreateEx(a1, a1);
  v2 = v1;
  if ( v1 < 0 )
  {
    FwReportReturnError("FwHashtableCreate", (unsigned int)v1);
    return (unsigned int)FwReportReturnError("FwHashtableCreate", v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180012da0  push    rbx
0x180012da2  sub     rsp, 20h
0x180012da6  mov     rdx, rcx
0x180012da9  call    FwHashtableCreateEx
0x180012dae  mov     ebx, eax
0x180012db0  test    eax, eax
0x180012db2  js      short loc_180012DBC
0x180012db4  mov     eax, ebx
0x180012db6  add     rsp, 20h
0x180012dba  pop     rbx
0x180012dbb  retn
0x180012dbc  mov     edx, ebx
0x180012dbe  lea     rcx, aFwhashtablecre_0; "FwHashtableCreate"
0x180012dc5  call    FwReportReturnError
0x180012dca  mov     edx, ebx
0x180012dcc  lea     rcx, aFwhashtablecre_0; "FwHashtableCreate"
0x180012dd3  call    FwReportReturnError
0x180012dd8  mov     ebx, eax
0x180012dda  jmp     short loc_180012DB4
```
