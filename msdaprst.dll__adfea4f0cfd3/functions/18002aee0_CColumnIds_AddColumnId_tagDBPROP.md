# CColumnIds::AddColumnId(tagDBPROP *)

- ea: `0x18002aee0`
- end: `0x18002af79`
- name: `?AddColumnId@CColumnIds@@QEAAXPEAUtagDBPROP@@@Z`
- size: `153`
- prototype: `void __fastcall(CColumnIds *__hidden this, struct tagDBPROP *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002cc98`

## callees

- `0x18001b008`
- `0x18002aee0`
- `0x18002af80`
- `0x18002b288`
- `0x18002dca4`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002af19`
- `OLEAUT32!__imp_VariantCopy` at `0x18002af19`

## pseudocode

```c
void __fastcall CColumnIds::AddColumnId(CColumnIds *this, struct tagDBPROP *a2)
{
  struct tagPropColId *v3; // rbx
  HRESULT v4; // eax
  int v5; // ebx
  struct tagPropColId *v7; // [rsp+48h] [rbp+10h]

  v3 = CColumnIds::AddNode(this);
  v7 = v3;
  try
  {
    CopyDBIDs((struct tagDBID *)v3, &a2->colid);
    *((_DWORD *)v3 + 8) = a2->dwOptions;
    v4 = VariantCopy((VARIANTARG *)((char *)v3 + 40), &a2->vValue);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049E88[0] )
          bidTraceW(off_180049220, 3249152, off_180049E88[0], (unsigned int)v4, 3173);
      }
      ThrowHR(v5);
    }
  }
  catch ( ... )
  {
    CColumnIds::RemoveNode(this, v7);
  }
}

```

## disassembly

```asm
0x18002aee0  mov     [rsp+arg_10], rbx
0x18002aee5  mov     [rsp+arg_0], rcx
0x18002aeea  push    rdi
0x18002aeeb  sub     rsp, 30h
0x18002aeef  mov     rdi, rdx
0x18002aef2  call    ?AddNode@CColumnIds@@AEAAPEAUtagPropColId@@XZ; CColumnIds::AddNode(void)
0x18002aef7  mov     rbx, rax
0x18002aefa  mov     [rsp+38h+arg_8], rax
0x18002aeff  lea     rdx, [rdi+10h]; struct tagDBID *
0x18002af03  mov     rcx, rax; struct tagDBID *
0x18002af06  call    ?CopyDBIDs@@YAXPEAUtagDBID@@PEBU1@@Z; CopyDBIDs(tagDBID *,tagDBID const *)
0x18002af0b  mov     ecx, [rdi+4]
0x18002af0e  mov     [rbx+20h], ecx
0x18002af11  lea     rdx, [rdi+30h]; pvargSrc
0x18002af15  lea     rcx, [rbx+28h]; pvargDest
0x18002af19  call    cs:__imp_VariantCopy
0x18002af20  nop     dword ptr [rax+rax+00h]
0x18002af25  mov     ebx, eax
0x18002af27  test    eax, eax
0x18002af29  jns     short loc_18002AF6B
0x18002af2b  test    byte ptr cs:_bidGblFlags, 2
0x18002af32  jz      short loc_18002AF63
0x18002af34  mov     rcx, cs:off_180049E88; "<CColumnIds::AddColumnId|ADO|ERR>  HRES"...
0x18002af3b  test    rcx, rcx
0x18002af3e  jz      short loc_18002AF63
0x18002af40  mov     [rsp+38h+var_18], 0C65h
0x18002af48  mov     r9d, eax
0x18002af4b  mov     r8, cs:off_180049E88; "<CColumnIds::AddColumnId|ADO|ERR>  HRES"...
0x18002af52  mov     edx, 319400h
0x18002af57  mov     rcx, cs:off_180049220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002af5e  call    _bidTraceW
0x18002af63  mov     ecx, ebx; int
0x18002af65  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002af6b  jmp     short $+2
0x18002af6d  mov     rbx, [rsp+38h+arg_10]
0x18002af72  add     rsp, 30h
0x18002af76  pop     rdi
0x18002af77  retn
```
