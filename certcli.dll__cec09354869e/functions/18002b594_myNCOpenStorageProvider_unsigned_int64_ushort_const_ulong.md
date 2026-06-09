# myNCOpenStorageProvider(unsigned __int64 *,ushort const *,ulong)

- ea: `0x18002b594`
- end: `0x18002b5e1`
- name: `?myNCOpenStorageProvider@@YAJPEA_KPEBGK@Z`
- size: `77`
- prototype: `__int64 __fastcall(unsigned __int64 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002b640`

## callees

- `0x18002b594`

## import_xrefs

- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18002b5c1`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18002b5c1`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002b5a7`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002b5a7`

## pseudocode

```c
__int64 __fastcall myNCOpenStorageProvider(unsigned __int64 *a1, const unsigned __int16 *a2)
{
  SECURITY_STATUS v3; // eax
  int v4; // ebx

  v3 = NCryptOpenStorageProvider(a1, a2, 0x40u);
  v4 = v3;
  if ( v3 )
  {
    CSPrintErrorLineFileData2(a2, 0x2DC01C4u, v3, 0);
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002b594  mov     [rsp+arg_0], rbx
0x18002b599  push    rdi
0x18002b59a  sub     rsp, 20h
0x18002b59e  mov     r8d, 40h ; '@'; dwFlags
0x18002b5a4  mov     rdi, rdx
0x18002b5a7  call    cs:__imp_NCryptOpenStorageProvider
0x18002b5ad  mov     ebx, eax
0x18002b5af  test    eax, eax
0x18002b5b1  jz      short loc_18002B5D4
0x18002b5b3  xor     r9d, r9d
0x18002b5b6  mov     r8d, eax
0x18002b5b9  mov     edx, 2DC01C4h
0x18002b5be  mov     rcx, rdi
0x18002b5c1  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002b5c7  test    ebx, ebx
0x18002b5c9  jle     short loc_18002B5D4
0x18002b5cb  movzx   ebx, bx
0x18002b5ce  or      ebx, 80070000h
0x18002b5d4  mov     eax, ebx
0x18002b5d6  mov     rbx, [rsp+28h+arg_0]
0x18002b5db  add     rsp, 20h
0x18002b5df  pop     rdi
0x18002b5e0  retn
```
