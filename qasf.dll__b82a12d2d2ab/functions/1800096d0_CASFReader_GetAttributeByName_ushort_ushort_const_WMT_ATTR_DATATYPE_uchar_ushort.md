# CASFReader::GetAttributeByName(ushort *,ushort const *,WMT_ATTR_DATATYPE *,uchar *,ushort *)

- ea: `0x1800096d0`
- end: `0x180009712`
- name: `?GetAttributeByName@CASFReader@@EEAAJPEAGPEBGPEAW4WMT_ATTR_DATATYPE@@PEAE0@Z`
- size: `66`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16 *, const unsigned __int16 *, enum WMT_ATTR_DATATYPE *, unsigned __int8 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800096d0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetAttributeByName(
        CASFReader *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        enum WMT_ATTR_DATATYPE *a4,
        unsigned __int8 *a5,
        unsigned __int16 *a6)
{
  __int64 v6; // rcx

  v6 = *((_QWORD *)this + 29);
  if ( v6 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, const unsigned __int16 *, enum WMT_ATTR_DATATYPE *, unsigned __int8 *, unsigned __int16 *))(*(_QWORD *)v6 + 40LL))(
             v6,
             a2,
             a3,
             a4,
             a5,
             a6);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800096d0  sub     rsp, 48h
0x1800096d4  mov     rcx, [rcx+0E8h]
0x1800096db  mov     r10, rdx
0x1800096de  test    rcx, rcx
0x1800096e1  jnz     short loc_1800096EA
0x1800096e3  mov     eax, 80004005h
0x1800096e8  jmp     short loc_18000970D
0x1800096ea  mov     rdx, [rsp+48h+arg_28]
0x1800096ef  mov     rax, [rcx]
0x1800096f2  mov     [rsp+48h+var_20], rdx
0x1800096f7  mov     rdx, [rsp+48h+arg_20]
0x1800096fc  mov     [rsp+48h+var_28], rdx
0x180009701  mov     rdx, r10
0x180009704  mov     rax, [rax+28h]
0x180009708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000970d  add     rsp, 48h
0x180009711  retn
```
