# CTrusteeProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)

- ea: `0x10023e00`
- end: `0x10023e7a`
- name: `?CopyPropertiesFromStaticTable@CTrusteeProperties@@QAEJPBUDBInfoProps@@@Z`
- size: `122`
- prototype: `int __thiscall(CTrusteeProperties *__hidden this, const struct DBInfoProps *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x100407e0`
- `0x10040c30`
- `0x10040ed0`

## callees

- `0x1001c6d0`
- `0x10023e00`

## pseudocode

```c
int __userpurge CTrusteeProperties::CopyPropertiesFromStaticTable@<eax>(
        CTrusteeProperties *this@<ecx>,
        int a2@<edi>,
        const struct DBInfoProps *a3)
{
  int result; // eax

  result = (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *const *, int, int, unsigned int, _DWORD, _DWORD, _DWORD, int))(**((_DWORD **)this + 2) + 4))(
             *((_DWORD *)this + 2),
             &rgDBInfoProps,
             217,
             3,
             DBPROPSET_TRUSTEE.Data1,
             *(_DWORD *)&DBPROPSET_TRUSTEE.Data2,
             *(_DWORD *)DBPROPSET_TRUSTEE.Data4,
             *(_DWORD *)&DBPROPSET_TRUSTEE.Data4[4],
             a2);
  if ( result >= 0 )
    return (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *const *, int, int, int, int, int, int))(**((_DWORD **)this + 3) + 4))(
             *((_DWORD *)this + 3),
             &rgDBInfoProps,
             220,
             1,
             -907963770,
             298949450,
             -1073739105,
             -524107185);
  return result;
}

```

## disassembly

```asm
0x10023e00  mov     edi, edi
0x10023e02  push    ebp
0x10023e03  mov     ebp, esp
0x10023e05  push    ecx
0x10023e06  movups  xmm0, xmmword ptr ds:_DBPROPSET_TRUSTEE.Data1
0x10023e0d  push    esi
0x10023e0e  mov     eax, ecx
0x10023e10  push    edi
0x10023e11  mov     [ebp+var_4], eax
0x10023e14  sub     esp, 10h
0x10023e17  mov     edi, [eax+8]
0x10023e1a  mov     eax, [edi]
0x10023e1c  mov     esi, [eax+4]
0x10023e1f  mov     eax, esp
0x10023e21  push    3
0x10023e23  push    0D9h
0x10023e28  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; DBInfoProps const * const rgDBInfoProps
0x10023e2d  mov     ecx, esi
0x10023e2f  movups  xmmword ptr [eax], xmm0
0x10023e32  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023e38  mov     ecx, edi
0x10023e3a  call    esi
0x10023e3c  test    eax, eax
0x10023e3e  js      short loc_10023E72
0x10023e40  mov     edi, [ebp+var_4]
0x10023e43  sub     esp, 10h
0x10023e46  movups  xmm0, ds:xmmword_10005430
0x10023e4d  mov     edi, [edi+0Ch]
0x10023e50  mov     eax, [edi]
0x10023e52  mov     esi, [eax+4]
0x10023e55  mov     eax, esp
0x10023e57  push    1
0x10023e59  push    0DCh
0x10023e5e  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; DBInfoProps const * const rgDBInfoProps
0x10023e63  mov     ecx, esi
0x10023e65  movups  xmmword ptr [eax], xmm0
0x10023e68  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023e6e  mov     ecx, edi
0x10023e70  call    esi
0x10023e72  pop     edi
0x10023e73  pop     esi
0x10023e74  mov     esp, ebp
0x10023e76  pop     ebp
0x10023e77  retn    4
```
