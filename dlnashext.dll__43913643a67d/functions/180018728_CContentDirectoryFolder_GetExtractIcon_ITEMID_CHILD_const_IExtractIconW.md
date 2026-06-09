# CContentDirectoryFolder::_GetExtractIcon(_ITEMID_CHILD const *,IExtractIconW * *)

- ea: `0x180018728`
- end: `0x1800187af`
- name: `?_GetExtractIcon@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAUIExtractIconW@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(CContentDirectoryFolder *__hidden this, const struct _ITEMID_CHILD *, struct IExtractIconW **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000fc50`

## callees

- `0x1800082b4`
- `0x18000ab48`
- `0x180018728`

## import_xrefs

- `ext-ms-win-casting-shell-l1-1-0!GetExtractIconForContentDirectoryFolder` at `0x180018787`
- `ext-ms-win-casting-shell-l1-1-0!GetExtractIconForContentDirectoryFolder` at `0x180018787`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDirectoryFolder::_GetExtractIcon(
        CContentDirectoryFolder *this,
        const struct _ITEMID_CHILD *a2,
        struct IExtractIconW **a3)
{
  int String; // ebx
  unsigned __int16 *v8[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v9; // [rsp+78h] [rbp+20h] BYREF

  v8[0] = 0;
  String = CContentDirectoryFolder::_GetString(this, a2, &PKEY_ItemClass, v8);
  if ( String >= 0 )
  {
    v9 = 0;
    CContentDirectoryFolder::_GetString(this, a2, &PKEY_FileExtension, &v9);
    String = GetExtractIconForContentDirectoryFolder(v8[0], v9, a3);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v9);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v8);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180018728  push    rbx
0x18001872a  push    rbp
0x18001872b  push    rsi
0x18001872c  push    rdi
0x18001872d  sub     rsp, 38h
0x180018731  mov     rbp, r8
0x180018734  mov     rdi, rdx
0x180018737  mov     rsi, rcx
0x18001873a  mov     [rsp+58h+var_38], 0
0x180018743  lea     r9, [rsp+58h+var_38]; unsigned __int16 **
0x180018748  lea     r8, PKEY_ItemClass; struct _tagpropertykey *
0x18001874f  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x180018754  mov     ebx, eax
0x180018756  test    eax, eax
0x180018758  js      short loc_18001879A
0x18001875a  mov     [rsp+58h+arg_18], 0
0x180018763  lea     r9, [rsp+58h+arg_18]; unsigned __int16 **
0x180018768  lea     r8, PKEY_FileExtension; struct _tagpropertykey *
0x18001876f  mov     rdx, rdi; struct _ITEMID_CHILD *
0x180018772  mov     rcx, rsi; this
0x180018775  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x18001877a  mov     r8, rbp
0x18001877d  mov     rdx, [rsp+58h+arg_18]
0x180018782  mov     rcx, [rsp+58h+var_38]
0x180018787  call    cs:__imp_GetExtractIconForContentDirectoryFolder
0x18001878d  mov     ebx, eax
0x18001878f  lea     rcx, [rsp+58h+arg_18]
0x180018794  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180018799  nop
0x18001879a  lea     rcx, [rsp+58h+var_38]
0x18001879f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800187a4  mov     eax, ebx
0x1800187a6  add     rsp, 38h
0x1800187aa  pop     rdi
0x1800187ab  pop     rsi
0x1800187ac  pop     rbp
0x1800187ad  pop     rbx
0x1800187ae  retn
```
