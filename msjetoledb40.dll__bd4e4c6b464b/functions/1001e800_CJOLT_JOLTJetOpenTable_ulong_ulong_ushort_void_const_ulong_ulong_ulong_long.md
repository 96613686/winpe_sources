# CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)

- ea: `0x1001e800`
- end: `0x1001e8a0`
- name: `?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z`
- size: `160`
- prototype: `int __stdcall(unsigned int, unsigned int, unsigned __int16 *, const void *, unsigned int, unsigned int, unsigned int *, int *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1001d7f0`
- `0x1001df20`
- `0x100413c0`
- `0x10041890`
- `0x10041f50`
- `0x10043f20`
- `0x10044460`
- `0x100446b0`
- `0x10044880`
- `0x10044ac0`
- `0x10046330`

## callees

- `0x1001e800`

## import_xrefs

- `msjet40!__imp__JetOpenTable@28` at `0x1001e816`
- `msjet40!__imp__JetOpenTable@28` at `0x1001e816`

## pseudocode

```c
int __userpurge CJOLT::JOLTJetOpenTable@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        const void *a6,
        _DWORD *a7,
        int *a8,
        unsigned int *a9,
        int *a10)
{
  int v10; // ecx

  v10 = JetOpenTable(a2, a1, a3, 0, 0, a6, a7);
  *a8 = v10;
  if ( v10 <= -1304 )
  {
    if ( v10 != -1304 )
    {
      if ( v10 == -1907 || v10 == -1809 )
      {
        *a7 = -1;
        return -2147217911;
      }
      if ( v10 == -1305 )
      {
        *a7 = -1;
        return -2147217865;
      }
      goto LABEL_11;
    }
    goto LABEL_13;
  }
  if ( v10 == -1302 )
  {
LABEL_13:
    *a7 = -1;
    return -2147217856;
  }
  if ( v10 && v10 != 5011 )
  {
LABEL_11:
    *a7 = -1;
    return -2147467259;
  }
  return 0;
}

```

## disassembly

```asm
0x1001e800  mov     edi, edi
0x1001e802  push    ebp
0x1001e803  mov     ebp, esp
0x1001e805  push    esi
0x1001e806  mov     esi, [ebp+arg_10]
0x1001e809  push    esi
0x1001e80a  push    [ebp+arg_C]
0x1001e80d  push    0
0x1001e80f  push    0
0x1001e811  push    [ebp+arg_0]
0x1001e814  push    edx
0x1001e815  push    ecx
0x1001e816  call    ds:__imp__JetOpenTable@28; JetOpenTable(x,x,x,x,x,x,x)
0x1001e81c  mov     ecx, eax
0x1001e81e  mov     eax, [ebp+arg_14]
0x1001e821  mov     [eax], ecx
0x1001e823  cmp     ecx, 0FFFFFAE8h
0x1001e829  jg      short loc_1001E865
0x1001e82b  jz      short loc_1001E890
0x1001e82d  cmp     ecx, 0FFFFF88Dh
0x1001e833  jz      short loc_1001E855
0x1001e835  cmp     ecx, 0FFFFF8EFh
0x1001e83b  jz      short loc_1001E855
0x1001e83d  cmp     ecx, 0FFFFFAE7h
0x1001e843  jnz     short loc_1001E879
0x1001e845  mov     dword ptr [esi], 0FFFFFFFFh
0x1001e84b  mov     eax, 80040E37h
0x1001e850  pop     esi
0x1001e851  pop     ebp
0x1001e852  retn    18h
0x1001e855  mov     dword ptr [esi], 0FFFFFFFFh
0x1001e85b  mov     eax, 80040E09h
0x1001e860  pop     esi
0x1001e861  pop     ebp
0x1001e862  retn    18h
0x1001e865  cmp     ecx, 0FFFFFAEAh
0x1001e86b  jz      short loc_1001E890
0x1001e86d  test    ecx, ecx
0x1001e86f  jz      short loc_1001E889
0x1001e871  cmp     ecx, 1393h
0x1001e877  jz      short loc_1001E889
0x1001e879  mov     dword ptr [esi], 0FFFFFFFFh
0x1001e87f  mov     eax, 80004005h
0x1001e884  pop     esi
0x1001e885  pop     ebp
0x1001e886  retn    18h
0x1001e889  xor     eax, eax
0x1001e88b  pop     esi
0x1001e88c  pop     ebp
0x1001e88d  retn    18h
0x1001e890  mov     dword ptr [esi], 0FFFFFFFFh
0x1001e896  mov     eax, 80040E40h
0x1001e89b  pop     esi
0x1001e89c  pop     ebp
0x1001e89d  retn    18h
```
