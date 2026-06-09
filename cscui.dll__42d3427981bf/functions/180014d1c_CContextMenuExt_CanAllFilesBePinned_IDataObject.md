# CContextMenuExt::_CanAllFilesBePinned(IDataObject *)

- ea: `0x180014d1c`
- end: `0x180014f41`
- name: `?_CanAllFilesBePinned@CContextMenuExt@@AEAAJPEAUIDataObject@@@Z`
- size: `549`
- prototype: `int(CContextMenuExt *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800154ec`

## callees

- `0x180003d60`
- `0x180014d1c`
- `0x18003ae4c`
- `0x18003ae7c`
- `0x18003d4c0`
- `0x18003f0c8`
- `0x18003f81c`
- `0x18003f848`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathAddBackslashW` at `0x180014e12`
- `SHLWAPI!PathAddBackslashW` at `0x180014e12`
- `USER32!LoadCursorW` at `0x180014d78`
- `USER32!LoadCursorW` at `0x180014d78`
- `USER32!SetCursor` at `0x180014d81`
- `USER32!SetCursor` at `0x180014f00`
- `USER32!SetCursor` at `0x180014d81`
- `USER32!SetCursor` at `0x180014f00`

## pseudocode

```c
__int64 __fastcall CContextMenuExt::_CanAllFilesBePinned(CContextMenuExt *this, struct IDataObject *a2)
{
  CNoPinList *v2; // r15
  unsigned int v4; // esi
  int v5; // edi
  HCURSOR CursorW; // rax
  HCURSOR v7; // r12
  __int64 v8; // rbx
  __int64 v9; // r9
  const unsigned __int16 *v10; // rax
  int v11; // r9d
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // r14
  __int64 v14; // rax
  WCHAR *i; // rcx
  int v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v18[2]; // [rsp+28h] [rbp-D8h] BYREF
  char v19; // [rsp+38h] [rbp-C8h]
  HCURSOR v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h]
  _QWORD *v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+60h] [rbp-A0h]
  _BYTE v25[2]; // [rsp+6Eh] [rbp-92h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = (CContextMenuExt *)((char *)this + 64);
  v4 = 0;
  if ( (unsigned int)CNoPinList::IsAnyPinDisallowed((CContextMenuExt *)((char *)this + 64)) == 1 )
  {
    v5 = 0;
  }
  else
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v18[0] = 0;
    v20 = SetCursor(CursorW);
    v18[1] = 0;
    v7 = v20;
    v19 = 1;
    v17[0] = 0;
    v5 = SyncContext_BuildFileListFromShellItemIDs(a2, (struct CscFilenameList *)v18, v17);
    if ( v5 >= 0 )
    {
      v24 = 0;
      v23 = v18;
      v5 = 0;
      *(_QWORD *)v17 = 0;
      while ( CscFilenameList::ShareIter::Next(
                (CscFilenameList::ShareIter *)&v23,
                (struct CscFilenameList::HSHARE *)v17) )
      {
        v8 = *(_QWORD *)v17;
        if ( (int)StringCchCopyW(pszPath, 0x104u, *(const unsigned __int16 **)(*(_QWORD *)v17 + 16LL)) < 0
          || !PathAddBackslashW(pszPath) )
        {
          v5 = -2147024690;
          break;
        }
        v5 = 0;
        v9 = -1;
        do
          ++v9;
        while ( pszPath[v9] );
        v21 = v8;
        v22 = 0;
        v10 = CscFilenameList::FileIter::Next((CscFilenameList::FileIter *)&v21);
        if ( v10 )
        {
          v12 = 260LL - v11;
          v13 = &pszPath[v11];
          do
          {
            if ( (int)StringCchCopyW(v13, v12, v10) >= 0 )
            {
              v5 = 0;
              v14 = -1;
              do
                ++v14;
              while ( pszPath[v14] );
              for ( i = (WCHAR *)&v25[2 * v14]; i > pszPath && (*i == 92 || *i == 42); --i )
                *i = 0;
              if ( CNoPinList::IsPinAllowed(v2, pszPath) == 1 )
                v4 = 1;
            }
            else
            {
              v5 = -2147024690;
            }
            v10 = CscFilenameList::FileIter::Next((CscFilenameList::FileIter *)&v21);
          }
          while ( v10 );
          v7 = v20;
          if ( v5 )
            break;
        }
      }
    }
    SetCursor(v7);
    CscFilenameList::~CscFilenameList((CscFilenameList *)v18);
  }
  if ( v5 < 0 )
    return (unsigned int)v5;
  return v4;
}

```

## disassembly

```asm
0x180014d1c  mov     [rsp-8+arg_10], rbx
0x180014d21  push    rbp
0x180014d22  push    rsi
0x180014d23  push    rdi
0x180014d24  push    r12
0x180014d26  push    r13
0x180014d28  push    r14
0x180014d2a  push    r15
0x180014d2c  lea     rbp, [rsp-190h]
0x180014d34  sub     rsp, 290h
0x180014d3b  mov     rax, cs:__security_cookie
0x180014d42  xor     rax, rsp
0x180014d45  mov     [rbp+1C0h+var_40], rax
0x180014d4c  lea     r15, [rcx+40h]
0x180014d50  xor     r13d, r13d
0x180014d53  mov     rcx, r15; this
0x180014d56  mov     rbx, rdx
0x180014d59  mov     esi, r13d
0x180014d5c  call    ?IsAnyPinDisallowed@CNoPinList@@QEAAJXZ; CNoPinList::IsAnyPinDisallowed(void)
0x180014d61  lea     edi, [r13+1]
0x180014d65  cmp     eax, edi
0x180014d67  jnz     short loc_180014D71
0x180014d69  mov     edi, r13d
0x180014d6c  jmp     loc_180014F10
0x180014d71  mov     edx, 7F02h; lpCursorName
0x180014d76  xor     ecx, ecx; hInstance
0x180014d78  call    cs:__imp_LoadCursorW
0x180014d7e  mov     rcx, rax; hCursor
0x180014d81  call    cs:__imp_SetCursor
0x180014d87  lea     r8, [rsp+2C0h+var_2A0]; int *
0x180014d8c  mov     [rsp+2C0h+var_298], r13
0x180014d91  lea     rdx, [rsp+2C0h+var_298]; this
0x180014d96  mov     [rsp+2C0h+var_280], rax
0x180014d9b  mov     rcx, rbx; struct IDataObject *
0x180014d9e  mov     [rsp+2C0h+var_290], r13
0x180014da3  mov     r12, rax
0x180014da6  mov     [rsp+2C0h+var_288], dil
0x180014dab  mov     [rsp+2C0h+var_2A0], r13d
0x180014db0  call    ?SyncContext_BuildFileListFromShellItemIDs@@YAJPEAUIDataObject@@PEAVCscFilenameList@@PEAH@Z; SyncContext_BuildFileListFromShellItemIDs(IDataObject *,CscFilenameList *,int *)
0x180014db5  mov     edi, eax
0x180014db7  test    eax, eax
0x180014db9  js      loc_180014EFD
0x180014dbf  lea     rax, [rsp+2C0h+var_298]
0x180014dc4  mov     [rsp+2C0h+var_260], r13d
0x180014dc9  mov     [rsp+2C0h+var_268], rax
0x180014dce  mov     edi, r13d
0x180014dd1  mov     qword ptr [rsp+2C0h+var_2A0], r13
0x180014dd6  lea     rdx, [rsp+2C0h+var_2A0]; struct CscFilenameList::HSHARE *
0x180014ddb  lea     rcx, [rsp+2C0h+var_268]; this
0x180014de0  call    ?Next@ShareIter@CscFilenameList@@QEAA_NPEAVHSHARE@2@@Z; CscFilenameList::ShareIter::Next(CscFilenameList::HSHARE *)
0x180014de5  test    al, al
0x180014de7  jz      loc_180014EFD
0x180014ded  mov     rbx, qword ptr [rsp+2C0h+var_2A0]
0x180014df2  lea     rcx, [rsp+2C0h+pszPath]; unsigned __int16 *
0x180014df7  mov     edx, 104h; unsigned __int64
0x180014dfc  mov     r8, [rbx+10h]; unsigned __int16 *
0x180014e00  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014e05  test    eax, eax
0x180014e07  js      loc_180014EF8
0x180014e0d  lea     rcx, [rsp+2C0h+pszPath]; pszPath
0x180014e12  call    cs:__imp_PathAddBackslashW
0x180014e18  test    rax, rax
0x180014e1b  jz      loc_180014EF8
0x180014e21  mov     edi, r13d
0x180014e24  lea     rax, [rsp+2C0h+pszPath]
0x180014e29  or      r9, 0FFFFFFFFFFFFFFFFh
0x180014e2d  inc     r9
0x180014e30  cmp     [rax+r9*2], r13w
0x180014e35  jnz     short loc_180014E2D
0x180014e37  lea     rcx, [rsp+2C0h+var_278]; this
0x180014e3c  mov     [rsp+2C0h+var_278], rbx
0x180014e41  mov     [rsp+2C0h+var_270], r13d
0x180014e46  call    ?Next@FileIter@CscFilenameList@@QEAAPEBGXZ; CscFilenameList::FileIter::Next(void)
0x180014e4b  test    rax, rax
0x180014e4e  jz      short loc_180014DD6
0x180014e50  movsxd  rcx, r9d
0x180014e53  lea     r14, [rsp+2C0h+pszPath]
0x180014e58  mov     ebx, 104h
0x180014e5d  mov     r12d, 1
0x180014e63  sub     rbx, rcx
0x180014e66  lea     r14, [r14+rcx*2]
0x180014e6a  mov     r8, rax; unsigned __int16 *
0x180014e6d  mov     rdx, rbx; unsigned __int64
0x180014e70  mov     rcx, r14; unsigned __int16 *
0x180014e73  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014e78  test    eax, eax
0x180014e7a  jns     short loc_180014E83
0x180014e7c  mov     edi, 800700CEh
0x180014e81  jmp     short loc_180014EDA
0x180014e83  mov     edi, r13d
0x180014e86  lea     rcx, [rsp+2C0h+pszPath]
0x180014e8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014e8f  inc     rax
0x180014e92  cmp     [rcx+rax*2], r13w
0x180014e97  jnz     short loc_180014E8F
0x180014e99  lea     rcx, [rsp+rax*2+2C0h+var_252]
0x180014e9e  jmp     short loc_180014EBC
0x180014ea0  mov     eax, 5Ch ; '\'
0x180014ea5  cmp     ax, [rcx]
0x180014ea8  jz      short loc_180014EB4
0x180014eaa  mov     eax, 2Ah ; '*'
0x180014eaf  cmp     ax, [rcx]
0x180014eb2  jnz     short loc_180014EC6
0x180014eb4  mov     [rcx], r13w
0x180014eb8  sub     rcx, 2
0x180014ebc  lea     rax, [rsp+2C0h+pszPath]
0x180014ec1  cmp     rcx, rax
0x180014ec4  ja      short loc_180014EA0
0x180014ec6  lea     rdx, [rsp+2C0h+pszPath]; unsigned __int16 *
0x180014ecb  mov     rcx, r15; this
0x180014ece  call    ?IsPinAllowed@CNoPinList@@QEAAJPEBG@Z; CNoPinList::IsPinAllowed(ushort const *)
0x180014ed3  cmp     eax, r12d
0x180014ed6  cmovz   esi, r12d
0x180014eda  lea     rcx, [rsp+2C0h+var_278]; this
0x180014edf  call    ?Next@FileIter@CscFilenameList@@QEAAPEBGXZ; CscFilenameList::FileIter::Next(void)
0x180014ee4  test    rax, rax
0x180014ee7  jnz     short loc_180014E6A
0x180014ee9  mov     r12, [rsp+2C0h+var_280]
0x180014eee  test    edi, edi
0x180014ef0  jz      loc_180014DD6
0x180014ef6  jmp     short loc_180014EFD
0x180014ef8  mov     edi, 800700CEh
0x180014efd  mov     rcx, r12; hCursor
0x180014f00  call    cs:__imp_SetCursor
0x180014f06  lea     rcx, [rsp+2C0h+var_298]; this
0x180014f0b  call    ??1CscFilenameList@@QEAA@XZ; CscFilenameList::~CscFilenameList(void)
0x180014f10  test    edi, edi
0x180014f12  cmovs   esi, edi
0x180014f15  mov     eax, esi
0x180014f17  mov     rcx, [rbp+1C0h+var_40]
0x180014f1e  xor     rcx, rsp; StackCookie
0x180014f21  call    __security_check_cookie
0x180014f26  mov     rbx, [rsp+2C0h+arg_10]
0x180014f2e  add     rsp, 290h
0x180014f35  pop     r15
0x180014f37  pop     r14
0x180014f39  pop     r13
0x180014f3b  pop     r12
0x180014f3d  pop     rdi
0x180014f3e  pop     rsi
0x180014f3f  pop     rbp
0x180014f40  retn
```
