# CColumnIds::GetNextValue(ulong *,tagDBID *,tagVARIANT *)

- ea: `0x18002bb50`
- end: `0x18002bbf4`
- name: `?GetNextValue@CColumnIds@@QEAAHPEAKPEAUtagDBID@@PEAUtagVARIANT@@@Z`
- size: `164`
- prototype: `int(CColumnIds *__hidden this, unsigned int *, struct tagDBID *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002cc28`

## callees

- `0x18001b008`
- `0x18002b288`
- `0x18002bb50`
- `0x18002dca4`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002bb82`
- `OLEAUT32!__imp_VariantCopy` at `0x18002bb82`

## pseudocode

```c
_BOOL8 __fastcall CColumnIds::GetNextValue(
        CColumnIds *this,
        unsigned int *a2,
        struct tagDBID *a3,
        struct tagVARIANT *a4)
{
  HRESULT v6; // eax
  int v7; // ebx
  __int64 v8; // rcx

  *a2 = *(_DWORD *)(*((_QWORD *)this + 1) + 32LL);
  CopyDBIDs(a3, *((const struct tagDBID **)this + 1));
  v6 = VariantCopy(a4, (const VARIANTARG *)(*((_QWORD *)this + 1) + 40LL));
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180049EE0[0] )
        bidTraceW(off_180049220, 3139584, off_180049EE0[0], (unsigned int)v6, 3066);
    }
    ThrowHR(v7);
  }
  v8 = *(_QWORD *)(*((_QWORD *)this + 1) + 72LL);
  *((_QWORD *)this + 1) = v8;
  return v8 != 0;
}

```

## disassembly

```asm
0x18002bb50  mov     [rsp+arg_0], rbx
0x18002bb55  push    rdi
0x18002bb56  sub     rsp, 30h
0x18002bb5a  mov     rax, [rcx+8]
0x18002bb5e  mov     rdi, rcx
0x18002bb61  mov     rbx, r9
0x18002bb64  mov     r10d, [rax+20h]
0x18002bb68  mov     [rdx], r10d
0x18002bb6b  mov     rdx, [rcx+8]; struct tagDBID *
0x18002bb6f  mov     rcx, r8; struct tagDBID *
0x18002bb72  call    ?CopyDBIDs@@YAXPEAUtagDBID@@PEBU1@@Z; CopyDBIDs(tagDBID *,tagDBID const *)
0x18002bb77  mov     rdx, [rdi+8]
0x18002bb7b  mov     rcx, rbx; pvargDest
0x18002bb7e  add     rdx, 28h ; '('; pvargSrc
0x18002bb82  call    cs:__imp_VariantCopy
0x18002bb89  nop     dword ptr [rax+rax+00h]
0x18002bb8e  mov     ebx, eax
0x18002bb90  test    eax, eax
0x18002bb92  jns     short loc_18002BBD4
0x18002bb94  test    byte ptr cs:_bidGblFlags, 2
0x18002bb9b  jz      short loc_18002BBCC
0x18002bb9d  mov     rcx, cs:off_180049EE0; "<CColumnIds::GetNextValue|ADO|ERR>  HRE"...
0x18002bba4  test    rcx, rcx
0x18002bba7  jz      short loc_18002BBCC
0x18002bba9  mov     r8, cs:off_180049EE0; "<CColumnIds::GetNextValue|ADO|ERR>  HRE"...
0x18002bbb0  mov     r9d, eax
0x18002bbb3  mov     rcx, cs:off_180049220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002bbba  mov     edx, 2FE800h
0x18002bbbf  mov     [rsp+38h+var_18], 0BFAh
0x18002bbc7  call    _bidTraceW
0x18002bbcc  mov     ecx, ebx; int
0x18002bbce  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002bbd4  mov     rax, [rdi+8]
0x18002bbd8  mov     rbx, [rsp+38h+arg_0]
0x18002bbdd  mov     rcx, [rax+48h]
0x18002bbe1  xor     eax, eax
0x18002bbe3  test    rcx, rcx
0x18002bbe6  mov     [rdi+8], rcx
0x18002bbea  setnz   al
0x18002bbed  add     rsp, 30h
0x18002bbf1  pop     rdi
0x18002bbf2  retn
```
