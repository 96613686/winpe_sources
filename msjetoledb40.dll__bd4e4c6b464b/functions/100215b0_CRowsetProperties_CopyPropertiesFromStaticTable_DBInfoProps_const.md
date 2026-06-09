# CRowsetProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)

- ea: `0x100215b0`
- end: `0x10021623`
- name: `?CopyPropertiesFromStaticTable@CRowsetProperties@@QAEJPBUDBInfoProps@@@Z`
- size: `115`
- prototype: `int __thiscall(CRowsetProperties *__hidden this, const struct DBInfoProps *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1000e140`
- `0x10013f50`
- `0x1001b4a0`
- `0x10025180`
- `0x10034e00`
- `0x10044ee0`

## callees

- `0x1001c6d0`
- `0x100215b0`

## pseudocode

```c
int __userpurge CRowsetProperties::CopyPropertiesFromStaticTable@<eax>(
        CRowsetProperties *this@<ecx>,
        int a2@<edi>,
        const struct DBInfoProps *a3)
{
  int result; // eax

  result = (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *, int, int, unsigned int, _DWORD, _DWORD, _DWORD, int))(**((_DWORD **)this + 2) + 4))(
             *((_DWORD *)this + 2),
             a3,
             79,
             74,
             DBPROPSET_ROWSET.Data1,
             *(_DWORD *)&DBPROPSET_ROWSET.Data2,
             *(_DWORD *)DBPROPSET_ROWSET.Data4,
             *(_DWORD *)&DBPROPSET_ROWSET.Data4[4],
             a2);
  if ( result >= 0 )
    return (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *, int, int, int, int, int, int))(**((_DWORD **)this + 3) + 4))(
             *((_DWORD *)this + 3),
             a3,
             155,
             13,
             -1499601888,
             298844197,
             -1073701700,
             -1039804593);
  return result;
}

```

## disassembly

```asm
0x100215b0  mov     edi, edi
0x100215b2  push    ebp
0x100215b3  mov     ebp, esp
0x100215b5  push    ecx
0x100215b6  movups  xmm0, xmmword ptr ds:_DBPROPSET_ROWSET.Data1
0x100215bd  push    esi
0x100215be  mov     eax, ecx
0x100215c0  push    edi
0x100215c1  mov     [ebp+var_4], eax
0x100215c4  sub     esp, 10h
0x100215c7  mov     edi, [eax+8]
0x100215ca  mov     eax, [edi]
0x100215cc  mov     esi, [eax+4]
0x100215cf  mov     eax, esp
0x100215d1  push    4Ah ; 'J'
0x100215d3  push    4Fh ; 'O'
0x100215d5  push    [ebp+arg_0]
0x100215d8  mov     ecx, esi
0x100215da  movups  xmmword ptr [eax], xmm0
0x100215dd  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100215e3  mov     ecx, edi
0x100215e5  call    esi
0x100215e7  test    eax, eax
0x100215e9  js      short loc_1002161B
0x100215eb  mov     edi, [ebp+var_4]
0x100215ee  sub     esp, 10h
0x100215f1  movups  xmm0, ds:xmmword_10005460
0x100215f8  mov     edi, [edi+0Ch]
0x100215fb  mov     eax, [edi]
0x100215fd  mov     esi, [eax+4]
0x10021600  mov     eax, esp
0x10021602  push    0Dh
0x10021604  push    9Bh
0x10021609  push    [ebp+arg_0]
0x1002160c  mov     ecx, esi
0x1002160e  movups  xmmword ptr [eax], xmm0
0x10021611  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10021617  mov     ecx, edi
0x10021619  call    esi
0x1002161b  pop     edi
0x1002161c  pop     esi
0x1002161d  mov     esp, ebp
0x1002161f  pop     ebp
0x10021620  retn    4
```
