# CCscItemFolder::_CreateFsIDs(uint,_ITEMID_CHILD const * const *,_ITEMID_CHILD * * *)

- ea: `0x180039088`
- end: `0x18003924b`
- name: `?_CreateFsIDs@CCscItemFolder@@AEAAJIPEBQEFBU_ITEMID_CHILD@@PEAPEAPEAU2@@Z`
- size: `451`
- prototype: `__int64 __fastcall(CCscItemFolder *__hidden this, unsigned int, const struct _ITEMID_CHILD *const *, struct _ITEMID_CHILD ***)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180038d00`
- `0x180038ec4`
- `0x18003a114`

## callees

- `0x180002810`
- `0x18000735c`
- `0x180032e80`
- `0x180033154`
- `0x180039088`
- `0x180039bcc`
- `0x18003a3e0`
- `0x18004c670`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x1800391bb`
- `SHELL32!__imp_ILFindLastID` at `0x1800391bb`
- `SHELL32!__imp_ILCloneFirst` at `0x1800391c4`
- `SHELL32!__imp_ILCloneFirst` at `0x1800391c4`
- `SHELL32!__imp_SHILCreateFromPath` at `0x1800391aa`
- `SHELL32!__imp_SHILCreateFromPath` at `0x1800391aa`
- `SHELL32!__imp_ILFree` at `0x1800391e6`
- `SHELL32!__imp_ILFree` at `0x1800391e6`

## pseudocode

```c
__int64 __fastcall CCscItemFolder::_CreateFsIDs(
        CCscItemFolder *this,
        unsigned int a2,
        const struct _ITEMID_CHILD *const *a3,
        struct _ITEMID_CHILD ***a4)
{
  HRESULT ItemFullPath; // ebx
  __int64 v9; // r14
  unsigned __int16 *v10; // rax
  __int64 v11; // r8
  const struct _ITEMID_CHILD *v12; // r9
  const WCHAR *ConstBuffer; // rax
  const ITEMIDLIST *ID; // rax
  DWORD rgfInOut; // [rsp+20h] [rbp-E0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+28h] [rbp-D8h] BYREF
  _WORD v18[260]; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+238h] [rbp+138h]
  _WORD *v20; // [rsp+240h] [rbp+140h]
  _WORD *v21; // [rsp+248h] [rbp+148h]
  _WORD *v22; // [rsp+250h] [rbp+150h]
  __int64 v23; // [rsp+258h] [rbp+158h]
  __int64 v24; // [rsp+260h] [rbp+160h]

  *a4 = 0;
  ItemFullPath = -2147467259;
  if ( a2 )
  {
    ItemFullPath = CscUtil_HeapAllocArray<_ITEMID_CHILD *>(a2, a4);
    if ( ItemFullPath >= 0 )
    {
      v9 = 0;
      if ( a2 )
      {
        while ( ItemFullPath >= 0 )
        {
          v10 = CItemIDFactory<tagCSCITEMDATA,86514056>::_IsValid((unsigned __int16 *)a3[v9]);
          if ( (-(__int64)(((unsigned __int64)(v10 + 7) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64)) != 0)
              & (unsigned __int64)v12) != 0 )
          {
            v23 = v11;
            v21 = v18;
            v24 = v11;
            v22 = v18;
            v19 = 34078720;
            v20 = v18;
            v18[0] = 0;
            ItemFullPath = CCscItemFolder::_GetItemFullPath(this, v12, (struct CPath *)v18);
            if ( ItemFullPath >= 0 )
            {
              ppidl = 0;
              rgfInOut = 0;
              ConstBuffer = CPath::_GetConstBuffer((CPath *)v18);
              ItemFullPath = SHILCreateFromPath(ConstBuffer, &ppidl, &rgfInOut);
              if ( ItemFullPath >= 0 )
              {
                ID = ILFindLastID(ppidl);
                (*a4)[v9] = (struct _ITEMID_CHILD *)ILCloneFirst(ID);
                if ( !(*a4)[v9] )
                  ItemFullPath = -2147024882;
                ILFree(ppidl);
              }
            }
            CPath::~CPath((CPath *)v18);
          }
          else
          {
            ItemFullPath = -2147467259;
          }
          v9 = (unsigned int)(v9 + 1);
          if ( (unsigned int)v9 >= a2 )
          {
            if ( ItemFullPath >= 0 )
              return (unsigned int)ItemFullPath;
            break;
          }
        }
        CscDestroyItemIDArray(a2, *a4);
        *a4 = 0;
      }
    }
  }
  return (unsigned int)ItemFullPath;
}

```

## disassembly

```asm
0x180039088  push    rbp
0x18003908a  push    rbx
0x18003908b  push    rsi
0x18003908c  push    rdi
0x18003908d  push    r12
0x18003908f  push    r13
0x180039091  push    r14
0x180039093  push    r15
0x180039095  lea     rbp, [rsp-188h]
0x18003909d  sub     rsp, 288h
0x1800390a4  mov     rax, cs:__security_cookie
0x1800390ab  xor     rax, rsp
0x1800390ae  mov     [rbp+1C0h+var_50], rax
0x1800390b5  mov     edi, edx
0x1800390b7  mov     rsi, r9
0x1800390ba  mov     qword ptr [r9], 0
0x1800390c1  mov     r12, r8
0x1800390c4  mov     r13, rcx
0x1800390c7  mov     ebx, 80004005h
0x1800390cc  test    edx, edx
0x1800390ce  jz      loc_180039226
0x1800390d4  mov     ecx, edi
0x1800390d6  mov     rdx, r9
0x1800390d9  call    ??$CscUtil_HeapAllocArray@PEAU_ITEMID_CHILD@@@@YAJ_KPEAPEAPEAU_ITEMID_CHILD@@@Z; CscUtil_HeapAllocArray<_ITEMID_CHILD *>(unsigned __int64,_ITEMID_CHILD * * *)
0x1800390de  mov     ebx, eax
0x1800390e0  test    eax, eax
0x1800390e2  js      loc_180039226
0x1800390e8  xor     r14d, r14d
0x1800390eb  test    edi, edi
0x1800390ed  jz      loc_180039226
0x1800390f3  mov     r8d, 208h
0x1800390f9  test    ebx, ebx
0x1800390fb  js      loc_180039215
0x180039101  mov     r9, [r12+r14*8]
0x180039105  mov     rcx, r9
0x180039108  call    ?_IsValid@?$CItemIDFactory@UtagCSCITEMDATA@@$0FCIBJII@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<tagCSCITEMDATA,86514056>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x18003910d  lea     rcx, [rax+0Eh]
0x180039111  neg     rax
0x180039114  sbb     rdx, rdx
0x180039117  and     rdx, rcx
0x18003911a  neg     rdx
0x18003911d  sbb     rax, rax
0x180039120  test    r9, rax
0x180039123  jz      loc_1800391FE
0x180039129  lea     rax, [rsp+2C0h+var_290]
0x18003912e  mov     [rbp+1C0h+var_68], r8
0x180039135  mov     [rbp+1C0h+var_78], rax
0x18003913c  mov     rdx, r9; struct _ITEMID_CHILD *
0x18003913f  lea     rax, [rsp+2C0h+var_290]
0x180039144  mov     [rbp+1C0h+var_60], r8
0x18003914b  mov     [rbp+1C0h+var_70], rax
0x180039152  lea     r8, [rsp+2C0h+var_290]; struct CPath *
0x180039157  lea     rax, [rsp+2C0h+var_290]
0x18003915c  mov     [rbp+1C0h+var_88], 2080000h
0x180039166  mov     [rbp+1C0h+var_80], rax
0x18003916d  mov     rcx, r13; this
0x180039170  xor     eax, eax
0x180039172  mov     [rsp+2C0h+var_290], ax
0x180039177  call    ?_GetItemFullPath@CCscItemFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAVCPath@@@Z; CCscItemFolder::_GetItemFullPath(_ITEMID_CHILD const *,CPath *)
0x18003917c  mov     ebx, eax
0x18003917e  test    eax, eax
0x180039180  js      short loc_1800391EC
0x180039182  lea     rcx, [rsp+2C0h+var_290]; this
0x180039187  mov     [rsp+2C0h+ppidl], 0
0x180039190  mov     [rsp+2C0h+rgfInOut], 0
0x180039198  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18003919d  mov     rcx, rax; pszPath
0x1800391a0  lea     r8, [rsp+2C0h+rgfInOut]; rgfInOut
0x1800391a5  lea     rdx, [rsp+2C0h+ppidl]; ppidl
0x1800391aa  call    cs:__imp_SHILCreateFromPath
0x1800391b0  mov     ebx, eax
0x1800391b2  test    eax, eax
0x1800391b4  js      short loc_1800391EC
0x1800391b6  mov     rcx, [rsp+2C0h+ppidl]; pidl
0x1800391bb  call    cs:__imp_ILFindLastID
0x1800391c1  mov     rcx, rax; pidl
0x1800391c4  call    cs:__imp_ILCloneFirst
0x1800391ca  mov     rcx, [rsi]
0x1800391cd  mov     [rcx+r14*8], rax
0x1800391d1  mov     ecx, 8007000Eh
0x1800391d6  mov     rax, [rsi]
0x1800391d9  cmp     qword ptr [rax+r14*8], 0
0x1800391de  cmovz   ebx, ecx
0x1800391e1  mov     rcx, [rsp+2C0h+ppidl]; pidl
0x1800391e6  call    cs:__imp_ILFree
0x1800391ec  lea     rcx, [rsp+2C0h+var_290]; this
0x1800391f1  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x1800391f6  mov     r8d, 208h
0x1800391fc  jmp     short loc_180039203
0x1800391fe  mov     ebx, 80004005h
0x180039203  inc     r14d
0x180039206  mov     eax, ebx
0x180039208  cmp     r14d, edi
0x18003920b  jb      loc_1800390F9
0x180039211  test    eax, eax
0x180039213  jns     short loc_180039226
0x180039215  mov     rdx, [rsi]; struct _ITEMID_CHILD **
0x180039218  mov     ecx, edi; unsigned int
0x18003921a  call    ?CscDestroyItemIDArray@@YAXIPEAPEAU_ITEMID_CHILD@@@Z; CscDestroyItemIDArray(uint,_ITEMID_CHILD * *)
0x18003921f  mov     qword ptr [rsi], 0
0x180039226  mov     eax, ebx
0x180039228  mov     rcx, [rbp+1C0h+var_50]
0x18003922f  xor     rcx, rsp; StackCookie
0x180039232  call    __security_check_cookie
0x180039237  add     rsp, 288h
0x18003923e  pop     r15
0x180039240  pop     r14
0x180039242  pop     r13
0x180039244  pop     r12
0x180039246  pop     rdi
0x180039247  pop     rsi
0x180039248  pop     rbx
0x180039249  pop     rbp
0x18003924a  retn
```
