# myNCOpenStorageProvider(unsigned __int64 *,ushort const *,ulong)

- ea: `0x180021d08`
- end: `0x180021d54`
- name: `?myNCOpenStorageProvider@@YAJPEA_KPEBGK@Z`
- size: `76`
- prototype: `__int64 __fastcall(unsigned __int64 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800168a0`
- `0x1800217b4`

## callees

- `0x180008610`
- `0x180021d08`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180021d1b`
- `ncrypt!NCryptOpenStorageProvider` at `0x180021d1b`

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
0x180021d08  mov     [rsp+arg_0], rbx
0x180021d0d  push    rdi
0x180021d0e  sub     rsp, 20h
0x180021d12  mov     r8d, 40h ; '@'; dwFlags
0x180021d18  mov     rdi, rdx
0x180021d1b  call    cs:__imp_NCryptOpenStorageProvider
0x180021d21  mov     ebx, eax
0x180021d23  test    eax, eax
0x180021d25  jz      short loc_180021D47
0x180021d27  xor     r9d, r9d; int
0x180021d2a  mov     r8d, eax; int
0x180021d2d  mov     edx, 2DC01C4h; unsigned int
0x180021d32  mov     rcx, rdi; unsigned __int16 *
0x180021d35  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180021d3a  test    ebx, ebx
0x180021d3c  jle     short loc_180021D47
0x180021d3e  movzx   ebx, bx
0x180021d41  or      ebx, 80070000h
0x180021d47  mov     eax, ebx
0x180021d49  mov     rbx, [rsp+28h+arg_0]
0x180021d4e  add     rsp, 20h
0x180021d52  pop     rdi
0x180021d53  retn
```
