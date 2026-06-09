# CJOLT::JOLTJetCreateIndex(ulong,ulong,ushort const *,ulong,ushort const *,ulong,ulong,long &)

- ea: `0x1001ea50`
- end: `0x1001ead2`
- name: `?JOLTJetCreateIndex@CJOLT@@SGJKKPBGK0KKAAJ@Z`
- size: `130`
- prototype: `int __stdcall(unsigned int, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1001d7f0`
- `0x10046330`

## callees

- `0x1001ea50`

## import_xrefs

- `msjet40!__imp__JetCreateIndex@28` at `0x1001ea65`
- `msjet40!__imp__JetCreateIndex@28` at `0x1001ea65`

## pseudocode

```c
int __userpurge CJOLT::JOLTJetCreateIndex@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        unsigned int a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        int *a8,
        unsigned int a9,
        int *a10)
{
  int Index; // ecx

  Index = JetCreateIndex(a2, a1, a3, a4, a5, a6, 0);
  *a8 = Index;
  if ( Index <= -1403 )
  {
    switch ( Index )
    {
      case -1403:
        return -2147217868;
      case -1907:
      case -1809:
        return -2147217911;
      case -1507:
        return -2147217903;
    }
    return -2147467259;
  }
  if ( Index && Index != 1409 && Index != 5011 )
    return -2147467259;
  return 0;
}

```

## disassembly

```asm
0x1001ea50  mov     edi, edi
0x1001ea52  push    ebp
0x1001ea53  mov     ebp, esp
0x1001ea55  push    0
0x1001ea57  push    [ebp+arg_C]
0x1001ea5a  push    [ebp+arg_8]
0x1001ea5d  push    [ebp+arg_4]
0x1001ea60  push    [ebp+arg_0]
0x1001ea63  push    edx
0x1001ea64  push    ecx
0x1001ea65  call    ds:__imp__JetCreateIndex@28; JetCreateIndex(x,x,x,x,x,x,x)
0x1001ea6b  mov     ecx, eax
0x1001ea6d  mov     eax, [ebp+arg_14]
0x1001ea70  mov     [eax], ecx
0x1001ea72  cmp     ecx, 0FFFFFA85h
0x1001ea78  jg      short loc_1001EAAF
0x1001ea7a  jz      short loc_1001EAA6
0x1001ea7c  cmp     ecx, 0FFFFF88Dh
0x1001ea82  jz      short loc_1001EA9D
0x1001ea84  cmp     ecx, 0FFFFF8EFh
0x1001ea8a  jz      short loc_1001EA9D
0x1001ea8c  cmp     ecx, 0FFFFFA1Dh
0x1001ea92  jnz     short loc_1001EAC3
0x1001ea94  mov     eax, 80040E11h
0x1001ea99  pop     ebp
0x1001ea9a  retn    18h
0x1001ea9d  mov     eax, 80040E09h
0x1001eaa2  pop     ebp
0x1001eaa3  retn    18h
0x1001eaa6  mov     eax, 80040E34h
0x1001eaab  pop     ebp
0x1001eaac  retn    18h
0x1001eaaf  test    ecx, ecx
0x1001eab1  jz      short loc_1001EACC
0x1001eab3  cmp     ecx, 581h
0x1001eab9  jz      short loc_1001EACC
0x1001eabb  cmp     ecx, 1393h
0x1001eac1  jz      short loc_1001EACC
0x1001eac3  mov     eax, 80004005h
0x1001eac8  pop     ebp
0x1001eac9  retn    18h
0x1001eacc  xor     eax, eax
0x1001eace  pop     ebp
0x1001eacf  retn    18h
```
