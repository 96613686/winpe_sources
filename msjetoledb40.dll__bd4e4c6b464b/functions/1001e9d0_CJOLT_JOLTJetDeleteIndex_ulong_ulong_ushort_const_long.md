# CJOLT::JOLTJetDeleteIndex(ulong,ulong,ushort const *,long &)

- ea: `0x1001e9d0`
- end: `0x1001ea3f`
- name: `?JOLTJetDeleteIndex@CJOLT@@SGJKKPBGAAJ@Z`
- size: `111`
- prototype: `int __stdcall(unsigned int, unsigned int, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1001df20`
- `0x10044ac0`

## callees

- `0x1001e9d0`

## import_xrefs

- `msjet40!__imp__JetDeleteIndex@12` at `0x1001e9da`
- `msjet40!__imp__JetDeleteIndex@12` at `0x1001e9da`

## pseudocode

```c
int __userpurge CJOLT::JOLTJetDeleteIndex@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        unsigned int a3,
        int *a4,
        const unsigned __int16 *a5,
        int *a6)
{
  int v6; // ecx

  v6 = JetDeleteIndex(a2, a1, a3);
  *a4 = v6;
  if ( v6 <= -1051 )
  {
    switch ( v6 )
    {
      case -1051:
        return -2147217866;
      case -1907:
      case -1809:
        return -2147217911;
      case -1404:
        return -2147217867;
    }
    return -2147467259;
  }
  if ( v6 == -1002 )
    return -2147217867;
  if ( v6 )
    return -2147467259;
  return 0;
}

```

## disassembly

```asm
0x1001e9d0  mov     edi, edi
0x1001e9d2  push    ebp
0x1001e9d3  mov     ebp, esp
0x1001e9d5  push    [ebp+arg_0]
0x1001e9d8  push    edx
0x1001e9d9  push    ecx
0x1001e9da  call    ds:__imp__JetDeleteIndex@12; JetDeleteIndex(x,x,x)
0x1001e9e0  mov     ecx, eax
0x1001e9e2  mov     eax, [ebp+arg_4]
0x1001e9e5  mov     [eax], ecx
0x1001e9e7  cmp     ecx, 0FFFFFBE5h
0x1001e9ed  jg      short loc_1001EA24
0x1001e9ef  jz      short loc_1001EA1B
0x1001e9f1  cmp     ecx, 0FFFFF88Dh
0x1001e9f7  jz      short loc_1001EA12
0x1001e9f9  cmp     ecx, 0FFFFF8EFh
0x1001e9ff  jz      short loc_1001EA12
0x1001ea01  cmp     ecx, 0FFFFFA84h
0x1001ea07  jnz     short loc_1001EA30
0x1001ea09  mov     eax, 80040E35h
0x1001ea0e  pop     ebp
0x1001ea0f  retn    8
0x1001ea12  mov     eax, 80040E09h
0x1001ea17  pop     ebp
0x1001ea18  retn    8
0x1001ea1b  mov     eax, 80040E36h
0x1001ea20  pop     ebp
0x1001ea21  retn    8
0x1001ea24  cmp     ecx, 0FFFFFC16h
0x1001ea2a  jz      short loc_1001EA09
0x1001ea2c  test    ecx, ecx
0x1001ea2e  jz      short loc_1001EA39
0x1001ea30  mov     eax, 80004005h
0x1001ea35  pop     ebp
0x1001ea36  retn    8
0x1001ea39  xor     eax, eax
0x1001ea3b  pop     ebp
0x1001ea3c  retn    8
```
