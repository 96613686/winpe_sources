# CDownloadWindowItem::Update(__MIDL___MIDL_itf_dlm_0000_0000_0014,ushort const *,bool,ushort const *)

- ea: `0x1803cd270`
- end: `0x1803cda10`
- name: `?Update@CDownloadWindowItem@@UEAAXU__MIDL___MIDL_itf_dlm_0000_0000_0014@@PEBG_N1@Z`
- size: `1952`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005030`
- `0x180007010`
- `0x1800096a0`
- `0x1800144d0`
- `0x1800600ec`
- `0x180069118`
- `0x18008cde8`
- `0x1800a2f18`
- `0x1802d04f8`
- `0x1802d0558`
- `0x1802dcf44`
- `0x1803b29f4`
- `0x1803b2c00`
- `0x1803cd270`
- `0x1803ce508`
- `0x1803d00e0`
- `0x1803d01e4`
- `0x1803d0954`
- `0x18042e608`
- `0x18045477c`
- `0x1804548e4`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!FindAtomW` at `0x1803cd56f`
- `KERNEL32!FindAtomW` at `0x1803cd620`
- `KERNEL32!FindAtomW` at `0x1803cd641`
- `KERNEL32!FindAtomW` at `0x1803cd77f`
- `KERNEL32!FindAtomW` at `0x1803cd951`
- `KERNEL32!FindAtomW` at `0x1803cd56f`
- `KERNEL32!FindAtomW` at `0x1803cd620`
- `KERNEL32!FindAtomW` at `0x1803cd641`
- `KERNEL32!FindAtomW` at `0x1803cd77f`
- `KERNEL32!FindAtomW` at `0x1803cd951`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803cd992`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803cd992`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x1803cd605`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x1803cd605`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindNextComponentW` at `0x1803cd557`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindNextComponentW` at `0x1803cd557`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsUNCW` at `0x1803cd504`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsUNCW` at `0x1803cd504`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x1803cd316`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x1803cd316`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1803cd6b7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1803cd6b7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathStripPathW` at `0x1803cd5de`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathStripPathW` at `0x1803cd5de`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x1803cd711`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x1803cd711`
- `USER32!PostMessageW` at `0x1803cd838`
- `USER32!PostMessageW` at `0x1803cd838`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803cd329`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803cd36c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803cd69a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803cd329`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803cd36c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803cd69a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd33b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd4a3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd67c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd742`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd76c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd33b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd4a3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd67c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd742`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1803cd76c`

## string_xrefs

- `0x1803cd637`: `extension`

## pseudocode

```c
void __fastcall CDownloadWindowItem::Update(
        _BYTE *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        char a4,
        const WCHAR *psz1)
{
  int v6; // eax
  __int64 v8; // rsi
  LPVOID *v10; // rdi
  void *v11; // rcx
  HRESULT v12; // eax
  char v13; // al
  bool v14; // al
  char v15; // al
  char v16; // al
  bool v17; // zf
  unsigned int v18; // edi
  __int64 v19; // r14
  WCHAR *v20; // r14
  WCHAR *NextComponentW; // rax
  ATOM AtomW; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v24; // r12
  const WCHAR *v25; // rcx
  ATOM v26; // ax
  DirectUI::Element *v27; // r12
  ATOM v28; // ax
  struct DirectUI::Element *v29; // rax
  DirectUI::Element *v30; // r14
  const unsigned __int16 *ExtensionW; // rax
  ATOM v32; // ax
  DirectUI::Element *v33; // rax
  _OWORD *v34; // rax
  void *v35; // r14
  int v36; // r14d
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rcx
  unsigned int v39; // edi
  ATOM v40; // ax
  DirectUI::Element *v41; // rdi
  int v42; // [rsp+20h] [rbp-E0h]
  LPWSTR ppwsz; // [rsp+30h] [rbp-D0h] BYREF
  struct IDownloadRateCalculator *v44; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR psz2[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v47[264]; // [rsp+460h] [rbp+360h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  v6 = *(_DWORD *)(a2 + 36);
  v8 = a2;
  if ( a1[312] )
  {
    if ( !v6 )
    {
      LOBYTE(v42) = 1;
      (*(void (__fastcall **)(_BYTE *, _QWORD, const WCHAR *, _QWORD))(*(_QWORD *)a1 + 448LL))(
        a1,
        0,
        L"percent_saved",
        0);
      a1[312] = 0;
    }
  }
  else if ( v6 )
  {
    CDownloadWindowItem::_SetTotalSize((CDownloadWindowItem *)a1, *(_QWORD *)(a2 + 80));
  }
  v10 = (LPVOID *)(a1 + 304);
  v11 = (void *)*((_QWORD *)a1 + 38);
  if ( psz1 )
  {
    if ( !v11 || StrCmpIW(psz1, *((PCWSTR *)a1 + 38)) )
    {
      CoTaskMemFree(*v10);
      v12 = SHStrDupW(psz1, (LPWSTR *)a1 + 38);
      if ( v12 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x536,
          (unsigned int)"inetcore\\ieframe\\browseui\\downloadmanager\\downloadwindowitem.cpp",
          (const char *)(unsigned int)v12,
          v42);
    }
  }
  else if ( v11 )
  {
    CoTaskMemFree(v11);
    *v10 = 0;
  }
  if ( a1[343] || (v13 = 0, *(_DWORD *)(v8 + 8) == 1) )
    v13 = 1;
  a1[343] = v13;
  v14 = a1[344] || *(_DWORD *)(v8 + 8) == 1 && !a1[402];
  a1[344] = v14;
  if ( a1[340] || (v15 = 0, *(_DWORD *)(v8 + 40) == 1) )
    v15 = 1;
  a1[340] = v15;
  if ( !*(_DWORD *)(v8 + 104) || *v10 || (v16 = 1, *((_QWORD *)a1 + 37)) )
    v16 = 0;
  v17 = *(_DWORD *)(v8 + 128) == 0;
  v18 = *(_DWORD *)v8;
  a1[341] = v16;
  *((_DWORD *)a1 + 102) = *(_DWORD *)(v8 + 4);
  a1[336] = !v17;
  if ( *((_DWORD *)a1 + 82) != v18 || a4 )
  {
    if ( v18 == 10 || v18 == 11 && *((_DWORD *)a1 + 101) == 2 )
    {
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)a1 + 384LL))(a1, 2);
      v34 = operator new(0x10u);
      v35 = v34;
      if ( v34 )
      {
        *v34 = *((_OWORD *)a1 + 13);
        if ( !PostMessageW(*((HWND *)a1 + 28), 0x4409u, (v18 != 10) + 2LL, (LPARAM)v34) )
          operator delete(v35);
      }
    }
    else
    {
      if ( !*((_QWORD *)a1 + 29) )
      {
        if ( a3 )
        {
          if ( v18 )
          {
            StringCchCopyW(pszPath, 0x104u, a3);
            PathCchRemoveFileSpec(pszPath, 0x104u);
            PathCchAddBackslashEx(pszPath, 0x104u, 0, 0);
            if ( SHStrDupW(pszPath, (LPWSTR *)a1 + 29) >= 0 )
            {
              v19 = -1;
              do
                ++v19;
              while ( pszPath[v19] );
              if ( (unsigned __int64)(v19 - 1) <= 0x102 && psz2[v19 + 263] == 92 && !PathCchIsRoot(pszPath) )
                psz2[v19 + 263] = 0;
              if ( PathIsUNCW(pszPath) )
              {
                v20 = pszPath;
                NextComponentW = pszPath;
                do
                {
                  if ( !*NextComponentW )
                    break;
                  v20 = NextComponentW;
                  NextComponentW = PathFindNextComponentW(NextComponentW);
                }
                while ( NextComponentW );
              }
              else
              {
                v20 = pszPath;
                if ( (int)PathToDisplayNameW(pszPath, v47) >= 0 )
                  v20 = v47;
              }
              AtomW = FindAtomW(L"action_location");
              Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)a1, AtomW);
              v24 = Descendent;
              if ( Descendent )
              {
                DirectUI::Element::SetContentString(Descendent, v20);
                DirectUI::Element::SetAccName(v24, v20);
                DirectUI::Element::SetAccDesc(v24, a3);
              }
              StringCchCopyW(psz2, 0x104u, a3);
              if ( CDownloadFilePathUtilities::IsProgressPath(psz2) )
                CDownloadFilePathUtilities::ConvertProgressPathToFinalPathInPlace(psz2);
              PathStripPathW(psz2);
              v25 = (const WCHAR *)*((_QWORD *)a1 + 32);
              if ( !v25 || *(_DWORD *)(v8 + 8) != 1 && StrCmpW(v25, psz2) )
              {
                v26 = FindAtomW(L"filename");
                v27 = DirectUI::Element::FindDescendent((DirectUI::Element *)a1, v26);
                v28 = FindAtomW(L"extension");
                v29 = DirectUI::Element::FindDescendent((DirectUI::Element *)a1, v28);
                v30 = v29;
                if ( v27 )
                {
                  if ( v29 )
                  {
                    ppwsz = 0;
                    SHStrDupW(psz2, &ppwsz);
                    if ( ppwsz )
                    {
                      CoTaskMemFree(*((LPVOID *)a1 + 33));
                      *((_QWORD *)a1 + 33) = ppwsz;
                      ExtensionW = PathFindExtensionW(psz2);
                      DirectUI::Element::SetContentString(v30, ExtensionW);
                      DirectUI::Element::SetAccDesc(v30, psz2);
                      DirectUI::Element::SetAccName(v27, psz2);
                      DirectUI::Element::SetAccDesc(v27, psz2);
                      (*(void (__fastcall **)(_BYTE *, WCHAR *))(*(_QWORD *)a1 + 392LL))(a1, psz2);
                      PathRemoveExtensionW(psz2);
                      DirectUI::Element::SetContentString(v27, psz2);
                    }
                  }
                }
              }
            }
          }
        }
      }
      if ( !*((_QWORD *)a1 + 31) && a3 && v18 )
        SHStrDupW(a3, (LPWSTR *)a1 + 31);
      if ( !*((_QWORD *)a1 + 30) && a3 && (v18 == 8 || v18 == 11) )
      {
        SHStrDupW(a3, (LPWSTR *)a1 + 30);
        v32 = FindAtomW(L"action_location");
        v33 = DirectUI::Element::FindDescendent((DirectUI::Element *)a1, v32);
        if ( v33 )
          DirectUI::Element::SetAccDesc(v33, a3);
      }
      if ( v18 == 1 && !*((_DWORD *)a1 + 83) && !*((_DWORD *)a1 + 88) && *(_DWORD *)(v8 + 132) )
        v18 = 7;
      (*(void (__fastcall **)(_BYTE *, _QWORD, _QWORD))(*(_QWORD *)a1 + 424LL))(a1, v18, *((unsigned int *)a1 + 83));
    }
  }
  if ( v18 - 2 <= 3 )
  {
    v36 = *(_DWORD *)(v8 + 36);
    if ( v36 )
    {
      if ( v18 == 5 )
        ATL::AtlComPtrAssign((struct IUnknown **)a1 + 40, 0);
      LODWORD(ppwsz) = 0;
      v44 = 0;
      if ( (int)CDownloadWindowItem::_GetRateCalculator((CDownloadWindowItem *)a1, &v44) < 0 )
      {
        if ( *(_QWORD *)(v8 + 88) )
        {
          v37 = *(_QWORD *)(v8 + 80);
          if ( v37 < 0x64 )
            v38 = 1;
          else
            v38 = v37 / 0x64;
          LODWORD(ppwsz) = *(_QWORD *)(v8 + 88) / v38;
        }
      }
      else if ( (*(int (__fastcall **)(struct IDownloadRateCalculator *, LPWSTR *))(*(_QWORD *)v44 + 72LL))(v44, &ppwsz) < 0 )
      {
        LODWORD(ppwsz) = 99;
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)a1 + 456LL))(a1);
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v44);
    }
    else
    {
      LOBYTE(a2) = v18 != 3;
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)a1 + 464LL))(a1, a2);
    }
    v39 = v18 - 2;
    if ( v39 )
    {
      if ( v39 == 1 )
      {
        v40 = FindAtomW(L"progress");
        v41 = DirectUI::Element::FindDescendent((DirectUI::Element *)a1, v40);
        if ( v41 )
        {
          LoadStringW(g_hinstMUI, *(_DWORD *)(v8 + 120) != 0 ? 53480 : 53463, psz2, 260);
          DirectUI::Element::SetContentString(v41, psz2);
          DirectUI::Element::SetAccName(v41, psz2);
          (*(void (__fastcall **)(_BYTE *, WCHAR *))(*(_QWORD *)a1 + 400LL))(a1, psz2);
        }
      }
    }
    else if ( v36 )
    {
      CDownloadWindowItem::_ShowTimeRemaining((CDownloadWindowItem *)a1);
    }
    else
    {
      CDownloadWindowItem::_ShowAmountDownloaded((CDownloadWindowItem *)a1);
    }
  }
}

```

## disassembly

```asm
0x1803cd270  mov     [rsp-8+arg_18], rbx
0x1803cd275  push    rbp
0x1803cd276  push    rsi
0x1803cd277  push    rdi
0x1803cd278  push    r12
0x1803cd27a  push    r13
0x1803cd27c  push    r14
0x1803cd27e  push    r15
0x1803cd280  lea     rbp, [rsp-580h]
0x1803cd288  sub     rsp, 680h
0x1803cd28f  mov     rax, cs:__security_cookie
0x1803cd296  xor     rax, rsp
0x1803cd299  mov     [rbp+5B0h+var_40], rax
0x1803cd2a0  mov     r14, [rbp+5B0h+psz1]
0x1803cd2a7  xor     r13d, r13d
0x1803cd2aa  mov     r12b, r9b
0x1803cd2ad  mov     eax, [rdx+24h]
0x1803cd2b0  mov     r15, r8
0x1803cd2b3  mov     rsi, rdx
0x1803cd2b6  mov     rbx, rcx
0x1803cd2b9  cmp     [rcx+138h], r13b
0x1803cd2c0  jnz     short loc_1803CD2D1
0x1803cd2c2  test    eax, eax
0x1803cd2c4  jz      short loc_1803CD2FC
0x1803cd2c6  mov     rdx, [rdx+50h]; qdw
0x1803cd2ca  call    ?_SetTotalSize@CDownloadWindowItem@@IEAAX_K@Z; CDownloadWindowItem::_SetTotalSize(unsigned __int64)
0x1803cd2cf  jmp     short loc_1803CD2FC
0x1803cd2d1  test    eax, eax
0x1803cd2d3  jnz     short loc_1803CD2FC
0x1803cd2d5  mov     rax, [rcx]
0x1803cd2d8  lea     r8, aPercentSaved; "percent_saved"
0x1803cd2df  xor     r9d, r9d
0x1803cd2e2  mov     byte ptr [rsp+6B0h+var_690], 1; int
0x1803cd2e7  xor     edx, edx
0x1803cd2e9  mov     rax, [rax+1C0h]
0x1803cd2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803cd2f5  mov     [rbx+138h], r13b
0x1803cd2fc  lea     rdi, [rbx+130h]
0x1803cd303  mov     rcx, [rdi]; pv
0x1803cd306  test    r14, r14
0x1803cd309  jz      short loc_1803CD367
0x1803cd30b  test    rcx, rcx
0x1803cd30e  jz      short loc_1803CD326
0x1803cd310  mov     rdx, rcx; psz2
0x1803cd313  mov     rcx, r14; psz1
0x1803cd316  call    cs:__imp_StrCmpIW
0x1803cd31d  nop     dword ptr [rax+rax+00h]
0x1803cd322  test    eax, eax
0x1803cd324  jz      short loc_1803CD37B
0x1803cd326  mov     rcx, [rdi]; pv
0x1803cd329  call    cs:__imp_CoTaskMemFree
0x1803cd330  nop     dword ptr [rax+rax+00h]
0x1803cd335  mov     rdx, rdi; ppwsz
0x1803cd338  mov     rcx, r14; psz
0x1803cd33b  call    cs:__imp_SHStrDupW
0x1803cd342  nop     dword ptr [rax+rax+00h]
0x1803cd347  test    eax, eax
0x1803cd349  jns     short loc_1803CD37B
0x1803cd34b  mov     rcx, [rbp+5B8h]; this
0x1803cd352  lea     r8, aInetcoreIefram_24; "inetcore\\ieframe\\browseui\\downloadma"...
0x1803cd359  mov     r9d, eax; char *
0x1803cd35c  mov     edx, 536h; void *
0x1803cd361  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1803cd367  test    rcx, rcx
0x1803cd36a  jz      short loc_1803CD37B
0x1803cd36c  call    cs:__imp_CoTaskMemFree
0x1803cd373  nop     dword ptr [rax+rax+00h]
0x1803cd378  mov     [rdi], r13
0x1803cd37b  cmp     [rbx+157h], r13b
0x1803cd382  jnz     short loc_1803CD38D
0x1803cd384  cmp     dword ptr [rsi+8], 1
0x1803cd388  mov     al, r13b
0x1803cd38b  jnz     short loc_1803CD38F
0x1803cd38d  mov     al, 1
0x1803cd38f  mov     [rbx+157h], al
0x1803cd395  cmp     [rbx+158h], r13b
0x1803cd39c  jnz     short loc_1803CD3B2
0x1803cd39e  cmp     dword ptr [rsi+8], 1
0x1803cd3a2  jnz     short loc_1803CD3AD
0x1803cd3a4  cmp     [rbx+192h], r13b
0x1803cd3ab  jz      short loc_1803CD3B2
0x1803cd3ad  mov     al, r13b
0x1803cd3b0  jmp     short loc_1803CD3B4
0x1803cd3b2  mov     al, 1
0x1803cd3b4  mov     [rbx+158h], al
0x1803cd3ba  cmp     [rbx+154h], r13b
0x1803cd3c1  jnz     short loc_1803CD3CC
0x1803cd3c3  cmp     dword ptr [rsi+28h], 1
0x1803cd3c7  mov     al, r13b
0x1803cd3ca  jnz     short loc_1803CD3CE
0x1803cd3cc  mov     al, 1
0x1803cd3ce  mov     [rbx+154h], al
0x1803cd3d4  cmp     [rsi+68h], r13d
0x1803cd3d8  jz      short loc_1803CD3EA
0x1803cd3da  cmp     [rdi], r13
0x1803cd3dd  jnz     short loc_1803CD3EA
0x1803cd3df  mov     al, 1
0x1803cd3e1  cmp     [rbx+128h], r13
0x1803cd3e8  jz      short loc_1803CD3ED
0x1803cd3ea  mov     al, r13b
0x1803cd3ed  cmp     [rsi+80h], r13d
0x1803cd3f4  mov     edi, [rsi]
0x1803cd3f6  mov     [rbx+155h], al
0x1803cd3fc  mov     eax, [rsi+4]
0x1803cd3ff  mov     [rbx+198h], eax
0x1803cd405  setnz   al
0x1803cd408  mov     [rbx+150h], al
0x1803cd40e  cmp     [rbx+148h], edi
0x1803cd414  jnz     short loc_1803CD41F
0x1803cd416  test    r12b, r12b
0x1803cd419  jz      loc_1803CD850
0x1803cd41f  cmp     edi, 0Ah
0x1803cd422  jz      loc_1803CD7E7
0x1803cd428  cmp     edi, 0Bh
0x1803cd42b  jnz     short loc_1803CD43A
0x1803cd42d  cmp     dword ptr [rbx+194h], 2
0x1803cd434  jz      loc_1803CD7E7
0x1803cd43a  lea     r14, [rbx+0E8h]
0x1803cd441  cmp     [r14], r13
0x1803cd444  jnz     loc_1803CD72A
0x1803cd44a  test    r15, r15
0x1803cd44d  jz      loc_1803CD72A
0x1803cd453  test    edi, edi
0x1803cd455  jz      loc_1803CD72A
0x1803cd45b  mov     r8, r15; unsigned __int16 *
0x1803cd45e  lea     rcx, [rbp+5B0h+pszPath]; unsigned __int16 *
0x1803cd465  mov     edx, 104h; unsigned __int64
0x1803cd46a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1803cd46f  mov     r12d, 104h
0x1803cd475  lea     rcx, [rbp+5B0h+pszPath]; pszPath
0x1803cd47c  mov     edx, r12d; cchPath
0x1803cd47f  call    PathCchRemoveFileSpec
0x1803cd484  xor     r9d, r9d; pcchRemaining
0x1803cd487  lea     rcx, [rbp+5B0h+pszPath]; pszPath
0x1803cd48e  xor     r8d, r8d; ppszEnd
0x1803cd491  mov     edx, r12d; cchPath
0x1803cd494  call    PathCchAddBackslashEx
0x1803cd499  mov     rdx, r14; ppwsz
0x1803cd49c  lea     rcx, [rbp+5B0h+pszPath]; psz
0x1803cd4a3  call    cs:__imp_SHStrDupW
0x1803cd4aa  nop     dword ptr [rax+rax+00h]
0x1803cd4af  test    eax, eax
0x1803cd4b1  js      loc_1803CD72A
0x1803cd4b7  lea     rax, [rbp+5B0h+pszPath]
0x1803cd4be  or      r14, 0FFFFFFFFFFFFFFFFh
0x1803cd4c2  inc     r14
0x1803cd4c5  cmp     [rax+r14*2], r13w
0x1803cd4ca  jnz     short loc_1803CD4C2
0x1803cd4cc  lea     rax, [r14-1]
0x1803cd4d0  cmp     rax, 102h
0x1803cd4d6  ja      short loc_1803CD4FD
0x1803cd4d8  cmp     [rbp+r14*2+5B0h+var_462], 5Ch ; '\'
0x1803cd4e2  jnz     short loc_1803CD4FD
0x1803cd4e4  lea     rcx, [rbp+5B0h+pszPath]; pszPath
0x1803cd4eb  call    PathCchIsRoot
0x1803cd4f0  test    eax, eax
0x1803cd4f2  jnz     short loc_1803CD4FD
0x1803cd4f4  mov     [rbp+r14*2+5B0h+var_462], r13w
0x1803cd4fd  lea     rcx, [rbp+5B0h+pszPath]; pszPath
0x1803cd504  call    cs:__imp_PathIsUNCW
0x1803cd50b  nop     dword ptr [rax+rax+00h]
0x1803cd510  test    eax, eax
0x1803cd512  jnz     short loc_1803CD53D
0x1803cd514  lea     rdx, [rbp+5B0h+var_250]; unsigned __int16 *
0x1803cd51b  lea     rcx, [rbp+5B0h+pszPath]; pszPath
0x1803cd522  call    PathToDisplayNameW
0x1803cd527  test    eax, eax
0x1803cd529  lea     r14, [rbp+5B0h+pszPath]
0x1803cd530  lea     rcx, [rbp+5B0h+var_250]
0x1803cd537  cmovns  r14, rcx
0x1803cd53b  jmp     short loc_1803CD568
0x1803cd53d  lea     r14, [rbp+5B0h+pszPath]
0x1803cd544  lea     rax, [rbp+5B0h+pszPath]
0x1803cd54b  cmp     [rax], r13w
0x1803cd54f  jz      short loc_1803CD568
0x1803cd551  mov     rcx, rax; pszPath
0x1803cd554  mov     r14, rax
0x1803cd557  call    cs:__imp_PathFindNextComponentW
0x1803cd55e  nop     dword ptr [rax+rax+00h]
0x1803cd563  test    rax, rax
0x1803cd566  jnz     short loc_1803CD54B
0x1803cd568  lea     rcx, aActionLocation; "action_location"
0x1803cd56f  call    cs:__imp_FindAtomW
0x1803cd576  nop     dword ptr [rax+rax+00h]
0x1803cd57b  movzx   edx, ax; unsigned __int16
0x1803cd57e  mov     rcx, rbx; this
0x1803cd581  call    ?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1803cd586  mov     r12, rax
0x1803cd589  test    rax, rax
0x1803cd58c  jz      short loc_1803CD5AF
0x1803cd58e  mov     rdx, r14; unsigned __int16 *
0x1803cd591  mov     rcx, rax; this
0x1803cd594  call    ?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1803cd599  mov     rdx, r14; unsigned __int16 *
0x1803cd59c  mov     rcx, r12; this
0x1803cd59f  call    ?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x1803cd5a4  mov     rdx, r15; unsigned __int16 *
0x1803cd5a7  mov     rcx, r12; this
0x1803cd5aa  call    ?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x1803cd5af  mov     r8, r15; unsigned __int16 *
0x1803cd5b2  lea     rcx, [rsp+6B0h+psz2]; unsigned __int16 *
0x1803cd5b7  mov     edx, 104h; unsigned __int64
0x1803cd5bc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1803cd5c1  lea     rcx, [rsp+6B0h+psz2]; unsigned __int16 *
0x1803cd5c6  call    ?IsProgressPath@CDownloadFilePathUtilities@@SA_NPEBG@Z; CDownloadFilePathUtilities::IsProgressPath(ushort const *)
0x1803cd5cb  test    al, al
0x1803cd5cd  jz      short loc_1803CD5D9
0x1803cd5cf  lea     rcx, [rsp+6B0h+psz2]; pszPath
0x1803cd5d4  call    ?ConvertProgressPathToFinalPathInPlace@CDownloadFilePathUtilities@@SAJPEAG@Z; CDownloadFilePathUtilities::ConvertProgressPathToFinalPathInPlace(ushort *)
0x1803cd5d9  lea     rcx, [rsp+6B0h+psz2]; pszPath
0x1803cd5de  call    cs:__imp_PathStripPathW
0x1803cd5e5  nop     dword ptr [rax+rax+00h]
0x1803cd5ea  mov     rcx, [rbx+100h]; psz1
0x1803cd5f1  test    rcx, rcx
0x1803cd5f4  jz      short loc_1803CD619
0x1803cd5f6  cmp     dword ptr [rsi+8], 1
0x1803cd5fa  jz      loc_1803CD72A
0x1803cd600  lea     rdx, [rsp+6B0h+psz2]; psz2
0x1803cd605  call    cs:__imp_StrCmpW
0x1803cd60c  nop     dword ptr [rax+rax+00h]
0x1803cd611  test    eax, eax
0x1803cd613  jz      loc_1803CD72A
0x1803cd619  lea     rcx, pszPath; "filename"
0x1803cd620  call    cs:__imp_FindAtomW
0x1803cd627  nop     dword ptr [rax+rax+00h]
0x1803cd62c  movzx   edx, ax; unsigned __int16
0x1803cd62f  mov     rcx, rbx; this
0x1803cd632  call    ?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1803cd637  lea     rcx, aExtension; "extension"
0x1803cd63e  mov     r12, rax
0x1803cd641  call    cs:__imp_FindAtomW
0x1803cd648  nop     dword ptr [rax+rax+00h]
0x1803cd64d  movzx   edx, ax; unsigned __int16
0x1803cd650  mov     rcx, rbx; this
0x1803cd653  call    ?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1803cd658  mov     r14, rax
0x1803cd65b  test    r12, r12
0x1803cd65e  jz      loc_1803CD72A
0x1803cd664  test    rax, rax
0x1803cd667  jz      loc_1803CD72A
0x1803cd66d  lea     rdx, [rsp+6B0h+ppwsz]; ppwsz
0x1803cd672  mov     [rsp+6B0h+ppwsz], r13
0x1803cd677  lea     rcx, [rsp+6B0h+psz2]; psz
0x1803cd67c  call    cs:__imp_SHStrDupW
0x1803cd683  nop     dword ptr [rax+rax+00h]
0x1803cd688  cmp     [rsp+6B0h+ppwsz], r13
0x1803cd68d  jz      loc_1803CD72A
0x1803cd693  mov     rcx, [rbx+108h]; pv
0x1803cd69a  call    cs:__imp_CoTaskMemFree
0x1803cd6a1  nop     dword ptr [rax+rax+00h]
0x1803cd6a6  mov     rax, [rsp+6B0h+ppwsz]
0x1803cd6ab  lea     rcx, [rsp+6B0h+psz2]; pszPath
0x1803cd6b0  mov     [rbx+108h], rax
0x1803cd6b7  call    cs:__imp_PathFindExtensionW
0x1803cd6be  nop     dword ptr [rax+rax+00h]
0x1803cd6c3  mov     rdx, rax; unsigned __int16 *
0x1803cd6c6  mov     rcx, r14; this
0x1803cd6c9  call    ?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1803cd6ce  lea     rdx, [rsp+6B0h+psz2]; unsigned __int16 *
0x1803cd6d3  mov     rcx, r14; this
0x1803cd6d6  call    ?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x1803cd6db  lea     rdx, [rsp+6B0h+psz2]; unsigned __int16 *
0x1803cd6e0  mov     rcx, r12; this
0x1803cd6e3  call    ?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x1803cd6e8  lea     rdx, [rsp+6B0h+psz2]; unsigned __int16 *
0x1803cd6ed  mov     rcx, r12; this
0x1803cd6f0  call    ?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x1803cd6f5  mov     rax, [rbx]
0x1803cd6f8  lea     rdx, [rsp+6B0h+psz2]
0x1803cd6fd  mov     rcx, rbx
0x1803cd700  mov     rax, [rax+188h]
0x1803cd707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803cd70c  lea     rcx, [rsp+6B0h+psz2]; pszPath
0x1803cd711  call    cs:__imp_PathRemoveExtensionW
0x1803cd718  nop     dword ptr [rax+rax+00h]
0x1803cd71d  lea     rdx, [rsp+6B0h+psz2]; unsigned __int16 *
0x1803cd722  mov     rcx, r12; this
0x1803cd725  call    ?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1803cd72a  lea     rdx, [rbx+0F8h]; ppwsz
0x1803cd731  cmp     [rdx], r13
0x1803cd734  jnz     short loc_1803CD74E
0x1803cd736  test    r15, r15
0x1803cd739  jz      short loc_1803CD74E
0x1803cd73b  test    edi, edi
0x1803cd73d  jz      short loc_1803CD74E
0x1803cd73f  mov     rcx, r15; psz
0x1803cd742  call    cs:__imp_SHStrDupW
0x1803cd749  nop     dword ptr [rax+rax+00h]
0x1803cd74e  lea     rdx, [rbx+0F0h]; ppwsz
0x1803cd755  cmp     [rdx], r13
0x1803cd758  jnz     short loc_1803CD7A6
0x1803cd75a  test    r15, r15
0x1803cd75d  jz      short loc_1803CD7A6
0x1803cd75f  cmp     edi, 8
0x1803cd762  jz      short loc_1803CD769
0x1803cd764  cmp     edi, 0Bh
0x1803cd767  jnz     short loc_1803CD7A6
0x1803cd769  mov     rcx, r15; psz
0x1803cd76c  call    cs:__imp_SHStrDupW
0x1803cd773  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
