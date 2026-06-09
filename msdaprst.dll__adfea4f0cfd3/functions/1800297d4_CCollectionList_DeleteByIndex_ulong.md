# CCollectionList::DeleteByIndex(ulong)

- ea: `0x1800297d4`
- end: `0x180029862`
- name: `?DeleteByIndex@CCollectionList@@QEAAJK@Z`
- size: `142`
- prototype: `__int64 __fastcall(CCollectionList *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180023f54`

## callees

- `0x18001b008`
- `0x180029700`
- `0x180029770`
- `0x1800297d4`

## pseudocode

```c
__int64 __fastcall CCollectionList::DeleteByIndex(CCollectionList *this)
{
  unsigned __int64 v3; // rsi
  unsigned int v4; // eax
  unsigned int v5; // ebx

  if ( !*((_DWORD *)this + 4) )
    return 2147942487LL;
  v3 = **((_QWORD **)this + 1);
  v4 = CCollectionArray::Delete(this, 0);
  v5 = v4;
  if ( v4 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180049E18[0] )
        bidTraceW(off_180049218, 996352, off_180049E18[0], v4, 973);
    }
  }
  else
  {
    return (unsigned int)CCollectionMap::DeleteByData((CCollectionList *)((char *)this + 24), v3);
  }
  return v5;
}

```

## disassembly

```asm
0x1800297d4  mov     [rsp+arg_0], rbx
0x1800297d9  mov     [rsp+arg_8], rsi
0x1800297de  push    rdi
0x1800297df  sub     rsp, 30h
0x1800297e3  cmp     dword ptr [rcx+10h], 0
0x1800297e7  mov     rdi, rcx
0x1800297ea  ja      short loc_1800297F3
0x1800297ec  mov     eax, 80070057h
0x1800297f1  jmp     short loc_180029851
0x1800297f3  mov     rax, [rcx+8]
0x1800297f7  xor     edx, edx; unsigned int
0x1800297f9  mov     rsi, [rax]
0x1800297fc  call    ?Delete@CCollectionArray@@QEAAJK@Z; CCollectionArray::Delete(ulong)
0x180029801  mov     ebx, eax
0x180029803  test    eax, eax
0x180029805  jz      short loc_180029841
0x180029807  test    byte ptr cs:_bidGblFlags, 2
0x18002980e  jz      short loc_18002984F
0x180029810  mov     rcx, cs:off_180049E18; "<CCollectionList::DeleteByIndex|ADO|ERR"...
0x180029817  test    rcx, rcx
0x18002981a  jz      short loc_18002984F
0x18002981c  mov     r8, cs:off_180049E18; "<CCollectionList::DeleteByIndex|ADO|ERR"...
0x180029823  mov     r9d, eax
0x180029826  mov     rcx, cs:off_180049218; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002982d  mov     edx, 0F3400h
0x180029832  mov     [rsp+38h+var_18], 3CDh
0x18002983a  call    _bidTraceW
0x18002983f  jmp     short loc_18002984F
0x180029841  lea     rcx, [rdi+18h]; this
0x180029845  mov     rdx, rsi; unsigned __int64
0x180029848  call    ?DeleteByData@CCollectionMap@@QEAAJ_K@Z; CCollectionMap::DeleteByData(unsigned __int64)
0x18002984d  mov     ebx, eax
0x18002984f  mov     eax, ebx
0x180029851  mov     rbx, [rsp+38h+arg_0]
0x180029856  mov     rsi, [rsp+38h+arg_8]
0x18002985b  add     rsp, 30h
0x18002985f  pop     rdi
0x180029860  retn
```
