# CTableProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)

- ea: `0x10022870`
- end: `0x100228e6`
- name: `?CopyPropertiesFromStaticTable@CTableProperties@@QAEJPBUDBInfoProps@@@Z`
- size: `118`
- prototype: `int __thiscall(CTableProperties *__hidden this, const struct DBInfoProps *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10044ee0`
- `0x10047070`

## callees

- `0x1001c6d0`
- `0x10022870`

## pseudocode

```c
int __userpurge CTableProperties::CopyPropertiesFromStaticTable@<eax>(
        CTableProperties *this@<ecx>,
        int a2@<edi>,
        const struct DBInfoProps *a3)
{
  int result; // eax

  result = (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *, int, int, unsigned int, _DWORD, _DWORD, _DWORD, int))(**((_DWORD **)this + 2) + 4))(
             *((_DWORD *)this + 2),
             a3,
             154,
             1,
             DBPROPSET_TABLE.Data1,
             *(_DWORD *)&DBPROPSET_TABLE.Data2,
             *(_DWORD *)DBPROPSET_TABLE.Data4,
             *(_DWORD *)&DBPROPSET_TABLE.Data4[4],
             a2);
  if ( result >= 0 )
    return (*(int (__thiscall **)(_DWORD, const struct DBInfoProps *, int, int, int, int, int, int))(**((_DWORD **)this + 3) + 4))(
             *((_DWORD *)this + 3),
             a3,
             200,
             9,
             -431176196,
             298885106,
             -1073693282,
             -524107185);
  return result;
}

```

## disassembly

```asm
0x10022870  mov     edi, edi
0x10022872  push    ebp
0x10022873  mov     ebp, esp
0x10022875  push    ecx
0x10022876  movups  xmm0, xmmword ptr ds:_DBPROPSET_TABLE.Data1
0x1002287d  push    esi
0x1002287e  mov     eax, ecx
0x10022880  push    edi
0x10022881  mov     [ebp+var_4], eax
0x10022884  sub     esp, 10h
0x10022887  mov     edi, [eax+8]
0x1002288a  mov     eax, [edi]
0x1002288c  mov     esi, [eax+4]
0x1002288f  mov     eax, esp
0x10022891  push    1
0x10022893  push    9Ah
0x10022898  push    [ebp+arg_0]
0x1002289b  mov     ecx, esi
0x1002289d  movups  xmmword ptr [eax], xmm0
0x100228a0  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100228a6  mov     ecx, edi
0x100228a8  call    esi
0x100228aa  test    eax, eax
0x100228ac  js      short loc_100228DE
0x100228ae  mov     edi, [ebp+var_4]
0x100228b1  sub     esp, 10h
0x100228b4  movups  xmm0, ds:xmmword_10005440
0x100228bb  mov     edi, [edi+0Ch]
0x100228be  mov     eax, [edi]
0x100228c0  mov     esi, [eax+4]
0x100228c3  mov     eax, esp
0x100228c5  push    9
0x100228c7  push    0C8h
0x100228cc  push    [ebp+arg_0]
0x100228cf  mov     ecx, esi
0x100228d1  movups  xmmword ptr [eax], xmm0
0x100228d4  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100228da  mov     ecx, edi
0x100228dc  call    esi
0x100228de  pop     edi
0x100228df  pop     esi
0x100228e0  mov     esp, ebp
0x100228e2  pop     ebp
0x100228e3  retn    4
```
