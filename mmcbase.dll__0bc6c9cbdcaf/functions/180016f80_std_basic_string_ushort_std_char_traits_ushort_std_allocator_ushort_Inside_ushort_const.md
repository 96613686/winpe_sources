# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x180016f80`
- end: `0x180016fba`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800170ec`
- `0x1800172dc`

## callees

- `0x180016f80`

## pseudocode

```c
bool __fastcall std::wstring::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r8

  if ( !a2 )
    return 0;
  v2 = a1[3] < 8u ? a1 : (_QWORD *)*a1;
  if ( a2 < (unsigned __int64)v2 )
    return 0;
  if ( a1[3] < 8u )
    v3 = a1;
  else
    v3 = (_QWORD *)*a1;
  return (unsigned __int64)v3 + 2 * a1[2] > a2;
}

```

## disassembly

```asm
0x180016f80  test    rdx, rdx
0x180016f83  jz      short loc_180016FB7
0x180016f85  cmp     qword ptr [rcx+18h], 8
0x180016f8a  jb      short loc_180016F91
0x180016f8c  mov     rax, [rcx]
0x180016f8f  jmp     short loc_180016F94
0x180016f91  mov     rax, rcx
0x180016f94  cmp     rdx, rax
0x180016f97  jb      short loc_180016FB7
0x180016f99  cmp     qword ptr [rcx+18h], 8
0x180016f9e  jb      short loc_180016FA5
0x180016fa0  mov     r8, [rcx]
0x180016fa3  jmp     short loc_180016FA8
0x180016fa5  mov     r8, rcx
0x180016fa8  mov     rax, [rcx+10h]
0x180016fac  lea     rcx, [r8+rax*2]
0x180016fb0  cmp     rcx, rdx
0x180016fb3  setnbe  al
0x180016fb6  retn
0x180016fb7  xor     al, al
0x180016fb9  retn
```
