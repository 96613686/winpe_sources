# CCabItemMenu::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x180010440`
- end: `0x1800106fd`
- name: `?InvokeCommand@CCabItemMenu@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `701`
- prototype: `__int64 __fastcall(CCabItemMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002620`
- `0x18000570c`
- `0x180008c48`
- `0x18000acec`
- `0x18000b42c`
- `0x18000b884`
- `0x18000e75c`
- `0x18000f8a8`
- `0x18000faa0`
- `0x18000facc`
- `0x180010440`
- `0x180011308`
- `0x1800113c8`
- `0x1800114fc`
- `0x180011e00`
- `0x180013010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800104ca`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800104e7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800104ca`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800104e7`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800104b3`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800104b3`
- `ole32!OleSetClipboard` at `0x18001059a`
- `ole32!OleSetClipboard` at `0x18001059a`

## string_xrefs

- `0x180010512`: `CabViewCopy`

## pseudocode

```c
__int64 __fastcall CCabItemMenu::InvokeCommand(CCabItemMenu *this, struct _CMINVOKECOMMANDINFO *a2)
{
  const WCHAR *hwnd; // rsi
  __int64 v6; // r14
  unsigned int v7; // esi
  struct _CABITEM **v8; // rax
  CCabObj *v9; // r10
  CCabObj *v10; // rcx
  IDataObject *v11; // rbx
  unsigned int v12; // edi
  unsigned int Count; // esi
  struct _CABITEM **Array; // rax
  CCabObj *v15; // r10
  CCabObj *v16; // rcx
  struct IDataObject *v17; // rsi
  unsigned int v18; // ebx
  CCabExtract *v19; // rcx
  unsigned __int16 v20[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pwszDst[264]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v22[264]; // [rsp+450h] [rbp+350h] BYREF

  if ( a2->cbSize < 0x38 )
    return 2147942487LL;
  if ( WORD1(a2->lpVerb) )
  {
    if ( a2->cbSize < 0x60 || (a2->fMask & 0x4000) == 0 || (hwnd = (const WCHAR *)a2[1].hwnd) == 0 )
    {
      SHAnsiToUnicode(a2->lpVerb, pwszDst, 260);
      hwnd = pwszDst;
    }
    if ( StrCmpICW(hwnd, L"copy") )
      v6 = StrCmpICW(hwnd, L"extract") == 0;
    else
      v6 = 8;
    a2->lpVerb = (LPCSTR)v6;
  }
  if ( LOWORD(a2->lpVerb) == 1 )
  {
    wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
      pwszDst,
      "CabViewExtract");
    *(_QWORD *)pwszDst = &FileExplorerTelemetry::CabViewExtract::`vftable';
    FileExplorerTelemetry::CabViewExtract::StartActivity((FileExplorerTelemetry::CabViewExtract *)pwszDst);
    if ( (unsigned int)CCabFolder::GetPath(*((CCabFolder **)this + 3), v22)
      && (Count = CCabItemList::GetCount((CCabItemMenu *)((char *)this + 32))) != 0 )
    {
      if ( operator new(0x268u) )
      {
        Array = CCabItemList::GetArray((CCabItemMenu *)((char *)this + 32));
        v16 = CCabObj::CCabObj(v15, *((HWND *)this + 2), *((struct CCabFolder **)this + 3), Array, Count);
      }
      else
      {
        v16 = 0;
      }
      v17 = (struct IDataObject *)(((unsigned __int64)v16 + 16) & -(__int64)(v16 != 0));
      if ( v17 )
      {
        StringCchCopyW(v20, 0x104u, v22);
        v18 = CCabExtract::ExtractToFolder(v19, *((HWND *)this + 2), v17);
        ((void (__fastcall *)(struct IDataObject *))v17->lpVtbl->Release)(v17);
        wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
          pwszDst,
          v18);
      }
      else
      {
        v18 = -2147024882;
      }
    }
    else
    {
      v18 = -2147418113;
    }
    FileExplorerTelemetry::CabViewExtract::~CabViewExtract((FileExplorerTelemetry::CabViewExtract *)pwszDst);
    return v18;
  }
  else
  {
    if ( LOWORD(a2->lpVerb) != 8 )
      return 2147942487LL;
    wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
      pwszDst,
      "CabViewCopy");
    *(_QWORD *)pwszDst = &FileExplorerTelemetry::CabViewCopy::`vftable';
    FileExplorerTelemetry::CabViewCopy::StartActivity((FileExplorerTelemetry::CabViewCopy *)pwszDst);
    v7 = CCabItemList::GetCount((CCabItemMenu *)((char *)this + 32));
    if ( v7
      && (!operator new(0x268u)
        ? (v10 = 0)
        : (v8 = CCabItemList::GetArray((CCabItemMenu *)((char *)this + 32)),
           v10 = CCabObj::CCabObj(v9, *((HWND *)this + 2), *((struct CCabFolder **)this + 3), v8, v7)),
          (v11 = (IDataObject *)(((unsigned __int64)v10 + 16)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64))) != 0) )
    {
      v12 = OleSetClipboard(v11);
      ((void (__fastcall *)(IDataObject *))v11->lpVtbl->Release)(v11);
    }
    else
    {
      v12 = -2147467259;
    }
    wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      pwszDst,
      v12);
    FileExplorerTelemetry::CabViewCopy::~CabViewCopy((FileExplorerTelemetry::CabViewCopy *)pwszDst);
    return v12;
  }
}

```

## disassembly

```asm
0x180010440  mov     [rsp-8+arg_10], rbx
0x180010445  push    rbp
0x180010446  push    rsi
0x180010447  push    rdi
0x180010448  push    r14
0x18001044a  push    r15
0x18001044c  lea     rbp, [rsp-570h]
0x180010454  sub     rsp, 670h
0x18001045b  mov     rax, cs:__security_cookie
0x180010462  xor     rax, rsp
0x180010465  mov     [rbp+590h+var_30], rax
0x18001046c  cmp     dword ptr [rdx], 38h ; '8'
0x18001046f  mov     rbx, rdx
0x180010472  mov     rdi, rcx
0x180010475  jnb     short loc_180010481
0x180010477  mov     eax, 80070057h
0x18001047c  jmp     loc_1800106D7
0x180010481  xor     r15d, r15d
0x180010484  cmp     [rdx+12h], r15w
0x180010489  jz      short loc_1800104FC
0x18001048b  cmp     dword ptr [rdx], 60h ; '`'
0x18001048e  jb      short loc_1800104A2
0x180010490  test    dword ptr [rdx+4], 4000h
0x180010497  jz      short loc_1800104A2
0x180010499  mov     rsi, [rdx+40h]
0x18001049d  test    rsi, rsi
0x1800104a0  jnz     short loc_1800104C0
0x1800104a2  mov     rcx, [rbx+10h]; pszSrc
0x1800104a6  lea     rdx, [rbp+590h+pwszDst]; pwszDst
0x1800104ad  mov     r8d, 104h; cwchBuf
0x1800104b3  call    cs:__imp_SHAnsiToUnicode
0x1800104b9  lea     rsi, [rbp+590h+pwszDst]
0x1800104c0  lea     rdx, pszStr2; "copy"
0x1800104c7  mov     rcx, rsi; pszStr1
0x1800104ca  call    cs:__imp_StrCmpICW
0x1800104d0  test    eax, eax
0x1800104d2  jnz     short loc_1800104DA
0x1800104d4  lea     r14d, [rax+8]
0x1800104d8  jmp     short loc_1800104F8
0x1800104da  lea     rdx, aExtract; "extract"
0x1800104e1  mov     rcx, rsi; pszStr1
0x1800104e4  mov     r14, r15
0x1800104e7  call    cs:__imp_StrCmpICW
0x1800104ed  test    eax, eax
0x1800104ef  mov     ecx, 1
0x1800104f4  cmovz   r14, rcx
0x1800104f8  mov     [rbx+10h], r14
0x1800104fc  movzx   eax, word ptr [rbx+10h]
0x180010500  sub     eax, 1
0x180010503  jz      loc_1800105D9
0x180010509  cmp     eax, 7
0x18001050c  jnz     loc_180010477
0x180010512  lea     rdx, aCabviewcopy; "CabViewCopy"
0x180010519  lea     rcx, [rbp+590h+pwszDst]
0x180010520  call    ??0?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010525  lea     rax, ??_7CabViewCopy@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::CabViewCopy::`vftable'
0x18001052c  lea     rcx, [rbp+590h+pwszDst]; this
0x180010533  mov     qword ptr [rbp+590h+pwszDst], rax
0x18001053a  call    ?StartActivity@CabViewCopy@FileExplorerTelemetry@@QEAAXXZ; FileExplorerTelemetry::CabViewCopy::StartActivity(void)
0x18001053f  lea     rcx, [rdi+20h]; this
0x180010543  call    ?GetCount@CCabItemList@@QEAAIXZ; CCabItemList::GetCount(void)
0x180010548  mov     esi, eax
0x18001054a  test    eax, eax
0x18001054c  jz      short loc_1800105B3
0x18001054e  mov     ecx, 268h; unsigned __int64
0x180010553  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010558  mov     r10, rax
0x18001055b  test    rax, rax
0x18001055e  jz      short loc_180010585
0x180010560  lea     rcx, [rdi+20h]; this
0x180010564  call    ?GetArray@CCabItemList@@QEAAPEAPEFAU_CABITEM@@XZ; CCabItemList::GetArray(void)
0x180010569  mov     r8, [rdi+18h]; struct CCabFolder *
0x18001056d  mov     r9, rax; struct _CABITEM **
0x180010570  mov     rdx, [rdi+10h]; HWND
0x180010574  mov     rcx, r10; this
0x180010577  mov     [rsp+690h+var_670], esi; unsigned int
0x18001057b  call    ??0CCabObj@@QEAA@PEAUHWND__@@PEAVCCabFolder@@PEAPEFAU_CABITEM@@I@Z; CCabObj::CCabObj(HWND__ *,CCabFolder *,_CABITEM * *,uint)
0x180010580  mov     rcx, rax
0x180010583  jmp     short loc_180010588
0x180010585  mov     rcx, r15
0x180010588  lea     rax, [rcx+10h]
0x18001058c  neg     rcx
0x18001058f  sbb     rbx, rbx
0x180010592  and     rbx, rax
0x180010595  jz      short loc_1800105B3
0x180010597  mov     rcx, rbx; pDataObj
0x18001059a  call    cs:__imp_OleSetClipboard
0x1800105a0  mov     rdx, [rbx]
0x1800105a3  mov     rcx, rbx
0x1800105a6  mov     edi, eax
0x1800105a8  mov     rax, [rdx+10h]
0x1800105ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105b1  jmp     short loc_1800105B8
0x1800105b3  mov     edi, 80004005h
0x1800105b8  mov     edx, edi
0x1800105ba  lea     rcx, [rbp+590h+pwszDst]
0x1800105c1  call    ?Stop@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800105c6  lea     rcx, [rbp+590h+pwszDst]; this
0x1800105cd  call    ??1CabViewCopy@FileExplorerTelemetry@@QEAA@XZ; FileExplorerTelemetry::CabViewCopy::~CabViewCopy(void)
0x1800105d2  mov     eax, edi
0x1800105d4  jmp     loc_1800106D7
0x1800105d9  lea     rdx, aCabviewextract; "CabViewExtract"
0x1800105e0  lea     rcx, [rbp+590h+pwszDst]
0x1800105e7  call    ??0?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800105ec  lea     rax, ??_7CabViewExtract@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::CabViewExtract::`vftable'
0x1800105f3  lea     rcx, [rbp+590h+pwszDst]; this
0x1800105fa  mov     qword ptr [rbp+590h+pwszDst], rax
0x180010601  call    ?StartActivity@CabViewExtract@FileExplorerTelemetry@@QEAAXXZ; FileExplorerTelemetry::CabViewExtract::StartActivity(void)
0x180010606  mov     rcx, [rdi+18h]; this
0x18001060a  lea     rdx, [rbp+590h+var_240]; unsigned __int16 *
0x180010611  call    ?GetPath@CCabFolder@@QEAAHPEAG@Z; CCabFolder::GetPath(ushort *)
0x180010616  test    eax, eax
0x180010618  jz      loc_1800106C4
0x18001061e  lea     rcx, [rdi+20h]; this
0x180010622  call    ?GetCount@CCabItemList@@QEAAIXZ; CCabItemList::GetCount(void)
0x180010627  mov     esi, eax
0x180010629  test    eax, eax
0x18001062b  jz      loc_1800106C4
0x180010631  mov     ecx, 268h; unsigned __int64
0x180010636  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001063b  mov     r10, rax
0x18001063e  test    rax, rax
0x180010641  jz      short loc_180010668
0x180010643  lea     rcx, [rdi+20h]; this
0x180010647  call    ?GetArray@CCabItemList@@QEAAPEAPEFAU_CABITEM@@XZ; CCabItemList::GetArray(void)
0x18001064c  mov     r8, [rdi+18h]; struct CCabFolder *
0x180010650  mov     r9, rax; struct _CABITEM **
0x180010653  mov     rdx, [rdi+10h]; HWND
0x180010657  mov     rcx, r10; this
0x18001065a  mov     [rsp+690h+var_670], esi; unsigned int
0x18001065e  call    ??0CCabObj@@QEAA@PEAUHWND__@@PEAVCCabFolder@@PEAPEFAU_CABITEM@@I@Z; CCabObj::CCabObj(HWND__ *,CCabFolder *,_CABITEM * *,uint)
0x180010663  mov     rcx, rax
0x180010666  jmp     short loc_18001066B
0x180010668  mov     rcx, r15
0x18001066b  lea     rax, [rcx+10h]
0x18001066f  neg     rcx
0x180010672  sbb     rsi, rsi
0x180010675  and     rsi, rax
0x180010678  jnz     short loc_180010681
0x18001067a  mov     ebx, 8007000Eh
0x18001067f  jmp     short loc_1800106C9
0x180010681  lea     r8, [rbp+590h+var_240]; unsigned __int16 *
0x180010688  mov     edx, 104h; unsigned __int64
0x18001068d  lea     rcx, [rsp+690h+var_660]; unsigned __int16 *
0x180010692  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010697  mov     rdx, [rdi+10h]; HWND
0x18001069b  mov     r8, rsi; struct IDataObject *
0x18001069e  call    ?ExtractToFolder@CCabExtract@@QEAAJPEAUHWND__@@PEAUIDataObject@@@Z; CCabExtract::ExtractToFolder(HWND__ *,IDataObject *)
0x1800106a3  mov     rdx, [rsi]
0x1800106a6  mov     ebx, eax
0x1800106a8  mov     rcx, rsi
0x1800106ab  mov     rax, [rdx+10h]
0x1800106af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106b4  mov     edx, ebx
0x1800106b6  lea     rcx, [rbp+590h+pwszDst]
0x1800106bd  call    ?Stop@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800106c2  jmp     short loc_1800106C9
0x1800106c4  mov     ebx, 8000FFFFh
0x1800106c9  lea     rcx, [rbp+590h+pwszDst]; this
0x1800106d0  call    ??1CabViewExtract@FileExplorerTelemetry@@QEAA@XZ; FileExplorerTelemetry::CabViewExtract::~CabViewExtract(void)
0x1800106d5  mov     eax, ebx
0x1800106d7  mov     rcx, [rbp+590h+var_30]
0x1800106de  xor     rcx, rsp; StackCookie
0x1800106e1  call    __security_check_cookie
0x1800106e6  mov     rbx, [rsp+690h+arg_10]
0x1800106ee  add     rsp, 670h
0x1800106f5  pop     r15
0x1800106f7  pop     r14
0x1800106f9  pop     rdi
0x1800106fa  pop     rsi
0x1800106fb  pop     rbp
0x1800106fc  retn
```
