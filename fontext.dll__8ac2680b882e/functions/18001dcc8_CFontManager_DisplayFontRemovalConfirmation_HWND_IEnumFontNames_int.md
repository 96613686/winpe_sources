# CFontManager::_DisplayFontRemovalConfirmation(HWND__ *,IEnumFontNames *,int *)

- ea: `0x18001dcc8`
- end: `0x18001de13`
- name: `?_DisplayFontRemovalConfirmation@CFontManager@@AEAAJPEAUHWND__@@PEAUIEnumFontNames@@PEAH@Z`
- size: `331`
- prototype: `int(CFontManager *__hidden this, HWND, struct IEnumFontNames *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001cf38`

## callees

- `0x18001dcc8`
- `0x18001dff0`
- `0x18001e31c`
- `0x18001e8c4`
- `0x180032010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18001dd3f`
- `SHLWAPI!PathFindExtensionW` at `0x18001dd6d`
- `SHLWAPI!PathFindExtensionW` at `0x18001dd3f`
- `SHLWAPI!PathFindExtensionW` at `0x18001dd6d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dd5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dd8c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dd5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dd8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd9e`

## pseudocode

```c
__int64 __fastcall CFontManager::_DisplayFontRemovalConfirmation(
        CFontManager *this,
        HWND a2,
        struct IEnumFontNames *a3,
        int *a4)
{
  __int64 v4; // rax
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  const WCHAR *ExtensionW; // rax
  const WCHAR *v12; // rax
  CFontManager *v13; // rcx
  CFontManager *v14; // rcx
  CFontManager *v17; // [rsp+50h] [rbp+20h] BYREF
  LPCWSTR pszPath; // [rsp+60h] [rbp+30h] BYREF

  v17 = this;
  v4 = *(_QWORD *)a3;
  LODWORD(v17) = 0;
  v8 = (*(__int64 (__fastcall **)(struct IEnumFontNames *, CFontManager **))(v4 + 40))(a3, &v17);
  pszPath = 0;
  v9 = v8;
  if ( v8 >= 0 )
  {
    while ( 1 )
    {
      v10 = (*(__int64 (__fastcall **)(struct IEnumFontNames *, LPCWSTR *))(*(_QWORD *)a3 + 24LL))(a3, &pszPath);
      v9 = v10;
      if ( v10 < 0 || v10 == 1 )
        break;
      if ( (_DWORD)v17 )
      {
        ExtensionW = PathFindExtensionW(pszPath);
        if ( CompareStringOrdinal(L".PFB", -1, ExtensionW, -1, 1) == 2
          || (v12 = PathFindExtensionW(pszPath), CompareStringOrdinal(L".AFM", -1, v12, -1, 1) == 2) )
        {
          LODWORD(v17) = (_DWORD)v17 - 1;
        }
        CoTaskMemFree((LPVOID)pszPath);
      }
    }
  }
  (*(void (__fastcall **)(struct IEnumFontNames *))(*(_QWORD *)a3 + 32LL))(a3);
  if ( v9 >= 0 )
  {
    if ( (_DWORD)v17 )
    {
      if ( (unsigned int)CFontManager::_FontListHasNonTTCFonts(v13, a3) )
      {
        if ( (_DWORD)v17 == 1 )
          return (unsigned int)CFontManager::_DisplaySingleFontRemoveConfirmation(v14, a2, a3, a4);
        else
          return (unsigned int)CFontManager::_DisplayMultipleFontRemoveConfirmation(v14, a2, (unsigned int)v17, a4);
      }
      else
      {
        *a4 = 1;
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001dcc8  mov     [rsp-18h+arg_8], rbx
0x18001dccd  mov     [rsp-18h+arg_18], rsi
0x18001dcd2  mov     [rsp-18h+arg_0], rcx
0x18001dcd7  push    rbp
0x18001dcd8  push    rdi
0x18001dcd9  push    r14
0x18001dcdb  mov     rbp, rsp
0x18001dcde  sub     rsp, 30h
0x18001dce2  mov     rax, [r8]
0x18001dce5  mov     r14, rdx
0x18001dce8  lea     rdx, [rbp+arg_0]
0x18001dcec  mov     dword ptr [rbp+arg_0], 0
0x18001dcf3  mov     rcx, r8
0x18001dcf6  mov     rsi, r9
0x18001dcf9  mov     rdi, r8
0x18001dcfc  mov     rax, [rax+28h]
0x18001dd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd05  mov     [rbp+pszPath], 0
0x18001dd0d  mov     ebx, eax
0x18001dd0f  test    eax, eax
0x18001dd11  js      loc_18001DDA9
0x18001dd17  mov     rax, [rdi]
0x18001dd1a  lea     rdx, [rbp+pszPath]
0x18001dd1e  mov     rcx, rdi
0x18001dd21  mov     rax, [rax+18h]
0x18001dd25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd2a  mov     ebx, eax
0x18001dd2c  test    eax, eax
0x18001dd2e  js      short loc_18001DDA9
0x18001dd30  cmp     eax, 1
0x18001dd33  jz      short loc_18001DDA9
0x18001dd35  cmp     dword ptr [rbp+arg_0], 0
0x18001dd39  jbe     short loc_18001DD17
0x18001dd3b  mov     rcx, [rbp+pszPath]; pszPath
0x18001dd3f  call    cs:__imp_PathFindExtensionW
0x18001dd45  or      r9d, 0FFFFFFFFh; cchCount2
0x18001dd49  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x18001dd51  or      edx, r9d; cchCount1
0x18001dd54  lea     rcx, pszExt; ".PFB"
0x18001dd5b  mov     r8, rax; lpString2
0x18001dd5e  call    cs:__imp_CompareStringOrdinal
0x18001dd64  cmp     eax, 2
0x18001dd67  jz      short loc_18001DD97
0x18001dd69  mov     rcx, [rbp+pszPath]; pszPath
0x18001dd6d  call    cs:__imp_PathFindExtensionW
0x18001dd73  or      r9d, 0FFFFFFFFh; cchCount2
0x18001dd77  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x18001dd7f  or      edx, r9d; cchCount1
0x18001dd82  lea     rcx, aAfm; ".AFM"
0x18001dd89  mov     r8, rax; lpString2
0x18001dd8c  call    cs:__imp_CompareStringOrdinal
0x18001dd92  cmp     eax, 2
0x18001dd95  jnz     short loc_18001DD9A
0x18001dd97  dec     dword ptr [rbp+arg_0]
0x18001dd9a  mov     rcx, [rbp+pszPath]; pv
0x18001dd9e  call    cs:__imp_CoTaskMemFree
0x18001dda4  jmp     loc_18001DD17
0x18001dda9  mov     rax, [rdi]
0x18001ddac  mov     rcx, rdi
0x18001ddaf  mov     rax, [rax+20h]
0x18001ddb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddb8  test    ebx, ebx
0x18001ddba  js      short loc_18001DDFE
0x18001ddbc  cmp     dword ptr [rbp+arg_0], 0
0x18001ddc0  jnz     short loc_18001DDC9
0x18001ddc2  mov     ebx, 80004005h
0x18001ddc7  jmp     short loc_18001DDFE
0x18001ddc9  mov     rdx, rdi; struct IEnumFontNames *
0x18001ddcc  call    ?_FontListHasNonTTCFonts@CFontManager@@AEAAHPEAUIEnumFontNames@@@Z; CFontManager::_FontListHasNonTTCFonts(IEnumFontNames *)
0x18001ddd1  test    eax, eax
0x18001ddd3  jz      short loc_18001DDF8
0x18001ddd5  mov     r8d, dword ptr [rbp+arg_0]; unsigned int
0x18001ddd9  mov     r9, rsi; int *
0x18001dddc  mov     rdx, r14; HWND
0x18001dddf  cmp     r8d, 1
0x18001dde3  jnz     short loc_18001DDEF
0x18001dde5  mov     r8, rdi; struct IEnumFontNames *
0x18001dde8  call    ?_DisplaySingleFontRemoveConfirmation@CFontManager@@AEAAJPEAUHWND__@@PEAUIEnumFontNames@@PEAH@Z; CFontManager::_DisplaySingleFontRemoveConfirmation(HWND__ *,IEnumFontNames *,int *)
0x18001dded  jmp     short loc_18001DDF4
0x18001ddef  call    ?_DisplayMultipleFontRemoveConfirmation@CFontManager@@AEAAJPEAUHWND__@@KPEAH@Z; CFontManager::_DisplayMultipleFontRemoveConfirmation(HWND__ *,ulong,int *)
0x18001ddf4  mov     ebx, eax
0x18001ddf6  jmp     short loc_18001DDFE
0x18001ddf8  mov     dword ptr [rsi], 1
0x18001ddfe  mov     rsi, [rsp+30h+arg_18]
0x18001de03  mov     eax, ebx
0x18001de05  mov     rbx, [rsp+30h+arg_8]
0x18001de0a  add     rsp, 30h
0x18001de0e  pop     r14
0x18001de10  pop     rdi
0x18001de11  pop     rbp
0x18001de12  retn
```
