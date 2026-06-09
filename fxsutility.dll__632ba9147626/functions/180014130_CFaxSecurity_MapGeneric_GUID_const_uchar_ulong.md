# CFaxSecurity::MapGeneric(_GUID const *,uchar *,ulong *)

- ea: `0x180014130`
- end: `0x18001414b`
- name: `?MapGeneric@CFaxSecurity@@UEAAJPEBU_GUID@@PEAEPEAK@Z`
- size: `27`
- prototype: `int(CFaxSecurity *__hidden this, const struct _GUID *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ADVAPI32!MapGenericMask` at `0x18001413e`
- `ADVAPI32!MapGenericMask` at `0x18001413e`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::MapGeneric(
        CFaxSecurity *this,
        const struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  MapGenericMask(a4, &GenericMapping);
  return 0;
}

```

## disassembly

```asm
0x180014130  sub     rsp, 28h
0x180014134  lea     rdx, GenericMapping; GenericMapping
0x18001413b  mov     rcx, r9; AccessMask
0x18001413e  call    cs:__imp_MapGenericMask
0x180014144  xor     eax, eax
0x180014146  add     rsp, 28h
0x18001414a  retn
```
