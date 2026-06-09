# IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)

- ea: `0x180010f10`
- end: `0x180010f5c`
- name: `?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z`
- size: `76`
- prototype: `bool(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010f10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010f32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010f32`

## pseudocode

```c
bool __fastcall IsStringEqualOrdinalIgnoreCase(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  if ( !a1 )
    a1 = &pServiceName;
  if ( !a2 )
    a2 = &pServiceName;
  return CompareStringOrdinal(a1, -1, a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180010f10  sub     rsp, 38h
0x180010f14  test    rcx, rcx
0x180010f17  jz      short loc_180010F4A
0x180010f19  test    rdx, rdx
0x180010f1c  jz      short loc_180010F53
0x180010f1e  mov     r9d, 0FFFFFFFFh; cchCount2
0x180010f24  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180010f2c  mov     r8, rdx; lpString2
0x180010f2f  mov     edx, r9d; cchCount1
0x180010f32  call    cs:__imp_CompareStringOrdinal
0x180010f39  nop     dword ptr [rax+rax+00h]
0x180010f3e  cmp     eax, 2
0x180010f41  setz    al
0x180010f44  add     rsp, 38h
0x180010f48  retn
0x180010f4a  lea     rcx, pServiceName
0x180010f51  jmp     short loc_180010F19
0x180010f53  lea     rdx, pServiceName
0x180010f5a  jmp     short loc_180010F1E
```
