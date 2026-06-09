# Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)

- ea: `0x180009b48`
- end: `0x180009b7a`
- name: `?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180009b48`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x180009b66`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180009b66`

## pseudocode

```c
_QWORD *__fastcall Common::GenericMap<unsigned short const *,unsigned short const *>::Find(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF

  Buffer[0] = a2;
  Buffer[1] = 0;
  result = RtlLookupElementGenericTableAvl(Table, Buffer);
  if ( result )
    return (_QWORD *)result[1];
  return result;
}

```

## disassembly

```asm
0x180009b48  sub     rsp, 38h
0x180009b4c  mov     rcx, cs:Table; Table
0x180009b53  mov     [rsp+38h+Buffer], rdx
0x180009b58  lea     rdx, [rsp+38h+Buffer]; Buffer
0x180009b5d  mov     [rsp+38h+var_10], 0
0x180009b66  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180009b6c  test    rax, rax
0x180009b6f  jz      short loc_180009B75
0x180009b71  mov     rax, [rax+8]
0x180009b75  add     rsp, 38h
0x180009b79  retn
```
