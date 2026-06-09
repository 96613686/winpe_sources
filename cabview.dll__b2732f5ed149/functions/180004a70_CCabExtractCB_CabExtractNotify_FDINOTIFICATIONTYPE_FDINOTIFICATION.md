# CCabExtractCB::CabExtractNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x180004a70`
- end: `0x180004d78`
- name: `?CabExtractNotify@CCabExtractCB@@CA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180002620`
- `0x180003adc`
- `0x1800043d4`
- `0x180004a70`
- `0x1800050dc`
- `0x180005130`
- `0x1800051e0`
- `0x180008b8c`
- `0x180008c94`
- `0x180011e00`
- `0x180013010`

## import_xrefs

- `SHELL32!SHGetPathFromIDListA` at `0x180004be8`
- `SHELL32!SHGetPathFromIDListA` at `0x180004be8`
- `SHELL32!SHBrowseForFolderW` at `0x180004bc3`
- `SHELL32!SHBrowseForFolderW` at `0x180004bc3`
- `SHELL32!__imp_ILFree` at `0x180004bd6`
- `SHELL32!__imp_ILFree` at `0x180004bf3`
- `SHELL32!__imp_ILFree` at `0x180004bd6`
- `SHELL32!__imp_ILFree` at `0x180004bf3`
- `SHLWAPI!PathFindFileNameW` at `0x180004cf4`
- `SHLWAPI!PathFindFileNameW` at `0x180004cf4`
- `SHLWAPI!PathCombineW` at `0x180004d08`
- `SHLWAPI!PathCombineW` at `0x180004d08`
- `SHLWAPI!PathAddBackslashA` at `0x180004c01`
- `SHLWAPI!PathAddBackslashA` at `0x180004c01`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180004b2c`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180004b43`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180004b2c`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180004b43`
- `SHLWAPI!__imp_SHAnsiToUnicodeCP` at `0x180004c69`
- `SHLWAPI!__imp_SHAnsiToUnicodeCP` at `0x180004c69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004b15`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004b15`

## pseudocode

```c
__int64 __fastcall CCabExtractCB::CabExtractNotify(enum FDINOTIFICATIONTYPE a1, struct FDINOTIFICATION *a2)
{
  void *pv; // rbx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  HINSTANCE v8; // rcx
  char *psz2; // rax
  UINT v10; // edx
  LPITEMIDLIST v11; // rsi
  BOOL v12; // ebx
  char *psz1; // rdx
  __int64 v14; // rsi
  CMemFile *v15; // rax
  unsigned int cb; // r8d
  void **v17; // rdx
  CMemFile *v18; // rbx
  const WCHAR *FileNameW; // rax
  unsigned int v20; // edx
  _browseinfoW bi; // [rsp+40h] [rbp-C0h] BYREF
  CHAR pszPath[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR v24[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR pwszDst[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned __int16 v26[600]; // [rsp+8C0h] [rbp+7C0h] BYREF

  pv = a2->pv;
  if ( a1 == fdintCABINET_INFO )
  {
    *((_DWORD *)pv + 14) = 1;
    return 0;
  }
  v4 = a1 - 2;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( !v5 )
    {
      *((_DWORD *)pv + 18) = 1;
      return CMemFile::Close((CMemFile *)a2->hf) == 0;
    }
    v6 = v5 - 1;
    if ( !v6 )
    {
      if ( *((_DWORD *)pv + 14) )
      {
        *((_DWORD *)pv + 14) = 0;
      }
      else
      {
        v8 = g_hinst;
        *((_QWORD *)pv + 8) = a2;
        psz2 = a2->psz2;
        v10 = 18;
        if ( !*psz2 )
          v10 = 13;
        LoadStringW(v8, v10, Buffer, 80);
        SHAnsiToUnicode(a2->psz1, pwszDst, 260);
        SHAnsiToUnicode(a2->psz2, v24, 260);
        StringCchPrintfW(v26, 0x258u, Buffer, pwszDst, v24);
        bi.hwndOwner = (HWND)*((_QWORD *)pv + 4);
        bi.lpszTitle = v26;
        bi.lpfn = (BFFCALLBACK)CCabExtractCB::BrowseNotify;
        *(_QWORD *)&bi.ulFlags = 65;
        *(_QWORD *)&bi.iImage = 0;
        bi.pidlRoot = 0;
        bi.pszDisplayName = 0;
        bi.lParam = (LPARAM)pv;
        v11 = SHBrowseForFolderW(&bi);
        if ( bi.pidlRoot )
          ILFree((LPITEMIDLIST)bi.pidlRoot);
        if ( !v11 )
          return -1;
        v12 = SHGetPathFromIDListA(v11, pszPath);
        ILFree(v11);
        if ( !v12 )
          return -1;
        PathAddBackslashA(pszPath);
        StringCchCopyA(a2->psz3, 0x100u, pszPath);
      }
      return 1;
    }
    if ( v6 == 1 )
      a2->iFolder = *((_DWORD *)pv + 18) == 0;
    return 0;
  }
  psz1 = a2->psz1;
  if ( psz1 )
    SHAnsiToUnicodeCP(SLOBYTE(a2->attribs) < 0 ? 0xFDE9 : 0, psz1, pszPath, 260);
  else
    *(_WORD *)pszPath = 0;
  CanonicalizeFilePath((unsigned __int16 *)pszPath);
  v14 = (*((__int64 (__fastcall **)(unsigned __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))pv + 5))(
          (unsigned __int64)pszPath & -(__int64)(a2->psz1 != 0),
          (unsigned int)a2->cb,
          a2->date,
          a2->time,
          a2->attribs,
          *((_QWORD *)pv + 6));
  if ( v14 )
  {
    if ( *((_QWORD *)pv + 3) == 1 )
    {
      Buffer[0] = 0;
      v15 = (CMemFile *)operator new(0x18u);
      if ( !v15 )
      {
        v18 = 0;
        goto LABEL_30;
      }
      cb = a2->cb;
      v17 = (void **)v14;
    }
    else
    {
      FileNameW = PathFindFileNameW((LPCWSTR)pszPath);
      PathCombineW(Buffer, *((LPCWSTR *)pv + 3), FileNameW);
      v15 = (CMemFile *)operator new(0x18u);
      if ( !v15 )
        return 0;
      cb = 0;
      v17 = 0;
    }
    v18 = CMemFile::CMemFile(v15, v17, cb);
LABEL_30:
    if ( v18 )
    {
      if ( CMemFile::Create(v18, Buffer) )
        return (__int64)v18;
      CMemFile::`scalar deleting destructor'(v18, v20);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004a70  push    rbp
0x180004a72  push    rbx
0x180004a73  push    rsi
0x180004a74  push    rdi
0x180004a75  lea     rbp, [rsp-0C88h]
0x180004a7d  sub     rsp, 0D88h
0x180004a84  mov     rax, cs:__security_cookie
0x180004a8b  xor     rax, rsp
0x180004a8e  mov     [rbp+0CA0h+var_30], rax
0x180004a95  mov     rbx, [rdx+20h]
0x180004a99  mov     rdi, rdx
0x180004a9c  test    ecx, ecx
0x180004a9e  jz      loc_180004D54
0x180004aa4  sub     ecx, 2
0x180004aa7  jz      loc_180004C47
0x180004aad  sub     ecx, 1
0x180004ab0  jz      loc_180004C27
0x180004ab6  sub     ecx, 1
0x180004ab9  jz      short loc_180004AD5
0x180004abb  cmp     ecx, 1
0x180004abe  jnz     loc_180004D5B
0x180004ac4  xor     eax, eax
0x180004ac6  cmp     [rbx+48h], eax
0x180004ac9  setz    al
0x180004acc  mov     [rdx+3Ah], ax
0x180004ad0  jmp     loc_180004D5B
0x180004ad5  cmp     dword ptr [rbx+38h], 0
0x180004ad9  jz      short loc_180004AEC
0x180004adb  mov     dword ptr [rbx+38h], 0
0x180004ae2  mov     eax, 1
0x180004ae7  jmp     loc_180004D5D
0x180004aec  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180004af3  lea     r8, [rbp+0CA0h+Buffer]; lpBuffer
0x180004afa  mov     [rbx+40h], rdi
0x180004afe  mov     r9d, 50h ; 'P'; cchBufferMax
0x180004b04  mov     rax, [rdx+10h]
0x180004b08  lea     edx, [r9-3Eh]
0x180004b0c  cmp     byte ptr [rax], 0
0x180004b0f  jnz     short loc_180004B15
0x180004b11  lea     edx, [r9-43h]; uID
0x180004b15  call    cs:__imp_LoadStringW
0x180004b1b  mov     rcx, [rdi+8]; pszSrc
0x180004b1f  lea     rdx, [rbp+0CA0h+pwszDst]; pwszDst
0x180004b26  mov     r8d, 104h; cwchBuf
0x180004b2c  call    cs:__imp_SHAnsiToUnicode
0x180004b32  mov     rcx, [rdi+10h]; pszSrc
0x180004b36  lea     rdx, [rbp+0CA0h+var_900]; pwszDst
0x180004b3d  mov     r8d, 104h; cwchBuf
0x180004b43  call    cs:__imp_SHAnsiToUnicode
0x180004b49  lea     rax, [rbp+0CA0h+var_900]
0x180004b50  mov     edx, 258h; unsigned __int64
0x180004b55  lea     r9, [rbp+0CA0h+pwszDst]
0x180004b5c  mov     [rsp+0DA0h+var_D80], rax
0x180004b61  lea     r8, [rbp+0CA0h+Buffer]; unsigned __int16 *
0x180004b68  lea     rcx, [rbp+0CA0h+var_4E0]; unsigned __int16 *
0x180004b6f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004b74  mov     rax, [rbx+20h]
0x180004b78  lea     rcx, [rsp+0DA0h+bi]; lpbi
0x180004b7d  mov     [rsp+0DA0h+bi.hwndOwner], rax
0x180004b82  lea     rax, [rbp+0CA0h+var_4E0]
0x180004b89  mov     [rsp+0DA0h+bi.lpszTitle], rax
0x180004b8e  lea     rax, ?BrowseNotify@CCabExtractCB@@CAHPEAUHWND__@@I_J1@Z; CCabExtractCB::BrowseNotify(HWND__ *,uint,__int64,__int64)
0x180004b95  mov     [rsp+0DA0h+bi.lpfn], rax
0x180004b9a  mov     qword ptr [rsp+0DA0h+bi.ulFlags], 41h ; 'A'
0x180004ba3  mov     qword ptr [rsp+0DA0h+bi.iImage], 0
0x180004bac  mov     [rsp+0DA0h+bi.pidlRoot], 0
0x180004bb5  mov     [rsp+0DA0h+bi.pszDisplayName], 0
0x180004bbe  mov     [rsp+0DA0h+bi.lParam], rbx
0x180004bc3  call    cs:__imp_SHBrowseForFolderW
0x180004bc9  mov     rcx, [rsp+0DA0h+bi.pidlRoot]; pidl
0x180004bce  mov     rsi, rax
0x180004bd1  test    rcx, rcx
0x180004bd4  jz      short loc_180004BDC
0x180004bd6  call    cs:__imp_ILFree
0x180004bdc  test    rsi, rsi
0x180004bdf  jz      short loc_180004C1E
0x180004be1  lea     rdx, [rbp+0CA0h+pszPath]; pszPath
0x180004be5  mov     rcx, rsi; pidl
0x180004be8  call    cs:__imp_SHGetPathFromIDListA
0x180004bee  mov     rcx, rsi; pidl
0x180004bf1  mov     ebx, eax
0x180004bf3  call    cs:__imp_ILFree
0x180004bf9  test    ebx, ebx
0x180004bfb  jz      short loc_180004C1E
0x180004bfd  lea     rcx, [rbp+0CA0h+pszPath]; pszPath
0x180004c01  call    cs:__imp_PathAddBackslashA
0x180004c07  mov     rcx, [rdi+18h]; char *
0x180004c0b  lea     r8, [rbp+0CA0h+pszPath]; char *
0x180004c0f  mov     edx, 100h; unsigned __int64
0x180004c14  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180004c19  jmp     loc_180004AE2
0x180004c1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004c22  jmp     loc_180004D5D
0x180004c27  mov     dword ptr [rbx+48h], 1
0x180004c2e  mov     rcx, [rdx+28h]; this
0x180004c32  call    ?Close@CMemFile@@QEAAPEAXXZ; CMemFile::Close(void)
0x180004c37  xor     ecx, ecx
0x180004c39  test    rax, rax
0x180004c3c  setz    cl
0x180004c3f  mov     rax, rcx
0x180004c42  jmp     loc_180004D5D
0x180004c47  mov     rdx, [rdx+8]
0x180004c4b  test    rdx, rdx
0x180004c4e  jz      short loc_180004C71
0x180004c50  mov     al, [rdi+34h]
0x180004c53  lea     r8, [rbp+0CA0h+pszPath]
0x180004c57  and     al, 80h
0x180004c59  mov     r9d, 104h
0x180004c5f  neg     al
0x180004c61  sbb     ecx, ecx
0x180004c63  and     ecx, 0FDE9h
0x180004c69  call    cs:__imp_SHAnsiToUnicodeCP
0x180004c6f  jmp     short loc_180004C77
0x180004c71  xor     eax, eax
0x180004c73  mov     word ptr [rbp+0CA0h+pszPath], ax
0x180004c77  lea     rcx, [rbp+0CA0h+pszPath]; unsigned __int16 *
0x180004c7b  call    ?CanonicalizeFilePath@@YAXPEAG@Z; CanonicalizeFilePath(ushort *)
0x180004c80  mov     rdx, [rbx+30h]
0x180004c84  mov     rax, [rdi+8]
0x180004c88  movzx   r10d, word ptr [rdi+34h]
0x180004c8d  neg     rax
0x180004c90  movzx   r9d, word ptr [rdi+32h]
0x180004c95  lea     rax, [rbp+0CA0h+pszPath]
0x180004c99  movzx   r8d, word ptr [rdi+30h]
0x180004c9e  sbb     rcx, rcx
0x180004ca1  mov     [rsp+0DA0h+var_D78], rdx
0x180004ca6  and     rcx, rax
0x180004ca9  mov     rax, [rbx+28h]
0x180004cad  mov     edx, [rdi]
0x180004caf  mov     dword ptr [rsp+0DA0h+var_D80], r10d
0x180004cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb9  mov     rsi, rax
0x180004cbc  test    rax, rax
0x180004cbf  jz      loc_180004D5B
0x180004cc5  cmp     qword ptr [rbx+18h], 1
0x180004cca  jnz     short loc_180004CF0
0x180004ccc  xor     ecx, ecx
0x180004cce  mov     [rbp+0CA0h+Buffer], cx
0x180004cd5  mov     ecx, 18h; unsigned __int64
0x180004cda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004cdf  test    rax, rax
0x180004ce2  jz      short loc_180004CEC
0x180004ce4  mov     r8d, [rdi]
0x180004ce7  mov     rdx, rsi
0x180004cea  jmp     short loc_180004D22
0x180004cec  xor     ebx, ebx
0x180004cee  jmp     short loc_180004D2D
0x180004cf0  lea     rcx, [rbp+0CA0h+pszPath]; pszPath
0x180004cf4  call    cs:__imp_PathFindFileNameW
0x180004cfa  mov     rdx, [rbx+18h]; pszDir
0x180004cfe  lea     rcx, [rbp+0CA0h+Buffer]; pszDest
0x180004d05  mov     r8, rax; pszFile
0x180004d08  call    cs:__imp_PathCombineW
0x180004d0e  mov     ecx, 18h; unsigned __int64
0x180004d13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d18  test    rax, rax
0x180004d1b  jz      short loc_180004D5B
0x180004d1d  xor     r8d, r8d; unsigned int
0x180004d20  xor     edx, edx; void **
0x180004d22  mov     rcx, rax; this
0x180004d25  call    ??0CMemFile@@QEAA@PEAPEAXK@Z; CMemFile::CMemFile(void * *,ulong)
0x180004d2a  mov     rbx, rax
0x180004d2d  test    rbx, rbx
0x180004d30  jz      short loc_180004D5B
0x180004d32  lea     rdx, [rbp+0CA0h+Buffer]; unsigned __int16 *
0x180004d39  mov     rcx, rbx; this
0x180004d3c  call    ?Create@CMemFile@@QEAAHPEBG@Z; CMemFile::Create(ushort const *)
0x180004d41  test    eax, eax
0x180004d43  jz      short loc_180004D4A
0x180004d45  mov     rax, rbx
0x180004d48  jmp     short loc_180004D5D
0x180004d4a  mov     rcx, rbx; this
0x180004d4d  call    ??_GCMemFile@@QEAAPEAXI@Z; CMemFile::`scalar deleting destructor'(uint)
0x180004d52  jmp     short loc_180004D5B
0x180004d54  mov     dword ptr [rbx+38h], 1
0x180004d5b  xor     eax, eax
0x180004d5d  mov     rcx, [rbp+0CA0h+var_30]
0x180004d64  xor     rcx, rsp; StackCookie
0x180004d67  call    __security_check_cookie
0x180004d6c  add     rsp, 0D88h
0x180004d73  pop     rdi
0x180004d74  pop     rsi
0x180004d75  pop     rbx
0x180004d76  pop     rbp
0x180004d77  retn
```
