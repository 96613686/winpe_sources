# CMediaServerFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x1800108c0`
- end: `0x1800109c6`
- name: `?GetUIObjectOf@CMediaServerFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(CMediaServerFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800108c0`
- `0x1800109cc`

## import_xrefs

- `api-ms-win-shell-dataobject-l1-1-0!SHCreateDataObject` at `0x180010911`
- `ext-ms-win-casting-shell-l1-1-0!GetContextMenuForMediaServerFolder` at `0x180010951`
- `ext-ms-win-casting-shell-l1-1-0!GetContextMenuForMediaServerFolder` at `0x180010951`
- `ext-ms-win-casting-shell-l1-1-0!GetExtractIconForMediaServerFolder` at `0x18001097d`
- `ext-ms-win-casting-shell-l1-1-0!GetExtractIconForMediaServerFolder` at `0x18001097d`

## pseudocode

```c
HRESULT __fastcall CMediaServerFolder::GetUIObjectOf(
        unsigned __int64 this,
        const struct _ITEMID_CHILD *a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        const struct _GUID *a5,
        unsigned int *a6,
        void **a7)
{
  __int64 v7; // rax
  HRESULT result; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx

  v7 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_0000010e_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_0000010e_0000_0000_c000_000000000046.Data1 )
    v7 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_0000010e_0000_0000_c000_000000000046.Data4;
  if ( !v7 )
    return SHCreateDataObject(*(LPCITEMIDLIST *)(this + 96), a3, a4, 0, a5, a7);
  v9 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_000214e4_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_000214e4_0000_0000_c000_000000000046.Data1 )
    v9 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_000214e4_0000_0000_c000_000000000046.Data4;
  if ( !v9 )
  {
    result = GetContextMenuForMediaServerFolder(a2, this & -(__int64)(this != 16), a3);
    goto LABEL_13;
  }
  v10 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1 )
    v10 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_000214fa_0000_0000_c000_000000000046.Data4;
  if ( !v10 )
  {
    result = GetExtractIconForMediaServerFolder(*a4, a7);
LABEL_13:
    if ( result == -2147467263 )
      return -2147467262;
    return result;
  }
  result = -2147467262;
  v11 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1 )
    v11 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4;
  if ( !v11 )
    return CMediaServerFolder::_GetQueryAssociations(0, a2, a5, a7);
  return result;
}

```

## disassembly

```asm
0x1800108c0  push    rbx
0x1800108c2  sub     rsp, 30h
0x1800108c6  mov     r11d, r8d
0x1800108c9  mov     r10, r9
0x1800108cc  mov     r8, [rsp+38h+arg_20]; struct _GUID *
0x1800108d1  mov     rbx, rdx
0x1800108d4  mov     rax, [r8]
0x1800108d7  sub     rax, qword ptr cs:_GUID_0000010e_0000_0000_c000_000000000046.Data1
0x1800108de  jnz     short loc_1800108EB
0x1800108e0  mov     rax, [r8+8]
0x1800108e4  sub     rax, qword ptr cs:_GUID_0000010e_0000_0000_c000_000000000046.Data4
0x1800108eb  test    rax, rax
0x1800108ee  jnz     short loc_180010918
0x1800108f0  mov     rax, [rsp+38h+arg_30]
0x1800108f5  xor     r9d, r9d
0x1800108f8  mov     rcx, [rcx+60h]
0x1800108fc  mov     edx, r11d
0x1800108ff  mov     [rsp+38h+arg_28], rax
0x180010904  mov     [rsp+38h+arg_20], r8
0x180010909  mov     r8, r10
0x18001090c  add     rsp, 30h
0x180010910  pop     rbx
0x180010911  jmp     cs:__imp_SHCreateDataObject
0x180010918  mov     rax, [r8]
0x18001091b  sub     rax, qword ptr cs:_GUID_000214e4_0000_0000_c000_000000000046.Data1
0x180010922  jnz     short loc_18001092F
0x180010924  mov     rax, [r8+8]
0x180010928  sub     rax, qword ptr cs:_GUID_000214e4_0000_0000_c000_000000000046.Data4
0x18001092f  test    rax, rax
0x180010932  jnz     short loc_180010959
0x180010934  lea     rax, [rcx-10h]
0x180010938  mov     r8d, r11d
0x18001093b  neg     rax
0x18001093e  mov     rax, [rsp+38h+arg_30]
0x180010943  sbb     rdx, rdx
0x180010946  mov     [rsp+38h+var_18], rax
0x18001094b  and     rdx, rcx
0x18001094e  mov     rcx, rbx
0x180010951  call    cs:__imp_GetContextMenuForMediaServerFolder
0x180010957  jmp     short loc_180010983
0x180010959  mov     rax, [r8]
0x18001095c  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data1
0x180010963  jnz     short loc_180010970
0x180010965  mov     rax, [r8+8]
0x180010969  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data4
0x180010970  test    rax, rax
0x180010973  jnz     short loc_180010995
0x180010975  mov     rdx, [rsp+38h+arg_30]
0x18001097a  mov     rcx, [r9]
0x18001097d  call    cs:__imp_GetExtractIconForMediaServerFolder
0x180010983  cmp     eax, 80004001h
0x180010988  jnz     short loc_1800109C0
0x18001098a  mov     eax, 80004002h
0x18001098f  add     rsp, 30h
0x180010993  pop     rbx
0x180010994  retn
0x180010995  mov     rcx, [r8]
0x180010998  mov     eax, 80004002h
0x18001099d  sub     rcx, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1
0x1800109a4  jnz     short loc_1800109B1
0x1800109a6  mov     rcx, [r8+8]
0x1800109aa  sub     rcx, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4; this
0x1800109b1  test    rcx, rcx
0x1800109b4  jnz     short loc_1800109C0
0x1800109b6  mov     r9, [rsp+38h+arg_30]; void **
0x1800109bb  call    ?_GetQueryAssociations@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CMediaServerFolder::_GetQueryAssociations(_ITEMID_CHILD const *,_GUID const &,void * *)
0x1800109c0  add     rsp, 30h
0x1800109c4  pop     rbx
0x1800109c5  retn
```
