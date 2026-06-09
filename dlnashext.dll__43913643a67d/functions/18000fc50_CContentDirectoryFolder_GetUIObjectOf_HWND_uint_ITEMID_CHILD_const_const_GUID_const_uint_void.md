# CContentDirectoryFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x18000fc50`
- end: `0x18000fda1`
- name: `?GetUIObjectOf@CContentDirectoryFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `337`
- prototype: `int(CContentDirectoryFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000fc50`
- `0x18000fda8`
- `0x180018728`
- `0x180019b84`

## import_xrefs

- `api-ms-win-shell-dataobject-l1-1-0!SHCreateDataObject` at `0x18000fca3`
- `api-ms-win-shell-dataobject-l1-1-0!SHCreateDataObject` at `0x18000fca3`
- `ext-ms-win-casting-shell-l1-1-0!GetContextMenuForContentDirectoryFolder` at `0x18000fce5`
- `ext-ms-win-casting-shell-l1-1-0!GetContextMenuForContentDirectoryFolder` at `0x18000fce5`

## pseudocode

```c
__int64 __fastcall CContentDirectoryFolder::GetUIObjectOf(
        unsigned __int64 this,
        HWND a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        const struct _GUID *riid,
        unsigned int *a6,
        void **ppv)
{
  __int64 v7; // rax
  int QueryAssociations; // eax
  __int64 v9; // rax
  int ContextMenuForContentDirectoryFolder; // eax
  __int64 v11; // rax
  int v12; // ebx
  __int64 v13; // rax

  *ppv = 0;
  v7 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_0000010e_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_0000010e_0000_0000_c000_000000000046.Data1 )
    v7 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_0000010e_0000_0000_c000_000000000046.Data4;
  if ( !v7 )
  {
    QueryAssociations = SHCreateDataObject(*(LPCITEMIDLIST *)(this + 72), a3, a4, 0, riid, ppv);
LABEL_19:
    v12 = QueryAssociations;
    goto LABEL_20;
  }
  v9 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_000214e4_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_000214e4_0000_0000_c000_000000000046.Data1 )
    v9 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_000214e4_0000_0000_c000_000000000046.Data4;
  if ( !v9 )
  {
    ContextMenuForContentDirectoryFolder = GetContextMenuForContentDirectoryFolder(
                                             a2,
                                             this & ((unsigned __int128)-(__int128)(this - 16) >> 64),
                                             a3,
                                             a4,
                                             ppv);
    goto LABEL_13;
  }
  v11 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1 )
    v11 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_000214fa_0000_0000_c000_000000000046.Data4;
  if ( !v11 )
  {
    ContextMenuForContentDirectoryFolder = CContentDirectoryFolder::_GetExtractIcon(
                                             (CContentDirectoryFolder *)(this - 16),
                                             (const struct _ITEMID_CHILD *)*a4,
                                             (struct IExtractIconW **)ppv);
LABEL_13:
    v12 = ContextMenuForContentDirectoryFolder;
    if ( ContextMenuForContentDirectoryFolder == -2147467263 )
      v12 = -2147467262;
    goto LABEL_20;
  }
  v12 = -2147467262;
  v13 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1 )
    v13 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4;
  if ( !v13 )
  {
    QueryAssociations = CContentDirectoryFolder::_GetQueryAssociations(
                          (CContentDirectoryFolder *)(this - 16),
                          (const struct _ITEMID_CHILD *)*a4,
                          riid,
                          ppv);
    goto LABEL_19;
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v12 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000fc50  push    rbx
0x18000fc52  sub     rsp, 30h
0x18000fc56  mov     r10, r9
0x18000fc59  mov     r11d, r8d
0x18000fc5c  mov     r9, [rsp+38h+arg_30]; void **
0x18000fc61  mov     rbx, rdx
0x18000fc64  mov     r8, [rsp+38h+arg_20]; struct _GUID *
0x18000fc69  mov     qword ptr [r9], 0
0x18000fc70  mov     rax, [r8]
0x18000fc73  sub     rax, qword ptr cs:_GUID_0000010e_0000_0000_c000_000000000046.Data1
0x18000fc7a  jnz     short loc_18000FC87
0x18000fc7c  mov     rax, [r8+8]
0x18000fc80  sub     rax, qword ptr cs:_GUID_0000010e_0000_0000_c000_000000000046.Data4
0x18000fc87  test    rax, rax
0x18000fc8a  jnz     short loc_18000FCAE
0x18000fc8c  mov     rcx, [rcx+48h]; pidlFolder
0x18000fc90  mov     edx, r11d; cidl
0x18000fc93  mov     [rsp+38h+ppv], r9; ppv
0x18000fc98  xor     r9d, r9d; pdtInner
0x18000fc9b  mov     [rsp+38h+riid], r8; riid
0x18000fca0  mov     r8, r10; apidl
0x18000fca3  call    cs:__imp_SHCreateDataObject
0x18000fca9  jmp     loc_18000FD53
0x18000fcae  mov     rax, [r8]
0x18000fcb1  sub     rax, qword ptr cs:_GUID_000214e4_0000_0000_c000_000000000046.Data1
0x18000fcb8  jnz     short loc_18000FCC5
0x18000fcba  mov     rax, [r8+8]
0x18000fcbe  sub     rax, qword ptr cs:_GUID_000214e4_0000_0000_c000_000000000046.Data4
0x18000fcc5  test    rax, rax
0x18000fcc8  jnz     short loc_18000FCED
0x18000fcca  lea     rax, [rcx-10h]
0x18000fcce  mov     [rsp+38h+riid], r9
0x18000fcd3  neg     rax
0x18000fcd6  mov     r9, r10
0x18000fcd9  mov     r8d, r11d
0x18000fcdc  sbb     rdx, rdx
0x18000fcdf  and     rdx, rcx
0x18000fce2  mov     rcx, rbx
0x18000fce5  call    cs:__imp_GetContextMenuForContentDirectoryFolder
0x18000fceb  jmp     short loc_18000FD18
0x18000fced  mov     rax, [r8]
0x18000fcf0  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data1
0x18000fcf7  jnz     short loc_18000FD04
0x18000fcf9  mov     rax, [r8+8]
0x18000fcfd  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data4
0x18000fd04  test    rax, rax
0x18000fd07  jnz     short loc_18000FD26
0x18000fd09  mov     rdx, [r10]; struct _ITEMID_CHILD *
0x18000fd0c  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18000fd10  mov     r8, r9; struct IExtractIconW **
0x18000fd13  call    ?_GetExtractIcon@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAUIExtractIconW@@@Z; CContentDirectoryFolder::_GetExtractIcon(_ITEMID_CHILD const *,IExtractIconW * *)
0x18000fd18  mov     ebx, eax
0x18000fd1a  cmp     eax, 80004001h
0x18000fd1f  jnz     short loc_18000FD55
0x18000fd21  lea     ebx, [rax+1]
0x18000fd24  jmp     short loc_18000FD55
0x18000fd26  mov     rax, [r8]
0x18000fd29  mov     ebx, 80004002h
0x18000fd2e  sub     rax, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1
0x18000fd35  jnz     short loc_18000FD42
0x18000fd37  mov     rax, [r8+8]
0x18000fd3b  sub     rax, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4
0x18000fd42  test    rax, rax
0x18000fd45  jnz     short loc_18000FD55
0x18000fd47  mov     rdx, [r10]; struct _ITEMID_CHILD *
0x18000fd4a  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18000fd4e  call    ?_GetQueryAssociations@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CContentDirectoryFolder::_GetQueryAssociations(_ITEMID_CHILD const *,_GUID const &,void * *)
0x18000fd53  mov     ebx, eax
0x18000fd55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd5c  lea     rax, WPP_GLOBAL_Control
0x18000fd63  cmp     rcx, rax
0x18000fd66  jz      short loc_18000FD99
0x18000fd68  test    byte ptr [rcx+1Ch], 2
0x18000fd6c  jz      short loc_18000FD99
0x18000fd6e  movzx   eax, byte ptr [rcx+19h]
0x18000fd72  mov     edx, ebx
0x18000fd74  sar     edx, 1Fh
0x18000fd77  and     edx, 0FFFFFFFDh
0x18000fd7a  add     edx, 5
0x18000fd7d  cmp     eax, edx
0x18000fd7f  jb      short loc_18000FD99
0x18000fd81  mov     rcx, [rcx+10h]
0x18000fd85  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x18000fd8c  mov     edx, 1Ch
0x18000fd91  mov     r9d, ebx
0x18000fd94  call    WPP_SF_d
0x18000fd99  mov     eax, ebx
0x18000fd9b  add     rsp, 30h
0x18000fd9f  pop     rbx
0x18000fda0  retn
```
