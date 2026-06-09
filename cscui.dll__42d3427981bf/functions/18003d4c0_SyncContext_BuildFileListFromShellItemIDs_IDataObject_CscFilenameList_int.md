# SyncContext_BuildFileListFromShellItemIDs(IDataObject *,CscFilenameList *,int *)

- ea: `0x18003d4c0`
- end: `0x18003d78e`
- name: `?SyncContext_BuildFileListFromShellItemIDs@@YAJPEAUIDataObject@@PEAVCscFilenameList@@PEAH@Z`
- size: `718`
- prototype: `__int64 __fastcall(struct IDataObject *, struct CscFilenameList *this, int *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180014d1c`
- `0x18002b290`
- `0x18003e260`

## callees

- `0x180004b80`
- `0x180007048`
- `0x180007dd4`
- `0x18000c1dc`
- `0x18001101c`
- `0x18001105c`
- `0x180011860`
- `0x18003d4c0`
- `0x18003dd40`
- `0x18003f20c`
- `0x18003f5e0`
- `0x18003f64c`
- `0x18003f894`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x18003d66c`
- `SHLWAPI!PathIsUNCW` at `0x18003d66c`
- `SHLWAPI!PathFindExtensionW` at `0x18003d6e0`
- `SHLWAPI!PathFindExtensionW` at `0x18003d6e0`
- `SHLWAPI!PathIsContentTypeW` at `0x18003d6d2`
- `SHLWAPI!PathIsContentTypeW` at `0x18003d6d2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003d6f4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003d6f4`

## pseudocode

```c
__int64 __fastcall SyncContext_BuildFileListFromShellItemIDs(
        struct IDataObject *a1,
        struct CscFilenameList *this,
        int *a3)
{
  int ItemPath; // ebx
  unsigned int *v6; // r9
  unsigned int i; // r15d
  unsigned int v8; // ecx
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // rax
  CscFilenameList *v11; // rcx
  bool v12; // r9
  unsigned __int16 *v13; // rdi
  bool v14; // r12
  bool v15; // r9
  unsigned int v16; // edi
  bool v17; // zf
  LPWSTR ExtensionW; // rax
  DWORD FileAttributesW; // eax
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v23; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int128 v27; // [rsp+68h] [rbp-98h]
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( a3 )
    *a3 = 0;
  v26 = 0;
  v27 = 0;
  v25 = 0;
  ItemPath = CIDArray::Initialize((CIDArray *)&v25, a1);
  if ( ItemPath < 0 )
  {
LABEL_40:
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_f72d3c378080343ef5b9ab31099f269e_Traceguids,
        (unsigned int)ItemPath);
    }
    goto LABEL_43;
  }
  for ( i = 0; ; ++i )
  {
    v8 = (_QWORD)v27 ? *(_DWORD *)v27 : 0;
    if ( i >= v8 )
      break;
    if ( ItemPath < 0 )
      goto LABEL_40;
    v21 = 1610678272;
    ItemPath = CIDArray::GetItemPath((CIDArray *)&v25, i, pszPath, (unsigned int)v6, &v21);
    if ( ItemPath >= 0 && (v21 & 0x40000000) != 0 )
    {
      if ( (v21 & 0x10000) == 0 )
        goto LABEL_47;
      v22 = 0;
      GetLinkTarget(pszPath, 3, &v22, v6);
      v9 = v22;
      if ( !v22 )
        goto LABEL_47;
      v23 = 0;
      v24 = 0;
      v10 = (unsigned __int16 *)DupStr(v22);
      v13 = v10;
      if ( !v10 )
        goto LABEL_46;
      v14 = 0;
      CscFilenameList::ParseFullPath(v11, v10, &v23, &v24);
      if ( v23 && v24 )
        v14 = CscFilenameList::FileExists(this, v23, v24, v15);
      operator delete(v13);
      if ( !v14 )
      {
LABEL_46:
        if ( !CscFilenameList::AddFile(this, v9, 0, v12) )
          ItemPath = -2147024882;
      }
      LocalFreeString(&v22);
      if ( ItemPath >= 0 )
      {
LABEL_47:
        if ( PathIsUNCW(pszPath) )
        {
          v16 = v21 & 0x20000000;
          if ( !a3 )
            goto LABEL_27;
          v17 = v16 == 0;
          if ( v16 )
          {
            if ( !*a3 )
              *a3 = SyncContext_FolderHasSubFolders(pszPath, this) == 0;
LABEL_27:
            v17 = v16 == 0;
          }
          if ( CscFilenameList::AddFile(this, pszPath, !v17, (bool)v6) )
          {
            if ( !v16 && PathIsContentTypeW(pszPath, L"text/html") )
            {
              ExtensionW = PathFindExtensionW(pszPath);
              if ( ExtensionW )
                *ExtensionW = 0;
              FileAttributesW = GetFileAttributesW(pszPath);
              v21 = FileAttributesW;
              if ( FileAttributesW != -1
                && (FileAttributesW & 0x10) != 0
                && !CscFilenameList::AddFile(this, pszPath, 1, (bool)v6) )
              {
                ItemPath = -2147024882;
              }
            }
          }
          else
          {
            ItemPath = -2147024882;
          }
          continue;
        }
      }
    }
  }
  if ( ItemPath < 0 )
    goto LABEL_40;
LABEL_43:
  CIDArray::~CIDArray((CIDArray *)&v25);
  return (unsigned int)ItemPath;
}

```

## disassembly

```asm
0x18003d4c0  mov     [rsp-8+arg_18], rbx
0x18003d4c5  push    rbp
0x18003d4c6  push    rsi
0x18003d4c7  push    rdi
0x18003d4c8  push    r12
0x18003d4ca  push    r13
0x18003d4cc  push    r14
0x18003d4ce  push    r15
0x18003d4d0  lea     rbp, [rsp-1A0h]
0x18003d4d8  sub     rsp, 2A0h
0x18003d4df  mov     rax, cs:__security_cookie
0x18003d4e6  xor     rax, rsp
0x18003d4e9  mov     [rbp+1D0h+var_40], rax
0x18003d4f0  mov     r14, r8
0x18003d4f3  mov     r13, rdx
0x18003d4f6  test    r8, r8
0x18003d4f9  jz      short loc_18003D502
0x18003d4fb  mov     dword ptr [r8], 0
0x18003d502  xorps   xmm0, xmm0
0x18003d505  xorps   xmm1, xmm1
0x18003d508  xor     eax, eax
0x18003d50a  mov     rdx, rcx; struct IDataObject *
0x18003d50d  lea     rcx, [rsp+2D0h+var_280]; this
0x18003d512  mov     [rsp+2D0h+var_270], rax
0x18003d517  movdqu  [rsp+2D0h+var_268], xmm0
0x18003d51d  movups  [rsp+2D0h+var_280], xmm1
0x18003d522  call    ?Initialize@CIDArray@@QEAAJPEAUIDataObject@@@Z; CIDArray::Initialize(IDataObject *)
0x18003d527  mov     ebx, eax
0x18003d529  test    eax, eax
0x18003d52b  js      loc_18003D727
0x18003d531  xor     r15d, r15d
0x18003d534  mov     esi, 8007000Eh
0x18003d539  mov     rax, qword ptr [rsp+2D0h+var_268]
0x18003d53e  test    rax, rax
0x18003d541  jz      short loc_18003D547
0x18003d543  mov     ecx, [rax]
0x18003d545  jmp     short loc_18003D549
0x18003d547  xor     ecx, ecx
0x18003d549  cmp     r15d, ecx
0x18003d54c  jnb     loc_18003D723
0x18003d552  test    ebx, ebx
0x18003d554  js      loc_18003D727
0x18003d55a  lea     rax, [rsp+2D0h+var_2A0]
0x18003d55f  mov     [rsp+2D0h+var_2A0], 60010000h
0x18003d567  lea     r8, [rbp+1D0h+pszPath]; unsigned __int16 *
0x18003d56b  mov     [rsp+2D0h+var_2B0], rax; unsigned int *
0x18003d570  mov     edx, r15d; unsigned int
0x18003d573  lea     rcx, [rsp+2D0h+var_280]; this
0x18003d578  call    ?GetItemPath@CIDArray@@QEAAJIPEAGIPEAK@Z; CIDArray::GetItemPath(uint,ushort *,uint,ulong *)
0x18003d57d  mov     ebx, eax
0x18003d57f  test    eax, eax
0x18003d581  js      loc_18003D71B
0x18003d587  test    [rsp+2D0h+var_2A0], 40000000h
0x18003d58f  jz      loc_18003D71B
0x18003d595  test    [rsp+2D0h+var_2A0], 10000h
0x18003d59d  jz      loc_18003D668
0x18003d5a3  lea     r8, [rsp+2D0h+var_298]; unsigned __int16 **
0x18003d5a8  mov     [rsp+2D0h+var_298], 0
0x18003d5b1  mov     edx, 3; unsigned int
0x18003d5b6  lea     rcx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x18003d5ba  call    ?GetLinkTarget@@YAJPEBGKPEAPEAGPEAK@Z; GetLinkTarget(ushort const *,ulong,ushort * *,ulong *)
0x18003d5bf  mov     rsi, [rsp+2D0h+var_298]
0x18003d5c4  test    rsi, rsi
0x18003d5c7  jz      loc_18003D663
0x18003d5cd  mov     rcx, rsi; unsigned __int16 *
0x18003d5d0  mov     [rsp+2D0h+var_290], 0
0x18003d5d9  mov     [rsp+2D0h+var_288], 0
0x18003d5e2  call    DupStr
0x18003d5e7  mov     rdi, rax
0x18003d5ea  test    rax, rax
0x18003d5ed  jz      short loc_18003D630
0x18003d5ef  lea     r9, [rsp+2D0h+var_288]; unsigned __int16 **
0x18003d5f4  mov     rdx, rax; unsigned __int16 *
0x18003d5f7  lea     r8, [rsp+2D0h+var_290]; unsigned __int16 **
0x18003d5fc  xor     r12b, r12b
0x18003d5ff  call    ?ParseFullPath@CscFilenameList@@AEBAXPEAGPEAPEAG1@Z; CscFilenameList::ParseFullPath(ushort *,ushort * *,ushort * *)
0x18003d604  mov     rdx, [rsp+2D0h+var_290]; unsigned __int16 *
0x18003d609  test    rdx, rdx
0x18003d60c  jz      short loc_18003D623
0x18003d60e  mov     r8, [rsp+2D0h+var_288]; unsigned __int16 *
0x18003d613  test    r8, r8
0x18003d616  jz      short loc_18003D623
0x18003d618  mov     rcx, r13; this
0x18003d61b  call    ?FileExists@CscFilenameList@@QEBA_NPEBG0_N@Z; CscFilenameList::FileExists(ushort const *,ushort const *,bool)
0x18003d620  mov     r12b, al
0x18003d623  mov     rcx, rdi; Block
0x18003d626  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d62b  test    r12b, r12b
0x18003d62e  jnz     short loc_18003D64A
0x18003d630  xor     r8d, r8d; bool
0x18003d633  mov     rdx, rsi; unsigned __int16 *
0x18003d636  mov     rcx, r13; this
0x18003d639  call    ?AddFile@CscFilenameList@@QEAA_NPEBG_N1@Z; CscFilenameList::AddFile(ushort const *,bool,bool)
0x18003d63e  test    al, al
0x18003d640  mov     esi, 8007000Eh
0x18003d645  cmovz   ebx, esi
0x18003d648  jmp     short loc_18003D64F
0x18003d64a  mov     esi, 8007000Eh
0x18003d64f  lea     rcx, [rsp+2D0h+var_298]; unsigned __int16 **
0x18003d654  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x18003d659  test    ebx, ebx
0x18003d65b  js      loc_18003D71B
0x18003d661  jmp     short loc_18003D668
0x18003d663  mov     esi, 8007000Eh
0x18003d668  lea     rcx, [rbp+1D0h+pszPath]; pszPath
0x18003d66c  call    cs:__imp_PathIsUNCW
0x18003d672  test    eax, eax
0x18003d674  jz      loc_18003D71B
0x18003d67a  mov     edi, [rsp+2D0h+var_2A0]
0x18003d67e  and     edi, 20000000h
0x18003d684  test    r14, r14
0x18003d687  jz      short loc_18003D6A9
0x18003d689  test    edi, edi
0x18003d68b  jz      short loc_18003D6AB
0x18003d68d  cmp     dword ptr [r14], 0
0x18003d691  jnz     short loc_18003D6A9
0x18003d693  mov     rdx, r13; this
0x18003d696  lea     rcx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x18003d69a  call    ?SyncContext_FolderHasSubFolders@@YAJPEBGPEAVCscFilenameList@@@Z; SyncContext_FolderHasSubFolders(ushort const *,CscFilenameList *)
0x18003d69f  xor     ecx, ecx
0x18003d6a1  test    eax, eax
0x18003d6a3  setz    cl
0x18003d6a6  mov     [r14], ecx
0x18003d6a9  test    edi, edi
0x18003d6ab  setnz   r8b; bool
0x18003d6af  lea     rdx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x18003d6b3  mov     rcx, r13; this
0x18003d6b6  call    ?AddFile@CscFilenameList@@QEAA_NPEBG_N1@Z; CscFilenameList::AddFile(ushort const *,bool,bool)
0x18003d6bb  test    al, al
0x18003d6bd  jnz     short loc_18003D6C3
0x18003d6bf  mov     ebx, esi
0x18003d6c1  jmp     short loc_18003D71B
0x18003d6c3  test    edi, edi
0x18003d6c5  jnz     short loc_18003D71B
0x18003d6c7  lea     rdx, pszContentType; "text/html"
0x18003d6ce  lea     rcx, [rbp+1D0h+pszPath]; pszPath
0x18003d6d2  call    cs:__imp_PathIsContentTypeW
0x18003d6d8  test    eax, eax
0x18003d6da  jz      short loc_18003D71B
0x18003d6dc  lea     rcx, [rbp+1D0h+pszPath]; pszPath
0x18003d6e0  call    cs:__imp_PathFindExtensionW
0x18003d6e6  test    rax, rax
0x18003d6e9  jz      short loc_18003D6F0
0x18003d6eb  xor     ecx, ecx
0x18003d6ed  mov     [rax], cx
0x18003d6f0  lea     rcx, [rbp+1D0h+pszPath]; lpFileName
0x18003d6f4  call    cs:__imp_GetFileAttributesW
0x18003d6fa  mov     [rsp+2D0h+var_2A0], eax
0x18003d6fe  cmp     eax, 0FFFFFFFFh
0x18003d701  jz      short loc_18003D71B
0x18003d703  test    al, 10h
0x18003d705  jz      short loc_18003D71B
0x18003d707  mov     r8b, 1; bool
0x18003d70a  lea     rdx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x18003d70e  mov     rcx, r13; this
0x18003d711  call    ?AddFile@CscFilenameList@@QEAA_NPEBG_N1@Z; CscFilenameList::AddFile(ushort const *,bool,bool)
0x18003d716  test    al, al
0x18003d718  cmovz   ebx, esi
0x18003d71b  inc     r15d
0x18003d71e  jmp     loc_18003D539
0x18003d723  test    ebx, ebx
0x18003d725  jns     short loc_18003D758
0x18003d727  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d72e  lea     rax, WPP_GLOBAL_Control
0x18003d735  cmp     rcx, rax
0x18003d738  jz      short loc_18003D758
0x18003d73a  test    byte ptr [rcx+1Ch], 2
0x18003d73e  jz      short loc_18003D758
0x18003d740  mov     rcx, [rcx+10h]
0x18003d744  lea     r8, WPP_f72d3c378080343ef5b9ab31099f269e_Traceguids
0x18003d74b  mov     edx, 1Fh
0x18003d750  mov     r9d, ebx
0x18003d753  call    WPP_SF_d
0x18003d758  lea     rcx, [rsp+2D0h+var_280]; this
0x18003d75d  call    ??1CIDArray@@QEAA@XZ; CIDArray::~CIDArray(void)
0x18003d762  mov     eax, ebx
0x18003d764  mov     rcx, [rbp+1D0h+var_40]
0x18003d76b  xor     rcx, rsp; StackCookie
0x18003d76e  call    __security_check_cookie
0x18003d773  mov     rbx, [rsp+2D0h+arg_18]
0x18003d77b  add     rsp, 2A0h
0x18003d782  pop     r15
0x18003d784  pop     r14
0x18003d786  pop     r13
0x18003d788  pop     r12
0x18003d78a  pop     rdi
0x18003d78b  pop     rsi
0x18003d78c  pop     rbp
0x18003d78d  retn
```
