# CJOLT::JOLTJetGetSidFromName(ulong,ushort const *,void *,ulong,ulong *,long *,long &)

- ea: `0x1001eb70`
- end: `0x1001ebb6`
- name: `?JOLTJetGetSidFromName@CJOLT@@SGJKPBGPAXKPAKPAJAAJ@Z`
- size: `70`
- prototype: `int __stdcall(unsigned int, const unsigned __int16 *, void *, unsigned int, unsigned int *, int *, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x100413c0`
- `0x10041890`
- `0x10041f50`

## callees

- `0x1001eb70`

## import_xrefs

- `msjet40!__imp__JetGetSidFromName@24` at `0x1001eb85`
- `msjet40!__imp__JetGetSidFromName@24` at `0x1001eb85`

## pseudocode

```c
int __userpurge CJOLT::JOLTJetGetSidFromName@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        unsigned int a3,
        const unsigned __int16 *a4,
        void *a5,
        unsigned int a6,
        unsigned int *a7,
        int *a8,
        int *a9)
{
  int SidFromName; // ecx

  SidFromName = JetGetSidFromName(a2, a1, a3, 511, a5, a6);
  *a7 = SidFromName;
  if ( SidFromName == -1903 )
    return -2147217813;
  if ( SidFromName >= 0 )
    return 0;
  return -2147467259;
}

```

## disassembly

```asm
0x1001eb70  mov     edi, edi
0x1001eb72  push    ebp
0x1001eb73  mov     ebp, esp
0x1001eb75  push    [ebp+arg_C]
0x1001eb78  push    [ebp+arg_8]
0x1001eb7b  push    1FFh
0x1001eb80  push    [ebp+arg_0]
0x1001eb83  push    edx
0x1001eb84  push    ecx
0x1001eb85  call    ds:__imp__JetGetSidFromName@24; JetGetSidFromName(x,x,x,x,x,x)
0x1001eb8b  mov     ecx, eax
0x1001eb8d  mov     eax, [ebp+arg_10]
0x1001eb90  mov     [eax], ecx
0x1001eb92  cmp     ecx, 0FFFFF891h
0x1001eb98  jz      short loc_1001EBAD
0x1001eb9a  test    ecx, ecx
0x1001eb9c  jns     short loc_1001EBA7
0x1001eb9e  mov     eax, 80004005h
0x1001eba3  pop     ebp
0x1001eba4  retn    14h
0x1001eba7  xor     eax, eax
0x1001eba9  pop     ebp
0x1001ebaa  retn    14h
0x1001ebad  mov     eax, 80040E6Bh
0x1001ebb2  pop     ebp
0x1001ebb3  retn    14h
```
