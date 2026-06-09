# CJOLT::JOLTJetOpenDatabase(ulong,ushort const *,ushort const *,ulong *,ulong,long &)

- ea: `0x1001e960`
- end: `0x1001e9ca`
- name: `?JOLTJetOpenDatabase@CJOLT@@SGJKPBG0PAKKAAJ@Z`
- size: `106`
- prototype: `int __userpurge@<eax>(int@<edx>, int@<ecx>, unsigned int, unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10044ee0`

## callees

- `0x1001e960`

## import_xrefs

- `msjet40!__imp__JetOpenDatabase@20` at `0x1001e972`
- `msjet40!__imp__JetOpenDatabase@20` at `0x1001e972`

## pseudocode

```c
int __userpurge CJOLT::JOLTJetOpenDatabase@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        unsigned int a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int *a6,
        unsigned int a7,
        int *a8)
{
  int v8; // eax
  bool v9; // cc

  v8 = JetOpenDatabase(a2, a1, a3, a4, a5);
  *a6 = v8;
  if ( v8 > 1208 )
  {
    if ( v8 == 5011 )
      return 0;
    v9 = v8 <= 0;
  }
  else
  {
    if ( v8 == 1208 )
    {
      *a6 = 0;
      return 0;
    }
    if ( v8 == -1905 )
      return -2147217843;
    v9 = v8 <= 0;
    if ( !v8 )
      return 0;
  }
  if ( !v9 )
    return 0;
  *(_DWORD *)a4 = -1;
  return -2147467259;
}

```

## disassembly

```asm
0x1001e960  mov     edi, edi
0x1001e962  push    ebp
0x1001e963  mov     ebp, esp
0x1001e965  push    esi
0x1001e966  push    [ebp+arg_8]
0x1001e969  mov     esi, [ebp+arg_4]
0x1001e96c  push    esi
0x1001e96d  push    [ebp+arg_0]
0x1001e970  push    edx
0x1001e971  push    ecx
0x1001e972  call    ds:__imp__JetOpenDatabase@20; JetOpenDatabase(x,x,x,x,x)
0x1001e978  mov     ecx, [ebp+arg_C]
0x1001e97b  mov     [ecx], eax
0x1001e97d  cmp     eax, 4B8h
0x1001e982  jg      short loc_1001E9AF
0x1001e984  jz      short loc_1001E9A2
0x1001e986  cmp     eax, 0FFFFF88Fh
0x1001e98b  jz      short loc_1001E998
0x1001e98d  test    eax, eax
0x1001e98f  jnz     short loc_1001E9B8
0x1001e991  xor     eax, eax
0x1001e993  pop     esi
0x1001e994  pop     ebp
0x1001e995  retn    10h
0x1001e998  mov     eax, 80040E4Dh
0x1001e99d  pop     esi
0x1001e99e  pop     ebp
0x1001e99f  retn    10h
0x1001e9a2  mov     dword ptr [ecx], 0
0x1001e9a8  xor     eax, eax
0x1001e9aa  pop     esi
0x1001e9ab  pop     ebp
0x1001e9ac  retn    10h
0x1001e9af  cmp     eax, 1393h
0x1001e9b4  jz      short loc_1001E991
0x1001e9b6  test    eax, eax
0x1001e9b8  jg      short loc_1001E991
0x1001e9ba  mov     dword ptr [esi], 0FFFFFFFFh
0x1001e9c0  mov     eax, 80004005h
0x1001e9c5  pop     esi
0x1001e9c6  pop     ebp
0x1001e9c7  retn    10h
```
