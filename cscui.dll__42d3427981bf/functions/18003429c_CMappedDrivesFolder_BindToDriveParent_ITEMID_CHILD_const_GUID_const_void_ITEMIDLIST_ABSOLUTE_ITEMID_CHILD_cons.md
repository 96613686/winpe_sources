# CMappedDrivesFolder::_BindToDriveParent(_ITEMID_CHILD const *,_GUID const &,void * *,_ITEMIDLIST_ABSOLUTE * *,_ITEMID_CHILD const * *)

- ea: `0x18003429c`
- end: `0x1800343d3`
- name: `?_BindToDriveParent@CMappedDrivesFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAXPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAPEFBU2@@Z`
- size: `311`
- prototype: `int(CMappedDrivesFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **, struct _ITEMIDLIST_ABSOLUTE **, const struct _ITEMID_CHILD **)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ad88`
- `0x18000ae9c`
- `0x1800339e0`
- `0x180033bf0`
- `0x180033c90`
- `0x180034784`
- `0x180034e4c`

## callees

- `0x180002810`
- `0x18000735c`
- `0x18003429c`
- `0x180034cec`
- `0x18004c670`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x18003437e`
- `SHELL32!SHBindToParent` at `0x18003437e`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180034366`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180034366`
- `SHELL32!__imp_ILFree` at `0x18003438d`
- `SHELL32!__imp_ILFree` at `0x18003438d`

## pseudocode

```c
__int64 __fastcall CMappedDrivesFolder::_BindToDriveParent(
        CMappedDrivesFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4,
        LPITEMIDLIST *ppidl,
        LPCITEMIDLIST *ppidlLast)
{
  HRESULT LocalPathForItem; // ebx
  const WCHAR *ConstBuffer; // rax
  DWORD rgfInOut[4]; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v12[260]; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+238h] [rbp+138h]
  _WORD *v14; // [rsp+240h] [rbp+140h]
  _WORD *v15; // [rsp+248h] [rbp+148h]
  _WORD *v16; // [rsp+250h] [rbp+150h]
  __int64 v17; // [rsp+258h] [rbp+158h]
  __int64 v18; // [rsp+260h] [rbp+160h]

  v15 = v12;
  *a4 = 0;
  v16 = v12;
  *ppidl = 0;
  v14 = v12;
  *ppidlLast = 0;
  v12[0] = 0;
  v17 = 520;
  v18 = 520;
  v13 = 34078720;
  LocalPathForItem = CMappedDrivesFolder::_GetLocalPathForItem((CMappedDrivesFolder *)0x208, a2, (struct CPath *)v12);
  if ( LocalPathForItem >= 0 )
  {
    rgfInOut[0] = 0;
    ConstBuffer = CPath::_GetConstBuffer((CPath *)v12);
    LocalPathForItem = SHILCreateFromPath(ConstBuffer, ppidl, rgfInOut);
    if ( LocalPathForItem >= 0 )
    {
      LocalPathForItem = SHBindToParent(*ppidl, a3, a4, ppidlLast);
      if ( LocalPathForItem < 0 )
      {
        ILFree(*ppidl);
        *ppidl = 0;
        *ppidlLast = 0;
      }
    }
  }
  CPath::~CPath((CPath *)v12);
  return (unsigned int)LocalPathForItem;
}

```

## disassembly

```asm
0x18003429c  mov     [rsp-8+arg_0], rbx
0x1800342a1  push    rbp
0x1800342a2  push    rsi
0x1800342a3  push    rdi
0x1800342a4  push    r14
0x1800342a6  push    r15
0x1800342a8  lea     rbp, [rsp-180h]
0x1800342b0  sub     rsp, 280h
0x1800342b7  mov     rax, cs:__security_cookie
0x1800342be  xor     rax, rsp
0x1800342c1  mov     [rbp+1A0h+var_30], rax
0x1800342c8  mov     rdi, [rbp+1A0h+ppidl]
0x1800342cf  lea     rax, [rsp+2A0h+var_270]
0x1800342d4  mov     rsi, [rbp+1A0h+ppidlLast]
0x1800342db  mov     ecx, 208h; this
0x1800342e0  mov     [rbp+1A0h+var_58], rax
0x1800342e7  mov     r15, r8
0x1800342ea  mov     qword ptr [r9], 0
0x1800342f1  lea     rax, [rsp+2A0h+var_270]
0x1800342f6  mov     [rbp+1A0h+var_50], rax
0x1800342fd  lea     r8, [rsp+2A0h+var_270]; struct CPath *
0x180034302  lea     rax, [rsp+2A0h+var_270]
0x180034307  mov     qword ptr [rdi], 0
0x18003430e  mov     [rbp+1A0h+var_60], rax
0x180034315  mov     r14, r9
0x180034318  xor     eax, eax
0x18003431a  mov     qword ptr [rsi], 0
0x180034321  mov     [rsp+2A0h+var_270], ax
0x180034326  mov     [rbp+1A0h+var_48], rcx
0x18003432d  mov     [rbp+1A0h+var_40], rcx
0x180034334  mov     [rbp+1A0h+var_68], 2080000h
0x18003433e  call    ?_GetLocalPathForItem@CMappedDrivesFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAVCPath@@@Z; CMappedDrivesFolder::_GetLocalPathForItem(_ITEMID_CHILD const *,CPath *)
0x180034343  mov     ebx, eax
0x180034345  test    eax, eax
0x180034347  js      short loc_1800343A1
0x180034349  lea     rcx, [rsp+2A0h+var_270]; this
0x18003434e  mov     [rsp+2A0h+rgfInOut], 0
0x180034356  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18003435b  mov     rcx, rax; pszPath
0x18003435e  lea     r8, [rsp+2A0h+rgfInOut]; rgfInOut
0x180034363  mov     rdx, rdi; ppidl
0x180034366  call    cs:__imp_SHILCreateFromPath
0x18003436c  mov     ebx, eax
0x18003436e  test    eax, eax
0x180034370  js      short loc_1800343A1
0x180034372  mov     rcx, [rdi]; pidl
0x180034375  mov     r9, rsi; ppidlLast
0x180034378  mov     r8, r14; ppv
0x18003437b  mov     rdx, r15; riid
0x18003437e  call    cs:__imp_SHBindToParent
0x180034384  mov     ebx, eax
0x180034386  test    eax, eax
0x180034388  jns     short loc_1800343A1
0x18003438a  mov     rcx, [rdi]; pidl
0x18003438d  call    cs:__imp_ILFree
0x180034393  mov     qword ptr [rdi], 0
0x18003439a  mov     qword ptr [rsi], 0
0x1800343a1  lea     rcx, [rsp+2A0h+var_270]; this
0x1800343a6  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x1800343ab  mov     eax, ebx
0x1800343ad  mov     rcx, [rbp+1A0h+var_30]
0x1800343b4  xor     rcx, rsp; StackCookie
0x1800343b7  call    __security_check_cookie
0x1800343bc  mov     rbx, [rsp+2A0h+arg_0]
0x1800343c4  add     rsp, 280h
0x1800343cb  pop     r15
0x1800343cd  pop     r14
0x1800343cf  pop     rdi
0x1800343d0  pop     rsi
0x1800343d1  pop     rbp
0x1800343d2  retn
```
