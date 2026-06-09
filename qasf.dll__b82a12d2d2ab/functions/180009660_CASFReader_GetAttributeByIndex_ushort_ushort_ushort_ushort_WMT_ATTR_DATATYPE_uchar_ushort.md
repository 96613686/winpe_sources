# CASFReader::GetAttributeByIndex(ushort,ushort *,ushort *,ushort *,WMT_ATTR_DATATYPE *,uchar *,ushort *)

- ea: `0x180009660`
- end: `0x1800096c4`
- name: `?GetAttributeByIndex@CASFReader@@EEAAJGPEAG00PEAW4WMT_ATTR_DATATYPE@@PEAE0@Z`
- size: `100`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, enum WMT_ATTR_DATATYPE *, unsigned __int8 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009660`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetAttributeByIndex(
        CASFReader *this,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        enum WMT_ATTR_DATATYPE *a6,
        unsigned __int8 *a7,
        unsigned __int16 *a8)
{
  __int64 v8; // rcx

  v8 = *((_QWORD *)this + 29);
  if ( v8 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, enum WMT_ATTR_DATATYPE *, unsigned __int8 *, unsigned __int16 *))(*(_QWORD *)v8 + 32LL))(
             v8,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180009660  sub     rsp, 58h
0x180009664  mov     rcx, [rcx+0E8h]
0x18000966b  movzx   r10d, dx
0x18000966f  test    rcx, rcx
0x180009672  jnz     short loc_18000967B
0x180009674  mov     eax, 80004005h
0x180009679  jmp     short loc_1800096BF
0x18000967b  mov     rdx, [rsp+58h+arg_38]
0x180009683  mov     rax, [rcx]
0x180009686  mov     [rsp+58h+var_20], rdx
0x18000968b  mov     rdx, [rsp+58h+arg_30]
0x180009693  mov     [rsp+58h+var_28], rdx
0x180009698  mov     rdx, [rsp+58h+arg_28]
0x1800096a0  mov     rax, [rax+20h]
0x1800096a4  mov     [rsp+58h+var_30], rdx
0x1800096a9  mov     rdx, [rsp+58h+arg_20]
0x1800096b1  mov     [rsp+58h+var_38], rdx
0x1800096b6  movzx   edx, r10w
0x1800096ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096bf  add     rsp, 58h
0x1800096c3  retn
```
